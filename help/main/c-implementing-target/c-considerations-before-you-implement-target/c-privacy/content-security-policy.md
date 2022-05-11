---
keywords: política de segurança de conteúdo;csp;at.js;lista de permissões;lista de permissão;cintilação;pré-ocultar;pré-oculto;pré-ocultação
description: Saiba mais sobre as diretivas de Política de segurança de conteúdo (CSP) que devem ser adicionadas ao usar o Adobe Target.
title: Como o [!DNL Target] lida com as Políticas de segurança de conteúdo (CSP)?
feature: Privacy & Security
role: Developer
exl-id: 31457b16-ed21-4540-8d0c-abfb49d1fbe9
source-git-commit: db632225d21c2e061e82269bec168341b410575a
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 29%

---

# Diretivas da Política de segurança de conteúdo (CSP)

Se estiver usando a [Política de segurança de conteúdo](https://en.wikipedia.org/wiki/Content_Security_Policy) (CSP) na implementação do [!DNL Adobe Target], você deve adicionar as seguintes diretivas da CSP ao usar [at.js 2.1 ou posterior](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md):

* `connect-src` com o `*.tt.omtrdc.net` na lista de permissões. Necessário para permitir a solicitação de rede para a borda do [!DNL Target].
* `style-src unsafe-inline`. Necessário para controle de pré-ocultação e cintilação.
* `script-src unsafe-inline`.  Necessário para permitir a execução do JavaScript que pode fazer parte de uma oferta do HTML.

## Perguntas frequentes

Consulte as seguintes perguntas frequentes sobre políticas de segurança:

### O CORS (Cross Origin Resource Sharing) e as políticas entre domínios do Flash apresentam problemas de segurança?

A maneira recomendada de implementar a política do CORS é permitir acesso somente a origens confiáveis que exigem isso por meio de uma lista de permissões de domínios confiáveis. O mesmo pode ser dito para a política entre domínios do Flash. Algumas [!DNL Adobe Target] os clientes estão preocupados com o uso de caracteres curingas para domínios em [!DNL Target]. A preocupação é que, se um usuário estiver conectado a um aplicativo e visitar um domínio permitido pela política, qualquer conteúdo mal-intencionado em execução nesse domínio poderá recuperar conteúdo confidencial do aplicativo e realizar ações dentro do contexto de segurança do usuário conectado. Isso geralmente é chamado de CSRF (Cross-Site Request Forgery).

Em um [!DNL Adobe Target] no entanto, estas políticas não devem representar um problema de segurança.

&quot;adobe.tt.omtrdc.net&quot; é um domínio de propriedade do Adobe. [!DNL Adobe Target] é uma ferramenta de teste e personalização e espera-se que [!DNL Target] O pode receber e processar solicitações de qualquer lugar sem exigir autenticação. Essas solicitações contêm pares de chave/valor usados para testes A/B, recomendações ou personalização de conteúdo.

[!DNL Adobe] não armazena informações pessoais identificáveis (PII) ou outras informações confidenciais em [!DNL Adobe Target] servidores de borda, aos quais &quot;adobe.tt.omtrdc.net&quot; aponta.

Espera-se que [!DNL Target] pode ser acessada de qualquer domínio por meio de chamadas JavaScript. A única maneira de permitir esse acesso é aproveitando &quot;Controle de acesso com permissão de origem&quot; com um curinga.
