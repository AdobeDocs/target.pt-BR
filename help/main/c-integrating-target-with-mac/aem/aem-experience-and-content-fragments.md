---
keywords: aem; experience manager; adobe experience manager; integrar; integração; fragmentos de experiência; fragmentos de conteúdo
description: Saiba como usar [!DNL Adobe Experience Manager] fragmentos de experiência e conteúdo em [!DNL Adobe Target] atividades.
title: Como usar [!DNL Adobe Experience Manager] (AEM) [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo]?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 14%

---

# AEM [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] visão geral

Use [!UICONTROL Fragmentos de experiência] (XFs) e [!UICONTROL Fragmentos de conteúdo] (CFs) criadas em [!DNL Adobe Experience Manager] (AEM) em [!DNL Target] atividades para auxiliar na otimização ou na personalização.

>[!NOTE]
>
>Considere o seguinte ao trabalhar com o AEM [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] em [!DNL Target]:
> 
>* Esses recursos exigem que você [!DNL Adobe Experience Manager] (AEM) cliente. Certifique-se de atender aos requisitos para cada tipo de fragmento: [Fragmento de experiência](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) ou [Fragmento de conteúdo](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
>
>* Esses recursos estão disponíveis para os seguintes tipos de atividades: [!UICONTROL Teste A/B], [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático], [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento de experiência] (XT). Este recurso não está disponível em [!UICONTROL Teste multivariado] (MVT) e [!UICONTROL Recommendations] atividades.
>* Você pode consumir [!UICONTROL Fragmentos de experiência] em [!DNL Target] atividades que utilizam [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).
>
>* Você pode consumir [!UICONTROL Fragmentos de conteúdo] no [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) somente.


Usando [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] criado em [!DNL AEM] em [!DNL Target] As atividades permitem combinar a facilidade de uso e o poder da [!DNL AEM] com poderosos recursos de Inteligência Artificial (AI) e Aprendizagem de Máquina (ML) em [!DNL Target] para testar e personalizar experiências em escala.

O [!DNL AEM] reúne todo o seu conteúdo e ativos em um local central para alimentar sua estratégia de personalização. O [!DNL AEM] permite que você crie conteúdo facilmente para desktops, tablets e dispositivos móveis em um único local sem escrever código. Não há necessidade de criar páginas para cada dispositivo. [!DNL AEM] O ajusta automaticamente cada experiência para cada dispositivo usando o conteúdo.

O [!DNL Target] permite entregar experiências personalizadas em escala com base em uma combinação de abordagens de aprendizagem de máquina baseadas em regras e AI que incorporam variáveis comportamentais, contextuais e offline. Com [!DNL Target], você pode configurar e executar facilmente [Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) e [Multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) para determinar as melhores ofertas, conteúdo e experiências.

[!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] representa um grande passo em frente para vincular os criadores e gerentes de conteúdo/experiência aos profissionais de otimização e personalização que estão gerando resultados comerciais usando [!DNL Target].

## Qual é a diferença entre [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo]?

[!DNL Adobe Experience Manager] [!UICONTROL Fragmentos de experiência] e [!UICONTROL Fragmentos de conteúdo] pode parecer semelhante na superfície, mas cada tipo de fragmento reproduz funções principais em casos de uso diferentes.

Para obter mais informações sobre como [!UICONTROL Fragmentos de conteúdo] e [!UICONTROL Fragmentos de experiência] são semelhantes, diferentes e quando e como usar cada visualização [Entender [!UICONTROL Fragmentos de conteúdo] e [!UICONTROL Fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html){target=_blank}.