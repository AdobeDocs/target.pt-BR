---
keywords: pesquisa de catálogo, catálogo, pesquisa, exclusão, coleção, filtro
description: Saiba como usar a Pesquisa no catálogo do Recommendations para localizar produtos ou conteúdo, criar coleções ou exclusões, remover itens do catálogo e muito mais.
title: Como uso a pesquisa no catálogo do Recommendations?
feature: Recommendations
exl-id: 925fea97-e2c5-4883-84e3-fd357a8ee8d9
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 22%

---

# ![PREMIUM](/help/main/assets/premium.png) Pesquisa no catálogo

O [!UICONTROL Pesquisa no catálogo] em [!DNL Adobe Recommendations] O ajuda a localizar os produtos ou conteúdo no catálogo. A tarefa mais básica que você pode executar nesta página é procurar um item. Além disso, você pode alterar o ambiente, salvar os resultados da pesquisa em coleções ou exclusões, adicionar facetas de filtro e modificar colunas na tabela, adicionar novas facetas de pesquisa e muito mais.

Catálogos se referem a todo o conjunto de produtos (entidades). Seu catálogo pode conter muitas coleções, uma maneira de organizar seus produtos em buckets lógicos.

## Acessar pesquisa no catálogo

Para acessar o [!UICONTROL Pesquisa no catálogo] página, clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Pesquisa no catálogo]**.

![Página Pesquisa no catálogo](/help/main/c-recommendations/c-products/assets/catalog-search.png)

## Procurar um item

Você pode usar uma pesquisa simples ou avançada para localizar itens no catálogo.

### Realizar uma pesquisa simples

1. Digite um termo de pesquisa no **[!UICONTROL Procurar produtos]** campo.

1. (Opcional) Você pode refinar sua pesquisa selecionando uma opção de pesquisa no menu de opções que é exibido ao clicar na seta para baixo no campo de pesquisa.

   ![imagem do menu searchproductsmenu](assets/searchproductsmenu.png)

   As opções de pesquisa incluem o seguinte:

   * TODAS - Pesquisa em todos os outros critérios de pesquisa, usando a lógica OU.
   * Nome
   * Marca
   * Categoria
   * ID
   * Mensagem

1. Agora é possível rolar pelos itens nos resultados da pesquisa para visualizar miniaturas e outras informações do produto.

   A ilustração a seguir mostra os resultados para &quot;bicicleta&quot; usando a opção Todos.

   ![Pesquisa no catálogo para bicicletas](/help/main/c-recommendations/c-products/assets/bike-results.png)

   O número que aparece ao lado de &quot;Produtos&quot; é o número de produtos que combinam com o termo de pesquisa, do total disponível no ambiente especificado.

   Observe que você pode usar a funcionalidade de preenchimento automático de pesquisa. Na ilustração a seguir, digitar &quot;bik&quot; retorna todos os produtos que contêm a palavra &quot;bike&quot;.

   ![Buscar preenchimento automático](/help/main/c-recommendations/c-products/assets/bike-results-2.png)

   >[!NOTE]
   >
   >Quando você faz uma pesquisa no catálogo em um atributo personalizado com um valor numérico, os resultados tratam o atributo personalizado como um tipo de sequência em vez de um valor numérico.
   >
   >No momento, não há nenhuma funcionalidade disponível que permita alterar o tipo de um atributo. Para fazer uma alteração, [abra um problema do cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) referenciando os atributos que precisam de alteração do tipo de sequência para numérico.

1. Você também pode usar filtros para encontrar o produto desejado. No exemplo a seguir, expandindo o [!UICONTROL Coleções] e selecionando &quot;Ferramentas de bicicleta&quot;, todas as ferramentas de bicicleta serão exibidas no catálogo.

   ![Ferramentas para bicicletas](/help/main/c-recommendations/c-products/assets/bike-results-3.png)

1. Você pode pesquisar mais na lista de resultados inserindo um termo de pesquisa, por exemplo, &quot;cadeia&quot;.

   ![Procurar cadeia](/help/main/c-recommendations/c-products/assets/bike-results-4.png)

### Executar uma pesquisa avançada {#advanced-search}

Você pode usar [!UICONTROL Pesquisa avançada] para refinar ainda mais os resultados da pesquisa ou salvar os resultados da pesquisa como uma [coleção](/help/main/c-recommendations/c-products/collections.md) ou [exclusão](/help/main/c-recommendations/c-products/exclusions.md).

1. Clique no botão **[!UICONTROL Pesquisa avançada]** link .

   ![Página Pesquisa avançada](/help/main/c-recommendations/c-products/assets/advances-search.png)

1. Use as listas suspensas para especificar o parâmetro, operador e valores para sua pesquisa.

1. (Opcional) Clique em **[!UICONTROL Adicionar regra]** para adicionar uma regra de pesquisa adicional.

   Cada regra de pesquisa adicional é unida com o operador AND.

1. Clique em **[!UICONTROL Pesquisa]**.

1. (Opcional) Clique em **[!UICONTROL Salvar como]**, depois clique em **[!UICONTROL Coleção]** ou **[!UICONTROL Exclusão]**.

   ![Salvar como opções](/help/main/c-recommendations/c-products/assets/save-as.png)

   Para obter mais informações, consulte [Criar uma coleção ou exclusão com base na Pesquisa avançada](#save-as) abaixo.

## Exibir os detalhes de um item

Você pode visualizar os detalhes de um item individual, incluindo ID, nome, mensagem, categoria e muito mais, visualizando os detalhes.

1. Clique em um item nos resultados da pesquisa para exibir seus detalhes.

   ![Detalhes do produto](/help/main/c-recommendations/c-products/assets/bike-results-5.png)

## Remover um item do catálogo

1. Clique em um item nos resultados da pesquisa para exibir seus detalhes.

1. Clique em **[!UICONTROL Remover do Catálogo]**.

1. Confirme se deseja remover o item.

Todas as informações sobre esse item são removidas do índice de catálogo. O item será incluído em seu catálogo somente se for adicionado novamente em um feed de dados. Um item excluído deve ser excluído separadamente dos feeds.

## Atualizar o catálogo

O índice do catálogo é criado automaticamente quando você carrega seu primeiro feed e é atualizado de acordo com o [programação especificada](/help/main/c-recommendations/c-products/feeds.md#steps).

O catálogo é atualizado automaticamente quando as atualizações são recebidas por meio de arquivos de feed, API ou atualizações de mbox. Normalmente, as atualizações são concluídas em uma hora. Se houver atualizações em andamento, será exibida a hora em que a atualização mais recente foi iniciada. Se não houver atualizações em andamento, será exibida a hora em que a atualização mais recente foi iniciada e finalizada.

## Criar uma coleção ou exclusão com base na Pesquisa avançada {#save-as}

Você pode criar [coleções](/help/main/c-recommendations/c-products/collections.md) ou [exclusões](/help/main/c-recommendations/c-products/exclusions.md) usando a Pesquisa avançada na página Pesquisa no catálogo ([!UICONTROL Recommendations] > [!UICONTROL Pesquisa no catálogo] > [!UICONTROL Pesquisa avançada]).

1. Executar um [pesquisa avançada](#advanced-search).

1. Clique em **[!UICONTROL Salvar como]**, depois clique em **[!UICONTROL Coleção]** ou **[!UICONTROL Exclusão]**.

   ![Salvar como opções](/help/main/c-recommendations/c-products/assets/save-as.png)

   >[!IMPORTANT]
   >
   >O [!UICONTROL Pesquisa avançada] A funcionalidade não diferencia maiúsculas de minúsculas; no entanto, os produtos retornados no momento do delivery são baseados na pesquisa que diferencia maiúsculas e minúsculas. Essa não correspondência pode levar à confusão. Certifique-se de considerar a diferenciação entre maiúsculas e minúsculas ao criar coleções ou exclusões com base em resultados usando o [!UICONTROL Pesquisa avançada] funcionalidade. Por exemplo, se você realiza uma busca para &quot;Feriado&quot;, essa busca inicial lista os resultados contendo &quot;Feriado&quot; e &quot;feriado&quot;. Em seguida, se você criar um catálogo com a intenção de encontrar produtos contendo &quot;feriado&quot;, somente os produtos contendo &quot;feriado&quot; serão exibidos. Os produtos contendo &quot;Feriado&quot; não serão exibidos. As exclusões são tratadas de maneira semelhante.

## Alterar o ambiente

[Ambientes](/help/main/administrating-target/environments.md) permite organizar seus sites e ambientes de pré-produção para fácil gerenciamento e relatórios separados.

1. Clique no link Environment .

   ![Link do ambiente](/help/main/c-recommendations/c-products/assets/environment.png)

1. Selecione o ambiente desejado.

## Modificar a página Pesquisa no catálogo (filtros e colunas)

Você pode modificar temporariamente os filtros e colunas disponíveis na variável [!UICONTROL Pesquisa no catálogo] página da sessão atual.

### Modificar filtros

Você pode adicionar outras facetas de filtro à [!UICONTROL Pesquisa no catálogo] página.

1. No **[!UICONTROL Filtros]** painel, clique em **[!UICONTROL Modificar]**.

   ![Link Modificar filtros](/help/main/c-recommendations/c-products/assets/modify-filters.png)

1. Selecione os aspectos de pesquisa desejados (ID, nome, mensagem etc.) e clique em **[!UICONTROL Salvar]**.

   ![Adicionar filtros](/help/main/c-recommendations/c-products/assets/add-filters.png)

Lembre-se de que as facetas de filtro adicionais estão disponíveis somente na sessão atual.

### Modificar colunas

Você pode modificar temporariamente as colunas ativas no [!UICONTROL Pesquisa no catálogo] página.

1. Clique no botão **[!UICONTROL Colunas]** link .

   ![Opções de colunas](/help/main/c-recommendations/c-products/assets/columns.png)

1. (Condicional) Para reorganizar a ordem das colunas ativas, arraste e solte as colunas no **[!UICONTROL Colunas ativas]** na ordem desejada.

1. (Condicional) Arraste e solte itens do **[!UICONTROL Colunas ativas]** para **[!UICONTROL Colunas Inativas]** (e vice-versa), conforme desejado.

   Você também pode clicar no ícone excluir ( x ) ao lado da coluna que deseja mover da seção ativa para inativa.

Lembre-se de que qualquer alteração feita se aplica somente à sessão atual.
