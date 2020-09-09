---
keywords: criteria sequence;multiple criteria;algorithms;criteria;recommendations criteria;sequence;
description: Use sequências de até cinco critérios para exercer maior controle dos itens exibidos nas atividades Adobe Target Recommendations.
title: Criar sequências de critérios
feature: criteria
uuid: 9a5ca86b-fc79-4c24-b86f-e333b0c63088
translation-type: tm+mt
source-git-commit: a4479a26873f39a41782e78651802899512b87fe
workflow-type: tm+mt
source-wordcount: '1106'
ht-degree: 43%

---


# ![PREMIUM](/help/assets/premium.png) Criar sequência de critérios

Use sequências de até cinco critérios para exercer maior controle dos itens que aparecem em suas atividades do [!UICONTROL Recommendations].

>[!NOTE]
>
>As sequências de critérios não podem ser usadas com as [!UICONTROL atividades do Recommendations] criadas antes da versão de outubro de 2016 [!DNL Target Premium].

Para criar uma sequência de critérios, você deve primeiro criar o critério que deseja incluir na sequência. Consulte [Criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md) para obter mais informações.

Ao usar uma sequência de critérios, você pode fornecer recomendações direcionadas adicionais, em vez de usar recomendações de backup mais genéricas, quando um critério não retorna resultados o suficiente para preencher seu design. Normalmente, uma sequência de critérios continuará de direcionamento mais específico, que pode retornar menos resultados, para direcionamento mais geral, que geralmente retorna mais resultados.

Suas sequências de critérios podem variar dependendo do tipo de página, como mostrado nos seguintes exemplos:

| Tipo de página | Possível ordem de sequência |
| --- | --- |
| Página do produto | <ol><li>Baseado no item atual, da mesma marca</li><li>Baseado no item atual, de todas as marcas</li><li>Baseado na semelhança de conteúdo</li><li>Baseado nos mais vendidos</li><li>Baseado nos itens mais visualizados por todo site</li></ol> |
| Home page | <ol><li>Baseado na última compra do visitante </li><li>Baseado no item favorito do visitante</li><li>Baseado na categoria favorita do visitante</li><li>Baseado nos mais vendidos</li><li>Baseado nos mais visualizados por todo site</li></ol> |

## Acesse a tela Criar sequência de critérios

Existem vários meios de alcançar a tela [!UICONTROL Criar sequência de critérios]. Algumas opções de tela variam de acordo com o modo que você chegar na tela.

* Na tela de biblioteca **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**, clique em **[!UICONTROL Criar critério]** > **[!UICONTROL Criar sequência de critérios]**. Critérios que você criar aqui ficam disponíveis automaticamente para todas atividades do [!UICONTROL Recommendations].
* Quando estiver criando uma atividade [!UICONTROL Recommendations] , na tela Selecionar critérios, clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Criar sequência]** de critérios. Você terá a opção de salvar sua nova sequência de critérios para uso com outras atividades do [!UICONTROL Recommendations].
* When you are editing a [!UICONTROL Recommendations] activity, click in a [!UICONTROL Recommendations Location] box on your page, then select **[!UICONTROL Change Criteria]**. Na tela [!UICONTROL Selecionar critério], clique em **[!UICONTROL Criar novo]** > **[!UICONTROL Criar sequência de critérios]**. Você terá a opção de salvar seu novo critério para uso com outras atividades do [!UICONTROL Recommendations].

As etapas a seguir pressupõem que você acesse a tela [!UICONTROL Criar sequência] de critérios usando o primeiro método: a tela **[!UICONTROL Recommendations]** > **[!UICONTROL Criteria]** Library (Biblioteca de critérios).

1. Clique em **[!UICONTROL Recommendations]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar critérios]** > **[!UICONTROL Criar sequência]** de critérios.

   ![](assets/CreateCriteriaSequence.png)

## Preencha a seção Informações

1. Digite um **[!UICONTROL Nome]** para a sequência.

   Este é o nome &quot;interno&quot; usado para descrever a sequência de critérios. Os visitantes do seu site não verão este nome.

   ![Criar seção de informações da sequência de critérios](/help/c-recommendations/c-algorithms/assets/criteria-sequence-info.png)

1. Digite um **[!UICONTROL Título de exibição genérico]** aberto ao público para aparecer na página, se vários critérios na sequência forem usados para preencher o design do [!UICONTROL Recommendations].

   Por exemplo, você pode querer substituir &quot;Clientes que viram isto também viram...&quot; por &quot;Recomendado para você&quot; se o design puder incluir itens baseados em mais de uma chave de [!UICONTROL recomendações].

1. Digite uma breve **[!UICONTROL Descrição]** da sequência de critérios.

   A descrição deve ajudá-lo a identificar a sequência de critérios e pode incluir informações sobre sua finalidade.

1. Selecione um **[!UICONTROL negócio vertical]**.

   Your default [industry vertical](/help/c-recommendations/c-algorithms/algorithms.md#section_936BCFCF234C49A2BEC1C38AAC2D71AF) appears automatically.

1. Selecione um **[!UICONTROL Tipo de página]**.

   Você pode selecionar vários tipos de página.

   Juntos, o negócio vertical e tipos de página são usados para categorizar sua sequência de critérios salva, tornando mais fácil o reuso de sequências para outras atividades do [!UICONTROL Recommendations].

## Criar sequência {#sequence}

A ordem de sequência define a ordem em que um design é preenchido. Se o Critério 1 não tiver recomendações suficientes para preencher seu design, os slots restantes serão preenchidos com o Critério 2 e assim por diante.

1. Na seção Sequência **[!UICONTROL de]** critérios, clique em **[!UICONTROL Adicionar critérios]**.

   ![Adicionar critérios](/help/c-recommendations/c-algorithms/assets/add-criteria.png)

1. On the [!UICONTROL Select Criteria] screen, select a criteria.

   Você pode usar a caixa Pesquisar e os menus suspensos do filtro para localizar os critérios desejados.

   ![Selecione o critério](/help/c-recommendations/c-algorithms/assets/select-criteria.png)

1. Clique em **[!UICONTROL Adicionar]**.

1. (Opcional) Deslize o **[!UICONTROL Limite de número de itens retornados]** para alternar para a posição &quot;ligado&quot; e especifique o número de itens (entre 1 e 50).

   ![Limitar o número de itens retornados alternar](/help/c-recommendations/c-algorithms/assets/limit-number.png)

   Para ajudá-lo a entender o valor da opção [!UICONTROL Limitar o número de itens retornados] , considere os seguintes casos de uso:

   * **Caso de uso 1**: Você deseja ter uma combinação de diferentes tipos de itens em uma única bandeja de recomendações. Por exemplo, você quer mostrar uma mistura de roupas (casacos) e tampas (camisas, camisas). Para isso, use uma Coleção para a atividade que inclua todos os tipos de produto potenciais que você deseja em qualquer slot do seu design. Em seguida, configure seus primeiros critérios com um filtro estático limitando os critérios para incluir apenas desgaste externo e configure seus segundo critérios com um filtro estático limitando os critérios para incluir somente os demais. Por fim, adicione ambos os critérios a uma sequência de critérios e limite o primeiro critério a 2 slots.

      A bandeja de recomendações pode ser parecida com esta no seu site:

      ![Bandeja de recomendações de produtos em destaque](/help/c-recommendations/c-algorithms/assets/featured-products.png)

   * **Caso de uso 2**: Você deseja uma combinação de itens alternativos e complementares. Configure um critério para usar um algoritmo exibido/exibido e use um filtro dinâmico que limite os itens recomendados à categoria do item atual. Configure o segundo critério para usar um algoritmo visualizado/comprado e usar um filtro dinâmico que inclua apenas itens recomendados que não correspondam à categoria do item atual. Por fim, adicione ambos os critérios a uma sequência e limite o primeiro critério a 2 slots.

1. Continue adicionando critérios adicionais à sua sequência. Você pode adicionar até cinco critérios em uma sequência.

## Especificar conteúdo de backup

Escolha qual conteúdo será retornado quando não houver recomendações suficientes disponíveis para preencher o modelo de design.

Quando você cria uma sequência de critérios, as configurações de recomendações backup e renderização parcial de design são ignoradas para os critérios individuais que fazem parte da sequência. Para usar recomendações backup e renderização parcial de design você deve habilitá-los para a sequência. Selecione as opções apropriadas. Se você escolher permitir recomendações backup, você também pode escolher aplicar regras de inclusão aos backups.

![Configurações de conteúdo de backup](/help/c-recommendations/c-algorithms/assets/backup-content-settings.png)

1. (Opcional) Deslize a opção Renderização **** parcial do design para a posição &quot;ligado&quot;.

   O maior número possível de slots será preenchido, mas o modelo de design pode incluir espaço em branco para os slots restantes.

1. (Opcional) Deslize o **[!UICONTROL backup Recommendations]** para alternar para a posição &quot;ligado&quot;.

   Preencha todos os slots vazios restantes no design com uma seleção aleatória dos produtos mais visualizados de todo o site.

   Para obter mais informações, consulte [Usar uma recomendação](/help/c-recommendations/c-algorithms/backup-recs.md)de backup.

1. (Condicional) Se você selecionou **[!UICONTROL Backup Recommendations]** na etapa anterior, é possível selecionar **[!UICONTROL Aplicar regras de inclusão às recomendações]** de backup.

   For more information see [Use dynamic and static inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

1. Clique em **[!UICONTROL Salvar]**.

   A sequência de critérios irá aparecer na lista de critérios.

   Para obter mais informações sobre as opções de lógica de recomendação, consulte [Critérios](../../c-recommendations/c-algorithms/algorithms.md).

## Vídeo de treinamento: criar critérios no Recommendations (12:33) ![Crachá do tutorial](/help/assets/tutorial.png)

Este vídeo contém as seguintes informações:

* Criar critérios
* Criar sequências de critérios
* Upload dos critérios personalizados

>[!VIDEO](https://video.tv.adobe.com/v/27694?quality=12)
