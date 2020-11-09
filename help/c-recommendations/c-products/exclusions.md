---
keywords: exclusions
description: Crie uma exclusão [!DNL Adobe Target Recommendations] para impedir que produtos ou conteúdo sejam recomendados para visitantes.
title: Exclusões no Adobe Target
feature: entities
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 45%

---


# Exclusões{#exclusions}

Crie uma exclusão para impedir que produtos ou conteúdo sejam recomendados para visitantes. [!DNL Adobe Target Recommendations] Uma exclusão é um subconjunto de produtos ou conteúdo que não deve ser recomendado aos visitantes.

As exclusões estão disponíveis em toda a conta. Diferentemente das coleções, onde você especifica uma coleção específica para cada experiência ao criar uma atividade [!UICONTROL Recommendations] , as exclusões se aplicam a todas as atividades na conta. Não há opção para atribuir um grupo de exclusão durante a criação da atividade.

Alguns exemplos de vezes que você usaria exclusões incluem:

* Produtos que foram descontinuados
* O catálogo de outono/inverno agora é o único que deve estar presente online. Nenhum item do catálogo de verão está mais disponível para compra.
* Itens que podem não ser recomendados na maioria das páginas/telas (produtos para adultos, filmes NC-17 etc.)
* Produtos com campos de metadados incompletos (miniatura ausente, preço ou outros metadados importantes)
* Produtos que nunca devem ser recomendados (talvez exista um SKU no sistema para algo, mas não é um item comprável, ou talvez seja um SKU falso para a equipe de controle de qualidade simular uma compra sem solicitar algo, etc)

>[!IMPORTANT]
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Usar as regras de inclusão estática e dinâmica](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Criar uma exclusão

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusões]** para exibir a lista de exclusões existentes.

   ![](assets/exclusions_list.png)

   O “Número de itens” relatado para cada exclusão na exibição de lista das [!UICONTROL Exclusões] é o número de produtos que correspondem às regras da exclusão no [grupo de hosts](/help/administrating-target/hosts.md) (ambiente) padrão configurado no Recommendations. Consulte [Configurações](/help/c-recommendations/plan-implement.md#concept_C1E1E2351413468692D6C21145EF0B84) para alterar o grupo de hosts padrão.

1. Clique em **[!UICONTROL Criar exclusão]**.

1. (Condicional) Escolha um ambiente no filtro **[!UICONTROL Ambiente]** ao criar (ou atualizar) uma exclusão para visualizar o conteúdo da exclusão no ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

   ![Criar exclusão](/help/c-recommendations/c-products/assets/CreateExclusion.png)

1. Digite um **[!UICONTROL Nome]** de exclusão e insira uma descrição opcional.

1. Use o criador de regras para criar suas exclusões.

   Selecione um parâmetro na lista Regras, selecione um operador e, em seguida, insira um ou mais valores para identificar os produtos. Separe vários valores com vírgulas.

1. Clique em **[!UICONTROL Salvar]**.

## Criar uma exclusão usando a Pesquisa avançada

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Caixa de diálogo Salvar como](/help/c-recommendations/c-products/assets/save-as.png)

Após criar uma pesquisa usando &quot;id > contains&quot; Por exemplo, você pode clicar em [!UICONTROL Salvar como] > [!UICONTROL Exclusão].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. Essa não correspondência pode levar à confusão. Certifique-se de considerar a sensibilidade a maiúsculas e minúsculas quando você cria exclusões baseadas em resultados usando a funcionalidade Pesquisa avançada. Por exemplo, se você realiza uma busca para &quot;Feriado&quot;, essa busca inicial lista os resultados contendo &quot;Feriado&quot; e &quot;feriado&quot;. Em seguida, se você criar uma exclusão com a intenção de excluir produtos contendo &quot;feriado&quot;, somente os produtos contendo &quot;feriado&quot; são excluídos. Os produtos contendo &quot;Feriado&quot; não são excluídos.

## Editar, copiar ou excluir uma exclusão

Passe o mouse sobre a exclusão desejada na lista e clique no ícone apropriado: editar, copiar ou excluir.

![Ícones de flutuação para uma exclusão](/help/c-recommendations/c-products/assets/hover-exclusions.png)

Você pode copiar uma exclusão existente para criar uma exclusão de duplicado que pode ser modificada. Isso permite criar uma exclusão semelhante com menos esforço.

Esteja ciente de que as exclusões estão disponíveis em toda a conta. Considere isso antes de excluir uma exclusão. As exclusões excluídas não podem ser recuperadas.

## Training video: Create collections and exclusions in Recommendations (7:05) ![Tutorial badge](/help/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar uma coleção
* Criar uma exclusão

>[!VIDEO](https://video.tv.adobe.com/v/27689)