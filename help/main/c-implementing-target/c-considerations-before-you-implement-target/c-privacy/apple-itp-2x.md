---
keywords: apple; ITP; prevenção de rastreamento inteligente; experience cloud id; ecid; itp
description: Saiba mais sobre o Adobe [!DNL Target] e o impacto da iniciativa Apple Intelligent Tracking Prevention (ITP) que busca proteger a privacidade dos usuários do Safari.
title: Como [!DNL Target] Gerenciar o suporte à Apple ITP?
feature: Privacy & Security
role: Developer
exl-id: 05a62be5-ccfb-4d5c-b511-35023b95e567
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '589'
ht-degree: 38%

---

# Apple Intelligent Tracking Prevention (ITP) 2.x

Intelligent Tracking Prevention (ITP) é a iniciativa da Apple para proteger a privacidade dos usuários do Safari. A primeira versão da ITP, que foi em 2017, direcionava o uso de cookies de terceiros. Na verdade, a Apple bloqueou completamente os cookies de terceiros, o que, por sua vez, causou um grande problema para empresas de tecnologia de marketing e publicidade, pois os cookies de terceiros geralmente são usados para rastrear visitantes e coletar dados do visitante. Agora, a Apple está prestes a colocar limitações e restrições em como cookies próprios são usados no Safari.

Essas versões da ITP incluem as seguintes restrições:

| Versão | Detalhes |
| --- | --- |
| [ITP 2.1](https://webkit.org/blog/8613/intelligent-tracking-prevention-2-1/) | Cookies limitados do lado do cliente que são colocados no navegador usando a `document.cookie` API até um prazo de sete dias.<br>Lançado em 21 de fevereiro de 2019. |
| [ITP 2.2](https://webkit.org/blog/8828/intelligent-tracking-prevention-2-2/) | Redução drástica do prazo de validade de sete dias para um dia.<br>Lançado em 24 de abril de 2019. |
| [ITP 2.3](https://webkit.org/blog/9521/intelligent-tracking-prevention-3-2/) | Eliminação de várias soluções alternativas, como a utilização de localStorage ou o uso do JavaScript `Document.referrer property`.<br>Lançado em 23 de setembro de 2019.<br>Recurso de defesa de cloaking CNAME para ITP, lançado no Safari 14, macOS Big Sur, Catalina, Mojave, iOS 14 e iPadOS 14. Todos os cookies criados por uma resposta HTTP colada por CNAME de terceiros serão definidos para expirar em sete dias.<br>Anunciado em 12 de novembro de 2020. |

## Qual é o impacto para mim como Adobe [!DNL Target] cliente? {#impact}

O [!DNL Target] fornece bibliotecas JavaScript para implantar em suas páginas para que o [!DNL Target] possa oferecer personalização em tempo real aos seus visitantes. Há três bibliotecas JavaScript do Target at.js 1.x, at.js 2.x que colocam o lado do cliente [!DNL Target] nos navegadores de seus visitantes por meio do `document.cookie` API. Como resultado, [!DNL Target] os cookies são afetados pela ITP 2.1, 2.2 e 2.3 da Apple e expirarão após sete dias (com a ITP 2.1) e após um dia (com a ITP 2.2 e a ITP 2.3).

Impactos da ITP 2.x do Apple [!DNL Target] nas seguintes áreas:

| Impacto | Detalhes |
| --- | --- |
| Aumento potencial das contagens de visitantes únicos | Como a janela de expiração está sendo definida como sete dias (com a ITP 2.1) e um dia (com a ITP 2.2 e a ITP 2.3), você pode ver um aumento de visitantes únicos vindos dos navegadores Safari. Se os visitantes revisitarem seu domínio após sete dias (ITP 2.1) ou um dia (ITP 2.2 e ITP 2.3), [!DNL Target] é forçada a colocar um novo [!DNL Target] no seu domínio, no lugar do cookie expirado. O novo [!DNL Target] cookie indica um novo visitante único, mesmo que o usuário seja o mesmo. |
| Redução nos períodos de pesquisa para [!DNL Target] atividades | Os perfis de visitante para [!DNL Target] atividades podem ter um período de lookback reduzido para a tomada de decisão. Os [!DNL Target] cookies são usados para identificar um visitante e armazenar atributos de perfil do usuário para personalização. Dado que [!DNL Target] os cookies podem ser expirados no Safari após sete dias (ITP 2.1) ou um dia (ITP 2.2 e 2.3), os dados de perfil do usuário que foram vinculados à limpeza [!DNL Target] não pode ser usado para a tomada de decisão. |
| Scripts de perfil com base em 3rdPartyID | Devido ao período de expiração estar definido como sete dias (com ITP 2.1) e um dia (com ITP 2.2 e ITP 2.3), [scripts de perfil](/help/main/c-target/c-visitor-profile/profile-parameters.md) com base no cookie 3rdPartyID, o funcionamento cessará após a expiração. |
| URLs de controle de qualidade/visualização em dispositivos iOS | Devido ao período de expiração estar definido como sete dias (com ITP 2.1) e um dia (com ITP 2.2 e ITP 2.3), [URLs de controle de qualidade/visualização](/help/main/c-activities/c-activity-qa/activity-qa.md) O parará de funcionar após a expiração, pois os URLs são baseados no cookie 3rdPartyID. |

## Minha implementação atual do [!DNL Target] será afetada?

Se estiver usando a biblioteca de ID do Experience Cloud (ECID), além da [!DNL Target] Biblioteca de JavaScript, sua implementação será afetada pelas formas listadas neste artigo: [Impacto do Safari ITP 2.1 nos clientes do Adobe Experience Cloud e do Experience Platform](https://medium.com/adobetech/safari-itp-2-1-impact-on-adobe-experience-cloud-customers-9439cecb55ac).
