---
keywords: exclusões
description: Saiba como criar exclusões no [!DNL Target Recommendations] para impedir que produtos ou conteúdo sejam recomendados aos visitantes.
title: Como faço para usar exclusões nas atividades de [!UICONTROL Recomendações]?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
TQID: 'https://experienceleague.adobe.com/6-PWkqq5eXAwyLcGGbSqSZmFdJa85yU3x7FPNEt8-2o'
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
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 3883dc9752db0a2427f70cb3036fe060c440361a
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 6%
---
# Exclusões {#exclusions}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como criar e gerenciar exclusões no [!DNL Adobe Target Recommendations] para impedir que produtos ou conteúdo sejam recomendados aos visitantes.

>[!ENDSHADEBOX]

Uma exclusão é um subconjunto de produtos ou conteúdo que não devem ser recomendados aos visitantes. As exclusões estão disponíveis em toda a conta. Diferentemente das coleções, que são selecionadas para cada experiência quando uma atividade [!DNL Recommendations] é criada, as exclusões se aplicam a todas as atividades na conta, e nenhum grupo de exclusão pode ser atribuído durante a criação da atividade.

As exclusões normalmente são usadas para:

* Produtos descontinuados.
* Itens de um catálogo que não está mais disponível. Por exemplo, quando apenas o catálogo de outono e inverno deve estar presente online, nenhum item do catálogo de verão pode ser comprado.
* Itens que podem ser inadequados para recomendar na maioria das páginas ou telas (produtos para adultos, filmes NC-17 e assim por diante).
* Produtos com campos de metadados incompletos (miniatura, preço ou outros metadados importantes ausentes).
* Produtos que nunca devem ser recomendados, como um SKU que existe no sistema, mas não é um item comprável, ou um SKU falso que a equipe de controle de qualidade usa para simular uma compra sem solicitar nada.

>[!IMPORTANT]
>
>As regras de exclusão são aplicadas globalmente a todos os [ambientes](/help/main/administrating-target/environments.md).
>
>Para obter informações detalhadas, exemplos e cenários de caso de uso sobre regras de exclusão estáticas e dinâmicas, consulte [Usar regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules).

## Criar uma exclusão

As regras de exclusão são definidas uma vez e depois se aplicam a cada atividade [!DNL Recommendations] na conta.

1. Clique em **[!UICONTROL Recomendações]** > **[!UICONTROL Exclusões]** para exibir a lista de exclusões existentes.

   >[!NOTE]
   >
   >O &quot;Número de Itens&quot; relatado para cada exclusão na exibição de lista **[!UICONTROL Exclusões]** é o número de produtos que correspondem às regras da exclusão no [grupo de hosts](/help/main/administrating-target/hosts.md) (ambiente) padrão configurado no Recommendations. Consulte [Planejar e implementar [!DNL Recommendations]](https://experienceleague.adobe.com/pt-br/docs/target-dev/developer/recommendations){target=_blank} no *Guia do Desenvolvedor do Adobe Target* para obter informações sobre como alterar o grupo de hosts padrão.


1. Clique no ícone **[!UICONTROL Mostrar Filtros]** ( ![Mostrar ícone Filtros](/help/main/assets/icons/Filter.svg) ) e escolha o [ambiente](/help/main/administrating-target/environments.md) desejado na lista suspensa **[!UICONTROL Ambiente]** para visualizar o conteúdo da exclusão nesse ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

   ![Página de exclusões com o painel Filtros aberto e a lista Ambiente](../assets/exclusions_2.png)

1. Clique em **[!UICONTROL Criar exclusão]**.

   ![Página de exclusões com o botão Criar exclusão](../assets/exclusions_1.png)

1. Digite um **[!UICONTROL Nome]** de exclusão. Uma descrição opcional também pode ser inserida.

1. Use o construtor de regras para definir a exclusão.

   Selecione um parâmetro na lista **[!UICONTROL Regras]**, selecione um operador e insira um ou mais valores para identificar os produtos. Separe vários valores com vírgulas.

1. Clique em **[!UICONTROL Criar]**.

1. Clique no ícone Mais Ações ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado da exclusão desejada na lista e clique na opção apropriada: **[!UICONTROL Editar]**, **[!UICONTROL Copiar]** ou **[!UICONTROL Excluir]**.

   ![Lista de exclusões com o menu Mais Ações aberto, mostrando Editar, Copiar e Excluir](../assets/exclusions_3.png)

<!--
## Create an exclusion using Advanced Search

You can also create exclusions using [!UICONTROL Advanced Search] on the [Catalog Search](/help/main/c-recommendations/c-products/catalog-search.md#save-as) page ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]). 

![Save as dialog](/help/main/c-recommendations/c-products/assets/save-as.png)

After creating a search using "id > contains," for example, you can then click [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>The [!UICONTROL Advanced Search] functionality is case-insensitive; however, products returned at the time of delivery are based on case-sensitive search. This mismatch might lead to confusion. Ensure that you consider case-sensitivity when you create exclusions based on results using the Advanced Search functionality. For example, if you perform a search for "Holiday," that initial search lists results containing "Holiday" and "holiday." If you then create an exclusion with the intent to exclude products containing "holiday," only products containing "holiday" are excluded. Products containing "Holiday" are not excluded.
-->


## Vídeo de treinamento: criar coleções e exclusões no Recommendations (7:05) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar uma coleção
* Criar uma exclusão

>[!VIDEO](https://video.tv.adobe.com/v/27689)
