---
keywords: Adobe Experience Platform Web SDK; aep web sdk; web sdk; sdk; adobe experience cloud; plataforma de rede de borda; adobe experience platform edge network; rede de borda; rede de borda da aep
description: Saiba como usar o SDK da Web da Adobe Experience Platform para interagir com os vários serviços na Adobe Experience Cloud por meio da AEP Edge Network.
title: Como implementar com o SDK da Web do Experience Platform?
feature: AEP Web SDK
role: Developer
exl-id: afcd741f-bb7e-4bc2-b96c-ec10d5d6f4c5
source-git-commit: 28be06a329d017fd25d069986a0b7b047ddda206
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 6%

---

# SDK da Web da Adobe Experience Platform

[!DNL Adobe Experience Platform Web SDK] (AEP Web SDK) é uma biblioteca JavaScript do lado do cliente que permite que os clientes do  [!DNL Adobe Experience Cloud] interajam com os vários serviços no Experience Cloud (incluindo  [!DNL Target]) por meio da  [!UICONTROL Adobe Experience Platform Edge Network]. Além da biblioteca do JavaScript, há uma extensão [!DNL Experience Platform Launch] para ajudar nas configurações do SDK da Web.

Para obter mais informações, consulte os seguintes links na ajuda do *Adobe Experience Platform Web SDK*:

* Para obter informações abrangentes: [O que é Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html)
* Para informações específicas de [!DNL Target]: [Visão geral do Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html)

## Documentação recomendada

Além da documentação [!DNL Platform Web SDK] mencionada acima, os tópicos neste guia também têm informações específicas para o [!DNL Platform Web SDK], pois estão relacionados aos recursos e funcionalidades do [!DNL Target].

| Recurso | Descrição/Link |
| --- | --- |
| [Controle de qualidade da atividade](/help/c-activities/c-activity-qa/activity-qa.md) | Use URLs de controle de qualidade em [!DNL Adobe Target] para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real. [!UICONTROL O ] Controle de qualidade da atividade permite testar completamente suas  [!DNL Target] atividades antes de iniciá-las ao vivo.<br>Consulte  [Compatibilidade do modo de controle de qualidade da biblioteca JavaScript do Target e URLs de ](/help/c-activities/c-activity-qa/activity-qa.md#compatibility) visualização [ ](/help/c-activities/c-activity-qa/activity-qa.md#preview). |
| [Analytics for Target (A4T) ](/help/c-integrating-target-with-mac/a4t/a4t.md) | [!DNL Adobe Analytics for Target] (A4T) é uma integração entre soluções que permite criar atividades com base em métricas de  [!DNL Analytics] conversão e segmentos de público-alvo. A integração A4T permite usar relatórios [!DNL Analytics] para examinar os resultados.<br>Consulte  [Tipos de atividade compatíveis ](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) e Etapas  [de implementação para uma implementação](/help/c-integrating-target-with-mac/a4t/a4timplementation.md#platform) do SDK da Web da Adobe Experience Platform. |
| [Públicos-alvo](/help/c-target/target.md) | Os públicos-alvo em [!DNL Adobe Target] determinam quem vê o conteúdo e as experiências em uma atividade direcionada.<br>Consulte  [Usar a ](/help/c-target/c-audiences/audiences.md#use-list) lista de Públicos-alvo e  [Combinar vários públicos-alvo](/help/c-target/combining-multiple-audiences.md). |
| [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | O redirecionamento de ofertas faz com que os navegadores dos visitantes redirecione para uma nova página.<br>Consulte  [O  [!DNL Adobe Experience Platform Web SDK] suporte a ofertas de redirecionamento para A4T?](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#platform) |
| [Tokens de resposta](/help/administrating-target/response-tokens.md) | Os tokens de resposta permitem enviar dados do Target para o Google Analytics e outras integrações de terceiros.<br>Consulte  [Envio de dados para o Google Analytics via ](/help/administrating-target/response-tokens.md#platform-web-sdk) SDK da Web da plataforma para ver uma amostra de código de como realizar essa tarefa. |
| [Implementação de aplicativos de página única ](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/spa-implementation.html?lang=en) no guia de  *visão geral do SDK da Web da* plataforma. | [!UICONTROL O Adobe Experience Platform Web ] SDK fornece recursos avançados para sua empresa personalizar tecnologias de próxima geração no lado do cliente, como aplicativos de página única (SPA). |
| [Alterações na criptografia do TLS (Transport Layer Security)](/help/c-implementing-target/c-considerations-before-you-implement-target/tls-transport-layer-security-encryption.md) | O TLS (Transport Layer Security) ajuda a manter os mais altos padrões de segurança e a promover a segurança dos dados do cliente. |
