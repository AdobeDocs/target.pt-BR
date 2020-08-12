---
keywords: content security policy;csp;at.js;whitelist;allowlist;flicker;pre-hide;pre-hiding;prehiding
description: Informações sobre diretivas de Política de segurança de conteúdo (CSP) que devem ser adicionadas ao usar o Adobe Target at.js 2.1 ou posterior.
title: Políticas de segurança de conteúdo (CSP)
feature: null
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 5%

---


# Diretivas da Política de segurança de conteúdo (CSP)

Se você estiver usando a Política [de Segurança de](https://en.wikipedia.org/wiki/Content_Security_Policy) Conteúdo (CSP) para sua implementação de Público alvo, adicione as seguintes diretivas CSP ao usar o [at.js 2.1 ou posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` com `*.tt.omtrdc.net` incluir na lista de permissões. Necessário para permitir a solicitação de rede para a [!DNL Target] borda.
* `style-src unsafe-inline`. Necessário para pré-ocultação e controle de oscilação.
* `script-src unsafe-inline`.  Necessário para permitir a execução do JavaScript que pode fazer parte de uma oferta HTML.
