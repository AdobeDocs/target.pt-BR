---
keywords: aplicativo móvel, perguntas frequentes, perguntas frequentes, aplicativo móvel target
description: Veja perguntas frequentes e suas respostas sobre o Adobe [!DNL Target] para aplicativos móveis.
title: Quais são as perguntas frequentes sobre o  [!DNL Target] para aplicativos móveis?
feature: Implementar dispositivos móveis
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 1%

---

# Perguntas frequentes sobre o Target para aplicativos móveis

Lista de perguntas frequentes sobre [!DNL Target] para aplicativos móveis.

## Devo usar [!DNL Adobe Experience Platform Launch] para implantar o SDK, ou posso implantar o SDK sem usar [!DNL Launch]?

O SDK está disponível no [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Se você não usar [o Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html), deverá gerenciar seu próprio arquivo de configurações e gerenciá-lo no aplicativo.

## Quais SDKs estão disponíveis hoje?

Atualmente, os SDKs do Adobe Experience Platform Mobile são compatíveis com iOS, Android e React. Para obter mais informações, consulte o [Guia de SDKs móveis da plataforma Adobe Experience Cloud](https://aep-sdks.gitbook.io/docs/).

## Qual é a frequência do recurso baseado na localização, em termos de verificação sobre a latitude e a longitude?

Consulte a documentação do [Adobe Places](https://placesdocs.com/places-services-by-adobe-documentation/) para obter mais informações.

## A at.js é necessária para que os SDKs do Adobe Experience Platform Mobile funcionem?

Não, você não precisa que a at.js use os SDKs móveis. at.js é a [!DNL Target] biblioteca JavaScript para sites. Os SDKs do Adobe Experience Platform Mobile são para aplicativos móveis.

## O [!DNL Target] Mobile é uma funcionalidade do SKU do produto Adobe [!DNL Target] Premium apenas?

Não. Para clientes [!DNL Adobe Target Standard], você pode usar nossos SDKs móveis para atividades de Teste A/B e Direcionamento de experiência (XT) somente com o complemento [!DNL Target Standard] Aplicativo móvel . Se quiser usar recursos alimentados por Recommendations ou AI no aplicativo móvel, você precisa de uma licença do Adobe Target Premium](/help/c-intro/intro.md#premium).[

## Existe uma integração de aplicativo móvel entre as atividades móveis Adobe Experience Manager (AEM) e [!DNL Target]?

Está no nosso roteiro, mas ainda não existe um calendário. No momento, você pode compartilhar JSON [Fragmentos de experiência](/help/c-experiences/c-manage-content/aem-experience-fragments.md) do AEM para o Target e pode haver potencial para usá-los em uma atividade de aplicativo móvel.
