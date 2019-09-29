---
description: 'Informações sobre a função adobe.target.sendNotifications(options) para at.js. '
keywords: adobe.target.sendNotifications;sendNotifications;sendnotifications;send notifications;notifications;at.js;funções;function
seo-description: Informações sobre a função adobe.target.sendNotifications(options) da biblioteca at.js de JavaScript do Adobe Target.
seo-title: Informações sobre a função adobe.target.sendNotifications(options) da biblioteca at.js de JavaScript do Adobe Target.
solution: Target
subtopic: Introdução
title: adobe.target.sendNotifications(options)
topic: Padrão
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

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
| Request &gt; notifications | Matriz de objetos | Sim |  | Notificações para o conteúdo exibido, seletores clicados e/ou exibições ou mboxes visitadas. |
| Request &gt; notifications &gt; address | Objeto | Não |  |  |
| Request &gt; notifications &gt; address &gt; url | String | Não |  | URL de onde a notificação foi disparada. |
| Request &gt; notifications &gt; address &gt; referringUrl | String | Não |  | O URL de referência do qual a notificação foi disparada. |
| Request &gt; notifications &gt; parameters | Objeto | Não | Os seguintes nomes não são permitidos para parâmetros:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Considere o seguinte:<ul><li>Limite máximo de 50 parâmetros.</li><li>O nome do parâmetro não pode ficar em branco.</li><li>Extensão máx. do nome do parâmetro: 128.</li><li>O nome do parâmetro não pode começar com "perfil".</li><li>Extensão máx. do valor do parâmetro: 5000.</li></ul> |  |
| Request &gt; notifications &gt; profileParameters | Objeto | Não | Os seguintes nomes não são permitidos para parâmetros:<ul><li>orderId</li><li>orderTotal</li><li>productPurchasedIds</li></ul>Considere o seguinte:<ul><li>Limite máximo de 50 parâmetros.</li><li>O nome do parâmetro não pode ficar em branco.</li><li>Extensão máx. do nome do parâmetro: 128.</li><li>O nome do parâmetro não pode começar com "perfil".</li><li>Extensão máx. do valor do parâmetro: 5000.</li></ul> |  |
| Request &gt; notifications &gt; order | Objeto | Não |  | Objeto que descreve os detalhes da ordem. |
| Request &gt; notifications &gt; order &gt; id | String | Não | `<=` 250 caracteres. | ID do pedido. |
| Request &gt; notifications &gt; order &gt; total | String | Não | `>=` 0 | Total do pedido. |
| Request &gt; notifications &gt; order &gt; purchasedProductIds | Matriz de string | Não | <ul><li>Valores em branco não são permitidos.</li><li>Comprimento máx. da ID de produto: 50.</li><li>IDs de produto, separadas por vírgulas e concatenadas, o comprimento total não pode exceder 250.</li></ul> | Identificações de produto da ordem. |
| Request &gt; notifications &gt; product | Objeto | Não |  |  |
| Request &gt; notifications &gt; product &gt; id | String | Não | `<=` 128 caracteres; não pode ficar em branco. | Identificação do produto. |
| Request &gt; notifications &gt; product &gt; categoryId | String | Não | `<=` 128 caracteres; não pode ficar em branco. | Identificação da categoria. |
| Request &gt; notifications &gt; id | String | Sim | `<=` 200 caracteres. | A ID da notificação será retornada em resposta e indicará que a notificação foi processada com sucesso. |
| Request &gt; notifications &gt; impressionId | String | Não | `<= 128` caracteres. | A ID da impressão é usada para unir (vincular) a notificação atual com uma notificação anterior ou executar a solicitação. Caso as duas correspondam, a segunda e as solicitações subsequentes não gerarão uma nova impressão para a atividade ou experiência. |
| Solicitação &gt; notificações &gt; tipo | String | Sim | “click” ou “display” são suportados. | Tipo de notificação. |
| Request &gt; notifications &gt; timestamp | Número`<int64>` | Sim |  | O carimbo de data e hora da notificação em milissegundos decorridos desde a época UNIX. |
| Request &gt; notifications &gt; tokens | Matriz de string | Sim |  | Uma lista de tokens para o conteúdo exibido ou para os seletores clicados, com base no tipo de notificação. |
| Request &gt; notifications &gt; mbox | Objeto | Não |  | Notificações para a mbox. |
| Request &gt; notifications &gt; mbox &gt; name | String | Não | Valores em branco não são permitidos.<br>Caracteres permitidos: consulte a observação após a tabela. | nome da mbox. |
| Request &gt; notifications &gt; mbox &gt; state | String | Não |  | token de estado da mbox. |
| Request &gt; notifications &gt; view | Objeto | Não |  |  |
| Request &gt; notifications &gt; view &gt; id | Número inteiro `<int64>` | Não |  | Identificação de exibição. A identificação atribuída à exibição quando ela foi criada por meio da API de exibição. |
| Request &gt; notifications &gt; view &gt; name | String | Não | `<= 128` caracteres. | Nome da exibição. |
| Request &gt; notifications &gt; view &gt; key | String | Não | `<=` 512 caracteres. | Chave da exibição. A chave definida para a exibição por meio da API. |
| Request &gt; notifications &gt; view &gt; state | String | Não |  | Token de estado da exibição. |

**Observação**: os seguintes caracteres são permitidos para `Request > notifications > mbox > name`:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## chamada sendNotifications() após renderizar mboxes buscadas previamente

```
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