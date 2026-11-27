---
keywords: email, ESP, provedor de serviços de email, rawbox, API de entrega, modelo somente para download, modelo de email, processamento em lote, email de tempo de compilação
description: Saiba como integrar emails com o Adobe [!DNL Target Recommendations], incluindo o uso da API de entrega, modelos rawbox e modelos apenas para download do [!DNL Target].
title: Como integrar o Recomendações ao email?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
TQID: 'https://experienceleague.adobe.com/ZyeOl6ysM03a0mMiNgHuicOLPfgpXnrdqXJE1gHRRvE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '1741'
ht-degree: 26%
---
# Integrar [!DNL Recommendations] ao email {#integrate-recs-email}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba mais sobre os métodos de integração do [!DNL Target Recommendations] com um Provedor de Serviços de Email (ESP) para personalização de hora de envio das recomendações de email.

>[!ENDSHADEBOX]

O [!DNL Adobe Target] oferece suporte à personalização de hora de envio das recomendações de email. A personalização de recomendações de tempo aberto não é compatível.

Três métodos estão disponíveis para integrar [!DNL Target Recommendations] com um ESP. Os recursos do ESP determinam qual método usar, e o gerente de conta ou consultor pode ajudar a escolher a melhor opção.

| Método | Detalhes |
| --- | --- |
| [Método 1: [!DNL Adobe Target Delivery API]](#delivery-api) (Preferencial) | Use o [!DNL Adobe Target Delivery API] para fazer solicitações de recomendações por cliente e por email. |
| [Método 2: [!DNL Adobe Rawbox API]](#rawbox) | Use o [!DNL Adobe Target Rawbox API] para fazer solicitações de recomendações por cliente e por email. |
| [Método 3: [!DNL Recommendations Download API]](#download-api) | Use o [!DNL Recommendations Download API] para solicitar recomendações em massa para uma lista de produtos ou categorias no formato CSV. |

Os métodos 1 e 2 exigem que o ESP faça chamadas para uma API externa com base no cliente por email e aguarde o retorno do conteúdo. Nem todos os ESPs suportam esses métodos, portanto, o ESP deve ser contatado para determinar se é compatível com esse padrão de integração.

O método 3 exige que o ESP participe de uma lista de recomendações por ID de produto ou ID de categoria à lista de emails. Essa associação pode ser baseada em um atributo, como o último produto visualizado, o último produto comprado ou a categoria mais visualizada do cliente. O ESP deve ter acesso a esses dados em seu perfil de cliente para executar a associação, portanto, o ESP deve ser contatado para determinar se tem acesso a esses dados e é compatível com esse padrão de integração.

>[!IMPORTANT]
>
>As seguintes diretrizes de capacidade se aplicam aos métodos da API de entrega e do modelo de email de rawbox (métodos 1 e 2):
>
>* As solicitações devem ser limitadas à taxa mais baixa de 1.000 solicitações por segundo ou 25 vezes o pico de tráfego diário.
>* O tráfego deve ser aumentado em etapas de 200 solicitações por segundo a cada minuto.
>
>Para usar limites de taxa mais altos, entre em contato com o gerente da conta.

## Método 1: usar a API de entrega (preferencial) {#delivery-api}

A API de entrega é uma solicitação POST que funciona com email de tempo de compilação. Essa opção é o método preferencial para o email de tempo de criação.

A maioria dos clientes de email não permite solicitações POST, portanto, essa API não é recomendada para casos de uso de tempo aberto. Alguns clientes de email, como o Gmail ou o Outlook, podem armazenar o conteúdo em cache ou bloquear a imagem e exigir que o recipient permita que ela seja processada de forma proativa.

O conteúdo padrão não pode ser retornado com a API de entrega.

O código a seguir é um exemplo de solicitação de entrega de API, em que `clientcode` é o código de cliente [!DNL Target]:

```javascript
curl -X POST \ 
  'https://clientcode.tt.omtrdc.net/rest/v1/mbox/?client=clientcode' \ 
  -H 'authorization: Bearer 3423614b-4843-4664-83c4-c6c3f6c8869b' \ 
  -H 'cache-control: no-cache' \ 
  -H 'content-type: application/json' \ 
  -d '{ 
  "mbox" : "email-mbox", 
  "tntId" : "111499796294071-449025.28_44", 
  "requestLocation" : { 
    "host" : "prod" 
  }, 
   "profileParameters" : { 
   }, 
  "mboxParameters" : { 
    "at_property": "b468a242-64a4-32a0-ca0c-890bddd78789", 
    "entity.id": "article-123", 
    "entity.event.detailsOnly" : "true" 
  } 
  "contentAsJson":  true 
}'
```

>[!NOTE]
>
>Forneça um valor exclusivo para `sessionId` e um dos `tntId` ou `thirdPartyId` para cada destinatário de email (para cada chamada de API). Sem valores exclusivos para esses campos, a resposta da API pode ser lenta ou falhar devido ao grande número de eventos gerados em um único perfil.

Para obter mais informações, consulte a [Documentação da API de entrega](https://experienceleague.adobe.com/docs/target-dev/developer/api/delivery-api/overview.html?lang=pt-BR){target=_blank}.

## Método 2: usar um modelo de email de rawbox {#rawbox}

Uma rawbox é semelhante a uma solicitação de mbox, mas para ambientes fora da Web, como provedores de serviços de email (ESPs). O [!DNL Adobe Experience Platform Web SDK] e o [!DNL at.js] não estão disponíveis para solicitações de rawbox, portanto, as solicitações devem ser criadas manualmente. Os exemplos a seguir explicam como trabalhar com solicitações de rawbox no email.

Essa abordagem permite rastrear o desempenho das recomendações em emails, testando-as da maneira normal com uma recomendação e continuando o rastreamento no site.

>[!NOTE]
>
>Ao usar um rawbox e o [!DNL Target], consulte o aviso de segurança importante em [Criar listas de permissões que especificam hosts autorizados a enviar chamadas de mbox para o [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist).

1. Configure uma atividade [!DNL Recommendations] em [!DNL Target], com a opção [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

1. Para o local, selecione o nome da mbox usada na solicitação de rawbox proveniente do ESP.

1. Selecione um design com a aparência desejada para o email.

No momento da criação do email, o ESP faz uma chamada aos servidores do [!DNL Target] para cada rawbox em cada email gerado. O ESP deve ter uma maneira de incluir o HTML retornado no email quando ele for enviado.

O sistema de email deve ser capaz de lidar com os seguintes cenários.

### Uma resposta válida é recebida, mas nenhuma recomendação está presente

* A resposta é o valor definido no parâmetro `mboxDefault`. Consulte a descrição desse parâmetro na tabela de parâmetros obrigatórios.
* O provedor de email deve ter um bloco HTML padrão de recomendações para usar neste caso.

### O servidor do [!DNL Target] atinge o limite de tempo e retorna sem dados

* O servidor [!DNL Target] retorna o seguinte conteúdo:

  `//ERROR: application server timeout`

* O aplicativo de email deve procurar esse texto e ser capaz de lidar com o erro. O provedor de email tem várias opções para lidar com este caso:

  * Tentar outra chamada de servidor imediatamente (recomendado, talvez com um contador de tentativas).
  * Descarte esse email específico e continue para o próximo.
  * Colocar esse email específico na fila e executar novamente os emails com falha em lote no final da execução inicial.

### Exemplo de URL de solicitação

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Parâmetros obrigatórios {#reqparams}

>[!NOTE]
>
>Para usar [!DNL Recommendations] no email, a chamada rawbox geralmente deve incluir `entity.id` ou `entity.categoryId`, ou ambos, dependendo do tipo de critérios de recomendação. O exemplo de chamada acima inclui ambas.

| Parâmetro | Valor | Descrição | Validação |
|--- |--- |--- |--- |
| `client_code` | *client_code* | O código de cliente usado em [!DNL Recommendations]. O consultor da Adobe pode fornecer esse valor. |  |
| `mbox` | *mboxName* | O nome da mbox usado para direcionamento. | Mesma validação que para todas as chamadas de mbox. Limite de <br> 250 caracteres.<br>Não pode conter nenhum dos seguintes caracteres: `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | desativado | Impede que a resposta configure um cookie em ambientes não-Web. |  |
| `entity.id`<br>(Obrigatório para determinados tipos de critérios: exibir/exibir, exibir/comprado, comprado/comprado) | *entity_id* | A productId na qual a recomendação se baseia, como um produto abandonado no carrinho ou uma compra anterior.<br>Se exigido pelos critérios, a chamada de rawbox deve incluir a `entity.id`. |  |
| `entity.event.detailsOnly` | true | Se `entity.id` for passado, é altamente recomendável passar esse parâmetro, para evitar que a solicitação incremente o número de exibições de página contadas para um item, a fim de não distorcer os algoritmos baseados na visualização do produto. |  |
| `entity.categoryId`<br>(Obrigatório para determinados tipos de critérios: mais vistos por categoria e mais vendidos por categoria) | *category_id* | A categoria em que a recomendação se baseia, como os mais vendidos em uma categoria.<br>Se exigido pelos critérios, a chamada de rawbox deve incluir a `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Se o parâmetro `mboxNoRedirect` não estiver presente, `mboxDefault` deverá ser um URL absoluto que retornará o conteúdo padrão se nenhuma recomendação estiver disponível. Esse URL pode ser uma imagem ou outro conteúdo estático.<br>Se o parâmetro `mboxNoRedirect` estiver presente, `mboxDefault` poderá ser qualquer texto que indique que não há recomendações, por exemplo `no_content`.<br>O provedor de email deverá tratar os casos em que esse valor for retornado e inserir o HTML padrão no email.<br>Consulte a prática recomendada de segurança abaixo das tabelas. |  |
| `mboxHost` | *mbox_host* | Este é o domínio que é adicionado ao ambiente padrão (grupo de hosts) quando a chamada é acionada. |  |
| `mboxPC` | Vazio | (Obrigatório para recomendações que usam o perfil de um visitante.)<br>Se nenhum &quot;thirdPartyId&quot; for fornecido, um novo tntId será gerado e retornado como parte da resposta. Caso contrário, o valor permanecerá vazio.<br>Consulte a observação sobre valores únicos abaixo das tabelas. | 1 &lt; Comprimento &lt; 128<br>Não pode conter mais do que um único “.” (ponto).<br>O único ponto permitido é para o sufixo de localização do perfil. |

### Parâmetros opcionais

| Parâmetro | Valor | Descrição | Validação |
|--- |--- |--- |--- |
| `mboxPC`<br>(Opcional) | *mboxPCId* | A ID de visitante [!DNL Target]. Use esse valor para rastrear um círculo completo de usuário de volta ao site em várias visitas ou ao usar um parâmetro de perfil do usuário.<br>Esse valor deve ser o PCID [!DNL Adobe Target] real do usuário, que é exportado do site para o CRM. O provedor de email recupera essa ID do CRM ou do data warehouse e a usa como o valor desse parâmetro.<br>O valor `mboxPC` também é útil para acompanhar o comportamento do visitante no site em várias visitas para o rastreamento de métricas, quando uma recomendação fizer parte de uma atividade A/B.<br>Consulte a observação sobre valores únicos abaixo das tabelas. | 1 &lt; Comprimento &lt; 128<br>Não pode conter mais do que um único “.” (ponto).<br>O único ponto permitido é para o sufixo de localização do perfil. |
| `mboxNoRedirect`<br>(Opcional) | 1 | Por padrão, o chamador é redirecionado quando nenhum conteúdo entregável é encontrado. Use esse parâmetro para desativar o comportamento padrão. |  |
| `mbox3rdPartyId` | *xxx* | Use essa opção para especificar uma ID de visitante personalizada para direcionamento de perfil. |  |

Para `mboxSession` e `mboxPC`, forneça um valor exclusivo para cada destinatário de email (para cada chamada de API). Sem valores exclusivos para esses campos, a resposta da API pode ser lenta ou falhar devido ao grande número de eventos gerados em um único perfil.

Como prática recomendada de segurança para `mboxDefault`, use hosts autorizados para incluir na lista de permissões os domínios de URL de redirecionamento padrão. Se o domínio usado na URL `mboxDefault` não for exibido, é possível expor um risco de vulnerabilidade de redirecionamento aberto. Hosts autorizados evitam o uso não autorizado de links redirecionadores ou `mboxDefault` por terceiros. [!DNL Target] usa hosts para incluir na lista de permissões os domínios para os quais os redirecionamentos são permitidos. Para obter mais informações, consulte o aviso de segurança no início desta seção.

### Possíveis respostas do servidor do [!DNL Target]

| Resposta | Descrição |
|--- |--- |
| //ERROR: | Gerado pelo balanceador de carga quando não é possível retornar o conteúdo. |
| Sucesso | O parâmetro `mboxNoRedirect` está definido como &#39;true&#39; e o servidor não retorna nenhuma recomendação (não há correspondência para a mbox ou o cache do servidor não foi inicializado). |
| bad request | O parâmetro da `mbox` está ausente.<ul><li>O parâmetro `mboxDefault` ou `mboxNoRedirect` não foi especificado.</li><li>O parâmetro de solicitação `mboxTrace` está especificado, mas `mboxNoRedirect` não está.</li><li>O parâmetro `mboxTarget` não é especificado quando os nomes das mboxes terminam com o sufixo `-clicked`.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | `mboxDefault` não é especificado quando não existe correspondência para a solicitação e o parâmetro `mboxNoRedirect` não é especificado. |
| `Invalid mbox name:= MBOX_NAME` | O parâmetro `mbox` contém caracteres inválidos. |
| `Mbox name [MBOX_NAME] is too long` | O parâmetro `mbox` tem mais de 250 caracteres. |

## Método 3: usar a API de download do Recomendações {#download-api}

Defina uma recomendação como de costume, mas escolha **somente download** na seção de apresentação ao invés de uma combinação de modelo e mbox. Em seguida, forneça ao ESP a ID da recomendação que foi criada. O ESP acessa os dados da recomendação por meio da API. Esses dados mostram quais itens devem ser recomendados para determinada categoria ou item-chave, como itens em um carrinho abandonado. O ESP armazena esses dados, conecta-os com sua própria aparência, exibe informações sobre cada item e os entrega nos emails.

Com essa opção, o servidor de recomendações não pode acompanhar diretamente o desempenho de uma recomendação ou dividir o tráfego em várias combinações de algoritmo e modelo. Além disso, as recomendações não estão vinculadas a um perfil de visitante.

Para obter mais informações sobre como baixar a API, consulte [APIs herdadas > Baixar](/help/main/assets/adobe-recommendations-classic.pdf).
