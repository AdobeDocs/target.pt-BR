---
keywords: personalização automatizada;oferta;relatórios;grupo;grupo de relatórios;automated personalization;offer;reporting;group;reporting group;ap
description: Saiba como usar grupos de relatórios de ofertas no [!DNL Adobe Target] [!UICONTROL Automated Personalization] atividades.
title: Posso usar o Offer Reporting Groups no [!UICONTROL Automated Personalization] Atividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: 9058a6c5-c651-480f-9b23-d0782a13b042
source-git-commit: b5f06878a6ca8b4c571bfe05a52bfb3f471a697e
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 26%

---

# Oferecer grupos de relatório em [!UICONTROL Automated Personalization]

Informações sobre o uso de grupos de relatórios no [!DNL Adobe Target] [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) atividades.

Os grupos de relatórios executam duas funções-chave:

* Os grupos de relatórios permitem que você veja suas ofertas agrupadas nos relatórios de atividades de AP.
* Os grupos de relatórios desempenham um papel [!DNL Target] função de modelos de personalização.

Quando você usa grupos de relatórios, [!DNL Target] O cria um modelo de personalização para cada grupo de relatórios usando os dados de todas as ofertas desse grupo. Sem grupos relatores, [!DNL Target] O cria um modelo de personalização para cada oferta na atividade de AP.

Se a configuração da atividade não tiver dados suficientes para criar um modelo de personalização por oferta, os grupos de relatórios ajudarão a reduzir os requisitos de dados a serem usados [!UICONTROL Automated Personalization]. Os grupos de relatórios também podem ajudar a resolver o problema de &quot;inicialização imediata&quot; para novas ofertas, agrupando ofertas semelhantes para que cada modelo receba mais dados para treinar. Os grupos de modelagem também podem ser usados para atividades em que novas ofertas são introduzidas regularmente na atividade de AP.

Essa abordagem funciona bem se os visitantes responderem da mesma maneira a todas as ofertas de um grupo. A prática recomendada é agrupar as ofertas nas quais grupos semelhantes de visitantes respondem de maneira similar. Ou seja, agrupe ofertas com taxas de conversão semelhantes. Você nunca deve colocar todas as ofertas em um único grupo de relatórios. Agrupar todas as ofertas ou agrupar ofertas com taxas de conversão diferentes provavelmente reduz a eficácia da [!DNL Target] modelos de personalização.

>[!NOTE]
>
>Se uma oferta for removida ou substituída de um determinado grupo de modelagem, o tráfego antigo que visualizou essa oferta específica também será excluído do grupo de modelagem. Em outras palavras, as ofertas excluídas não contribuem para quais dados são usados para o [!DNL Target] modelos de personalização para aprender.

## Configurar grupos de relatórios

1. No **[!UICONTROL Experiências]** de uma atividade de AP, clique no link **[!UICONTROL Gerenciar conteúdo]** ícone.

   ![Ícone Gerenciar conteúdo](/help/main/c-reports/assets/ap_manage_content.png)

1. Clique na guia **[!UICONTROL Ofertas]** na parte superior da caixa de diálogo [!UICONTROL Gerenciar conteúdo].
1. (Condicional) Adicione experiências específicas a um grupo de relatórios, passando o mouse sobre a oferta desejada e clicando no ícone da pasta **[!UICONTROL Grupo de relatórios]**.

   ![Ícone do Grupo de relatórios](/help/main/c-reports/assets/ap_manage_content_2.png)

1. (Condicional) Adicione experiências em lote a um grupo de relatórios, marcando as caixas de seleção das experiências relevantes e clicando no ícone **[!UICONTROL Grupo de relatório]** ícone de pasta no canto superior direito da caixa de diálogo.

   ![Ícone do Grupo de relatórios](/help/main/c-reports/assets/ap_manage_content_3.png)

1. Para atribuir a oferta selecionada a um grupo de relatórios existente, selecione **[!UICONTROL Existente]**, em seguida, o grupo de relatórios desejado na lista suspensa e clique em **[!UICONTROL Aplicar]**.

   Ou

   Para criar um grupo de relatórios para atribuir a oferta selecionada, selecione **[!UICONTROL Novo]**, nomeie o novo grupo de relatórios e clique em **[!UICONTROL Aplicar]**.

   ![Novo ícone para criar um novo grupo de relatórios](/help/main/c-reports/assets/ap_reporting_groups.png)

Você pode usar o [!UICONTROL Localização] lista para filtrar ofertas por local. Use a lista [!UICONTROL Grupos de relatórios] para filtrar ofertas a grupos de relatórios. Você também pode usar a lista [!UICONTROL Grupo de relatórios] para filtrar [!UICONTROL Ofertas não atribuídas], de modo que possa atribuir um grupo de relatórios a uma oferta que não está atualmente atribuída a qualquer grupo de relatórios.

Para obter informações sobre como direcionar uma oferta para públicos específicos, consulte [Target [!UICONTROL Automated Personalization] ofertas](/help/main/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

## Avisos

* É importante entender que os grupos de relatórios afetam como [!DNL Target] O cria seus modelos. Como resultado, [!DNL Adobe] A recomenda que você use grupos de relatórios somente se planejar substituir ou adicionar novas ofertas enquanto uma atividade estiver ativa. Se uma nova oferta for introduzida em uma atividade ativa, colocar a nova oferta em um grupo com ofertas semelhantes existentes permitirá que a máquina use os dados já coletados para as outras ofertas em seu grupo para saber mais sobre a nova oferta. Você nunca deve colocar todas as ofertas em um único grupo de relatórios.

* As atividades de AP têm combinações de localização+oferta (rótulos de modelo). Quando [!DNL Target] registra dados em relatórios, [!DNL Target] O considera essas combinações para que fique claro de qual evento (exibição, clique e assim por diante) a oferta veio.

  Por exemplo, uma atividade pode ter vários locais e várias ofertas, que podem se sobrepor. Se um visitante visualizar mais de uma dessas ofertas em locais diferentes, [!DNL Target] O registra dados somente para essas ofertas. Se o mesmo visitante clicar em uma oferta posteriormente, [!DNL Target] registra um evento somente dessa combinação (não de todas as combinações).

  Da mesma forma, se o clique vem de um local diferente, que está presente em uma métrica, mas não exibe uma oferta, esse evento será registrado na atividade, mas não para nenhuma combinação de oferta+local. Como resultado, essa oferta não aparece no grupo de relatórios de oferta.

  Esse comportamento ocorre porque o clique pode ser feito de uma mbox diferente, e não da mbox que serviu a oferta. Por esse motivo, a métrica é associada à atividade, mas não à oferta.

## Exibir ofertas em um grupo de relatórios

1. Clique em **[!UICONTROL Atividades]**, clique no link desejado [!UICONTROL Automated Personalization] atividade na lista, em seguida, clique no botão **[!UICONTROL Relatórios]** para exibir a [Nível da oferta](/help/main/c-reports/personalization-reports/reports-ap.md) relatório.

   Se você tiver muitas atividades, clique no link [!UICONTROL Mostrar filtros] (funil) e selecione a variável [!UICONTROL Automated Personalization] caixa de seleção para filtrar a lista para exibir somente [!UICONTROL Automated Personalization] atividades.

1. Clique em **[!UICONTROL Controle]** ou **[!UICONTROL Direcionado]** na tabela para exibir as ofertas não agrupadas e as ofertas dentro dos grupos de relatórios.

   ![Grupos de ofertas: controle e direcionado](/help/main/c-reports/c-report-settings/assets/offer-groups.png)

Para obter informações sobre o uso de [!UICONTROL Automated Personalization] relatórios (incluindo o [!UICONTROL Nível da oferta] relatório), consulte [Relatórios de resumo do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).


