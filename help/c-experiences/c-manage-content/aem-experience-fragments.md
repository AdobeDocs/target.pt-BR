---
description: Informações sobre como usar os fragmentos de experiência criados no Adobe Experience Manager (AEM) nas atividades do Target para auxiliar a otimização ou a personalização.
keywords: experience;aem;adobe experience manager;exportar para adobe target;fragmentos de experiência;fragmentos;XF
seo-description: Informações sobre como usar os fragmentos de experiência criados no Adobe Experience Manager (AEM) nas atividades do Target para auxiliar a otimização ou a personalização.
seo-title: Fragmentos de experiência do AEM
solution: Target
title: Fragmentos de experiência do AEM
topic: Padrão
uuid: 4dc2b5da-524f-4d6a-8ffc-8c3ac78cb39e
translation-type: tm+mt
source-git-commit: 35e22ec50ef1f128563ac255c202c14a0d674c03

---


# Fragmentos de experiência do AEM{#aem-experience-fragments}

Informações sobre como usar os fragmentos de experiência criados no Adobe Experience Manager (AEM) nas atividades do Target para auxiliar a otimização ou a personalização.

## Fragmentos de experiência do AEM {#topic_1E1E4EA01F074349B2CF8785387B5FE8}

Informações sobre como usar os fragmentos de experiência criados no Adobe Experience Manager (AEM) nas atividades do Target para auxiliar a otimização ou a personalização.

>[!NOTE]
>
>Esse recurso exige que você seja um cliente do Adobe Experience Manager (AEM). Para obter mais informações, consulte os [Requisitos](../../c-experiences/c-manage-content/aem-experience-fragments.md#section_AE6F0971E1574B3AA324003599B96E5A) abaixo.

## Visão geral {#section_95A91830530F493B81C5C9CDB9B783EA}

A utilização de fragmentos de experiência criados no AEM nas atividades do Target permite combinar a facilidade de uso e o poder do AEM com os poderosos recursos de Inteligência automatizada (AI) e Aprendizagem de Máquina (ML) no Target para testar e personalizar experiências em escala.

O AEM reúne todo o seu conteúdo e ativos em um local central para alimentar sua estratégia de personalização. O AEM permite que você crie conteúdo facilmente para desktops, tablets e dispositivos móveis em um único local sem escrever código. Não há necessidade de criar páginas para cada dispositivo. O AEM ajusta automaticamente cada experiência usando seu conteúdo. 

O Target permite entregar experiências personalizadas em escala com base em uma combinação de abordagens de aprendizagem de máquina baseadas em regras e AI que incorporam variáveis comportamentais, contextuais e offline.  Com o Target você pode configurar e executar facilmente atividades A/B e multivariadas (MVT) para determinar as melhores ofertas, conteúdo e experiências.

Os fragmentos de experiência representam um enorme passo à frente para vincular os criadores e gerentes de conteúdo/experiência aos profissionais de otimização e personalização que impulsionam os resultados de negócios usando o Target.

## Exigências {#section_AE6F0971E1574B3AA324003599B96E5A}

Você deve estar provido da funcionalidade dos fragmentos de experiência dentro do Target. Além disso, o AEM 6.3 deve ser usado com o service pack apropriado ou o AEM 6.4 (ou posterior). Seu representante de conta pode ajudar a assegurar que você atenda aos requisitos para usar este recurso:

* Adobe Experience Manager 6.4 (ou posterior).
* Adobe Experience Manager 6.3 SP2 (ou posterior).
* Conta do Adobe Target Standard ou Premium.
* Entre em contato com o Atendimento ao cliente do Adobe Target para ativar a integração e informar os detalhes de autenticação.

## Criação e configuração dos Fragmentos de experiência no AEM {#section_745C8EFE29F547A2958FDBF61A5ADF7B}

Para usar fragmentos de experiência do AEM no Target, você deve executar as seguintes etapas:

### Etapa 1: integrar o AEM ao Target

Para obter mais informações, consulte:

* **AEM 6.3:**[ativação do Adobe Analytics e do Adobe Target](https://docs.adobe.com/docs/en/aem/6-3/administer/integration/marketing-cloud/opt-in.html) na documentação do _Adobe Experience Manager 6.3_.
* **AEM 6.4:**[ativação do Adobe Analytics e do Adobe Target](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/opt-in.html) na documentação do _Adobe Experience Manager 6.4_.

### Etapa 2: criar o fragmento de experiência

Fragmentos de experiência são criados no AEM. Para obter mais informações, consulte:

* **AEM 6.3:**[fragmentos de experiência](https://docs.adobe.com/docs/en/aem/6-3/author/experience-fragments.html) na documentação do *Adobe Experience Manager 6.3*.
* **AEM 6.4:**[fragmentos de experiência](https://helpx.adobe.com/experience-manager/6-4/sites/authoring/using/experience-fragments.html) na documentação do *Adobe Experience Manager 6.4*.

### Etapa 3: configurar o AEM para compartilhar o fragmento de experiência com o Target

1. Dentro do AEM, selecione o fragmento de experiência desejado ou a pasta que o contém, depois clique em [!UICONTROL Propriedades].
2. Clique na guia [!UICONTROL Serviços em nuvem], em seguida, na lista suspensa [!UICONTROL Configuração do serviço em nuvem], selecione [!UICONTROL Adobe Target].

   >[!NOTE]
   >
   >A etapa anterior pressupõe que alguém em sua organização tenha criado a configuração do Adobe Target.

3. Clique em [!UICONTROL Salvar e fechar].

### Etapa 4: publique o fragmento de experiência e exporte-o para o Target

**AEM 6.3:**

1. No AEM, selecione o fragmento de experiência desejado, clique na guia [!UICONTROL Publicar], e, em seguida, clique no botão [!UICONTROL Publicar].
2. No AEM, selecione o fragmento de experiência desejado, clique em [!UICONTROL Exportar para Adobe Target], e clique em [!UICONTROL OK].

   ![](assets/experience_fragment_export_to_target.png)

**AEM 6.4:**

1. Dentro do AEM, selecione o fragmento de experiência desejado, clique em [!UICONTROL Exportar para o Adobe Target].

   ![](assets/experience_fragment_export_to_target.png)

2. Na caixa de diálogo exibida, selecione [!UICONTROL Publicar] para publicar todos os ativos do fragmento de experiência no [!DNL Target].

## Uso de fragmentos de experiência nas atividades do Target {#section_17CE4BE6B2B74CCEBAE0C68DEB84ABB9}

Depois de executar as tarefas anteriores, o fragmento de experiência é exibido na página [!UICONTROL Ofertas] no Target.

>[!NOTE]
>
>No momento, o Target procura fragmentos de experiência a cada dez minutos. O fragmento de experiência importado deve estar disponível no Target dentro de dez minutos, mas essa janela de tempo deve ficar mais curta no futuro.

>[!IMPORTANT]
>
>O fragmento de experiência é importado no momento para o Target como uma oferta HTML. Observe que a versão &quot;mestre&quot; do fragmento de experiência permanece no AEM. Você não pode editar o fragmento de experiência no Target.

Você pode passar o mouse sobre um fragmento de experiência na lista e clicar no ícone Exibir ( ![](assets/icon_info.png)

) para ver informações adicionais sobre o fragmento de experiência, incluindo o URL de entrega de ofertas públicas, seu caminho AEM e um deep link para abrir o fragmento de experiência no AEM.

Você pode consumir fragmentos de experiência em atividades do Target usando o Visual Experience Composer (VEC) ou o Experience Compositor baseado em formulário.

>[!NOTE]
>
>Para utilizar totalmente a funcionalidade AI e ML do Target, você pode selecionar [Autoalocação](../../c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) ou [Personalização automatizada](../../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) ao criar um teste A/B.

**Para consumir Fragmentos de experiência usando o VEC:**

1. No Target, durante a criação ou edição de uma experiência no [Visual Experience Composer](../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D), clique no local na página onde você deseja inserir conteúdo AEM e, em seguida, selecione **[!UICONTROL Trocar com fragmento de experiência]** para exibir a lista [!UICONTROL Escolher um fragmento de experiência].

   >[!NOTE]
   >
   >A opção [!UICONTROL Trocar com fragmento de experiência] não está disponível para imagens. Se você quiser usar essa opção com uma imagem, clique no elemento de contêiner que contém a imagem desejada.

   A lista [!UICONTROL Fragmento de experiência] exibe todo o conteúdo criado no AEM que está agora nativamente disponível dentro do Target.

   ![](assets/experience_fragment_list.png)

1. Selecione o fragmento de experiência desejado e clique em **[!UICONTROL Salvar]**.
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

1. No Target, durante a criação ou edição de uma experiência no [Experience Composer baseado em formulário](../../c-experiences/form-experience-composer.md#task_FAC842A6535045B68B4C1AD3E657E56E), selecione o local na página onde você deseja inserir conteúdo AEM e selecione **[!UICONTROL Alterar fragmento de experiência]** para exibir a lista [!UICONTROL Escolher um fragmento de experiência].

   ![](assets/experience_fragment_list.png)

   A lista [!UICONTROL Fragmento de experiência] exibe todo o conteúdo criado no AEM que está agora nativamente disponível dentro do Target.

1. Selecione o fragmento de experiência desejado e clique em **[!UICONTROL Salvar]**.
1. Termine configurando a atividade.

## Vídeo de treinamento: uso de fragmentos de experiência do AEM com o Adobe Target {#section_C0EDC54063464F41A182492D2045BC64}

O vídeo a seguir mostra como configurar e usar os fragmentos de experiência: [Uso dos fragmentos de experiência do AEM com o Adobe Target](https://helpx.adobe.com/experience-manager/kt/sites/using/experience-fragment-target-feature-video-use.html).
