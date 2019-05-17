---
description: 'Informações sobre a função adobe. target. applyoffers (opções) para at. js. '
keywords: adobe.target.notificação; elemento; seletor; notificação; extensão
seo-description: Informações sobre a função adobe. target. applyoffers (opções) da biblioteca do Adobe Target no javascript.
seo-title: Informações sobre a função adobe. target. applyoffers (opções) da biblioteca do Adobe Target no javascript.
solution: Target
subtopic: Introdução
title: adobe.target.applyOffers(options)
topic: Padrão
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# adobe. target. applyoffers (opções) - at. js 2. x

Essa função permite aplicar mais de uma oferta que foi recuperada por `adobe.target.getOffers()`.

>[!NOTE]
>
>Esta função foi introduzida com at. js 2. x. Essa função não está disponível para o at. js versão 1.*x*.

| Chave | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| selector | String | Não | Elemento HTML ou seletor CSS usado para identificar o elemento HTML, onde [!DNL Target] deve colocar o conteúdo da oferta. Se nenhum seletor for fornecido, o [!DNL Target] presume que o elemento HTML que devemos usar é HTML HEAD. |
| Resposta | Objeto | Sim | Objeto response de `getOffers()`.<br>Consulte Tabela de solicitações abaixo. |

## Resposta

| Nome do campo | Descrição |
| --- | --- |
| resposta &gt; pré-busca &gt; exibições &gt; opções &gt; conteúdo | Observe que o conteúdo da &quot;opção&quot; não está bem definido e depende diretamente da estrutura de tipo/modelo de opção. |
| resposta &gt; pré-busca &gt; exibições &gt; opções &gt; tipo | Tipo de opção. Reflete o tipo de campo &quot;conteúdo&quot;. O tipo suportado é ações. |
| resposta &gt; pré-busca &gt; exibições &gt; estado | Um token de estado de exibição opaco que deve ser encaminhado com a notificação de visualização para a exibição |
| resposta &gt; pré-busca &gt; exibições &gt; opções &gt; responseTokens | Contém o mapa de `responseTokens` que foi coletado quando a opção atual estava sendo processada. |
| resposta &gt; pré-busca &gt; exibições &gt; analytics &gt; carga | A carga do Analytics para integração do cliente que deve ser enviada para o Analytics depois que a exibição for aplicada. |
| resposta &gt; pré-busca &gt; exibições &gt; rastreamento | O objeto que contém todos os dados de rastreamento da chamada de pré-busca por exibição.<br>O objeto de rastreamento também incluirá uma versão para o rastreamento.<br>O objeto de rastreamento também incluirá detalhes da exibição atual. |
| resposta &gt; pré-busca &gt; exibições &gt; opções &gt; eventToken | O registro em log de eventos é feito por opção. Para cada opção aplicada, o respectivo token de evento deve ser adicionado à lista de tokens de notificação. Observe que uma Exibição é composta por várias opções. Se todas as opções tiverem sido aplicadas e visualizadas, todos `eventTokens` precisam ser incluídos na notificação. |
| resposta &gt; pré-busca &gt; exibições &gt; nome | O nome de exibição legível. |
| resposta &gt; pré-busca &gt; exibições &gt; métricas | Relatar métricas que devem ser assistidas e notificadas [!DNL Target]. Atualmente, apenas a métrica de cliques é compatível. Se o elemento for clicado, o `eventTokens` apropriado deve ser coletado e uma notificação deve ser enviada. |
| resposta &gt; pré-busca &gt; exibições &gt; chave | A chave ou impressão digital que identifica a exibição. |
| resposta &gt; pré-busca &gt; exibições &gt; id | ID da exibição. |
| resposta &gt; notificações &gt; id | ID de notificação. |
| resposta &gt; notificações &gt; eventos &gt; tipo | O tipo da notificação, clique ou exibição. |
| resposta &gt; notificações &gt; eventos &gt; rastreamento | O rastreamento do evento de notificação. |
| resposta &gt; notificações &gt; eventos &gt; token | O token que foi enviado com o evento de notificação. |
| resposta &gt; notificações &gt; eventos &gt; carimbo de data e hora | O carimbo de data e hora enviado com o evento de notificação. |
| resposta &gt; notificações &gt; eventos &gt; errorCode | Se a notificação falhar, o código indicará o motivo da falha. |
| resposta &gt; notificações &gt; eventos | Os eventos registrados ou não registrados para a notificação atual. |
| resposta &gt; notificações | Indica as notificações registradas ou com falha. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; rastreamento | O objeto que contém todos os dados de rastreamento para a solicitação de mbox individual. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; responseTokens | Contém o mapa de `responseTokens` para execução de solicitação de mbox específica. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; opção &gt; conteúdo | Observe que o conteúdo da &quot;opção&quot; não está bem definido e depende diretamente da estrutura de tipo/modelo de opção. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; opção &gt; tipo | Tipo de opção. Reflete o tipo de campo &quot;conteúdo&quot;. Os tipos suportados são: html, redirecionamento, JSON e dinâmico. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; opções | Opção de resposta. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; métricas &gt; eventtoken | Token do evento de clique. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; métricas &gt; tipo | &quot;click&quot; |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; métricas | Contém a lista de `clickThrough` métricas. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; mbox | O nome da mbox. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; índice | Indica que a resposta é para a mbox com este índice da solicitação. |
| resposta &gt; executar &gt; mboxes &gt; mbox &gt; analytics &gt; carga | A carga do Analytics para integração do cliente que deve ser enviada para o Analytics após a aplicação da mbox. (Consulte a seção Campanhas habilitadas para A4T.) |
| resposta &gt; executar &gt; mboxes | Lista de mboxes executadas. |
| resposta &gt; executar &gt; carga &gt; opções &gt; conteúdo | Observe que o conteúdo da &quot;opção&quot; não está bem definido e depende diretamente da estrutura de tipo/modelo de opção. |
| resposta &gt; executar &gt; carga &gt; opções &gt; tipo | Tipo de opção. Reflete o tipo de campo &quot;conteúdo&quot;. Os tipos suportados são: html, redirecionamento, JSON, dinâmico e ações. |
| resposta &gt; executar &gt; carga &gt; opções | Opções que não são agrupadas por exibições (target-global-mbox + opções de atividades com exibições não agrupadas por exibições). |
| resposta &gt; executar &gt; carga &gt; métricas | Métricas de clique que não foram definidas para pertencer a uma exibição específica. |
| resposta &gt; executar &gt; carga &gt; rastreamento | O objeto que contém todos os dados de rastreamento da solicitação de carga. |
| resposta &gt; executar &gt; carga &gt; analytics &gt; carga | A carga do Analytics para integração do cliente que deve ser enviada para o Analytics após a aplicação do conteúdo de carregamento da página. (Consulte a seção Campanhas habilitadas para A4T.) |

## Exemplo de chamada applyOffers ()

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
