---
keywords: chave de recomendação;lógica de recomendação;categoria atual;atributo personalizado;último item comprado;último item exibido;item mais exibido;item mais exibido;categoria favorita;popularidade;item exibido recentemente;última compra;última visualização;mais exibido;favorito;exibido recentemente
description: Saiba como usar recomendações com base em chaves que usam o contexto de comportamento do visitante para mostrar resultados relevantes nas atividades do [!UICONTROL Recommendations].
title: Como baseio a [!UICONTROL Recomendação] em uma [!UICONTROL Chave de Recomendação]?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
TQID: 'https://experienceleague.adobe.com/1gI3rMMf9s5ogc4BvBz4fMUqxed1Nqad0XoaR8SlU58'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c4147b6e-073b-4d3c-9ab1-d60f2f4434ef
    internal-label: Behavioral data
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '3740'
ht-degree: 12%
---
# Basear a recomendação em uma chave de recomendação {#base-on-recommendation-key}

>[!BEGINSHADEBOX]

**Nesta página:** saiba mais sobre os tipos de algoritmo, algoritmos e chaves de recomendação disponíveis para basear recomendações em atividades do [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

As recomendações baseadas em algoritmo usam o contexto do comportamento do visitante para mostrar resultados relevantes em [!DNL Adobe Target] [!DNL Recommendations] atividades. Cada tipo de algoritmo oferece seu próprio conjunto de algoritmos. Para obter um resumo dos tipos de algoritmo e seus algoritmos, consulte [Introdução aos Critérios](/help/main/c-recommendations/c-algorithms/algorithms.md#section_885B3BB1B43048A88A8926F6B76FC482).

Cada critério é definido em sua própria guia. O tráfego é dividido uniformemente nos testes de critério: com dois critérios, o tráfego é dividido igualmente entre eles e com dois critérios e dois designs, o tráfego é dividido uniformemente entre as quatro combinações. Uma porcentagem dos visitantes do site também pode ser definida para ver o conteúdo padrão, para comparação. Nesse caso, a porcentagem especificada de visitantes visualiza o conteúdo padrão e o restante é dividido entre os critérios e as combinações de design.

Para obter mais informações sobre como criar critérios e definir seus tipos e algoritmos, consulte [Criar critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Algoritmos diferentes se adaptam a diferentes tipos de páginas. As seções a seguir descrevem cada tipo de algoritmo e seus algoritmos.

## Baseado em carrinho {#cart-based}

O tipo de algoritmo **[!UICONTROL Baseado em carrinho]** recomenda itens com base no conteúdo do carrinho atual do visitante. As chaves de recomendação são fornecidas como valores separados por vírgulas no [parâmetro de mbox `cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=pt-BR){target=_blank}. Somente os primeiros dez valores são considerados.

A lógica de recomendação baseada em carrinho é semelhante ao algoritmo baseado em usuário &quot;**[!UICONTROL Recomendado para você]**&quot; e aos algoritmos baseados em item &quot;**[!UICONTROL Pessoas que Visualizaram Isto, Compraram Aquilo]**&quot; e &quot;**[!UICONTROL Pessoas que Compraram Isto, Compraram Aquilo]**&quot;.

O [!DNL Target] usa técnicas de filtragem colaborativa para determinar semelhanças para cada item no carrinho do visitante e, em seguida, combina as semelhanças comportamentais de todos os itens em uma lista mesclada.

Os profissionais de marketing podem escolher se [!DNL Target] observa o comportamento do visitante em uma única sessão ou em várias sessões:

* **[!UICONTROL Única sessão]**: com base no que outros visitantes fizeram em uma única sessão.

  Uma única sessão se adapta a produtos que &quot;acompanham&quot; uns aos outros com base em uso, ocasião ou evento. Por exemplo, um visitante que está comprando uma impressora também pode precisar de tinta e papel, e um visitante que está comprando manteiga de amendoim também pode precisar de pão e geleia.

* **[!UICONTROL Entre sessões]**: com base no que outros visitantes fizeram em várias sessões.

  Várias sessões se adaptam a produtos que se complementam com base na preferência ou no gosto do visitante. Por exemplo, um visitante que gosta de Star Wars também pode gostar de Indiana Jones, mesmo que o visitante não queira necessariamente assistir a ambos os filmes na mesma sessão. Da mesma forma, um visitante que gosta do jogo de tabuleiro &quot;Codenames&quot; também pode gostar do jogo de tabuleiro &quot;Avalon&quot;, mesmo que o visitante não possa jogar os dois jogos simultaneamente.

[!DNL Target] faz recomendações para cada visitante com base nos itens em seu carrinho atual, independentemente do comportamento do visitante ser considerado em uma única sessão ou em várias sessões.

Os seguintes algoritmos estão disponíveis com o tipo de algoritmo **[!UICONTROL Baseado em carrinho]**:

| Algoritmo | Como funciona | Quando usar | Chaves de recomendação |
| --- | --- | --- | --- |
| **[!UICONTROL Pessoas que os visualizaram, também visualizaram]** | Recomenda itens visualizados com mais frequência na mesma sessão em que o item especificado é visualizado. Retorna outros produtos visualizados pelas pessoas após a visualização deste. O produto especificado não está incluído no conjunto de resultados. | Crie oportunidades de conversão adicionais recomendando itens que outros visitantes que visualizaram um item também visualizaram. Por exemplo, os visitantes que visualizam bicicletas rodoviárias no site também podem ver capacetes de bicicleta, kits de ciclismo, fechaduras e assim por diante, portanto, uma recomendação pode sugerir outros produtos que ajudem a aumentar a receita. | **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]** |
| **[!UICONTROL Pessoas Que Os Visualizaram, Também Compraram]** | Recomenda itens visualizados que são comprados com mais frequência na mesma sessão em que o item especificado é visualizado. Retorna outros produtos comprados pelas pessoas após a visualização deste. O produto especificado não está incluído no conjunto de resultados. | Aumente as oportunidades de venda cruzada exibindo uma recomendação em uma página de produto, por exemplo, que exibe itens que outros visitantes que visualizaram o item compraram. Se o visitante estiver visualizando uma vara de pesca, a recomendação poderá mostrar itens adicionais que outros visitantes compraram, como caixas de engrenagens, pernaltas e iscas de pesca. À medida que os visitantes navegam pelo site, eles recebem recomendações de compra adicionais. | **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]** |
| **[!UICONTROL Pessoas que Compraram Estes, Também Compraram]** | Recomenda os itens que são comprados com mais frequência pelos clientes ao mesmo tempo que o item especificado. Retorna outros produtos comprados pelas pessoas após a compra deste. O produto especificado não está incluído no conjunto de resultados. | Aumente as oportunidades de venda cruzada exibindo uma recomendação em uma página de resumo do carrinho de compras, por exemplo, que exibe itens que outros compradores também compraram. Se o visitante estiver comprando um terno, a recomendação poderá exibir itens adicionais que outros visitantes compraram junto com o terno, como gravatas, sapatos e abotoaduras. À medida que os visitantes revisam suas compras, eles recebem recomendações adicionais. | **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]** |

## [!UICONTROL Com Base Em Popularidade]

O tipo de algoritmo **[!UICONTROL Baseado em Popularidade]** recomenda itens com base em sua popularidade geral no site ou em sua popularidade na categoria, marca, gênero favoritos ou mais visualizados do usuário.

Os seguintes algoritmos estão disponíveis com o tipo de algoritmo **[!UICONTROL Baseado em Popularidade]**:

| Algoritmo | Como funciona | Quando usar | Chaves de recomendação |
| --- | --- | --- | --- |
| **[!UICONTROL Mais visualizados em todo o site]** | A recomendação é determinada pelo item exibido com mais frequência, com base nos critérios de recenticidade/frequência. Consulte [Mais visualizados na pontuação do site](#most-viewed). | Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites. | |
| **[!UICONTROL Mais Visualizados por Categoria]** | A recomendação é determinada pela categoria que recebeu mais atividade, usando o mesmo método que para o item mais exibido, exceto que as categorias são pontuadas em vez de produtos. Consulte [Mais visualizados por pontuação de categoria](#most-viewed-category). | Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites. | **[!UICONTROL Categoria Atual]**, **[!UICONTROL Categoria Favorita]** |
| **[!UICONTROL Mais Visualizados pelo Atributo de Item]** | Recomenda itens ou mídias semelhantes aos itens ou mídias mais visualizados no site. O atributo de item no qual basear a recomendação é selecionado, por exemplo, &quot;Nome&quot; ou &quot;Marca&quot;. Em seguida, os atributos de perfil armazenados no perfil do visitante para correspondência são selecionados, por exemplo, &quot;Marca favorita&quot;, &quot;Último item adicionado ao carrinho&quot; ou &quot;Programa mais visualizado&quot;. | | |
| **[!UICONTROL Mais visualizados por atributo de perfil]** | Recomenda os itens mais visualizados agrupados por um atributo de perfil de visitante, em vez de por informações de item, como **[!UICONTROL Mais visualizados por categoria]** e **[!UICONTROL Mais visualizados por atributo de item]** fazem. [!DNL Target] mantém uma lista classificada separada por valor de atributo e, no momento da entrega, mostra a cada visitante a lista que corresponde a seu próprio valor armazenado. Consulte [Algoritmos de atributo de perfil](#profile-attribute-algorithms). | | |
| **[!UICONTROL Mais vendidos em todo o site]** | Exibe os itens incluídos nas ordens mais concluídas de todo o site. Várias unidades do mesmo item em um único pedido são contadas como um pedido. | Crie recomendações para os itens mais vendidos no site para aumentar a conversão e a receita. Essa lógica é adequada para visitantes novos do site. | |
| **[!UICONTROL Mais vendidos por categoria]** | Exibe os itens incluídos nas ordens mais concluídas por categoria. Várias unidades do mesmo item em um único pedido são contadas como um pedido. | Crie recomendações para os itens mais vendidos no site com base na categoria para aumentar a conversão e a receita. Essa lógica é adequada para visitantes novos do site. | **[!UICONTROL Categoria Atual]**, **[!UICONTROL Categoria Favorita]** |
| **[!UICONTROL Mais vendidos por atributo de item]** | Recomenda itens ou mídias semelhantes aos itens ou mídias mais comprados no site. O atributo de item no qual basear a recomendação é selecionado, por exemplo, &quot;Nome&quot; ou &quot;Marca&quot;. Em seguida, os atributos de perfil armazenados no perfil do visitante para correspondência são selecionados, por exemplo, &quot;Marca favorita&quot;, &quot;Último item adicionado ao carrinho&quot; ou &quot;Programa mais visualizado&quot;. | | |
| **[!UICONTROL Mais vendidos por atributo de perfil]** | Recomenda os itens mais vendidos agrupados por um atributo de perfil de visitante, em vez de por informações de item, como fazem os **[!UICONTROL Mais vendidos por categoria]** e os **[!UICONTROL Mais vendidos por atributo de item]**. [!DNL Target] mantém uma lista de mais vendidos separada por valor de atributo e, no momento da entrega, mostra a cada visitante a lista que corresponde a seu próprio valor armazenado. Consulte [Algoritmos de atributo de perfil](#profile-attribute-algorithms). | | |
| **[!UICONTROL Métrica Top by Analytics]** | Exibe o &quot;X superior&quot;, onde *x* é uma métrica [!DNL Analytics] arbitrária. Ao usar dados comportamentais de mboxes, **[!UICONTROL Mais vendidos]** ou **[!UICONTROL Mais visualizados]** podem ser usados (x = &quot;Vendidos&quot; ou x = &quot;Visualizados&quot;). Ao usar dados comportamentais de [!DNL Adobe Analytics], x = &quot;Adições ao carrinho&quot; ou alguma outra métrica [!DNL Analytics] pode ser usada. | | |

### [!UICONTROL Mais visualizados em todo o site] pontuação {#most-viewed}

A recomendação é o item exibido com mais frequência, determinado pelos critérios de recenticidade/frequência da seguinte maneira:

* 10 pontos para primeira visualização de produto
* 5 pontos para cada visualização seguinte
* No final de uma sessão, divida todos os valores por 2

Por exemplo, visualizar a prancha de surfe A e depois a prancha de surfe B em uma sessão resulta em A: 10, B: 5. Quando a sessão termina, o resultado é A: 5, B: 2.5. Se os mesmos itens forem exibidos na próxima sessão, os valores serão alterados para A: 15, B: 7.5.

### [!UICONTROL Mais visualizados por pontuação de Categoria] {#most-viewed-category}

A recomendação é a categoria que recebeu mais atividade. Ela usa o mesmo método que &quot;item mais exibido&quot;, exceto que as categorias são pontuadas em vez de produtos, com os seguintes critérios de recenticidade/frequência:

* 10 pontos para primeira visualização de categoria
* 5 pontos para cada visualização seguinte

A cada visita, a pontuação de cada categoria não atual que foi visualizada antes é diminuída em 1.

Por exemplo, visualizar a categoria A e depois a categoria B em uma sessão resulta em A: 9, B: 10. Se os mesmos itens forem exibidos na próxima sessão, os valores serão alterados para A: 20, B: 9.

### Algoritmos de atributo de perfil {#profile-attribute-algorithms}

>[!CONTEXTUALHELP]
>id="target_recommendations_profile_attribute"
>title="Atributo de perfil"
>abstract="É possível criar um Atributo de perfil usando Scripts de perfil. Depois que um Script de perfil é criado e ativado, o atributo de Perfil correspondente pode ser usado com esse algoritmo."

**[!UICONTROL Mais Visualizados pelo Atributo de Perfil]** e **[!UICONTROL Mais Vendidos pelo Atributo de Perfil]** dependem de um script de perfil para preencher o atributo. O nome do script deve começar com o prefixo `recsAttribute` para que [!DNL Target] o armazene como `user.recsAttribute<Name>`. Um script pode ser escrito para qualquer característica do visitante que seja relevante para o caso de uso. Para obter mais informações sobre como definir atributos de perfil com scripts de perfil, consulte [Parâmetros de perfil](https://experienceleague.adobe.com/pt-br/docs/target/using/audiences/visitor-profiles/profile-parameters).

Por exemplo, o script a seguir, chamado `recsAttributeRegion`, baseia as recomendações na região do visitante:

```
var region = mbox.param('userRegion');
if (region) return region;
```

Da mesma forma, o script a seguir, chamado `recsAttributeLoyaltyTier`, baseia as recomendações no nível de fidelidade do visitante:

```
var tier = mbox.param('visitorLoyaltyTier');
if (tier) return tier;
```

Depois que o script é criado e ativado, a entrada **[!UICONTROL Region]** ou **[!UICONTROL Camada de Fidelidade]** correspondente fica disponível na lista suspensa de atributos de perfil da janela de criação de critérios. O prefixo `recsAttribute` em si não é mostrado na lista suspensa.

## [!UICONTROL Baseado em Item]

O tipo de algoritmo **[!UICONTROL Baseado em Item]** recomenda itens semelhantes a um item que o usuário está visualizando atualmente ou visualizou recentemente.

Os seguintes algoritmos estão disponíveis com o tipo de algoritmo **[!UICONTROL Baseado em Item]**:

| Algoritmo | Como funciona | Quando usar | Chaves de recomendação |
| --- | --- | --- | --- |
| **[!UICONTROL Pessoas Que Visualizaram Isto, Visualizaram Aquilo]** | Recomenda itens visualizados com mais frequência na mesma sessão em que o item especificado é visualizado. Retorna outros produtos visualizados pelas pessoas após a visualização deste. O produto especificado não está incluído no conjunto de resultados. | Crie oportunidades de conversão adicionais recomendando itens que outros visitantes que visualizaram um item também visualizaram. Por exemplo, os visitantes que visualizam bicicletas rodoviárias no site também podem ver capacetes de bicicleta, kits de ciclismo, fechaduras e assim por diante, portanto, uma recomendação pode sugerir outros produtos que ajudem a aumentar a receita. | **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]** |
| **[!UICONTROL Pessoas que Visualizaram Isto, Compraram Aquilo]** | Recomenda itens visualizados que são comprados com mais frequência na mesma sessão em que o item especificado é visualizado. Retorna outros produtos comprados pelas pessoas após a visualização deste. O produto especificado não está incluído no conjunto de resultados. | Aumente as oportunidades de venda cruzada exibindo uma recomendação em uma página de produto, por exemplo, que exibe itens que outros visitantes que visualizaram o item compraram. Se o visitante estiver visualizando uma vara de pesca, a recomendação poderá mostrar itens adicionais que outros visitantes compraram, como caixas de engrenagens, pernaltas e iscas de pesca. À medida que os visitantes navegam pelo site, eles recebem recomendações de compra adicionais. | **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]** |
| **[!UICONTROL Pessoas que Compraram Isto, Compraram Aquilo]** | Recomenda os itens que são comprados com mais frequência pelos clientes ao mesmo tempo que o item especificado. Retorna outros produtos comprados pelas pessoas após a compra deste. O produto especificado não está incluído no conjunto de resultados. | Aumente as oportunidades de venda cruzada exibindo uma recomendação em uma página de resumo do carrinho de compras, por exemplo, que exibe itens que outros compradores também compraram. Se o visitante estiver comprando um terno, a recomendação poderá exibir itens adicionais que outros visitantes compraram junto com o terno, como gravatas, sapatos e abotoaduras. À medida que os visitantes revisam suas compras, eles recebem recomendações adicionais. | **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]** |
| **[!UICONTROL Itens com Atributos Semelhantes]** | Recomenda itens ou mídias semelhantes a itens ou mídias baseados na atividade da página atual ou no comportamento passado do visitante. Se **[!UICONTROL Itens com Atributos Semelhantes]** ou **[!UICONTROL Mídia com Atributos Semelhantes]** for selecionado, as regras de similaridade de conteúdo poderão ser definidas. Para obter mais informações, consulte [Similaridade de conteúdo](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity). | A similaridade de conteúdo é eficaz para novos itens, que provavelmente não serão exibidos nas recomendações usando **[!UICONTROL Pessoas que Visualizaram Isto]**, **[!UICONTROL Visualizaram Aquilo]** e outra lógica baseada no comportamento anterior. Ele também pode gerar recomendações para novos visitantes, que não têm compras anteriores ou outros dados históricos. | **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]** |

## [!UICONTROL Baseado em Usuário]

O tipo de algoritmo **[!UICONTROL Baseado em Usuário]** recomenda itens com base no comportamento do usuário.

Os seguintes algoritmos estão disponíveis com o tipo de algoritmo **[!UICONTROL Baseado em Usuário]**:

| Algoritmo | Como funciona | Quando usar | Chaves de recomendação |
| --- | --- | --- | --- |
| **[!UICONTROL Itens visualizados recentemente]** | Use o histórico do visitante (abrangendo sessões) para apresentes os últimos *x* itens que o visitante viu, baseado no número de slots no design. Consulte [detalhes de Itens visualizados recentemente](#recently-viewed). | Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites. | |
| **[!UICONTROL Recomendado para você]** | Recomenda itens com base no histórico de navegação, visualização e compra de cada visitante. Exibições e compras são usadas para determinar os itens recomendados. A lista de recomendações é ponderada em relação à atividade mais recente do visitante, é atualizada na sessão e se torna mais personalizada conforme o usuário navega no site. | Forneça conteúdo e experiências personalizadas para visitantes novos e recorrentes. A chave de recomendação especificada (por exemplo, **[!UICONTROL Item atual]**) é usada para aplicar qualquer filtro de regra de inclusão selecionado, por exemplo, para excluir itens que não atendem a determinados critérios (produtos indisponíveis, artigos publicados há mais de 30 dias, filmes com classificação R e assim por diante) ou para limitar os itens incluídos a uma única categoria ou à categoria atual. | Chaves de filtragem: **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]** |

### Detalhes de [!UICONTROL Itens visualizados recentemente] {#recently-viewed}

O algoritmo **[!UICONTROL Itens Visualizados Recentemente]** retorna resultados específicos para um determinado [ambiente](/help/main/administrating-target/hosts.md). Se dois sites pertencerem a ambientes diferentes e um visitante alternar entre os dois sites, cada site exibirá somente itens visualizados recentemente do site em questão. Se dois sites estiverem no mesmo ambiente e um visitante alternar entre eles, ele visualizará os mesmos itens visualizados recentemente em ambos os sites.

O critério **[!UICONTROL Itens visualizados recentemente]** não pode ser usado para recomendações de backup.

**[!UICONTROL Itens visualizados recentemente]** ou **[!UICONTROL Mídia visualizada recentemente]** podem ser filtrados para que somente itens com um determinado atributo sejam exibidos.

* **[!UICONTROL Os critérios de]** visualizados recentemente podem ser configurados, assim como os outros critérios em recomendações.
* [Coleções](/help/main/c-recommendations/c-products/collections.md), [exclusões](/help/main/c-recommendations/c-products/exclusions.md) e [inclusões](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) podem ser usadas da mesma forma que com qualquer outro critério.

Um caso de uso é uma empresa multinacional com várias empresas, em que um visitante pode visualizar itens em várias propriedades digitais. Os itens visualizados recentemente podem ser limitados à propriedade em que foram visualizados, para que não sejam exibidos no site de outra propriedade.

>[!NOTE]
>
>**[!UICONTROL Itens visualizados recentemente]** respeita as configurações globais de exclusões e a configuração de coleção selecionada para a atividade. Se um item for excluído por uma exclusão global ou não fizer parte da coleção selecionada, ele não será exibido. Portanto, ao usar o critério **[!UICONTROL Itens visualizados recentemente]**, a configuração &quot;Todas as coleções&quot; geralmente deve ser usada.

## Critérios personalizados {#custom}

O tipo de algoritmo **[!UICONTROL Critério personalizado]** recomenda itens com base em um arquivo personalizado carregado.

A recomendação é determinada por um item armazenado no perfil do visitante, usando os atributos user.*x* ou profile.*x*. Quando esta opção é selecionada, o valor `entity.id` deve estar presente no atributo do perfil. Quando as recomendações se baseiam em atributos personalizados, o atributo personalizado deve ser selecionado primeiro e, em seguida, o tipo de recomendação.

A filtragem em tempo real pode ser aplicada à saída dos critérios personalizados. Por exemplo, os itens recomendados podem ser limitados aos da categoria ou marca favorita de um visitante. Isso combina cálculos offline com filtragem em tempo real, de modo que o [!DNL Target] pode adicionar personalização às recomendações calculadas offline ou listas com preparo personalizado. A ciência de dados e a pesquisa da organização são então combinadas com o delivery, a filtragem em tempo de execução, os testes A/B, o direcionamento, os relatórios e as integrações do Adobe.

As regras de inclusão em **[!UICONTROL Critérios personalizados]** transformam recomendações estáticas em recomendações dinâmicas com base nos interesses do visitante.

* Os critérios personalizados agora podem ser configurados, assim como outros critérios nas recomendações.
* [Coleções](/help/main/c-recommendations/c-products/collections.md), [exclusões](/help/main/c-recommendations/c-products/exclusions.md) e [inclusões](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) podem ser usadas da mesma forma que com qualquer outro critério.

Os possíveis casos de uso incluem:

* Recomendar filmes de uma lista personalizada, mas somente se o visitante ainda não os assistiu.
* Execute um algoritmo offline e use os resultados para alimentar as recomendações, garantindo que os itens indisponíveis nunca sejam recomendados.
* Inclua somente itens que sejam da categoria favorita deste visitante.

## Chaves de recomendação {#keys}

As seguintes chaves de recomendação estão disponíveis na lista suspensa **[!UICONTROL Chave de recomendação]**:

| Chave | Como é determinado | O que passar | Usar em | Não usar em | Algoritmos |
| --- | --- | --- | --- | --- | --- |
| **[!UICONTROL Item atual]** | O item que o visitante está visualizando no momento. As recomendações exibem outros itens que possam interessar o visitante que está interessado no item especificado. | O valor `entity.id` deve ser passado como parâmetro na mbox de exibição. | Páginas de item único, como páginas de produtos. | Páginas de resultados de pesquisa nulas. | **[!UICONTROL Itens com Atributos Semelhantes]**, **[!UICONTROL Pessoas que Visualizaram Isto, Visualizaram Aquilo]**, **[!UICONTROL Pessoas Que Visualizaram Isto, Compraram Aquilo]**, **[!UICONTROL Pessoas Que Compraram Isto, Compraram Aquilo]** |
| **[!UICONTROL Último item comprado]** | O último item que foi comprado por cada visitante único. | Nada. Isso é capturado automaticamente. | Página inicial, página minha conta, anúncios em outros sites. | Páginas de produto ou páginas relevantes para compras. | **[!UICONTROL Itens com Atributos Semelhantes]**, **[!UICONTROL Pessoas que Visualizaram Isto, Visualizaram Aquilo]**, **[!UICONTROL Pessoas Que Visualizaram Isto, Compraram Aquilo]**, **[!UICONTROL Pessoas Que Compraram Isto, Compraram Aquilo]** |
| **[!UICONTROL Último item visualizado]** | O último item que foi visualizado por cada visitante único. | Nada. Isso é capturado automaticamente. | Página inicial, página minha conta, anúncios em outros sites. | Páginas de produto ou páginas relevantes para compras. | **[!UICONTROL Itens com Atributos Semelhantes]**, **[!UICONTROL Pessoas que Visualizaram Isto, Visualizaram Aquilo]**, **[!UICONTROL Pessoas Que Visualizaram Isto, Compraram Aquilo]**, **[!UICONTROL Pessoas Que Compraram Isto, Compraram Aquilo]** |
| **[!UICONTROL Item mais visualizado]** | Os itens ou mídias exibidos com mais frequência no site. Essa lógica exibe recomendações com base nos itens mais visualizados para aumentar as conversões de outros itens. Por exemplo, um site de mídia pode exibir recomendações em sua página inicial para os vídeos mais visualizados, incentivando os visitantes a assistir a vídeos adicionais. | | | | **[!UICONTROL Itens com Atributos Semelhantes]**, **[!UICONTROL Pessoas que Visualizaram Isto, Visualizaram Aquilo]**, **[!UICONTROL Pessoas Que Visualizaram Isto, Compraram Aquilo]**, **[!UICONTROL Pessoas Que Compraram Isto, Compraram Aquilo]** |
| **[!UICONTROL Categoria Atual]** | A categoria do produto que o visitante está visualizando no momento. As recomendações exibem itens na categoria de produto especificada. | O valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição. | Páginas de categoria única. | Páginas de resultados de pesquisa nulas. | **[!UICONTROL Mais vendidos]**, **[!UICONTROL Mais visualizados]** |
| **[!UICONTROL Categoria Favorita]** | A categoria de produto favorita do visitante. As recomendações exibem itens na categoria de produto especificada. | O valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição. | Páginas de categoria única. | Páginas de resultados de pesquisa nulas. | **[!UICONTROL Mais vendidos]**, **[!UICONTROL Mais visualizados]** |

### Chave de recomendação personalizada

As recomendações podem ser baseadas no valor de um atributo de perfil personalizado. Por exemplo, os filmes recomendados podem ser exibidos com base no filme que um visitante adicionou mais recentemente à fila.

1. Selecione o atributo de perfil personalizado na lista suspensa **[!UICONTROL Chave de recomendação]** (por exemplo, &quot;**[!UICONTROL Último programa adicionado à Lista de favoritos]**&quot;).

1. Selecione a **[!UICONTROL Lógica de recomendação]** (por exemplo, &quot;**[!UICONTROL Pessoas que assistiram isto, assistiram aquilo]**&quot;).

Se o atributo de perfil personalizado não corresponder diretamente a uma única ID de entidade, especifique como [!DNL Recommendations] corresponde a uma entidade. Por exemplo, para exibir os itens mais vendidos da marca favorita de um visitante:

1. Selecione o atributo de perfil personalizado na lista suspensa **[!UICONTROL Chave de recomendação]** (por exemplo, &quot;Marca favorita&quot;).

1. Selecione a **[!UICONTROL Lógica de Recomendação]** para usar com esta chave (por exemplo, &quot;**[!UICONTROL Mais vendidos]**&quot;).

   A opção **[!UICONTROL Agrupar por Valor Exclusivo de]** é exibida.

1. Selecione o atributo de entidade que corresponde à chave escolhida. Neste caso, &quot;**[!UICONTROL Marca favorita]**&quot; corresponde a `entity.brand`.

   [!DNL Recommendations] agora gera uma lista de &quot;**[!UICONTROL Mais vendidos]**&quot; para cada marca e mostra para o visitante a lista de &quot;**[!UICONTROL Mais vendidos]**&quot; apropriada com base no valor armazenado no atributo de perfil **[!UICONTROL Marca favorita]** do visitante.

### [!UICONTROL Afinidade do Site] {#site-affinity}

Recomenda itens com base na certeza de uma relação entre os itens. Este critério pode ser configurado para definir quantos dados são necessários antes que uma recomendação seja exibida, usando o controle deslizante **[!UICONTROL Regras de inclusão]**. Por exemplo, quando a opção muito forte é selecionada, os produtos com maior certeza de correspondência são recomendados.

Por exemplo, se uma afinidade muito forte estiver definida e o design incluir cinco itens, três dos quais alcançam o limite de força de conexão, os dois itens que não alcançarem os requisitos mínimos de força não serão exibidos nas recomendações e serão substituídos pelos itens de backup definidos. Os itens com a maior afinidade são exibidos primeiro.

Como outro exemplo, um retailer online pode recomendar itens em visitas subsequentes nas quais um visitante tenha mostrado interesse durante sessões anteriores. A atividade para cada sessão de visitante é capturada para calcular uma afinidade com base em um modelo de recenticidade e frequência. À medida que o visitante retorna ao site, a afinidade do site é usada para exibir recomendações com base em ações anteriores no site.

Uma afinidade fraca do site pode fornecer os melhores resultados para clientes com coleções de produtos e comportamentos de site diversos.

Esta lógica pode ser usada com as seguintes chaves de recomendação: **[!UICONTROL Item Atual]**, **[!UICONTROL Último Item Comprado]**, **[!UICONTROL Último Item Visualizado]**, **[!UICONTROL Item Mais Visualizado]**.
