---
keywords: pesquisa de catálogo;catálogo;pesquisa;exclusão;coleção;filtro;catalog search;catalog;exclusion;collection;filter
description: Saiba como usar a Pesquisa no catálogo do Recommendations para localizar produtos ou conteúdo, criar coleções ou exclusões, remover itens do catálogo e muito mais.
title: Como usar a Pesquisa no catálogo do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '1040'
ht-degree: 23%

---

# Pesquisa no catálogo

A variável [!UICONTROL Pesquisa no catálogo] página em [!DNL Adobe Recommendations] O ajuda a localizar os produtos ou conteúdo no catálogo. A tarefa mais básica que você pode executar nessa página é procurar um item. Além disso, você pode alterar o ambiente, salvar resultados de pesquisa em coleções ou exclusões, adicionar facetas de filtro e modificar colunas na tabela, adicionar novas facetas de pesquisa e muito mais.

Catálogos se referem a todo o conjunto de produtos (entidades). Seu catálogo pode conter muitas coleções, uma maneira de organizar seus produtos em compartimentos lógicos.

## Acessar a pesquisa no catálogo

Para acessar o [!UICONTROL Pesquisa no catálogo] clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Pesquisa no catálogo]**.

![Página de pesquisa do catálogo](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## Pesquisar um item

Você pode usar uma pesquisa simples ou avançada para localizar itens em seu catálogo.

### Executar uma pesquisa simples

1. Digite um termo de pesquisa no campo **[!UICONTROL Pesquisar produtos]** campo.

1. (Opcional) Você pode refinar sua pesquisa selecionando uma opção de pesquisa no menu de opções que é exibido ao clicar na seta para baixo no campo de pesquisa.

   ![imagem searchproductsmenu](assets/searchproductsmenu.png)

   As opções de pesquisa incluem o seguinte:

   * TODAS - Pesquisa em todos os outros critérios de pesquisa, usando a lógica OU.
   * Nome
   * Marca
   * Categoria
   * ID
   * Mensagem

1. Agora é possível percorrer os itens nos resultados da pesquisa para exibir miniaturas e outras informações do produto.

   A ilustração a seguir mostra os resultados para &quot;bicicleta&quot; usando a opção Todos.

   ![Pesquisa no catálogo de bicicletas](/help/main/c-recommendations/c-products/assets/bike-results.png)

   O número que aparece ao lado de &quot;Produtos&quot; é o número de produtos que combinam com o termo de pesquisa, do total disponível no ambiente especificado.

   Observe que você pode usar a funcionalidade de preenchimento automático de pesquisa. Na ilustração a seguir, digitar &quot;bicicleta&quot; retorna todos os produtos que contêm a palavra &quot;bicicleta&quot;.

   ![Pesquisar preenchimento automático](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >Quando você faz uma pesquisa no catálogo em um atributo personalizado com um valor numérico, os resultados tratam o atributo personalizado como um tipo de sequência em vez de um valor numérico.
   >
   >Atualmente, não há nenhuma funcionalidade disponível que permita alterar o tipo de um atributo. Para fazer uma alteração, [abra um problema do cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) referenciando os atributos que precisam de alteração do tipo de sequência para numérico.

1. Também é possível usar filtros para encontrar o produto desejado. No exemplo a seguir, ao expandir a variável [!UICONTROL Coleções] faceta e selecionando &quot;Bike Tools&quot;, todas as ferramentas de bicicleta na exibição do catálogo.

   ![Ferramentas de bicicleta](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. Você pode pesquisar mais na lista de resultados inserindo um termo de pesquisa, por exemplo &quot;cadeia&quot;.

   ![Pesquisar cadeia](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### Executar uma pesquisa avançada {#advanced-search}

Você pode usar [!UICONTROL Pesquisa avançada] para refinar ainda mais os resultados da pesquisa ou para salvar os resultados da pesquisa como um [coleção](/help/main/c-recommendations/c-products/collections.md) ou [exclusão](/help/main/c-recommendations/c-products/exclusions.md).

1. Clique em **[!UICONTROL Pesquisa avançada]** link.

   ![Página Pesquisa avançada](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use as listas suspensas para especificar o parâmetro, operador e valores da pesquisa.

1. (Opcional) Clique em **[!UICONTROL Adicionar regra]** para adicionar uma regra de pesquisa adicional.

   Cada regra de pesquisa adicional é unida com o operador AND.

1. Clique em **[!UICONTROL Pesquisa]**.

1. (Opcional) Clique em **[!UICONTROL Salvar como]** e, em seguida, clique em **[!UICONTROL Coleção]** ou **[!UICONTROL Exclusão]**.

   ![Salvar como opções](/help/main/c-recommendations/c-products/assets/save-as.png)

   Para obter mais informações, consulte [Criar uma coleção ou exclusão com base na Pesquisa avançada](#save-as) abaixo.

## Exibir detalhes de um item

Você pode exibir os detalhes de um item individual, incluindo ID, nome, mensagem, categoria e muito mais, exibindo seus detalhes.

1. Clique em um item nos resultados da pesquisa para exibir seus detalhes.

   ![Detalhes do produto](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## Remover um item do catálogo

1. Clique em um item nos resultados da pesquisa para exibir seus detalhes.

1. Clique em **[!UICONTROL Remover do catálogo]**.

1. Confirme se deseja remover o item.

Todas as informações sobre esse item são removidas do índice do catálogo. O item será incluído no catálogo somente se for adicionado novamente em um feed de dados. Um item excluído deve ser excluído separadamente dos feeds.

## Atualizar o catálogo

O índice do catálogo é criado automaticamente ao fazer upload do primeiro feed e atualizado de acordo com [programação especificada](/help/main/c-recommendations/c-products/feeds.md#steps).

O catálogo é atualizado automaticamente quando as atualizações são recebidas por meio de arquivos de feed, API ou atualizações de mbox. Normalmente, as atualizações são concluídas em uma hora. Se houver atualizações em andamento, será exibida a hora em que a atualização mais recente foi iniciada. Se não houver atualizações em andamento, será exibida a hora em que a atualização mais recente foi iniciada e finalizada.

## Criar uma coleção ou exclusão com base na Pesquisa avançada {#save-as}

Você pode criar [coleções](/help/main/c-recommendations/c-products/collections.md) ou [exclusões](/help/main/c-recommendations/c-products/exclusions.md) usando a Pesquisa avançada na página Pesquisa no catálogo ([!UICONTROL Recommendations] > [!UICONTROL Pesquisa no catálogo] > [!UICONTROL Pesquisa avançada]).

1. Execute um [pesquisa avançada](#advanced-search).

1. Clique em **[!UICONTROL Salvar como]** e, em seguida, clique em **[!UICONTROL Coleção]** ou **[!UICONTROL Exclusão]**.

   ![Salvar como opções](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >A variável [!UICONTROL Pesquisa avançada] A funcionalidade não diferencia maiúsculas de minúsculas; no entanto, os produtos retornados no momento do delivery baseiam-se na pesquisa sensível a maiúsculas e minúsculas. Essa não correspondência pode levar à confusão. Considere a diferenciação entre maiúsculas e minúsculas ao criar coleções ou exclusões com base nos resultados usando o [!UICONTROL Pesquisa avançada] funcionalidade. Por exemplo, se você realiza uma busca para &quot;Feriado&quot;, essa busca inicial lista os resultados contendo &quot;Feriado&quot; e &quot;feriado&quot;. Em seguida, se você criar um catálogo com a intenção de encontrar produtos contendo &quot;feriado&quot;, somente os produtos contendo &quot;feriado&quot; serão exibidos. Os produtos contendo &quot;Feriado&quot; não serão exibidos. As exclusões são tratadas de maneira semelhante.

## Alterar o ambiente

[Ambientes](/help/main/administrating-target/environments.md) O permite organizar seus sites e ambientes de pré-produção para facilitar o gerenciamento e gerar relatórios separados.

1. Clique no link Ambiente.

   ![Link de ambiente](/help/main/c-recommendations/c-products/assets/environment.png)

1. Selecione o ambiente desejado.

## Modificar a página Pesquisa no catálogo (filtros e colunas)

É possível modificar temporariamente os filtros e colunas disponíveis na [!UICONTROL Pesquisa no catálogo] página da sessão atual.

### Modificar filtros

É possível adicionar outras facetas de filtro à [!UICONTROL Pesquisa no catálogo] página.

1. No **[!UICONTROL Filtros]** clique em **[!UICONTROL Modificar]**.

   ![Modificar link de filtros](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Selecione os aspectos de pesquisa desejados (ID, nome, mensagem etc.) e clique em **[!UICONTROL Salvar]**.

   ![Adicionar filtros](/help/main/c-recommendations/c-products/assets/add-filters.png)

Lembre-se de que as facetas de filtro adicionais estão disponíveis somente na sessão atual.

### Modificar colunas

Você pode modificar temporariamente as colunas ativas na [!UICONTROL Pesquisa no catálogo] página.

1. Clique em **[!UICONTROL Colunas]** link.

   ![Opções de colunas](/help/main/c-recommendations/c-products/assets/columns.png)

1. (Condicional) Para reordenar a ordem das colunas ativas, arraste e solte as colunas na **[!UICONTROL Colunas ativas]** na ordem desejada.

1. (Condicional) Arraste e solte itens da caixa **[!UICONTROL Colunas ativas]** para o **[!UICONTROL Colunas inativas]** (e vice-versa), conforme desejado.

   Você também pode clicar no ícone excluir ( x ) ao lado da coluna que deseja mover da seção ativa para inativa.

Lembre-se de que as alterações feitas se aplicam somente à sessão atual.
