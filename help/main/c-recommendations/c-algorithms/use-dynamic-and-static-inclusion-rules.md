---
keywords: regras de inclusão, critérios de inclusão, recomendações, criar novos critérios, promoção, promoções, filtragem dinâmica, dinâmica, valores em branco, ignorar regra de filtragem, filtro estático, filtrar por valor, correspondência de atributos de entidade, correspondência de atributos de perfil, correspondência de parâmetros, filtrar por valor, filtro estático
description: Saiba como criar regras de inclusão no Adobe [!DNL Target] Recommendations para critérios e promoções. Para obter melhores resultados, adicione regras de filtragem mais dinâmicas ou estáticas.
title: Como usar as regras de inclusão estática e dinâmica no Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '2093'
ht-degree: 16%

---

# Uso das regras de inclusão estática e dinâmica

Informações sobre como criar regras de inclusão para critérios e promoções no [!DNL Adobe Target] e adicionar regras de filtragem dinâmicas ou estáticas para obter melhores resultados para suas recomendações.

O processo para criar e usar regras de inclusão para critérios e promoções é semelhante, assim como os casos de uso e exemplos. Os critérios e as promoções e o uso das regras de inclusão são abordados nesta seção.

## Adicionar regras de filtragem aos critérios {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Ao [criar um critério](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), clique em **[!UICONTROL Adicionar regra de filtragem]** em **[!UICONTROL Regras de inclusão]**.

![inclusion_options_new imagem](assets/inclusion_options_new.png)

As opções disponíveis variam, dependendo do vertical do setor selecionado e da chave de recomendação.

## Adicionar regras de filtragem às promoções  {#section_D59AFB62E2EE423086281CF5D18B1076}

Ao [criar uma promoção](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), selecione **[!UICONTROL Promover por atributo]** e clique em **[!UICONTROL Adicionar regra de filtragem]**.

![imagem inclusion_options](assets/inclusion_options.png)

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

As seções a seguir listam os tipos de opções de filtro para [!UICONTROL Filtragem dinâmica] e [!UICONTROL Filtrar por valor] para critérios e promoções:

### Filtragem dinâmica

As regras de inclusão dinâmica são mais poderosas do que as regras de inclusão estática e geram melhores resultados e envolvimento. Considere o seguinte:

* As regras de inclusão dinâmica fornecem recomendações ao corresponder um atributo em um parâmetro de perfil do usuário ou em uma chamada de mbox.

   Por exemplo, você pode criar uma recomendação de &quot;Critérios mais populares&quot;. No conjunto de recomendações retornadas, você pode filtrar qualquer recomendação (em tempo real) em relação a um atributo transmitido quando o usuário acessa uma página em que as recomendações são exibidas.

* Use regras estáticas para limitar quais itens são incluídos na recomendação (em vez de usar coleções).

* É possível criar quantas regras de inclusão dinâmica forem necessárias. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

As seguintes opções estão disponíveis para a filtragem dinâmica:

| Opção de filtragem dinâmica | Detalhes |
| --- | --- |
| [Correspondência de atributos de entidade](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinamicamente comparando um pool de itens de recomendações em potencial a um item específico com o qual os usuários interagiram.<br>Uso [!UICONTROL Correspondência de atributos de entidade] quando quiser mostrar recomendações com maior probabilidade de atrair o visitante, como a marca favorita do visitante. |
| [Correspondência de atributos de perfil](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinamicamente comparando itens (entidades) com um valor no perfil do usuário.<br>Uso [!UICONTROL Correspondência de atributo de perfil] quando quiser mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita. |
| [Correspondência de parâmetros](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).<br>Uso [!UICONTROL Correspondência de parâmetros] para recomendar o conteúdo que corresponda aos parâmetros da página ou aos parâmetros do visitante, como dimensões do dispositivo ou localização geográfica. |

### Filtrar por valor

A seguinte opção está disponível para filtrar por valor:

| Filtrar por opção de valor | Detalhes |
| --- | --- |
| [Filtro estático](/help/main/c-recommendations/c-algorithms/static-value.md) | Insira manualmente um ou mais valores estáticos para filtrar. |

## Operadores disponíveis {#operators}

Os critérios e promoções dinâmicos são muito mais eficientes do que os critérios e promoções estáticos e geram melhores resultados e engajamento.

Os exemplos a seguir fornecem ideias gerais sobre como usar promoções e exclusões dinâmicas em seus esforços de marketing:

| Operador | Exemplos |
| --- | --- |
| Igual a<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil, Correspondência de parâmetros e Filtro estático.) | Usando o operador &quot;equals&quot; em promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens de:<ul><li>A mesma marca</li><li>A mesma categoria</li><li>A mesma categoria E da marca própria</li><li>A mesma loja</li></ul> |
| Não é igual<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil, Correspondência de parâmetros e Filtro estático.) | Usando o operador &quot;não é igual&quot; em promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens de:<ul><li>Uma série de TV diferente</li><li>Um gênero diferente</li><li>Uma série de produtos diferente</li><li>Uma ID de estilo diferente</li></ul> |
| Não Contém Subcadeia De Caracteres<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil, Correspondência de parâmetros e Filtro estático.) | Usando o operador &quot;não contém substring&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>O título não contém uma palavra não jurada</li></ul> |
| Começa com<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil, Correspondência de parâmetros e Filtro estático.) | Usando o operador &quot;inicia com&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>O nome do produto começa com iPhone</li></ul> |
| Termina com<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil, Correspondência de parâmetros e Filtro estático.) | Usando o operador &quot;termina com&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>O conteúdo termina com EN, que indica inglês</li></ul> |
| É maior que ou igual a<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil, Correspondência de parâmetros e Filtro estático.) | Usando o operador &quot;é maior que ou igual a&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>Custa o mesmo ou é mais caro</li></ul> |
| É menor que ou igual a<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil, Correspondência de parâmetros e Filtro estático.) | Usando o operador &quot;é menor que ou igual a&quot;, quando um visitante visualizar um item no seu site (como um produto), será possível promover outros itens que:<ul><li>Custa o mesmo ou é mais barato</li><li>Excluir itens mais baratos</li></ul> |
| Está entre<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil e Correspondência de parâmetros.) | Usando o operador &quot;is between&quot; nas promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens que sejam:<ul><li>Mais caro</li><li>Mais barato</li><li>Custo mais ou menos 30%</li><li>Episódios posteriores na mesma temporada</li><li>Livros anteriores em uma série</li></ul> |
| Está contido na lista<br>(Disponível com Correspondência de atributos de perfil e Correspondência de parâmetros.) | Usando o operador &quot;está contido na lista&quot; na correspondência de atributos de perfil, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens que sejam:<ul><li>Disponível na geografia do visitante</li></ul>**Exemplo**: você deseja recomendar somente itens que estejam disponíveis na área geográfica de um visitante.<br>A regra de filtro pode ter esta aparência:<br>`availableGeographies list contains an item in user.currentGeography`<br>**Nota**: ao usar esse operador, uma lista é esperada no [lado direito](#caveats) da regra. |
| Não está contido na lista<br>(Disponível com Correspondência de atributos de perfil e Correspondência de parâmetros.) | Usando o operador &quot;não consta na lista&quot; na correspondência de atributos de perfil, quando um visitante visualiza um item no seu site (como um produto, artigo ou filme), é possível excluir outros itens que são:<ul><li>Na lista dos últimos dez itens que o visitante visualizou</li></ul></ul>**Exemplo**: não é possível promover itens que o visitante visualizou recentemente e nos quais não mostrou interesse.<br>Sua regra de filtragem pode ser semelhante a:<br>`id is not contained in list user.lastViewedItems`<br>**Nota**: ao usar esse operador, uma lista é esperada no [lado direito](#caveats) da regra. |
| A lista contém um item em<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil e Correspondência de parâmetros.) | Usando o operador &quot;lista contém um item em&quot; na correspondência do atributo de perfil, quando um visitante visualizar um item no seu site (como um evento esportivo ou concerto), será possível promover outros itens que sejam:<ul><li>Associado a uma das equipes favoritas do visitante</li></ul>**Exemplo**: você deseja recomendar jogos que estejam associados a uma das equipes favoritas do visitante.<br>Sua regra de filtragem pode ser semelhante a:<br>` teamsPlaying list contains an item in user.favoriteTeams`<br>**Nota**: ao usar esse operador, uma lista é esperada no [ambos os lados](#caveats) da regra. |
| A lista não contém um item em<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil e Correspondência de parâmetros.) | Usando o operador &quot;lista não contém um item em&quot; na correspondência de atributos de parâmetro, quando um visitante visualiza um item no seu site (como um produto, artigo ou filme), é possível excluir outros itens que são:<ul><li>Contido em uma lista de tipos proibidos</li></ul>**Exemplo**: você deseja excluir itens que estão disponíveis para visitantes que são adultos, como cigarro e álcool.<br>Sua regra de filtragem pode ser semelhante a:<br>`itemType is not contained in list mbox.prohibitedTypes`<br>**Nota**: ao usar esse operador, uma lista é esperada no [ambos os lados](#caveats) da regra. |
| A lista contém todos os itens em<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil e Correspondência de parâmetros.) | Usando o operador &quot;lista contém todos os itens em&quot; na correspondência do atributo de perfil, quando um visitante visualiza um item no seu site (como uma publicação de trabalho ou fórmula), é possível promover outros itens que:<ul><li>Incluir um conjunto de habilidades</li><li>Incluir um conjunto de ingredientes necessários</li></ul>**Exemplo 1**: suponha que um visitante tenha um conjunto de habilidades (Java, C++ e HTML). Os itens no catálogo são trabalhos com as habilidades necessárias (Java e HTML). Verifique se o perfil do visitante contém todas as habilidades necessárias antes de recomendar o trabalho ao visitante.<br>Sua regra de filtragem pode ser semelhante a:<br>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<br>**Exemplo 2**: Suponha que um usuário tenha uma lista de ingredientes de despensa. A receita tem uma lista de ingredientes necessários. Você deseja garantir que o perfil do visitante contenha todos os ingredientes necessários antes de recomendar a receita ao visitante.<br>Sua regra de filtragem pode ser semelhante a:<br>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<br>**Nota**: ao usar esse operador, uma lista é esperada no [ambos os lados](#caveats) da regra. |
| A lista não contém todos os itens em<br>(Disponível com Correspondência de atributos de entidade, Correspondência de atributos de perfil e Correspondência de parâmetros.) | Usando o operador &quot;lista não contém todos os itens em&quot; na correspondência do atributo de entidade, quando um visitante visualizar um item no seu site (como evento esportivo ou concerto), será possível promover outros itens que:<ul><li>Não inclua um conjunto de equipes</li></ul>**Exemplo**: Suponha que um evento esportivo inclua duas equipes. O perfil do visitante indica que ele não deseja exibir jogos para essas equipes. Você deseja garantir que não recomende um jogo se essas equipes estiverem jogando.<br>Sua regra de filtragem pode ser semelhante a:<br>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<br>**Nota**: ao usar esse operador, uma lista é esperada no [ambos os lados](#caveats) da regra. |

## Lidar com valores em branco ao filtrar por Correspondência de atributos de entidade, Correspondência de atributos de perfil e Correspondência de parâmetros {#section_7D30E04116DB47BEA6FF840A3424A4C8}

É possível escolher várias opções para lidar com valores vazios ao filtrar por [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributo de perfil], e [!UICONTROL Correspondência de parâmetros] para critérios e promoções de saída.

Anteriormente, nenhum resultado era retornado se um valor estivesse em branco. A lista suspensa &quot;se *x* estiver em branco&quot; permite escolher a ação apropriada a ser executada se o critério tiver valores em branco, conforme mostrado na ilustração a seguir:

![imagem empty_value](assets/empty_value.png)

Para selecionar a ação desejada, passe o mouse sobre o ícone de engrenagem (![imagem icon_gear](assets/icon_gear.png)) e escolha a ação desejada:

| Ação | Disponível para | Detalhes |
|--- |--- |--- |
| [!UICONTROL Ignorar esta regra de filtragem] | [!UICONTROL Correspondência de atributo de perfil] e [!UICONTROL Correspondência de parâmetros] | Esta ação é o padrão para [!UICONTROL Correspondência de atributo de perfil] e [!UICONTROL Correspondência de parâmetros].<br>Esta opção especifica que a regra será ignorada. Por exemplo, se houver três regras de filtragem e a terceira regra não passar nenhum valor, em vez de não retornar nenhum resultado, você poderá simplesmente ignorar a terceira regra com os valores em branco. |
| [!UICONTROL Não mostrar nenhum resultado para este critério]<br>(Somente critérios) | [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributo de perfil], e [!UICONTROL Correspondência de parâmetros] | Esta ação é o padrão para [!UICONTROL Correspondência de atributos de entidade].<br>Esta ação é a forma como [!DNL Target] valores vazios tratados antes da adição desta opção: nenhum resultado é mostrado para este critério. |
| [!UICONTROL Não promover itens<br>(Somente promoções)] | [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributo de perfil], e [!UICONTROL Correspondência de parâmetros] | Esta ação é o padrão para [!UICONTROL Correspondência de atributos de entidade].<br>Esta ação é a forma como [!DNL Target] valores vazios tratados antes da adição desta opção: nenhum resultado é mostrado para este critério. |
| [!UICONTROL Usar um valor estático] | [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributo de perfil], e [!UICONTROL Correspondência de parâmetros] | Se um valor estiver em branco, você poderá optar por usar um valor estático. |

## Avisos {#caveats}

>[!IMPORTANT]
>
>Atributos de tipo de dados diferentes podem não ser compatíveis em critérios ou promoções dinâmicas durante o tempo de execução com os operadores “é igual a” e “não é igual a”. Uso [!UICONTROL Valor], [!UICONTROL Margem], [!UICONTROL Inventário], e [!UICONTROL Ambiente] valores sabiamente no lado direito se o lado esquerdo tiver atributos predefinidos ou personalizados.

![imagem left_right](assets/left_right.png)

A tabela a seguir mostra regras em vigor e regras que podem não ser compatíveis durante o tempo de execução:

| Regras compatíveis | Regras Potencialmente Incompatíveis |
|--- |--- |
| valor - está entre - 90% e 110% do item atual - salesValue | salesValue - está entre - 90% e 110% do item atual - valor |
| valor - está entre - 90% e 110% do item atual - valor | clearancePrice - está entre - 90% e 110% do item atual - margem |
| margem - está entre - 90% e 110% do item atual - margem | storeInventory - é igual a - item atual - inventário |
| inventário - igual a - item atual - inventário |  |
