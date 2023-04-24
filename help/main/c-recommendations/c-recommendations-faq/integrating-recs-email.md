---
keywords: email, ESP, provedor de serviços de email, rawbox, API de entrega, modelo somente para download, modelo de email, processamento em lote, email de tempo de compilação
description: Saiba como integrar emails com a API de entrega, modelos rawbox e modelos apenas para download do Adobe [!DNL Target Recommendations], including using the [!DNL Target] .
title: Como integrar o Recommendations ao email?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 08fcb507-2c91-444a-b8ac-26165e359f6f
source-git-commit: 2a25fdb42ce4470f9126b7e0e7f6fd9e60c350e5
workflow-type: tm+mt
source-wordcount: '1715'
ht-degree: 96%

---

# Integrar o [!DNL Recommendations] ao email

O [!DNL Adobe Target] oferece suporte à personalização de hora de envio das recomendações de email.

Há três métodos disponíveis para integrar o [!DNL Target Recommendations] ao seu Provedor de serviços de email (ESP). Os recursos do ESP determinam qual método usar. Seu gerente de conta ou consultor pode ajudá-lo a escolher a melhor opção para você.

| Método | Detalhes |
| --- | --- |
| [Método 1: [!DNL Adobe Target Delivery API]](#delivery-api) (Preferencial) | Use o [!DNL Adobe Target Delivery API] para fazer solicitações de recomendações por cliente/por email. |
| [Método 2: [!DNL Adobe Rawbox API]](#rawbox) | Use o [!DNL Adobe Target Rawbox API] para fazer solicitações de recomendações por cliente/por email. |
| [Método 3: [!DNL Recommendations Download API]](#download-api) | Use a API de download do Recommendations para solicitar recomendações em massa para uma lista de produtos ou categorias no formato CSV. |

O uso do método 1 ou do método 2 exige que o ESP faça chamadas para uma API externa com base no cliente/email e aguarde o retorno do conteúdo. Estes métodos não são compatíveis com todos os ESPs; entre em contato com o seu ESP para descobrir se ele é compatível com esse padrão de integração.

O uso do método 3 exige que o ESP participe de uma lista de recomendações por ID de produto ou ID de categoria feita para a sua lista de emails. Esse método pode ser baseado em um atributo, como o último produto visualizado do cliente, o último produto comprado ou a categoria mais visualizada. No entanto, o ESP deve ter acesso a esses dados em seu perfil de cliente para realizar a associação. Entre em contato com o seu ESP para descobrir se ele tem acesso a esses dados e é compatível com esse padrão de integração.

A personalização de recomendações de tempo aberto não é compatível com o [!DNL Adobe Target].

>[!IMPORTANT]
>
>As seguintes diretrizes de capacidade se aplicam aos métodos da API de entrega e do modelo de email de rawbox descritos abaixo (métodos 1 e 2):
>
>* As solicitações devem ser limitadas à uma taxa pequena de 1.000 solicitações por segundo, ou 25 vezes o pico de tráfego diário.
>* Aumentar o tráfego em etapas de 200 solicitações por segundo a cada minuto.
> 
>Entre em contato com seu gerente de contas se desejar usar limites de taxas mais altos.

## Método 1: usar a API de entrega (preferencial) {#delivery-api}

A API de entrega é uma solicitação POST que funciona com o email de tempo de criação. Essa opção é o método preferencial para o email de tempo de criação.

A maioria dos clientes de email não permite solicitações POST; portanto, essa API não é recomendada para os casos de uso de tempo aberto. Alguns clientes de email, como o Gmail ou o Outlook, podem armazenar o conteúdo em cache ou bloquear a imagem e exigir que o recipient permita que ela seja processada.

Não é possível retornar o conteúdo padrão usando a API de entrega.

O código a seguir é um exemplo de solicitação de entrega da API:

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

Onde `clientcode` é o código de cliente do [!DNL Target].

>[!NOTE]
>
>Certifique-se de fornecer um valor único para ambas `sessionId` e um dos `tntId` ou `thirdPartyId` para cada destinatário de email (por exemplo, para cada chamada de API). Se você não fornecer valores exclusivos para esses campos, a resposta da API poderá ser lenta ou falhar devido ao grande número de eventos gerados em um único perfil.

Consulte a [Documentação da API de entrega](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/delivery-api/overview.html) para obter mais informações.{target=_blank}

## Método 2: usar um modelo de email de rawbox {#rawbox}

Uma rawbox é semelhante a uma solicitação de mbox, mas para ambientes fora da Web, como provedores de serviços de email (ESPs). Como você não tem o [!DNL Adobe Experience Platform Web SDK] ou a [!DNL at.js] para usar em solicitações de rawbox, deve criar suas solicitações manualmente. Os exemplos abaixo explicam como trabalhar com solicitações de rawbox no email.

>[!NOTE]
>
>Ao usar um rawbox e o [!DNL Target], consulte o aviso de segurança importante em [Criar listas de permissões que especificam hosts autorizados a enviar chamadas de mbox para o [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist).

Essa abordagem permite rastrear o desempenho das recomendações em emails, testá-las da maneira normal com uma recomendação, e continuar a rastrear o site.

Defina uma atividade de [!DNL Recommendations] no [!DNL Target] usando a opção [Criador de experiências baseado em formulários](/help/main/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E). Para o local, selecione o nome da mbox escolhido para usar na solicitação de rawbox proveniente do ESP. Selecione um design com a aparência desejada para o seu email. No momento da criação do email, o ESP faz uma chamada aos servidores do [!DNL Target] para cada rawbox em cada email gerado. Seu ESP deve ter uma maneira de incluir o HTML retornado no email quando ele for enviado.

O sistema de email usado deve ser capaz de lidar com os seguintes cenários:

### Uma resposta válida é recebida, mas nenhuma recomendação está presente

* Neste caso, a resposta será o que for definido como o valor do parâmetro `mboxDefault`. Veja a explicação abaixo sobre este parâmetro.
* O provedor de email deve ter um bloco HTML padrão de recomendações para usar neste caso.

### O servidor do [!DNL Target] atinge o limite de tempo e retorna sem dados

* Nesse caso, o servidor do [!DNL Target] retorna o seguinte conteúdo:

   `//ERROR: application server timeout`

* O aplicativo de email deve procurar esse texto e ser capaz de lidar com o erro. O provedor de email tem várias opções para lidar com este caso:

   * Tentar outra chamada de servidor imediatamente (recomendado, talvez com um contador de tentativas).
   * Descartar esse email específico e continuar com o próximo.
   * Colocar esse email específico na fila e executar novamente os emails com falha em lote no final da execução inicial.

### Exemplo de URL de solicitação

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Parâmetros obrigatórios: {#reqparams}

>[!NOTE]
>
>Para usar o [!DNL Recommendations] no email, a chamada rawbox geralmente deve incluir `entity.id`, `entity.categoryId` ou ambos, dependendo do tipo de critérios de recomendação. O exemplo de chamada acima inclui ambas.

| Parâmetro | Valor | Descrição | Validação |
|--- |--- |--- |--- |
| `client_code` | *client_code* | O código do cliente usado no Recommendations. Seu consultor da Adobe pode fornecer esse valor. |  |
| `mbox` | *mboxName* | O nome da mbox usado para direcionamento. | Mesma validação que para todas as chamadas de mbox.<br>Limite de 250 caracteres.<br>Não pode conter nenhum dos seguintes caracteres: `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | desativado | Impede que a resposta configure um cookie em ambientes não-Web. |  |
| `entity.id`<br>(Obrigatório para determinados tipos de critérios: exibir/exibir, exibir/comprado, comprado/comprado) | *entity_id* | A productId na qual a recomendação se baseia, como um produto abandonado no carrinho ou uma compra anterior.<br>Se exigido pelos critérios, a chamada de rawbox deve incluir a `entity.id`. |  |
| `entity.event.detailsOnly` | true | Se `entity.id` for transmitido, é altamente recomendável também transmitir esse parâmetro para evitar que a solicitação incremente o número de exibições de página contadas para um item, a fim de não distorcer os algoritmos baseados na visualização do produto. |  |
| `entity.categoryId`<br>(Obrigatório para determinados tipos de critérios: mais vistos por categoria e mais vendidos por categoria) | *category_id* | A categoria na qual a recomendação se baseia, como os mais vendidos em uma categoria.<br>Se exigido pelos critérios, a chamada de rawbox deve incluir a `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Se o parâmetro `mboxNoRedirect` não estiver presente, `mboxDefault` deverá ser um URL absoluto que retornará o conteúdo padrão se nenhuma recomendação estiver disponível. Esse URL pode ser uma imagem ou outro conteúdo estático.<br>Se o parâmetro `mboxNoRedirect` estiver presente, `mboxDefault` poderá ser qualquer texto indicando que não há recomendações, por exemplo `no_content`.<br>O provedor de email precisa tratar os casos em que esse valor for retornado e inserir o HTML padrão no email. <br> **Prática recomendada de segurança**: se o domínio usado no URL `mboxDefault` não estiver na lista de permissões, você poderá ser exposto ao risco de uma vulnerabilidade de redirecionamento aberto. Para evitar o uso não autorizado de links redirecionadores ou `mboxDefault` por terceiros, a Adobe recomenda qusar &quot;hosts autorizados&quot; para permitir a lista de domínios de URL de redirecionamento padrão. O Target usa hosts para a lista de permissões de domínios aos quais você deseja permitir redirecionamentos. Para obter mais informações, consulte [Criar lista de permissões que especificam hosts autorizados a enviar chamadas de mbox para o  [!DNL Target]](/help/main/administrating-target/hosts.md#allowlist) em *Hosts*. |  |
| `mboxHost` | *mbox_host* | Este é o domínio que é adicionado ao ambiente padrão (grupo de hosts) quando a chamada é acionada. |  |
| `mboxPC` | Vazio | (Obrigatório para recomendações que usam o perfil de um visitante.)<br>Se nenhum &quot;thirdPartyId&quot; for fornecido, um novo tntId será gerado e retornado como parte da resposta. Caso contrário, fica vazio.<br>**Observação:** certifique-se de fornecer um valor exclusivo de `mboxSession` e `mboxPC` para cada destinatário de email (ou seja, para cada chamada de API). Se você não fornecer valores exclusivos para esses campos, a resposta da API poderá ser lenta ou falhar devido ao grande número de eventos gerados em um único perfil. | 1 &lt; Comprimento &lt; 128<br>Não pode conter mais do que um único “.” (ponto).<br>O único ponto permitido é para o sufixo de localização do perfil. |

### Parâmetros opcionais

| Parâmetro | Valor | Descrição | Validação |
|--- |--- |--- |--- |
| `mboxPC`<br>(Opcional) | *mboxPCId* | ID de visitante do Target. Use esse valor quando quiser acompanhar um círculo completo do usuário de volta ao seu site em várias visitas ou ao usar um parâmetro de perfil do usuário.<br>Esse valor precisa ser o PCID real do [!DNL Adobe Target] para o usuário, que seria exportado do site para o seu CRM. O provedor de email recuperaria essa ID do seu CRM ou Data Warehouse e o usaria como o valor desse parâmetro.<br>O valor `mboxPC` também é útil para acompanhar o comportamento do visitante no site em várias visitas para o rastreamento de métricas quando uma recomendação fizer parte de uma atividade A/B.<br>**Observação:** certifique-se de fornecer um valor exclusivo de `mboxSession` e `mboxPC` para cada destinatário de email (ou seja, para cada chamada de API). Se você não fornecer valores exclusivos para esses campos, a resposta da API poderá ser lenta ou falhar devido ao grande número de eventos gerados em um único perfil. | 1 &lt; Comprimento &lt; 128<br>Não pode conter mais do que um único “.” (ponto).<br>O único ponto permitido é para o sufixo de localização do perfil. |
| `mboxNoRedirect`<br>(Opcional) | 1 | Por padrão, o chamador é redirecionado quando nenhum conteúdo entregável é encontrado. Use para desativar o comportamento padrão. |  |
| `mbox3rdPartyId` | *xxx* | Use essa opção se você tiver sua própria ID de visitante personalizado para usar para direcionamento de perfil. |  |

### Possíveis respostas do servidor do [!DNL Target]

| Resposta | Descrição |
|--- |--- |
| //ERROR: | Gerado pelo balanceador de carga quando não é capaz de retornar o conteúdo |
| Sucesso | O parâmetro `mboxNoRedirect` é definido como &quot;true&quot; e o servidor não retorna nenhuma recomendação (ou seja, não há correspondência para a mbox ou o cache do servidor não foi inicializado). |
| bad request | O parâmetro da `mbox` está ausente.<ul><li>O parâmetro `mboxDefault` ou `mboxNoRedirect` não foi especificado.</li><li>O parâmetro de rastreamento `mboxTrace` está especificado, mas `mboxNoRedirect` não está.</li><li>O parâmetro `mboxTarget` não é especificado quando os nomes das mboxes terminam com o sufixo `-clicked`.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | `mboxDefault` não especificado quando não existe correspondência para a solicitação e o parâmetro `mboxNoRedirect` não é especificado. |
| `Invalid mbox name:= MBOX_NAME` | Indica que o parâmetro da `mbox` contém caracteres inválidos. |
| `Mbox name [MBOX_NAME] is too long` | Indica que o parâmetro da `mbox` excede 250 caracteres. |

## Método 3: usar a API de download do Recommendations {#download-api}

Defina uma recomendação como de costume, mas escolha **somente download** na seção de apresentação ao invés de uma combinação de modelo e mbox. Depois, no ESP, diga ao ESP qual ID de recomendação você criou. O ESP acessa os dados da recomendação por meio de API. Esses dados mostram quais itens devem ser recomendados para determinada categoria ou item-chave, como itens em um carrinho abandonado. O ESP armazena esses dados, conecta-os com sua própria aparência, exibe informações sobre cada item e envia isso por email.

Com essa opção, o servidor de recomendações não poderá acompanhar diretamente o desempenho de uma recomendação ou dividir o tráfego entre múltiplas combinações de algoritmo/modelo. Além disso, as recomendações não estão vinculadas a um perfil de visitante.

Para obter mais informações sobre como baixar a API, consulte [APIs herdadas > Baixar](/help/main/assets/adobe-recommendations-classic.pdf).
