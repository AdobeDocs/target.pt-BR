---
keywords: regras de inclusão, critérios de inclusão, recomendações, criar novos critérios, promoção, promoções, filtragem dinâmica, dinâmica, valores em branco, ignorar regra de filtragem, filtro estático, filtrar por valor, correspondência de atributos de entidade, correspondência de atributos de perfil, correspondência de parâmetros, filtrar por valor, filtro estático
description: Saiba como criar regras de inclusão no [!DNL Target] Recommendations para critérios e promoções.
title: Como usar as regras de inclusão estática e dinâmica no Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
TQID: https://experienceleague.adobe.com/PM9h863-uQWm3wrU7OVWfmnqQgyUGmF7QFpTUaAZuCQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 2258
ht-degree: 14%

---

# Uso das regras de inclusão estática e dinâmica

Crie regras de inclusão para critérios e promoções em [!DNL Adobe Target] e adicione regras de filtragem dinâmicas ou estáticas para obter melhores resultados para suas recomendações.

O processo para criar e usar regras de inclusão para critérios e promoções é semelhante, assim como os casos de uso e exemplos. Os critérios e as promoções e o uso das regras de inclusão são abordados nesta seção.

## Adicionar regras de filtragem a critérios e promoções {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

As seguintes seções contêm mais informações:

### Adicionar regras de filtragem aos critérios

1. Ao [criar critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) (**[!UICONTROL Recommendations] > [!UICONTROL Critérios] > [!UICONTROL Criar critérios] > [!UICONTROL Criar critérios]**), clique em **[!UICONTROL Adicionar regra de filtragem]** em **[!UICONTROL Regras de inclusão]**.

   ![Adicionar Regra de Filtragem](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. Clique na lista suspensa **Filtro Estático** na caixa &quot;A que outras regras a recomendação deve obedecer&quot; e escolha a opção desejada na lista suspensa [!UICONTROL Filtro Estático].

   ![Lista suspensa de Filtro Estático](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   As opções disponíveis variam, dependendo do vertical do setor selecionado e da chave de recomendação.

### Adicionar regras de filtragem às promoções

1. Ao [criar uma promoção](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), selecione **[!UICONTROL Promover por atributo]** e clique em **[!UICONTROL Adicionar regra de filtragem]**.

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

As seções a seguir listam os tipos de opções de filtragem para [!UICONTROL Filtragem Dinâmica] e [!UICONTROL Filtrar por Valor] para critérios e promoções:

### Filtragem dinâmica

As regras de inclusão dinâmica são mais poderosas do que as regras de inclusão estática e geram melhores resultados e envolvimento. Considere o seguinte:

* As regras de inclusão dinâmica fornecem recomendações ao corresponder um atributo em um parâmetro de perfil do usuário ou em uma chamada de mbox.

  Por exemplo, você pode criar uma recomendação de &quot;Critérios mais populares&quot;. No conjunto de recomendações retornadas, você pode filtrar qualquer recomendação (em tempo real) em relação a um atributo transmitido quando o usuário acessa uma página em que as recomendações são exibidas.

* Use regras estáticas para limitar quais itens são incluídos na recomendação (em vez de usar coleções).

* É possível criar quantas regras de inclusão dinâmica forem necessárias. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

As seguintes opções estão disponíveis para a filtragem dinâmica:

| Opção de filtragem dinâmica | Detalhes |
| --- | --- |
| [[!UICONTROL Correspondência de atributos de entidade]](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinamicamente comparando um pool de itens de recomendações em potencial a um item específico com o qual os usuários interagiram.<P>Use a [!UICONTROL Correspondência de atributos de entidade] quando quiser mostrar recomendações com maior probabilidade de atrair o visitante, como a marca favorita do visitante. |
| [[!UICONTROL Correspondência de atributos de perfil]](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinamicamente comparando itens (entidades) com um valor no perfil do usuário.<P>Use a [!UICONTROL Correspondência de atributos de perfil] quando quiser mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita. |
| [[!UICONTROL Correspondência de parâmetros]](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).<P>Use a [!UICONTROL Correspondência de Parâmetros] para recomendar o conteúdo que corresponda aos parâmetros da página ou aos parâmetros do visitante, como dimensões de dispositivo ou localização geográfica. |

### Filtrar por valor

A seguinte opção está disponível para filtrar por valor:

| Filtrar por opção de valor | Detalhes |
| --- | --- |
| [[!UICONTROL Filtro estático]](/help/main/c-recommendations/c-algorithms/static-value.md) | Insira manualmente um ou mais valores estáticos para filtrar. |

## Operadores disponíveis {#operators}

Os critérios e promoções dinâmicos são muito mais eficientes do que os critérios e promoções estáticos e geram melhores resultados e engajamento.

Os exemplos a seguir fornecem ideias gerais sobre como usar promoções e exclusões dinâmicas em seus esforços de marketing:

>[!NOTE]
>
>&quot;List&quot; requer que entidades e atributos de perfil sejam armazenados como matrizes. Uma lista separada por vírgulas não funciona.

| Operador | Exemplos |
| --- | --- |
| [!UICONTROL é igual a qualquer um de]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil], [!UICONTROL Correspondência de parâmetros] e [!UICONTROL Filtro estático].) | Usando o operador &quot;equals&quot; em promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens de:<ul><li>A mesma marca</li><li>A mesma categoria</li><li>A mesma categoria E da marca própria</li><li>A mesma loja</li></ul> |
| [!UICONTROL não é igual a qualquer um de]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil], [!UICONTROL Correspondência de parâmetros] e [!UICONTROL Filtro estático].) | Usando o operador &quot;[!UICONTROL não é igual a nenhum dos]&quot; em promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens de:<ul><li>Uma série de TV diferente</li><li>Um gênero diferente</li><li>Uma série de produtos diferente</li><li>Uma ID de estilo diferente</li></ul> |
| [!UICONTROL é maior que ou igual a qualquer um de]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil], [!UICONTROL Correspondência de parâmetros] e [!UICONTROL Filtro estático].) | Usando o operador &quot;[!UICONTROL é maior que ou igual a qualquer um dos]&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>Custa o mesmo ou é mais caro</li></ul> |
| [!UICONTROL é menor que ou igual a qualquer um de]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil], [!UICONTROL Correspondência de parâmetros] e [!UICONTROL Filtro estático].) | Usando o operador &quot;[!UICONTROL is less than or equal to an of]&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>Custa o mesmo ou é mais barato</li><li>Excluir itens mais baratos</li></ul> |
| [!UICONTROL contém qualquer um de] (Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil], [!UICONTROL Correspondência de parâmetros] e [!UICONTROL Filtro estático].) | Usando o operador &quot;[!UICONTROL contém qualquer um de]&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>O título contém a mesma marca</li></ul> |
| [!UICONTROL não contém nenhum de]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil], [!UICONTROL Correspondência de parâmetros] e [!UICONTROL Filtro estático].) | Usando o operador &quot;não contém nenhum&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>O título não contém uma palavra não jurada</li></ul> |
| [!UICONTROL começa com qualquer um de]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil], [!UICONTROL Correspondência de parâmetros] e [!UICONTROL Filtro estático].) | Usando o operador &quot;[!UICONTROL começa com um de]&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>O nome do produto começa com iPhone</li></ul> |
| [!UICONTROL termina com qualquer um de]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil], [!UICONTROL Correspondência de parâmetros] e [!UICONTROL Filtro estático].) | Usando o operador &quot;[!UICONTROL termina com um de]&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>O conteúdo termina com EN, que indica inglês</li></ul> |
| [!UICONTROL está entre]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros].) | Usando o operador &quot;i[!UICONTROL s between]&quot; em promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens que sejam:<ul><li>Mais caro</li><li>Mais barato</li><li>Custo mais ou menos 30%</li><li>Episódios posteriores na mesma temporada</li><li>Livros anteriores em uma série</li></ul> |
| A lista [!UICONTROL contém um item em]<P>(Disponível com [!UICONTROL Correspondência de atributo de perfil] e [!UICONTROL Correspondência de parâmetro].) | Usando a lista &quot;[!UICONTROL contém um operador item em]&quot; na correspondência de atributos de perfil, quando um visitante está visualizando um item no seu site (como um produto, artigo ou filme), é possível promover outros itens que são:<ul><li>Disponível na geografia do visitante</li></ul>**Exemplo**: você deseja recomendar itens que estejam disponíveis somente na área geográfica de um visitante.<P>A regra de filtro pode ter esta aparência:<P>`availableGeographies list contains an item in user.currentGeography`<P>**Observação**: ao usar este operador, uma lista é esperada no [lado direito](#caveats) da regra. |
| [!UICONTROL a lista não contém um item em]<P>(Disponível com [!UICONTROL Correspondência de atributo de perfil] e [!UICONTROL Correspondência de parâmetro].) | Ao usar a lista &quot;[!UICONTROL não contém um item no operador &quot;]&quot; na correspondência de atributos de perfil, quando um visitante está visualizando um item no seu site (como um produto, artigo ou filme), é possível excluir outros itens que são:<ul><li>Na lista dos últimos dez itens que o visitante visualizou</li></ul></ul>**Exemplo**: você não deseja promover itens que o visitante visualizou recentemente e nos quais não mostrou interesse.<P>Sua regra de filtragem pode ser semelhante a:<P>`id is not contained in list user.lastViewedItems`<P>**Observação**: ao usar este operador, uma lista é esperada no [lado direito](#caveats) da regra. |
| A lista [!UICONTROL contém um item em]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros].) | Usando a lista &quot;[!UICONTROL contém um operador item em]&quot; na correspondência de atributos de perfil, quando um visitante está visualizando um item no seu site (como um evento esportivo ou concerto), é possível promover outros itens que são:<ul><li>Associado a uma das equipes favoritas do visitante</li></ul>**Exemplo**: você deseja recomendar jogos que estejam associados a uma das equipes favoritas do visitante.<P>Sua regra de filtragem pode ser semelhante a:<P>` teamsPlaying list contains an item in user.favoriteTeams`<P>**Observação**: ao usar este operador, uma lista é esperada em [ambos os lados](#caveats) da regra. |
| [!UICONTROL a lista não contém um item em]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros].) | Ao usar a lista &quot;[!UICONTROL não contém um item no operador &quot;]&quot; na correspondência de atributos de parâmetro, quando um visitante está visualizando um item no seu site (como um produto, artigo ou filme), é possível excluir outros itens que são:<ul><li>Contido em uma lista de tipos proibidos</li></ul>**Exemplo**: você deseja excluir itens que estejam disponíveis para visitantes que sejam adultos, como cigarro e álcool.<P>Sua regra de filtragem pode ser semelhante a:<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**Observação**: ao usar este operador, uma lista é esperada em [ambos os lados](#caveats) da regra. |
| A lista [!UICONTROL contém todos os itens em]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros].) | Ao usar a lista &quot;[!UICONTROL não contém um operador item em]&quot; na correspondência de atributos de perfil, quando um visitante está visualizando um item no seu site (como uma publicação de trabalho ou fórmula), é possível promover outros itens que:<ul><li>Incluir um conjunto de habilidades</li><li>Incluir um conjunto de ingredientes necessários</li></ul>**Exemplo 1**: suponha que um visitante tenha um conjunto de habilidades (Java, C++ e HTML). Os itens no catálogo são trabalhos com as habilidades necessárias (Java e HTML). Verifique se o perfil do visitante contém todas as habilidades necessárias antes de recomendar o trabalho ao visitante.<P>Sua regra de filtragem pode ser semelhante a:<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**Exemplo 2**: suponha que um usuário tenha uma lista de ingredientes de despensa. A receita tem uma lista de ingredientes necessários. Você deseja garantir que o perfil do visitante contenha todos os ingredientes necessários antes de recomendar a receita ao visitante.<P>Sua regra de filtragem pode ser semelhante a:<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**Observação**: ao usar este operador, uma lista é esperada em [ambos os lados](#caveats) da regra. |
| A lista [!UICONTROL não contém todos os itens em]<P>(Disponível com [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros].) | Ao usar a lista &quot;[!UICONTROL não contém todos os itens no operador &quot;]&quot; na correspondência de atributos de entidade, quando um visitante está visualizando um item no seu site (como um evento esportivo ou um concerto), é possível promover outros itens que:<ul><li>Não inclua um conjunto de equipes</li></ul>**Exemplo**: suponha que um evento esportivo inclua duas equipes. O perfil do visitante indica que ele não deseja exibir jogos para essas equipes. Você deseja garantir que não recomende um jogo se essas equipes estiverem jogando.<P>Sua regra de filtragem pode ser semelhante a:<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**Observação**: ao usar este operador, uma lista é esperada em [ambos os lados](#caveats) da regra. |

## Lidar com valores vazios ao filtrar por [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros] {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Você pode escolher várias opções para tratar valores vazios ao filtrar por [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros] para critérios e promoções de saída.

Anteriormente, nenhum resultado era retornado se um valor estivesse em branco. A lista suspensa &quot;se *x* estiver em branco&quot; permite escolher a ação apropriada a ser executada se o critério tiver valores em branco, conforme mostrado na ilustração a seguir:

![imagem de valor_vazio](assets/empty_value.png)

Para selecionar a ação desejada, passe o mouse sobre o ícone de engrenagem (![icon_gear image](assets/icon_gear.png)) e escolha a ação desejada:

| Ação | Disponível para | Detalhes |
|--- |--- |--- |
| [!UICONTROL Ignorar esta regra de filtragem] | [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros] | Esta ação é o padrão para [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros].<P>Esta opção especifica que a regra será ignorada. Por exemplo, se houver três regras de filtragem e a terceira regra não passar nenhum valor, em vez de não retornar nenhum resultado, você poderá simplesmente ignorar a terceira regra com os valores em branco. |
| [!UICONTROL Não mostrar nenhum resultado para este critério]<P>(Somente critérios) | [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros] | Esta ação é o padrão para [!UICONTROL Correspondência de atributos de entidade].<P>Esta ação é a forma como [!DNL Target] lidava com os valores em branco antes da adição desta opção: nenhum resultado é mostrado para este critério. |
| [!UICONTROL Não promover itens<P>(Somente promoções)] | [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros] | Esta ação é o padrão para [!UICONTROL Correspondência de atributos de entidade].<P>Esta ação é a forma como [!DNL Target] lidava com os valores em branco antes da adição desta opção: nenhum resultado é mostrado para este critério. |
| [!UICONTROL Usar um valor estático] | [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros] | Se um valor estiver em branco, você poderá optar por usar um valor estático. |

## Avisos {#caveats}

>[!IMPORTANT]
>
>Atributos de tipo de dados diferentes podem não ser compatíveis em critérios ou promoções dinâmicas durante o tempo de execução com os operadores “é igual a” e “não é igual a”. Use os valores de [!UICONTROL Valor], [!UICONTROL Margem], [!UICONTROL Inventário] e [!UICONTROL Ambiente] sabiamente no lado direito se o lado esquerdo tiver atributos predefinidos ou personalizados.

![imagem da esquerda_direita](assets/left_right.png)

A tabela a seguir mostra regras em vigor e regras que podem não ser compatíveis durante o tempo de execução:

| Regras compatíveis | Regras Potencialmente Incompatíveis |
|--- |--- |
| valor - está entre - 90% e 110% do item atual - salesValue | salesValue - está entre - 90% e 110% do item atual - valor |
| valor - está entre - 90% e 110% do item atual - valor | clearancePrice - está entre - 90% e 110% do item atual - margem |
| margem - está entre - 90% e 110% do item atual - margem | storeInventory - é igual a - item atual - inventário |
| inventário - igual a - item atual - inventário |  |
