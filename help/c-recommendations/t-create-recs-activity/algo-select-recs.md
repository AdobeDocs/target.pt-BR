---
keywords: recommendations; atividade do recommendations; critérios; algoritmo
description: Saiba como selecionar os critérios (regras que determinam quais produtos ou conteúdo recomendar) a serem usados na atividade do Adobe [!DNL Target] Recommendations.
title: Como seleciono critérios para uma atividade do Recommendations?
feature: Recommendations
exl-id: 119227ec-88c3-4de9-b2cf-f7d5fa2e98f6
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 74%

---

# ![PREMIUM](/help/assets/premium.png) Selecionar critério

Selecione os [critérios](/help/c-recommendations/c-algorithms/algorithms.md) a serem usados na atividade do [!DNL Adobe Target Recommendations] Critérios são regras que determinam quais produtos recomendar com base em um conjunto predeterminado de comportamentos do visitante.

Você pode testar vários tipos de recomendação ao incluir mais um critério.

Se você selecionar vários critérios, o tráfego será dividido igualmente entre eles. Por exemplo, se você tiver selecionado dois critérios, e sua atividade for projetada para exibir conteúdo padrão para 20% dos participantes da atividade, então 40% dos participantes da atividade verão as recomendações controladas por cada critério. Não há opções para alterar as porcentagens de cada critério.

* Para pesquisar um critério existente (por exemplo, se forem exibidos muitos cartões de critério), digite no campo de pesquisa até que os critérios desejados sejam exibidos, selecione o critério e clique em **[!UICONTROL Concluído]**.

   Alguns critérios são fornecidos com o [!DNL Recommendations]. Você e sua equipe também podem criar seus próprios critérios personalizados.

* Para criar um novo critério, clique em **[!UICONTROL Criar critério]** > **[!UICONTROL Criar critério]**, em seguida, preencha as informações para o novo critério. Para obter informações sobre como criar novos critérios, consulte [Criar um novo critério](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Para selecionar o critério:**

1. Ao [criar uma nova recomendação](/help/c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), na caixa de diálogo **[!UICONTROL Selecionar critério]**, localize e selecione um ou mais critérios.

   ![Caixa de diálogo Selecionar critérios](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   É possível usar o filtro [!UICONTROL Tipo de setor], o filtro [!UICONTROL Tipo de página] e a caixa de seleção [!UICONTROL Compatível] para filtrar a lista de critérios. Essas opções ajudam a localizar os critérios desejados.

   * **Tipo de setor:** o tipo de setor é usado para ajudar a classificar os critérios de [!DNL Recommendations]. Para alterar o ramo do setor padrão, clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Configurações]** e selecione a configuração padrão desejada **[!UICONTROL Vertical do setor]**.
   * **Tipo de página:** o tipo de página ajuda a categorizar suas recomendações. Também há critérios incorporados que podem ser escolhidos para cada tipo de página.
   * **Compatível:** mostra apenas os critérios pelos quais a página selecionada passa os dados solicitados. Nem todos os critérios serão executados corretamente em cada página. A página e a mbox precisam passar pela `entity.id` ou `entity.categoryId` para as recomendações do item atual/categoria atual para serem compatíveis. Em geral, é melhor mostrar apenas critérios compatíveis. No entanto, se você desejar que critérios incompatíveis estejam disponíveis para a atividade, desmarque a caixa de seleção **[!UICONTROL Compatível]**. Essa opção pode ser desativada ou ativada nas configurações: **[!UICONTROL Recommendations]** > **[!UICONTROL Definições]**.

1. Clique em **[!UICONTROL Avançar]** para exibir a caixa de diálogo [Selecionar design](/help/c-recommendations/c-design-overview/design-overview.md).
