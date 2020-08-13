---
keywords: mobile app;frequently asked questions;faq;target mobile app
description: Perguntas frequentes sobre o Adobe Target para aplicativos móveis.
title: Perguntas frequentes sobre o Adobe Target para aplicativos móveis
feature: mobile implementation
topic: Target
uuid: 3d6422ac-7cff-4e0d-9cea-64a64cd1a098
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 2%

---


# Perguntas frequentes sobre o Target para aplicativos móveis

Lista de perguntas frequentes sobre aplicativos [!DNL Target] para dispositivos móveis.

## Devo usar [!DNL Adobe Experience Platform Launch] para implantar o SDK ou posso implantar o SDK sem usar [!DNL Launch]?

O SDK está disponível no git [do](https://github.com/Adobe-Marketing-Cloud/acp-sdks/)Adobe Marketing Cloud. Se você não usar o [Launch](https://docs.adobe.com/content/help/en/launch/using/overview.html), precisará gerenciar seu próprio arquivo de configurações e gerenciá-lo no aplicativo.

## Quais SDKs estão disponíveis hoje?

Os SDKs do Adobe Experience Platform Mobile atualmente são compatíveis com iOS, Android e React. Para obter mais informações, consulte o guia [SDKs móveis da plataforma](https://aep-sdks.gitbook.io/docs/)Adobe Experience Cloud.

## Qual é a frequência do recurso baseado na localização, em termos de verificação da latitude e longitude?

Consulte a documentação [](https://placesdocs.com/places-services-by-adobe-documentation/) Adobe Places para obter mais informações.

## Preciso do at.js para que os SDKs do Adobe Experience Platform Mobile funcionem?

Não, você não precisa do at.js para usar os SDKs móveis. at.js é a biblioteca [!DNL Target] JavaScript para sites. Os SDKs do Adobe Experience Platform Mobile são para aplicativos móveis.

## O Público alvo Mobile é uma funcionalidade do SKU de produto Adobe Target Premium somente?

Não. Para [!DNL Adobe Target Standard] os clientes, você pode usar nossos SDKs móveis para atividades de teste A/B e direcionamento de experiência (XT) somente com o complemento do aplicativo [!DNL Target Standard] Mobile. Se você quiser usar os recursos habilitados para Recommendations ou AI no aplicativo móvel, você precisa de uma licença do [Adobe Target Premium](/help/c-intro/intro.md#premium) .

## Existe uma integração de aplicativo móvel entre o Adobe Experience Manager (AEM) e o Público alvo Mobile atividade?

Está no nosso roteiro, mas ainda não existe um calendário. Atualmente, você pode compartilhar Fragmentos [de](/help/c-experiences/c-manage-content/aem-experience-fragments.md) experiência JSON de AEM para Público alvo e, em seguida, usá-los em uma atividade de aplicativo móvel.
