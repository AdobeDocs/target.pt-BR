---
description: Informações sobre o suporte do Target para ITP 2.1 e ITP 2.2 da Apple por meio da biblioteca da Experience Cloud ID (ECID) 4.3.
keywords: maçã;ITP;prevenção de rastreamento inteligente
seo-description: Informações sobre o suporte do Adobe Target para ITP 2.1 e ITP 2.2 da Apple por meio da biblioteca da Experience Cloud ID (ECID) 4.3.
seo-title: Suporte ao Adobe Target e Apple ITP
solution: Target
subtopic: Introdução
title: Apple ITP 2.x
topic: Padrão
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Apple Intelligent Tracking Prevention (ITP) 2.x

A Prevenção de rastreamento inteligente (ITP) é a iniciativa da Apple para proteger a privacidade dos usuários do Safari. A primeira versão do ITP, que foi lançada em 2017, teve como objetivo o uso de cookies de terceiros. Na verdade, a Apple bloqueou cookies de terceiros na sua totalidade, o que, por sua vez, causou uma grave dor de cabeça para as empresas de tecnologia de anúncios e de tecnologia de marketing, pois os cookies de terceiros geralmente são usados para rastrear visitantes e coletar dados de visitantes. Agora, a Apple está em movimento para colocar limitações e restrições sobre como os cookies primários são usados no Safari.

Essas versões do ITP incluem as seguintes restrições:

| Versão | Detalhes |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Cookies do lado do cliente reduzidos que são colocados no navegador usando a `document.cookie` API para uma expiração de sete dias.<br>Lançamento em 21 de fevereiro de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Reduziu drasticamente o prazo de validade de sete dias para um dia.<br>Lançamento em 24 de abril de 2019. |

## Qual é o impacto para mim como cliente do Adobe Target?

[!DNL Target] fornece bibliotecas JavaScript para que você possa implantar em suas páginas para que [!DNL Target] possam fornecer personalização em tempo real aos seus visitantes. Há três bibliotecas JavaScript do Target ([at.js 1).*x* e at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)e [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) que colocam [!DNL Target] cookies do cliente nos navegadores dos visitantes por meio da `document.cookie` API. Como resultado, [!DNL Target] os cookies são afetados pelo ITP 2.1 e 2.2 da Apple e expiram após sete dias (com ITP 2.1) e um dia depois (com ITP 2.2).

Impacto da Apple ITP 2.1 e 2.1 [!DNL Target] nas seguintes áreas:

| Impacto | Detalhes |
| --- | --- |
| Aumento potencial da contagem de visitantes únicos | Devido à definição da janela de expiração para sete dias (com ITP 2.1) e um dia (com ITP 2.2), você pode ver um aumento de visitantes únicos provenientes de navegadores Safari. Se os visitantes visitarem novamente seu domínio após sete dias (ITP 2.1) ou um dia (ITP 2.2), [!DNL Target] será forçado a colocar um novo [!DNL Target] cookie no seu domínio no lugar do cookie expirado. O novo [!DNL Target] cookie se traduz em um novo visitante único, mesmo que o usuário seja o mesmo. |
| Períodos de pesquisa reduzidos para [!DNL Target] atividades | Os perfis de visitante para [!DNL Target] atividades podem ter um período de pesquisa para decisão. [!DNL Target] os cookies são utilizados para identificar um visitante e armazenar atributos de perfil de usuário para personalização. Como os [!DNL Target] cookies podem expirar no Safari após sete dias (ITP 2.1) ou um dia (ITP 2.2), os dados do perfil do usuário que foram vinculados ao [!DNL Target] cookie removido não podem ser usados para decisão. |

## Minha implementação atual de [!DNL Target] impacto?

Em um navegador Safari, navegue até seu site no qual você tem uma biblioteca [!DNL Target] JavaScript. Se você vir um [!DNL Target] cookie definido no contexto de um CNAME, como `analytics.company.com`, você não será afetado pelo ITP 2.1 ou 2.2.

Se você estiver usando a biblioteca da Experience Cloud ID (ECID) além da biblioteca do Target JavaScript, sua implementação será afetada das formas listadas neste artigo: Impacto do ITP 2.1 do [Safari ITP 2.1 nos clientes](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac)da Adobe Experience Cloud e da Experience Platform.

## Como posso atenuar o impacto das versões ITP 2.1, ITP 2.2 e ITP futuras para [!DNL Target]?

Para atenuar o impacto das versões ITP 2.1, ITP 2.2 e ITP futuras para [!DNL Target], conclua as seguintes tarefas:

1. Implante a biblioteca da Experience Cloud ID (ECID) em suas páginas.

   A biblioteca ECID permite a estrutura de identificação de pessoas para as soluções principais da Experience Cloud. A biblioteca ECID permite identificar os mesmos visitantes do site e seus dados em diferentes soluções da Experience Cloud, atribuindo identificadores persistentes e exclusivos. A biblioteca ECID será atualizada com frequência para ajudar a atenuar as alterações relacionadas ao ITP que afetam sua implementação.

   Para ITP 2.1 e ITP 2.2, a biblioteca [ECID 4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) deve ser usada para mitigação.

1. Use o CNAME e a inscrição da Adobe no programa de certificados gerenciados do Adobe Analytics.

   Depois de instalar a biblioteca ECID 4.3.0+, você pode aproveitar o CNAME e o Managed Certificate Program do Adobe Analytics. Este programa permite que você implemente um certificado primário para cookies primários sem custos. Aproveitar o CNAME ajudará [!DNL Target] os clientes a atenuar o impacto do ITP 2.1 e do ITP 2.2.

   Se você não estiver aproveitando o CNAME, poderá iniciar o processo conversando com seu representante de conta e inscrevendo-se no Programa [](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program)Adobe Managed Certificate.

Depois de implantar uma biblioteca JavaScript do Target em conjunto com a biblioteca ECID v4.3.0+ e inscrever-se no Programa de certificados gerenciados da Adobe para aproveitar o CNAME, você terá um plano de mitigação robusto e de longo prazo para as alterações relacionadas ao ITP.

As the industry makes strides to create a more secure web for consumers, [!DNL Adobe Target] is absolutely committed to delivering personalized experiences while meeting and exceeding the privacy expectations of visitors. [!DNL Adobe Target] já anunciou suporte para as Políticas [do mesmo site do](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google Chrome, além de suporte para ITP 2.1 e ITP 2.2 da Apple.

À medida que as políticas forem evoluindo para proteger nossos consumidores, também [!DNL Adobe] continuarão a oferecer suporte a essas iniciativas no [!DNL Target]mercado, ajudando nossos clientes a fornecer as melhores experiências personalizadas da classe.
