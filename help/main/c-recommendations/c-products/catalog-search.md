---
keywords: pesquisa de catálogo;catálogo;pesquisa;exclusão;coleção;filtro;recomendações
description: Saiba como usar o  [!DNL Recommendations] [!UICONTROL Catalog Search] para localizar produtos ou conteúdo, remover itens do catálogo e muito mais.
title: Como usar o  [!DNL Recommendations] [!UICONTROL Catalog Search]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 22%

---

# [!UICONTROL Catalog Search]

A página [!UICONTROL Catalog Search] no [!DNL Adobe Recommendations] ajuda a localizar os produtos ou conteúdo no catálogo. A tarefa mais básica que você pode executar nessa página é procurar um item. Além disso, você pode alterar o ambiente, filtrar aspectos, modificar colunas na tabela, adicionar novos aspectos de pesquisa e muito mais.

Catálogos se referem a todo o conjunto de produtos (entidades). Seu catálogo pode conter muitas coleções, uma maneira de organizar seus produtos em compartimentos lógicos.

## Acessar [!UICONTROL Catalog Search]

1. Para acessar a página [!UICONTROL Catalog Search], clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Catalog Search]**.

1. (Opcional) Para aplicar filtros à sua pesquisa, clique no ícone **[!UICONTROL Show Filters]** ( ![ícone Mostrar filtros](/help/main/assets/icons/Filter.svg) ). Você pode filtrar por [!UICONTROL Environment], [!UICONTROL Collections], [!UICONTROL Category], [!UICONTROL Brand], [!UICONTROL Inventory] e [!UICONTROL Value].

## Executar uma pesquisa simples

1. Digite um termo de pesquisa no campo **[!UICONTROL Search In]**.

1. (Opcional) Você pode refinar sua pesquisa selecionando uma opção de pesquisa no menu de opções que é exibido ao clicar na seta para baixo no campo [!UICONTROL Search In].

   As opções de pesquisa incluem o seguinte:

   * ID
   * Nome
   * Mensagem

1. Role pelos itens nos resultados da pesquisa para visualizar miniaturas e outras informações do produto.

   >[!NOTE]
   >
   > Quando você faz uma pesquisa no catálogo em um atributo personalizado com um valor numérico, os resultados tratam o atributo personalizado como um tipo de sequência em vez de um valor numérico.
   >
   >Não há nenhuma funcionalidade disponível no momento que permita alterar o tipo de um atributo. Para fazer uma alteração, [abra um problema do cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) referenciando os atributos que precisam de alteração do tipo de sequência para numérico.

<!-- ### Perform an advanced search {#advanced-search}

You can use [!UICONTROL Advanced Search] to further refine your search results or to save your search results as a [collection](/help/main/c-recommendations/c-products/collections.md) or [exclusion](/help/main/c-recommendations/c-products/exclusions.md).

1. Click the **[!UICONTROL Advanced Search]** link.

   ![Advanced Search page](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use the drop-down lists to specify the parameter, operator, and values for your search.

1. (Optional) Click **[!UICONTROL Add Rule]** to add an additional search rule.

   Each additional search rule is joined with the AND operator.

1. Click **[!UICONTROL Search]**.

1. (Optional) Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   For more information, see [Create a collection or exclusion based on Advanced Search](#save-as) below.-->

## Exibir detalhes de um item

Você pode exibir os detalhes de um item individual, incluindo ID, nome, mensagem, categoria e muito mais, exibindo seus detalhes.

1. Clique em um item nos resultados da pesquisa para exibir seus detalhes.

## Remover um item do catálogo

1. Clique em um item nos resultados da pesquisa para exibir seus detalhes.

1. Clique em **[!UICONTROL Remove from Catalog]**.

1. Confirme se deseja remover o item.

Todas as informações sobre esse item são removidas do índice do catálogo. O item será incluído no catálogo somente se for adicionado novamente em um feed de dados. Um item excluído deve ser excluído separadamente dos feeds.

## Atualizar o catálogo

O índice do catálogo é criado automaticamente ao carregar seu primeiro feed e atualizado de acordo com o [agendamento especificado](/help/main/c-recommendations/c-products/feeds.md#steps).

O catálogo é atualizado automaticamente quando as atualizações são recebidas por meio de arquivos de feed, API ou atualizações de mbox. Normalmente, as atualizações são concluídas em uma hora. Se houver atualizações em andamento, será exibida a hora em que a atualização mais recente foi iniciada. Se não houver atualizações em andamento, será exibida a hora em que a atualização mais recente foi iniciada e finalizada.

<!-- ## Create a collection or exclusion based on Advanced Search {#save-as}

You can create [collections](/help/main/c-recommendations/c-products/collections.md) or [exclusions](/help/main/c-recommendations/c-products/exclusions.md) using [!UICONTROL Advanced Search] on the [!UICONTROL Catalog Search] page ([!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

1. Perform an [advanced search](#advanced-search).

1. Click **[!UICONTROL Save As]**, then click **[!UICONTROL Collection]** or **[!UICONTROL Exclusion]**.

   ![Save as options](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create collections or exclusions based on results using the [!UICONTROL Advanced Search] functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create a catalog with the intent to return products containing "holiday," only products containing "holiday" are returned. Products containing "Holiday" are not returned. Exclusions are handled in a similar fashion.-->

## Alterar o ambiente

[Os ambientes](/help/main/administrating-target/environments.md) permitem organizar os sites e os ambientes de pré-produção para facilitar o gerenciamento e gerar relatórios separados.

1. Clique no ícone Mostrar filtros ( ![ícone Mostrar filtros](/help/main/assets/icons/Filter.svg) ).

1. Selecione o ambiente desejado na lista suspensa **[!UICONTROL Environment]**.

<!-- ## Modify the Catalog Search page (filters and columns)

You can temporarily modify the available filters and columns on the [!UICONTROL Catalog Search] page for the current session.

### Modify filters

You can add additional filter facets to the [!UICONTROL Catalog Search] page.

1. In the **[!UICONTROL Filters]** panel, click **[!UICONTROL Modify]**.

   ![Modify filters link](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Select the desired search facets (ID, name, message, etc.), then click **[!UICONTROL Save]**.

   ![Add filters](/help/main/c-recommendations/c-products/assets/add-filters.png)

Keep in mind that the additional filter facets are available in the current session only.-->

## Modificar colunas

Você pode modificar as colunas ativas na página [!UICONTROL Catalog Search].

1. Clique no ícone **[!UICONTROL Customize Table]** ( ![Ícone Personalizar tabela](/help/main/assets/icons/ColumnSetting.svg) ).

1. Marque ou desmarque as colunas desejadas que deseja exibir ou ocultar.

Todas as alterações feitas são persistentes nas sessões.
