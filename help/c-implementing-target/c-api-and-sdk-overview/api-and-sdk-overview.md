---
keywords: server side;server-side;api;sdk;node.js;nodejs;node js;recommendations api;api:apis
description: Informações sobre APIs de delivery do lado do servidor, SDKs e APIs de Recommendations de Públicos alvos.
title: Informações sobre APIs de delivery do lado do servidor da Adobe Target, SDK do Node.js e APIs Recommendations do Público alvo.
feature: server-side
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 20%

---


# Lado do servidor: implementação do Target{#server-side-implement-target}

Informações sobre APIs, SDKs e APIs de delivery do lado [!DNL Adobe Target] [!DNL Target Recommendations] do servidor.

O processo a seguir ocorre em uma implementação do lado do servidor do [!DNL Target]:

1. Um dispositivo cliente faz uma solicitação para uma experiência por meio do servidor.
1. O servidor envia essa solicitação para o [!DNL Target].
1. O [!DNL Target] envia a resposta para o servidor.
1. Seu servidor toma a decisão sobre qual experiência fornecer ao dispositivo cliente para que ele seja renderizado.

A experiência não precisa ser exibida em um navegador. A experiência pode ser exibida em um email ou quiosque, por meio de um assistente de voz, ou por meio de outra experiência não visual ou dispositivo não baseado em navegador. Como o servidor fica entre o cliente e o [!DNL Target], esse tipo de implementação também será ideal se você precisar de mais controle e segurança ou de processos de back-end complexos que deseja executar no servidor.

>[!NOTE]
>
>Um visitante pela primeira vez só pode ser inicializado no lado do cliente. Um visitante pela primeira vez *não pode* ser inicializado no lado do servidor.

As seções a seguir fornecem mais informações sobre as várias APIs e o SDK do NodeJS:

## APIs de entrega no lado do servidor

Link: [Server Side Delivery APIs](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Adicionada a API do [!DNL Target] Delivery, você pode:

* Forneça experiências através da Web, incluindo canais SPA e móveis, bem como dispositivos IoT não baseados em navegador, como TVs conectadas, quiosques ou telas digitais na loja.
* Forneça experiências de qualquer plataforma ou aplicativo do lado do servidor que possa fazer chamadas HTTP/s.
* Forneça experiências consistentes e personalizadas a um visitante, independentemente do canal ou dispositivos usados pelo visitante para se envolver com sua empresa.
* Armazene as experiências em cache de um visitante em uma sessão no seu servidor para que várias chamadas de API possam ser evitadas, o que proporciona um melhor desempenho.
* Integre-se perfeitamente a [!DNL Adobe Experience Cloud] produtos, como [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) e o servidor [!DNL Experience Cloud ID Service] do lado do servidor.

## SDKs do lado do servidor

Link: [SDKs do Adobe Target](https://adobetarget-sdks.gitbook.io/docs/)

O portal de documentação do SDK do lado do [!DNL Adobe Target] servidor ajuda a implementar [!DNL Target] em seus servidores no idioma desejado.

## APIs do Target Recommendations

Link: [APIs](https://developers.adobetarget.com/api/recommendations) Público alvo Recommendations e Visão geral [da API](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html)Adobe Recommendations.

The Recommendations APIs let you programmatically interact with [!DNL Target] recommendations servers. These APIs can be integrated with a range of application stacks to perform functions that you would typically do via the [!DNL Target] user interface.
