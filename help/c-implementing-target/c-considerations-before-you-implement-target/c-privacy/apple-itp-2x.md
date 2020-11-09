---
keywords: apple;ITP;intelligent tracking prevention
description: Informações sobre o suporte da Adobe Target para o ITP 2.x da Apple por meio da biblioteca de ID do Experience Cloud (ECID) 4.3.
title: Suporte do Adobe Target e Apple ITP
feature: privacy and security
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 54%

---


# Apple Intelligent Tracking Prevention (ITP) 2.x

Intelligent Tracking Prevention (ITP) é a iniciativa da Apple para proteger a privacidade dos usuários do Safari. A primeira versão da ITP, que foi em 2017, direcionava o uso de cookies de terceiros. Na verdade, a Apple bloqueou completamente os cookies de terceiros, o que, por sua vez, causou um grande problema para empresas de tecnologia de marketing e publicidade, pois os cookies de terceiros geralmente são usados para rastrear visitantes e coletar dados do visitante. Agora, a Apple está prestes a colocar limitações e restrições em como cookies próprios são usados no Safari.

Essas versões da ITP incluem as seguintes restrições:

| Versão | Detalhes |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Cookies limitados do lado do cliente que são colocados no navegador usando a `document.cookie` API até um prazo de sete dias.<br>Lançado em 21 de fevereiro de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Redução drástica do prazo de validade de sete dias para um dia.<br>Lançado em 24 de abril de 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Foram eliminadas várias soluções alternativas, como o uso do localStorage ou o JavaScript `Document.referrer property`.<br>Lançado em 23 de setembro de 2019. |

## Qual é o impacto para mim como cliente do Adobe Target? {#impact}

O [!DNL Target] fornece bibliotecas JavaScript para implantar em suas páginas para que o [!DNL Target] possa oferecer personalização em tempo real aos seus visitantes. Há três bibliotecas JavaScript do Target ([at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md), and [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) that place client-side [!DNL Target] cookies on your visitors&#39; browsers via the `document.cookie` API. As a result, [!DNL Target] cookies are impacted by Apple’s ITP 2.x and will expire after seven days (with ITP 2.1) and after one day (with ITP 2.2 and ITP 2.3).

O Apple ITP 2.x impacta [!DNL Target] nas seguintes áreas:

| Impacto | Detalhes |
| --- | --- |
| Aumento potencial das contagens de visitantes únicos | Devido à definição da janela de expiração para sete dias (com ITP 2.1) e um dia (com ITP 2.2 e ITP 2.3), é possível que você veja um aumento de visitantes únicos provenientes dos navegadores Safari. If your visitors revisit your domain after seven days (ITP 2.1) or one day (ITP 2.2 and ITP 2.3), [!DNL Target] is forced to place a new [!DNL Target] cookie on your domain in place of the expired cookie. O novo [!DNL Target] cookie indica um novo visitante único, mesmo que o usuário seja o mesmo. |
| Redução nos períodos de pesquisa para [!DNL Target] atividades | Os perfis de visitante para [!DNL Target] atividades podem ter um período de lookback reduzido para a tomada de decisão. Os [!DNL Target] cookies são usados para identificar um visitante e armazenar atributos de perfil do usuário para personalização. Given that [!DNL Target] cookies can be expired on Safari after seven days (ITP 2.1) or one day (ITP 2.2 and 2.3), the user profile data that was tied to the purged [!DNL Target] cookie cannot be used for decisioning. |
| Scripts de perfil com base em 3rdPartyID | Devido à definição da janela de expiração para sete dias (com ITP 2.1) e um dia (com ITP 2.2 e ITP 2.3), os scripts [de](/help/c-target/c-visitor-profile/profile-parameters.md) perfil com base no cookie 3rdPartyID deixarão de funcionar após a expiração. |
| URLs de QA/Pré-visualização em dispositivos iOS | Devido à definição da janela de expiração para sete dias (com ITP 2.1) e um dia (com ITP 2.2 e ITP 2.3), os URLs [de](/help/c-activities/c-activity-qa/activity-qa.md) QA/Pré-visualização pararão de funcionar após a expiração, pois os URLs são baseados no cookie 3rdPartyID. |

## Minha implementação atual do [!DNL Target] será afetada?

Em um navegador do Safari, navegue até o site em que você tem uma biblioteca JavaScript [!DNL Target]. If you see a [!DNL Target] cookie set in the context of a CNAME, such as `analytics.company.com`, then you are not impacted by ITP 2.x.

Se você estiver usando a biblioteca da Experience Cloud ID (ECID), além da biblioteca do Javascript do Target, sua implementação será afetada pelas formas listadas neste artigo: [Impacto da ITP 2.1 do Safari nos clientes da Adobe Experience Cloud e da Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## Como posso atenuar o impacto de futuras versões ITP 2.x para o Público alvo?

Para atenuar o impacto de futuras versões do ITP 2.x no Público alvo, conclua as seguintes tarefas:

1. Implante a biblioteca da Experience Cloud ID (ECID) em suas páginas.

   A biblioteca da ECID ativa a estrutura de identificação de pessoas para as soluções principais da Experience Cloud. A biblioteca da ECID permite identificar os mesmos visitantes do site e seus dados em diferentes soluções da Experience Cloud, atribuindo identificadores persistentes e exclusivos. A biblioteca da ECID será atualizada frequentemente para ajudar a mitigar as alterações relacionadas à ITP que afetam sua implementação.

   Para ITP 2.x, a biblioteca [ECID 4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html) deve ser usada para mitigação.

1. Use o CNAME da Adobe e inscreva-se no Programa Managed Certificate do Adobe Analytics.

   Depois de instalar a biblioteca da ECID 4.3.0+, você pode aproveitar o CNAME e o Programa Managed Certificate do Adobe Analytics. Esse programa permite implementar um certificado próprio para cookies próprios sem custos adicionais. Leveraging CNAME will help [!DNL Target] customers mitigate the impact of ITP 2.x.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

Depois de implantar uma biblioteca JavaScript do Target, em conjunto com a biblioteca da ECID v4.3.0+, e inscrever-se no Programa Adobe Managed Certificate para usar o CNAME, você terá um plano de mitigação robusto e de longo prazo para alterações relacionadas à ITP.

Conforme o setor se esforça para criar uma Web mais segura para os consumidores, o [!DNL Adobe Target] mantém o absoluto compromisso de fornecer experiências personalizadas, cumprindo e excedendo as expectativas de privacidade dos visitantes. [!DNL Adobe Target] já anunciou suporte para as Políticas [do mesmo site do](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google Chrome, além de suporte para o ITP 2.x da Apple.

À medida que as políticas continuam a evoluir para proteger nossos consumidores, o [!DNL Adobe] também continuará a oferecer suporte a essas iniciativas no [!DNL Target], enquanto ajuda nossos clientes a fornecer as melhores experiências personalizadas.
