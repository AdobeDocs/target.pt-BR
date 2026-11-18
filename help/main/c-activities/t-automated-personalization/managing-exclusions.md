---
keywords: deduplicação;permitir duplicatas;excluir ofertas duplicadas;personalização automatizada;não permitir ofertas duplicadas;excluir;conteúdo padrão;
description: Gerenciar exclusões nas atividades de [!UICONTROL Automated Personalization] (AP).
title: Como gerenciar exclusões nas atividades do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
TQID: 'https://experienceleague.adobe.com/ERpNwQPsIRBmU0vTZbGa-lYg30BYl-uJxA8UT0f6060'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 4%
---
# Gerenciar exclusões {#manage-exclusions}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como evitar ofertas duplicadas, excluir experiências específicas e excluir conteúdo padrão em atividades do **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

As exclusões controlam quais ofertas e experiências uma atividade de **[!UICONTROL Automated Personalization]** (AP) serve. Elas impedem que a mesma oferta seja exibida duas vezes, removem combinações de ofertas que não funcionam juntas e removem o conteúdo padrão, para que a atividade forneça experiências mais claras e relevantes que se alinhem às suas metas e público-alvo.

## Permitir ou não ofertas duplicadas {#allow-duplicate-offers}

<a id="concept_4EF78013F80E48EFA024AE0274C9F037"></a>

Evite que as ofertas da biblioteca de ofertas sejam duplicadas quando usadas em locais diferentes nas atividades AP.

Uma atividade pode ter, por exemplo, seis locais em uma página com 12 ofertas, portanto, a mesma oferta pode ser colocada em mais de um local. Não permitir ofertas duplicadas impede que a mesma oferta seja exibida ao mesmo tempo em locais diferentes na mesma atividade.

1. Ao [criar ou editar uma atividade de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), clique no ícone **[!UICONTROL Configurar]** ( ![ícone Configurar](/help/main/assets/icons/Setting.svg) ).

1. Clique em **[!UICONTROL Permitir Ofertas Duplicadas]** para ativar ou desativar esse recurso, dependendo das suas necessidades.

   ![Ícone Configurar](../assets/exclusion-1.png)

## Excluir experiências específicas {#exclude-experiences}

<a id="task_C17D36EF58AF4908B17A3D84CA6DE85A"></a>

Exclua experiências específicas para remover determinadas combinações de ofertas da atividade de AP. Algumas combinações podem não funcionar juntas ou você pode limitar o número de experiências testadas para diminuir os requisitos de tráfego da atividade.

1. Ao [criar ou editar uma atividade de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), clique no ícone **[!UICONTROL Gerenciar conteúdo]** ( ![Ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) ).

   A lista **[!UICONTROL Experiências]** mostra cada experiência gerada com permutas de todas as opções de conteúdo e locais.

1. Exclua as experiências que você não deseja testar.

   * Para excluir uma única experiência, clique no ícone **[!UICONTROL Mais Ações]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) e clique em **[!UICONTROL Excluir]**.
   * Para excluir várias experiências de uma só vez, marque a caixa de seleção de cada experiência e clique em **[!UICONTROL Excluir]**. O ícone **[!UICONTROL Excluir]** é exibido quando uma ou mais experiências são selecionadas.

   ![Exclusão em lote de experiências](/help/main/c-activities/t-automated-personalization/assets/exclude1.png)

   As experiências foram excluídas da atividade e seu **[!UICONTROL Status]** é exibido como **[!UICONTROL Excluídos]**.

## Excluir conteúdo padrão {#exclude-default-content}

<a id="task_DCB4528989DF4C05A3A4729E5891D18F"></a>

Exclua o conteúdo padrão quando não quiser que ele faça parte da atividade de AP, para que um local contenha apenas uma oferta que seja diferente do conteúdo padrão. Essa abordagem também permite alterar a aparência do restante da página para atender às ofertas testadas. Por exemplo, para corresponder à paleta de cores das ofertas, é possível alterar a cor do plano de fundo da página e excluir a cor de plano de fundo padrão.

1. Ao [criar ou editar uma atividade de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md#create-ap-activity), selecione o conteúdo que deseja substituir e clique em **[!UICONTROL Alterar Texto/HTML]**, **[!UICONTROL Alterar Oferta de Imagem]** ou **[!UICONTROL Alterar Cor de Fundo]**. As opções disponíveis variam dependendo do tipo de conteúdo.

   ![Alterar opções](../assets/exclusion-1.png)

1. Crie seu novo conteúdo.

1. Clique no ícone **[!UICONTROL Mais Ações]** ( ![ícone Mais Ações](/help/main/assets/icons/Setting.svg) ) e clique na opção **Excluir Oferta Padrão/Incluir Oferta Padrão** para excluir ou incluir a oferta padrão.

   <!--
   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![Include checkbox in Edit Text/HTML dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   For Image/Video content: 

   ![Include checkbox in Select Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   For background color: 

   ![Include checkbox in Edit Background Color dialog box](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)
   -->

<!--
1. Click **[!UICONTROL Save]**.

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_vec_4 image](assets/exclude_content_vec_4.png)

**To exclude default content using the [!UICONTROL Form-Based Experience Composer]:** 

1. While creating or editing an AP activity, click **[!UICONTROL Change Text/HTML]** or **[!UICONTROL Change Image Offer]** under **[!UICONTROL Content]**. 
1. In the dialog box, create your new content and uncheck **[!UICONTROL Include]** to the right of the default content (or uncheck the Default Image/Video in the [!UICONTROL Select Content] screen). 

   Depending on the content or offer type, the [!UICONTROL Include] checkbox is in a slightly different place. 

   For Text/HTML content: 

   ![exclude_content_form_1 image](assets/exclude_content_form_1.png)

   For Image/Video content: 

   ![exclude_content_form_2 image](assets/exclude_content_form_2.png)

1. Click **[!UICONTROL Save]**. 

   You can see the experiences created from the offers you specified under [!UICONTROL Manage Content]. You notice that no experiences are created in [!UICONTROL Manage Content] using the default offer you excluded. 

   ![exclude_content_form_3 image](assets/exclude_content_form_3.png)
-->
