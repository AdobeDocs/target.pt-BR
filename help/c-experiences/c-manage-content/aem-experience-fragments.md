---
description: Informações sobre como usar os fragmentos de experiência criados no Adobe Experience Manager (AEM) nas atividades do Target para auxiliar a otimização ou a personalização.
keywords: experiência; json; aem; adobe experience manager; exportar para o adobe target; fragmentos de experiência; fragmentos; XF
seo-description: Informações sobre o uso de fragmentos de experiência criados no Adobe Experience Manager (AEM) nas atividades do Adobe Target para auxiliar na otimização ou na personalização.
seo-title: Fragmentos de experiência do Adobe Experience Manager (AEM) no Adobe Target
solution: Target
title: Fragmentos de experiência do AEM
topic: Padrão
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: aee1785aede1894cac9632da7a0471ae429c8bc6

---


# Fragmentos de experiência do AEM{#aem-experience-fragments}

Information about using experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization.

>[!NOTE]
>
>This feature requires that you are an [!DNL Adobe Experience Manager] (AEM) customer. Para obter mais informações, consulte os [Requisitos](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.

## Visão geral {#section_95A91830530F493B81C5C9CDB9B783EA}

Using experience fragments created in AEM in [!DNL Target] activities lets you combine the ease-of-use and power of AEM with powerful Automated Intelligence (AI) and Machine Learning (ML) capabilities in [!DNL Target] to test and personalize experiences at scale.

O AEM reúne todo o seu conteúdo e ativos em um local central para alimentar sua estratégia de personalização. O AEM permite que você crie conteúdo facilmente para desktops, tablets e dispositivos móveis em um único local sem escrever código. Não há necessidade de criar páginas para cada dispositivo. O AEM ajusta automaticamente cada experiência usando seu conteúdo.

[!DNL Target]O permite entregar experiências personalizadas em escala com base em uma combinação de abordagens de aprendizagem de máquina baseadas em regras e AI que incorporam variáveis comportamentais, contextuais e offline. With [!DNL Target] you can easily set up and run [A/B Test](/help/c-activities/t-test-ab/test-ab.md) and [Multivariate](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) activities to determine the best offers, content, and experiences.

Os fragmentos de experiência representam um enorme passo à frente para vincular os criadores e gerentes de conteúdo/experiência aos profissionais de otimização e personalização que impulsionam os resultados de negócios usando o [!DNL Target].

## Exigências {#section_AE6F0971E1574B3AA324003599B96E5A}

You must be provisioned with the experience fragments functionality within [!DNl Target]. Além disso, o AEM 6.3 deve ser usado com o service pack apropriado ou o AEM 6.4 (ou posterior). Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

* Adobe Experience Manager 6.4 (ou posterior).
* Adobe Experience Manager 6.3 SP2 (ou posterior).
* Conta do Adobe Target Standard ou Adobe Target Premium.
* Contact [Adobe Target Customer Care](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) to enable the integration and to provide you with authentication details.

## Criação e configuração dos Fragmentos de experiência no AEM {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

In order to use AEM experience fragments in [!DNL Target], you must perform the following steps:

### Etapa 1: integrar o AEM ao Target

Para obter mais informações, consulte:

* **AEM 6.3**: [Escolha o Adobe Analytics e o Adobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) na documentação _do Adobe Experience Manager 6.3_ .
* **AEM 6.4**: [Escolha o Adobe Analytics e o Adobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) na documentação _do Adobe Experience Manager 6.4_ .
* **AEM 6.5**: [Escolha o Adobe Analytics e o Adobe Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/opt-in.html) na documentação *do Adobe Experience Manager 6.5* .

### Etapa 2: criar o fragmento de experiência

Fragmentos de experiência são criados no AEM. Para obter mais informações, consulte:

* **AEM 6.3**: [Fragmentos de experiência](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) na documentação *do Adobe Experience Manager 6.3* .
* **AEM 6.4**: [Fragmentos de experiência](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) na documentação *do Adobe Experience Manager 6.4* .
* **AEM 6.5**: [Fragmentos de experiência](https://helpx.adobe.com/experience-manager/6-5/sites/authoring/using/experience-fragments.html) na documentação *do Adobe Experience Manager 6.5* .

### Etapa 3: configurar o AEM para compartilhar o fragmento de experiência com o Target

1. Dentro do AEM, selecione o fragmento de experiência desejado ou a pasta que o contém, depois clique em **[!UICONTROL Propriedades]**.
2. Click the **[!UICONTROL Cloud Services]** tab, then from the **[!UICONTROL Cloud Service Configuration]** drop-down list, select **[!UICONTROL Adobe Target]**.

   >[!NOTE]
   >
   >The previous step assumes that someone in your organization has created the [!DNL Adobe Target] configuration.

3. Clique em **[!UICONTROL Salvar e fechar]**.

### Etapa 4: publique o fragmento de experiência e exporte-o para o Target

Dependendo da sua versão do AEM, consulte os links a seguir para obter instruções passo a passo:

* **AEM 6.3**: [Exportar um fragmento de experiência para o Target](https://helpx.adobe.com/experience-manager/6-3/sites/administering/using/experience-fragments-target.html) na documentação *do Adobe Experience Manager 6.3* .
* **AEM 6.4**: [Exportar um fragmento de experiência para o Target](https://docs.adobe.com/content/help/en/experience-manager-64/administering/integration/experience-fragments-target.html) na documentação *do Adobe Experience Manager 6.4* .
* **AEM 6.5**: [Exportar um fragmento de experiência para o Target](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/experience-fragments-target.html) na documentação *do Adobe Experience Manager 6.5* .

## Uso de fragmentos de experiência nas atividades do Target {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o fragmento de experiência é exibido na página [!UICONTROL Ofertas] no Target.

>[!NOTE]
>
>[!DNL Target]No momento, o procura fragmentos de experiência a cada dez minutos. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.

>[!IMPORTANT]
>
>The experience fragment is currently imported into [!DNL Target] as an HTML offer. Observe que a versão "mestre" do fragmento de experiência permanece no AEM. Você não pode editar o fragmento de experiência no Target.

You can hover over an experience fragment in the list, then click the View icon ![View icon](assets/icon_info.png) to see additional information about the experience fragment, including its public offer delivery URL, its AEM path, and a deep link to open the experience fragment inside of AEM.

You can consume Experience Fragments in [!DNL Target] activities using the [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) or the [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>To fully utilize the [!DNL Target] AI and ML functionality, you can select [Auto-Allocate](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) or [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) while creating an A/B Test.

**Para consumir Fragmentos de experiência usando o VEC:**

1. No [!DNL Target], ao criar ou editar uma experiência no [Visual Experience Composer](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), clique no local na página onde deseja inserir conteúdo AEM e selecione a opção desejada para exibir a lista [!UICONTROL Escolher um fragmento] de experiência.

   * [!UICONTROL Inserir antes]
   * [!UICONTROL Inserir depois de]
   * [!UICONTROL Trocar com fragmento de experiência]
   A lista [!UICONTROL Fragmento de experiência] exibe todo o conteúdo criado no AEM que está agora nativamente disponível dentro do [!DNL Target].

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

**Para consumir Fragmentos de experiência usando o Experience Composer baseado em formulário:**

1. No [!DNl Target], ao criar ou editar uma experiência no Criador de experiências [baseado em forma](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local na página onde deseja inserir conteúdo AEM e selecione **[!UICONTROL Alterar fragmento de experiência]** para exibir a lista [!UICONTROL Escolher um fragmento] de experiência.

   ![](assets/experience_fragment_list.png)

   A lista [!UICONTROL Fragmento de experiência] exibe todo o conteúdo criado no AEM que está agora nativamente disponível dentro do [!DNL Target].

1. Selecione o fragmento de experiência desejado e clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Considerações (# considerações)

* [!DNL Target]No momento, o procura fragmentos de experiência a cada dez minutos. The imported experience fragment should be available in [!DNL Target] within ten minutes, but this time frame should shorten going forward.
* The experience fragment is currently imported into [!DNL Target] as an HTML offer. Observe que a versão "mestre" do fragmento de experiência permanece no AEM. Você não pode editar o fragmento de experiência no [!DNL Target].
* É possível importar ofertas JSON como fragmentos de experiência. [!DNL Target] Contudo, essas ofertas são importadas como ofertas HTML. No momento, ofertas JSON (fragmentos de experiência) não são totalmente compatíveis na [!DNL Target] interface do usuário.

## Vídeo de treinamento: uso de fragmentos de experiência do AEM com o Adobe Target {#section_C0EDC54063464F41A182492D2045BC64}

O vídeo a seguir mostra como configurar e usar os fragmentos de experiência: [Uso dos fragmentos de experiência do AEM com o Adobe Target](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html).
