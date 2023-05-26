---
keywords: recomendações;atividade de recomendações;critérios;algoritmo;recommendations;recommendations activity;criteria;algorithm
description: Saiba como selecionar os critérios (regras que determinam quais produtos ou conteúdo recomendar) para usar em seu Adobe [!DNL Target] Atividade do Recommendations.
title: Como selecionar critérios para uma atividade do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 74%

---

# Selecione o critério

Selecione os [critérios](/help/main/c-recommendations/c-algorithms/algorithms.md) a serem usados na atividade do [!DNL Adobe Target Recommendations] Critérios são regras que determinam quais produtos recomendar com base em um conjunto predeterminado de comportamentos do visitante.

Você pode testar vários tipos de recomendação ao incluir mais um critério.

Se você selecionar vários critérios, o tráfego será dividido igualmente entre eles. Por exemplo, se você tiver selecionado dois critérios, e sua atividade for projetada para exibir conteúdo padrão para 20% dos participantes da atividade, então 40% dos participantes da atividade verão as recomendações controladas por cada critério. Não há opções para alterar as porcentagens de cada critério.

* Para pesquisar um critério existente (por exemplo, se forem exibidos muitos cartões de critério), digite no campo de pesquisa até que os critérios desejados sejam exibidos, selecione o critério e clique em **[!UICONTROL Concluído]**.

   Alguns critérios são fornecidos com o [!DNL Recommendations]. Você e sua equipe também podem criar seus próprios critérios personalizados.

* Para criar um novo critério, clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**, em seguida, preencha as informações para o novo critério. Para obter informações sobre como criar novos critérios, consulte [Criar um novo critério](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Para selecionar o critério:**

1. Enquanto [criação de uma nova recomendação](/help/main/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), no **[!UICONTROL Selecionar critério]** localize e selecione um ou mais critérios.

   ![Caixa de diálogo Selecionar critérios](/help/main/c-recommendations/t-create-recs-activity/assets/filters.png)

   É possível usar o filtro [!UICONTROL Tipo de setor], o filtro [!UICONTROL Tipo de página] e a caixa de seleção [!UICONTROL Compatível] para filtrar a lista de critérios. Essas opções ajudam a localizar os critérios desejados.

   * **Tipo de setor:** o tipo de setor é usado para ajudar a classificar os critérios de [!DNL Recommendations]. Para alterar o negócio vertical padrão, clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Configurações]** e selecione o padrão desejado **[!UICONTROL Vertical do setor]** configuração.
   * **Tipo de página:** o tipo de página ajuda a categorizar suas recomendações. Também há critérios incorporados que podem ser escolhidos para cada tipo de página.
   * **Compatível:** mostra apenas os critérios pelos quais a página selecionada passa os dados solicitados. Nem todos os critérios serão executados corretamente em cada página. A página e a mbox precisam passar pela `entity.id` ou `entity.categoryId` para as recomendações do item atual/categoria atual para serem compatíveis. Em geral, é melhor mostrar apenas critérios compatíveis. No entanto, se você desejar que critérios incompatíveis estejam disponíveis para a atividade, desmarque a caixa de seleção **[!UICONTROL Compatível]**. Esta opção pode ser desativada ou ativada nas configurações: **[!UICONTROL Recommendations]** > **[!UICONTROL Configurações]**.

1. Clique em **[!UICONTROL Avançar]** para exibir a caixa de diálogo [Selecionar design](/help/main/c-recommendations/c-design-overview/design-overview.md).
