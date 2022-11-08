---
keywords: personalização automatizada, oferta, relatórios, grupo, grupo de relatórios, ap
description: Saiba como usar grupos de relatórios de ofertas no Adobe [!DNL Target] [!UICONTROL Automated Personalization] atividades.
title: Posso usar Grupos de relatórios de oferta nas atividades do Automated Personalization?
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: 3a11b368838adb4a6b4f99249db260da8f3f423b
workflow-type: tm+mt
source-wordcount: '698'
ht-degree: 38%

---

# ![PREMIUM](/help/main/assets/premium.png)[!UICONTROL  Oferecer grupos de relatório na personalização automatizada]

Informações sobre o uso de grupos de relatórios em [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP).

Os grupos de relatórios executam duas funções-chave:

* Os grupos de relatórios permitem que você veja suas ofertas agrupadas em relatórios de atividade de AP.
* Os grupos de relatórios desempenham um papel fundamental com a forma como o [!DNL Target] função de modelos de personalização.

Ao usar grupos de relatórios, [!DNL Target] O cria um modelo de personalização para cada grupo de relatórios usando os dados de todas as ofertas desse grupo. Sem grupos de relatórios, [!DNL Target] O cria um modelo de personalização para cada oferta na atividade de AP.

Se a configuração da atividade não tiver dados suficientes para criar um modelo de personalização por oferta, os grupos de relatórios poderão ajudar a reduzir os requisitos de dados a serem usados [!UICONTROL Automated Personalization]. Os grupos de relatórios também podem ajudar a resolver o problema de &quot;inicialização imediata&quot; para novas ofertas, agrupando ofertas semelhantes para que cada modelo receba mais dados para treinar. Os grupos de modelagem também podem ser usados para atividades em que novas ofertas são introduzidas regularmente na atividade de AP.

Essa abordagem funciona bem se os visitantes responderem da mesma maneira a todas as ofertas de um grupo. A prática recomendada é agrupar as ofertas nas quais grupos semelhantes de visitantes respondem de maneira similar. Ou seja, agrupe ofertas com taxas de conversão semelhantes. Você nunca deve colocar todas as ofertas em um único grupo de relatórios. O agrupamento de todas as ofertas ou o agrupamento de ofertas com diferentes taxas de conversão provavelmente reduz a eficácia do [!DNL Target] modelos de personalização.

>[!NOTE]
>
>Se uma oferta for removida ou substituída de um determinado grupo de modelagem, o tráfego antigo que visualizou essa oferta específica também será excluído do grupo de modelagem. Em outras palavras, ofertas excluídas não contribuem para quais dados são usados para a variável [!DNL Target] modelos de personalização para aprender.

## Configurar grupos de relatórios

1. No **[!UICONTROL Experiências]** de uma atividade de AP, clique no botão **[!UICONTROL Gerenciar conteúdo]** ícone .

   ![Ícone Gerenciar conteúdo](/help/main/c-reports/assets/ap_manage_content.png)

1. Clique na guia **[!UICONTROL Ofertas]** na parte superior da caixa de diálogo [!UICONTROL Gerenciar conteúdo].
1. (Condicional) Adicione experiências específicas a um grupo de relatórios, passando o mouse sobre a oferta desejada e clicando no ícone da pasta **[!UICONTROL Grupo de relatórios]**.

   ![Ícone do Grupo de relatórios](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Condicional) Adicione experiências em lote a um grupo de relatórios, marcando a caixa de seleção das experiências relevantes e clicando no botão **[!UICONTROL Grupo de relatórios]** ícone de pasta no canto superior direito da caixa de diálogo.

   ![Ícone do Grupo de relatórios](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Para atribuir a oferta selecionada a um grupo de relatórios existente, selecione **[!UICONTROL Existente]**, em seguida, o grupo de relatórios desejado na lista suspensa e clique em **[!UICONTROL Aplicar]**.

   Ou

   Para criar um grupo de relatórios para atribuir a oferta selecionada, selecione **[!UICONTROL Novo]**, nomeie o novo grupo de relatórios e clique em **[!UICONTROL Aplicar]**.

   ![Novo ícone para criar um novo grupo de relatórios](/help/main/c-reports/assets/ap_reporting_groups.png)

Você pode usar o [!UICONTROL Localização] lista para filtrar ofertas por localização. Use a lista [!UICONTROL Grupos de relatórios] para filtrar ofertas a grupos de relatórios. Você também pode usar a lista [!UICONTROL Grupo de relatórios] para filtrar [!UICONTROL Ofertas não atribuídas], de modo que possa atribuir um grupo de relatórios a uma oferta que não está atualmente atribuída a qualquer grupo de relatórios.

Para obter informações sobre como segmentar uma oferta para públicos específicos, consulte  [Ofertas do Target AP](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Avisos

* É importante entender que os grupos de relatórios afetam o como [!DNL Target] O constrói seus modelos. Como resultado, [!DNL Adobe] A recomenda usar os grupos de relatórios somente se você planeja substituir ou adicionar novas ofertas enquanto uma atividade está ativa. Se uma nova oferta for introduzida em uma atividade ativa, colocá-la em um grupo com ofertas semelhantes existentes permitirá que a máquina use os dados já coletados para as outras ofertas em seu grupo para saber mais sobre a nova oferta. Você nunca deve colocar todas as ofertas em um único grupo de relatórios.

## Exibir ofertas em um grupo de relatórios

1. Clique em **[!UICONTROL Atividades]**, clique no [!UICONTROL Automated Personalization] na lista, em seguida, clique no botão **[!UICONTROL Relatórios]** para exibir a variável [Nível da oferta](/help/main/c-reports/personalization-reports/reports-ap.md) relatório.

   Se você tiver muitas atividades, pode filtrar a lista ao selecionar [!UICONTROL Personalização automatizada] na lista suspensa [!UICONTROL Tipo].

1. Clique em **[!UICONTROL Controle]** ou **[!UICONTROL Direcionado]** na tabela para exibir as ofertas desagrupadas e as ofertas dentro dos grupos de relatórios.

   ![Grupos de ofertas: Controle e direcionado](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Para obter informações sobre como usar [!UICONTROL Automated Personalization] relatórios (incluindo o [!UICONTROL Nível da oferta] relatório), consulte [Relatórios de resumo do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).


