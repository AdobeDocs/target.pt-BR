---
keywords: lado do servidor; no lado do servidor; api; sdk; node.js; nodejs; node js; api do recommendations; api:apis
description: Saiba mais sobre as APIs do Adobe [!DNL Target] server-side delivery APIs, SDKs, and [!DNL Target] Recommendations.
title: 'Onde posso saber mais sobre as APIs e os SDKs de entrega do lado do servidor? [!DNL Target] '
feature: Implementar o lado do servidor
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 20%

---

# Lado do servidor: implementação do Target

Informações sobre [!DNL Adobe Target] APIs de entrega do lado do servidor, SDKs e [!DNL Target Recommendations] APIs.

O processo a seguir ocorre em uma implementação do lado do servidor do [!DNL Target]:

1. Um dispositivo cliente faz uma solicitação para uma experiência por meio do servidor.
1. O servidor envia essa solicitação para o [!DNL Target].
1. O [!DNL Target] envia a resposta para o servidor.
1. O servidor decide qual experiência deve ser entregue ao dispositivo cliente para que seja renderizada.

A experiência não precisa ser exibida em um navegador. A experiência pode ser exibida em um email ou quiosque, por meio de um assistente de voz ou por alguma outra experiência não visual ou dispositivo não baseado em navegador. Como o servidor fica entre o cliente e o [!DNL Target], esse tipo de implementação também será ideal se você precisar de mais controle e segurança ou de processos de back-end complexos que deseja executar no servidor.

>[!NOTE]
>
>Um visitante pela primeira vez pode ser inicializado somente no lado do cliente. Um visitante pela primeira vez *não pode* ser inicializado no lado do servidor.

As seções a seguir fornecem mais informações sobre as várias APIs e o SDK do NodeJS:

## APIs de entrega no lado do servidor

Link: [APIs de entrega do lado do servidor](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Com a [!DNL Target] API de entrega, você pode:

* Forneça experiências através da Web, incluindo SPA e canais móveis, bem como dispositivos IoT não baseados em navegador, como TVs conectadas, quiosques ou telas digitais na loja.
* Forneça experiências de qualquer plataforma ou aplicativo do lado do servidor que possa fazer chamadas HTTP/s.
* Forneça experiências consistentes e personalizadas a um visitante, independentemente de qual canal ou dispositivos o visitante usou para se envolver com sua empresa.
* Armazene em cache as experiências de um visitante em uma sessão do seu servidor para que várias chamadas de API possam ser evitadas, o que melhora o desempenho.
* Integre-se perfeitamente a [!DNL Adobe Experience Cloud] produtos, como [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) e [!DNL Experience Cloud ID Service] do lado do servidor.

## SDKs do lado do servidor

Link: [Adobe Target SDKs](https://adobetarget-sdks.gitbook.io/docs/)

O [!DNL Adobe Target] portal de documentação do SDK do lado do servidor ajuda a implementar [!DNL Target] em seus servidores no idioma escolhido.

## APIs do Target Recommendations

Link: [APIs do Recommendations do Target](https://developers.adobetarget.com/api/recommendations) e [Visão geral da API do Adobe Recommendations](https://experienceleague.adobe.com/docs/target-learn/recommendations-api-tutorial/recs-api-overview.html).

As APIs do Recommendations permitem interagir programaticamente com os servidores de recomendações [!DNL Target]. Essas APIs podem ser integradas a uma variedade de pilhas de aplicativos para executar funções que você normalmente faria por meio da [!DNL Target] interface do usuário.
