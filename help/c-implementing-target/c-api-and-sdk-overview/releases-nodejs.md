---
description: Notas de versão relacionadas ao SDK Node.js do Adobe Target
keywords: at.js;sdk;node.js;release;updates;sdks;server side;server-side;server-side;nodejs;at.js;sdk;node.js;release;updates;sdks;server side;server-side;server-side;server-side;nodejs
seo-description: Notas de versão relacionadas às APIs do servidor do Adobe Target.
seo-title: Notas de versão relacionadas ao SDK Node.js do Adobe Target.
solution: Target
title: Notas de versão - SDK do Target Node.js
topic: Padrão
translation-type: tm+mt
source-git-commit: 540367e4c49c712df98dc132bccf4f29b4d6f095

---


# Notas de versão - SDK do Target Node.js

Notas de versão relacionadas ao SDK [Node.js do](https://github.com/adobe/target-nodejs-sdk)Adobe Target.

O SDK do Target Node.js permite que você implante o lado do [!DNL Target] servidor.

Esse SDK do Node.js ajuda você a se integrar facilmente [!DNL Target] com outras [!DNL Adobe Experience Cloud] soluções, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]e [!DNL Adobe Audience Manager].

O SDK do Node.js apresenta práticas recomendadas e remove complexidades ao integrar-se [!DNL Target] por meio de nossa API de entrega, para que suas equipes de engenharia possam se concentrar na lógica comercial.

## Versão 1.0.0 (9 de outubro de 2019)

As seções a seguir fornecem mais informações sobre a versão 1.0.0 do SDK do Target Node.js:

### Adição de

* Suporte à API de entrega de exibição do Target v1, incluindo pré-busca de Carregamento de página e Visualização.
* Suporte total para fornecer todos os tipos de ofertas criadas no Visual Experience Composer (VEC).
* Suporte para busca prévia e notificações para otimização de desempenho ao armazenar conteúdo pré-buscado em cache.
* Suporte para otimizar o desempenho em [!DNL Target] integrações híbridas via `serverState` quando [!DNL Target] é implantado tanto no servidor quanto no cliente.

   Estamos introduzindo uma configuração chamada `serverState` que contém experiências recuperadas pelo lado do servidor, para que o at.js v2.2+ não faça uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.

* Aberto originado no GitHub como SDK [do](https://github.com/adobe/target-nodejs-sdk)Target Node.js.
* Novo método [da API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientsendnotifications) sendNotifications() para enviar notificações exibidas/clicadas [!DNL Target] para conteúdo pré-buscado via [getOffers()](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers).
* Criação da solicitação da API de entrega de exibição simplificada, com preenchimento automático de campo interno com padrões (por exemplo, `request.id`, `request.context`etc.).
* Validação dos argumentos do método da API do SDK.
* Atualização do README, amostras e testes de unidade.
* Novo fluxo CI configurado usando ações GitHub.
* CoC adicionado, diretrizes de contribuição, RP e modelos de edição

### Alterado 

* Projeto renomeado para `target-nodejs-sdk`.
* Observação importante, substituindo a API do Target BatchMbox v2 pela API do Target View Delivery v1.
* [os argumentos do método](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientcreate) da API create() foram modificados, removendo o aninhamento redundante (consulte a declaração do método antigo [aqui](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate)).
* [os argumentos do método](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) da API getOffers() foram modificados (consulte a declaração do método antigo [aqui](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers)).
* O método `getTargetCookieName()` API foi substituído pelo `TargetCookieName` acessador. Consulte Acessadores do utilitário [TargetClient](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors).
* O método `getTargetLocationHintCookieName()` API foi substituído pelo `TargetLocationHintCookieName` acessador.  Consulte Acessadores do utilitário [TargetClient](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclient-utility-accessors).

### Removido

* Suporte à API do Target BatchMbox v2.
* O método [da API](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) getOffer() foi removido. Em vez disso, use o método [da API](https://git.corp.adobe.com/anischev/target-nodejs-sdk/blob/TNT-33695/README.md#targetclientgetoffers) getOffers().

