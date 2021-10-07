---
keywords: recommendations, atividade do recommendations, critérios, algoritmo, chave de recomendação, chave personalizada, vertical do setor, varejo, comércio eletrônico, geração de clientes em potencial, b2b, serviços financeiros, mídia, publicação
description: Saiba como usar critérios em Adobe [!DNL Target] [!DNL Recommendations].
title: Como uso os critérios no  [!DNL Target] Recommendations?
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
source-git-commit: 7a52f7c046fb00672ef1b13704308be39f89c7ad
workflow-type: tm+mt
source-wordcount: '700'
ht-degree: 24%

---

# ![Critérios](/help/assets/premium.png) PREMIUM

Critérios em [!DNL Adobe Target] [!DNL Recommendations] são regras que determinam quais produtos ou conteúdo recomendar com base em um conjunto predeterminado de comportamentos do visitante. Os critérios podem ser baseados em tendências populares, nos comportamentos atuais e passados de um visitante ou em produtos e conteúdo semelhantes. Você pode comparar vários tipos de recomendação por meio da adição de vários critérios.

As seções a seguir explicam mais sobre chaves de critérios e a lógica de recomendação que pode ser usada para cada chave. Clique nos links para obter informações mais detalhadas.

## Vertical do setor {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Ao criar um critério, você seleciona um vertical do setor com base nas metas de sua atividade de recomendações.

| Vertical do setor | Meta |
|--- |--- |
| Varejo/Comércio eletrônico | Conversão resultando em compra |
| Geração de lead/B2B/Serviços financeiros | Conversão sem compra |
| Mídia/Publicação | Envolvimento |

Outras opções de critério mudam de acordo com o negócio vertical que você selecionar. Você pode definir seu negócio vertical padrão na página **[!UICONTROL Recommendations > Configurações]** ou especificar o negócio vertical para cada critério.

## Tipo de algoritmo {#section_885B3BB1B43048A88A8926F6B76FC482}

O tipo de algoritmo selecionado determina os algoritmos disponíveis. Há vários tipos de algoritmos, que são representados como cartões de critérios quando você configura uma atividade [!DNL Recommendations].

![Página Critérios](assets/criteria-page.png)

A tabela a seguir explica os vários tipos de algoritmos e seus algoritmos associados.

| Tipo de algoritmo | Quando usar | Algoritmos disponíveis |
| --- | --- | --- |
| [!UICONTROL Baseado em popularidade] | Faça recomendações com base na popularidade geral de um item em seu site ou na popularidade dos itens em uma categoria favorita ou mais exibida do usuário, marca, gênero e assim por diante. | <ul><li>Mais visualizados no site</li><li>Mais visualizados por categoria</li><li>Mais visualizados por atributo de item</li><li>Mais vendidos no site</li><li>Mais vendidos por categoria</li><li>Principais Vendedores por Atributo de Item</li><li>Principais por métrica do Analytics</li></ul> |
| [!UICONTROL Baseado em item] | Faça recomendações baseadas em encontrar itens semelhantes a um item que o usuário está visualizando ou visualizou recentemente. | <ul><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Pessoas que visualizaram isto, compraram aquilo</li><li>Pessoas que compraram isto, compraram aquilo</li><li>Itens com atributos similares</li></ul> |
| [!UICONTROL Baseado em usuário] | Faça recomendações com base no comportamento do usuário. | <ul><li>Itens visualizados recentemente </li><li>Recomendado para você</li></ul> |
| Baseado em carrinho | (Em breve) Faça recomendações com base no conteúdo do carrinho do usuário. | <ul><li>Pessoas que visualizaram estes, visualizaram aqueles</li><li>Pessoas que visualizaram estes, compraram aqueles</li><li>Pessoas que compraram isto, compraram aqueles</li></ul> |
| [!UICONTROL Critérios personalizados] | Faça recomendações com base em um arquivo personalizado que você fez upload. | <ul><li>Algoritmo personalizado</li></ul> |

Para obter mais informações sobre cada algoritmo, consulte [Basear a recomendação em uma chave de recomendação](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Usar uma chave de recomendação personalizada {#custom-key}

Também é possível basear as recomendações no valor de um atributo de perfil personalizado.

>[!NOTE]
>
>Parâmetros de perfil personalizados podem ser passados para [!DNL Target] por meio de JavaScript, API ou integrações. Para obter mais informações sobre atributos de perfil personalizados, consulte [Perfis de visitante](/help/c-target/c-visitor-profile/visitor-profile.md).

Por exemplo, suponha que você deseja exibir filmes recomendados com base no filme adicionado recentemente por um usuário à fila.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**.

1. Preencha as informações na seção [Informações básicas](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Na seção [Algoritmo Recomendado](/help/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo), selecione **[!UICONTROL Baseado em Item]** na lista **[!UICONTROL Tipo de Algoritmo]**.

1. Selecione **[!UICONTROL Pessoas que viram isto, viram aquilo]** na lista **[!UICONTROL Algoritmo]**.

1. Selecione o atributo de perfil personalizado na lista **[!UICONTROL Chave de recomendação]** (por exemplo, [!UICONTROL Último programa adicionado à Lista de favoritos]).

   ![Caixa de diálogo Criar novos critérios](assets/custom-key1.png)

## Exibição de informações de critérios {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Você pode exibir os detalhes dos critérios em um cartão pop-up, passando o mouse sobre ele e clicando no ícone Informações, sem precisar abrir os critérios.

![Passar o mouse sobre o cartão de critérios](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Clique na guia **[!UICONTROL Informações do algoritmo]** para exibir as informações gerais sobre os critérios selecionados, incluindo Nome, Descrições, Vertical do setor, Tipos de página, Chave de recomendação, Lógica de recomendação e ID do algoritmo.

![Guia Informações do algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Clique na guia **[!UICONTROL Uso do algoritmo]** para exibir uma lista de atividades que fazem referência aos critérios selecionados. O cartão lista atividades ativas, inativas e de rascunho. Clique nas listas suspensas Atividades ao vivo/Atividades inativas/Atividades de rascunho para exibir toda a lista de atividades que fazem referência a esse critério. Você pode clicar no link da atividade para abri-la para edição.

![Guia Uso de algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>O recurso [!UICONTROL Uso do algoritmo] é atualmente compatível somente para atividades do Recommendations. No momento, esse recurso não é compatível com atividades de Teste A/B, Alocação automática, Direcionamento automático e Direcionamento de experiência (XT) que incluem [recomendações como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md).
