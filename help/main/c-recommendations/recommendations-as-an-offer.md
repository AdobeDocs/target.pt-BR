---
keywords: Recommendations, oferta
description: Saiba como utilizar o Adobe Recommendations como uma oferta em atividades de Testes A/B (incluindo Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT)
title: Como uso o Recommendations como uma oferta em outros tipos de atividade?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: ec520555-b439-46a9-ab2d-f0981532bffb
source-git-commit: f848c79cb95009b5810a1707d04e548a57220e12
workflow-type: tm+mt
source-wordcount: '507'
ht-degree: 60%

---

# Recommendations como uma oferta

Agora você pode incluir recomendações nas atividades de [!UICONTROL A/B Test] (incluindo [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]) e [!UICONTROL Experience Targeting] (XT).

Essa funcionalidade permite capacidades nunca antes vistas, como:

* Teste e direcione conteúdo de recomendações e não recomendações em uma mesma atividade.
* Experimente com facilidade a colocação de recomendações na página, incluindo a ordem de várias recomendações.
* Impulsione automaticamente o tráfego para a experiência do recommendations com melhor desempenho usando o [!UICONTROL Auto-Allocate].
* Atribua de maneira dinâmica os visitantes a experiências de recomendação personalizadas com base em seus perfis usando o [!UICONTROL Auto-Target].

Para começar, crie uma atividade [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] usando o [!UICONTROL Visual Experience Composer] e use a ação [!UICONTROL Insert Before], [!UICONTROL Insert After] ou [!UICONTROL Replace With] para adicionar recomendações a uma experiência.

## Adicionar uma recomendação como uma oferta em uma atividade Teste A/B ou XT

1. Inicie o fluxo de trabalho guiado de três etapas usando o Visual Experience Composer (VEC) para criar uma atividade de [Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou [Direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Para Testes A/B, lembre-se de que você pode escolher a opção [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para impulsionar automaticamente o tráfego para a recomendação com melhor desempenho ou a opção [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para atribuir os visitantes a experiências de recomendação personalizadas com base em seus perfis.

1. Ao criar uma [experiência](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md), clique no elemento ao qual deseja adicionar uma recomendação como uma oferta, clique em **[!UICONTROL Replace Content]** e selecione **[!UICONTROL Recommendation]**.

   ![Inserir recomendação como uma oferta](/help/main/c-recommendations/t-create-recs-activity/assets/recs-as-offer.png)

1. Selecione entre as seguintes opções para ver os critérios populares do recommendations por tipo de página:

   * Página de carrinho
   * Página de categoria
   * Página inicial
   * Página de aterrissagem
   * Página do produto
   * Página de resultados da pesquisa
   * Página de agradecimento
   * Outras

1. Selecione os [critérios](/help/main/c-recommendations/c-algorithms/algorithms.md) desejados e clique em [!UICONTROL Next].
1. Selecione o [design](/help/main/c-recommendations/c-design-overview/design-overview.md) desejado e clique em [!UICONTROL Next].
1. Na caixa de diálogo [!UICONTROL Options], especifique o seguinte:

   * Escolha uma [coleção](/help/main/c-recommendations/c-products/collections.md).
   * Configure as opções de [Promoção principal e Promoção secundária](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md), conforme necessário.

1. Clique em [!UICONTROL Save].
1. Termine de configurar a atividade de Teste A/B ou XT usado o fluxo de trabalho orientado de três partes.

## Editar a configuração de uma oferta do recommendations

Há duas maneiras de editar a configuração de uma oferta:

* Usando o menu [!UICONTROL Edit]
* Usando o painel [!UICONTROL Modifications]

### Editar uma oferta do recommendations utilizando o menu Editar

1. Clique na oferta que você deseja editar e em **[!UICONTROL Edit]**.

   ![Editar oferta de recomendações](/help/main/c-recommendations/assets/recs-offer-edit.png)

1. Escolha entre as seguintes opções:

   * [Alterar critérios](/help/main/c-recommendations/c-algorithms/algorithms.md)
   * [Alterar design](/help/main/c-recommendations/c-design-overview/design-overview.md)
   * [Alterar coleção](/help/main/c-recommendations/c-products/collections.md)
   * [Alterar promoção](/help/main/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Faça suas edições.

### Editar uma oferta do recommendations utilizando o painel Modificações

1. Clique no ícone [!UICONTROL Modifications] **( `</>` )** para exibir o painel [Modificações](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Passe o cursor do mouse sobre a ação desejada e clique no ícone **[!UICONTROL Edit]**.

   ![Painel de modificações](/help/main/c-recommendations/assets/recs-offer-modifications.png)

1. Faça suas edições.

## Excluir uma oferta do recommendations

Há duas maneiras de excluir uma oferta do recommendations:

* Usando o menu [!UICONTROL Edit]
* Usando o painel [!UICONTROL Modifications]

### Excluir uma oferta do recommendations utilizando o menu Editar

1. Clique na oferta que você deseja remover e em **[!UICONTROL Layout > Remove]**.

   ![Remover](/help/main/c-recommendations/assets/recs-offer-remove.png)

### Excluir uma oferta do recommendations utilizando o painel Modificações

1. Clique no ícone [!UICONTROL Modifications] **( &lt;/> )** para exibir o painel [Modificações](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Passe o cursor do mouse sobre a ação desejada e clique no ícone [!UICONTROL Delete].

   ![Ícone de Excluir](/help/main/c-recommendations/assets/recs-offer-delete.png)

### Exibição do status da oferta de recomendações {#status}

O status da oferta de recomendações (algoritmo) é exibido na parte inferior da página [!UICONTROL Overview] para atividades de Teste A/B e XT que contêm ofertas da Recommendations:

* Resultados prontos
* Resultados não prontos
* Falha do feed

![Status da oferta de recomendações](/help/main/c-recommendations/assets/recs-offer-status.png)

## Vídeo de treinamento: Recommendations como uma oferta ![Selo de visão geral](/help/main/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)
