---
keywords: email, ESP, provedor de serviços de email, rawbox, API de entrega, modelo somente para download, modelo de email, processamento em lote, email de tempo de compilação
description: Saiba como integrar e-mail à Adobe Target Recommendations, incluindo o uso da API do Delivery do Público alvo, modelos de rawbox e modelos somente para download.
title: Como integrar o Recommendations ao email?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1490'
ht-degree: 90%

---


# ![PREMIUM](/help/assets/premium.png) Integrar o Recommendations com o email{#integrate-recommendations-with-email}

Informações sobre como integrar o email ao Recommendations.

Os recursos do seu provedor de serviços de email determinam qual método utilizar. Seu gerente de conta ou consultor pode ajudá-lo a escolher a melhor opção para você.

## Opção 1: usar a API de entrega {#section_9F00D271BABA4B7390B461F4C44EC319}

A API de entrega é uma solicitação POST que funciona com o email de tempo de criação. Essa opção é o método preferencial para o email de tempo de criação.

A maioria dos clientes de email não permite solicitações POST; portanto, essa API não é recomendada para os casos de uso em tempo aberto. Alguns clientes de email, como o Gmail ou o Outlook, podem armazenar o conteúdo em cache ou bloquear a imagem e exigir que o destinatário permita que ela seja processada.

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

Onde `clientcode` é o código de cliente do Target.

>[!NOTE]
>
>Certifique-se de fornecer um valor único para ambas `sessionId` e um dos `tntId` ou `thirdPartyId` para cada destinatário de email (por exemplo, para cada chamada de API). Se você não fornecer valores únicos para esses campos, a resposta da API pode ser lenta ou falhar devido ao grande número de eventos gerados em um único perfil.

Consulte a [Documentação da API de entrega](https://developers.adobetarget.com/api/#server-side-delivery) para obter mais informações.

## Opção 2: Usar um modelo de email rawbox {#section_C0D48A42BCCE45D6A68852F722C7C352}

Uma rawbox é semelhante a uma solicitação de mbox, mas para ambientes não-Web, como provedores de serviços de email (ESPs). Como você não tem [!DNL mbox.js] ou [!DNL at.js] para usar nas solicitações de rawbox, deve criar as solicitações manualmente. Os exemplos abaixo explicam como trabalhar com solicitações de rawbox no email.

>[!NOTE]
>
>Ao usar uma rawbox e [!DNL Target], consulte o aviso de segurança importante em [Criar lista de permissões que especificam hosts autorizados a enviar chamadas de mbox para o Público alvo](/help/administrating-target/hosts.md#allowlist).

Essa abordagem permite rastrear o desempenho das recomendações em emails, testá-las da maneira normal com uma recomendação, e continuar a rastrear o site.

Defina uma atividade de [!DNL Recommendations] no [!DNL Adobe Target] usando a opção [Criador de experiências baseado em formulários](/help/c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E). Para o local, selecione o nome da mbox escolhido para usar na solicitação de rawbox proveniente do ESP. Selecione um design com a aparência desejada para o seu email. No momento da criação do email, o ESP faz uma chamada aos servidores do [!DNL Adobe Target] para cada rawbox em cada email gerado. Seu ESP deve ter uma maneira de incluir o HTML retornado no email quando ele for enviado.

O sistema de email usado deve ser capaz de lidar com esses cenários:

### Uma resposta válida é recebida, mas nenhuma recomendação está presente

* Neste caso, a resposta será o que for definido como o valor do parâmetro mboxDefault. Veja a explicação abaixo sobre este parâmetro.
* O provedor de email deve ter um bloco HTML padrão de recomendações para usar neste caso.

### O servidor do Target atinge o limite de tempo e não retorna dados

* Nesse caso, o servidor do Target retornará o seguinte conteúdo:

   `//ERROR: application server timeout`

* O aplicativo de email deve procurar esse texto e ser capaz de lidar com o erro. O provedor de email tem várias opções para lidar com este caso:

   * Tentar outra chamada de servidor imediatamente (recomendado, talvez com um contador de tentativas).
   * Descartar esse email específico e continuar com o próximo.
   * Colocar esse email específico na fila e executar novamente os emails com falha como um lote no final da execução inicial.

### Exemplo de URL de solicitação

```
https://client_code.tt.omtrdc.net/m2/client_code/ubox/raw?mbox=mbox_name&mboxSession=1396032094853-955654&mboxPC=1396032094853-955654&mboxXDomain=disabled&entity.event.detailsOnly=true&mboxDefault=nocontent&mboxNoRedirect=1&entity.id=2A229&entity.categoryId=5674
```

### Parâmetros obrigatórios: {#reqparams}

>[!NOTE]
>
>Para usar as [!DNL Recommendations] nos emails, a chamada da rawbox geralmente deve incluir a `entity.id` ou `entity.categoryId`, ou ambas, dependendo do tipo de critério de recomendação. O exemplo de chamada acima inclui ambas.

| Parâmetro | Valor | Descrição | Validação |
|--- |--- |--- |--- |
| `client_code` | *client_code* | O código do cliente usado nas Recommendations. Seu consultor da Adobe pode fornecer esse valor. |  |
| `mbox` | *mboxName* | O nome da mbox usado para direcionamento. | Mesma validação que para todas as chamadas de mbox.<br>Limite de 250 caracteres.<br>Não pode conter nenhum dos seguintes caracteres: `', ", %22, %27, <, >, %3C, %3E` |
| `mboxXDomain` | desativado | Impede que a resposta configure um cookie em ambientes não-Web. |  |
| `entity.id`<br>(Obrigatório para determinados tipos de critérios: exibir/exibir, exibir/comprado, comprado/comprado) | *entity_id* | A productId na qual a recomendação se baseia, como um produto abandonado no carrinho ou uma compra anterior.<br>Se exigido pelos critérios, a chamada de rawbox deve incluir a `entity.id`. |  |
| `entity.event.detailsOnly` | true | Se `entity.id` for transmitido, é altamente recomendável também transmitir esse parâmetro para evitar que a solicitação incremente o número de exibições de página contadas para um item, a fim de não distorcer os algoritmos baseados na visualização do produto. |  |
| `entity.categoryId`<br>(Obrigatório para determinados tipos de critérios: mais vistos por categoria e mais vendidos por categoria) | *category_id* | A categoria na qual a recomendação se baseia, como os mais vendidos em uma categoria.<br>Se exigido pelos critérios, a chamada de rawbox deve incluir a `entity.categoryId`. |  |
| `mboxDefault` | *`https://www.default.com`* | Se o parâmetro `mboxNoRedirect` não estiver presente, `mboxDefault` deverá ser um URL absoluto que retornará o conteúdo padrão se nenhuma recomendação estiver disponível. Pode ser uma imagem ou outro conteúdo estático.<br>Se o parâmetro `mboxNoRedirect` estiver presente, `mboxDefault` poderá ser qualquer texto indicando que não há recomendações, por exemplo `no_content`.<br>O provedor de email precisará lidar com o caso em que esse valor é retornado e inserir o HTML padrão no email.  <br> **Práticas** recomendadas de segurança: Observe que se o domínio usado no  `mboxDefault` URL não for incluir na lista de permissões, você poderá ser exposto a um risco de vulnerabilidade de redirecionamento aberto. Para evitar o uso não autorizado de links do Redirecionador ou `mboxDefault` por terceiros, recomendamos que você use &quot;hosts autorizados&quot; para lista de permissões os domínios de URL de redirecionamento padrão. O público alvo usa hosts para lista de permissões domínios para os quais você deseja permitir redirecionamentos. Para obter mais informações, consulte [Criar Lista de permissões que especificam hosts autorizados a enviar chamadas de mbox para o Público alvo](/help/administrating-target/hosts.md#allowlist) em *Hosts*. |  |
| `mboxHost` | *mbox_host* | Este é o domínio que é adicionado ao ambiente padrão (grupo de hosts) quando a chamada é acionada. |  |
| `mboxPC` | Empty | (Obrigatório para recomendações que usam o perfil de um visitante.)<br>Se nenhum &quot;thirdPartyId&quot; for fornecido, um novo tntId será gerado e retornado como parte da resposta. Caso contrário, fica vazio.<br>**Observação:** certifique-se de fornecer um valor exclusivo de `mboxSession` e `mboxPC` para cada destinatário de email (ou seja, para cada chamada de API). Se você não fornecer valores únicos para esses campos, a resposta da API pode ser lenta ou falhar devido ao grande número de eventos gerados em um único perfil. | 1 &lt; Comprimento &lt; 128<br>Não pode conter mais do que um único “.” (ponto).<br>O único ponto permitido é para o sufixo de localização do perfil. |

### Parâmetros opcionais

| Parâmetro | Valor | Descrição | Validação |
|--- |--- |--- |--- |
| `mboxPC`<br>(Opcional) | *mboxPCId* | ID de visitante do Target. Use esse valor quando quiser acompanhar um círculo completo do usuário de volta ao seu site em várias visitas ou ao usar um parâmetro de perfil do usuário.<br>Esse valor precisa ser a PCID real do Adobe Target para o usuário, que seria exportado do site para o seu CRM. O provedor de email recuperaria essa ID do seu CRM ou data warehouse e o usaria como o valor desse parâmetro.<br>O valor `mboxPC` também é útil para acompanhar o comportamento do visitante no site em várias visitas para o rastreamento de métricas quando uma recomendação fizer parte de uma atividade A/B.<br>**Observação:** certifique-se de fornecer um valor exclusivo de `mboxSession` e `mboxPC` para cada destinatário de email (ou seja, para cada chamada de API). Se você não fornecer valores únicos para esses campos, a resposta da API pode ser lenta ou falhar devido ao grande número de eventos gerados em um único perfil. | 1 &lt; Comprimento &lt; 128<br>Não pode conter mais do que um único “.” (ponto).<br>O único ponto permitido é para o sufixo de localização do perfil. |
| `mboxNoRedirect`<br>(Opcional) | 1 | Por padrão, o chamador é redirecionado quando nenhum conteúdo entregável é encontrado. Use para desativar o comportamento padrão. |  |
| `mbox3rdPartyId` | *xxx* | Use se tiver seu próprio ID de visitante personalizado para usar no direcionamento de perfil. |  |

### Possíveis respostas do servidor do Target

| Resposta | Descrição |
|--- |--- |
| //ERROR: | Gerado pelo balanceador de carga quando não é capaz de retornar o conteúdo |
| success | O parâmetro `mboxNoRedirect` é definido como &quot;true&quot; e o servidor não retorna nenhuma recomendação (ou seja, não há correspondência para a mbox ou o cache do servidor não foi inicializado). |
| bad request | O parâmetro da `mbox` está ausente.<ul><li>O parâmetro `mboxDefault` ou `mboxNoRedirect` não foi especificado.</li><li>O parâmetro de rastreamento `mboxTrace` está especificado, mas `mboxNoRedirect` não está.</li><li>O parâmetro `mboxTarget` não é especificado quando os nomes das mboxes terminam com o sufixo `-clicked`.</li></ul> |
| `Cannot redirect to default content, please specify mboxDefault parameter` | `mboxDefault` não especificado quando não existe correspondência para a solicitação e o parâmetro `mboxNoRedirect` não é especificado. |
| `Invalid mbox name:= MBOX_NAME` | Indica que o parâmetro da `mbox` contém caracteres inválidos. |
| `Mbox name [MBOX_NAME] is too long` | Indica que o parâmetro da `mbox` excede 250 caracteres. |

## Opção 3: usar o modelo somente download {#section_518C279AF0094BE780F4EA40A832A164}

Defina uma recomendação como de costume, mas escolha **somente download** na seção de apresentação ao invés de uma combinação de modelo e mbox. Depois, no ESP, diga ao ESP qual ID de recomendação você criou. O ESP acessa os dados da recomendação por meio de API. Esses dados mostram quais itens devem ser recomendados para determinada categoria ou item-chave, como itens em um carrinho abandonado. O ESP armazena esses dados, conecta-os com sua própria aparência, exibe informações sobre cada item e envia isso por email.

Com essa opção, o servidor do Recommendations não poderá acompanhar diretamente o desempenho de uma recomendação ou dividir o tráfego entre múltiplas combinações de algoritmo/modelo. Além disso, as recomendações não estão vinculadas a um perfil de visitante.

Para obter mais informações sobre como baixar a API, consulte [APIs herdadas > Baixar](/help/assets/adobe-recommendations-classic.pdf).
