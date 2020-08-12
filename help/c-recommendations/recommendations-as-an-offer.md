---
keywords: Recommendations;offer
description: O Adobe Recommendations como uma oferta em atividades de Testes A/B (incluindo Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT)
title: O Adobe Recommendations como uma oferta em atividades de Testes A/B (incluindo Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT)
feature: null
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '556'
ht-degree: 98%

---


# ![PREMIUM](/help/assets/premium.png) Recommendations como uma oferta

Agora, você pode incluir recomendações nas atividades de [!UICONTROL Teste A/B] (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) e [!UICONTROL Direcionamento de experiência] (XT).

Essa funcionalidade permite capacidades nunca antes vistas, como:

* Teste e direcione conteúdo de recomendações e não recomendações em uma mesma atividade.
* Experimente com facilidade a colocação de recomendações na página, incluindo a ordem de várias recomendações.
* Impulsione automaticamente o tráfego para a experiência do recommendations com melhor desempenho usando [!UICONTROL Alocação automática].
* Atribua de maneira dinâmica os visitantes a experiências de recomendação personalizadas com base em seus perfis usando o [!UICONTROL Direcionamento automático].

Para começar, crie uma atividade de [!UICONTROL Teste A/B] ou [!UICONTROL Direcionamento de experiência] usando o [!UICONTROL Visual Experience Composer] e use a ação [!UICONTROL Inserir antes], [!UICONTROL Inserir depois] ou [!UICONTROL Substituir por] para adicionar recomendações a uma experiência.

## Adicionar uma recomendação como uma oferta em uma atividade Teste A/B ou XT

1. Inicie o fluxo de trabalho guiado de três etapas usando o Visual Experience Composer (VEC) para criar uma atividade de [Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) ou [Direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/xt-create.md) (XT).

   >[!NOTE]
   >
   >Para Testes A/B, lembre-se de que você pode escolher a opção [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para impulsionar automaticamente o tráfego para a recomendação com melhor desempenho ou a opção [Direcionamento automático](/help/c-activities/auto-target-to-optimize.md) para atribuir os visitantes a experiências de recomendação personalizadas com base em seus perfis.

1. Ao criar uma [experiência](/help/c-experiences/c-visual-experience-composer/viztarget-options.md), clique no elemento ao qual deseja adicionar uma recomendação como uma oferta, selecione a ação **[!UICONTROL Inserir antes]**, **[!UICONTROL Inserir após]** ou **[!UICONTROL Substituir por]** e selecione [!UICONTROL Recomendação].

   A ilustração a seguir mostra a opção [!UICONTROL Inserir após > Recomendação].

   ![Inserir recomendação como uma oferta](/help/c-recommendations/assets/replace-after-recommendations.png)

1. Selecione entre as seguintes opções para ver os critérios populares do recommendations por tipo de página:

   * Página de carrinho
   * Página de categoria
   * Página inicial
   * Página de aterrissagem
   * Página do produto
   * Página de resultados da pesquisa
   * Página de agradecimento
   * Outras

1. Selecione os [critérios](/help/c-recommendations/c-algorithms/algorithms.md) desejados e clique em [!UICONTROL Avançar].
1. Selecione o [design](/help/c-recommendations/c-design-overview/design-overview.md) desejado e clique em [!UICONTROL Avançar].
1. Na caixa de diálogo [!UICONTROL Opções], especifique o seguinte:

   * Escolha uma [coleção](/help/c-recommendations/c-products/collections.md).
   * Configure as opções de [Promoção principal e Promoção secundária](/help/c-recommendations/t-create-recs-activity/adding-promotions.md), conforme necessário.

1. Clique em [!UICONTROL Salvar].
1. Termine de configurar a atividade de Teste A/B ou XT usado o fluxo de trabalho orientado de três partes.

## Editar a configuração de uma oferta do recommendations

Há duas maneiras de editar a configuração de uma oferta:

* Utilizando o menu [!UICONTROL Editar]
* Uso do painel de [!UICONTROL Modificações]

### Editar uma oferta do recommendations utilizando o menu Editar

1. Clique na oferta que você deseja editar e em **[!UICONTROL Editar]**.

   ![Editar oferta de recomendações](/help/c-recommendations/assets/recs-offer-edit.png)

1. Escolha entre as seguintes opções:

   * [Alterar critérios](/help/c-recommendations/c-algorithms/algorithms.md)
   * [Alterar design](/help/c-recommendations/c-design-overview/design-overview.md)
   * [Alterar coleção](/help/c-recommendations/c-products/collections.md)
   * [Alterar promoção](/help/c-recommendations/t-create-recs-activity/adding-promotions.md)

1. Faça suas edições.

### Editar uma oferta do recommendations utilizando o painel Modificações

1. Clique no ícone [!UICONTROL Modificações] **(`</>`)** para exibir o painel [Modificações](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Passe o cursor do mouse sobre a ação desejada e clique no ícone **[!UICONTROL Editar]**.

   ![Painel de modificações](/help/c-recommendations/assets/recs-offer-modifications.png)

1. Faça suas edições.

## Excluir uma oferta do recommendations

Há duas maneiras de excluir uma oferta do recommendations:

* Utilizando o menu [!UICONTROL Editar]
* Uso do painel de [!UICONTROL Modificações]

### Excluir uma oferta do recommendations utilizando o menu Editar

1. Clique na oferta que você deseja excluir e em **[!UICONTROL Layout > Remover]**.

   ![Remover](/help/c-recommendations/assets/recs-offer-remove.png)

### Excluir uma oferta do recommendations utilizando o painel Modificações

1. Clique no ícone [!UICONTROL Modificações] **( &lt;/>)** para exibir o painel [Modificações](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).
1. Passe o cursor do mouse sobre a ação desejada e clique no ícone [!UICONTROL Excluir].

   ![Ícone de Excluir](/help/c-recommendations/assets/recs-offer-delete.png)

### Exibição do status da oferta de recomendações {#status}

O status da oferta de recomendações (algoritmo) é exibido na parte inferior da página [!UICONTROL Visão geral] das atividades de Teste A/B e XT que contêm as ofertas do Recommendations:

* Resultados prontos
* Resultados não prontos
* Falha do feed

![Status da oferta de recomendações](/help/c-recommendations/assets/recs-offer-status.png)

## Vídeo de treinamento: Recommendations como um selo de ![Visão geral da oferta](/help/assets/overview.png)

>[!VIDEO](https://video.tv.adobe.com/v/28878)