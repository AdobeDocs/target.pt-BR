---
keywords: inclusion rules;inclusion criteria;recommendations;create new criteria;promotion;promotions;dynamic filtering;dynamic;empty values;ignore filtering rule;static filter;filter by value;entity attribute matching;profile attribute matching;parameter matching;filter by value;static filter
description: Informações sobre como criar regras de inclusão no Adobe Target Recommendations para critérios e promoções e adicionar regras de filtragem dinâmicas ou estáticas adicionais para obter melhores resultados.
title: Usar regras de inclusão dinâmicas e estáticas no Adobe Target Recommendations
feature: criteria
mini-toc-levels: 3
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1062'
ht-degree: 39%

---


# ![PREMIUM](/help/assets/premium.png) Uso das regras de inclusão estática e dinâmica{#use-dynamic-and-static-inclusion-rules}

Informações sobre como criar regras de inclusão para critérios e promoções em [!DNL Adobe Target] e adicionar regras de filtragem dinâmicas ou estáticas adicionais para obter melhores resultados para suas recomendações.

>[!NOTE]
>
>O processo para criar e usar regras de inclusão para critérios e promoções é semelhante, assim como os casos de uso e exemplos. Os critérios e promoções, bem como a utilização das regras de inclusão, são abrangidos pela presente seção.

## Adicionar regras de filtragem aos critérios {#section_CD0D74B8D3BE4A75A78C36CF24A8C57F}

Ao [criar um critério](/help/c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE), clique em **[!UICONTROL Adicionar regra de filtragem]** em **[!UICONTROL Regras de inclusão]**.

![](assets/inclusion_options_new.png)

As opções disponíveis variam, dependendo do vertical do setor selecionado e da chave de recomendação.

## Adicionar regras de filtragem às promoções   {#section_D59AFB62E2EE423086281CF5D18B1076}

Ao [criar uma promoção](/help/c-recommendations/t-create-recs-activity/adding-promotions.md#task_CC5BD28C364742218C1ACAF0D45E0E14), selecione **[!UICONTROL Promover por atributo]** e clique em **[!UICONTROL Adicionar regra de filtragem]**.

![](assets/inclusion_options.png)

## Tipos de filtro {#section_0125F1ED10A84C0EB45325122460EBCD}

As seções a seguir listas os tipos de opções de filtragem para [!UICONTROL Filtragem Dinâmica] e [!UICONTROL Filtrar por Valor] para os critérios e promoções:

### Filtragem dinâmica

As regras de inclusão dinâmica são mais poderosas do que as regras de inclusão estáticas e proporcionam melhores resultados e envolvimento. Considere o seguinte:

* As regras de inclusão dinâmica fornecem recomendações ao corresponder um atributo no parâmetro de perfil de um usuário ou em uma chamada de mbox.

   Por exemplo, você pode criar uma recomendação &quot;Critérios mais populares&quot; e, em seguida, definir o conjunto de recomendações retornadas, em seguida, filtrar quaisquer recomendações (em tempo real) em relação a um atributo passado quando o usuário acessa uma página onde as recomendações são exibidas.

* Use regras estáticas para limitar quais itens são incluídos na recomendação (em vez de usar coleções).

* Você pode criar quantas regras de inclusão dinâmica forem necessárias. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

As seguintes opções estão disponíveis para filtragem dinâmica:

| Opção de filtragem dinâmica | Detalhes |
| --- | --- |
| [Correspondência de atributos de entidade](/help/c-recommendations/c-algorithms/entity-attribute-matching.md) | Filtre dinamicamente comparando um pool de itens de recomendações potenciais a um item específico com o qual os usuários interagiram.<br>Use a  [!UICONTROL Correspondência de atributos de ] entidade quando quiser mostrar recomendações mais susceptíveis a apelar ao visitante, como a marca favorita do visitante. |
| [Correspondência de atributos de perfil](/help/c-recommendations/c-algorithms/profile-attribute-matching.md) | Filtre dinamicamente comparando itens (entidades) com um valor no perfil do usuário.<br>Use a  [!UICONTROL Correspondência de atributos do ] Perfil quando quiser mostrar recomendações que correspondem a um valor armazenado no perfil do visitante, como tamanho ou marca favorita. |
| [Correspondência de parâmetros](/help/c-recommendations/c-algorithms/parameter-matching.md) | Filtre dinamicamente comparando itens (entidades) com um valor na solicitação (API ou mbox).<br>Use  [!UICONTROL Parameter ] Matching (Correspondência de parâmetro) para recomendar o conteúdo que corresponda aos parâmetros da página ou aos parâmetros do visitante, como dimensões do dispositivo ou localização geográfica. |

### Filtrar por valor

A seguinte opção está disponível para filtragem por valor:

| Opção Filtrar por valor | Detalhes |
| --- | --- |
| [Filtro estático](/help/c-recommendations/c-algorithms/static-value.md) | Insira manualmente um ou mais valores estáticos para filtrar. |

## Critérios dinâmicos e exemplos de promoção

Critérios e promoções dinâmicos são muito mais poderosos do que critérios e promoções estáticas e geram melhores resultados e envolvimento.

Os exemplos a seguir fornecem ideias gerais sobre como você pode usar promoções dinâmicas em seus esforços de marketing:

| Operador | Exemplos |
| --- | --- |
| Igual | Usando o operador &quot;igual&quot; em promoções dinâmicas, quando um visitante estiver visualizando um item em seu site (como um produto, artigo ou filme), você pode promover outros itens de:<ul><li>mesma marca</li><li>mesma categoria</li><li>mesma categoria E de marca própria</li><li>mesma loja</li></ul> |
| Não é igual | Usando o operador &quot;não é igual&quot; em promoções dinâmicas, quando um visitante está visualizando um item em seu site (como um produto, artigo ou filme), você pode promover outros itens de:<ul><li>uma série de TV diferente</li><li>um gênero diferente</li><li>uma série diferente de produtos</li><li>uma ID de estilo diferente</li></ul> |
| Está entre | Usando o operador &quot;está entre&quot; em promoções dinâmicas, quando um visitante está visualizando um item em seu site (como um produto, artigo ou filme), você pode promover outros itens que sejam:<ul><li>mais caros</li><li>mais baratos</li><li>com custo de mais ou menos 30%</li><li>episódios posteriores na mesma temporada</li><li>livros anteriores em uma série</li></ul> |

## Tratamento de valores vazios ao filtrar por Correspondência de Atributos de Entidade, Correspondência de Atributos de Perfil e Correspondência de Parâmetro {#section_7D30E04116DB47BEA6FF840A3424A4C8}

Você pode escolher várias opções para manipular valores vazios ao filtrar por [!UICONTROL Correspondência de Atributos de Entidade], [!UICONTROL Correspondência de Atributos de Perfil] e [!UICONTROL Correspondência de Parâmetro] para critérios de saída e promoções.

Anteriormente, nenhum resultado era retornado se um valor estivesse em branco. A lista suspensa &quot;se *x* estiver em branco&quot; permite escolher a ação apropriada a ser executada se o critério tiver valores em branco, conforme mostrado na ilustração a seguir:

![](assets/empty_value.png)

Para selecionar a ação desejada, passe o mouse sobre o ícone de engrenagem (![](assets/icon_gear.png)), em seguida, escolha a ação desejada:

| Ação | Disponível para | Detalhes |
|--- |--- |--- |
| [!UICONTROL Ignorar esta regra de filtragem] | [!UICONTROL Correspondência de Atributo de perfil ] [!UICONTROL e Correspondência de Parâmetro] | Esta é a ação padrão para [!UICONTROL Correspondência de Atributo de Perfil] e [!UICONTROL Correspondência de Parâmetro].<br>Esta opção especifica que a regra será ignorada. Por exemplo, se houver três regras de filtragem e a terceira regra não passar nenhum valor, em vez de não retornar nenhum resultado, você poderá simplesmente ignorar a terceira regra com os valores em branco. |
| [!UICONTROL Não mostrar resultados para este critério]<br> (somente Critérios) | [!UICONTROL Correspondência] de atributos de entidade, Correspondência [!UICONTROL  de atributos de ]Perfil e Correspondência de  [!UICONTROL parâmetros] | Esta é a ação padrão para [!UICONTROL Correspondência de Atributo de Entidade].<br>[!DNL Target]Esta ação é a forma como o lidava com os valores em branco antes da adição desta opção: nenhum resultado será mostrado para este critério. |
| [!UICONTROL Não promover nenhum item<br> (somente promoções)] | [!UICONTROL Correspondência] de atributos de entidade, Correspondência [!UICONTROL  de atributos de ]Perfil e Correspondência de  [!UICONTROL parâmetros] | Esta é a ação padrão para [!UICONTROL Correspondência de Atributo de Entidade].<br>[!DNL Target]Esta ação é a forma como o lidava com os valores em branco antes da adição desta opção: nenhum resultado será mostrado para este critério. |
| [!UICONTROL Usar um valor estático] | [!UICONTROL Correspondência] de atributos de entidade, Correspondência [!UICONTROL  de atributos de ]Perfil e Correspondência de  [!UICONTROL parâmetros] | Se um valor estiver em branco, você poderá optar por usar um valor estático. |

## Avisos {#section_A889FAF794B7458CA074DEE06DD0E345}

>[!IMPORTANT]
>
>Atributos de tipo de dados diferentes podem não ser compatíveis em critérios ou promoções dinâmicas durante o tempo de execução com os operadores “é igual a” e “não é igual a”. Você deve usar os valores [!UICONTROL Valor], [!UICONTROL Margem], [!UICONTROL Inventário] e [!UICONTROL Ambiente] sabiamente no lado direito se o lado esquerdo tiver atributos predefinidos ou atributos personalizados.

![](assets/left_right.png)

A tabela a seguir mostra regras em vigor e regras que podem não ser compatíveis durante o tempo de execução:

| Regras compatíveis | Regras potencialmente incompatíveis |
|--- |--- |
| valor - está entre - 90% e 110% do item atual - salesValue | salesValue - está entre - 90% e 110% do item atual - valor |
| valor - está entre - 90% e 110% do item atual - valor | clearancePrice - está entre - 90% e 110% do item atual - margem |
| margem - está entre - 90% e 110% do item atual - margem | storeInventory - é igual a - item atual - inventário |
| inventário - igual a - item atual - inventário |  |
