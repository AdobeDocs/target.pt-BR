---
keywords: lado do servidor; no lado do servidor; api; sdk; node.js; nodejs; node js; api do recommendations; api:apis
description: Saiba mais sobre o Adobe [!DNL Target] APIs de entrega do lado do servidor, SDKs e [!DNL Target] APIs do Recommendations.
title: Onde posso saber mais [!DNL Target] APIs e SDKs de entrega do lado do servidor?
feature: Implement Server-side
role: Developer
exl-id: cdee007f-f54d-4cf3-9575-6319da3434a5
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '385'
ht-degree: 21%

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
>Um visitante pela primeira vez pode ser inicializado somente no lado do cliente. Um visitante pela primeira vez *cannot* ser inicializado no lado do servidor.

As seções a seguir fornecem mais informações sobre as várias APIs e o SDK do NodeJS:

## APIs de entrega no lado do servidor

Link: [APIs de entrega no lado do servidor](https://developers.adobetarget.com/api/delivery-api/)

`/rest/v1/delivery`

Usar o [!DNL Target] API de entrega, você pode:

* Forneça experiências através da Web, incluindo SPA e canais móveis, bem como dispositivos IoT não baseados em navegador, como TVs conectadas, quiosques ou telas digitais na loja.
* Forneça experiências de qualquer plataforma ou aplicativo do lado do servidor que possa fazer chamadas HTTP/s.
* Forneça experiências consistentes e personalizadas a um visitante, independentemente de qual canal ou dispositivos o visitante usou para se envolver com sua empresa.
* Armazene em cache as experiências de um visitante em uma sessão do seu servidor para que várias chamadas de API possam ser evitadas, o que melhora o desempenho.
* Faça a integração perfeita com o [!DNL Adobe Experience Cloud] produtos, como [!DNL Adobe Analytics], [!DNL Adobe Audience Manager] (AAM) e [!DNL Experience Cloud ID Service] do lado do servidor.

## SDKs do lado do servidor

Link: [SDKs do Adobe Target](https://developer.adobe.com/target/)

O [!DNL Adobe Target] o portal de documentação do SDK do lado do servidor ajuda a implementar [!DNL Target] nos servidores, no idioma escolhido.

## APIs do Target Recommendations

Link: [APIs do Recommendations do Target](https://developer.adobe.com/target/){target=_blank}.

As APIs do Recommendations permitem interagir programaticamente com [!DNL Target] servidores do recommendations. Essas APIs podem ser integradas a uma variedade de pilhas de aplicativos para executar funções que normalmente seriam realizadas por meio da variável [!DNL Target] interface do usuário.
