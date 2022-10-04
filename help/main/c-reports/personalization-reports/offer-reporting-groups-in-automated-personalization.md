---
keywords: personalização automatizada, oferta, relatórios, grupo, grupo de relatórios
description: Saiba como usar grupos de relatórios de ofertas no Adobe [!DNL Target] Atividades do Automated Personalization . Uso de grupos de relatórios, [!DNL Target] cria apenas um modelo de personalização para cada grupo de relatórios.
title: Posso usar Grupos de relatórios de oferta nas atividades do Automated Personalization?
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: d90e541588f51e16dd9b11ead1ece77e9ca1408b
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 62%

---

# ![PREMIUM](/help/main/assets/premium.png) Oferecer grupos de relatório na personalização automatizada

Informações sobre o uso de grupos de relatórios em [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Os grupos de relatórios executam duas funções-chave:

* Eles permitem ver suas ofertas agrupadas em relatórios de atividade AP.
* Eles desempenham um papel fundamental em como a função [!DNL Target] função de modelos de personalização.

Ao usar grupos de relatórios, [!DNL Target] O cria somente um modelo de personalização para cada grupo de relatórios, em vez de cada oferta na atividade de AP, usando os dados de todas as ofertas desse grupo.

Se a configuração da atividade não tiver dados suficientes para criar um modelo de personalização por oferta, os grupos de relatórios poderão ajudar a reduzir os requisitos de dados para usar a Personalização automatizada. Os grupos de relatórios também podem ajudar a resolver o problema de &quot;inicialização imediata&quot; para novas ofertas, agrupando ofertas semelhantes para que cada modelo receba mais dados para treinar. Os grupos de modelagem também podem ser usados para atividades em que novas ofertas estão sendo introduzidas regularmente na atividade de AP.

Essa abordagem funciona bem se os visitantes responderem da mesma maneira a todas as ofertas de um grupo. A prática recomendada é agrupar as ofertas nas quais grupos semelhantes de visitantes respondem de maneira similar. Ou seja, agrupe ofertas com taxas de conversão semelhantes. Você nunca deve colocar todas as ofertas em um único grupo de relatórios. O agrupamento de todas as ofertas ou o agrupamento de ofertas com taxas de conversão muito diferentes provavelmente reduz a eficácia do [!DNL Target] modelos de personalização.

>[!NOTE]
>
>Se uma oferta for removida ou substituída de um determinado grupo de modelagem, o tráfego antigo que visualizou essa oferta específica também será excluído do grupo de modelagem. Em outras palavras, ofertas excluídas não contribuem para quais dados são usados para a variável [!DNL Target] modelos de personalização para aprender.

**Para configurar grupos de relatórios:**

1. No [!UICONTROL Experiências] de uma atividade de AP, clique no botão **[!UICONTROL Gerenciar conteúdo]** ícone .

   ![](/help/main/c-reports/assets/ap_manage_content.png)

1. Clique na guia **[!UICONTROL Ofertas]** na parte superior da caixa de diálogo [!UICONTROL Gerenciar conteúdo].
1. (Condicional) Adicione experiências específicas a um grupo de relatórios, passando o mouse sobre a oferta desejada e clicando no ícone da pasta **[!UICONTROL Grupo de relatórios]**.

   ![](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Condicional) Adicione experiências em lote a um grupo de relatórios, marcando a caixa de seleção das experiências relevantes e clicando no ícone da pasta **[!UICONTROL Grupo de relatórios]** no canto superior direito da caixa de diálogo.

   ![](/help/main/c-reports/assets/ap_manage_content_3.png)

1. (Condicional) Para atribuir a oferta selecionada a um grupo de relatórios existente, selecione **[!UICONTROL Existente]**, selecione o grupo de relatórios desejado na lista suspensa e clique em **[!UICONTROL Aplicar]**.

   Ou

   Para criar um novo grupo de relatórios para atribuir a oferta selecionada, selecione **[!UICONTROL Novo]**, nomeie o novo grupo de relatórios e clique em **[!UICONTROL Aplicar]**.

   ![](/help/main/c-reports/assets/ap_reporting_groups.png)
