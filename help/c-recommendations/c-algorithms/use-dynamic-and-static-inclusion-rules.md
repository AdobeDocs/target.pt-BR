---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Informações sobre como criar regras de inclusão no Adobe Target Recommendations para critérios e promoções e adicionar regras de filtragem dinâmicas ou estáticas adicionais para obter melhores resultados.
title: Usar regras de inclusão dinâmicas e estáticas no Adobe Target Recommendations
feature: criteria
mini-toc-levels: 3
uuid: f0ee2086-1126-44a4-9379-aa897dc0e06b
translation-type: tm+mt
source-git-commit: 381c405e55475f2474881541698d69b87eddf6fb
workflow-type: tm+mt
source-wordcount: '1478'
ht-degree: 56%

---


# ![PREMIUM](/help/assets/premium.png) Uso das regras de inclusão estática e dinâmica{#use-dynamic-and-static-inclusion-rules}

Informações sobre como criar regras de inclusão para critérios e promoções no Adobe Target e adicionar regras de filtragem dinâmicas ou estáticas adicionais para obter melhores resultados para suas recomendações.

O processo para criar e usar regras de inclusão para critérios e promoções é semelhante, assim como os casos de uso e exemplos. Os critérios e as promoções e o uso de regras de inclusão são abordados neste tópico.

## Adicionar regras de filtragem aos critérios {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Ao [criar um critério](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), clique em **[!UICONTROL Adicionar regra de filtragem]** em **[!UICONTROL Regras de inclusão]**.

![](assets/inclusion_options_new.png)

As opções disponíveis variam, dependendo do vertical do setor selecionado e da chave de recomendação.

## Adicionar regras de filtragem às promoções  {#section_D59AFB62E2EE423086281CF5D18B1076}

Ao [criar uma promoção](../../c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), selecione **[!UICONTROL Promover por atributo]** e clique em **[!UICONTROL Adicionar regra de filtragem]**.

![](assets/inclusion_options.png)

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

A tabela a seguir lista os tipos de opções de filtragem para os critérios e as promoções:

### Filtragem dinâmica

As seguintes opções estão disponíveis para filtragem dinâmica:

#### Correspondência de atributos de entidade

Filtre dinamicamente comparando um pool de itens de recomendações potenciais a um item específico com o qual os usuários interagiram.

Por exemplo, recomende somente itens que correspondam à marca do item atual.

Operadores disponíveis:

* é igual a
* não é igual
* está entre
* contém
* não contém
* começa com
* termina com
* o valor está presente
* o valor não está presente
* é maior que ou igual a
* é menor que ou igual a

#### Correspondência de atributos de perfil

Filtre dinamicamente comparando itens (entidades) com um valor no perfil do usuário.

Por exemplo, recomende somente itens que correspondam à marca favorita do visitante.

Operadores disponíveis:

* é igual a
* não é igual
* contém
* não contém
* começa com
* termina com
* é maior que ou igual a
* é menor que ou igual a
* está entre

#### Correspondência de parâmetros

Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).

Por exemplo, recomende somente o conteúdo que corresponda ao parâmetro de página do &quot;setor&quot;.

Importante: se a atividade foi criada antes de 31 de outubro de 2016, ocorrerá falha na sua entrega se o filtro &quot;Correspondência de parâmetros&quot; for usado. Para resolver este problema:

* Crie uma nova atividade e adicione nela seus critérios.
* Use um critério que não contenha o filtro &quot;Correspondência de parâmetros&quot;.
* Remova o filtro &quot;Correspondência de parâmetros&quot; de seus critérios.

Operadores disponíveis:

* é igual a
* não é igual
* contém
* não contém
* começa com
* termina com
* é maior que ou igual a
* é menor que ou igual a
* está entre

### Filtrar por valor

A opção a seguir está disponível para filtragem dinâmica:

#### Filtro estático

Insira manualmente um ou mais valores estáticos para filtrar.

Por exemplo, apenas recomende um conteúdo com uma classificação MPAA de &quot;G&quot; ou &quot;PG&quot;.

Operadores disponíveis:

* é igual a
* não é igual
* contém
* não contém
* começa com
* termina com
* o valor está presente
* o valor não está presente
* é maior que ou igual a
* é menor que ou igual a

>[!NOTE]
>
>Se você estiver familiarizado com a configuração das regras de inclusão antes do Target versão 17.6.1 (junho de 2017), perceberá que algumas opções e operadores foram alterados. Somente os operadores aplicáveis à opção selecionada são exibidos e alguns operadores foram renomeados (&quot;matches&quot; agora é &quot;equals&quot;) para ficarem mais consistentes e intuitivos. Todas as regras de exclusão existentes criadas antes desta versão foram migradas automaticamente para a nova estrutura. Nenhuma reestruturação é necessária da sua parte.

Você pode criar a quantidade de regras de inclusão necessária. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

## Critérios dinâmicos e exemplos de promoção

As promoções e os critérios dinâmicos são muito mais eficientes do que os estáticos e geram melhores resultados e envolvimento.

Os seguintes exemplos fornecem ideias sobre como você pode usar promoções dinâmicas em seus esforços de marketing:

### Igual

Usando o operador &quot;igual&quot; em promoções dinâmicas, quando um visitante estiver visualizando um item em seu site (como um produto, artigo ou filme), você pode promover outros itens de:

* mesma marca
* mesma categoria
* mesma categoria E de marca própria
* mesma loja

### Não é igual

Usando o operador &quot;não é igual&quot; em promoções dinâmicas, quando um visitante está visualizando um item em seu site (como um produto, artigo ou filme), você pode promover outros itens de:

* uma série de TV diferente
* um gênero diferente
* uma série diferente de produtos
* uma ID de estilo diferente

### Está entre

Usando o operador &quot;está entre&quot; em promoções dinâmicas, quando um visitante está visualizando um item em seu site (como um produto, artigo ou filme), você pode promover outros itens que sejam:

* mais caros
* mais baratos
* com custo de mais ou menos 30%
* episódios posteriores na mesma temporada
* livros anteriores em uma série

## Handling empty values when filtering by Entity Attribute Matching, Profile Attribute Matching, and Parameter Matching {#section_7D30E04116DB47BEA6FF840A3424A4C8}

You can choose several options to handle empty values when filtering by [!UICONTROL Entity Attribute Matching], [!UICONTROL Profile Attribute Matching], and [!UICONTROL Parameter Matching] for exit criteria and promotions.

Anteriormente, nenhum resultado era retornado se um valor estivesse em branco. A lista suspensa &quot;se *x* estiver em branco&quot; permite escolher a ação apropriada a ser executada se o critério tiver valores em branco, conforme mostrado na ilustração a seguir:

![](assets/empty_value.png)

Para selecionar a ação desejada, passe o mouse sobre o ícone de engrenagem (![](assets/icon_gear.png)), em seguida, escolha a ação desejada:

| Ação | Disponível para | Detalhes |
|--- |--- |--- |
| Ignorar esta regra de filtragem | Correspondência de atributo de perfil<br>Correspondência de parâmetros | Esta é a ação padrão para a Correspondência de atributos de perfil e a Correspondência de parâmetros.<br>Esta opção especifica que a regra será ignorada. Por exemplo, se houver três regras de filtragem e a terceira regra não passar nenhum valor, em vez de não retornar nenhum resultado, você poderá simplesmente ignorar a terceira regra com os valores em branco. |
| Não promover nenhum item | Correspondência do Atributo<br>MatchingProfile do Atributo da Entidade<br>MatchingParameter | Esta é a ação padrão para a Correspondência de atributos de entidade.<br>[!DNL Target]Esta ação é a forma como o lidava com os valores em branco antes da adição desta opção: nenhum resultado será mostrado para este critério. |
| Usar um valor estático | Correspondência de atributos de entidade<br>Correspondência de atributo de perfil<br>Correspondência de parâmetros | Se um valor estiver em branco, você poderá optar por usar um valor estático. |

## Exemplos de correspondência de atributos de perfil {#section_9873E2F22E094E479569D05AD5BB1D40}

[!UICONTROL A Correspondência] de atributos de perfil permite que você recomende somente os itens que correspondem a um atributo do perfil visitante, como nos exemplos abaixo.

### Exemplo 1: Recomendar itens da marca favorita do usuário

For example, you can use the [!UICONTROL Profile Attribute Matching] option to create a rule that recommends items only where the brand equals the value or text stored in `profile.favoritebrand`. Com essa regra, se um visitante estiver olhando para shorts de corrida de uma marca específica, apenas as recomendações exibirão a correspondência dessa marca favorita do usuário (o valor armazenado em `profile.favoritebrand` no perfil do visitante).

```
Profile Attribute Matching
brand - equals - the value/text stored in - profile.favoritebrand
```

### Exemplo 2: Correspondência de empregos a candidatos a emprego

Suponha que você esteja tentando combinar empregos com candidatos a emprego. Você deseja recomendar somente trabalhos que estejam na mesma cidade que o candidato a emprego.

Você pode usar as regras de inclusão para corresponder a localização de um visitante de trabalho de seu perfil a uma lista de trabalhos, como no exemplo a seguir:

```
Profile Attribute Matching
jobCity - equals - the value/text stored in - profile.usersCity
```

## Exemplos de Correspondência de Atributos de Entidade

[!UICONTROL A Correspondência] de atributos de entidade permite recomendar somente os itens que correspondem a um atributo do item que o usuário está visualizando no momento, o item que o usuário visualizou mais recentemente, o item que o usuário comprou mais recentemente, o item que o usuário visualizou mais frequentemente ou de um item armazenado em um atributo personalizado no perfil do visitante, como nos exemplos abaixo.

### Exemplo 3: Venda a um produto mais caro

Suponha que você seja um varejista de roupas e queira incentivar os usuários a considerar itens com preços mais altos e, portanto, mais lucrativos. Você pode usar os operadores &quot;igual&quot; e &quot;é entre&quot; para promover itens mais caros que sejam da mesma categoria e da mesma marca. Por exemplo, uma loja de sapatos pode promover sapatos de corrida mais caros em um esforço para vender um visitante olhando para tênis de corrida.

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### Exemplo 4: Promoção de produtos de etiquetas privadas

Você pode combinar filtros dinâmicos e estáticos para promover produtos de etiquetas privadas. Por exemplo, uma empresa de suprimento de escritório pode promover cartuchos de toner da marca da empresa para promover uma venda mais lucrativa para um visitante que olha para o toner — e promover canetas da marca da empresa para fazer uma venda mais lucrativa para um visitante que olha para as canetas.

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```

## Avisos {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>Atributos de tipo de dados diferentes podem não ser compatíveis em critérios ou promoções dinâmicas durante o tempo de execução com os operadores “é igual a” e “não é igual a”. You should use [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory], and [!UICONTROL Environment] values wisely on the right hand side if the left hand side has predefined attributes or custom attributes.

![](assets/left_right.png)

A tabela a seguir mostra regras em vigor e regras que podem não ser compatíveis durante o tempo de execução:

| Regras compatíveis | Regras potencialmente incompatíveis |
|--- |--- |
| valor - está entre - 90% e 110% do item atual - salesValue | salesValue - está entre - 90% e 110% do item atual - valor |
| valor - está entre - 90% e 110% do item atual - valor | clearancePrice - está entre - 90% e 110% do item atual - margem |
| margem - está entre - 90% e 110% do item atual - margem | storeInventory - é igual a - item atual - inventário |
| inventário - igual a - item atual - inventário |  |
