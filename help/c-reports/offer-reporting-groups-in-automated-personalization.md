---
keywords: personalização automatizada;oferta;relatório;grupo;grupo de relatórios;personalização automatizada;oferta;relatório;grupo;grupo de relatórios
description: Informações sobre como usar grupos de relatórios em atividades de Personalização automatizada (AP) no Adobe Target.
title: Ofereça grupos de relatórios em atividades de Personalização automatizada (AP) no Adobe Target
topic: Advanced
uuid: 5b111a68-bd05-4ef1-8156-d064f2c7e257
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) Oferecer grupos de relatório na personalização automatizada{#offer-reporting-groups-in-automated-personalization}

Information about using reporting groups in [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) activities.

Os grupos de relatórios executam duas funções-chave:

* Eles permitem ver suas ofertas agrupadas em relatórios de atividade AP.
* They play a key role with how the [!DNL Target] personalization models function.

When you use reporting groups, [!DNL Target] creates only one personalization model for each reporting group instead of each offer in your AP activity using the data from all offers in that group.

Se a configuração da atividade não tiver dados suficientes para criar um modelo de personalização por oferta, os grupos de relatórios poderão ajudar a reduzir os requisitos de dados para usar a Personalização automatizada. Os grupos de relatórios também podem ajudar a resolver o problema de "inicialização imediata" para novas ofertas, agrupando ofertas semelhantes para que cada modelo receba mais dados para treinar. Os grupos de modelagem também podem ser usados para atividades em que novas ofertas estão sendo introduzidas regularmente na atividade de AP.

Essa abordagem funciona bem se os visitantes responderem da mesma maneira a todas as ofertas de um grupo. A prática recomendada é agrupar as ofertas nas quais grupos semelhantes de visitantes respondem de maneira similar. Ou seja, agrupe ofertas com taxas de conversão semelhantes. Você nunca deve colocar todas as ofertas em um único grupo de relatórios. Grouping all offers or grouping offers with very different conversion rates likely reduces the effectiveness of the [!DNL Target] personalization models.

>[!NOTE]
>
>Se uma oferta for removida ou substituída de um determinado grupo de modelagem, o tráfego antigo que visualizou essa oferta específica também será excluído do grupo de modelagem. In other words, deleted offers do not contribute to what data is used for the [!DNL Target] personalization models to learn.

**Para configurar grupos de relatórios:**

1. On the [!UICONTROL Experiences] page of an AP activity, click the **[!UICONTROL Manage Content]** icon.

   ![](assets/ap_manage_content.png)

1. Clique na guia **[!UICONTROL Ofertas]** na parte superior da caixa de diálogo [!UICONTROL Gerenciar conteúdo].
1. (Condicional) Adicione experiências específicas a um grupo de relatórios, passando o mouse sobre a oferta desejada e clicando no ícone da pasta **[!UICONTROL Grupo de relatórios].**

   ![](assets/ap_manage_content_2.png)

1. (Condicional) Adicione experiências em lote a um grupo de relatórios, marcando a caixa de seleção das experiências relevantes e clicando no ícone da pasta **[!UICONTROL Grupo de relatórios]no canto superior direito da caixa de diálogo.**

   ![](assets/ap_manage_content_3.png)

1. (Conditional) To assign the selected offer to an existing reporting group, select **[!UICONTROL Existing]**, select the desired reporting group from the drop-down list, then click **[!UICONTROL Apply]**.

   Ou

   Para criar um novo grupo de relatórios para atribuir a oferta selecionada, selecione **[!UICONTROL Novo]**, nomeie o novo grupo de relatórios e clique em **[!UICONTROL Aplicar]**.

   ![](assets/ap_reporting_groups.png)

