---
keywords: apple; ITP; prevenção de rastreamento inteligente; experience cloud id; ecid
description: Saiba mais sobre o Adobe [!DNL Target] e o impacto da iniciativa Apple Intelligent Tracking Prevention (ITP) que busca proteger a privacidade dos usuários do Safari.
title: Como o [!DNL Target] lida com o suporte à Apple ITP?
feature: Privacidade e segurança
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 50%

---

# Apple Intelligent Tracking Prevention (ITP) 2.x

Informações sobre o suporte [!DNL Adobe Target] para ITP 2.x da Apple por meio da biblioteca Experience Cloud ID (ECID) 4.3.

Intelligent Tracking Prevention (ITP) é a iniciativa da Apple para proteger a privacidade dos usuários do Safari. A primeira versão da ITP, que foi em 2017, direcionava o uso de cookies de terceiros. Na verdade, a Apple bloqueou completamente os cookies de terceiros, o que, por sua vez, causou um grande problema para empresas de tecnologia de marketing e publicidade, pois os cookies de terceiros geralmente são usados para rastrear visitantes e coletar dados do visitante. Agora, a Apple está prestes a colocar limitações e restrições em como cookies próprios são usados no Safari.

Essas versões da ITP incluem as seguintes restrições:

| Versão | Detalhes |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Cookies limitados do lado do cliente que são colocados no navegador usando a `document.cookie` API até um prazo de sete dias.<br>Lançado em 21 de fevereiro de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Redução drástica do prazo de validade de sete dias para um dia.<br>Lançado em 24 de abril de 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-2-3/) | Eliminação de várias soluções alternativas, como empregar localStorage ou usar o JavaScript `Document.referrer property`.<br>Lançado em 23 de setembro de 2019. |

## Qual é o impacto para mim como cliente do Adobe [!DNL Target]? {#impact}

O [!DNL Target] fornece bibliotecas JavaScript para implantar em suas páginas para que o [!DNL Target] possa oferecer personalização em tempo real aos seus visitantes. Há três bibliotecas JavaScript do Target ([at.js 1.x, at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e [mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md)) que colocam os cookies [!DNL Target] do lado do cliente nos navegadores de seus visitantes por meio da API `document.cookie`. Como resultado, os cookies [!DNL Target] são afetados pela ITP 2.x da Apple e expirarão após sete dias (com a ITP 2.1) e após um dia (com a ITP 2.2 e a ITP 2.3).

A Apple ITP 2.x afeta [!DNL Target] nas seguintes áreas:

| Impacto | Detalhes |
| --- | --- |
| Aumento potencial das contagens de visitantes únicos | Como a janela de expiração está sendo definida como sete dias (com a ITP 2.1) e um dia (com a ITP 2.2 e a ITP 2.3), você pode ver um aumento de visitantes únicos vindos dos navegadores Safari. Se os visitantes revisitarem seu domínio após sete dias (ITP 2.1) ou um dia (ITP 2.2 e ITP 2.3), [!DNL Target] será forçado a colocar um novo cookie [!DNL Target] em seu domínio, no lugar do cookie expirado. O novo [!DNL Target] cookie indica um novo visitante único, mesmo que o usuário seja o mesmo. |
| Redução nos períodos de pesquisa para [!DNL Target] atividades | Os perfis de visitante para [!DNL Target] atividades podem ter um período de lookback reduzido para a tomada de decisão. Os [!DNL Target] cookies são usados para identificar um visitante e armazenar atributos de perfil do usuário para personalização. Considerando que os cookies [!DNL Target] podem ser expirados no Safari após sete dias (ITP 2.1) ou um dia (ITP 2.2 e 2.3), os dados do perfil do usuário vinculados ao cookie [!DNL Target] não podem ser usados para a tomada de decisão. |
| Scripts de perfil com base em 3rdPartyID | Como a janela de expiração está sendo definida como sete dias (com ITP 2.1) e um dia (com ITP 2.2 e ITP 2.3), [scripts de perfil](/help/c-target/c-visitor-profile/profile-parameters.md) com base no cookie 3rdPartyID parará de funcionar após a expiração. |
| URLs de controle de qualidade/visualização em dispositivos iOS | Como a janela de expiração está sendo definida como sete dias (com ITP 2.1) e um dia (com ITP 2.2 e ITP 2.3), [QA/URLs de visualização](/help/c-activities/c-activity-qa/activity-qa.md) pararão de funcionar após a expiração porque os URLs são baseados no cookie 3rdPartyID. |

## Minha implementação atual do [!DNL Target] será afetada?

Em um navegador do Safari, navegue até o site em que você tem uma biblioteca JavaScript [!DNL Target]. Se você vir um cookie [!DNL Target] definido no contexto de um CNAME, como `analytics.company.com`, você não é afetado pela ITP 2.x.

Se você estiver usando a biblioteca da Experience Cloud ID (ECID), além da biblioteca do Javascript do Target, sua implementação será afetada pelas formas listadas neste artigo: [Impacto da ITP 2.1 do Safari nos clientes da Adobe Experience Cloud e da Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).

## Como posso reduzir o impacto das próximas versões da ITP 2.x no Target?

Para reduzir o impacto de futuras versões da ITP 2.x no Target, realize as seguintes tarefas:

1. Implante a biblioteca da Experience Cloud ID (ECID) em suas páginas.

   A biblioteca da ECID ativa a estrutura de identificação de pessoas para as soluções principais da Experience Cloud. A biblioteca da ECID permite identificar os mesmos visitantes do site e seus dados em diferentes soluções da Experience Cloud, atribuindo identificadores persistentes e exclusivos. A biblioteca da ECID será atualizada frequentemente para ajudar a mitigar as alterações relacionadas à ITP que afetam sua implementação.

   Para ITP 2.x, [A biblioteca ECID 4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html) deve ser usada para mitigação.

1. Use o CNAME da Adobe e inscreva-se no Programa Managed Certificate do Adobe Analytics.

   Depois de instalar a biblioteca da ECID 4.3.0+, você pode aproveitar o CNAME e o Programa Managed Certificate do Adobe Analytics. Esse programa permite implementar um certificado próprio para cookies próprios sem custos adicionais. O uso do CNAME ajudará os clientes [!DNL Target] a minimizar o impacto da ITP 2.x.

   Se não estiver usando o CNAME, inicie o processo falando com o representante de conta e se inscrevendo no [Adobe Managed Certificate Program](https://experienceleague.adobe.com/docs/core-services/interface/ec-cookies/cookies-first-party.html#adobe-managed-certificate-program).

Depois de implantar uma biblioteca JavaScript do Target, em conjunto com a biblioteca da ECID v4.3.0+, e inscrever-se no Programa Adobe Managed Certificate para usar o CNAME, você terá um plano de mitigação robusto e de longo prazo para alterações relacionadas à ITP.

Conforme o setor se esforça para criar uma Web mais segura para os consumidores, o [!DNL Adobe Target] mantém o absoluto compromisso de fornecer experiências personalizadas, cumprindo e excedendo as expectativas de privacidade dos visitantes. [!DNL Adobe Target] A já anunciou suporte para as Políticas do SameSite Chrome do  [ ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/google-chrome-samesite-cookie-policies.md) Google, além de oferecer suporte para a ITP 2.x da Apple.

À medida que as políticas continuam a evoluir para proteger nossos consumidores, o [!DNL Adobe] também continuará a oferecer suporte a essas iniciativas no [!DNL Target], enquanto ajuda nossos clientes a fornecer as melhores experiências personalizadas.
