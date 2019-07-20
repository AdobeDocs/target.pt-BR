---
description: 'Informações sobre a função adobe. target. sendnotifications (opções) para at. js. '
seo-description: Informações sobre a função adobe. target. sendnotifications (opções) da biblioteca do Adobe Target no javascript.
seo-title: Informações sobre a função adobe. target. sendnotifications (opções) da biblioteca do Adobe Target no javascript.
solution: Target
subtopic: Introdução
title: adobe. target. sendnotifications (opções)
topic: Padrão
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# adobe. target. sendnotifications (opções)

This function sends a notification to Target edge when an experience is rendered without using `adobe.target.applyOffer()` or `adobe.target.applyOffers()`.

>[!NOTE]
>
>Esta função foi introduzida no at. js 2.1.0 e estará disponível para qualquer versão acima de 2.1.0.

| Chave | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| consumerId | String | Não | O valor padrão é a mbox global do cliente se não for fornecida. Essa chave é usada para gerar a ID de dados complementares usada para integração A4T. |
| Solicitação | Objeto | Sim | Consulte Tabela de solicitações abaixo. |
| timeout | Número | Não | Tempo limite da solicitação. Se não for especificado, o tempo limite padrão da at.js será usado. |

## Solicitação

| Nome do campo | Tipo | Obrigatório? | Limitação | Descrição |
| --- | --- | --- | --- | --- |
| Solicitação &gt; Notificações | Matriz de objetos | Sim |  | Notificações para o conteúdo exibido, cliques clicados e/ou visualizações visitadas ou mboxes. |
| Solicitação &gt; notificações &gt; endereço | Objeto | Não |  |  |
| Solicitação &gt; notificações &gt; endereço &gt; url | String | Não |  | URL de onde a notificação foi disparada. |
| Solicitação &gt; notificações &gt; endereço &gt; referringurl | String | Não |  | O URL de referência a partir do qual a notificação foi disparada. |
| Solicitação &gt; notificações &gt; parâmetros | Objeto | Não | Os seguintes nomes não são permitidos para parâmetros:<ul><li>orderId</li><li>orderTotal</li><li>Productpurchasedids</li></ul>Considere o seguinte:<ul><li>Limite máximo de parameters 0 parâmetros.</li><li>O nome do parâmetro não deve estar em branco.</li><li>Extensão máx. do nome máx. 128.</li><li>O nome do parâmetro não deve começar com "perfil".</li><li>Extensão máx. do valor do parâmetro 5000.</li></ul> |  |
| Solicitação &gt; notificações &gt; profileparameters | Objeto | Não | Os seguintes nomes não são permitidos para parâmetros:<ul><li>orderId</li><li>orderTotal</li><li>Productpurchasedids</li></ul>Considere o seguinte:<ul><li>Limite máximo de parameters 0 parâmetros.</li><li>O nome do parâmetro não deve estar em branco.</li><li>Extensão máx. do nome máx. 128.</li><li>O nome do parâmetro não deve começar com "perfil".</li><li>Extensão máx. do valor do parâmetro 5000.</li></ul> |  |
| Solicitação &gt; notificações &gt; ordem | Objeto | Não |  | Objeto que descreve os detalhes do pedido. |
| Solicitação &gt; notificações &gt; ordem &gt; id | String | Não | `<=` 250 caracteres. | ID do pedido. |
| Solicitação &gt; notificações &gt; ordem &gt; total | String | Não | `>=` 0 | Total do pedido. |
| Solicitação &gt; notificações &gt; ordem &gt; purchasedproductids | Matriz de string | Não | <ul><li>Valores em branco permitidos.</li><li>Cada extensão máx. do produto 50.</li><li>IDs de produto, separadas por vírgulas e concatenadas, o tamanho total não deve exceder 250.</li></ul> | Ordenar IDs de produto. |
| Solicitação &gt; notificações &gt; produto | Objeto | Não |  |  |
| Solicitação &gt; notificações &gt; produto &gt; id | String | Não | `<=` 128 caracteres; não pode estar em branco. | Identificação do produto. |
| Solicitação &gt; notificações &gt; produto &gt; categoryid | String | Não | `<=` 128 caracteres; não pode estar em branco. | ID da categoria. |
| Solicitação &gt; notificações &gt; id | String | Sim | `<=` 200 caracteres. | A ID de notificação será retornada em resposta e indicará que a notificação foi processada com sucesso. |
| Solicitação &gt; notificações &gt; impressionid | String | Não | `<= 128` caracteres. | A ID de impressão é usada para unir (link) a notificação atual com uma notificação anterior ou executar solicitação. Caso ambos correspondam, a segunda e outra solicitação subsequente não gerarão uma nova impressão para a atividade ou experiência. |
| Solicitação &gt; notificações &gt; tipo | String | Sim | «click» ou «display» é suportado. | Tipo de notificação. |
| Solicitação &gt; notificações &gt; carimbo de data e hora | Número`<int64>` | Sim |  | Carimbo de data e hora da notificação em milissegundos decorridos desde a época UNIX. |
| Solicitação &gt; notificações &gt; tokens | Matriz de string | Sim |  | Uma lista de tokens para o conteúdo exibido ou os seletores clicados, com base no tipo de notificação. |
| Solicitação &gt; notificações &gt; mbox | Objeto | Não |  | Notificações para a mbox. |
| Solicitação &gt; notificações &gt; nome &gt; nome | String | Não | Valores em branco permitidos.<br>Caracteres permitidos: Consulte a observação seguinte. | nome da mbox. |
| Solicitação &gt; notificações &gt; mbox &gt; estado | String | Não |  | token de estado da mbox. |
| Solicitação &gt; notificações &gt; exibição | Objeto | Não |  |  |
| Solicitação &gt; notificações &gt; exibir &gt; id | Número inteiro `<int64>` | Não |  | Exibir id. A ID atribuída à exibição quando a exibição foi criada por meio da API de exibição. |
| Solicitação &gt; notificações &gt; exibir &gt; nome | String | Não | `<= 128` caracteres. | Nome da exibição. |
| Solicitação &gt; notificações &gt; exibir &gt; chave | String | Não | `<=` 512 caracteres. | Exibir chave. A chave que foi definida com a exibição por meio da API. |
| Solicitação &gt; notificações &gt; exibir &gt; estado | String | Não |  | Exibir token de estado. |

**Observação**: Os seguintes caracteres são permitidos para `Request > notifications > mbox > name`:

```
- '-, ./=`:;&!@#$%^&*()+|?~[]{}'
```

## chamada sendnotifications () após renderizar mboxes pré-buscadas

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
>If you are using Adobe Analytics, `getOffers()` with prefetch only and `sendNotifications()`, the Analytics request must be fired after `sendNotifications()` is executed. The purpose of this is to ensure that the SDID generated by `sendNotifications()` will match the SDID sent to Analytics and Target.