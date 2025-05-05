---
keywords: exclusões
description: Saiba como criar exclusões no [!DNL Target Recommendations] para impedir que produtos ou conteúdo sejam recomendados aos visitantes.
title: Como faço para usar exclusões em atividades [!UICONTROL Recommendations]?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 14%

---

# Exclusões

Crie uma exclusão em [!DNL Adobe Target Recommendations] para impedir que produtos ou conteúdo sejam recomendados aos visitantes. Uma exclusão é um subconjunto de produtos ou conteúdo que não devem ser recomendados aos visitantes.

As exclusões estão disponíveis em toda a conta. Ao contrário das coleções, em que você especifica uma coleção específica para cada experiência ao criar uma atividade [!UICONTROL Recommendations], as exclusões se aplicam a todas as atividades na conta. Não há opção para atribuir um grupo de exclusão durante a criação da atividade.

Alguns exemplos de vezes que você usaria exclusões incluem:

* Produtos descontinuados.
* O catálogo de outono e inverno agora é o único catálogo que deve estar presente online. Nenhum item do catálogo de Verão está mais disponível para compra.
* Itens que podem ser inadequados para recomendar na maioria das páginas ou telas (produtos para adultos, filmes NC-17 e assim por diante).
* Produtos com campos de metadados incompletos (miniatura, preço ou outros metadados importantes ausentes).
* Produtos que nunca devem ser recomendados (talvez exista uma SKU no sistema para algo, mas ela não é um item que pode ser comprado). Ou talvez seja um SKU falso para a equipe de controle de qualidade simular uma compra sem realmente solicitar algo e assim por diante).

>[!IMPORTANT]
>
>As regras de exclusão são aplicadas globalmente a todos os [ambientes](/help/main/administrating-target/environments.md).
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Usar as regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Criar uma exclusão

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** para exibir a lista de exclusões existentes.

   O &quot;Número de Itens&quot; relatado para cada exclusão na exibição de lista [!UICONTROL Exclusions] é o número de produtos que correspondem às regras da exclusão no [grupo de hosts](/help/main/administrating-target/hosts.md) (ambiente) padrão configurado no Recommendations. Consulte [Planejar e implementar [!DNL Recommendations]](https://experienceleague.adobe.com/pt-br/docs/target-dev/developer/recommendations){target=_blank} no *Guia do Desenvolvedor do Adobe Target* para obter informações sobre como alterar o grupo de hosts padrão.

1. (Condicional) Clique no ícone **[!UICONTROL Show Filters]** ( ![Ícone Mostrar filtros](/help/main/assets/icons/Filter.svg) ) e escolha o [ambiente](/help/main/administrating-target/environments.md) desejado na lista suspensa **[!UICONTROL Environment]** ao criar (ou atualizar) uma exclusão para visualizar o conteúdo da exclusão nesse ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

1. Clique em **[!UICONTROL Create Exclusion]**.

1. Digite uma exclusão **[!UICONTROL Name]** e insira uma descrição opcional.

1. Use o criador de regras para criar suas exclusões.

   Selecione um parâmetro na lista [!UICONTROL Rules], selecione um operador e insira um ou mais valores para identificar os produtos. Separe vários valores com vírgulas.

1. Clique em **[!UICONTROL Create]**.

<!-- ## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded. -->

## Editar, copiar ou excluir uma exclusão

Clique no ícone Mais Ações ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado da exclusão desejada na lista e clique no ícone apropriado: [!UICONTROL Edit], [!UICONTROL Copy] ou [!UICONTROL Delete].

Você pode copiar uma exclusão existente para criar uma exclusão duplicada que poderá ser modificada. Essa opção permite criar uma exclusão semelhante com menos esforço.

Esteja ciente de que as exclusões estão disponíveis em toda a conta. Considere esse aviso antes de excluir uma exclusão. As exclusões excluídas não podem ser recuperadas.

## Vídeo de treinamento: criar coleções e exclusões no Recommendations (7:05) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar uma coleção
* Criar uma exclusão

>[!VIDEO](https://video.tv.adobe.com/v/35372?captions=por_br)
