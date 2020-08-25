---
keywords: experience;json;aem;adobe experience manager;export to adobe target;experience fragments;fragments;XF
description: Informações sobre como usar fragmentos de experiência criados no Adobe Experience Manager (AEM) no Adobe Target atividade para ajudar na otimização ou personalização.
title: Fragmentos de experiência do Adobe Experience Manager (AEM) no Adobe Target
feature: aem
topic: Standard
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: fbb0a4b07f9294846aac88ac692159e658c2c8e2
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 32%

---


# Fragmentos de experiência do AEM{#aem-experience-fragments}

Information about using experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization.

>[!NOTE]
>
>This feature requires that you are an [!DNL Adobe Experience Manager] ([!DNL AEM]) customer. Para obter mais informações, consulte os [Requisitos](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.

## Visão geral {#section_95A91830530F493B81C5C9CDB9B783EA}

Using experience fragments created in [!DNL AEM] in [!DNL Target] activities lets you combine the ease-of-use and power of [!DNL AEM] with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in [!DNL Target] to test and personalize experiences at scale.

[!DNL AEM]O reúne todo o seu conteúdo e ativos em um local central para alimentar sua estratégia de personalização. [!DNL AEM]O permite que você crie conteúdo facilmente para desktops, tablets e dispositivos móveis em um único local sem escrever código. Não há necessidade de criar páginas para cada dispositivo. [!DNL AEM] ajusta automaticamente cada experiência usando seu conteúdo.

[!DNL Target]O permite entregar experiências personalizadas em escala com base em uma combinação de abordagens de aprendizagem de máquina baseadas em regras e AI que incorporam variáveis comportamentais, contextuais e offline. With [!DNL Target] you can easily set up and run [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Multivariate](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) activities to determine the best offers, content, and experiences.

Os fragmentos de experiência representam um enorme passo à frente para vincular os criadores e gerentes de conteúdo/experiência aos profissionais de otimização e personalização que impulsionam os resultados de negócios usando o [!DNL Target].

## Exigências {#section_AE6F0971E1574B3AA324003599B96E5A}

Você deve estar provido da funcionalidade dos fragmentos de experiência dentro do [!DNL Target]. In addition, you must be using [!DNL AEM] 6.3 with the appropriate service pack or [!DNL AEM] 6.4 (or later). Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

* [!DNL Adobe Experience Manager] 6.4 (ou posterior).
* [!DNL Adobe Experience Manager] 6.3 SP2 (ou posterior).
* [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium] conta.
* Contact [Adobe Target Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to enable the integration and to provide you with authentication details.

## Creating and configuring experience fragments in [!DNL AEM] {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use [!DNL AEM] experience fragments in [!DNL Target], you must perform the following steps:

### Etapa 1: Integrar [!DNL AEM] com [!DNL Target]

Para obter mais informações, consulte:

* **[!DNL AEM]6.3**: [Aceitar Adobe Analytics e Adobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) na documentação do _Adobe Experience Manager 6.3_ .
* **[!DNL AEM]6.4**: [Aceitar Adobe Analytics e Adobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) na documentação do _Adobe Experience Manager 6.4_ .
* **[!DNL AEM]6.5**: [Aceitar Adobe Analytics e Adobe Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) na documentação do *Adobe Experience Manager 6.5* .

### Etapa 2: criar o fragmento de experiência

Fragmentos de experiência são criados no [!DNL AEM]. Para obter mais informações, consulte:

* **[!DNL AEM]6.3**: [Fragmentos](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) de experiência na documentação do *Adobe Experience Manager 6.3* .
* **[!DNL AEM]6.4**: [Fragmentos](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) de experiência na documentação do *Adobe Experience Manager 6.4* .
* **[!DNL AEM]6.5**: [Fragmentos](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) de experiência na documentação do *Adobe Experience Manager 6.5* .

### Step 3: Configure [!DNL AEM] to share the experience fragment with [!DNL Target]

1. From within [!DNL AEM], select the desired experience fragment or its containing folder, then click **[!UICONTROL Properties]**.
2. Clique na guia **[!UICONTROL Serviços em nuvem]**, em seguida, na lista suspensa **[!UICONTROL Configuração do serviço em nuvem]**, selecione **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >The previous step assumes that someone in your organization has created the [!DNL Adobe Target] configuration.

3. Clique em **[!UICONTROL Salvar e fechar]**.

### Etapa 4: publique o fragmento de experiência e exporte-o para o [!DNL Target]

Dependendo da sua [!DNL AEM] versão, consulte os seguintes links para obter instruções detalhadas:

* **[!DNL AEM]6.3**: [Exportar um fragmento de experiência para o Público alvo](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) na documentação do *Adobe Experience Manager 6.3* .
* **[!DNL AEM]6.4**: [Exportar um fragmento de experiência para o Público alvo](https://docs.adobe.com/content/help/en/experience-manager-64/administering/integration/experience-fragments-target.html) na documentação do *Adobe Experience Manager 6.4* .
* **[!DNL AEM]6.5**: [Exportar um fragmento de experiência para o Público alvo](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) na documentação do *Adobe Experience Manager 6.5* .

## Using experience fragments in Target activities {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o fragmento de experiência é exibido na página [!UICONTROL Ofertas] no [!DNL Target].

>[!NOTE]
>
>[!DNL Target]No momento, o procura fragmentos de experiência a cada dez minutos. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.

>[!IMPORTANT]
>
>The experience fragment is currently imported into [!DNL Target] as an HTML offer. Note that the experience fragment &quot;primary&quot; version remains in [!DNL AEM]. Você não pode editar o fragmento de experiência no [!DNL Target].

Você pode passar o mouse sobre um fragmento de experiência na lista e, em seguida, clicar no ícone de [!UICONTROL Visualização] ícone de ![Visualização](assets/icon_info.png) para ver informações adicionais sobre o fragmento de experiência, incluindo seu URL de delivery de oferta pública e seu [!DNL AEM] caminho.

You can consume experience fragments in [!DNL Target] activities using the [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) or the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>To fully utilize the [!DNL Target] AI and ML functionality, you can select [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) while creating an A/B Test.

**Para consumir fragmentos de experiência usando o VEC:**

1. Em [!DNL Target], ao criar ou editar uma experiência no [Visual Experience Composer](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), clique no local na página onde deseja inserir o [!DNL AEM] conteúdo e selecione a opção desejada para exibir a lista [!UICONTROL Escolher um fragmento] de experiência.

   * [!UICONTROL Inserir antes]
   * [!UICONTROL Inserir depois de]
   * [!UICONTROL Trocar por fragmento de experiência]

   A lista [!UICONTROL Fragmento de experiência][!DNL AEM] exibe todo o conteúdo criado no que está agora nativamente disponível dentro do [!DNL Target].

   >[!NOTE]
   >
   >A opção [!UICONTROL Trocar com fragmento de experiência] não está disponível para imagens. Se você quiser usar essa opção com uma imagem, clique no elemento de contêiner que contém a imagem desejada.

   ![](assets/experience_fragment_list.png)

1. Select the desired experience fragment, then click **[!UICONTROL Done]**.
1. Termine configurando a atividade.

   Para obter mais informações sobre a configuração de vários tipos de atividades, consulte os tópicos a seguir:

   * **Teste A/B:** [criar um teste A/B](../../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72)
   * **Autoalocação:** [autoalocação](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4)
   * **Segmentação automática:** [segmentação automática para experiências personalizadas](../../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3)
   * **Para obter mais informações, consulte** [Criação de uma atividade de Personalização automatizada](../../c-activities/t-automated-personalization/create-ap-activity.md#task_8AAF837796D74CF893CA2F88BA1491C9)
   * **Direcionamento de experiência (XT):** [criar uma atividade de direcionamento de experiência](../../c-activities/t-experience-target/t-xt-create/xt-create.md#task_D6B3429AC31549E1A70EDF04B3DDC765)
   * **Teste multivariado (MVT):** [criar um teste multivariado](../../c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md#task_BF870FA60A8245AB8F0B775BE32EA710)
   * **Recommendations:** [criar uma atividade do Recommendations](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F)

**Para consumir fragmentos de experiência usando o Criador de experiências baseado em forma:**

1. Em [!DNL Target], ao criar ou editar uma experiência no Criador de experiências baseado em [formulário](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local na página onde deseja inserir o [!DNL AEM] conteúdo e, em seguida, selecione **[!UICONTROL Alterar fragmento]** de experiência para exibir a lista [!UICONTROL Escolher um fragmento] de experiência.

   ![](assets/experience_fragment_list.png)

   A lista [!UICONTROL Fragmento de experiência][!DNL AEM] exibe todo o conteúdo criado no que está agora nativamente disponível dentro do [!DNL Target].

1. Selecione o fragmento de experiência desejado e clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Considerações {#considerations}

* [!DNL Target]No momento, o procura fragmentos de experiência a cada dez minutos. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
* The experience fragment is currently imported into [!DNL Target] as an HTML offer. Note that the experience fragment &quot;primary&quot; version remains in [!DNL AEM]. Você não pode editar o fragmento de experiência no [!DNL Target].
* É possível importar ofertas JSON como fragmentos de experiência para [!DNL Target]. No entanto, essas ofertas são importadas como ofertas HTML. No momento, as ofertas JSON (fragmentos de experiência) não são totalmente suportadas na [!DNL Target] interface do usuário.

## Training video: Using AEM experience fragments with Adobe Target ![Tutorial badge](/help/assets/overview.png) {#section_C0EDC54063464F41A182492D2045BC64}

O vídeo a seguir mostra como configurar e usar fragmentos de experiência:

>[!VIDEO](https://video.tv.adobe.com/v/22383)

>[!NOTE]
>
>O recurso de [!DNL AEM] deep link discutido às 4:54 foi removido.

Para obter mais informações, consulte [Uso de fragmentos de experiência com o Adobe Target](https://docs.adobe.com/content/help/en/experience-manager-learn/sites/personalization/experience-fragment-target-offer-feature-video-use.html) na página Vídeos e Tutorials *do* AEM Sites.
