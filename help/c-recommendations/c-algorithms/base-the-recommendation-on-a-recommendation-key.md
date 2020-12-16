---
keywords: recommendation key;recommendation logic;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: O Recommendations baseado em chaves usa o contexto de comportamento do visitante para mostrar resultados relevantes no Adobe Target Recommendations atividade.
title: Basear a recomendação em uma chave de recomendação
feature: criteria
mini-toc-levels: 2
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '2889'
ht-degree: 69%

---


# Basear a recomendação em uma chave de recomendação

O Recommendations baseado em chaves usa o contexto de comportamento do visitante para mostrar resultados relevantes nas atividades [!DNL Adobe Target] [!DNL Recommendations].

Há dois tipos de recomendações:

* **Popularidade:** lista itens de acordo com mais visualizados, mais vendidos e métricas principais. A chave fica vazia para critérios de popularidade.
* **Baseado em chave:** inclui o resto dos critérios. Recommendations oferecem um conjunto diverso de escolhas a respeito do tipo de chave. As opções vão desde &quot;item atual&quot; até &quot;parâmetros de perfil&quot;, que permitem que você defina programaticamente as chaves dos valores para recomendar. Você pode testar vários critérios uns em relação aos outros baseando cada critério em uma chave diferente.

Cada critério é definido em sua própria guia. O tráfego é dividido uniformemente entre os diferentes testes de critérios. Em outras palavras, se você tem dois critérios, o tráfego é dividido igualmente entre eles. Se você tem dois critérios e dois designs, o tráfego é dividido igualmente entre as quatro combinações. Também é possível especificar uma porcentagem de visitantes do site que veem o conteúdo padrão, para comparação. Nesse caso, o percentual especificado de visitantes acompanha o conteúdo padrão e o restante é dividido entre os seus critérios e combinações de design.

1. Crie um novo critério ou selecione um critério existente e clique em **[!UICONTROL Editar]**.
1. Para alterar a chave de recomendação, selecione a nova chave na lista suspensa [!UICONTROL Chave de recomendação] e clique em **[!UICONTROL Salvar]** ou **[!UICONTROL Atualizar]**.

   Como lógicas diferentes levam a chaves de recomendações diferentes, recomendações diferentes se apresentam para localização em diferentes tipos de páginas. Consulte as seções a seguir para obter mais informações sobre cada chave de recomendação.

## Chaves de recomendação

As seguintes chaves de recomendação estão disponíveis na lista suspensa [!UICONTROL Chave de recomendação]:

### Item Atual {#current-item}

A recomendação é determinada pelo item que o visitante está vendo atualmente.

As recomendações exibem outros itens que possam interessar o visitante que está interessado no item especificado.

Quando essa opção é selecionada, o valor `entity.id` deve ser passado como parâmetro na mbox de exibição.

#### Lógica (critério)

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

#### Onde usar em seu site

* Páginas de item único, como páginas de produtos.
* NÃO use em páginas de resultados de busca nulos.

### Categoria Atual  {#current-category}

A recomendação é determinada pela categoria de produto que o visitante está vendo atualmente.

As recomendações exibem itens na categoria de produto especificada.

Quando essa opção é selecionada, o valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição.

#### Lógica (critério)

* Mais vendidos
* Mais visualizados

#### Onde usar em seu site

* Páginas de categoria única.
* NÃO use em páginas de resultados de busca nulos.

### Atributo personalizado   {#custom}

Recomendação determinada por um item que é armazenado no perfil do visitante, utilizando os atributos usuário.*x* ou perfil.*x* atributos.

Quando esta opção é selecionada, o valor `entity.id` deve estar presente no atributo do perfil.

Ao basear as recomendações em atributos personalizados, selecione o atributo personalizado e, em seguida, selecione o tipo de recomendação.

Você pode realizar uma filtragem em tempo real sobre os próprios resultados de critérios personalizados. Por exemplo, você pode limitar os itens recomendados somente àqueles da categoria ou marca favorita de um visitante. Isso permite combinar os cálculos offline com filtragens em tempo real.

Essa funcionalidade significa que você pode usar [!DNL Target] para adicionar personalização sobre suas recomendações calculadas offline ou listas com curadoria personalizada. Isso combina o poder de seus cientistas de dados e pesquisa com a entrega testada e comprovada da Adobe, filtragem em tempo de execução, testes A/B, direcionamento, relatórios, integrações e muito mais.

Com a adição das regras de inclusão aos critérios personalizados, as recomendações foram transformadas de estáticas para dinâmicas com base nos interesses de um visitante.

* Os critérios personalizados agora podem ser configurados, assim como outros critérios nas recomendações.
* Você pode utilizar [coleções](/help/c-recommendations/c-products/collections.md), [exclusões](/help/c-recommendations/c-products/exclusions.md) e [inclusões](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) da mesma forma que os outros critérios.

Os possíveis casos de uso incluem:

* Você deseja recomendar filmes de uma lista personalizada, mas somente se o visitante ainda não os assistiu.
* Você deseja executar um algoritmo offline e usar os resultados para ativar suas recomendações, mas é necessário garantir que itens fora de estoque nunca sejam recomendados.
* Você deseja incluir apenas itens que são da categoria favorita deste visitante.

#### Lógica (critério)

* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Comportamento geral]
* [!UICONTROL Mais visualizados]
* [!UICONTROL Mais vendidos]

Se a chave é um atributo personalizado do perfil e o tipo de algoritmo é Mais visualizados ou Mais vendidos, uma nova lista suspensa que mostra o chamado &quot;Agrupado pelo valor único de&quot; que tem uma lista de atributos de entidade conhecidos (exceto ID, categoria, margem, valor, inventário e ambiente). Esse campo é obrigatório.

#### Onde usar em seu site

* Pode ser usado em qualquer página.

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

### Categoria favorita {#favorite-category}

A recomendação é determinada pela categoria que recebeu a mais atividade, utilizando o mesmo método usado para &quot;item mais visto&quot;, exceto que as categorias são classificadas, em vez de os produtos.

Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de categoria
* 5 pontos para cada visualização seguinte

Categorias visitadas pela primeira vez recebem 10 pontos. 5 pontos são dados para visitas seguintes para a mesma categoria. Com cada visita, categorias não atuais que foram vistas anteriormente são diminuídas em 1.

Por exemplo, a visualização da categoria A e da categoria B em uma sessão resulta em A: 9, B: 10. Se você viu os mesmos itens na próxima sessão, os valores mudam para A: 20, B: 9.

#### Lógica (critério)

* [!UICONTROL Mais vendidos]
* [!UICONTROL Mais visualizados]

#### Onde usar em seu site

* Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

### Último item comprado {#last-purchased}

A recomendação é determinada pelo último item comprado por cada visitante único. Ela é capturada automaticamente, assim nenhum valor precisa ser aprovado na página.

#### Lógica (critério)

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

#### Onde usar em seu site

* Página inicial, página minha conta, anúncios em outros sites.
* NÃO use nas páginas do produto ou páginas relevantes para compras.

### Último item visualizado  {#last-viewed}

A recomendação é determinada pelo último item visto por cada visitante único. Ela é capturada automaticamente, assim nenhum valor precisa ser aprovado na página.

#### Lógica (critério)

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

#### Onde usar em seu site

* Página inicial, página minha conta, anúncios em outros sites.
* NÃO use nas páginas do produto ou páginas relevantes para compras.

### Item Mais Visualizado  {#most-viewed}

A recomendação é determinada pelo item visto com mais frequência, usando o mesmo método utilizado para a categoria de favoritos.

Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de produto
* 5 pontos para cada visualização seguinte
* No fim da sessão, divida todos os valores por 2

Por exemplo, visualizar a prancha_de_surfe_A e depois a prancha_de_surfe_B em uma sessão resulta em A: 10, B: 5. Quando a sessão é encerrada, você tem A: 5, B: 2,5. Se você exibir os mesmos itens na sessão seguinte, os valores vão mudar para A: 15 B: 7,5.

#### Lógica (critério)

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

#### Onde usar em seu site

* Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

### Popularidade  {#popularity}

A recomendação é determinada pela popularidade de itens em seu site. A popularidade inclui os principais vendedores e os mais visualizados por dados de mbox e, se você utilizar o Adobe Analytics, todas as métricas disponíveis no relatório do produto. Itens são classificados de acordo com a lógica de recomendação que você selecionou.

#### Lógica (critério)

* [!UICONTROL Mais vendidos]
* [!UICONTROL Mais visualizados]
* Métricas de relatório do produto (se você estiver usando o Adobe Analytics)

#### Onde usar em seu site

* Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

### Itens visualizados recentemente   {#recently-viewed}

Use o histórico do visitante (abrangendo sessões) para apresentes os últimos *x* itens que o visitante viu, baseado no número de slots no design.

Os critérios de Itens visualizados recentemente retornam resultados específicos para um determinado [ambiente](/help/administrating-target/hosts.md). Se dois sites pertencerem a ambientes diferentes e um visitante alternar entre os dois sites, cada site exibirá somente itens visualizados recentemente do site em questão. Caso dois sites estejam no mesmo ambiente e um visitante alternar entre eles, ele verá os mesmos itens visualizados recentemente em ambos os sites.

>[!NOTE]
>
>Não é possível usar os critérios [!UICONTROL Itens visualizados recentemente] para recomendações de backup.

Os itens/mídias visualizados recentemente agora podem ser filtrados para que somente os itens com um determinado atributo sejam exibidos.

* Os critérios visualizados recentemente são configuráveis, exatamente como os outros critérios nas recomendações.
* Você pode utilizar [coleções](/help/c-recommendations/c-products/collections.md), [exclusões](/help/c-recommendations/c-products/exclusions.md) e [inclusões](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) (incluindo as regras especiais para Preço e Inventário) da mesma forma que os outros critérios.

Os possíveis casos de uso incluem:

Uma empresa multinacional com diversas empresas pode ter itens de exibição de visitantes em várias propriedades digitais. Nesse caso, é possível limitar os itens exibidos recentemente somente àqueles da respectiva propriedade em que foram visualizados. Isso impede que os itens visualizados recentemente sejam exibidos no site de outra propriedade digital.

#### Onde usar em seu site

* Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

>[!NOTE]
>
>[!UICONTROL Os ] Itens visualizados recentemente respeitam as configurações globais de exclusões e a configuração de coleção selecionada para a atividade. Se um item for excluído por uma exclusão global ou não estiver contido na coleção selecionada, ele não será exibido. Portanto, ao usar um critério [!UICONTROL Itens visualizados recentemente], a configuração &quot;Todas as coleções&quot; geralmente deve ser usada.

## Lógica da recomendação

O [!DNL Target Recommendations] usa algoritmos sofisticados para determinar quando as ações de um visitante se qualificam para os critérios definidos na sua atividade. A chave de recomendação determina as opções de lógica de recomendação disponíveis.

A seguinte lógica de recomendação (critérios) está disponível na lista suspensa [!UICONTROL Lógica de Recomendação]:

### Itens/Mídia com atributos semelhantes {#similar-attributes}

Recomenda itens ou mídias semelhantes a itens ou mídias baseados na atividade da página atual ou no comportamento passado do visitante.

Se você selecionar Itens/Mídia com atributos semelhantes, terá a opção de definir regras de similaridade de conteúdo.

O uso da similaridade de conteúdo para gerar recomendações é especialmente eficaz para novos itens, que provavelmente não serão exibidos nas recomendações usando Pessoas que visualizaram isso, viram aquilo e outras lógicas com base no comportamento anterior. Você também pode usar similaridade de conteúdo para gerar recomendações úteis para novos visitantes, que não possuem compras antigas ou outros dados de histórico.

Para obter mais informações, consulte [Semelhança de conteúdo](/help/c-recommendations/c-algorithms/create-new-algorithm.md#similarity).

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Item Atual
* Último Item Comprado
* Último item visualizado
* Item Mais Visualizado

### Mais visualizados {#most-viewed-logic}

Exibe os itens ou mídias visualizados com mais frequência no site.

Essa lógica permite que você exiba recomendações com base nos itens mais visualizados do site para aumentar as conversões de outros itens. Por exemplo, um site de mídia pode exibir recomendações em seu home page para seus vídeos mais visualizados, a fim de incentivar visitantes a assistir a vídeos adicionais.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Categoria Atual
* Atributo personalizado 
* Categoria favorita
* Popularidade

### Pessoas que compraram isto, compraram aquilo {#bought-bought}

Recomenda os itens que são comprados com mais frequência pelos clientes ao mesmo tempo que o item especificado.

Esta lógica retorna outros produtos que as pessoas compraram depois de comprarem este; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada exibindo uma recomendação em uma página de resumo do carrinho de compras, por exemplo, que exibe itens que outros compradores também compraram. Por exemplo, se o visitante estiver comprando um terno, a recomendação poderá exibir itens adicionais que outros visitantes compraram junto com o terno, como gravatas, sapatos de vestimenta e caixotes. À medida que os visitantes revisam suas compras, você fornece recomendações adicionais.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Item Atual
* Atributo personalizado 
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que visualizaram isto, compraram aquilo {#viewed-bought}

Recomenda itens visualizados que são comprados com mais frequência na mesma sessão em que o item especificado é visualizado. Este critério retorna outros produtos que pessoas compraram depois de ver este, o produto especificado não é incluído nos resultados.

Essa lógica retorna outros produtos que as pessoas compraram depois de ver este; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite aumentar as oportunidades de venda cruzada exibindo uma recomendação em uma página de produto, por exemplo, que exibe itens que outros visitantes visualizaram o item comprado. Por exemplo, se o visitante estiver visualizando uma haste de pesca, a recomendação poderá mostrar itens adicionais que outros visitantes compraram, como caixas de ataque, panelas e lures de pesca. À medida que os visitantes navegam pelo seu site, você fornece recomendações de compra adicionais.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Item Atual
* Atributo personalizado 
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Pessoas que visualizaram isto, visualizaram aquilo {#viewed-viewed}

Recomenda itens visualizados com mais frequência na mesma sessão em que o item especificado é visualizado.

Esta lógica retorna outros produtos que as pessoas visualizaram depois de ver este; o produto especificado não está incluído no conjunto de resultados.

Essa lógica permite criar oportunidades de conversão adicionais recomendando itens que outros visitantes que visualizaram um item também visualizaram. Por exemplo, visitantes que visualizações bicicletas de estrada em seu site também podem olhar para capacetes de bicicleta, kits de ciclismo, fechaduras e assim por diante. Você pode criar uma recomendação usando essa lógica que sugere outros produtos para ajudá-lo a aumentar a receita.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Item Atual
* Atributo personalizado 
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Afinidade do site {#site-affinity}

Recomenda itens com base na certeza de uma relação entre os itens. Você pode configurar esses critérios para determinar quantos dados são exigidos antes de uma recomendação ser apresentada usando o controle deslizante Regras de inclusão. Por exemplo, se você selecionar muito forte, serão recomendados os produtos com maior certeza de correspondência.

Por exemplo, se você definir uma afinidade muito forte e seu design incluir cinco itens, três dos quais alcançam o limite de força de conexão, os dois itens que não alcançarem os requisitos mínimos de força não serão exibidos nas recomendações e serão substituídos por seus itens de backup definidos. Os itens com a maior afinidade são exibidos primeiro.

Por exemplo, um varejista online pode recomendar itens em visitas subsequentes nos quais um visitante tenha mostrado interesse durante sessões passadas. A atividade de cada sessão de visitante é capturada para calcular uma afinidade com base em um modelo de recenticidade e frequência. Conforme esse visitante retorna ao seu site, a afinidade do site é usada para exibir recomendações com base em ações passadas no seu site.

Alguns clientes com coleções de produtos e comportamento do site diversos poderão obter melhores resultados caso definam uma afinidade do site fraca.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado

### Mais vendidos {#top-sellers}

Exibe os itens incluídos nas ordens mais concluídas. Várias unidades do mesmo item em um único pedido são contadas como um pedido.

Essa lógica permite que você crie recomendações para itens mais vendidos no seu site para aumentar a conversão e a receita. Essa lógica é especialmente adequada para visitantes pela primeira vez do site.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Categoria favorita
* Popularidade

### Recommendations baseado no usuário {#user-based}

Recomenda itens com base em cada histórico de navegação, exibição e compra de visitantes. Esses itens são geralmente chamados de &quot;Recomendado para você&quot;.

Esse critério permite que você forneça conteúdo e experiências personalizadas para visitantes novos e recorrentes. A lista de recomendações é ponderada em relação à atividade mais recente do visitante, é atualizada em sessão e se torna mais personalizada à medida que o usuário navega em seu site.

As visualizações e compras são usadas para determinar os itens recomendados. A chave de recomendação especificada (por exemplo, Item atual) é usada para aplicar qualquer filtros de regra de inclusão selecionado.

Por exemplo, você pode:

* Exclua itens que não atendem a determinados critérios (produtos esgotados, artigos publicados há mais de 30 dias, filmes com classificação R etc.).
* Limitar itens incluídos a uma única categoria ou à categoria atual.

Essa lógica pode ser usada com as seguintes chaves de recomendação:

* Item Atual
* Último item comprado
* Último item visualizado
* Item Mais Visualizado