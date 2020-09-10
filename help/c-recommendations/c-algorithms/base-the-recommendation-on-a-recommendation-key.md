---
keywords: recommendation key;recommendation logic;current category;custom attribute;last purchased item;last viewed item;most viewed item;most viewed item;favorite category;popularity;recently viewed item;last purchased;last viewed;most viewed;favorite;recently viewed
description: O Recommendations baseado em chaves utiliza o contexto de comportamento do visitante para mostrar resultados relevantes no Adobe Target Recommendations atividade.
title: Basear a recomendação em uma chave de recomendação
feature: criteria
mini-toc-levels: 2
translation-type: tm+mt
source-git-commit: 00749d54d0416c57364ff648bd0911e636c84bc7
workflow-type: tm+mt
source-wordcount: '1452'
ht-degree: 97%

---


# Basear a recomendação em uma chave de recomendação

Recommendations based on keys utilize visitor behavior context to show relevant results in [!DNL Adobe Target] [!DNL Recommendations] activities.

Há dois tipos de recomendações:

* **Popularidade:** lista itens de acordo com mais visualizados, mais vendidos e métricas principais. A chave fica vazia para critérios de popularidade.
* **Baseado em chave:** inclui o resto dos critérios. Recommendations oferecem um conjunto diverso de escolhas a respeito do tipo de chave. As opções vão desde &quot;item atual&quot; até &quot;parâmetros de perfil&quot;, que permitem que você defina programaticamente as chaves dos valores para recomendar. Você pode testar vários critérios uns em relação aos outros baseando cada critério em uma chave diferente.

Cada critério é definido em sua própria guia. O tráfego é dividido uniformemente entre os diferentes testes de critérios. Em outras palavras, se você tem dois critérios, o tráfego é dividido igualmente entre eles. Se você tem dois critérios e dois designs, o tráfego é dividido igualmente entre as quatro combinações. Também é possível especificar uma porcentagem de visitantes do site que veem o conteúdo padrão, para comparação. Nesse caso, o percentual especificado de visitantes acompanha o conteúdo padrão e o restante é dividido entre os seus critérios e combinações de design.

1. Crie uma nova recomendação ou selecione uma recomendação existente e clique em **[!UICONTROL Editar]**.
1. Para alterar a chave de recomendação, selecione a nova chave na lista suspensa [!UICONTROL Chave de recomendação] e clique em **[!UICONTROL Salvar]**.

   Como lógicas diferentes levam a chaves de recomendações diferentes, recomendações diferentes se apresentam para localização em diferentes tipos de páginas. Consulte as seções a seguir para obter mais informações sobre cada chave.

## Item Atual

A recomendação é determinada pelo item que o visitante está vendo atualmente.

As recomendações exibem outros itens que possam interessar o visitante que está interessado no item especificado.

Quando essa opção é selecionada, o valor `entity.id` deve ser passado como parâmetro na mbox de exibição.

### Lógica (critério)

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

### Onde usar em seu site

Páginas de item único, como páginas de produtos.

NÃO use em páginas de resultados de busca nulos.

## Categoria Atual

A recomendação é determinada pela categoria de produto que o visitante está vendo atualmente.

As recomendações exibem itens na categoria de produto especificada.

Quando essa opção é selecionada, o valor `entity.categoryId` deve ser passado como parâmetro para a mbox de exibição.

### Lógica (critério)

* Mais vendidos
* Mais visualizados

### Onde usar em seu site

Páginas de categoria única.

NÃO use em páginas de resultados de busca nulos.

## Atributo personalizado  {#custom}

Recomendação determinada por um item que é armazenado no perfil do visitante, utilizando os atributos usuário.*x* ou perfil.*x* atributos.

Quando esta opção é selecionada, o valor `entity.id` deve estar presente no atributo do perfil.

### Lógica (critério)

* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Comportamento geral]
* [!UICONTROL Mais visualizados]
* [!UICONTROL Mais vendidos]

Se a chave é um atributo personalizado do perfil e o tipo de algoritmo é Mais visualizados ou Mais vendidos, uma nova lista suspensa que mostra o chamado &quot;Agrupado pelo valor único de&quot; que tem uma lista de atributos de entidade conhecidos (exceto ID, categoria, margem, valor, inventário e ambiente). Esse campo é obrigatório.

### Onde usar em seu site

Pode ser usado em qualquer página.

### Usar uma chave de recomendações personalizada

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

## Último item comprado

A recomendação é determinada pelo último item comprado por cada visitante único. Ela é capturada automaticamente, assim nenhum valor precisa ser aprovado na página.

### Lógica (critério)

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

### Onde usar em seu site

Página inicial, página minha conta, anúncios em outros sites.

NÃO use nas páginas do produto ou páginas relevantes para compras.

## Último item visualizado

A recomendação é determinada pelo último item visto por cada visitante único. Ela é capturada automaticamente, assim nenhum valor precisa ser aprovado na página.

### Lógica (critério)

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

### Onde usar em seu site

Página inicial, página minha conta, anúncios em outros sites.

NÃO use nas páginas do produto ou páginas relevantes para compras.

## Item Mais Visualizado

A recomendação é determinada pelo item visto com mais frequência, usando o mesmo método utilizado para a categoria de favoritos.

Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de produto
* 5 pontos para cada visualização seguinte
* No fim da sessão, divida todos os valores por 2

Por exemplo, visualizar a prancha_de_surfe_A e depois a prancha_de_surfe_B em uma sessão resulta em A: 10, B: 5. Quando a sessão é encerrada, você tem A: 5, B: 2,5. Se você exibir os mesmos itens na sessão seguinte, os valores vão mudar para A: 15 B: 7,5.

### Lógica (critério)

* [!UICONTROL Itens com atributos similares]
* [!UICONTROL Pessoas que visualizaram isto, visualizaram aquilo]
* [!UICONTROL Pessoas que visualizaram isto, compraram aquilo]
* [!UICONTROL Pessoas que compraram isto, compraram aquilo]
* [!UICONTROL Afinidade do site]

### Onde usar em seu site

Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

## Categoria favorita

A recomendação é determinada pela categoria que recebeu a mais atividade, utilizando o mesmo método usado para &quot;item mais visto&quot;, exceto que as categorias são classificadas, em vez de os produtos.

Isso é determinado pelos critérios de recenticidade/frequência que funciona da seguinte maneira:

* 10 pontos para primeira visualização de categoria
* 5 pontos para cada visualização seguinte

Categorias visitadas pela primeira vez recebem 10 pontos. 5 pontos são dados para visitas seguintes para a mesma categoria. Com cada visita, categorias não atuais que foram vistas anteriormente são diminuídas em 1.

Por exemplo, a visualização da categoria A e da categoria B em uma sessão resulta em A: 9, B: 10. Se você viu os mesmos itens na próxima sessão, os valores mudam para A: 20, B: 9.

### Lógica (critério)

* [!UICONTROL Mais vendidos]
* [!UICONTROL Mais visualizados]

### Onde usar em seu site

Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

## Popularidade

A recomendação é determinada pela popularidade de itens em seu site. A popularidade inclui os principais vendedores e os mais visualizados por dados de mbox e, se você utilizar o Adobe Analytics, todas as métricas disponíveis no relatório do produto. Itens são classificados de acordo com a lógica de recomendação que você selecionou.

### Lógica (critério)

* [!UICONTROL Mais vendidos]
* [!UICONTROL Mais visualizados]
* Métricas de relatório do produto (se você estiver usando o Adobe Analytics)

### Onde usar em seu site

Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

## Itens visualizados recentemente  {#recently-viewed}

Use o histórico do visitante (abrangendo sessões) para apresentes os últimos *x* itens que o visitante viu, baseado no número de slots no design.

O critério Itens visualizados recentemente agora retorna resultados específicos a um certo [ambiente](/help/administrating-target/hosts.md). Se dois sites pertencerem a ambientes diferentes e um visitante alternar entre os dois sites, cada site exibirá somente itens visualizados recentemente do site em questão. Caso dois sites estejam no mesmo ambiente e um visitante alternar entre eles, ele verá os mesmos itens visualizados recentemente em ambos os sites.

### Onde usar em seu site

Páginas gerais, como página inicial ou de aterrissagem e anúncios em outros sites.

>[!NOTE]
>
>Os Itens visualizados recentemente respeitam as configurações globais de Exclusões e a configuração de Coleção selecionada para a Atividade. Se um item for excluído por uma Exclusão global ou não fizer parte da Coleção selecionada, ele não será exibido; portanto, ao usar um critério de Itens visualizados recentemente, a configuração “Todas as coleções” geralmente deve ser usada.