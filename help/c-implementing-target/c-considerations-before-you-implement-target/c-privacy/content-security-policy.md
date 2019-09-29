---
description: Informações sobre diretivas de Política de segurança de conteúdo (CSP) que devem ser adicionadas ao usar o Adobe Target at.js 2.1 ou posterior.
keywords: política de segurança de conteúdo;csp;at.js;whitelist;flicker;pre-hide;pre-hide;prehide;política de segurança de conteúdo;csp;at.js;whitelist;flicker;pre-hide;pre-hide;prehide;prehide;prehide
seo-description: Informações sobre diretivas de Política de segurança de conteúdo (CSP) que devem ser adicionadas ao usar o Adobe Target at.js 2.1 ou posterior.
seo-title: Content Security Policies (CSP)
solution: Target
subtopic: Introdução
title: Diretivas de Política de Segurança de Conteúdo (CSP)
topic: Padrão
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Diretivas de Política de Segurança de Conteúdo (CSP)

Se você estiver usando a Política [de segurança de](https://en.wikipedia.org/wiki/Content_Security_Policy) conteúdo (CSP) para sua implementação do Target, adicione as seguintes diretivas CSP ao usar o [at.js 2.1 ou posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` com `*.tt.omtrdc.net` lista de permissões. Necessário para permitir a solicitação de rede para a [!DNL Target] borda.
* `style-src unsafe-inline`. Necessário para pré-ocultação e controle de oscilação.
* `script-src unsafe-inline`.  Necessário para permitir a execução do JavaScript que pode fazer parte de uma oferta HTML.
