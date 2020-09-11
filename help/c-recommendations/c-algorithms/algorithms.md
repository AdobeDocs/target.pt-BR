---
keywords: recommendations;recommendations activity;criteria;algorithm;recommendation key;custom key;industry vertical;retail;eccommerce;lead generation;b2b;financial services;media;publishing
description: Critérios no Adobe Target Recommendations são regras que determinam quais produtos recomendar com base em um conjunto predeterminado de comportamentos de visitante.
title: Critérios no Adobe Target Recommendations
feature: criteria
uuid: 738db164-174b-45b8-bb8a-778f6494f1d7
translation-type: tm+mt
source-git-commit: 55f0791bb68fc98e319fa70a647e5168ac72ae1e
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 69%

---


# ![Critérios](/help/assets/premium.png) PREMIUM

Critérios são regras que determinam quais produtos recomendar com base em um conjunto predeterminado de comportamentos do visitante.

Os critérios determinam qual ação resultará em qual recomendação. Você pode comparar vários tipos de recomendação por meio da adição de vários critérios.

## Vertical do setor {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Você seleciona um vertical do setor com base nos objetivos da atividade do Recommendations. Dependendo do vertical do setor selecionado,

| Vertical do setor | Meta |
|--- |--- |
| Varejo/Comércio eletrônico | Conversão resultando em compra |
| Geração de lead/B2B/Serviços financeiros | Conversão sem compra |
| Mídia/Publicação | Envolvimento |

## Recommendation key {#section_885B3BB1B43048A88A8926F6B76FC482}

A chave de recomendação selecionada determina o tipo de critério. Há vários tipos de critérios, que são representados como cartões de critérios quando você configura uma atividade do [!DNL Recommendations].

| Tipo de critério | Teclas |
|--- |--- |
| Atividade da Página Atual | Itens recomendados com base no que os usuários fazem na página atual. Por exemplo, os visitantes que visualizam um determinado artigo talvez queiram ver outros artigos da mesma categoria.<ul><li>[Item Atual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[Categoria Atual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| Personalizado | Recomende itens com base em atributos personalizados.<ul><li>[Atributo personalizado ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>Ao basear as recomendações em atributos personalizados, selecione o atributo personalizado e, em seguida, selecione o tipo de recomendação. |
| Comportamento anterior | Itens recomendados com base no modo como os visitantes responderam a um item no passado. Por exemplo, pessoas que compram um item de uma determinada marca têm maior probabilidade de comprar outro item dessa mesma marca.<ul><li>[Último item comprado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[Último item visualizado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[Item Mais Visualizado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[Categoria favorita](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| Popularidade | Recomende os itens mais populares, como os vídeos mais acessados em uma categoria relacionada ou os produtos que foram mais vistos no seu site.<ul><li>[Popularidade](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| Itens visualizados recentemente | Recomende os itens que um visitante viu mais recentemente, como os itens que o visitante viu na última vez em que visitou seu site, ou os artigos mais populares do momento.<br>O algoritmo de Itens visualizados recentemente retorna resultados específicos para a atividade de um visitante em um [ambiente](/help/administrating-target/hosts.md). Se dois sites pertencerem a ambientes diferentes e um visitante alternar entre eles, o algoritmo retornará apenas os itens visualizados recentemente do site apropriado.<br>Esse tipo de critério não é limitado por coleções.<ul><li>[Itens visualizados recentemente ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed)</li></ul>**Observação:** você não pode usar os critérios de Itens visualizados recentemente para recomendações de backup.<br>Os itens/mídias visualizados recentemente agora podem ser filtrados para que somente os itens com um determinado atributo sejam exibidos.<ul><li>Os critérios visualizados recentemente são configuráveis, exatamente como os outros critérios nas recomendações.</li><li>Você pode utilizar [coleções](/help/c-recommendations/c-products/collections.md), [exclusões](/help/c-recommendations/c-products/exclusions.md) e [inclusões](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) da mesma forma que os outros critérios.</li></ul>Os possíveis casos de uso incluem:<ul><li>Uma empresa multinacional com diversas empresas pode ter itens de exibição de visitantes em várias propriedades digitais. Nesse caso, é possível limitar os itens exibidos recentemente somente àqueles da respectiva propriedade em que foram visualizados. Isso impede que os itens visualizados recentemente sejam exibidos no site de outra propriedade digital.</li></ul> |

## Uso de uma chave de recomendação personalizada {#custom-key}

Também é possível basear as recomendações no valor de um atributo de perfil personalizado.

>[!NOTE]
>
>Parâmetros de perfil personalizados podem ser passados para o Público alvo por meio de JavaScript, API ou integrações. Para obter mais informações sobre atributos de perfil personalizados, consulte perfis [de](/help/c-target/c-visitor-profile/visitor-profile.md)Visitante.

Por exemplo, suponha que você deseja exibir filmes recomendados com base no filme que um usuário adicionou mais recentemente à fila.

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Last Show Added to Watchlist]).

1. Select your [!UICONTROL Recommendation Logic] (for example, [!UICONTROL People Who Viewed This, Viewed That]).

   ![Caixa de diálogo Criar novo critério](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

If your custom profile attribute does not directly match to a single entity ID, it is necessary to explain to [!DNL Recommendations] how you want the match to an entity to occur.

Por exemplo, suponha que você deseja exibir os itens mais vendidos de uma marca favorita do usuário.

1. Select your custom profile attribute from the [!UICONTROL Recommendation Key] drop-down list (for example, [!UICONTROL Favorite Brand]).

1. Select the [!UICONTROL Recommendation Logic] you want to use with this key (for example, [!UICONTROL Top Sellers]).

   A opção [!UICONTROL Agrupar por valor exclusivo de] é exibida.

1. Selecione o atributo de entidade que corresponde à chave escolhida. In this case [!UICONTROL Favorite Brand] matches to `entity.brand`.

   [!DNL Recommendations] agora produz uma lista &quot;Mais vendidos&quot; para cada marca e mostra ao usuário a lista &quot;Mais vendidos&quot; apropriada, com base no valor armazenado no atributo de perfil da Marca  Favorita.

   ![Atributo de mais vendidos](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

## Criteria/algorithms {#criteria-algorithms}

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
| [Recommendations baseado em usuário](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | Recomenda itens com base em cada histórico de navegação, exibição e compra de visitantes. Esses itens são geralmente chamados de &quot;Recomendado para você&quot;. |

>[!NOTE]
>
>Se estiver executando uma recomendação e alterar seus critérios, seus dados de relatório serão perdidos.

Você também pode usar informações adicionais conhecidas sobre um visitante para aprimorar suas recomendações.

Todos os critérios de um dia são executados duas vezes ao dia. Todos os critérios de uma semana ou mais são executados uma vez ao dia. Critérios de afinidade do site são executados uma vez ao dia. Critérios de backup são executados duas vezes ao dia.

## Viewing criteria information {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Você pode exibir os detalhes dos critérios em um cartão pop-up, passando o mouse sobre ele e clicando no ícone Informações, sem precisar abrir os critérios.

![Passar o mouse sobre o cartão de critérios](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Clique na guia **[!UICONTROL Informações do algoritmo]** para exibir as informações gerais sobre os critérios selecionados, incluindo Nome, Descrições, Vertical do setor, Tipos de página, Chave de recomendação, Lógica de recomendação e ID do algoritmo.

![Guia Informações do algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Clique na guia **[!UICONTROL Uso do algoritmo]** para exibir uma lista de atividades que fazem referência aos critérios selecionados. As listas de cartão estão ativas, inativas e atividades de rascunho. Clique nas listas suspensas Atividades ativas/Atividades inativas/Atividades de rascunho para visualização toda a lista de atividades que fazem referência a esses critérios. Você pode clicar no link da atividade para abri-la para edição.

![Guia Uso do algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>O recurso de Uso [!UICONTROL de] algoritmo é atualmente compatível somente com o Recommendations atividade. No momento, esse recurso não é compatível com atividades de teste A/B, autoalocação, Público alvo automático e direcionamento de experiência (XT) que incluem [recomendações como oferta](/help/c-recommendations/recommendations-as-an-offer.md).
