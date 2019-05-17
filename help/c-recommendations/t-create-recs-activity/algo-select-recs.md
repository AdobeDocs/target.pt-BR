---
description: Selecione os critérios a serem usados na atividade do Recommendations.
keywords: recommendations; atividade do Recommendations; critérios
seo-description: Selecione os critérios a serem usados na atividade do Recommendations.
seo-title: Selecione o critério
solution: Target
title: Selecione o critério
title-outputclass: premium
topic: Premium
uuid: 1a1e13e0-7fbd-4f86-80da-cd4e96748d30
badge: premium
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# ![PREMIUM](/help/assets/premium.png) Selecionar critério{#select-criteria}

Selecione os critérios a serem usados na atividade do Recommendations.

Você pode testar vários tipos de recomendação ao incluir mais um critério.

Se você selecionar vários critérios, o tráfego será dividido igualmente entre eles. Por exemplo, se você tiver selecionado dois critérios, e sua atividade for projetada para exibir conteúdo padrão para 20% dos participantes da atividade, então 40% dos participantes da atividade verão as recomendações controladas por cada critério. Não há opções para alterar as porcentagens de cada critério.

* Para pesquisar um critério existente (por exemplo, se forem exibidos muitos cartões de critério), digite no campo de pesquisa até que os critérios desejados sejam exibidos, selecione o critério e clique em **[!UICONTROL Concluído]**.

   Alguns critérios são fornecidos com o [!DNL Recommendations]. Você e sua equipe também podem criar seus próprios critérios personalizados.

* Para criar um novo critério, clique em **[!UICONTROL Criar novo]** e preencha as informações do novo critério. Para obter informações sobre como criar novos critérios, consulte [Criar um novo critério](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE).

1. [Crie uma nova recomendação](../../c-recommendations/t-create-recs-activity/create-recs-activity.md#task_6874328773C64C44A73F0A130AD3F96F) ou encontre a recomendação cujos critérios você deseja definir e clique em **[!UICONTROL Editar]**.
1. Selecione o tipo de setor e página.

* **Tipo de setor:** O tipo de setor é usado para ajudar a categorizar [!DNL Recommendations] critérios. Para alterar o ramo do setor padrão, clique em **[!UICONTROL Configurações]** e selecione a configuração de **Ramo do setor]padrão desejada.[!UICONTROL **
* **Tipo de página:** o tipo de página ajuda a categorizar suas recomendações. Também há critérios incorporados que podem ser escolhidos para cada tipo de página.
* **Compatível:** mostra apenas os critérios pelos quais a página selecionada passa os dados solicitados. Nem todos os critérios serão executados corretamente em cada página. A página e a mbox precisam passar pela `entity.id` ou [!DNL entity.categoryId] para as recomendações do item atual/categoria atual para serem compatíveis. Em geral, é melhor mostrar apenas critérios compatíveis. No entanto, se você desejar que critérios incompatíveis estejam disponíveis para a atividade, desmarque a caixa de seleção **[!UICONTROL Compatível]**. Esta opção pode ser desativada ou ativada nas [!UICONTROL preferências] do [!DNL Target].

1. Clique em **[!UICONTROL Adicionar]**.
