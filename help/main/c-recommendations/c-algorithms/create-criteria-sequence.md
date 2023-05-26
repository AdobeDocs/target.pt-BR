---
keywords: sequência de critérios;vários critérios;algoritmos;critérios;critérios de recomendações;sequência;número limite de itens retornados;controle de nível de slot;slot
description: Saiba como definir sequências de até cinco critérios para exercer maior controle dos itens que aparecem no Adobe [!DNL Target] Atividades do Recommendations.
title: Como criar sequências de critérios no Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '834'
ht-degree: 34%

---

# Criar sequências de critérios

Use sequências de até cinco critérios para exercer maior controle dos itens que aparecem em suas atividades do [!UICONTROL Recommendations. ] Você também pode limitar o número de itens retornados (às vezes chamados de &quot;controle no nível do slot&quot;).

>[!NOTE]
>
>As sequências de critérios não podem ser usadas com as [!UICONTROL atividades do Recommendations] criadas antes da versão de outubro de 2016 [!DNL Target Premium].

Para criar uma sequência de critérios, você deve primeiro criar o critério que deseja incluir na sequência. Consulte [Criar critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) para obter mais informações.

Ao usar uma sequência de critérios, você pode fornecer recomendações direcionadas adicionais, em vez de usar recomendações de backup mais genéricas, quando um critério não retorna resultados o suficiente para preencher seu design. Normalmente, uma sequência de critérios prosseguirá de um direcionamento mais específico, que pode retornar menos resultados, para um direcionamento mais geral, que geralmente retorna mais resultados.

As sequências de critérios podem variar em ordem, dependendo do tipo de página, como mostrado nos exemplos a seguir:

| Tipo de página | Ordem de sequência possível |
| --- | --- |
| Página do produto | <ol><li>Baseado no item atual, da mesma marca</li><li>Baseado no item atual, de todas as marcas</li><li>Baseado na semelhança de conteúdo</li><li>Baseado nos mais vendidos</li><li>Baseado nos itens mais visualizados por todo site</li></ol> |
| Home page | <ol><li>Baseado na última compra do visitante </li><li>Baseado no item favorito do visitante</li><li>Baseado na categoria favorita do visitante</li><li>Baseado nos mais vendidos</li><li>Baseado nos mais visualizados por todo site</li></ol> |

## Criar uma sequência de critérios

Crie sequências de critérios a partir da variável [!UICONTROL Criar sequência de critérios] tela.

Existem vários meios de alcançar a tela [!UICONTROL Criar sequência de critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela de biblioteca **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**, clique em **[!UICONTROL Criar critério]** > **[!UICONTROL Criar sequência de critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!UICONTROL Recommendations].
* Ao criar uma [!UICONTROL Recommendations] atividade, na tela Selecionar critério, clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Criar sequência de critérios]**. Você terá a opção de salvar sua nova sequência de critérios para uso com outras atividades do [!UICONTROL Recommendations].
* Ao editar um [!UICONTROL Recommendations] atividade, clique em uma [!UICONTROL Localização do Recommendations] na sua página e selecione **[!UICONTROL Alterar critérios]**. Na tela [!UICONTROL Selecionar critério], clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Criar sequência de critérios]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!UICONTROL Recommendations].

As etapas a seguir pressupõem que você acesse o [!UICONTROL Criar sequência de critérios] usando o primeiro método: a variável **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]** tela da biblioteca.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar sequência de critérios]**.

   ![Imagem CreateCriteriaSequence](assets/CreateCriteriaSequence.png)

1. Preencha as informações em [Informações básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info) seção.

1. No **[!UICONTROL Sequência de critérios]** clique em **[!UICONTROL Adicionar critério]**.

   A ordem de sequência define a ordem de preenchimento de um design. Se o Critério 1 não tiver recomendações suficientes para preencher o seu design, os slots restantes serão preenchidos com o Critério 2 e assim por diante.

   ![Adicionar critério](/help/main/c-recommendations/c-algorithms/assets/add-criteria.png)

1. No [!UICONTROL Selecionar critério] , selecione um critério e clique em **[!UICONTROL Adicionar]**.

   Você pode usar a caixa Pesquisa e os menus suspensos de filtro para encontrar os critérios desejados.

   ![Selecione o critério](/help/main/c-recommendations/c-algorithms/assets/select-criteria.png)

1. (Opcional) Deslize o **[!UICONTROL Limitar o número de itens retornados]** alterne para a posição &quot;on&quot; e especifique o número de itens (entre 1 e 50).

   ![Limitar a alternância de número de itens retornados](/help/main/c-recommendations/c-algorithms/assets/limit-number.png)

   Para ajudar você a entender o valor do [!UICONTROL Limitar o número de itens retornados] (às vezes chamada de &quot;controle de nível de slot&quot;) considere os seguintes casos de uso:

   * **Caso de uso 1**: você deseja ter uma combinação de diferentes tipos de itens em uma única bandeja de recomendações. Por exemplo, você quer mostrar uma mistura de roupas externas (jaquetas) e tops (camisas, camisetas). Para isso, use uma Coleção para a atividade que inclua todos os tipos de produtos em potencial que você deseja em qualquer espaço em seu design. Em seguida, configure os primeiros critérios com um filtro estático que limita os critérios para incluir somente roupas externas e configure os segundos critérios com um filtro estático que limita os critérios para incluir somente tops. Por fim, adicione ambos os critérios a uma sequência de critérios e limite os primeiros critérios a 2 slots.

      A bandeja de recomendações pode ter esta aparência em seu site:

      ![Bandeja de recomendações de produtos em destaque](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Caso de uso 2**: você deseja uma combinação de itens alternativos e complementares. Configure um critério para usar um algoritmo exibido/exibido e use um filtro dinâmico que limite os itens recomendados para a categoria do item atual. Configure os segundos critérios para usar um algoritmo exibido/comprado e usar um filtro dinâmico que inclua apenas itens recomendados que não correspondam à categoria do item atual. Por fim, adicione ambos os critérios a uma sequência e limite os primeiros critérios a 2 slots.

1. Continue adicionando critérios adicionais à sequência. Você pode adicionar até cinco critérios em uma sequência.

1. Ativar [Opções de conteúdo de backup](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Clique em **[!UICONTROL Salvar]**.

   A sequência de critérios irá aparecer na lista de critérios.

   Para obter mais informações sobre as opções de lógica de recomendação, consulte [Critérios](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Vídeo de treinamento: criar critérios no Recommendations (12:33) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
