---
keywords: exclusões
description: Saiba como criar exclusões no Adobe [!DNL Target] Recommendations para impedir que produtos ou conteúdo sejam recomendados aos visitantes.
title: Como usar exclusões nas atividades do Recommendations?
feature: Recommendations
exl-id: e41487c7-6d47-4958-8e4b-616a2ad56b3c
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 29%

---

# Exclusões

Crie uma exclusão em [!DNL Adobe Target Recommendations] para impedir que produtos ou conteúdo sejam recomendados aos visitantes. Uma exclusão é um subconjunto de produtos ou conteúdo que não devem ser recomendados aos visitantes.

As exclusões estão disponíveis em toda a conta. Ao contrário das coleções, em que você especifica uma coleção específica para cada experiência ao criar uma atividade [!UICONTROL Recommendations], as exclusões se aplicam a todas as atividades na conta. Não há opção para atribuir um grupo de exclusão durante a criação da atividade.

Alguns exemplos de vezes que você usaria exclusões incluem:

* Produtos que foram descontinuados
* O catálogo de outono/inverno agora é o único catálogo que deve estar presente online. Nenhum item do catálogo de Verão está mais disponível para compra.
* Itens que podem ser inadequados para recomendar na maioria das páginas/telas (produtos para adultos, filmes NC-17, etc.)
* Produtos com campos de metadados incompletos (miniatura, preço ou outros metadados importantes ausentes)
* Produtos que nunca devem ser recomendados (talvez exista um SKU no sistema para algo, mas ele não é um item comprável ou talvez seja um SKU falso para a equipe de controle de qualidade simular uma compra sem realmente solicitar algo etc.)

>[!IMPORTANT]
>
>As regras de exclusão são aplicadas globalmente a todos os ambientes.
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Usar as regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

## Criar uma exclusão

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Exclusions]** para exibir a lista de exclusões existentes.

   ![imagem da lista de exclusões](assets/exclusions_list.png)

   O &quot;Número de Itens&quot; relatado para cada exclusão na exibição de lista [!UICONTROL Exclusions] é o número de produtos que correspondem às regras da exclusão no [grupo de hosts](/help/main/administrating-target/hosts.md) (ambiente) padrão configurado no Recommendations. Consulte [Configurações](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html){target=_blank} para alterar o grupo de hosts padrão.

1. Clique em **[!UICONTROL Create Exclusion]**.

1. (Condicional) Escolha um ambiente no filtro **[!UICONTROL Environment]** ao criar (ou atualizar) uma exclusão para visualizar o conteúdo da exclusão no ambiente. Por padrão, os resultados do grupo de hosts padrão são exibidos.

   ![Criar exclusão](/help/main/c-recommendations/c-products/assets/CreateExclusion.png)

1. Digite uma exclusão **[!UICONTROL Name]** e insira uma descrição opcional.

1. Use o criador de regras para criar suas exclusões.

   Selecione um parâmetro na lista Regras, selecione um operador e, em seguida, insira um ou mais valores para identificar os produtos. Separe vários valores com vírgulas.

1. Clique em **[!UICONTROL Save]**.

## Criar uma exclusão usando a Pesquisa avançada

Você também pode criar exclusões usando [!UICONTROL Advanced Search] na página [Pesquisa de Catálogo](/help/main/c-recommendations/c-products/catalog-search.md#save-as) ( [!UICONTROL Recommendations] > [!UICONTROL Catalog Search] > [!UICONTROL Advanced Search]).

![Salvar como caixa de diálogo](/help/main/c-recommendations/c-products/assets/save-as.png)

Após criar uma pesquisa usando &quot;id > contains&quot; Por exemplo, você pode clicar em [!UICONTROL Save As] > [!UICONTROL Exclusion].

>[!IMPORTANT]
>
>A funcionalidade [!UICONTROL Advanced Search] não diferencia maiúsculas de minúsculas; no entanto, os produtos retornados no momento da entrega baseiam-se em pesquisa que diferencia maiúsculas de minúsculas. Essa não correspondência pode levar à confusão. Certifique-se de considerar a sensibilidade a maiúsculas e minúsculas quando você cria exclusões baseadas em resultados usando a funcionalidade Pesquisa avançada. Por exemplo, se você realiza uma busca para &quot;Feriado&quot;, essa busca inicial lista os resultados contendo &quot;Feriado&quot; e &quot;feriado&quot;. Em seguida, se você criar uma exclusão com a intenção de excluir produtos contendo &quot;feriado&quot;, somente os produtos contendo &quot;feriado&quot; são excluídos. Os produtos contendo &quot;Feriado&quot; não são excluídos.

## Editar, copiar ou excluir uma exclusão

Passe o mouse sobre a exclusão desejada na lista, em seguida, clique no ícone apropriado: editar, copiar ou excluir.

![Focalizar ícones para uma exclusão](/help/main/c-recommendations/c-products/assets/hover-exclusions.png)

Você pode copiar uma exclusão existente para criar uma exclusão duplicada que poderá ser modificada. Isso permite criar uma exclusão semelhante com menos esforço.

Esteja ciente de que as exclusões estão disponíveis em toda a conta. Considere isso antes de excluir uma exclusão. As exclusões excluídas não podem ser recuperadas.

## Vídeo de treinamento: criar coleções e exclusões no Recommendations (7:05) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar uma coleção
* Criar uma exclusão

>[!VIDEO](https://video.tv.adobe.com/v/27689)
