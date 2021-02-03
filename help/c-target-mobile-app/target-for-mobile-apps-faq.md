---
keywords: aplicativo móvel;perguntas frequentes;aplicativo móvel público alvo;aplicativo móvel
description: Perguntas frequentes sobre o Adobe Target para aplicativos móveis.
title: Perguntas frequentes sobre o Público alvo para aplicativos móveis
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 2%

---


# Perguntas frequentes sobre o Target para aplicativos móveis

Lista de perguntas frequentes sobre [!DNL Target] para aplicativos móveis.

## Devo usar [!DNL Adobe Experience Platform Launch] para implantar o SDK, ou posso implantar o SDK sem usar [!DNL Launch]?

O SDK está disponível no [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Se você não usar [Iniciar](https://experienceleague.adobe.com/docs/launch/using/overview.html), precisará gerenciar seu próprio arquivo de configurações e gerenciá-lo no aplicativo.

## Quais SDKs estão disponíveis hoje?

Os SDKs do Adobe Experience Platform Mobile atualmente são compatíveis com iOS, Android e React. Para obter mais informações, consulte o guia [SDKs móveis da plataforma Adobe Experience Cloud](https://aep-sdks.gitbook.io/docs/).

## Qual é a frequência do recurso baseado na localização, em termos de verificação da latitude e longitude?

Consulte a documentação [Locais de Adobe](https://placesdocs.com/places-services-by-adobe-documentation/) para obter mais informações.

## Preciso do at.js para que os SDKs do Adobe Experience Platform Mobile funcionem?

Não, você não precisa do at.js para usar os SDKs móveis. at.js é a [!DNL Target] biblioteca JavaScript para sites. Os SDKs do Adobe Experience Platform Mobile são para aplicativos móveis.

## O Público alvo Mobile é uma funcionalidade do SKU de produto Adobe Target Premium somente?

Não. Para clientes [!DNL Adobe Target Standard], você pode usar nossos SDKs móveis para atividades de teste A/B e direcionamento de experiência (XT) somente com o complemento [!DNL Target Standard] do aplicativo móvel. Se você quiser usar os recursos habilitados para Recommendations ou AI no aplicativo móvel, você precisa de uma licença [Adobe Target Premium](/help/c-intro/intro.md#premium).

## Existe uma integração de aplicativo móvel entre o Adobe Experience Manager (AEM) e o Público alvo Mobile atividade?

Está no nosso roteiro, mas ainda não existe um calendário. Atualmente, você pode compartilhar JSON [Fragmentos de experiência](/help/c-experiences/c-manage-content/aem-experience-fragments.md) de AEM para Público alvo e pode haver potencial para usá-los em uma atividade de aplicativo móvel.
