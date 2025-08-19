---
keywords: chave de recomendação;lógica de recomendação;categoria atual;atributo personalizado;último item comprado;último item exibido;item mais exibido;item mais exibido;categoria favorita;popularidade;item exibido recentemente;última compra;última visualização;mais exibido;favorito;exibido recentemente
description: Saiba como usar recomendações com base em chaves que usam o contexto de comportamento do visitante para mostrar resultados relevantes nas atividades do Adobe [!DNL Target] Recommendations.
title: Como baseio a recomendação em uma Chave de recomendação?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '3845'
ht-degree: 33%

---

# Basear a recomendação em uma chave de recomendação

As recomendações baseadas em algoritmos usam o contexto de comportamento do visitante para mostrar resultados relevantes em [!DNL Adobe Target] [!DNL Recommendations] atividades.

Cada tipo de algoritmo fornece algoritmos diferentes apropriados para seu tipo, conforme mostrado na tabela a seguir:

| Tipo de algoritmo | Quando usar | Algoritmos disponíveis |
| --- | --- | --- |
| [!UICONTROL Cart-Based] | Faça recomendações com base no conteúdo do carrinho do usuário. | <ul><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Pessoas que visualizaram e compraram essas</li><li>Pessoas que compraram isto, compraram aquilo</li></ul> |
| [!UICONTROL Popularity-Based] | Faça recomendações com base na popularidade geral de um item em todo o site ou na popularidade de itens na categoria, marca, gênero e assim por diante favoritas ou mais visualizadas de um usuário. | <ul><li>Mais visualizados no site</li><li>Mais visualizados por categoria</li><li>Mais visualizados pelo atributo de item</li><li>Mais vendidos em todo o site</li><li>Mais vendidos por categoria</li><li>Mais Vendidos por Atributo de Item</li><li>Comece pela métrica do Analytics</li></ul> |
| [!UICONTROL Item-Based] | Fazer recomendações com base na localização de itens semelhantes a um item que o usuário está visualizando atualmente ou que visualizou recentemente. | <ul><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Pessoas que visualizaram isto, compraram aquilo</li><li>Pessoas que compraram isto, compraram aquilo</li><li>Itens com atributos similares</li></ul> |
| [!UICONTROL User-Based] | Faça recomendações com base no comportamento do usuário. | <ul><li>Itens visualizados recentemente </li><li>Recomendado para você</li></ul> |
| [!UICONTROL Custom Criteria] | Faça recomendações com base em um arquivo personalizado que você fez upload. | <ul><li>Algoritmo personalizado</li></ul> |

Cada critério é definido em sua própria guia. O tráfego é dividido uniformemente entre os diferentes testes de critérios. Em outras palavras, se você tem dois critérios, o tráfego é dividido igualmente entre eles. Se você tem dois critérios e dois designs, o tráfego é dividido igualmente entre as quatro combinações. Também é possível especificar uma porcentagem de visitantes do site que veem o conteúdo padrão, para comparação. Nesse caso, a porcentagem especificada de visitantes visualiza o conteúdo padrão e o restante é dividido entre seus critérios e combinações de design.

Para obter mais informações sobre como criar critérios e definir seus tipos e algoritmos, consulte [Criar critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md).

Diferentes algoritmos de recomendações se prestam ao posicionamento em diferentes tipos de páginas. Consulte as seções a seguir para obter mais informações sobre cada tipo de algoritmo e seus algoritmos disponíveis.

## Baseado em carrinho {#cart-based}

O tipo de algoritmo [!UICONTROL Cart-Based] permite recomendar itens com base no conteúdo do carrinho atual do visitante. As chaves de recomendação são fornecidas por meio do [parâmetro de mbox `cartIds`](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} em valores separados por vírgulas. Somente os primeiros dez valores são considerados.

A lógica de recomendação baseada em carrinho é semelhante ao algoritmo baseado em usuário &quot;[!UICONTROL Recommended For You]&quot; e aos algoritmos baseados em item &quot;[!UICONTROL People Who Viewed These, Bought Those]&quot; e &quot;[!UICONTROL People Who Bought These, Bought Those]&quot;.

O [!DNL Target] usa técnicas de filtragem colaborativa para determinar semelhanças para cada item no carrinho do visitante, em seguida, combina essas semelhanças comportamentais em cada item para obter uma lista mesclada.

[!DNL Target] também oferece aos profissionais de marketing a opção de observar o comportamento do visitante em uma única sessão ou em várias sessões:

* **[!UICONTROL Single Session]**: com base no que outros visitantes fizeram em uma única sessão.

  Observar o comportamento em uma única sessão pode fazer sentido quando há uma sensação de que os produtos &quot;acompanham&quot; um ao outro com base em um uso, ocasião ou evento. Por exemplo, um visitante está comprando uma impressora e também pode precisar de tinta e papel. Ou um visitante está comprando manteiga de amendoim e também pode precisar de pão e geleia.

* **[!UICONTROL Across Sessions]**: com base no que outros visitantes fizeram em várias sessões.

  Observar o comportamento em várias sessões pode fazer sentido quando há uma sensação de que os produtos &quot;acompanham&quot; um ao outro com base na preferência ou no gosto do visitante. Por exemplo, um visitante gosta de Star Wars e também pode gostar de Indiana Jones, mesmo que o visitante não queira necessariamente assistir a ambos os filmes na mesma sessão. Ou, um visitante gosta do jogo de tabuleiro &quot;Codenames&quot; e também pode gostar do jogo de tabuleiro &quot;Avalon&quot;, mesmo que o visitante não possa jogar ambos os jogos simultaneamente. 

O [!DNL Target] faz recomendações para cada visitante com base nos itens em seu carrinho atual, independentemente de você observar o comportamento do visitante em uma única sessão ou em várias sessões.

Os seguintes algoritmos estão disponíveis com o tipo de algoritmo [!UICONTROL Cart-Based]:

### [!UICONTROL People Who Viewed This, Viewed Those]

Recomenda itens visualizados com mais frequência na mesma sessão em que o item especificado é visualizado.

Essa lógica retorna outros produtos que as pessoas visualizaram após verem esse produto; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite criar oportunidades de conversão adicionais, recomendando itens que outros visitantes que visualizaram um item também visualizaram. Por exemplo, os visitantes que visualizam bicicletas rodoviárias em seu site também podem ver capacetes de bicicleta, kits de ciclismo, fechaduras e assim por diante. Você pode criar uma recomendação usando essa lógica que sugere que outros produtos ajudam a aumentar a receita.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que visualizaram isto, compraram aqueles

Recomenda itens visualizados que são comprados com mais frequência na mesma sessão em que o item especificado é visualizado. Este critério retorna outros produtos que pessoas compraram depois de ver este, o produto especificado não é incluído nos resultados.

Essa lógica retorna outros produtos que as pessoas compraram após verem este; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada ao exibir uma recomendação em uma página de produto, por exemplo, que exibe itens que outros visitantes que visualizaram o item compraram. Por exemplo, se o visitante estiver visualizando uma vara de pesca, a recomendação poderá mostrar itens adicionais que outros visitantes compraram, como caixas de engrenagens, pernaltas e iscas de pesca. À medida que os visitantes navegam em seu site, você fornece a eles recomendações de compra adicionais.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que compraram isto, compraram aquilo tudo

Recomenda os itens que são comprados com mais frequência pelos clientes ao mesmo tempo que o item especificado.

Essa lógica retorna outros produtos comprados pelas pessoas após a compra deste; o produto especificado não é incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada ao exibir uma recomendação em uma página de resumo do carrinho de compras, por exemplo, que exibe itens que outros compradores também compraram. Por exemplo, se o visitante estiver comprando um terno, a recomendação poderá exibir itens adicionais que outros visitantes compraram junto com o terno, como gravatas, sapatos e abotoaduras. À medida que os visitantes revisam suas compras, você fornece a eles recomendações adicionais.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

## [!UICONTROL Popularity-Based]

O tipo de algoritmo [!UICONTROL Popularity-Based] permite fazer recomendações com base na popularidade geral de um item no site ou com base na popularidade de itens na categoria, marca, gênero e assim por diante favorita ou mais visualizada de um usuário.

Os seguintes algoritmos estão disponíveis com o tipo de algoritmo [!UICONTROL Popularity-Based]:

### Mais visualizados no site {#most-viewed}

A recomendação é determinada pelo item que foi exibido com mais frequência. Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de produto
* 5 pontos para cada visualização seguinte
* No fim da sessão, divida todos os valores por 2

Por exemplo, visualizar a prancha_de_surfe_A e depois a prancha_de_surfe_B em uma sessão resulta em A: 10, B: 5. Quando a sessão terminar, você terá A: 5, B: 2.5. Se você visualizar os mesmos itens na próxima sessão, os valores serão alterados para A: 15 B: 7.5.

Use esse algoritmo em páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

### Mais visualizados por categoria {#most-viewed-category}

A recomendação é determinada pela categoria que recebeu a mais atividade, utilizando o mesmo método usado para &quot;item mais visto&quot;, exceto que as categorias são classificadas, em vez de os produtos.

Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de categoria
* 5 pontos para cada visualização seguinte

Categorias visitadas pela primeira vez recebem 10 pontos. 5 pontos são dados para visitas seguintes para a mesma categoria. Com cada visita, categorias não atuais que foram vistas anteriormente são diminuídas em 1.

Por exemplo, a visualização da categoria A e da categoria B em uma sessão resulta em A: 9, B: 10. Se você viu os mesmos itens na próxima sessão, os valores mudam para A: 20, B: 9.

Use esse algoritmo em páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

Se você selecionar o algoritmo Mais visualizados por categoria, poderá selecionar as seguintes Chaves de recomendações:

* Categoria Atual
* Categoria favorita

### Mais visualizados pelo atributo de item

Recomenda itens ou mídias semelhantes aos itens ou mídias mais visualizados no site.

Esse algoritmo permite selecionar em qual atributo de item você deseja basear a recomendação, por exemplo, &quot;Nome&quot; ou &quot;Marca&quot;.

Em seguida, selecione quais atributos de perfil são armazenados no perfil do visitante para correspondência. Por exemplo, &quot;Marca favorita&quot;, &quot;Último item adicionado ao carrinho&quot; ou &quot;Programa mais visualizado&quot;.

### Mais vendidos em todo o site {#top-sellers}

Exibe os itens incluídos nas ordens mais concluídas de todo o site. Várias unidades do mesmo item em um único pedido são contadas como um pedido.

Esse algoritmo permite criar recomendações para os itens mais vendidos em seu site para aumentar a conversão e a receita. Essa lógica é especialmente adequada para visitantes novos do site.

### Mais vendidos por categoria

Exibe os itens incluídos nas ordens mais concluídas por categoria. Várias unidades do mesmo item em um único pedido são contadas como um pedido.

Esse algoritmo permite criar recomendações para os itens mais vendidos em seu site com base na categoria para aumentar a conversão e a receita. Essa lógica é especialmente adequada para visitantes novos do site.

Se você selecionar o algoritmo Mais visualizados por categoria, poderá selecionar as seguintes Chaves de recomendações:

* Categoria Atual
* Categoria favorita

### Mais Vendidos por Atributo de Item

Recomenda itens ou mídias semelhantes aos itens ou mídias mais comprados em seu site.

Esse algoritmo permite selecionar em qual atributo de item você deseja basear a recomendação, por exemplo, &quot;Nome&quot; ou &quot;Marca&quot;.

Em seguida, selecione quais atributos de perfil são armazenados no perfil do visitante para correspondência. Por exemplo, &quot;Marca favorita&quot;, &quot;Último item adicionado ao carrinho&quot; ou &quot;Programa mais visualizado&quot;.

### Comece pela métrica do Analytics

Exibe o &quot;X superior&quot;, onde *x* é uma métrica [!DNL Analytics] arbitrária. Ao usar dados comportamentais de mboxes, você pode usar Mais vendidos ou Mais visualizados (x = &quot;Vendido&quot; ou x = &quot;Visualizado&quot;). Se você estiver usando dados comportamentais de [!DNL Adobe Analytics], poderá usar x = &quot;Adições ao carrinho&quot; ou alguma outra métrica [!DNL Analytics].

## [!UICONTROL Item-Based]

O tipo de recomendação [!UICONTROL Item-Based] permite fazer recomendações com base na localização de itens semelhantes a um item que o usuário está visualizando atualmente ou que visualizou recentemente.

Os seguintes algoritmos estão disponíveis com o tipo de algoritmo [!UICONTROL Item-Based]:

### Pessoas que visualizaram isto, visualizaram aquilo {#viewed-viewed}

Recomenda itens visualizados com mais frequência na mesma sessão em que o item especificado é visualizado.

Essa lógica retorna outros produtos que as pessoas visualizaram após verem esse produto; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite criar oportunidades de conversão adicionais, recomendando itens que outros visitantes que visualizaram um item também visualizaram. Por exemplo, os visitantes que visualizam bicicletas rodoviárias em seu site também podem ver capacetes de bicicleta, kits de ciclismo, fechaduras e assim por diante. Você pode criar uma recomendação usando essa lógica que sugere que outros produtos ajudam a aumentar a receita.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que visualizaram isto, compraram aquilo {#viewed-bought}

Recomenda itens visualizados que são comprados com mais frequência na mesma sessão em que o item especificado é visualizado. Este critério retorna outros produtos que pessoas compraram depois de ver este, o produto especificado não é incluído nos resultados.

Essa lógica retorna outros produtos que as pessoas compraram após verem este; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada ao exibir uma recomendação em uma página de produto, por exemplo, que exibe itens que outros visitantes que visualizaram o item compraram. Por exemplo, se o visitante estiver visualizando uma vara de pesca, a recomendação poderá mostrar itens adicionais que outros visitantes compraram, como caixas de engrenagens, pernaltas e iscas de pesca. À medida que os visitantes navegam em seu site, você fornece a eles recomendações de compra adicionais.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que compraram isto, compraram aquilo {#bought-bought}

Recomenda os itens que são comprados com mais frequência pelos clientes ao mesmo tempo que o item especificado.

Essa lógica retorna outros produtos comprados pelas pessoas após a compra deste; o produto especificado não é incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada ao exibir uma recomendação em uma página de resumo do carrinho de compras, por exemplo, que exibe itens que outros compradores também compraram. Por exemplo, se o visitante estiver comprando um terno, a recomendação poderá exibir itens adicionais que outros visitantes compraram junto com o terno, como gravatas, sapatos e abotoaduras. À medida que os visitantes revisam suas compras, você fornece a eles recomendações adicionais.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Itens com atributos similares {#similar-attributes}

Recomenda itens ou mídias semelhantes a itens ou mídias baseados na atividade da página atual ou no comportamento passado do visitante.

Se selecionar Itens/mídia com atributos similares, você terá a opção de definir regras de similaridade de conteúdo.

Usar a similaridade de conteúdo para gerar recomendações é especialmente eficaz para novos itens, que provavelmente não serão exibidos nas recomendações usando Pessoas que visualizaram isto, visualizaram aquilo e outra lógica baseada no comportamento anterior. Você também pode usar similaridade de conteúdo para gerar recomendações úteis para novos visitantes, que não possuem compras antigas ou outros dados de histórico.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

Para obter mais informações, consulte [Similaridade de conteúdo](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

## [!UICONTROL User-Based]

O tipo de algoritmo baseado no usuário permite fazer recomendações com base no comportamento do usuário.

Os seguintes algoritmos estão disponíveis com o tipo de algoritmo [!UICONTROL User-Based]:

### Itens visualizados recentemente {#recently-viewed}

Use o histórico do visitante (abrangendo sessões) para apresentes os últimos *x* itens que o visitante viu, baseado no número de slots no design.

O algoritmo de Itens Visualizados Recentemente retorna um resultado específico para um determinado [ambiente](/help/main/administrating-target/hosts.md). Se dois sites pertencerem a ambientes diferentes e um visitante alternar entre os dois sites, cada site exibirá somente itens visualizados recentemente do site em questão. Se dois sites estiverem no mesmo ambiente e um visitante alternar entre eles, ele visualizará os mesmos itens visualizados recentemente em ambos os sites.

>[!NOTE]
>
>Você não pode usar os critérios [!UICONTROL Recently Viewed Items] para recomendações de backup.

[!UICONTROL Recently Viewed Items]/Mídia pode ser filtrada para que somente itens com um determinado atributo sejam exibidos.

* Os critérios visualizados recentemente são configuráveis, exatamente como os outros critérios nas recomendações.
* Você pode usar [coleções](/help/main/c-recommendations/c-products/collections.md), [exclusões](/help/main/c-recommendations/c-products/exclusions.md) e [inclusões](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) da mesma forma que qualquer outro critério.

Os possíveis casos de uso incluem: uma empresa multinacional com várias empresas pode ter um visitante para visualizar itens em várias propriedades digitais. Nesse caso, é possível limitar os itens exibidos recentemente somente àqueles da respectiva propriedade em que foram visualizados. Isso impede que itens visualizados recentemente sejam exibidos no site de outra propriedade digital.

Use esse algoritmo em páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] respeita as configurações globais de exclusões e a configuração de coleção selecionada para a atividade. Se um item for excluído por uma exclusão global ou não fizer parte da coleção selecionada, ele não será exibido. Portanto, ao usar um critério [!UICONTROL Recently Viewed Items], a configuração &quot;Todas as coleções&quot; geralmente deve ser usada.

### Recomendado para você {#recommended-for-you}

Recomenda itens com base no histórico de navegação, visualização e compra de cada visitante.

Esse algoritmo permite fornecer conteúdo e experiências personalizadas para visitantes novos e recorrentes. A lista de recomendações é ponderada em relação à atividade mais recente do visitante, é atualizada na sessão e se torna mais personalizada conforme o usuário navega em seu site.

Exibições e compras são usadas para determinar os itens recomendados. A chave de recomendação especificada (por exemplo, Item atual) é usada para aplicar qualquer filtro de regra de inclusão selecionado.

Por exemplo, você pode:

* Exclua itens que não atendam a determinados critérios (produtos indisponíveis, artigos publicados há mais de 30 dias, filmes com classificação R e assim por diante).
* Limitar os itens incluídos a uma única categoria ou à categoria atual.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves de filtragem:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

## Critérios personalizados {#custom}

O tipo de algoritmo Critérios personalizados permite fazer recomendações com base em um arquivo personalizado do qual você fez upload.

Recomendação determinada por um item que é armazenado no perfil do visitante, utilizando os atributos usuário.*x* ou perfil.*x* atributos.

Quando esta opção é selecionada, o valor `entity.id` deve estar presente no atributo do perfil.

Ao basear as recomendações em atributos personalizados, selecione o atributo personalizado e, em seguida, selecione o tipo de recomendação.

Você pode realizar uma filtragem em tempo real sobre os próprios resultados de critérios personalizados. Por exemplo, você pode limitar os itens recomendados somente àqueles da categoria ou marca favorita de um visitante. Isso permite combinar os cálculos offline com filtragens em tempo real.

Essa funcionalidade significa que você pode usar o [!DNL Target] para adicionar personalização às suas recomendações calculadas offline ou listas com preparo personalizado. Isso combina o poder de seus cientistas de dados e pesquisa com a entrega testada e comprovada da Adobe, filtragem em tempo de execução, testes A/B, direcionamento, relatórios, integrações e muito mais.

Com a adição das regras de inclusão aos critérios personalizados, as recomendações foram transformadas de estáticas para dinâmicas com base nos interesses de um visitante.

* Os critérios personalizados agora podem ser configurados, assim como outros critérios nas recomendações.
* Você pode usar [coleções](/help/main/c-recommendations/c-products/collections.md), [exclusões](/help/main/c-recommendations/c-products/exclusions.md) e [inclusões](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) da mesma forma que qualquer outro critério.

Os possíveis casos de uso incluem:

* Você deseja recomendar filmes de uma lista personalizada, mas somente se o visitante ainda não os assistiu.
* Você deseja executar um algoritmo offline e usar os resultados para potencializar suas recomendações, mas deve garantir que os itens esgotados nunca sejam recomendados.
* Você deseja incluir apenas itens que são da categoria favorita deste visitante.

## Chaves de recomendação {#keys}

As seguintes chaves de recomendação estão disponíveis na lista suspensa [!UICONTROL Recommendation Key]:

### Item Atual {#current-item}

A recomendação é determinada pelo item que o visitante está vendo atualmente.

As recomendações exibem outros itens que possam interessar o visitante que está interessado no item especificado.

Quando essa opção é selecionada, o valor `entity.id` deve ser passado como parâmetro na mbox de exibição.

Pode ser usado com os seguintes algoritmos:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Use a chave de recomendações do [!UICONTROL Current Item] em seu site em:

* Páginas de item único, como páginas de produtos.
* NÃO use em páginas de resultados de busca nulos.

### Último item comprado {#last-purchased}

A recomendação é determinada pelo último item comprado por cada visitante único. Isso é capturado automaticamente, portanto, nenhum valor deve ser transmitido na página.

Pode ser usado com os seguintes algoritmos:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Use a chave de recomendações do [!UICONTROL Last Purchased Item] em seu site em:

* Página inicial, página minha conta, anúncios em outros sites.
* NÃO use nas páginas do produto ou páginas relevantes para compras.

#### Chave de recomendações personalizadas

Você pode basear as recomendações no valor de um atributo de perfil personalizado. Por exemplo, suponha que você deseja exibir filmes recomendados com base no filme adicionado recentemente por um visitante à fila.

1. Selecione o atributo de perfil personalizado na lista suspensa **[!UICONTROL Recommendation Key]** (por exemplo, &quot;Último programa adicionado à Lista de favoritos&quot;).
1. Em seguida, selecione **[!UICONTROL Recommendation Logic]** (por exemplo, &quot;Pessoas que assistiram isto, assistiram aquilo&quot;).

   ![Caixa de diálogo Criar novos critérios](/help/main/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Se o atributo de perfil personalizado não corresponder diretamente a uma única ID de entidade, é necessário explicar ao [!DNL Recommendations] como você deseja que a correspondência seja feita a uma entidade. Por exemplo, suponha que você deseja exibir os principais itens de venda da marca favorita de um visitante.

1. Selecione o atributo de perfil personalizado na lista suspensa **[!UICONTROL Recommendation Key]** (por exemplo, &quot;Marca favorita&quot;).

1. Em seguida, selecione o **[!UICONTROL Recommendation Logic]** que deseja usar com esta chave (por exemplo, &quot;Mais vendidos&quot;).

   A opção [!UICONTROL Group By Unique Value Of] é exibida.

1. Selecione o atributo de entidade que corresponde à chave escolhida. Neste caso, &quot;Marca favorita&quot; corresponde à `entity.brand`.

   [!DNL Recommendations] agora gera uma lista de &quot;Mais vendidos&quot; para cada marca e mostra para o visitante a lista de &quot;Mais vendidos&quot; adequada com base no valor armazenado no atributo de perfil de Marca favorita do visitante.

   ![Caixa de diálogo 2 Criar novos critérios](/help/main/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Último item visualizado {#last-viewed}

A recomendação é determinada pelo último item visto por cada visitante único. Isso é capturado automaticamente, portanto, nenhum valor deve ser transmitido na página.

Pode ser usado com os seguintes algoritmos:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

Use a chave de recomendações do [!UICONTROL Last Viewed Item] em seu site em:

* Página inicial, página minha conta, anúncios em outros sites.
* NÃO use nas páginas do produto ou páginas relevantes para compras.

### Item Mais Visualizado {#most-viewed-logic}

Exibe os itens ou as mídias que são exibidos com mais frequência no site.

Essa lógica permite exibir recomendações com base nos itens mais visualizados no site para aumentar as conversões de outros itens. Por exemplo, um site de mídia pode exibir recomendações em sua página inicial para os vídeos mais visualizados, incentivando os visitantes a assistir a vídeos adicionais.

Essa chave de recomendação pode ser usada com os seguintes algoritmos:

* [!UICONTROL Items with similar attributes]
* [!UICONTROL People Who Viewed This, Viewed That]
* [!UICONTROL People Who Viewed This, Bought That]
* [!UICONTROL People Who Bought This, Bought That]

### Categoria Atual {#current-category}

A recomendação é determinada pela categoria de produto que o visitante está vendo atualmente.

As recomendações exibem itens na categoria de produto especificada.

Quando essa opção é selecionada, o valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição.

Essa chave de recomendação pode ser usada com os seguintes algoritmos:

* Mais vendidos
* Mais visualizados

Use a chave de recomendações do [!UICONTROL Current Category] em seu site em:

* Páginas de categoria única.
* NÃO use em páginas de resultados de busca nulos.

### Categoria favorita {#favorite-category}

A recomendação é determinada pela categoria de produto favorita do visitante.

As recomendações exibem itens na categoria de produto especificada.

Quando essa opção é selecionada, o valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição.

Essa chave de recomendação pode ser usada com os seguintes algoritmos:

* Mais vendidos
* Mais visualizados

Use a chave de recomendações do [!UICONTROL Current Category] em seu site em:

* Páginas de categoria única.
* NÃO use em páginas de resultados de busca nulos.

### Afinidade do site {#site-affinity}

Recomenda itens com base na certeza de uma relação entre os itens. Você pode configurar esses critérios para determinar quantos dados são exigidos antes de uma recomendação ser apresentada usando o controle deslizante Regras de inclusão. Por exemplo, se você selecionar muito forte, serão recomendados os produtos com maior certeza de correspondência.

Por exemplo, se você definir uma afinidade muito forte e seu design incluir cinco itens, três dos quais alcançam o limite de força de conexão, os dois itens que não alcançarem os requisitos mínimos de força não serão exibidos nas recomendações e serão substituídos por seus itens de backup definidos. Os itens com a maior afinidade são exibidos primeiro.

Por exemplo, um retailer online pode recomendar itens em visitas subsequentes nas quais um visitante tenha mostrado interesse durante sessões anteriores. A atividade para cada sessão de visitante é capturada para calcular uma afinidade com base em um modelo de recenticidade e frequência. À medida que esse visitante retorna ao seu site, a afinidade do site é usada para exibir recomendações com base em ações anteriores no site.

Alguns clientes com coleções de produtos e comportamento do site diversos poderão obter melhores resultados caso definam uma afinidade do site fraca.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado
