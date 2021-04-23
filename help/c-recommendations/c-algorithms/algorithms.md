---
keywords: recommendations, atividade do recommendations, critérios, algoritmo, chave de recomendação, chave personalizada, vertical do setor, varejo, comércio eletrônico, geração de clientes em potencial, b2b, serviços financeiros, mídia, publicação
description: Saiba como usar critérios no Adobe [!DNL Target] Recommendations. Critérios são regras que determinam qual conteúdo recomendar com base em um conjunto predeterminado de comportamentos do visitante.
title: Como uso os critérios no  [!DNL Target] Recommendations?
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1086'
ht-degree: 52%

---

# ![Critérios](/help/assets/premium.png) PREMIUM

Critérios em [!DNL Adobe Target] são regras que determinam quais produtos ou conteúdo recomendar com base em um conjunto predeterminado de comportamentos do visitante. Os critérios podem ser baseados em tendências populares, nos comportamentos atuais e passados de um visitante ou em produtos e conteúdo semelhantes. Você pode comparar vários tipos de recomendação por meio da adição de vários critérios.

As seções a seguir explicam mais sobre chaves de critérios e a lógica de recomendação que pode ser usada para cada chave. Clique nos links para obter informações mais detalhadas.

## Vertical do setor {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Ao criar um critério, você seleciona um vertical do setor com base nas metas de sua atividade de recomendações.

| Vertical do setor | Meta |
|--- |--- |
| Varejo/Comércio eletrônico | Conversão resultando em compra |
| Geração de lead/B2B/Serviços financeiros | Conversão sem compra |
| Mídia/Publicação | Envolvimento |

Outras opções de critério mudam de acordo com o negócio vertical que você selecionar. Você pode definir seu negócio vertical padrão na página **[!UICONTROL Recommendations > Configurações]** ou especificar o negócio vertical para cada critério.

## Chave de recomendação {#section_885B3BB1B43048A88A8926F6B76FC482}

A chave de recomendação selecionada determina o tipo de critério. Há vários tipos de critérios, que são representados como cartões de critérios quando você configura uma atividade do [!DNL Recommendations].

![Página Critérios](/help/c-recommendations/c-algorithms/assets/criteria-page.png)

A tabela a seguir explica os vários tipos de critérios e suas chaves acompanhantes. Clique nos links para obter informações mais detalhadas sobre cada chave.

| Tipo de critério | Teclas |
|--- |--- |
| Atividade da Página Atual | Itens recomendados com base no que os usuários fazem na página atual. Por exemplo, os visitantes que visualizam um determinado artigo talvez queiram ver outros artigos da mesma categoria.<ul><li>[Item Atual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[Categoria Atual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| Personalizado | Recomende itens com base em atributos personalizados.<ul><li>[Atributo personalizado ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>Ao basear as recomendações em atributos personalizados, selecione o atributo personalizado e, em seguida, selecione o tipo de recomendação. |
| Comportamento anterior | Itens recomendados com base no modo como os visitantes responderam a um item no passado. Por exemplo, pessoas que compram um item de uma determinada marca têm maior probabilidade de comprar outro item dessa mesma marca.<ul><li>[Último item comprado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[Último item visualizado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[Item Mais Visualizado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[Categoria favorita](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| Popularidade | Recomende os itens mais populares, como os vídeos mais acessados em uma categoria relacionada ou os produtos que foram mais vistos no seu site.<ul><li>[Popularidade](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| [Itens visualizados recentemente ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed) | Itens recomendados que um visitante viu mais recentemente, como os itens que um visitante viu na última vez em que visitou seu site, ou os artigos mais populares do momento. |

## Usar uma chave de recomendação personalizada {#custom-key}

Também é possível basear as recomendações no valor de um atributo de perfil personalizado.

>[!NOTE]
>
>Parâmetros de perfil personalizados podem ser enviados para o Target por meio de JavaScript, API ou integrações. Para obter mais informações sobre atributos de perfil personalizados, consulte [Perfis de visitante](/help/c-target/c-visitor-profile/visitor-profile.md).

Por exemplo, suponha que você deseja exibir filmes recomendados com base no filme adicionado recentemente por um usuário à fila.

1. Selecione o atributo de perfil personalizado na lista suspensa [!UICONTROL Chave de recomendação] (por exemplo, [!UICONTROL Último programa adicionado à Lista de favoritos]).

1. Selecione a [!UICONTROL Lógica de Recomendação] (por exemplo, [!UICONTROL Pessoas que viram isto, viram aquilo]).

   ![Caixa de diálogo Criar novos critérios](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

Se o atributo de perfil personalizado não corresponder diretamente a uma única ID de entidade, é necessário explicar para [!DNL Recommendations] como você deseja que a correspondência seja feita a uma entidade.

Por exemplo, suponha que você deseja exibir os itens mais vendidos da marca favorita de um usuário.

1. Selecione o atributo de perfil personalizado na lista suspensa [!UICONTROL Chave de recomendação] (por exemplo, [!UICONTROL Marca favorita]).

1. Selecione a [!UICONTROL Lógica de Recomendação] que deseja usar com essa chave (por exemplo, [!UICONTROL Mais Vendidos]).

   A opção [!UICONTROL Agrupar por valor exclusivo de] é exibida.

1. Selecione o atributo de entidade que corresponde à chave escolhida. Nesse caso, [!UICONTROL Marca favorita] corresponde a `entity.brand`.

   [!DNL Recommendations] O agora gera uma lista de &quot;Mais vendidos&quot; para cada marca e mostra ao usuário a lista de &quot;Mais vendidos&quot; apropriada com base no valor armazenado no atributo de perfil  [!UICONTROL Marca ] favorita .

   ![Atributo Mais Vendidos](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Critérios/algoritmos {#criteria-algorithms}

O [!DNL Target Recommendations] usa algoritmos sofisticados para determinar quando as ações de um visitante se qualificam para os critérios definidos na sua atividade. A chave de recomendação determina as opções de lógica de recomendação disponíveis.

| Critérios | Descrição |
|--- |--- |
| [Itens/Mídia com atributos semelhantes](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#similar-attributes) | Recomenda itens ou mídias semelhantes a itens ou mídias baseados na atividade da página atual ou no comportamento passado do visitante. |
| [Pessoas que visualizaram isto, visualizaram aquilo](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-viewed) | Recomenda itens visualizados com mais frequência na mesma sessão em que o item especificado é visualizado. |
| [Pessoas que visualizaram isto, compraram aquilo](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#viewed-bought) | Recomenda itens visualizados que são comprados com mais frequência na mesma sessão em que o item especificado é visualizado. |
| [Pessoas que compraram isto, compraram aquilo](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#bought-bought) | Recomenda os itens que são comprados com mais frequência pelos clientes ao mesmo tempo que o item especificado. |
| [Afinidade do site](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#site-affinity) | Recomenda itens com base na certeza de uma relação entre os itens. |
| [Mais vendidos](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#top-sellers) | Os itens incluídos nos pedidos mais concluídos. Várias unidades do mesmo item em um único pedido são contadas como um pedido. |
| [Mais visualizados](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed) | Os itens ou mídias visualizados com mais frequência. |
| [Recommendations baseado em usuário](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | Recomenda itens com base no histórico de navegação, visualização e compra de cada visitante. Geralmente, esses itens são chamados de &quot;Recomendado para você&quot;. |

>[!NOTE]
>
>Se estiver executando uma recomendação e alterar seus critérios, seus dados de relatório serão perdidos.

Você também pode usar informações adicionais conhecidas sobre um visitante para aprimorar suas recomendações.

Todos os critérios de um dia são executados duas vezes ao dia. Todos os critérios de uma semana ou mais são executados uma vez ao dia. Critérios de afinidade do site são executados uma vez ao dia. Critérios de backup são executados duas vezes ao dia.

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
