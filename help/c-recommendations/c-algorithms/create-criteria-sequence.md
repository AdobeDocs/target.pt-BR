---
keywords: sequência de critérios, vários critérios, algoritmos, critérios, critérios de recomendações, sequência, limite de itens retornados, controle de nível de slot, slot
description: Saiba como definir sequências de até cinco critérios para exercer maior controle dos itens que aparecem em suas atividades de Adobe [!DNL Target] Recommendations.
title: Como faço para criar sequências de critérios no Recommendations?
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 34%

---

# ![PREMIUM](/help/assets/premium.png) Criar sequência de critérios

Use sequências de até cinco critérios para exercer maior controle dos itens que aparecem em suas atividades do [!UICONTROL Recommendations. ] Também é possível limitar o número de itens retornados (às vezes chamados de &quot;controle de nível de slot&quot;).

>[!NOTE]
>
>As sequências de critérios não podem ser usadas com as [!UICONTROL atividades do Recommendations] criadas antes da versão de outubro de 2016 [!DNL Target Premium].

Para criar uma sequência de critérios, você deve primeiro criar o critério que deseja incluir na sequência. Consulte [Criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) para obter mais informações.

Ao usar uma sequência de critérios, você pode fornecer recomendações direcionadas adicionais, em vez de usar recomendações de backup mais genéricas, quando um critério não retorna resultados o suficiente para preencher seu design. Normalmente, uma sequência de critérios continuará do direcionamento mais específico, que pode retornar menos resultados, para o direcionamento mais geral, que geralmente retorna mais resultados.

Suas sequências de critérios podem variar em ordem, dependendo do tipo de página, conforme mostrado nos exemplos a seguir:

| Tipo de página | Ordem de sequência possível |
| --- | --- |
| Página do produto | <ol><li>Baseado no item atual, da mesma marca</li><li>Baseado no item atual, de todas as marcas</li><li>Baseado na semelhança de conteúdo</li><li>Baseado nos mais vendidos</li><li>Baseado nos itens mais visualizados por todo site</li></ol> |
| Página inicial | <ol><li>Baseado na última compra do visitante </li><li>Baseado no item favorito do visitante</li><li>Baseado na categoria favorita do visitante</li><li>Baseado nos mais vendidos</li><li>Baseado nos mais visualizados por todo site</li></ol> |

## Criar uma sequência de critérios

Você cria sequências de critérios a partir da tela [!UICONTROL Criar sequência de critérios].

Existem vários meios de alcançar a tela [!UICONTROL Criar sequência de critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela de biblioteca **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**, clique em **[!UICONTROL Criar critério]** > **[!UICONTROL Criar sequência de critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!UICONTROL Recommendations].
* Ao criar uma atividade [!UICONTROL Recommendations], na tela Selecionar critérios , clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Criar sequência de critérios]**. Você terá a opção de salvar sua nova sequência de critérios para uso com outras atividades do [!UICONTROL Recommendations].
* Ao editar uma atividade [!UICONTROL Recommendations], clique em uma caixa [!UICONTROL Localização do Recommendations] na página e selecione **[!UICONTROL Alterar critérios]**. Na tela [!UICONTROL Selecionar critério], clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Criar sequência de critérios]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!UICONTROL Recommendations].

As etapas a seguir pressupõem que você acesse a tela [!UICONTROL Criar sequência de critérios] usando o primeiro método: a tela da biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar sequência de critérios]**.

   ![](assets/CreateCriteriaSequence.png)

1. Preencha as informações na seção [Informações básicas](/help/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Na seção **[!UICONTROL Sequência de critérios]**, clique em **[!UICONTROL Adicionar critérios]**.

   A ordem de sequência define a ordem em que um design é preenchido. Se o Critério 1 não tiver recomendações suficientes para preencher seu design, os slots restantes serão preenchidos com o Critério 2 e assim por diante.

   ![Adicionar critérios](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. Na tela [!UICONTROL Selecionar critério], selecione um critério e clique em **[!UICONTROL Adicionar]**.

   Você pode usar a caixa Pesquisar e os menus suspensos do filtro para encontrar os critérios desejados.

   ![Selecione o critério](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. (Opcional) Deslize o **[!UICONTROL Limite o número de itens retornados]** para a posição &quot;ativada&quot; e especifique o número de itens (entre 1 e 50).

   ![Limitar o número de itens retornados](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   Para ajudar você a entender o valor da opção [!UICONTROL Limit the number of items return] (às vezes chamada de &quot;slot level control&quot;), considere os seguintes casos de uso:

   * **Caso de uso 1**: Você deseja ter uma combinação de diferentes tipos de itens em uma única bandeja de recomendações. Por exemplo, você deseja mostrar uma mistura de ternos (casacos) e tampas (camisas, T-shirts). Para fazer isso, use uma Coleção para a atividade que inclui todos os tipos de produto potenciais desejados em qualquer slot do design. Em seguida, configure seus primeiros critérios com um filtro estático limitando os critérios para incluir somente desgaste externo e configure seu segundo critério com um filtro estático limitando os critérios para incluir somente os menus. Finalmente, adicione ambos os critérios a uma sequência de critérios e limite o primeiro critério a dois slots.

      A bandeja de recomendações pode ter esta aparência no site:

      ![Bandeja de recomendações de Produtos em destaque](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Caso de uso 2**: Você deseja uma combinação de itens alternativos e complementares. Configure um critério para usar um algoritmo visualizado/visualizado e um filtro dinâmico que limite os itens recomendados para a categoria do item atual. Configure o segundo critério para usar um algoritmo visualizado/comprado e usar um filtro dinâmico que inclua apenas itens recomendados que não correspondam à categoria do item atual. Finalmente, adicione ambos os critérios a uma sequência e limite o primeiro critério a dois slots.

1. Continue adicionando critérios adicionais à sua sequência. Você pode adicionar até cinco critérios em uma sequência.

1. Ative [Opções de Conteúdo de Backup](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Clique em **[!UICONTROL Salvar]**.

   A sequência de critérios irá aparecer na lista de critérios.

   Para obter mais informações sobre as opções de lógica de recomendação, consulte [Critérios](/help/c-recommendations/c-algorithms/algorithms.md).

## Vídeo de treinamento: criar critérios no Recommendations (12:33)  ![Selo do tutorial](/help/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
