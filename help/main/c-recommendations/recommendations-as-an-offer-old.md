---
keywords: Recommendations, oferta
description: Saiba como utilizar o Adobe Recommendations como uma oferta em atividades de Testes A/B (incluindo Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT)
title: Como uso o Recommendations como uma oferta em outros tipos de atividade?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: 3821d868f45b85d2f6f0e204f9828544b759067b
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 47%

---

# Recommendations como uma oferta

Agora você pode incluir recomendações nas atividades de [!UICONTROL A/B Test] (incluindo [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]) e [!UICONTROL Experience Targeting] (XT).

Essa funcionalidade permite capacidades nunca antes vistas, como:

* Teste e direcione conteúdo de recomendações e não recomendações em uma mesma atividade.
* Experimente facilmente a colocação de recomendações na página, incluindo a ordem de várias recomendações.
* Impulsione automaticamente o tráfego para a experiência do recommendations com melhor desempenho usando o [!UICONTROL Auto-Allocate].
* Atribua de maneira dinâmica os visitantes a experiências de recomendação personalizadas com base em seus perfis usando o [!UICONTROL Auto-Target].

Para começar, crie uma atividade [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] usando o [!UICONTROL Visual Experience Composer] e use a ação [!UICONTROL Recommend] para adicionar recomendações a uma experiência.

## Adicionar uma recomendação como uma oferta em uma atividade Teste A/B ou XT

1. Inicie o fluxo de trabalho guiado de três etapas usando o Visual Experience Composer (VEC) para criar uma atividade de [Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou [Direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Para Testes A/B, lembre-se de que você pode escolher a opção [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para impulsionar automaticamente o tráfego para a recomendação com melhor desempenho ou a opção [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para atribuir os visitantes a experiências de recomendação personalizadas com base em seus perfis.

1. Ao criar uma [experiência](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), clique no elemento ao qual deseja adicionar uma recomendação como uma oferta, clique em **[!UICONTROL Replace Content]** ( ![Ícone Substituir Conteúdo](/help/main/assets/icons/Switch.svg) ) e selecione **[!UICONTROL Recommendation]**.

   ![Inserir recomendação como uma oferta](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. No painel [!UICONTROL Recommendation], no lado direito, clique em **[!UICONTROL Select a Recommendation]** para exibir a caixa de diálogo [!UICONTROL Select Criteria].

1. Clique em **[!UICONTROL Create Criteria]** ou selecione um critério existente.

1. (Opcional) Clique no ícone **[!UICONTROL Filter]** ( ![Ícone de filtro](/help/main/assets/icons/Filter.svg) ) para selecionar entre as seguintes opções para exibir os critérios de recomendações populares por tipo de página:

   * Página de carrinho
   * Página de categoria
   * Página inicial
   * Página de aterrissagem
   * Página do produto
   * Página de resultados da pesquisa
   * Página de agradecimento
   * Outras

1. Clique em **[!UICONTROL Create Criteria]** ou selecione um [critério](/help/main/c-recommendations/c-algorithms/algorithms.md) existente e clique em **[!UICONTROL Next]** para exibir a caixa de diálogo [!UICONTROL Select Design].

1. Clique em **[!UICONTROL Create Design]** ou selecione um [design](/help/main/c-recommendations/c-design-overview/design-overview.md) existente e clique em **[!UICONTROL &#x200B; Next]**.

1. Na caixa de diálogo [!UICONTROL Options], especifique o seguinte:

   * Escolha uma [coleção](/help/main/c-recommendations/c-products/collections.md).
   * Configure as opções de [Promoção principal e Promoção secundária](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md), conforme necessário.

1. Clique em **[!UICONTROL Save]**.
1. Termine de configurar a atividade de Teste A/B ou XT usado o fluxo de trabalho orientado de três partes.

## Editar a configuração de uma oferta do recommendations

1. No painel [!UICONTROL Recommendation], clique no ícone **[!UICONTROL Edit]** ( ![Ícone Editar](/help/main/assets/icons/Edit.svg) ) ao lado de [!UICONTROL Criteria Name], [!UICONTROL Design Name] ou [!UICONTROL Collection Name] para alterar o elemento.

## Excluir uma oferta do recommendations

1. Clique no ícone **[!UICONTROL Delete]** ( ![Ícone Excluir](/help/main/assets/icons/Delete.svg) ) na parte superior do painel [!UICONTROL Recommendation].

### Exibição do status da oferta de recomendações {#status}

O status das ofertas de recomendações (algoritmo) é exibido na parte inferior da página [!UICONTROL Overview] da atividade para atividades de Teste A/B e XT que contêm as ofertas do Recommendations:

* Resultados prontos
* Resultados não prontos
* Falha do feed
