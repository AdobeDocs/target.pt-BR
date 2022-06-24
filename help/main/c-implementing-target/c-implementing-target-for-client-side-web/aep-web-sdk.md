---
keywords: Adobe Experience Platform Web SDK; aep web sdk; web sdk; sdk; adobe experience cloud; plataforma de rede de borda; adobe experience platform edge network; rede de borda; rede de borda da aep
description: Saiba como usar o SDK da Web da Adobe Experience Platform para interagir com os vários serviços na Adobe Experience Cloud por meio da AEP Edge Network.
title: Como implementar com o SDK da Web do Experience Platform?
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '563'
ht-degree: 15%

---

# SDK da Web da Adobe Experience Platform

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK) é uma biblioteca JavaScript do lado do cliente que permite que os clientes da [!DNL Adobe Experience Cloud] para interagir com os vários serviços no Experience Cloud (incluindo [!DNL Target]) através da [!UICONTROL Rede de borda Adobe Experience Platform]. Além da biblioteca do JavaScript, há uma [!DNL Adobe Experience Platform] para ajudar com as configurações do SDK da Web.

Para obter mais informações, consulte os seguintes links na *Adobe Experience Platform Web SDK* ajuda:

* Para obter informações abrangentes: [O que é o SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR)
* Para obter informações específicas de [!DNL Target]: [Visão geral do Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html?lang=pt-BR)

## Tutorial: Implementar o Adobe Experience Cloud com o SDK da Web da plataforma

Saiba como [implementar aplicativos do Experience Cloud usando o Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/overview.html){target=_blank}. Para obter informações específicas do Target, consulte [Configurar o Target com o SDK da Web da plataforma](https://experienceleague.adobe.com/docs/platform-learn/implement-web-sdk/applications-setup/setup-target.html){target=_blank} no tutorial.

## Documentação recomendada

Além do [!DNL Platform Web SDK] documentação mencionada acima, os tópicos neste guia também têm informações específicas para o [!DNL Platform Web SDK] no que se refere a [!DNL Target] recursos e funcionalidades.

| Recurso | Descrição/Link |
| --- | --- |
| [Controle de qualidade da atividade](/help/main/c-activities/c-activity-qa/activity-qa.md) | Usar URLs de controle de qualidade em [!DNL Adobe Target] para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real. [!UICONTROL Controle de qualidade da atividade] permite testar totalmente a [!DNL Target] antes de iniciá-las ao vivo.<br>Consulte [Compatibilidade do Modo de QA da biblioteca JavaScript do Target](/help/main/c-activities/c-activity-qa/activity-qa.md#compatibility) e [Visualizar URLs](/help/main/c-activities/c-activity-qa/activity-qa.md#preview). |
| [Analytics for Target (A4T) ](/help/main/c-integrating-target-with-mac/a4t/a4t.md) | O [!DNL Adobe Analytics for Target] (A4T) é uma integração entre soluções que permite criar atividades com base nas métricas de conversão e nos segmentos de público-alvo do [!DNL Analytics]. A integração A4T permite que você use os relatórios do [!DNL Analytics] para examinar os resultados.<br>Consulte [Tipos de atividades suportadas](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) e [Etapas de implementação para uma implementação do SDK da Web da Adobe Experience Platform](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md#platform). |
| [Públicos-alvo](/help/main/c-target/target.md) | Públicos-alvo em [!DNL Adobe Target] determine quem vê o conteúdo e as experiências em uma atividade direcionada.<br>Consulte [Usar a lista de Públicos-alvo](/help/main/c-target/c-audiences/audiences.md#use-list) e [Combinar vários públicos](/help/main/c-target/combining-multiple-audiences.md). |
| [Criar públicos-alvo](/help/main/c-target/c-audiences/audiences.md) | O uso de públicos-alvo criados na [!DNL Adobe Experience Platform] fornece dados do cliente mais avançados, o que resulta em uma personalização mais impactante.<ul>Consulte [Usar públicos-alvo de [!DNL Adobe Experience Platform]](/help/main/c-target/c-audiences/audiences.md#aep). |
| [Decisões de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md) | Adicione as decisões de oferta criadas no Adobe Journey Optimizer às atividades do Target (teste A/B manual ou direcionamento de experiência) para determinar e fornecer a melhor oferta para seus visitantes na Web e em dispositivos móveis. |
| [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | O redirecionamento de ofertas faz com que os navegadores dos visitantes redirecione para uma nova página.<br>Consulte [O [!DNL Adobe Experience Platform Web SDK] oferece suporte a ofertas de redirecionamento para A4T?](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [Tokens de resposta](/help/main/administrating-target/response-tokens.md) | Os tokens de resposta permitem enviar dados do Target para o Google Analytics e outras integrações de terceiros.<br>Consulte [Envio de dados para o Google Analytics por meio do SDK da Web da plataforma](/help/main/administrating-target/response-tokens.md#platform-web-sdk) para ver um exemplo de código de como realizar essa tarefa. |
| [Implementação de aplicativos de página única](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) no *Visão geral do SDK da Web da plataforma* guia. | [!UICONTROL Adobe Experience Platform Web SDK] O fornece recursos avançados para sua empresa personalizar tecnologias de próxima geração no lado do cliente, como aplicativos de página única (SPA). |
| [Alterações na criptografia do TLS (Transport Layer Security)](https://developer.adobe.com/target/before-implement/tls-transport-layer-security-encryption/){target=_blank} | O TLS (Transport Layer Security){target=_blank} ajuda a manter os mais altos padrões de segurança e a promover a segurança dos dados do cliente. |
