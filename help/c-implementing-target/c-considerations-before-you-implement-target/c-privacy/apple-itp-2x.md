---
description: Informações sobre o suporte do Target para ITP 2.1 e ITP 2.2 da Apple pela biblioteca da Experience Cloud ID (ECID) 4.3.
keywords: apple; ITP; prevenção de rastreamento inteligente
seo-description: Informações sobre o suporte do Adobe Target para ITP 2.1 e ITP 2.2 da Apple pela biblioteca da Experience Cloud ID (ECID) 4.3.
seo-title: Suporte ao Adobe Target e à Apple ITP
solution: Target
subtopic: Introdução
title: Apple ITP 2. x
topic: Padrão
translation-type: tm+mt
source-git-commit: 71419ee6053eeb86ab6595cfba2f05d8506e05b3

---


# Apple Intelligent Tracking Prevention (ITP) 2. x

A Prevenção de rastreamento inteligente (ITP) é a iniciativa da Apple para proteger a privacidade dos usuários do Safari. A primeira versão do ITP, que estava em 2017, direcionada ao uso de cookies de terceiros. Na verdade, a Apple bloqueou os cookies de terceiros, que, por sua vez, causavam uma acache intensa para empresas técnicas e técnicas de especialistas, pois os cookies de terceiros geralmente são usados para rastrear visitantes e coletar dados de visitantes. Agora, a Apple está em movimento para colocar limitações e restrições sobre como os cookies primários são usados no Safari.

Essas versões do ITP incluem as seguintes restrições:

| Versão | Detalhes |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Capped client-side cookies that are placed on the browser using the `document.cookie` API to a seven-day expiry.<br>Lançado em 21 de fevereiro de 21 19. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Reduza drasticamente o cap de expiração de sete dias para um dia.<br>Lançado em 24 de abril de 2019. |

## Qual é o impacto para mim como cliente do Adobe Target?

[!DNL Target] fornece bibliotecas javascript para você implantar em suas páginas para [!DNL Target] oferecer personalização em tempo real aos seus visitantes. There are three Target JavaScript libraries ([at.js 1.*x* e at. js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)e [mbox. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) que posicionam [!DNL Target] os cookies do cliente nos navegadores de seus visitantes por meio da `document.cookie` API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.1 and 2.2 and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2).

Apple ITP 2.1 and 2.1 impact [!DNL Target] in the following areas:

| Impacto | Detalhes |
| --- | --- |
| Aumento potencial das contagens de visitantes únicos | Devido à janela de expiração estar sendo definida como sete dias (com ITP 2.1) e um dia (com ITP 2.2), você pode ver um aumento de visitantes únicos vindos de navegadores Safari. If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. The new [!DNL Target] cookie translates to a new unique visitor even though the user is the same. |
| Decreased lookback periods for [!DNL Target] activities | Visitor profiles for [!DNL Target] activities might have a decreased lookback period for decisioning. [!DNL Target] os cookies aproveitam a identidade de um visitante e armazenam atributos de perfil de usuário para personalização. Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |

## Is my current implementation of [!DNL Target] impacted?

In a Safari browser, navigate to your website on which you have a [!DNL Target] JavaScript library. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.1 or 2.2.

If you are using the Experience Cloud ID (ECID) library in addition to the Target JavaScript library, your implementation will be impacted in the ways listed in this article: [Safari ITP 2.1 Impact on Adobe Experience Cloud and Experience Platform Customers](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## How can I mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target]?

To mitigate the impact of ITP 2.1, ITP 2.2, and future ITP releases to [!DNL Target], complete the following tasks:

1. Implante a biblioteca da Experience Cloud ID (ECID) às suas páginas.

   A biblioteca ECID ativa a estrutura de identificação de pessoas para soluções principais da Experience Cloud. A biblioteca ECID permite identificar os mesmos visitantes do site e seus dados em soluções diferentes da Experience Cloud atribuindo identificadores persistentes e exclusivos. A biblioteca ECID será atualizada frequentemente para ajudar a mitigar quaisquer alterações relacionadas ao ITP que afetam sua implementação.

   For ITP 2.1 and ITP 2.2, [ECID library 4.3.0+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) must be utilized for mitigation.

1. Use o CNAME e o inscrito da Adobe no programa de certificados gerenciados do Adobe Analytics.

   Depois de instalar a biblioteca ECID 4.3.0 +, você pode aproveitar o Adobe Analytics «CNAME e o Programa de certificado gerenciado». Esse programa permite implementar um certificado próprio para cookies primários sem custos adicionais. Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.1 and ITP 2.2.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/adobe_managed_cert_pgm.html).

Depois de implantar uma biblioteca do Target javascript em conjunto com a biblioteca ECID v 4.3.0 + e inscrever-se no Adobe Managed Certificate Program para aproveitar o CNAME, você terá um plano de minimização robusto e longo para alterações relacionadas ao ITP.

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] já anunciou suporte para [as Políticas](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) do Google Chrome do Google, além de oferecer suporte para ITP 2.1 e ITP 2.2 da Apple.

As policies continue to evolve to protect our consumers, [!DNL Adobe] will also continue to support these initiatives in [!DNL Target], while helping our customers provide the best-in-class personalized experiences.
