---
keywords: política de segurança de conteúdo; csp; at.js; whitelist;  de lista de permissões; cintilação; pré-ocultar; pré-ocultação; pré-ocultação
description: Saiba mais sobre as diretivas de Política de segurança de conteúdo (CSP) que devem ser adicionadas ao usar o Adobe Target.
title: Como [!DNL Target] Lidar com as políticas de segurança de conteúdo (CSP)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '97'
ht-degree: 5%

---

# Diretivas da Política de segurança de conteúdo (CSP)

Se estiver usando [Política de segurança de conteúdo](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para sua [!DNL Adobe Target] , você deve adicionar as seguintes diretivas CSP ao usar [at.js 2.1 ou posterior](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` com `*.tt.omtrdc.net` incluir na lista de permissões. Necessário para permitir a solicitação de rede para o [!DNL Target] borda.
* `style-src unsafe-inline`. Necessário para pré-ocultação e controle de cintilação.
* `script-src unsafe-inline`.  Necessário para permitir a execução do JavaScript que pode fazer parte de uma oferta do HTML.
