---
keywords: regras de inclusão, critérios de inclusão, recomendações, criar novos critérios, promoção, promoções, filtragem dinâmica, dinâmica, valores em branco, ignorar regra de filtragem, filtro estático, filtrar por valor, correspondência de atributos de entidade, correspondência de atributos de perfil, correspondência de parâmetros, filtrar por valor, filtro estático
description: Saiba como criar regras de inclusão no Adobe Target Recommendations para critérios e promoções. Adicione outras regras de filtragem dinâmica ou estática para obter melhores resultados.
title: Como uso as regras de inclusão estática e dinâmica no Recommendations?
feature: Recommendations
mini-toc-levels: 3
exl-id: 49b20e75-ee55-4239-94a0-6d175e2d4811
translation-type: tm+mt
source-git-commit: 6ba670ef69fa23c0023636a1920eed15dcd9dd06
workflow-type: tm+mt
source-wordcount: '1100'
ht-degree: 41%

---

# ![PREMIUM](/help/assets/premium.png) Uso das regras de inclusão estática e dinâmica{#use-dynamic-and-static-inclusion-rules}

Informações sobre como criar regras de inclusão para critérios e promoções em [!DNL Adobe Target] e adicionar regras de filtragem dinâmica ou estática adicionais para obter melhores resultados para suas recomendações.

>[!NOTE]
>
>O processo para criar e usar regras de inclusão para critérios e promoções é semelhante, assim como os casos de uso e exemplos. Os critérios e promoções e o uso de regras de inclusão são abordados nesta seção.

## Adicionar regras de filtragem aos critérios {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Ao [criar um critério](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), clique em **[!UICONTROL Adicionar regra de filtragem]** em **[!UICONTROL Regras de inclusão]**.

![](assets/inclusion_options_new.png)

As opções disponíveis variam, dependendo do vertical do setor selecionado e da chave de recomendação.

## Adicionar regras de filtragem às promoções   {#section_D59AFB62E2EE423086281CF5D18B1076}

Ao [criar uma promoção](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), selecione **[!UICONTROL Promover por atributo]** e clique em **[!UICONTROL Adicionar regra de filtragem]**.

![](assets/inclusion_options.png)

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

As seções a seguir listam os tipos de opções de filtragem para [!UICONTROL Filtragem Dinâmica] e [!UICONTROL Filtrar por Valor] para ambos os critérios e promoções:

### Filtragem dinâmica

As regras de inclusão dinâmica são mais eficientes do que as regras de inclusão estática e proporcionam melhores resultados e envolvimento. Considere o seguinte:

* As regras de inclusão dinâmica fornecem recomendações ao corresponder um atributo no parâmetro do perfil de um usuário ou em uma chamada de mbox.

   Por exemplo, você pode criar uma recomendação de &quot;Critérios mais populares&quot; e, em seguida, definir o conjunto de recomendações retornadas, em seguida, filtrar quaisquer recomendações (em tempo real) em relação a um atributo passado quando o usuário acessa uma página onde as recomendações são exibidas.

* Use regras estáticas para limitar quais itens são incluídos na recomendação (em vez de usar coleções).

* Você pode criar quantas regras de inclusão dinâmica forem necessárias. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

As seguintes opções estão disponíveis para filtragem dinâmica:

| Opção de filtragem dinâmica | Detalhes |
| --- | --- |
| [Correspondência de atributos de entidade](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinamicamente comparando um conjunto de possíveis itens de recomendações a um item específico com o qual os usuários interagiram.<br>Use a  [!UICONTROL Correspondência de atributos de ] entidade quando desejar mostrar recomendações que provavelmente serão atraídas ao visitante, como a marca favorita do visitante. |
| [Correspondência de atributos de perfil](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinamicamente comparando os itens (entidades) com um valor no perfil do usuário.<br>Use a  [!UICONTROL Correspondência de atributos ] de perfil quando quiser mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita. |
| [Correspondência de parâmetros](/help/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).<br>Use a  [!UICONTROL Correspondência ] de parâmetros para recomendar o conteúdo que corresponda aos parâmetros da página ou aos parâmetros do visitante, como dimensões de dispositivo ou localização geográfica. |

### Filtrar por valor

A seguinte opção está disponível para filtragem por valor:

| Opção Filtrar por valor | Detalhes |
| --- | --- |
| [Filtro estático](/help/c-recommendations/c-algorithms/static-value.md) | Insira manualmente um ou mais valores estáticos para filtrar. |

## Critérios dinâmicos e exemplos de promoção

Os critérios e as promoções dinâmicas são muito mais eficientes do que os critérios e promoções estáticas e geram melhores resultados e envolvimento.

Os seguintes exemplos fornecem ideias gerais sobre como usar promoções dinâmicas em seus esforços de marketing:

| Operador | Exemplos |
| --- | --- |
| Igual | Usando o operador &quot;equals&quot; em promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens de:<ul><li>mesma marca</li><li>mesma categoria</li><li>mesma categoria E de marca própria</li><li>mesma loja</li></ul> |
| Does Not Equal | Usando o operador &quot;não é igual&quot; em promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens de:<ul><li>uma série de TV diferente</li><li>um gênero diferente</li><li>uma série diferente de produtos</li><li>uma ID de estilo diferente</li></ul> |
| Está entre | Usando o operador &quot;is between&quot; nas promoções dinâmicas, quando um visitante visualizar um item no seu site (como um produto, artigo ou filme), será possível promover outros itens que sejam:<ul><li>mais caros</li><li>mais baratos</li><li>com custo de mais ou menos 30%</li><li>episódios posteriores na mesma temporada</li><li>livros anteriores em uma série</li></ul> |

## Lidar com valores em branco ao filtrar por Correspondência de atributos de entidade, Correspondência de atributos de perfil e Correspondência de parâmetros {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Você pode escolher várias opções para lidar com valores em branco ao filtrar por [!UICONTROL Correspondência de atributos de entidade], [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros] para critérios e promoções de saída.

Anteriormente, nenhum resultado era retornado se um valor estivesse em branco. A lista suspensa &quot;se *x* estiver em branco&quot; permite escolher a ação apropriada a ser executada se o critério tiver valores em branco, conforme mostrado na ilustração a seguir:

![](assets/empty_value.png)

Para selecionar a ação desejada, passe o mouse sobre o ícone de engrenagem (![](assets/icon_gear.png)), em seguida, escolha a ação desejada:

| Ação | Disponível para | Detalhes |
|--- |--- |--- |
| [!UICONTROL Ignorar esta regra de filtragem] | [!UICONTROL Correspondência de atributos de perfil ] e correspondência  [!UICONTROL de parâmetros] | Esta é a ação padrão para [!UICONTROL Correspondência de atributos de perfil] e [!UICONTROL Correspondência de parâmetros].<br>Esta opção especifica que a regra será ignorada. Por exemplo, se houver três regras de filtragem e a terceira regra não passar nenhum valor, em vez de não retornar nenhum resultado, você poderá simplesmente ignorar a terceira regra com os valores em branco. |
| [!UICONTROL Não mostrar nenhum resultado para este critério]<br> (somente Critérios) | [!UICONTROL Correspondência de atributos de entidade], Correspondência de atributos  [!UICONTROL de perfil] e Correspondência de  [!UICONTROL parâmetros] | Esta é a ação padrão para [!UICONTROL Correspondência de atributos de entidade].<br>[!DNL Target]Esta ação é a forma como o lidava com os valores em branco antes da adição desta opção: nenhum resultado será mostrado para este critério. |
| [!UICONTROL Não promover nenhum item<br> (somente Promoções)] | [!UICONTROL Correspondência de atributos de entidade], Correspondência de atributos  [!UICONTROL de perfil] e Correspondência de  [!UICONTROL parâmetros] | Esta é a ação padrão para [!UICONTROL Correspondência de atributos de entidade].<br>[!DNL Target]Esta ação é a forma como o lidava com os valores em branco antes da adição desta opção: nenhum resultado será mostrado para este critério. |
| [!UICONTROL Usar um valor estático] | [!UICONTROL Correspondência de atributos de entidade], Correspondência de atributos  [!UICONTROL de perfil] e Correspondência de  [!UICONTROL parâmetros] | Se um valor estiver em branco, você poderá optar por usar um valor estático. |

## Avisos {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>Atributos de tipo de dados diferentes podem não ser compatíveis em critérios ou promoções dinâmicas durante o tempo de execução com os operadores “é igual a” e “não é igual a”. Você deve usar os valores [!UICONTROL Value], [!UICONTROL Margin], [!UICONTROL Inventory] e [!UICONTROL Environment] de maneira inteligente no lado direito se o lado esquerdo tiver atributos predefinidos ou atributos personalizados.

![](assets/left_right.png)

A tabela a seguir mostra regras em vigor e regras que podem não ser compatíveis durante o tempo de execução:

| Regras compatíveis | Regras potencialmente incompatíveis |
|--- |--- |
| valor - está entre - 90% e 110% do item atual - salesValue | salesValue - está entre - 90% e 110% do item atual - valor |
| valor - está entre - 90% e 110% do item atual - valor | clearancePrice - está entre - 90% e 110% do item atual - margem |
| margem - está entre - 90% e 110% do item atual - margem | storeInventory - é igual a - item atual - inventário |
| inventário - igual a - item atual - inventário |  |
