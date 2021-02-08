---
keywords: recomendações;recomendações atividade;critérios;algoritmo;chave de recomendação;chave personalizada;chave personalizada;vertical do setor;varejo;comércio;geração de chumbo;b2b;serviços financeiros;mídia;publicar;Recomendações;Recomendações;Recomendações ;critérios;algoritmo;chave de recomendação;chave personalizada;chave;indústria vertical;varejo;eccommerce;geração de chumbo;b2b;serviços financeiros;mídia;publicação
description: Saiba como usar critérios na Adobe Target Recommendations. Critérios são regras que determinam qual conteúdo recomendar com base em um conjunto predeterminado de comportamentos de visitante.
title: Como uso critérios no Público alvo Recommendations?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1087'
ht-degree: 52%

---


# ![Critérios](/help/assets/premium.png) PREMIUM

Os critérios em [!DNL Adobe Target] são regras que determinam quais produtos ou conteúdo serão recomendados com base em um conjunto predeterminado de comportamentos de visitante. Os critérios podem ser baseados em tendências populares, nos comportamentos atuais e passados de um visitante ou em produtos e conteúdo semelhantes. Você pode comparar vários tipos de recomendação por meio da adição de vários critérios.

As seções a seguir explicam mais sobre chaves de critérios e a lógica de recomendação que você pode usar para cada chave. Clique nos links para obter informações mais detalhadas.

## Vertical do setor {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Ao criar um critério, você seleciona um vertical do setor com base nas metas de sua atividade de recomendações.

| Vertical do setor | Meta |
|--- |--- |
| Varejo/Comércio eletrônico | Conversão resultando em compra |
| Geração de lead/B2B/Serviços financeiros | Conversão sem compra |
| Mídia/Publicação | Envolvimento |

Outras opções de critérios mudam com base no vertical do setor selecionado. Você pode definir seu setor padrão vertical na página **[!UICONTROL Recommendations > Configurações]** ou especificar o setor vertical para cada critério.

## Chave de recomendação {#section_885B3BB1B43048A88A8926F6B76FC482}

A chave de recomendação selecionada determina o tipo de critério. Há vários tipos de critérios, que são representados como cartões de critérios quando você configura uma atividade do [!DNL Recommendations].

![Página Critérios](/help/c-recommendations/c-algorithms/assets/criteria-page.png)

A tabela a seguir explica os vários tipos de critérios e as chaves que os acompanham. Clique nos links para obter informações mais detalhadas sobre cada chave.

| Tipo de critério | Teclas |
|--- |--- |
| Atividade da Página Atual | Itens recomendados com base no que os usuários fazem na página atual. Por exemplo, os visitantes que visualizam um determinado artigo talvez queiram ver outros artigos da mesma categoria.<ul><li>[Item Atual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-item)</li><li>[Categoria Atual](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#current-category)</li></ul> |
| Personalizado | Recomende itens com base em atributos personalizados.<ul><li>[Atributo personalizado ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#custom)</li></ul>Ao basear as recomendações em atributos personalizados, selecione o atributo personalizado e, em seguida, selecione o tipo de recomendação. |
| Comportamento anterior | Itens recomendados com base no modo como os visitantes responderam a um item no passado. Por exemplo, pessoas que compram um item de uma determinada marca têm maior probabilidade de comprar outro item dessa mesma marca.<ul><li>[Último item comprado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-purchased)</li><li>[Último item visualizado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#last-viewed)</li><li>[Item Mais Visualizado](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#most-viewed-logic)</li><li>[Categoria favorita](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#favorite-category)</li></ul> |
| Popularidade | Recomende os itens mais populares, como os vídeos mais acessados em uma categoria relacionada ou os produtos que foram mais vistos no seu site.<ul><li>[Popularidade](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#popularity)</li></ul> |
| [Itens visualizados recentemente ](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#recently-viewed) | Itens recomendados que um visitante visualizou mais recentemente, como os itens que um visitante visualizou na última vez em que visitou site, ou os artigos que apresentam as tendências mais importantes no momento. |

## Usando uma chave de recomendação personalizada {#custom-key}

Também é possível basear as recomendações no valor de um atributo de perfil personalizado.

>[!NOTE]
>
>Parâmetros de perfil personalizados podem ser passados para o Público alvo por meio de JavaScript, API ou integrações. Para obter mais informações sobre atributos de perfil personalizados, consulte [perfis de Visitante](/help/c-target/c-visitor-profile/visitor-profile.md).

Por exemplo, suponha que você deseja exibir filmes recomendados com base no filme que um usuário adicionou mais recentemente à fila.

1. Selecione seu atributo de perfil personalizado na lista suspensa [!UICONTROL Chave de recomendação] (por exemplo, [!UICONTROL Última exibição adicionada à lista de monitoramento]).

1. Selecione sua [!UICONTROL Lógica de recomendação] (por exemplo, [!UICONTROL Pessoas que viram isso, viram aquilo]).

   ![Caixa de diálogo Criar novo critério](/help/c-recommendations/c-algorithms/assets/custom-key1.png)

Se o atributo de perfil personalizado não corresponder diretamente a uma única ID de entidade, será necessário explicar para [!DNL Recommendations] como você deseja que ocorra a correspondência com uma entidade.

Por exemplo, suponha que você deseja exibir os itens mais vendidos de uma marca favorita do usuário.

1. Selecione seu atributo de perfil personalizado na lista suspensa [!UICONTROL Chave de recomendação] (por exemplo, [!UICONTROL Marca favorita]).

1. Selecione a [!UICONTROL Lógica de Recomendação] que deseja usar com esta chave (por exemplo, [!UICONTROL Mais Vendidos]).

   A opção [!UICONTROL Agrupar por valor exclusivo de] é exibida.

1. Selecione o atributo de entidade que corresponde à chave escolhida. Nesse caso, [!UICONTROL Marca favorita] corresponde a `entity.brand`.

   [!DNL Recommendations] agora produz uma lista &quot;Mais Vendidos&quot; para cada marca e mostra ao usuário a lista &quot;Mais Vendidos&quot; apropriada, com base no valor armazenado no atributo  [!UICONTROL Favorito ] Brandprofile.

   ![Atributo de mais vendidos](/help/c-recommendations/c-algorithms/assets/custom-key2.png)

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
| [Recommendations baseado em usuário](/help/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#user-based) | Recomenda itens com base em cada histórico de navegação, exibição e compra de visitantes. Esses itens são geralmente chamados de &quot;Recomendado para você&quot;. |

>[!NOTE]
>
>Se estiver executando uma recomendação e alterar seus critérios, seus dados de relatório serão perdidos.

Você também pode usar informações adicionais conhecidas sobre um visitante para aprimorar suas recomendações.

Todos os critérios de um dia são executados duas vezes ao dia. Todos os critérios de uma semana ou mais são executados uma vez ao dia. Critérios de afinidade do site são executados uma vez ao dia. Critérios de backup são executados duas vezes ao dia.

## Exibindo informações de critérios {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Você pode exibir os detalhes dos critérios em um cartão pop-up, passando o mouse sobre ele e clicando no ícone Informações, sem precisar abrir os critérios.

![Passar o mouse sobre o cartão de critérios](/help/c-recommendations/c-algorithms/assets/criteria_hover.png)

Clique na guia **[!UICONTROL Informações do algoritmo]** para exibir as informações gerais sobre os critérios selecionados, incluindo Nome, Descrições, Vertical do setor, Tipos de página, Chave de recomendação, Lógica de recomendação e ID do algoritmo.

![Guia Informações do algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_info.png)

Clique na guia **[!UICONTROL Uso do algoritmo]** para exibir uma lista de atividades que fazem referência aos critérios selecionados. As listas de cartão estão ativas, inativas e atividades de rascunho. Clique nas listas suspensas Atividades ativas/Atividades inativas/Atividades de rascunho para visualização toda a lista de atividades que fazem referência a esses critérios. Você pode clicar no link da atividade para abri-la para edição.

![Guia Uso do algoritmo](/help/c-recommendations/c-algorithms/assets/criteria_usage.png)

>[!NOTE]
>
>O recurso [!UICONTROL Uso do algoritmo] é atualmente compatível somente com o Recommendations atividade. No momento, esse recurso não é compatível com atividades de teste A/B, autoalocação, Público alvo automático e direcionamento de experiência (XT) que incluem [recomendações como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md).
