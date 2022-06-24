---
keywords: política de segurança de conteúdo;csp;at.js;lista de permissões;lista de permissão;cintilação;pré-ocultar;pré-oculto;pré-ocultação
description: Saiba mais sobre as diretivas de Política de segurança de conteúdo (CSP) que devem ser adicionadas ao usar o Adobe Target.
title: Como o  [!DNL Target]  lida com as Políticas de segurança de conteúdo (CSP)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 90%

---

# Diretivas da Política de segurança de conteúdo (CSP)

Se estiver usando [Política de segurança de conteúdo](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) para sua [!DNL Adobe Target] , você deve adicionar as seguintes diretivas CSP ao usar [at.js 2.1 ou posterior](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}:

* `connect-src` com o `*.tt.omtrdc.net` na lista de permissões. Necessário para permitir a solicitação de rede para a borda do [!DNL Target].
* `style-src unsafe-inline`. Necessário para controle de pré-ocultação e cintilação.
* `script-src unsafe-inline`.  Necessário para permitir a execução do JavaScript que pode fazer parte de uma oferta do HTML.

## Perguntas frequentes

Consulte as seguintes perguntas frequentes sobre políticas de segurança:

### O CORS (Compartilhamento de recursos entre origens) e as políticas entre domínios do Flash apresentam problemas de segurança?

A maneira recomendada de implementar a política CORS é permitir o acesso apenas a origens confiáveis que o exijam por meio de uma lista de permissões de domínios confiáveis. O mesmo pode ser dito para a política entre domínios do Flash. Alguns clientes do [!DNL Adobe Target] estão preocupados com o uso de caracteres curingas para domínios no [!DNL Target]. A preocupação é que, se um usuário estiver conectado a um aplicativo e visitar um domínio permitido pela política, qualquer conteúdo mal-intencionado em execução nesse domínio poderá recuperar conteúdo confidencial do aplicativo e realizar ações dentro do contexto de segurança do usuário conectado. Geralmente, essa ação é chamada de CSRF (Falsificação de solicitação entre sites).

No entanto, em uma implementação do [!DNL Adobe Target], estas políticas não devem representar um problema de segurança.

“adobe.tt.omtrdc.net” é um domínio de propriedade da Adobe. O [!DNL Adobe Target] é uma ferramenta de teste e personalização e espera-se que o [!DNL Target] possa receber e processar solicitações de qualquer lugar sem exigir autenticação. Essas solicitações contêm pares de chave/valor usados para testes A/B, recomendações ou personalização de conteúdo.

O [!DNL Adobe] não armazena informações pessoais identificáveis (PII) ou outras informações confidenciais em servidores de borda do [!DNL Adobe Target], para os quais “adobe.tt.omtrdc.net” aponta.

Espera-se que o [!DNL Target] possa ser acessado de qualquer domínio por meio de chamadas JavaScript. A única maneira de permitir esse acesso é usando “Access-Control-Allow-Origin” com um curinga.
