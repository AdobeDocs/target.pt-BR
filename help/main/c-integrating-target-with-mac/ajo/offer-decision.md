---
keywords: opções do visual experience composer;opções do experience composer;opções de experiência;decisão de oferta;offer decisioning;ajo;otimizador de jornadas
description: Saiba como adicionar uma decisão de oferta criada no  [!DNL Adobe Journey Optimizer]  a uma atividade.
title: Como Usar As Decisões De Oferta?
feature: Integrations
exl-id: cec46d5c-bb5e-4cc9-8785-370f158d3f8e
source-git-commit: d31c9a6f47ea73342cfb638600f351ade4be7013
workflow-type: tm+mt
source-wordcount: '887'
ht-degree: 0%

---

# Usar decisões de oferta

Use o [!DNL Adobe Target] com [!DNL Adobe Journey Optimizer] decisões de oferta para determinar e entregar a próxima melhor oferta para seus visitantes na Web e em dispositivos móveis.

Adicione decisões de oferta criadas em [!DNL Adobe Journey Optimizer] às atividades de [!DNL Target] (manual [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting]) usando o [!UICONTROL Visual Experience Composer] (VEC) ou o [!UICONTROL Form-Based Composer] para testar e entregar ofertas personalizadas aos seus visitantes nos seus canais de entrada alimentados pelo [!DNL Target].

Para obter mais informações sobre [!DNL Adobe Journey Optimizer] e decisões de oferta, consulte os seguintes tópicos na documentação de *[!DNL Journey Optimizer]*:

* [Introdução ao Journey Optimizer](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/get-started.html?lang=pt-BR)

* [Sobre o Gerenciamento de Decisão](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/get-started-decision/starting-offer-decisioning.html?lang=pt-BR)

## Pré-requisitos

Para usar decisões de oferta em [!DNL Target], você precisa do seguinte:

* [!DNL Adobe Target Standard] ou [!DNL Adobe Target Premium] implementados usando o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}.

  O recurso não está disponível ao implementar o [!DNL Target] com a at.js ou outros [!DNL Target] SDKs.

* [!DNL Adobe Journey Optimizer Ultimate] (AJO + Offer Decisioning) ou [!DNL Adobe Experience Platform] e o complemento de serviços de aplicativos [!UICONTROL Offer Decisioning].

## Casos de uso de exemplo

Os exemplos a seguir são casos de uso de como você pode usar a integração [!DNL Target]/[!DNL Adobe Journey Optimizer] para usar decisões de oferta em atividades [!DNL Target]:

### Merchandising esportivo

Como profissional de marketing de uma liga esportiva, você deseja personalizar o conteúdo em sua página inicial (no desktop e no site para dispositivos móveis). Você deseja personalizar o conteúdo com base em várias dimensões e apresentar uma oferta para comprar produtos de franquia relacionados. Você está interessado em:

* A equipe favorita do visitante
* Atividade recente de atleta/jogador (por exemplo, movimento da equipe, atualizações de contrato ou lesões)

Por exemplo, você deseja fornecer uma experiência personalizada para cada uma das seguintes regiões: Dortmund, Frankfurt e Bochum, e para usuários que são fãs implícitos e explícitos dessas equipes. Como métricas, você deseja observar as visitas e cliques no site de mercadorias.

Você deseja criar uma atividade [!UICONTROL A/B Test] (divisão 50/50) entre a experiência padrão e a experiência personalizada (que inclui uma decisão de oferta com ofertas para cada região e equipe). Você deseja usar essa atividade para determinar a conversão e o aumento da experiência personalizada em relação ao controle.

### Plataformas de streaming de jogos

Como profissional de marketing para uma organização de jogos, você deseja oferecer uma oferta personalizada para uma plataforma de streaming de jogos para usuários de desktop e dispositivos móveis de diferentes regiões: Alemanha, França, México e Brasil. Quando um visitante acessa o site do desktop ou móvel de uma dessas regiões geográficas, você deseja fornecer uma oferta para streaming de jogo no idioma local e com um preço correspondente para a moeda local.

No [!DNL Adobe Journey Optimizer], você pode criar uma oferta principal da página inicial personalizada para cada uma das regiões geográficas direcionadas, além de uma oferta substituta com uma página inicial principal padrão. Em seguida, você poderá criar uma decisão de oferta que incorpore essas ofertas e suas regras de qualificação. Em seguida, no [!DNL Target], você pode criar uma atividade do [!DNL Experience Targeting] (XT) e inserir essa decisão de oferta no seu site para desktop ou dispositivos móveis para fornecer a experiência personalizada aos visitantes.

## Crie uma experiência que use uma decisão de oferta:

1. Ao editar ou criar uma atividade manual [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] (XT) no [!UICONTROL Visual Experience Composer] (VEC), clique em um elemento de página para exibir o [menu de opções](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   ![Menu Opções no Visual Experience Composer](assets/options-menu1.png)

   >[!NOTE]
   >
   >Você também pode criar uma experiência que use o [!UICONTROL Offer Decisions] no [[!UICONTROL Form-Based Experience Composer]](/help/main/c-experiences/form-experience-composer.md).

1. Clique em **[!UICONTROL Replace Content]** e depois em **[!UICONTROL Offer Decision]**.

   A opção [!UICONTROL Offer Decision] está disponível somente durante a edição ou criação das atividades [manuais [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) ou [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT). Essa opção não está disponível para outros tipos de atividade. As opções disponíveis no menu variam de acordo com o elemento selecionado.

   ![Menu Opções no Visual Experience Composer](assets/options-menu.png)

1. No painel **[!UICONTROL Add Offer Decision]**, no lado direito do VEC, selecione a sandbox desejada e clique em Selecionar decisão de oferta.placement.

   Uma [sandbox](https://experienceleague.adobe.com/docs/experience-platform/sandbox/ui/overview.html?lang=pt-BR){target=_blank} no [!DNL Adobe Experience Platform] permite particionar sua instância em ambientes virtuais. Por exemplo, você pode ter um ambiente de produção e um ambiente de preparo. Um [posicionamento](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioning/create-components/creating-placements.html?lang=pt-BR){target=_blank} em [!DNL Adobe Journey Optimizer] ajuda a garantir que o conteúdo de oferta correto seja exibido no local correto.

   ![Listas suspensas de Sandbox e Posicionamentos na caixa de diálogo Adicionar Decisão de Oferta](/help/main/c-integrating-target-with-mac/ajo/assets/sandbox-placement.png)

1. Selecione o posicionamento de oferta e a decisão de oferta desejados e clique em **[!UICONTROL Add]**.

   ![Caixa de diálogo Selecionar decisão de oferta](/help/main/c-integrating-target-with-mac/ajo/assets/select-offer-decision.png)

   Seu site é exibido no VEC, onde você pode ver a decisão de oferta recém-criada no painel [!UICONTROL Modifications]. Você pode clicar em uma oferta em [!UICONTROL Offer Preview] na parte inferior do painel [!UICONTROL Offer Decision] para examinar a decisão de oferta.

   <!--You can examine the various offers contained in the offer by clicking the appropriate icon at the bottom of the [!UICONTROL Offer Preview] dialog box, including the fallback offer. A fallback offer is the default offer displayed when a visitor is not eligible for any of the personalized offers in the collection.-->

   ![Visualização da oferta](assets/offer-preview2.png)

1. Conclua a criação da atividade concluindo as etapas [!UICONTROL Targeting] e [!UICONTROL Goals & Settings] do fluxo de trabalho guiado de três partes.

   >[!IMPORTANT]
   >
   >Para garantir que a atividade [!DNL Target] seja personalizada, verifique se as datas de início/término da atividade atual estão sincronizadas com as datas de início/término da decisão de oferta em [!DNL Adobe Journey Optimizer]. Se as datas de início/término de [!DNL Target] estiverem fora do intervalo de datas de início/término da decisão de oferta, o conteúdo [!DNL Target] padrão será exibido para os visitantes.

## Observações e limitações

Considere as seguintes informações ao trabalhar com as decisões de oferta:

* A integração do Offer Decisioning funciona para [!DNL Target] implementações baseadas no [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}. Este recurso não está disponível ao implementar o [!DNL Target] com a at.js ou outros [!DNL Target] SDKs.

* A integração [!DNL Target]/[!DNL Adobe Journey Optimizer] dá suporte somente às atividades [manuais [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) e [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT). Este recurso não está disponível para outros tipos de atividades.

* Você não pode usar o [[!UICONTROL Analytics as the reporting source]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) se estiver usando decisões de oferta em uma atividade do. Escolha [!DNL Target] como fonte de relatórios na página [!UICONTROL Goals and Settings] durante a configuração da atividade se você usar decisões de oferta na atividade.

* Ofertas com o tipo de conteúdo text/html não são compatíveis com a entrega de conteúdo deliveryURL. O deliveryURL é suportado pelo [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) somente onde o cliente é responsável por buscar e compor explicitamente o conteúdo.

* Os relatórios de [!DNL Target] não fornecem relatórios de nível de decisão de oferta.

* A visualização de [links de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) para [!DNL Target] experiências que contêm decisões de oferta afeta o limite de frequência definido em [!DNL Adobe Journey Optimizer] para essas decisões de oferta.
