---
keywords: política de segurança de conteúdo;csp;at.js;whitelist;lista de permissões;flicker;pre-hide;pre-hide;prehide;política de segurança de conteúdo;csp;at.js;whitelist;
description: Saiba mais sobre as diretivas de Política de segurança de conteúdo (CSP) que você deve adicionar ao usar o Adobe Target.
title: Como o Público alvo lida com as políticas de segurança de conteúdo (CSP)?
feature: Privacy & Security
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 5%

---


# Diretivas da Política de segurança de conteúdo (CSP)

Se você estiver usando [Política de segurança de conteúdo](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para sua implementação [!DNL Adobe Target], adicione as seguintes diretivas CSP ao usar [at.js 2.1 ou posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` com  `*.tt.omtrdc.net` incluir na lista de permissões. Necessário para permitir a solicitação de rede para a borda [!DNL Target].
* `style-src unsafe-inline`. Necessário para pré-ocultação e controle de oscilação.
* `script-src unsafe-inline`.  Necessário para permitir a execução do JavaScript que pode fazer parte de uma oferta HTML.
