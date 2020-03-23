---
keywords: apple;ITP;intelligent tracking prevention
description: Informações sobre suporte do Adobe Target para ITP 2.1 e ITP 2.2 da Apple por meio da biblioteca Experience Cloud ID (ECID) 4.3.
title: Suporte do Adobe Target e Apple ITP
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 0fad08727233566dae6e948e53cda4f7acb64f6f

---


# Apple Intelligent Tracking Prevention (ITP) 2.x

Intelligent Tracking Prevention (ITP) é a iniciativa da Apple para proteger a privacidade dos usuários do Safari. A primeira versão da ITP, que foi em 2017, direcionava o uso de cookies de terceiros. Na verdade, a Apple bloqueou completamente os cookies de terceiros, o que, por sua vez, causou um grande problema para empresas de tecnologia de marketing e publicidade, pois os cookies de terceiros geralmente são usados para rastrear visitantes e coletar dados do visitante. Agora, a Apple está prestes a colocar limitações e restrições em como cookies próprios são usados no Safari.

Essas versões da ITP incluem as seguintes restrições:

| Versão | Detalhes |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Cookies limitados do lado do cliente que são colocados no navegador usando a `document.cookie` API até um prazo de sete dias.<br>Lançado em 21 de fevereiro de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Redução drástica do prazo de validade de sete dias para um dia.<br>Lançado em 24 de abril de 2019. |

## Qual é o impacto para mim como cliente do Adobe Target? {#impact}

O [!DNL Target] fornece bibliotecas JavaScript para implantar em suas páginas para que o [!DNL Target] possa oferecer personalização em tempo real aos seus visitantes. Há três bibliotecas JavaScript do Target ([at.js 1.x and at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md), and [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) that place client-side [!DNL Target] cookies on your visitors&#39; browsers via the `document.cookie` API. Como resultado, os [!DNL Target] cookies são afetados pela ITP 2.1 e 2.2 da Apple e expirarão após sete dias (com a ITP 2.1) e após um dia (com a ITP 2.2).

As versões Apple ITP 2.1 e 2.2 afetam o [!DNL Target] nas seguintes áreas:

| Impacto | Detalhes |
| --- | --- |
| Aumento potencial das contagens de visitantes únicos | Como a janela de expiração está sendo definida como sete dias (com a ITP 2.1) e um dia (com a ITP 2.2), você pode ver um aumento de visitantes únicos vindos dos navegadores do Safari. Se os visitantes revisitarem seu domínio após sete dias (ITP 2.1) ou um dia (ITP 2.2), o [!DNL Target] será forçado a colocar um novo [!DNL Target] cookie em seu domínio, no lugar do cookie expirado. O novo [!DNL Target] cookie indica um novo visitante único, mesmo que o usuário seja o mesmo. |
| Redução nos períodos de pesquisa para [!DNL Target] atividades | Os perfis de visitante para [!DNL Target] atividades podem ter um período de lookback reduzido para a tomada de decisão. Os [!DNL Target] cookies são usados para identificar um visitante e armazenar atributos de perfil do usuário para personalização. Considerando que os [!DNL Target] cookies podem ser expirados no Safari após sete dias (ITP 2.1) ou um dia (ITP 2.2), os dados de perfil do usuário vinculados ao [!DNL Target] cookie não podem ser usados para a tomada de decisão. |
| Scripts de perfil baseados em 3rdPartyID | Devido à definição da janela de expiração para sete dias (com ITP 2.1) e um dia (com ITP 2.2), os scripts [de](/help/c-target/c-visitor-profile/profile-parameters.md) perfil com base no cookie 3rdPartyID deixarão de funcionar após a expiração. |
| URLs de QA/visualização em dispositivos iOS | Devido à definição da janela de expiração para sete dias (com ITP 2.1) e um dia (com ITP 2.2), os URLs [de](/help/c-activities/c-activity-qa/activity-qa.md) QA/Visualização pararão de funcionar após a expiração, pois os URLs são baseados no cookie 3rdPartyID. |

## Minha implementação atual do [!DNL Target] será afetada?

Em um navegador do Safari, navegue até o site em que você tem uma biblioteca JavaScript [!DNL Target]. Se você vir um [!DNL Target] cookie definido no contexto de um CNAME, como `analytics.company.com`, você não é afetado pela ITP 2.1 ou 2.2.

Se você estiver usando a biblioteca da Experience Cloud ID (ECID), além da biblioteca do Javascript do Target, sua implementação será afetada pelas formas listadas neste artigo: [Impacto da ITP 2.1 do Safari nos clientes da Adobe Experience Cloud e da Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## Como posso reduzir o impacto da ITP 2.1, da ITP 2.2 e das próximas versões da ITP?[!DNL Target]

Para reduzir o impacto da ITP 2.1, da ITP 2.2 e das próximas versões da ITP no [!DNL Target], realize as seguintes tarefas:

1. Implante a biblioteca da Experience Cloud ID (ECID) em suas páginas.

   A biblioteca da ECID ativa a estrutura de identificação de pessoas para as soluções principais da Experience Cloud. A biblioteca da ECID permite identificar os mesmos visitantes do site e seus dados em diferentes soluções da Experience Cloud, atribuindo identificadores persistentes e exclusivos. A biblioteca da ECID será atualizada frequentemente para ajudar a mitigar as alterações relacionadas à ITP que afetam sua implementação.

   Para ITP 2.1 e ITP 2.2, a biblioteca [ECID 4.3.0+](https://docs.adobe.com/content/help/en/id-service/using/release-notes/release-notes.html) deve ser usada para mitigação.

1. Use o CNAME da Adobe e inscreva-se no Programa Managed Certificate do Adobe Analytics.

   Depois de instalar a biblioteca da ECID 4.3.0+, você pode aproveitar o CNAME e o Programa Managed Certificate do Adobe Analytics. Esse programa permite implementar um certificado próprio para cookies próprios sem custos adicionais. O uso do CNAME ajudará os clientes do [!DNL Target] a minimizar o impacto da ITP 2.1 e da ITP 2.2.

   If you are not leveraging CNAME, you can start the process by talking with your account representative and enrolling in the [Adobe Managed Certificate Program](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

Depois de implantar uma biblioteca JavaScript do Target, em conjunto com a biblioteca da ECID v4.3.0+, e inscrever-se no Programa Adobe Managed Certificate para usar o CNAME, você terá um plano de mitigação robusto e de longo prazo para alterações relacionadas à ITP.

Conforme o setor se esforça para criar uma Web mais segura para os consumidores, o [!DNL Adobe Target] mantém o absoluto compromisso de fornecer experiências personalizadas, cumprindo e excedendo as expectativas de privacidade dos visitantes. A [!DNL Adobe Target] já anunciou suporte para [Google’s SameSite Chrome Policies](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md), além de oferecer suporte para a ITP 2.1 e para a ITP 2.2 da Apple.

À medida que as políticas continuam a evoluir para proteger nossos consumidores, o [!DNL Adobe] também continuará a oferecer suporte a essas iniciativas no [!DNL Target], enquanto ajuda nossos clientes a fornecer as melhores experiências personalizadas.
