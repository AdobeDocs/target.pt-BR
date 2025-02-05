---
keywords: sequência de critérios;vários critérios;algoritmos;critérios;critérios de recomendações;sequência;número limite de itens retornados;controle de nível de slot;slot
description: Saiba como definir sequências de até cinco critérios para exercer maior controle dos itens que aparecem em suas atividades do Recommendations.
title: Como criar sequências de critérios no Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 5366c86c-7685-478b-a621-9b3f24296ab7
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '751'
ht-degree: 18%

---

# Criar sequências de critérios

Use sequências de até cinco critérios para exercer maior controle dos itens que aparecem em suas atividades de [!DNL Adobe Target] [!UICONTROL Recommendations]. Você também pode limitar o número de itens retornados (às vezes chamados de &quot;controle no nível do slot&quot;).

>[!NOTE]
>
>As sequências de critérios não podem ser usadas com [!UICONTROL Recommendations] atividades criadas antes da Versão de outubro de 2016 do [!DNL Target Premium].

Para criar uma sequência de critérios, você deve primeiro criar o critério que deseja incluir na sequência. Consulte [Criar critérios](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md) para obter mais informações.

Ao usar uma sequência de critérios, você pode fornecer recomendações direcionadas adicionais, em vez de usar recomendações de backup mais genéricas, quando um critério não retorna resultados o suficiente para preencher seu design. Normalmente, uma sequência de critérios prossegue a partir de um direcionamento mais específico, que pode retornar menos resultados, para um direcionamento mais geral, que geralmente retorna mais resultados.

As sequências de critérios podem variar em ordem, dependendo do tipo de página, como mostrado nos exemplos a seguir:

| Tipo de página | Ordem de sequência possível |
| --- | --- |
| Página do produto | <ol><li>Com base no item atual, da mesma marca</li><li>Baseado no item atual, de todas as marcas</li><li>Baseado na semelhança de conteúdo</li><li>Baseado nos mais vendidos</li><li>Baseado nos itens mais visualizados por todo site</li></ol> |
| Home page | <ol><li>Baseado na última compra do visitante </li><li>Baseado no item favorito do visitante</li><li>Baseado na categoria favorita do visitante</li><li>Baseado nos mais vendidos</li><li>Baseado nos mais visualizados por todo site</li></ol> |

## Criar uma sequência de critérios

Você cria sequências de critérios da tela [!UICONTROL Create Criteria Sequence].

Há várias maneiras de acessar a tela [!UICONTROL Create Criteria Sequence]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela da biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**, clique em **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!UICONTROL Recommendations].
* Ao criar uma atividade [!UICONTROL Recommendations], na tela [!UICONTROL Select Criteria], clique em **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Você tem a opção de salvar sua nova sequência de critérios para uso com outras atividades do [!UICONTROL Recommendations].
* Quando você editar uma atividade [!UICONTROL Recommendations], clique em uma caixa [!UICONTROL Recommendations Location] na sua página e selecione **[!UICONTROL Change Criteria]**. Na tela [!UICONTROL Select Criteria], clique em **[!UICONTROL Create New]** > **[!UICONTROL Create Criteria Sequence]**. Você tem a opção de salvar seu novo critério para uso com outras atividades do [!UICONTROL Recommendations].

As etapas a seguir consideram que você acesse a tela [!UICONTROL Create Criteria Sequence] usando o primeiro método: a tela de biblioteca **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]**.

1. Clique em **[!UICONTROL Create Criteria]** > **[!UICONTROL Create Criteria Sequence]**.

1. Preencha as informações na seção [Informações Básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Na seção **[!UICONTROL Criteria Sequence]**, clique no sinal de adição ( + ) para adicionar uma ou mais sequências de critérios.

   A ordem de sequência define a ordem de preenchimento de um design. Se o Critério 1 não tiver recomendações suficientes para preencher o seu design, os slots restantes serão preenchidos com o Critério 2 e assim por diante.

1. Na tela [!UICONTROL Select Criteria], selecione um critério e clique em **[!UICONTROL Save]**.

   Você pode usar a caixa [!UICONTROL Search] e a opção de filtro para encontrar os critérios desejados.

1. (Opcional) Deslize o botão **[!UICONTROL Limit the number of items returned]** para a posição &quot;ligado&quot; e especifique o número de itens (entre 1 e 50).

   Para ajudá-lo a entender o valor da opção [!UICONTROL Limit the number of items returned] (às vezes chamada de &quot;controle no nível do slot&quot;), considere os seguintes casos de uso:

   * **Caso de uso 1**: você deseja ter uma combinação de diferentes tipos de itens em uma única bandeja de recomendações. Por exemplo, você quer mostrar uma mistura de roupas externas (jaquetas) e tops (camisas, camisetas). Para isso, use uma Coleção para a atividade que inclua todos os tipos de produtos em potencial que você deseja em qualquer espaço em seu design. Em seguida, configure os primeiros critérios com um filtro estático que limita os critérios para incluir somente roupas externas e configure os segundos critérios com um filtro estático que limita os critérios para incluir somente tops. Por fim, adicione ambos os critérios a uma sequência de critérios e limite os primeiros critérios a 2 slots.

     A bandeja de recomendações pode ter esta aparência em seu site:

     ![Bandeja de recomendações de Produtos em Destaque](/help/main/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Caso de uso 2**: você deseja uma combinação de itens alternativos e complementares. Configure um critério para usar um algoritmo exibido/exibido e use um filtro dinâmico que limite os itens recomendados para a categoria do item atual. Configure os segundos critérios para usar um algoritmo exibido/comprado e usar um filtro dinâmico que inclua apenas itens recomendados que não correspondam à categoria do item atual. Por fim, adicione ambos os critérios a uma sequência e limite os primeiros critérios a 2 slots.

1. Continue adicionando critérios adicionais à sequência. Você pode adicionar até cinco critérios em uma sequência.

1. Habilitar [opções de Conteúdo de Backup](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

1. Clique em **[!UICONTROL Create]**.

   A sequência de critérios é exibida na lista [!UICONTROL Criteria].

   Para obter mais informações sobre as opções de lógica de recomendação, consulte [Critérios](/help/main/c-recommendations/c-algorithms/algorithms.md).
