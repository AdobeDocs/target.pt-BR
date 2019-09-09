---
description: Informações sobre as diretivas de Política de Segurança de Conteúdo (CSP) que você deve adicionar ao usar o Adobe Target no. js 2.1 ou posterior.
keywords: política de segurança do conteúdo; csp; at. js; lista de permissões; oscilação; pre-hide; pré-ocultar; prehiding
seo-description: Informações sobre as diretivas de Política de Segurança de Conteúdo (CSP) que você deve adicionar ao usar o Adobe Target no. js 2.1 ou posterior.
seo-title: Políticas de segurança de conteúdo (CSP)
solution: Target
subtopic: Introdução
title: Diretivas de Política de segurança de conteúdo (CSP)
topic: Padrão
translation-type: tm+mt
source-git-commit: df40d69676cea586451e3b64b56ef602da91173f

---


# Diretivas de Política de segurança de conteúdo (CSP)

Se você estiver usando [a Política](https://en.wikipedia.org/wiki/Content_Security_Policy) de segurança de conteúdo (CSP) da implementação do Target, deverá adicionar as seguintes diretivas CSP ao usar [at. js 2.1 ou posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` com `*.tt.omtrdc.net` permissões. Necessário para permitir a solicitação de rede à [!DNL Target] borda.
* `style-src unsafe-inline`. Necessário para o controle de oscilação e oscilação.
* `script-src unsafe-inline`.  Necessário para permitir a execução do javascript que pode ser parte de uma oferta HTML.
