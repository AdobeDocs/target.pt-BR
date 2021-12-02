---
keywords: chave de recomendação, lógica de recomendação, categoria atual, atributo personalizado, último item comprado, último item visualizado, item mais visualizado, item mais visualizado, categoria favorita, popularidade, item visualizado recentemente, último comprado, mais visualizado, favorito, visualizado recentemente
description: Saiba como usar recomendações com base em chaves que usam o contexto de comportamento do visitante para mostrar resultados relevantes no Adobe [!DNL Target] Atividades do Recommendations .
title: Como basear a recomendação em uma chave de recomendação?
feature: Recommendations
mini-toc-levels: 2
exl-id: 49764f18-88fb-41be-b2a0-e7ced9de742c
source-git-commit: ce5a9428602c6ef5547a407bbc56ff2cbd7631b6
workflow-type: tm+mt
source-wordcount: '3936'
ht-degree: 40%

---

# Basear a recomendação em uma chave de recomendação

O Recommendations baseado em algoritmos usa o contexto de comportamento do visitante para mostrar resultados relevantes em [!DNL Adobe Target] [!DNL Recommendations] atividades.

Cada tipo de algoritmo fornece algoritmos diferentes adequados para seu tipo, conforme mostrado na tabela a seguir:

| Tipo de algoritmo | Quando usar | Algoritmos disponíveis |
| --- | --- | --- |
| [!UICONTROL Baseado em carrinho] | Faça recomendações com base no conteúdo do carrinho do usuário. | <ul><li>Pessoas que visualizaram estes, visualizaram aqueles</li><li>Pessoas que visualizaram estes, compraram aqueles</li><li>Pessoas que compraram isto, compraram aqueles</li></ul> |
| [!UICONTROL Baseado em popularidade] | Faça recomendações com base na popularidade geral de um item em seu site ou na popularidade dos itens em uma categoria favorita ou mais exibida do usuário, marca, gênero e assim por diante. | <ul><li>Mais visualizados no site</li><li>Mais visualizados por categoria</li><li>Mais visualizados por atributo de item</li><li>Mais vendidos no site</li><li>Mais vendidos por categoria</li><li>Principais Vendedores por Atributo de Item</li><li>Principais por métrica do Analytics</li></ul> |
| [!UICONTROL Baseado em item] | Faça recomendações baseadas em encontrar itens semelhantes a um item que o usuário está visualizando ou visualizou recentemente. | <ul><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Pessoas que visualizaram isto, compraram aquilo</li><li>Pessoas que compraram isto, compraram aquilo</li><li>Itens com atributos similares</li></ul> |
| [!UICONTROL Baseado em usuário] | Faça recomendações com base no comportamento do usuário. | <ul><li>Itens visualizados recentemente </li><li>Recomendado para você</li></ul> |
| [!UICONTROL Critérios personalizados] | Faça recomendações com base em um arquivo personalizado que você fez upload. | <ul><li>Algoritmo personalizado</li></ul> |

Cada critério é definido em sua própria guia. O tráfego é dividido uniformemente entre os diferentes testes de critérios. Em outras palavras, se você tem dois critérios, o tráfego é dividido igualmente entre eles. Se você tem dois critérios e dois designs, o tráfego é dividido igualmente entre as quatro combinações. Também é possível especificar uma porcentagem de visitantes do site que veem o conteúdo padrão, para comparação. Nesse caso, a porcentagem especificada de visitantes visualiza o conteúdo padrão, e o restante é dividido entre seus critérios e combinações de design.

Para obter mais informações sobre como criar critérios e definir seus tipos de algoritmos e algoritmos, consulte [Criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md).

Algoritmos de recomendações diferentes se prestam à localização em diferentes tipos de páginas. Consulte as seções a seguir para obter mais informações sobre cada tipo de algoritmo e seus algoritmos disponíveis.

## Baseado em carrinho {#cart-based}

O [!UICONTROL Baseado em carrinho] o tipo de algoritmo permite recomendar itens com base no conteúdo do carrinho atual do visitante. As chaves de recomendação são fornecidas por meio do parâmetro mbox `cartIds` em valores separados por vírgula. Somente os primeiros 10 valores são considerados.

A lógica de recomendação baseada no carrinho é semelhante ao &quot;[!UICONTROL Recomendado Para Você]&quot; algoritmo baseado no usuário e no &quot;[!UICONTROL Pessoas que visualizaram estes, compraram aqueles]&quot; e &quot;[!UICONTROL Pessoas que compraram isto, compraram aqueles]&quot; algoritmos baseados em itens.

[!DNL Target] O usa técnicas de filtragem colaborativas para determinar semelhanças para cada item no carrinho do visitante e combina essas semelhanças comportamentais em cada item para obter uma lista mesclada.

[!DNL Target] também oferece aos profissionais de marketing a opção de observar o comportamento do visitante em uma única sessão ou em várias sessões:

* **[!UICONTROL Sessão única]**: Com base no que outros visitantes fizeram em uma única sessão.

   Olhar para o comportamento em uma única sessão pode fazer sentido quando há uma sensação de que os produtos &quot;vão&quot; fortemente uns com os outros com base em um uso, ocasião ou evento. Por exemplo, um visitante está comprando uma impressora e também pode precisar de tinta e papel. Ou, um visitante está comprando manteiga de amendoim e também pode precisar de pão e geleia.

* **[!UICONTROL Em sessões]**: Com base no que outros visitantes fizeram em várias sessões.

   Observar o comportamento em várias sessões pode fazer sentido quando há uma sensação de que os produtos &quot;aceitam&quot; fortemente uns com os outros com base na preferência ou sabor do visitante. Por exemplo, um visitante gosta de Star Wars e também pode gostar de Indiana Jones, mesmo que o visitante não queira assistir a ambos os filmes na mesma sessão. Ou, um visitante gosta do jogo de tabuleiro &quot;Codenames&quot; e também pode gostar do jogo de tabuleiro &quot;Avalon&quot;, mesmo que o visitante não possa jogar os dois jogos simultaneamente. 

[!DNL Target] O faz recomendações para cada visitante com base nos itens em seu carrinho atual, independentemente de você observar o comportamento do visitante em uma única sessão ou em várias sessões.

Os seguintes algoritmos estão disponíveis com o [!UICONTROL Baseado em carrinho] tipo de algoritmo:

### [!UICONTROL Pessoas que visualizaram isto, visualizaram aqueles]

Recomenda itens visualizados com mais frequência na mesma sessão em que o item especificado é visualizado.

Essa lógica retorna outros produtos visualizados após esta visualização; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite criar oportunidades de conversão adicionais, recomendando itens que outros visitantes que visualizaram um item também visualizaram. Por exemplo, os visitantes que visualizam bicicletas de estrada em seu site também podem ver capacetes de bicicletas, kits de bicicletas, fechaduras e assim por diante. Você pode criar uma recomendação usando essa lógica que sugere que outros produtos o ajudem a aumentar a receita.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que viram isto, compraram aquelas

Recomenda itens visualizados que são comprados com mais frequência na mesma sessão em que o item especificado é visualizado. Este critério retorna outros produtos que pessoas compraram depois de ver este, o produto especificado não é incluído nos resultados.

Essa lógica retorna outros produtos que as pessoas compraram após visualizar este; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada exibindo uma recomendação em uma página de produto, por exemplo, que exibe itens que outros visitantes visualizaram o item comprado. Por exemplo, se o visitante estiver visualizando um polo de pesca, a recomendação pode mostrar itens adicionais que outros visitantes compraram, como caixas de ataque, arruaceiros e arruaceiros de pesca. Conforme os visitantes navegam em seu site, você fornece recomendações de compra adicionais para eles.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que compraram isto, compraram aquilo

Recomenda os itens que são comprados com mais frequência pelos clientes ao mesmo tempo que o item especificado.

Essa lógica retorna outros produtos que as pessoas compraram depois de comprar esse; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada exibindo uma recomendação em uma página de resumo do carrinho de compras, por exemplo, que exibe itens que outros compradores também compraram. Por exemplo, se o visitante estiver comprando um terno, a recomendação poderá exibir itens adicionais que outros visitantes compraram junto com o terno, como gravatas, sapatos de vestimenta e caixotes. Conforme os visitantes revisam suas compras, você os fornece recomendações adicionais.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

## [!UICONTROL Baseado em popularidade]

O [!UICONTROL Baseado em popularidade] O tipo de algoritmo permite fazer recomendações com base na popularidade geral de um item em seu site ou com base na popularidade dos itens em uma categoria favorita ou mais exibida do usuário, marca, gênero e assim por diante.

Os seguintes algoritmos estão disponíveis com o [!UICONTROL Baseado em popularidade] tipo de algoritmo:

### Mais visualizados no site {#most-viewed}

A recomendação é determinada pelo item que foi visualizado com mais frequência. Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de produto
* 5 pontos para cada visualização seguinte
* No fim da sessão, divida todos os valores por 2

Por exemplo, visualizar a prancha_de_surfe_A e depois a prancha_de_surfe_B em uma sessão resulta em A: 10, B: 5. Quando a sessão terminar, você terá A: 5, B: 2.5. Se você exibir os mesmos itens na próxima sessão, os valores serão alterados para A: 15 B: 7.5.

Use esse algoritmo em páginas gerais, como páginas iniciais ou de aterrissagem e anúncios em outros sites.

### Mais visualizados por categoria {#most-viewed-category}

A recomendação é determinada pela categoria que recebeu a mais atividade, utilizando o mesmo método usado para &quot;item mais visto&quot;, exceto que as categorias são classificadas, em vez de os produtos.

Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de categoria
* 5 pontos para cada visualização seguinte

Categorias visitadas pela primeira vez recebem 10 pontos. 5 pontos são dados para visitas seguintes para a mesma categoria. Com cada visita, categorias não atuais que foram vistas anteriormente são diminuídas em 1.

Por exemplo, a visualização da categoria A e da categoria B em uma sessão resulta em A: 9, B: 10. Se você viu os mesmos itens na próxima sessão, os valores mudam para A: 20, B: 9.

Use esse algoritmo em páginas gerais, como páginas iniciais ou de aterrissagem e anúncios em outros sites.

Se você selecionar o algoritmo Mais visualizados por categoria , é possível selecionar as seguintes Chaves do Recommendations:

* Categoria Atual
* Categoria favorita

### Mais visualizados por atributo de item

Recomenda itens ou mídias semelhantes aos itens ou mídias mais visualizados do site.

Este algoritmo permite selecionar em qual atributo de item você deseja basear a recomendação, por exemplo, &quot;Nome&quot; ou &quot;Marca&quot;.

Em seguida, selecione quais atributos de perfil armazenados no perfil do visitante devem corresponder, por exemplo, &quot;Marca favorita&quot;, &quot;Último item adicionado ao carrinho&quot; ou &quot;Mostrar mais visualizado&quot;.

### Mais vendidos no site {#top-sellers}

Exibe os itens incluídos nos pedidos mais concluídos de todo o site. Várias unidades do mesmo item em um único pedido são contadas como um pedido.

Este algoritmo permite que você crie recomendações para itens mais vendidos no site para aumentar a conversão e a receita. Essa lógica é especialmente adequada para visitantes novos do site.

### Mais vendidos por categoria

Exibe os itens incluídos nos pedidos mais concluídos por categoria. Várias unidades do mesmo item em um único pedido são contadas como um pedido.

Este algoritmo permite criar recomendações para itens mais vendidos no site com base na categoria para aumentar a conversão e a receita. Essa lógica é especialmente adequada para visitantes novos do site.

Se você selecionar o algoritmo Mais visualizados por categoria , é possível selecionar as seguintes Chaves do Recommendations:

* Categoria Atual
* Categoria favorita

### Principais Vendedores por Atributo de Item

(Informações em breve)

### Principais por métrica do Analytics

Exibe o &quot;x superior&quot;, onde *x* é um procedimento arbitrário [!DNL Analytics] métrica. Ao usar dados comportamentais de mboxes, você pode usar Mais vendidos ou Mais visualizados (x = &quot;Vendidos&quot; ou x = &quot;Visualizados&quot;). Se estiver usando dados comportamentais do [!DNL Adobe Analytics], você pode usar x = &quot;Adições ao carrinho&quot; ou algum outro [!DNL Analytics] métrica.

## [!UICONTROL Baseado em item]

O [!UICONTROL Baseado em item] o tipo de recomendação permite que você faça recomendações com base na localização de itens semelhantes a um item que o usuário está visualizando no momento ou que foi visualizado recentemente.

Os seguintes algoritmos estão disponíveis com o [!UICONTROL Baseado em item] tipo de algoritmo:

### Pessoas que visualizaram isto, visualizaram aquilo {#viewed-viewed}

Recomenda itens visualizados com mais frequência na mesma sessão em que o item especificado é visualizado.

Essa lógica retorna outros produtos visualizados após esta visualização; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite criar oportunidades de conversão adicionais, recomendando itens que outros visitantes que visualizaram um item também visualizaram. Por exemplo, os visitantes que visualizam bicicletas de estrada em seu site também podem ver capacetes de bicicletas, kits de bicicletas, fechaduras e assim por diante. Você pode criar uma recomendação usando essa lógica que sugere que outros produtos o ajudem a aumentar a receita.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que visualizaram isto, compraram aquilo {#viewed-bought}

Recomenda itens visualizados que são comprados com mais frequência na mesma sessão em que o item especificado é visualizado. Este critério retorna outros produtos que pessoas compraram depois de ver este, o produto especificado não é incluído nos resultados.

Essa lógica retorna outros produtos que as pessoas compraram após visualizar este; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada exibindo uma recomendação em uma página de produto, por exemplo, que exibe itens que outros visitantes visualizaram o item comprado. Por exemplo, se o visitante estiver visualizando um polo de pesca, a recomendação pode mostrar itens adicionais que outros visitantes compraram, como caixas de ataque, arruaceiros e arruaceiros de pesca. Conforme os visitantes navegam em seu site, você fornece recomendações de compra adicionais para eles.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que compraram isto, compraram aquilo {#bought-bought}

Recomenda os itens que são comprados com mais frequência pelos clientes ao mesmo tempo que o item especificado.

Essa lógica retorna outros produtos que as pessoas compraram depois de comprar esse; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada exibindo uma recomendação em uma página de resumo do carrinho de compras, por exemplo, que exibe itens que outros compradores também compraram. Por exemplo, se o visitante estiver comprando um terno, a recomendação poderá exibir itens adicionais que outros visitantes compraram junto com o terno, como gravatas, sapatos de vestimenta e caixotes. Conforme os visitantes revisam suas compras, você os fornece recomendações adicionais.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Itens com atributos similares {#similar-attributes}

Recomenda itens ou mídias semelhantes a itens ou mídias baseados na atividade da página atual ou no comportamento passado do visitante.

Se você selecionar Itens/mídia com atributos similares, você terá a opção de definir regras de similaridade de conteúdo.

Usar similaridade de conteúdo para gerar recomendações é especialmente eficaz para novos itens, que provavelmente não aparecem em recomendações usando pessoas que viram isto, viram aquilo e outras lógicas baseadas em comportamento anterior. Você também pode usar similaridade de conteúdo para gerar recomendações úteis para novos visitantes, que não possuem compras antigas ou outros dados de histórico.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves do Recommendations:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

Para obter mais informações, consulte [Similaridade de conteúdo](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

## [!UICONTROL Baseado em usuário]

O tipo de algoritmo baseado em usuário permite fazer recomendações com base no comportamento do usuário.

Os seguintes algoritmos estão disponíveis com o [!UICONTROL Baseado em usuário] tipo de algoritmo:

### Itens visualizados recentemente {#recently-viewed}

Use o histórico do visitante (abrangendo sessões) para apresentes os últimos *x* itens que o visitante viu, baseado no número de slots no design.

O algoritmo de Itens visualizados recentemente retorna um resultado específico para um determinado [ambiente](/help/administrating-target/hosts.md). Se dois sites pertencerem a ambientes diferentes e um visitante alternar entre os dois sites, cada site exibirá somente itens visualizados recentemente do site em questão. Se dois sites estiverem no mesmo ambiente e um visitante alternar entre eles, ele visualizará os mesmos itens visualizados recentemente em ambos os sites.

>[!NOTE]
>
>Não é possível usar a variável [!UICONTROL Itens visualizados recentemente] critérios para recomendações de backup.

Os itens/mídias visualizados recentemente agora podem ser filtrados para que somente os itens com um determinado atributo sejam exibidos.

* Os critérios visualizados recentemente são configuráveis, exatamente como os outros critérios nas recomendações.
* Você pode utilizar [coleções](/help/c-recommendations/c-products/collections.md), [exclusões](/help/c-recommendations/c-products/exclusions.md) e [inclusões](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) da mesma forma que os outros critérios.

Os possíveis casos de uso incluem, uma empresa multinacional com várias empresas pode ter itens de exibição de visitante em várias propriedades digitais. Nesse caso, é possível limitar os itens exibidos recentemente somente àqueles da respectiva propriedade em que foram visualizados. Isso impede que itens visualizados recentemente sejam exibidos no site de outra propriedade digital.

Use esse algoritmo em páginas gerais, como páginas iniciais ou de aterrissagem e anúncios em outros sites.

>[!NOTE]
>
>[!UICONTROL Itens visualizados recentemente] O respeita as configurações globais de exclusões e a configuração de coleção selecionada para a atividade. Se um item for excluído por uma exclusão global ou não estiver contido na coleção selecionada, ele não será exibido. Portanto, ao usar um [!UICONTROL Itens visualizados recentemente] , a configuração &quot;Todas as coleções&quot; geralmente deve ser usada.

### Recomendado para você {#recommended-for-you}

Recomenda itens com base no histórico de navegação, visualização e compra de cada visitante.

Esse algoritmo permite que você forneça conteúdo e experiências personalizadas para visitantes novos e recorrentes. A lista de recomendações é ponderada em relação à atividade mais recente do visitante, é atualizada na sessão e se torna mais personalizada conforme o usuário navega em seu site.

As exibições e compras são usadas para determinar os itens recomendados. A chave de recomendação especificada (por exemplo, Item atual) é usada para aplicar quaisquer filtros de regras de inclusão selecionados.

Por exemplo, você pode:

* Exclua itens que não atendem a determinados critérios (produtos esgotados, artigos publicados há mais de 30 dias, filmes com classificação R e assim por diante).
* Limitar itens incluídos a uma única categoria ou à categoria atual.

Se você selecionar esse algoritmo, poderá selecionar as seguintes Chaves de filtragem:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

## Critérios personalizados {#custom}

O tipo de algoritmo de Critérios personalizados permite fazer recomendações com base em um arquivo personalizado que você faz upload.

Recomendação determinada por um item que é armazenado no perfil do visitante, utilizando os atributos usuário.*x* ou perfil.*x* atributos.

Quando esta opção é selecionada, o valor `entity.id` deve estar presente no atributo do perfil.

Ao basear as recomendações em atributos personalizados, selecione o atributo personalizado e, em seguida, selecione o tipo de recomendação.

Você pode realizar uma filtragem em tempo real sobre os próprios resultados de critérios personalizados. Por exemplo, você pode limitar os itens recomendados somente àqueles da categoria ou marca favorita de um visitante. Isso permite combinar os cálculos offline com filtragens em tempo real.

Essa funcionalidade significa que você pode usar [!DNL Target] para adicionar personalização às suas recomendações calculadas offline ou listas com preparo personalizado. Isso combina o poder de seus cientistas de dados e pesquisa com a entrega testada e comprovada da Adobe, filtragem em tempo de execução, testes A/B, direcionamento, relatórios, integrações e muito mais.

Com a adição das regras de inclusão aos critérios personalizados, as recomendações foram transformadas de estáticas para dinâmicas com base nos interesses de um visitante.

* Os critérios personalizados agora podem ser configurados, assim como outros critérios nas recomendações.
* Você pode utilizar [coleções](/help/c-recommendations/c-products/collections.md), [exclusões](/help/c-recommendations/c-products/exclusions.md) e [inclusões](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) da mesma forma que os outros critérios.

Os possíveis casos de uso incluem:

* Você deseja recomendar filmes de uma lista personalizada, mas somente se o visitante ainda não os assistiu.
* Você deseja executar um algoritmo offline e usar os resultados para potencializar suas recomendações, mas é necessário garantir que itens esgotados nunca sejam recomendados.
* Você deseja incluir apenas itens que são da categoria favorita deste visitante.

## Chaves de recomendação

As seguintes chaves de recomendação estão disponíveis no [!UICONTROL Chave de recomendação] lista suspensa:

### Item Atual {#current-item}

A recomendação é determinada pelo item que o visitante está vendo atualmente.

As recomendações exibem outros itens que possam interessar o visitante que está interessado no item especificado.

Quando essa opção é selecionada, o valor `entity.id` deve ser passado como parâmetro na mbox de exibição.

Pode ser usado com os seguintes algoritmos:

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]

Use o [!UICONTROL Item atual] chave de recomendações no seu site em:

* Páginas de item único, como páginas de produtos.
* NÃO use em páginas de resultados de busca nulos.

### Último item comprado {#last-purchased}

A recomendação é determinada pelo último item comprado por cada visitante único. Isso é capturado automaticamente, portanto, nenhum valor deve ser transmitido na página.

Pode ser usado com os seguintes algoritmos:

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]

Use o [!UICONTROL Último item comprado] chave de recomendações no seu site em:

* Página inicial, página minha conta, anúncios em outros sites.
* NÃO use nas páginas do produto ou páginas relevantes para compras.

#### Chave de recomendações personalizada

Você pode basear as recomendações no valor de um atributo de perfil personalizado. Por exemplo, suponha que você deseja exibir filmes recomendados com base no filme adicionado recentemente por um visitante à fila.

1. Selecione o atributo de perfil personalizado na lista suspensa **[!UICONTROL Chave de recomendação]** (por exemplo, &quot;Último programa adicionado à Lista de favoritos&quot;).
1. Em seguida, selecione a **[!UICONTROL Lógica de recomendação]** (por exemplo, &quot;Pessoas que assistiram isto, assistiram aquilo&quot;).

   ![Caixa de diálogo Criar novos critérios](/help/c-recommendations/c-algorithms/assets/create-new-criteria-1.png)

Se o atributo de perfil personalizado não corresponder diretamente a uma única ID de entidade, é necessário explicar ao [!DNL Recommendations] como você deseja que a correspondência seja feita a uma entidade. Por exemplo, suponha que você deseja exibir os principais itens de venda da marca favorita de um visitante.

1. Selecione o atributo de perfil personalizado na lista suspensa **[!UICONTROL Chave de recomendação]** (por exemplo, &quot;Marca favorita&quot;).

1. Em seguida, selecione **[!UICONTROL Lógica de recomendação]** que deseja usar com esta chave (por exemplo, &quot;Mais vendidos&quot;).

   A opção [!UICONTROL Agrupar por valor exclusivo de] é exibida.

1. Selecione o atributo de entidade que corresponde à chave escolhida. Neste caso, &quot;Marca favorita&quot; corresponde à `entity.brand`.

   O [!DNL Recommendations] agora gera uma lista de &quot;Mais vendidos&quot; para cada marca e mostra para o visitante a lista de &quot;Mais vendidos&quot; adequada com base no valor armazenado no atributo de perfil de Marca favorita do visitante.

   ![Caixa de diálogo 2 Criar novos critérios](/help/c-recommendations/c-algorithms/assets/create-new-criteria-2.png)

### Último item visualizado {#last-viewed}

A recomendação é determinada pelo último item visto por cada visitante único. Isso é capturado automaticamente, portanto, nenhum valor deve ser transmitido na página.

Pode ser usado com os seguintes algoritmos:

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]

Use o [!UICONTROL Último item visualizado] chave de recomendações no seu site em:

* Página inicial, página minha conta, anúncios em outros sites.
* NÃO use nas páginas do produto ou páginas relevantes para compras.

### Item Mais Visualizado {#most-viewed-logic}

Exibe os itens ou mídias visualizados com mais frequência em seu site.

Essa lógica permite exibir recomendações baseadas nos itens mais visualizados do site para aumentar as conversões de outros itens. Por exemplo, um site de mídia pode exibir recomendações em sua página inicial de seus vídeos mais visualizados para incentivar os visitantes a assistir a vídeos adicionais.

Essa chave de recomendação pode ser usada com os seguintes algoritmos:

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]

### Categoria Atual {#current-category}

A recomendação é determinada pela categoria de produto que o visitante está vendo atualmente.

As recomendações exibem itens na categoria de produto especificada.

Quando essa opção é selecionada, o valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição.

Essa chave de recomendação pode ser usada com os seguintes algoritmos:

* Mais vendidos
* Mais visualizados

Use o [!UICONTROL Categoria atual] chave de recomendações no seu site em:

* Páginas de categoria única.
* NÃO use em páginas de resultados de busca nulos.

### Categoria favorita {#favorite-category}

A recomendação é determinada pela categoria de produto favorita do visitante.

As recomendações exibem itens na categoria de produto especificada.

Quando essa opção é selecionada, o valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição.

Essa chave de recomendação pode ser usada com os seguintes algoritmos:

* Mais vendidos
* Mais visualizados

Use o [!UICONTROL Categoria atual] chave de recomendações no seu site em:

* Páginas de categoria única.
* NÃO use em páginas de resultados de busca nulos.

### Afinidade do site {#site-affinity}

Recomenda itens com base na certeza de uma relação entre os itens. Você pode configurar esses critérios para determinar quantos dados são exigidos antes de uma recomendação ser apresentada usando o controle deslizante Regras de inclusão. Por exemplo, se você selecionar muito forte, serão recomendados os produtos com maior certeza de correspondência.

Por exemplo, se você definir uma afinidade muito forte e seu design incluir cinco itens, três dos quais alcançam o limite de força de conexão, os dois itens que não alcançarem os requisitos mínimos de força não serão exibidos nas recomendações e serão substituídos por seus itens de backup definidos. Os itens com a maior afinidade são exibidos primeiro.

Por exemplo, uma varejista online pode recomendar itens em visitas subsequentes em que um visitante tenha mostrado interesse durante sessões anteriores. A atividade para cada sessão do visitante é capturada para calcular uma afinidade com base no recenticidade e no modelo de frequência. Conforme esse visitante retorna ao seu site, a afinidade do site é usada para exibir recomendações com base em ações anteriores no seu site.

Alguns clientes com coleções de produtos e comportamento do site diversos poderão obter melhores resultados caso definam uma afinidade do site fraca.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado
