---
description: Informações sobre o uso de grupos de relatórios em atividades de Automated Personalization (AP).
keywords: personalização automatizada, oferta, relatórios, grupo
seo-description: Informações sobre o uso de grupos de relatórios em atividades de Automated Personalization (AP).
seo-title: Oferecer Grupos de relatório na Automated Personalization
solution: Target
title: Oferecer Grupos de relatório na Automated Personalization
title-outputclass: premium
topic: Advanced
uuid: 5b111a68-bd05-4ef1-8156-d064f2c7e257
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Oferecer grupos de relatório na personalização automatizada{#offer-reporting-groups-in-automated-personalization}

Informações sobre o uso de grupos de relatórios em atividades de Automated Personalization (AP).

Os grupos de relatórios executam duas funções-chave:

* Eles permitem ver suas ofertas agrupadas em relatórios de atividade AP.
* Eles desempenham um papel importante na forma como os modelos de personalização do Target funcionam.

Ao usar os grupos de relatórios, o Target cria apenas um modelo de personalização para cada grupo de relatórios, em vez de cada oferta na atividade de AP, usando os dados de todas as ofertas desse grupo.

Se a configuração da atividade não tiver dados suficientes para criar um modelo de personalização por oferta, os grupos de relatórios poderão ajudar a reduzir os requisitos de dados para usar a Personalização automatizada. Os grupos de relatórios também podem ajudar a resolver o problema de &quot;inicialização imediata&quot; para novas ofertas, agrupando ofertas semelhantes para que cada modelo receba mais dados para treinar. Os grupos de modelagem também podem ser usados para atividades em que novas ofertas estão sendo introduzidas regularmente na atividade de AP.

Essa abordagem funciona bem se os visitantes responderem da mesma maneira a todas as ofertas de um grupo. A prática recomendada é agrupar as ofertas nas quais grupos semelhantes de visitantes respondem de maneira similar. Ou seja, agrupe ofertas com taxas de conversão semelhantes. Você nunca deve colocar todas as ofertas em um único grupo de relatórios. O agrupamento de todas as ofertas ou daquelas com taxas de conversão muito diferentes provavelmente reduz a eficácia dos modelos de personalização do Target.

>[!NOTE]
>
>Se uma oferta for removida ou substituída de um determinado grupo de modelagem, o tráfego antigo que visualizou essa oferta específica também será excluído do grupo de modelagem. Ou seja, as ofertas excluídas não contribuem para qual tipo de dados é usado nos modelos de personalização do Target para ser aprendido.

**Para configurar grupos de relatórios:**

1. Na página Experiências de uma atividade de AP, clique no ícone **[!UICONTROL Gerenciar conteúdo].**

   ![](assets/ap_manage_content.png)

1. Clique na guia **[!UICONTROL Ofertas]** na parte superior da caixa de diálogo [!UICONTROL Gerenciar conteúdo].
1. (Condicional) Adicione experiências específicas a um grupo de relatórios, passando o mouse sobre a oferta desejada e clicando no ícone da pasta **[!UICONTROL Grupo de relatórios].**

   ![](assets/ap_manage_content_2.png)

1. (Condicional) Adicione experiências em lote a um grupo de relatórios, marcando a caixa de seleção das experiências relevantes e clicando no ícone da pasta **[!UICONTROL Grupo de relatórios]no canto superior direito da caixa de diálogo.**

   ![](assets/ap_reporting_groups.png)

1. Para atribuir a oferta selecionada a um grupo de relatórios existente, selecione **[!UICONTROL Existente]**, em seguida, o grupo de relatórios desejado na lista suspensa e clique em **[!UICONTROL Aplicar]**.

   Ou

   Para criar um novo grupo de relatórios para atribuir a oferta selecionada, selecione **[!UICONTROL Novo]**, nomeie o novo grupo de relatórios e clique em **[!UICONTROL Aplicar]**.

   ![](assets/ap_manage_content_3.png)

