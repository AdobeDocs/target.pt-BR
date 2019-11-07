---
keywords: recommendations; atividade do Recommendations; critérios
description: Selecione os critérios a serem usados na atividade do Adobe Target Recommendations.
title: Selecione o critério
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# ![PREMIUM](/help/assets/premium.png) Selecionar critério{#select-criteria}

Selecione os [critérios](/help/c-recommendations/c-algorithms/algorithms.md) a serem usados na atividade do Recommendations. Critérios são regras que determinam quais produtos recomendar com base em um conjunto predeterminado de comportamentos do visitante.

Você pode testar vários tipos de recomendação ao incluir mais um critério.

Se você selecionar vários critérios, o tráfego será dividido igualmente entre eles. Por exemplo, se você tiver selecionado dois critérios, e sua atividade for projetada para exibir conteúdo padrão para 20% dos participantes da atividade, então 40% dos participantes da atividade verão as recomendações controladas por cada critério. Não há opções para alterar as porcentagens de cada critério.

* Para pesquisar um critério existente (por exemplo, se forem exibidos muitos cartões de critério), digite no campo de pesquisa até que os critérios desejados sejam exibidos, selecione o critério e clique em **[!UICONTROL Concluído]**.

   Alguns critérios são fornecidos com o [!DNL Recommendations]. Você e sua equipe também podem criar seus próprios critérios personalizados.

* Para criar um novo critério, clique em **[!UICONTROL Criar critério]** e preencha as informações do novo critério. Para obter informações sobre como criar novos critérios, consulte [Criar um novo critério](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

**Para selecionar o critério:**

1. Ao [criar uma nova recomendação](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F), na caixa de diálogo **[!UICONTROL Critérios]**, localize e selecione um ou mais critérios.

   ![Caixa de diálogo Selecionar critérios](/help/c-recommendations/t-create-recs-activity/assets/filters.png)

   É possível usar o filtro [!UICONTROL Tipo de setor], o filtro [!UICONTROL Tipo de página] e a caixa de seleção [!UICONTROL Compatível] para filtrar a lista de critérios. Essas opções ajudam a localizar os critérios desejados.

   * **Tipo de setor:** o tipo de setor é usado para ajudar a classificar os critérios de [!DNL Recommendations]. Para alterar o ramo do setor padrão, clique em **[!UICONTROL Configurações]** e selecione a configuração de **[!UICONTROL Ramo do setor]** padrão desejada.
   * **Tipo de página:** o tipo de página ajuda a categorizar suas recomendações. Também há critérios incorporados que podem ser escolhidos para cada tipo de página.
   * **Compatível:** mostra apenas os critérios pelos quais a página selecionada passa os dados solicitados. Nem todos os critérios serão executados corretamente em cada página. A página e a mbox precisam passar pela `entity.id` ou `entity.categoryId` para as recomendações do item atual/categoria atual para serem compatíveis. Em geral, é melhor mostrar apenas critérios compatíveis. No entanto, se você desejar que critérios incompatíveis estejam disponíveis para a atividade, desmarque a caixa de seleção **[!UICONTROL Compatível]**. Esta opção pode ser desativada ou ativada nas [!DNL Target] [!UICONTROL Preferências].

1. Clique em **[!UICONTROL Avançar]** para exibir a caixa de diálogo [Selecionar design](/help/c-recommendations/c-design-overview/design-overview.md).
