---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Informações sobre APIs de delivery do lado do servidor da Adobe Target, SDK do Node.js e APIs Recommendations do Público alvo.
title: Informações sobre APIs de delivery do lado do servidor da Adobe Target, SDK do Node.js e APIs Recommendations do Público alvo.
feature: server-side
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 08ad3291a1f981fbc3963ce403bf19849c358b97
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 11%

---


# Lado do servidor: implementação do Target{#server-side-implement-target}

Informações sobre APIs de delivery do lado do [!DNL Adobe Target] servidor, SDK do Node.js e [!DNL Target Recommendations] APIs.

O processo a seguir ocorre em uma implementação do lado do servidor do [!DNL Target]:

1. Um dispositivo cliente faz uma solicitação para uma experiência por meio do servidor.
1. O servidor envia essa solicitação para o [!DNL Target].
1. O [!DNL Target] envia a resposta para o servidor.
1. Seu servidor toma a decisão sobre qual experiência fornecer ao dispositivo cliente para que ele seja renderizado.

A experiência não precisa ser exibida em um navegador. A experiência pode ser exibida em um email ou quiosque, por meio de um assistente de voz, ou por meio de outra experiência não visual ou dispositivo não baseado em navegador. Como o servidor fica entre o cliente e o [!DNL Target], esse tipo de implementação também será ideal se você precisar de mais controle e segurança ou de processos de back-end complexos que deseja executar no servidor.

As seções a seguir fornecem mais informações sobre as várias APIs e o SDK do NodeJS:

## APIs de entrega no lado do servidor

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Adicionada a API do [!DNL Target] Delivery, você pode:

* Forneça experiências na Web, incluindo SPAs e canais móveis, bem como dispositivos IoT não baseados em navegador, como TVs conectadas, quiosques ou telas digitais na loja.
* Forneça experiências de qualquer plataforma ou aplicativo do lado do servidor que possa fazer chamadas HTTP/s.
* Forneça experiências consistentes e personalizadas a um visitante, independentemente do canal ou dispositivos usados pelo visitante para se envolver com sua empresa.
* Armazene as experiências em cache de um visitante em uma sessão no seu servidor para que várias chamadas de API possam ser evitadas, o que proporciona um melhor desempenho.
* Integre-se perfeitamente a [!DNL Adobe Experience Cloud] produtos, como [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) e o servidor [!DNL Experience Cloud ID Service] do lado do servidor.

## SDK do Node.js

Link: [SDK do Node.js](https://github.com/adobe/target-nodejs-sdk)

O Node.js SDK é um kit sofisticado de desenvolvimento de software que remove as complexidades do gerenciamento de cookies, sessões e integração com [!DNL Experience Cloud] produtos, como [!DNL Analytics], [!DNL Experience Cloud Visitor ID Service]e [!DNL Audience Manager]. Em segundo plano, o SDK do Node.js usa a `/rest/v1/delivery` API. Estes são alguns recursos notáveis que são suportados no SDK Node.js:

* **Suporte para busca prévia e notificações que permitem otimizar o desempenho por meio do cache:** Você pode usar o SDK Node.js para recuperar experiências e armazená-las em cache localmente no servidor Node.js com o objetivo de minimizar as chamadas do servidor para [!DNL Target] e otimizar o desempenho do aplicativo.
* **Capacidade de recuperar atividades criadas pelo VEC:** Recupere atividades criadas por VEC no lado do servidor. A resposta que contém atividades criadas por VEC tem seletores que podem ser usados para ocultar apenas partes da sua página que precisam ser personalizadas. Isso ajuda a otimizar a métrica [](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html)Primeira pintura em Conteúdo da sua página, que é um KPI importante para a sua empresa atingir uma pontuação alta no sistema [Google PageRank](https://en.wikipedia.org/wiki/PageRank) .

## SDK Java do público alvo

Link: [SDK Java do público alvo](https://github.com/adobe/target-java-sdk)

O Java SDK é um kit sofisticado de desenvolvimento de software que remove as complexidades do gerenciamento de cookies, sessões e integração com [!DNL Adobe Experience Cloud] soluções, como [!DNL Adobe Analytics], o [!DNL Experience Cloud Visitor ID Service]e [!DNL Adobe Audience Manager]. Em segundo plano, o Java SDK usa a `/rest/v1/delivery` API. Estes são alguns recursos notáveis que são suportados no Java SDK:

* **Suporte para busca prévia e notificações que permitem otimizar o desempenho por meio do cache**: Você pode usar o JavaSDK para recuperar experiências e armazená-las em cache localmente em seu servidor Java com o objetivo de minimizar as chamadas do servidor para [!DNL Target] e otimizar o desempenho do aplicativo.
* **Capacidade de recuperar atividades** criadas pelo VEC: Recupere atividades criadas por VEC no lado do servidor. A resposta que contém atividades criadas por VEC tem seletores que podem ser usados para ocultar apenas partes da sua página que precisam ser personalizadas. Isso ajuda a otimizar a métrica [Primeira pintura](https://developers.google.com/web/fundamentals/performance/user-centric-performance-metrics.html) de conteúdo da sua página, que é um KPI importante para a sua empresa atingir uma pontuação alta no sistema [Google PageRank](https://en.wikipedia.org/wiki/PageRank) .

## Desenvolvedores Adobe Target

Link: [Desenvolvedores Adobe Target](http://developers.adobetarget.com/)

O site de desenvolvedores da Adobe Target ajuda você a implementar [!DNL Target] em aplicativos do lado do cliente, aplicativos do lado do servidor, aplicativos móveis, IoT e muito mais. Você também pode exportar seus [!DNL Target] dados para soluções de terceiros.

## APIs do Target Recommendations

Link: [APIs](https://developers.adobetarget.com/api/recommendations) Público alvo Recommendations e Visão geral [da API](https://docs.adobe.com/content/help/en/target-learn/recommendations-api-tutorial/recs-api-overview.html)Adobe Recommendations.

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
