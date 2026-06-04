---
keywords: Recomendações, oferta
description: Saiba como utilizar o Recomendações da Adobe como uma oferta em atividades de Testes A/B (incluindo Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT)
title: Como uso o Recomendações como oferta em outros tipos de atividade?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: f6034e83564a9a386e21e4e57279c66cc3c94537
workflow-type: tm+mt
source-wordcount: '492'
ht-degree: 42%

---

# Recomendações como oferta

Agora você pode incluir recomendações nas atividades de [!UICONTROL Teste A/B] (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) e [!UICONTROL Direcionamento de experiência] (XT).

Essa funcionalidade permite capacidades nunca antes vistas, como:

* Teste e direcione conteúdo de recomendações e não recomendações em uma mesma atividade.
* Experimente facilmente a colocação de recomendações na página, incluindo a ordem de várias recomendações.
* Impulsione automaticamente o tráfego para a experiência do recommendations com melhor desempenho usando [!UICONTROL Alocação automática].
* Atribua de maneira dinâmica os visitantes a experiências de recomendação personalizadas com base em seus perfis usando o [!UICONTROL Direcionamento automático].

Para começar, crie uma atividade de [!UICONTROL Teste A/B] ou [!UICONTROL Direcionamento de experiência] usando o [!UICONTROL Visual Experience Composer] e use a ação [!UICONTROL Recomendar] para adicionar recomendações a uma experiência.

## Adicionar uma recomendação como uma oferta em uma atividade Teste A/B ou XT

1. Inicie o fluxo de trabalho guiado de três etapas usando o Visual Experience Composer (VEC) para criar uma atividade de [Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou [Direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Para Testes A/B, lembre-se de que você pode escolher a opção [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para impulsionar automaticamente o tráfego para a recomendação com melhor desempenho ou a opção [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para atribuir os visitantes a experiências de recomendação personalizadas com base em seus perfis.

1. Ao criar uma [experiência](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), clique no elemento ao qual deseja adicionar uma recomendação como uma oferta, clique em **[!UICONTROL Substituir Conteúdo]** ( ![Ícone Substituir Conteúdo](/help/main/assets/icons/Switch.svg) ) e selecione **[!UICONTROL Recomendação]**.

   ![Inserir recomendação como uma oferta](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. No painel [!UICONTROL Recomendação], no lado direito, clique em **[!UICONTROL Selecionar uma Recomendação]** para exibir a caixa de diálogo [!UICONTROL Selecionar Critérios].

1. Clique em **[!UICONTROL Criar critério]** ou selecione um critério existente.

1. (Opcional) Clique no ícone **[!UICONTROL Filtro]** ( ![Ícone Filtro](/help/main/assets/icons/Filter.svg) ) para selecionar entre as seguintes opções para exibir os critérios de recomendações populares por tipo de página:

   * Página de carrinho
   * Página de categoria
   * Página inicial
   * Página de destino
   * Página do produto
   * Página de resultados da pesquisa
   * Página de agradecimento
   * Outras

1. Clique em **[!UICONTROL Criar critério]** ou selecione um [critério](/help/main/c-recommendations/c-algorithms/algorithms.md) existente e clique em **[!UICONTROL Avançar]** para exibir a caixa de diálogo [!UICONTROL Selecionar Design].

1. Clique em **[!UICONTROL Criar design]** ou selecione um [design](/help/main/c-recommendations/c-design-overview/design-overview.md) existente e clique em **[!UICONTROL Avançar]**.

1. Na caixa de diálogo [!UICONTROL Opções], especifique o seguinte:

   * Escolha uma [coleção](/help/main/c-recommendations/c-products/collections.md).
   * Configure as opções de [Promoção principal e Promoção secundária](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md), conforme necessário.

1. Clique em **[!UICONTROL Salvar]**.
1. Termine de configurar a atividade de Teste A/B ou XT usado o fluxo de trabalho orientado de três partes.

## Editar a configuração de uma oferta do Recomendações

1. No painel [!UICONTROL Recomendação], clique no ícone **[!UICONTROL Editar]** ( ![ícone Editar](/help/main/assets/icons/Edit.svg) ) ao lado de [!UICONTROL Nome do Critério], [!UICONTROL Nome do Design] ou [!UICONTROL Nome da Coleção] para alterar o elemento.

## Excluir uma oferta do Recomendações

1. Clique no ícone **[!UICONTROL Excluir]** ( ![Ícone Excluir](/help/main/assets/icons/Delete.svg) ) na parte superior do painel [!UICONTROL Recomendação].

### Exibição do status da oferta de recomendações {#status}

O status das ofertas de recomendações (algoritmo) é exibido na parte inferior da página [!UICONTROL Visão geral] da atividade para atividades de Teste A/B e XT que contêm ofertas do Recommendations:

* Resultados prontos
* Resultados não prontos
* Falha do feed
