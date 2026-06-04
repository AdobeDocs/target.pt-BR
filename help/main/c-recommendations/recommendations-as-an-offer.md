---
keywords: Recomendações, oferta
description: Saiba como utilizar o Recomendações da Adobe como uma oferta em atividades de Testes A/B (incluindo Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT)
title: Como uso o Recomendações como oferta em outros tipos de atividade?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
TQID: https://experienceleague.adobe.com/ZMOb5RdY6bES331INSM7VF-w4be-5Xmjqon0YvfuNG4
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 571
ht-degree: 55%

---

# Recomendações como oferta

Agora você pode incluir recomendações nas atividades de [!UICONTROL Teste A/B] (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) e [!UICONTROL Direcionamento de experiência] (XT).

Essa funcionalidade permite capacidades nunca antes vistas, como:

* Teste e direcione conteúdo de recomendações e não recomendações em uma mesma atividade.
* Experimente com facilidade a colocação de recomendações na página, incluindo a ordem de várias recomendações.
* Impulsione automaticamente o tráfego para a experiência do recommendations com melhor desempenho usando [!UICONTROL Alocação automática].
* Atribua de maneira dinâmica os visitantes a experiências de recomendação personalizadas com base em seus perfis usando o [!UICONTROL Direcionamento automático].

Para começar, crie uma atividade de [!UICONTROL Teste A/B] ou [!UICONTROL Direcionamento de Experiência] usando o [!UICONTROL Visual Experience Composer] e use a ação [!UICONTROL Inserir Antes], [!UICONTROL Inserir Depois] ou [!UICONTROL Substituir Por] para adicionar recomendações a uma experiência.

## Adicionar uma recomendação como uma oferta em uma atividade Teste A/B ou XT

1. Inicie o fluxo de trabalho guiado de três etapas usando o Visual Experience Composer (VEC) para criar uma atividade de [Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou [Direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Para Testes A/B, lembre-se de que você pode escolher a opção [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para impulsionar automaticamente o tráfego para a recomendação com melhor desempenho ou a opção [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para atribuir os visitantes a experiências de recomendação personalizadas com base em seus perfis.

1. Ao criar uma [experiência](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), clique no elemento ao qual deseja adicionar uma recomendação como uma oferta, clique em **[!UICONTROL Substituir Conteúdo]** e selecione **[!UICONTROL Recomendação]**.

   ![Inserir recomendação como uma oferta](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. Selecione entre as seguintes opções para ver os critérios populares de recomendações por tipo de página:

   * Página de carrinho
   * Página de categoria
   * Página inicial
   * Página de destino
   * Página do produto
   * Página de resultados da pesquisa
   * Página de agradecimento
   * Outras

1. Selecione os [critérios](/help/main/c-recommendations/c-algorithms/algorithms.md) desejados e clique em [!UICONTROL Avançar].
1. Selecione o [design](/help/main/c-recommendations/c-design-overview/design-overview.md) desejado e clique em [!UICONTROL Avançar].
1. Na caixa de diálogo [!UICONTROL Opções], especifique o seguinte:

   * Escolha uma [coleção](/help/main/c-recommendations/c-products/collections.md).
   * Configure as opções de [Promoção principal e Promoção secundária](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md), conforme necessário.

1. Clique em [!UICONTROL Salvar].
1. Termine de configurar a atividade de Teste A/B ou XT usado o fluxo de trabalho orientado de três partes.

## Editar a configuração de uma oferta do Recomendações

Há duas maneiras de editar a configuração de uma oferta:

* Usando o menu [!UICONTROL Editar]
* Usando o painel [!UICONTROL Modificações]

### Editar uma oferta do Recomendações utilizando o menu Editar

1. Clique na oferta que você deseja editar e em **[!UICONTROL Editar]**.

   ![Editar oferta de recomendações](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. Escolha entre as seguintes opções:

   * [Alterar critérios](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [Alterar design](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [Alterar coleção](/help/main/c-recommendations/c-products/collections.md)
   * [Alterar promoção](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Faça suas edições.

### Editar uma oferta do Recomendações utilizando o painel Modificações

1. Clique no ícone [!UICONTROL Modificações] **( `</>` )** para exibir o painel [Modificações](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Passe o mouse sobre a ação desejada e clique no ícone **[!UICONTROL Editar]**.

   ![Painel de modificações](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. Faça suas edições.

## Excluir uma oferta do Recomendações

Há duas maneiras de excluir uma oferta do Recomendações:

* Usando o menu [!UICONTROL Editar]
* Usando o painel [!UICONTROL Modificações]

### Excluir uma oferta do Recomendações utilizando o menu Editar

1. Clique na oferta que você deseja remover e em **[!UICONTROL Layout > Remover]**.

   ![Remover](/help/main/c-recommendations/assets/recs-offer-remove.png)

### Excluir uma oferta do Recomendações utilizando o painel Modificações

1. Clique no ícone [!UICONTROL Modificações] **( &lt;/> )** para exibir o painel [Modificações](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Passe o cursor do mouse sobre a ação desejada e clique no ícone [!UICONTROL Excluir].

   ![Ícone de Excluir](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Exibição do status da oferta de recomendações {#status}

O status da oferta de recomendações (algoritmo) é exibido na parte inferior da página [!UICONTROL Visão geral] das atividades de Teste A/B e XT que contêm as ofertas do Recommendations:

* Resultados prontos
* Resultados não prontos
* Falha do feed

![Status da oferta de recomendações](/help/main/c-recommendations/assets/recs-offer-status.png)

## Vídeo de treinamento: Recomendações como oferta ![Selo de visão geral](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
