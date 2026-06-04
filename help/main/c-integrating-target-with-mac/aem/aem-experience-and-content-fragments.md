---
keywords: aem;experience manager;adobe experience manager;integrar;integração;fragmentos de experiência;fragmentos de conteúdo
description: Saiba como usar fragmentos de experiência e de conteúdo do  [!DNL Adobe Experience Manager]  em atividades do  [!DNL Adobe Target] .
title: Como usar os  [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo]?
feature: Integrations
exl-id: 6f1a02da-8f59-4a8b-8e97-c20444ef53c8
TQID: https://experienceleague.adobe.com/OlgveSjoE0rh1orFsbEZVCSbjd3TKEk8fdBbbXtLxhA
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bbbea26f-9621-49eb-9ab8-e06fb3bbce8c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e6ff21d3-dec6-4298-8590-7c749fffaf78
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 407
ht-degree: 40%

---

# Visão geral dos [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] do AEM

Use os [!UICONTROL Fragmentos de Experiência] (XFs) e os [!UICONTROL Fragmentos de Conteúdo] (CFs) criados no [!DNL Adobe Experience Manager] (AEM) em [!DNL Target] atividades para auxiliar na otimização e na personalização.

Os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] criados no [!DNL AEM] em [!DNL Target] atividades permitem combinar a facilidade de uso e o poder do [!DNL AEM] com os poderosos recursos de Inteligência Artificial (AI) e Aprendizado de Máquina (ML) do [!DNL Target] para testar e personalizar experiências em escala.

O [!DNL AEM] reúne todo o seu conteúdo e ativos em um local central para alimentar sua estratégia de personalização. O [!DNL AEM] permite que você crie conteúdo facilmente para desktops, tablets e dispositivos móveis em um único local sem escrever código. Não há necessidade de criar páginas para cada dispositivo. O [!DNL AEM] ajusta automaticamente cada experiência para cada dispositivo usando o conteúdo.

O [!DNL Target] permite entregar experiências personalizadas em escala com base em uma combinação de abordagens de aprendizado de máquina baseadas em regras e IA que incorporam variáveis comportamentais, contextuais e offline.

Os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] representam um enorme passo à frente para vincular os criadores e gerentes de conteúdo/experiência aos profissionais de otimização e personalização que impulsionam os resultados de negócios usando o [!DNL Target].

## Considerações

Considere o seguinte ao trabalhar com os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] do AEM em [!DNL Target]:
* Esses recursos exigem que você seja um cliente do [!DNL Adobe Experience Manager] (AEM). Certifique-se de atender aos requisitos para cada tipo de fragmento: [fragmento de experiência](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) ou [fragmento de conteúdo](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
* Os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL Teste A/B]](/help/main/c-activities/t-test-ab/test-ab.md)
   * [[!UICONTROL Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)
   * [[!UICONTROL Direcionamento automático]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)
   * [[!UICONTROL Automated Personalization] (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md)
   * [[!UICONTROL Direcionamento de experiência] (XT)](/help/main/c-activities/t-experience-target/experience-target.md)

* Os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] não estão disponíveis para os seguintes tipos de atividades:

   * [[!UICONTROL Teste multivariado] (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md)
   * [[!UICONTROL Recomendações]](/help/main/c-recommendations/recommendations.md)

* Você pode consumir [!UICONTROL Fragmentos de experiência] em [!DNL Target] atividades usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) e o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).
* Você pode consumir [!UICONTROL Fragmentos de conteúdo] em [!DNL Target] atividades usando somente o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

## Qual é a diferença entre [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo]?

[!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] podem parecer semelhantes na superfície, mas cada tipo de fragmento desempenha funções principais em casos de uso diferentes.

Para obter mais informações sobre como os [!UICONTROL Fragmentos de experiência] e os [!UICONTROL Fragmentos de conteúdo] são semelhantes, diferentes e quando e como usar cada um, consulte [Entender sobre os [!UICONTROL Fragmentos de conteúdo] e os [!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=pt-BR){target=_blank} no [guia de vídeos e tutoriais do AEM Sites](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=pt-BR){target=_blank}.
