---
keywords: regras de inclusão, critérios de inclusão, recomendações, criar novos critérios, promoção, promoções, filtragem dinâmica, dinâmica, valores em branco, ignorar regra de filtragem, filtro estático, filtrar por valor, correspondência de atributos de entidade, correspondência de atributos de perfil, correspondência de parâmetros, filtrar por valor, filtro estático
description: Saiba como criar regras de inclusão no [!DNL Target] Recommendations para critérios e promoções.
title: Uso das regras de inclusão estática e dinâmica
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
TQID: 'https://experienceleague.adobe.com/PM9h863-uQWm3wrU7OVWfmnqQgyUGmF7QFpTUaAZuCQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '2164'
ht-degree: 7%
---
# Uso das regras de inclusão estática e dinâmica {#inclusion-rules}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como adicionar regras de filtragem dinâmica e estática a critérios e promoções em [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

As regras de inclusão restringem os itens que podem aparecer nas recomendações. Eles são criados para critérios e promoções em [!DNL Adobe Target], com regras de filtragem dinâmicas ou estáticas. O processo, os casos de uso e os exemplos são semelhantes para critérios e promoções, portanto, esta página aborda ambos.

## Adicionar regras de filtragem {#add-filtering-rules}

As etapas a seguir adicionam uma regra de filtragem aos critérios.

1. Ao [criar critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#create-criteria) (**[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** > **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar critérios]**), clique em **[!UICONTROL Adicionar regra de filtragem]** em **[!UICONTROL Regras de inclusão]**.

   ![Adicionar Regra de Filtragem](/help/main/c-recommendations/c-algorithms/assets/add-fitering-rule.png)

1. Na caixa &quot;A recomendação deve obedecer a quais outras regras&quot;, clique na lista suspensa **[!UICONTROL Filtro estático]** e selecione a opção desejada.

   ![Lista suspensa de Filtro Estático](/help/main/c-recommendations/c-algorithms/assets/dynamic-and-static.png)

   As opções disponíveis variam, dependendo do vertical do setor selecionado e da chave de recomendação.

Para adicionar uma regra de filtragem a uma promoção, selecione **[!UICONTROL Promover por Atributo]** enquanto [cria a promoção](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md) e clique em **[!UICONTROL Adicionar Regra de Filtragem]**.

## Tipos de filtro {#filter-types}

As seções a seguir descrevem as opções de filtragem para **[!UICONTROL Filtragem Dinâmica]** e **[!UICONTROL Filtrar por Valor]**, tanto para critérios quanto para promoções.

### Filtragem dinâmica

As regras de inclusão dinâmica se adaptam ao visitante ou à solicitação, enquanto as regras de inclusão estática usam valores fixos.

* As regras de inclusão dinâmica fornecem recomendações ao corresponder um atributo em um parâmetro de perfil do usuário ou em uma chamada de mbox.

  Por exemplo, uma recomendação de &quot;Critérios mais populares&quot; pode ser criada. No conjunto de recomendações retornadas, qualquer recomendação pode ser filtrada (em tempo real) em relação a um atributo que é transmitido quando o usuário acessa uma página em que as recomendações são exibidas.

* É possível criar várias regras de inclusão dinâmica. As regras de inclusão são unidas com um operador AND, portanto, todas as regras devem ser atendidas para que um item seja incluído em uma recomendação.

As seguintes opções estão disponíveis para a filtragem dinâmica:

| Opção de filtragem dinâmica | Detalhes |
| --- | --- |
| [**[!UICONTROL Correspondência de atributos de entidade]**](/help/main/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtra dinamicamente comparando um pool de itens recomendados em potencial a um item específico com o qual o visitante interagiu.<P>Use a **[!UICONTROL Correspondência de atributos de entidade]** para mostrar recomendações com maior probabilidade de atrair o visitante, como a marca favorita do visitante. |
| [**[!UICONTROL Correspondência de atributos de perfil]**](/help/main/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtra dinamicamente comparando itens (entidades) com um valor no perfil do visitante.<P>Use a **[!UICONTROL Correspondência de atributos de perfil]** para mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita. |
| [**[!UICONTROL Correspondência de parâmetros]**](/help/main/c-recommendations/c-algorithms/parameter-matching.md) | Filtra dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).<P>Use a **[!UICONTROL Correspondência de Parâmetros]** para recomendar o conteúdo que corresponda aos parâmetros da página ou aos parâmetros do visitante, como dimensões de dispositivo ou localização geográfica. |

### Filtrar por valor

As regras estáticas limitam quais itens são incluídos na recomendação, em vez de usar coleções. A seguinte opção está disponível para filtrar por valor:

| Filtrar por opção de valor | Detalhes |
| --- | --- |
| [**[!UICONTROL Filtro estático]**](/help/main/c-recommendations/c-algorithms/static-value.md) | Filtra por um ou mais valores estáticos inseridos manualmente. |

## Operadores disponíveis {#operators}

Os exemplos a seguir mostram como promoções e exclusões dinâmicas podem ser usadas para marketing.

>[!NOTE]
>
>Os operadores &quot;list&quot; exigem que as entidades e os atributos de perfil sejam armazenados como arrays. Uma lista separada por vírgulas não funciona.

| Operador | Disponível com | Exemplos |
|--- |--- |--- |
| **[!UICONTROL é igual a qualquer um de]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]**, **[!UICONTROL Correspondência de parâmetros]** e **[!UICONTROL Filtro estático]** | Quando um visitante visualiza um item no site (como um produto, artigo ou filme), as promoções dinâmicas que usam o operador &quot;equals&quot; podem promover outros itens de:<ul><li>A mesma marca</li><li>A mesma categoria</li><li>A mesma categoria E da marca própria</li><li>A mesma loja</li></ul> |
| **[!UICONTROL não é igual a qualquer um de]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]**, **[!UICONTROL Correspondência de parâmetros]** e **[!UICONTROL Filtro estático]** | Quando um visitante está visualizando um item no site (como um produto, artigo ou filme), as promoções dinâmicas que usam o operador &quot;**[!UICONTROL não é igual a qualquer um de]**&quot; podem promover outros itens de:<ul><li>Uma série de TV diferente</li><li>Um gênero diferente</li><li>Uma série de produtos diferente</li><li>Uma ID de estilo diferente</li></ul> |
| **[!UICONTROL é maior que ou igual a qualquer um de]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]**, **[!UICONTROL Correspondência de parâmetros]** e **[!UICONTROL Filtro estático]** | Quando um visitante está visualizando um item no site (como um produto), o operador &quot;**[!UICONTROL &quot; é maior que ou igual a qualquer um de]**&quot; pode promover outros itens que:<ul><li>Custa o mesmo ou é mais caro</li></ul> |
| **[!UICONTROL é menor que ou igual a qualquer um de]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]**, **[!UICONTROL Correspondência de parâmetros]** e **[!UICONTROL Filtro estático]** | Quando um visitante está visualizando um item no site (como um produto), o operador &quot;**[!UICONTROL é menor que ou igual a qualquer um de]**&quot; pode promover outros itens que:<ul><li>Custa o mesmo ou é mais barato</li></ul> |
| **[!UICONTROL contém qualquer um dos]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]**, **[!UICONTROL Correspondência de parâmetros]** e **[!UICONTROL Filtro estático]** | Quando um visitante está visualizando um item no site (como um produto), o operador &quot;**[!UICONTROL contém qualquer um dos]**&quot; pode promover outros itens que:<ul><li>O título contém a mesma marca</li></ul> |
| **[!UICONTROL não contém nenhum de]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]**, **[!UICONTROL Correspondência de parâmetros]** e **[!UICONTROL Filtro estático]** | Quando um visitante está visualizando um item no site (como um produto), o operador &quot;**[!UICONTROL não contém qualquer um de]**&quot; pode promover outros itens que:<ul><li>O título não contém uma palavra não jurada</li></ul> |
| **[!UICONTROL começa com qualquer um de]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]**, **[!UICONTROL Correspondência de parâmetros]** e **[!UICONTROL Filtro estático]** | Quando um visitante está visualizando um item no site (como um produto), o operador &quot;**[!UICONTROL começa com qualquer um de]**&quot; pode promover outros itens que:<ul><li>O nome do produto começa com iPhone</li></ul> |
| **[!UICONTROL termina com qualquer um de]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]**, **[!UICONTROL Correspondência de parâmetros]** e **[!UICONTROL Filtro estático]** | Quando um visitante exibe um item no site (como um produto), o operador &quot;**[!UICONTROL termina com qualquer um de]**&quot; pode promover outros itens que:<ul><li>O conteúdo termina com EN, que indica o idioma inglês</li></ul> |
| **[!UICONTROL está entre]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Quando um visitante está visualizando um item no site (como um produto, artigo ou filme), as promoções dinâmicas que usam o operador &quot;**[!UICONTROL está entre]**&quot; podem promover outros itens que sejam:<ul><li>Mais caro</li><li>Mais barato</li><li>Custo mais ou menos 30%</li><li>Episódios posteriores na mesma temporada</li><li>Livros anteriores em uma série</li></ul> |
| A lista **[!UICONTROL contém um item em]** (lista à direita) | **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Na correspondência de atributos de perfil, quando um visitante visualiza um item no site (como um produto, artigo ou filme), o operador &quot;**[!UICONTROL lista contém um item em]**&quot; pode promover outros itens que sejam:<ul><li>Disponível na geografia do visitante</li></ul>**Exemplo**: itens recomendados que estão disponíveis somente na área geográfica do visitante.<P>A regra de filtro pode ter esta aparência:<P>`availableGeographies list contains an item in user.currentGeography`<P>**Observação**: quando este operador é usado, uma lista é esperada no [lado direito](#caveats) da regra. |
| **[!UICONTROL a lista não contém um item em]** (lista à direita) | **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Na correspondência de atributos de perfil, quando um visitante visualiza um item no site (como um produto, artigo ou filme), o operador &quot;**[!UICONTROL lista não contém um item em]**&quot; pode excluir outros itens que sejam:<ul><li>Na lista dos últimos dez itens que o visitante visualizou</li></ul>**Exemplo**: os itens que o visitante visualizou recentemente e não mostrou interesse não são promovidos.<P>A regra de filtragem pode ter esta aparência:<P>`id is not contained in list user.lastViewedItems`<P>**Observação**: quando este operador é usado, uma lista é esperada no [lado direito](#caveats) da regra. |
| A lista **[!UICONTROL contém um item em]** (listas em ambos os lados) | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Na correspondência de atributos de perfil, quando um visitante exibe um item no site (como um evento esportivo ou concerto), o operador &quot;**[!UICONTROL lista contém um item em]**&quot; pode promover outros itens que sejam:<ul><li>Associado a uma das equipes favoritas do visitante</li></ul>**Exemplo**: jogos recomendados que estão associados a uma das equipes favoritas do visitante.<P>A regra de filtragem pode ter esta aparência:<P>`teamsPlaying list contains an item in user.favoriteTeams`<P>**Observação**: quando este operador é usado, uma lista é esperada em [ambos os lados](#caveats) da regra. |
| **[!UICONTROL a lista não contém um item em]** (listas em ambos os lados) | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Na correspondência de parâmetros, quando um visitante visualiza um item no site (como um produto, artigo ou filme), o operador &quot;**[!UICONTROL lista não contém um item em]**&quot; pode excluir outros itens que sejam:<ul><li>Contido em uma lista de tipos proibidos</li></ul>**Exemplo**: itens que estão disponíveis apenas para visitantes adultos, como cigarro e álcool, são excluídos.<P>A regra de filtragem pode ter esta aparência:<P>`itemType is not contained in list mbox.prohibitedTypes`<P>**Observação**: quando este operador é usado, uma lista é esperada em [ambos os lados](#caveats) da regra. |
| A lista **[!UICONTROL contém todos os itens em]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Na correspondência de atributos de perfil, quando um visitante visualiza um item no site (como uma publicação de trabalho ou fórmula), o operador &quot;**[!UICONTROL lista contém todos os itens em]**&quot; pode promover outros itens que:<ul><li>Incluir um conjunto de habilidades</li><li>Incluir um conjunto de ingredientes necessários</li></ul>**Exemplo 1**: um visitante tem um conjunto de habilidades (Java, C++ e HTML). Os itens no catálogo são trabalhos com as habilidades necessárias (Java e HTML). O perfil do visitante deve conter todas as habilidades necessárias para que o trabalho seja recomendado ao visitante.<P>A regra de filtragem pode ter esta aparência:<P>`profile.jobSeekerSkills contains all items in entity.requiredSkills`<P>**Exemplo 2**: um usuário tem uma lista de ingredientes de despensa. A receita tem uma lista de ingredientes necessários. O perfil do visitante deve conter todos os ingredientes necessários antes que a fórmula seja recomendada ao visitante.<P>A regra de filtragem pode ter esta aparência:<P>`profile.ingredientsInPantry contains all items in recipe.ingredientsRequired`<P>**Observação**: quando este operador é usado, uma lista é esperada em [ambos os lados](#caveats) da regra. |
| A lista **[!UICONTROL não contém todos os itens em]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Na correspondência do atributo de entidade, quando um visitante exibe um item no site (como um evento esportivo ou concerto), o operador &quot;**[!UICONTROL lista não contém todos os itens em]**&quot; pode promover outros itens que:<ul><li>Não inclua um conjunto de equipes</li></ul>**Exemplo**: um evento esportivo inclui duas equipes. O perfil do visitante indica que ele não deseja exibir jogos para essas equipes, portanto, um jogo não deve ser recomendado se essas equipes estiverem jogando.<P>A regra de filtragem pode ter esta aparência:<P>`profile.leastfavoriteTeams does not contain all items in entity.teamsPlaying`<P>**Observação**: quando este operador é usado, uma lista é esperada em [ambos os lados](#caveats) da regra. |

## Tratar valores vazios {#empty-values}

Várias opções estão disponíveis para tratar valores vazios ao filtrar por **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]**, para critérios e promoções.

Anteriormente, nenhum resultado era retornado se um valor estivesse em branco. A lista suspensa &quot;Se *x* estiver Vazio&quot; especifica a ação a ser executada quando os critérios tiverem valores vazios, como mostrado na seguinte ilustração:

![Opções de valor vazias](/help/main/c-recommendations/c-algorithms/assets/empty_value.png)

Para selecionar a ação desejada, passe o mouse sobre o ícone de engrenagem ( ![Ícone de engrenagem](/help/main/c-recommendations/c-algorithms/assets/icon_gear.png) ) e escolha a ação desejada:

| Ação | Disponível para | Detalhes |
|--- |--- |--- |
| **[!UICONTROL Ignorar esta regra de filtragem]** | **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Esta ação é o padrão para **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]**.<P>A regra é ignorada. Por exemplo, se houver três regras de filtragem e a terceira regra não passar nenhum valor, a terceira regra com os valores vazios poderá ser ignorada em vez de retornar nenhum resultado. |
| **[!UICONTROL Não mostrar nenhum resultado para este critério]**<P>(Somente critérios) | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Esta ação é o padrão para **[!UICONTROL Correspondência de atributos de entidade]**.<P>Esta ação é a forma como [!DNL Target] lidava com os valores em branco antes da adição desta opção: nenhum resultado é mostrado para este critério. |
| **[!UICONTROL Não promover itens]**<P>(Somente promoções) | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Esta ação é o padrão para **[!UICONTROL Correspondência de atributos de entidade]**.<P>Esta ação é a forma como [!DNL Target] lidava com os valores em branco antes da adição desta opção: nenhum resultado é mostrado para esta promoção. |
| **[!UICONTROL Usar um valor estático]** | **[!UICONTROL Correspondência de atributos de entidade]**, **[!UICONTROL Correspondência de atributos de perfil]** e **[!UICONTROL Correspondência de parâmetros]** | Um valor estático pode ser usado quando um valor está vazio. |

## Avisos {#caveats}

>[!IMPORTANT]
>
>Atributos de tipo de dados diferentes podem não ser compatíveis em critérios ou promoções dinâmicas no tempo de execução com os operadores &quot;é igual a&quot; e &quot;não é igual a&quot;. Quando o lado esquerdo tiver atributos predefinidos ou personalizados, escolha cuidadosamente os valores de **[!UICONTROL Valor]**, **[!UICONTROL Margem]**, **[!UICONTROL Inventário]** e **[!UICONTROL Ambiente]** no lado direito.

![Lados esquerdo e direito de uma regra de filtragem](/help/main/c-recommendations/c-algorithms/assets/left_right.png)

A tabela a seguir mostra regras compatíveis e regras que podem não ser compatíveis no tempo de execução:

| Regras compatíveis | Regras potencialmente incompatíveis |
|--- |--- |
| valor - está entre - 90% e 110% do item atual - salesValue | salesValue - está entre - 90% e 110% do item atual - valor |
| valor - está entre - 90% e 110% do item atual - valor | clearancePrice - está entre - 90% e 110% do item atual - margem |
| margem - está entre - 90% e 110% do item atual - margem | storeInventory - é igual a - item atual - inventário |
| inventário - igual a - item atual - inventário |  |
