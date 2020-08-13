---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria
description: Use sequências de até cinco critérios para exercer maior controle dos itens que aparecem em suas atividades do Recommendations.
title: Criar sequências de critérios
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 99%

---


# ![PREMIUM](/help/assets/premium.png) Criar sequência de critérios{#create-criteria-sequences}

Use sequências de até cinco critérios para exercer maior controle dos itens que aparecem em suas atividades do Recommendations.

>[!NOTE]
>
>As sequências de critérios não podem ser usadas com as [!UICONTROL atividades do Recommendations] criadas antes da versão de outubro de 2016 [!DNL Target Premium].

Para criar uma sequência de critérios, você deve primeiro criar o critério que deseja incluir na sequência. Consulte [Criação de critérios](../../c-recommendations/c-algorithms/create-new-algorithm.md#task_8A9CB465F28D44899F69F38AD27352FE) para obter mais informações.

Ao usar uma sequência de critérios, você pode fornecer recomendações direcionadas adicionais, em vez de usar recomendações de backup mais genéricas, quando um critério não retorna resultados o suficiente para preencher seu design. Tipicamente, uma sequência de critérios irá prosseguir do direcionamento mais específico, que pode retornar menos resultados, para o direcionamento mais geral, que geralmente retorna mais resultados.

Por exemplo, uma sequência de critérios de uma página de produto pode seguir esta ordem:

1. Baseado no item atual, da mesma marca
1. Baseado no item atual, de todas as marcas
1. Baseado na semelhança de conteúdo
1. Baseado nos mais vendidos
1. Baseado nos itens mais visualizados por todo site

Uma sequência de critérios de uma página inicial pode seguir esta ordem:

1. Baseado na última compra do visitante
1. Baseado no item favorito do visitante
1. Baseado na categoria favorita do visitante
1. Baseado nos mais vendidos
1. Baseado nos mais visualizados por todo site

Existem vários meios de alcançar a tela [!UICONTROL Criar sequência de critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Quando você criar uma atividade de [!UICONTROL Recomendações], clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Criar sequência de critérios]** na tela [!UICONTROL Selecionar critério]. Você terá a opção de salvar sua nova sequência de critérios para uso com outras atividades do [!UICONTROL Recommendations].
* Quando você editar uma atividade de [!UICONTROL Recommendations], clique em uma caixa de [!UICONTROL Localização das Recommendations] na sua página e selecione **[!UICONTROL Alterar critério]**. Na tela [!UICONTROL Selecionar critério], clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Criar sequência de critérios]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!UICONTROL Recommendations].
* Na tela de biblioteca **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**, clique em **[!UICONTROL Criar critério]** > **[!UICONTROL Criar sequência de critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!UICONTROL Recommendations].

1. Clique em **[!UICONTROL Criar critérios]** ou **[!UICONTROL Criar novo]**.

   ![Criar novos critérios](/help/c-recommendations/c-algorithms/assets/button_CreateCriteria_new.png)

1. Selecione **[!UICONTROL Criar sequência de critérios]**.

   ![](assets/CreateCriteriaSequence.png)

1. Digite um **[!UICONTROL Nome]** para a sequência.

   Este é o nome &quot;interno&quot; usado para descrever a sequência de critérios. Os visitantes do seu site não verão este nome.
1. Digite um **[!UICONTROL Título de exibição genérico]** aberto ao público para aparecer na página, se vários critérios na sequência forem usados para preencher o design do [!UICONTROL Recommendations].

   Por exemplo, você pode querer substituir &quot;Clientes que viram isto também viram...&quot; por &quot;Recomendado para você&quot; se o design puder incluir itens baseados em mais de uma chave de [!UICONTROL recomendações].
1. Digite uma breve **[!UICONTROL Descrição]** da sequência de critérios.

   A descrição deve ajudar a identificar a sequência de critérios e pode incluir informações sobre seu propósito.
1. Selecione um **[!UICONTROL negócio vertical]**.

   Seu negócio vertical padrão aparece automaticamente.
1. Selecione um **[!UICONTROL Tipo de página]**.

   Você pode selecionar vários tipos de página.

   Juntos, o negócio vertical e tipos de página são usados para categorizar sua sequência de critérios salva, tornando mais fácil o reuso de sequências para outras atividades do [!UICONTROL Recommendations].
1. Defina suas **[!UICONTROL regras de conteúdo]**.

   Quando você cria uma sequência de critérios, as configurações de recomendações backup e renderização parcial de design são ignoradas para os critérios individuais que fazem parte da sequência. Para usar recomendações backup e renderização parcial de design você deve habilitá-los para a sequência. Selecione as opções apropriadas. Se você escolher permitir recomendações backup, você também pode escolher aplicar regras de inclusão aos backups.
1. Defina a ordem da sequência.

1. Clique em **[!UICONTROL Adicionar critério]**.
1. Na tela Adicionar critério, selecione um critério.
1. Clique em **[!UICONTROL Adicionar]**.

   Você pode adicionar até cinco critérios em uma sequência.
1. Clique em **[!UICONTROL Salvar]**.

   A sequência de critérios irá aparecer na lista de critérios.

   ![](assets/CriteriaSequenceCard.png)

   Para obter mais informações sobre as opções de lógica de recomendação, consulte [Critérios](../../c-recommendations/c-algorithms/algorithms.md#concept_4BD01DC437F543C0A13621C93A302750).

## Vídeo de treinamento: criar critérios no Recommendations (12:33) ![Crachá do tutorial](/help/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
