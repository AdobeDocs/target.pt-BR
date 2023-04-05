---
keywords: aem;experience manager;adobe experience manager;integrar;integração;fragmentos de experiência;fragmentos de conteúdo
description: Saiba como usar fragmentos de experiência e de conteúdo do  [!DNL Adobe Experience Manager]  em atividades do  [!DNL Adobe Target] .
title: Como usar [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] do  [!DNL Adobe Experience Manager]  (AEM)?
feature: Integrations
source-git-commit: 0135831b56c48b0adca49e843c5ddd6574358aa4
workflow-type: ht
source-wordcount: '396'
ht-degree: 100%

---

# Visão geral dos [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] do AEM

Use os [!UICONTROL fragmentos de experiência] (XFs) e [!UICONTROL fragmentos de conteúdo] (CFs) criados no [!DNL Adobe Experience Manager] (AEM) em atividades do [!DNL Target] para auxiliar na otimização ou personalização.

>[!NOTE]
>
>Considere o seguinte ao trabalhar com os [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] do AEM no [!DNL Target]:
> 
>* Esses recursos exigem que você seja um cliente do [!DNL Adobe Experience Manager] (AEM). Certifique-se de atender aos requisitos para cada tipo de fragmento: [fragmento de experiência](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md#requirements) ou [fragmento de conteúdo](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md#requirements).
>
>* Esses recursos estão disponíveis para os seguintes tipos de atividades: [!UICONTROL Teste A/B], [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático], [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento de experiência] (XT). Este recurso não está disponível nas atividades de [!UICONTROL Teste multivariado] (MVT) e do [!UICONTROL Recommendations].
>* Você pode consumir [!UICONTROL fragmentos de experiência] em atividades do [!DNL Target] usando o [Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).
>
>* Você pode consumir [!UICONTROL fragmentos de conteúdo] usando apenas o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).


A utilização de [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] criados no [!DNL AEM] em atividades do [!DNL Target] permite combinar a facilidade de uso e o potencial do [!DNL AEM] com os eficientes recursos de inteligência artificial (IA) e aprendizado de máquina (ML) do [!DNL Target] para testar e personalizar experiências em escala.

O [!DNL AEM] reúne todo o seu conteúdo e ativos em um local central para alimentar sua estratégia de personalização. O [!DNL AEM] permite que você crie conteúdo facilmente para desktops, tablets e dispositivos móveis em um único local sem escrever código. Não há necessidade de criar páginas para cada dispositivo. O [!DNL AEM] ajusta automaticamente cada experiência para cada dispositivo usando o conteúdo.

O [!DNL Target] permite entregar experiências personalizadas em escala com base em uma combinação de abordagens de aprendizado de máquina baseadas em regras e IA que incorporam variáveis comportamentais, contextuais e offline. Com o [!DNL Target], você pode configurar e executar atividades de [teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) e [teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) com facilidade, a fim de determinar as melhores ofertas, experiências e conteúdo.

Os [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] representam um enorme avanço para conectar os criadores e gerentes de conteúdo/experiência aos profissionais de otimização e personalização que impulsionam os resultados comerciais usando o [!DNL Target].

## Qual é a diferença entre os [!UICONTROL fragmentos de experiência] e os [!UICONTROL fragmentos de conteúdo]?

Os [!UICONTROL fragmentos de experiência] e [!UICONTROL fragmentos de conteúdo] do [!DNL Adobe Experience Manager] podem parecer semelhantes na superfície, mas cada tipo de fragmento desempenha um papel importante em casos de uso diferentes.

Para obter mais informações sobre as similaridades e diferenças dos [!UICONTROL fragmentos de conteúdo] e [!UICONTROL fragmentos de experiência], e saber quando e como usar cada um, consulte [Entenda os [!UICONTROL fragmentos de conteúdo] e [!UICONTROL fragmentos de experiência]](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/content-fragments/understand-content-fragments-and-experience-fragments.html?lang=pt-BR){target=_blank} in the [AEM Sites videos and tutorials guide](https://experienceleague.adobe.com/docs/experience-manager-learn/sites/overview.html?lang=pt-BR){target=_blank}.