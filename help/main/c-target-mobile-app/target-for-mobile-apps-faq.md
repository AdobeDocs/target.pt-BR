---
keywords: aplicativo móvel, perguntas frequentes, perguntas frequentes, aplicativo móvel target
description: Exibir perguntas frequentes e suas respostas sobre o Adobe [!DNL Target] para aplicativos móveis.
title: Perguntas frequentes sobre [!DNL Target] para aplicativos móveis?
feature: Implement Mobile
role: Developer
exl-id: 1ddd8345-e753-4608-9293-939e092cb16d
source-git-commit: 2dad7d51935cd1550f60218e63277b84ce9088ac
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 3%

---

# Perguntas frequentes sobre o Target para aplicativos móveis

Lista de perguntas frequentes sobre [!DNL Target] para aplicativos móveis.

## Devo usar tags em [!DNL Adobe Experience Platform] para implantar o SDK ou posso implantar o SDK sem usar [!DNL Launch]?

O SDK está disponível no [Adobe Marketing Cloud git](https://github.com/Adobe-Marketing-Cloud/acp-sdks/). Se você não usar [tags no Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR), você deve gerenciar seu próprio arquivo de configurações e gerenciá-lo no aplicativo.

## Quais SDKs estão disponíveis hoje?

Atualmente, os SDKs do Adobe Experience Platform Mobile são compatíveis com iOS, Android e React. Para obter mais informações, consulte o [Guia de SDKs móveis da Adobe Experience Cloud Platform](https://aep-sdks.gitbook.io/docs/).

## Qual é a frequência do recurso baseado na localização, em termos de verificação sobre a latitude e a longitude?

Consulte a [Documentação do Adobe Places Service](https://experienceleague.adobe.com/docs/places/using/home.html) para obter mais informações.

## A at.js é necessária para que os SDKs do Adobe Experience Platform Mobile funcionem?

Não, você não precisa que a at.js use os SDKs móveis. at.js é a variável [!DNL Target] Biblioteca de JavaScript para sites. Os SDKs do Adobe Experience Platform Mobile são para aplicativos móveis.

## Is [!DNL Target] Mobile uma funcionalidade do Adobe [!DNL Target] Somente SKU do produto Premium?

Não. Para [!DNL Adobe Target Standard] clientes, você pode usar nossos SDKs móveis para atividades de Teste A/B e Direcionamento de experiência (XT) somente com a [!DNL Target Standard] Complemento do aplicativo móvel. Se quiser usar recursos alimentados por Recommendations ou IA no aplicativo móvel, é necessário um [Adobe Target Premium](/help/main/c-intro/intro.md#premium) licença.

## Existe uma integração de aplicativo móvel entre o Adobe Experience Manager (AEM) e o [!DNL Target] atividades móveis?

Está no nosso roteiro, mas ainda não existe um calendário. Atualmente, você pode compartilhar JSON [Fragmentos de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) do AEM ao Target e pode haver potencial para usá-los em uma atividade de aplicativo móvel.
