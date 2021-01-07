---
keywords: adobe.target.sendNotifications;sendNotifications;sendnotifications;send notifications;notifications;at.js;functions;function
description: Informações sobre a função adobe.target.sendNotifications(options) da biblioteca at.js de JavaScript do Adobe Target.
title: adobe.target.sendNotifications(options)
feature: at.js
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '612'
ht-degree: 100%

---


# adobe.target.sendNotifications(options)

Esta função envia uma notificação para a borda do Target quando uma experiência é renderizada sem usar `adobe.target.applyOffer()` ou `adobe.target.applyOffers()`.

>[!NOTE]
>
>Esta função foi introduzida na at.js 2.1.0 e estará disponível para todas as versões a partir da 2.1.0.

| Chave | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| consumerId | String | Não | O valor padrão é a mbox global do cliente se não for fornecida. Essa chave é usada para gerar a ID de dados complementares usada para integração A4T. |
| Solicitação | Objeto | Sim | Consulte Tabela de solicitações abaixo. |
| timeout | Número | Não | Tempo limite da solicitação. Se não for especificado, o tempo limite padrão da at.js será usado. |

## Solicitação

| Nome do campo | Tipo | Obrigatório? | Limitação | Descrição |
| --- | --- | --- | --- | --- |
| Request > notifications | Matriz de objetos | Sim |  | Notificações para o conteúdo exibido, seletores clicados e/ou exibições ou mboxes visitadas. |
| Request > notifications > address | Objeto | Não |  |  |
| Request > notifications > address > url | String | Não |  | URL de onde a notificação foi disparada. |
| Request > notifications > address > referringUrl | String | Não |  | O URL de referência do qual a notificação foi disparada. |
| Request > notifications > parameters | Objeto | Não | Os seguintes nomes não são permitidos para parâmetros:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Considere o seguinte:<ul><li>Limite máximo de 50 parâmetros.</li><li>O nome do parâmetro não pode ficar em branco.</li><li>Extensão máx. do nome do parâmetro: 128.</li><li>O nome do parâmetro não pode começar com &quot;perfil&quot;.</li><li>Extensão máx. do valor do parâmetro: 5000.</li></ul> |  |
| Request > notifications > profileParameters | Objeto | Não | Os seguintes nomes não são permitidos para parâmetros:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Considere o seguinte:<ul><li>Limite máximo de 50 parâmetros.</li><li>O nome do parâmetro não pode ficar em branco.</li><li>Extensão máx. do nome do parâmetro: 128.</li><li>O nome do parâmetro não pode começar com &quot;perfil&quot;.</li><li>Extensão máx. do valor do parâmetro: 5000.</li></ul> |  |
| Request > notifications > order | Objeto | Não |  | Objeto que descreve os detalhes da ordem. |
| Request > notifications > order > id | String | Não | `<=` 250 caracteres. | ID do pedido. |
| Request > notifications > order > total | String | Não | `>=` 0 | Total do pedido. |
| Request > notifications > order > purchasedProductIds | Matriz de string | Não | <ul><li>Valores em branco não são permitidos.</li><li>Comprimento máx. da ID de produto: 50.</li><li>IDs de produto, separadas por vírgulas e concatenadas, o comprimento total não pode exceder 250.</li></ul> | Identificações de produto da ordem. |
| Request > notifications > product | Objeto | Não |  |  |
| Request > notifications > product > id | String | Não | `<=` 128 caracteres; não pode ficar em branco. | Identificação do produto. |
| Request > notifications > product > categoryId | String | Não | `<=` 128 caracteres; não pode ficar em branco. | Identificação da categoria. |
| Request > notifications > id | String | Sim | `<=` 200 caracteres. | A ID da notificação será retornada em resposta e indicará que a notificação foi processada com sucesso. |
| Request > notifications > impressionId | String | Não | `<= 128` caracteres. | A ID da impressão é usada para unir (vincular) a notificação atual com uma notificação anterior ou executar a solicitação. Caso as duas correspondam, a segunda e as solicitações subsequentes não gerarão uma nova impressão para a atividade ou experiência. |
| Solicitação > notificações > tipo | String | Sim | “click” ou “display” são suportados. | Tipo de notificação. |
| Request > notifications > timestamp | Número`<int64>` | Sim |  | O carimbo de data e hora da notificação em milissegundos decorridos desde a época UNIX. |
| Request > notifications > tokens | Matriz de string | Sim |  | Uma lista de tokens para o conteúdo exibido ou para os seletores clicados, com base no tipo de notificação. |
| Request > notifications > mbox | Objeto | Não |  | Notificações para a mbox. |
| Request > notifications > mbox > name | String | Não | Valores em branco não são permitidos.<br>Caracteres permitidos: consulte a observação após a tabela. | nome da mbox. |
| Request > notifications > mbox > state | String | Não |  | token de estado da mbox. |
| Request > notifications > view | Objeto | Não |  |  |
| Request > notifications > view > id | Número inteiro `<int64>` | Não |  | Identificação de exibição. A identificação atribuída à exibição quando ela foi criada por meio da API de exibição. |
| Request > notifications > view > name | String | Não | `<= 128` caracteres. | Nome da exibição. |
| Request > notifications > view > key | String | Não | `<=` 512 caracteres. | Chave da exibição. A chave definida para a exibição por meio da API. |
| Request > notifications > view > state | String | Não |  | Token de estado da exibição. |

**Observação**: os seguintes caracteres são permitidos para `Request > notifications > mbox > name`:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## chamada sendNotifications() após renderizar mboxes buscadas previamente

```javascript
function createTokens(options) {
  return options.map(e => e.eventToken);
}

function createNotification(mbox, type, tokens) {
  const id = 11111; // here we should use a random ID like UUID
  const timestamp = Date.now();
  const { name, state, parameters, profileParameters, order, product } = mbox;
  const result = {
    id,
    type,
    timestamp,
    parameters,
    profileParameters,
    order,
    product
  };

  result.mbox = { name, state };
  result.tokens = tokens;

  return result;
}

adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "a1-serverside-ab"
        }
      ]
    }
  }
})
.then(response => {
  const mboxes = response.prefetch.mboxes;
  const notifications = mboxes.map(mbox => {
    const type = "display";
    const tokens = createTokens(mbox.options);

    return createNotification(mbox, type, tokens);
  });
  
  adobe.target.sendNotifications({
    request: { notifications }
  });
})
```

>[!NOTE]
>
>Se você estiver usando o Adobe Analytics, `getOffers()` com busca prévia somente e `sendNotifications()`, a solicitação do Analytics deverá ser acionada após a execução de `sendNotifications()`. A finalidade disso é garantir que a SDID gerada pela `sendNotifications()` corresponda à SDID enviada para o Analytics e para o Target.