---
keywords: adobe.target.applyOffers;applyOffers;applyoffers;apply offers;at.js;functions;function
description: Informações sobre a função adobe.target.applyOffers(options) da biblioteca at.js de JavaScript do Adobe Target.
title: adobe.target.applyOffers(options) - at.js 2.x
feature: client-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '791'
ht-degree: 95%

---


# adobe.target.applyOffers(options) - at.js 2.x

Essa função permite aplicar mais de uma oferta que foi recuperada por `adobe.target.getOffers()`.

>[!NOTE]
>
>Essa função foi introduzida com a at.js 2.x. Essa função não está disponível para a at.js versão 1.*x*.

| Chave | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| selector | String    | Não | Elemento HTML ou seletor CSS usado para identificar o elemento HTML, onde [!DNL Target] deve colocar o conteúdo da oferta. If a selector is not provided, [!DNL Target] assumes that the HTML element to use is HTML HEAD. |
| Resposta | Objeto | Sim | Objeto response de `getOffers()`.<br>Consulte Tabela de solicitações abaixo. |

## Resposta

>[!NOTE]
>
>Consulte a documentação [da API de](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) Delivery para obter informações sobre os tipos aceitáveis para todos os campos listados abaixo.

| Nome do campo | Descrição |
| --- | --- |
| resposta > pré-busca > exibições > opções > conteúdo | Observe que o conteúdo da &quot;opção&quot; não está bem definido e depende diretamente da estrutura de tipo/modelo de opção. |
| resposta > pré-busca > exibições > opções > tipo | Tipo de opção. Reflete o tipo de campo &quot;conteúdo&quot;. O tipo suportado é ações. |
| resposta > pré-busca > exibições > estado | Um token de estado de exibição opaco que deve ser encaminhado com a notificação de visualização para a exibição |
| resposta > pré-busca > exibições > opções > responseTokens | Contém o mapa de `responseTokens` que foi coletado quando a opção atual estava sendo processada. |
| resposta > pré-busca > exibições > analytics > carga | A carga do Analytics para integração no lado do cliente que deve ser enviada para o Analytics depois que a exibição for aplicada. |
| resposta > pré-busca > exibições > rastreamento | O objeto que contém todos os dados de rastreamento da chamada de pré-busca por exibição.<br>O objeto de rastreamento também incluirá uma versão para o rastreamento.<br>O objeto de rastreamento também incluirá detalhes da exibição atual. |
| resposta > pré-busca > exibições > opções > eventToken | O registro em log de eventos é feito por opção. Para cada opção aplicada, o respectivo token de evento deve ser adicionado à lista de tokens de notificação. Observe que uma Exibição é composta por várias opções. Se todas as opções tiverem sido aplicadas e visualizadas, todos `eventTokens` precisam ser incluídos na notificação. |
| resposta > pré-busca > exibições > nome | O nome de exibição legível. |
| resposta > pré-busca > exibições > métricas | Relatar métricas que devem ser assistidas e notificadas [!DNL Target]. Atualmente, apenas a métrica de cliques é compatível. Se o elemento for clicado, o `eventTokens` apropriado deve ser coletado e uma notificação deve ser enviada. |
| resposta > pré-busca > exibições > chave | A chave ou impressão digital que identifica a exibição. |
| resposta > pré-busca > exibições > id | ID da exibição. |
| resposta > notificações > id | ID de notificação. |
| resposta > notificações > eventos > tipo | O tipo da notificação, clique ou exibição. |
| resposta > notificações > eventos > rastreamento | O rastreamento do evento de notificação. |
| resposta > notificações > eventos > token | O token que foi enviado com o evento de notificação. |
| resposta > notificações > eventos > carimbo de data e hora | O carimbo de data e hora enviado com o evento de notificação. |
| resposta > notificações > eventos > errorCode | Se a notificação falhar, o código indicará o motivo da falha. |
| resposta > notificações > eventos | Os eventos registrados ou não registrados para a notificação atual. |
| resposta > notificações | Indica as notificações registradas ou com falha. |
| resposta > executar > mboxes > mbox > rastreamento | O objeto que contém todos os dados de rastreamento para a solicitação de mbox individual. |
| resposta > executar > mboxes > mbox > responseTokens | Contém o mapa de `responseTokens` para execução de solicitação de mbox específica. |
| resposta > executar > mboxes > mbox > opção > conteúdo | Observe que o conteúdo da &quot;opção&quot; não está bem definido e depende diretamente da estrutura de tipo/modelo de opção. |
| resposta > executar > mboxes > mbox > opção > tipo | Tipo de opção. Reflete o tipo de campo &quot;conteúdo&quot;. Os tipos suportados são: html, redirecionamento, JSON e dinâmico. |
| resposta > executar > mboxes > mbox > opções | Opção de resposta. |
| resposta > executar > mboxes > mbox > métricas > eventtoken | Token do evento de clique. |
| resposta > executar > mboxes > mbox > métricas > tipo | &quot;click&quot; |
| resposta > executar > mboxes > mbox > métricas | Contém a lista de `clickThrough` métricas. |
| resposta > executar > mboxes > mbox > mbox | O nome da mbox. |
| resposta > executar > mboxes > mbox > índice | Indica que a resposta é para a mbox com este índice da solicitação. |
| resposta > executar > mboxes > mbox > analytics > carga | A carga do Analytics para integração no lado do cliente que deve ser enviada para o Analytics após a aplicação da mbox. (Consulte a seção Campanhas habilitadas para A4T.) |
| resposta > executar > mboxes | Lista de mboxes executadas. |
| resposta > executar > carga > opções > conteúdo | Observe que o conteúdo da &quot;opção&quot; não está bem definido e depende diretamente da estrutura de tipo/modelo de opção. |
| resposta > executar > carga > opções > tipo | Tipo de opção. Reflete o tipo de campo &quot;conteúdo&quot;. Os tipos suportados são: html, redirecionamento, JSON, dinâmico e ações. |
| resposta > executar > carga > opções | Opções que não são agrupadas por exibições (target-global-mbox + opções de atividades com exibições não agrupadas por exibições). |
| resposta > executar > carga > métricas | Métricas de clique que não foram definidas para pertencer a uma exibição específica. |
| resposta > executar > carga > rastreamento | O objeto que contém todos os dados de rastreamento da solicitação de carga. |
| resposta > executar > carga > analytics > carga | A carga do Analytics para integração no lado do do cliente que deve ser enviada para o Analytics após a aplicação do conteúdo de carregamento da página. (Consulte a seção Campanhas habilitadas para A4T.) |

## Exemplo de chamada applyOffers()

```
adobe.target.applyOffers({response:{
  "execute": {
    "pageLoad": {
      "options": [{
        "type": "html",
        "content": "page-load"
      },
      {
        "type": "actions",
        "content": [{
          "type": "setHtml",
          "content": "<h1>Container 1</h1>",
          "selector": "#container1",
          "cssSelector": "#container1"
        },
        {
          "type": "setHtml",
          "content": "<h3>Container 3</h3>",
          "selector": "#container3",
          "cssSelector": "#container3"
        }]
      }],
 
 
      "metrics": [{
        "type": "click",
        "selector": "#container1",
        "eventToken": "page-load-click-metric" 
      }]
    }
  }
}});
```

## Exemplo de chamada de encadeamento de Promessa com `getOffers()` e `applyOffers()`, porque essas funções são baseadas em Promessa

```
adobe.target.getOffers({...})
.then(response => adobe.target.applyOffers({ response: response }))
.then(() => console.log("Success"))
.catch(error => console.log("Error", error));
```
