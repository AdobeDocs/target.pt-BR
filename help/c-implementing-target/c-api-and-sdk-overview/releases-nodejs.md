---
keywords: at.js;sdk;node.js;release;updates;sdks;server side;serverside;server-side;nodejs
description: Notas de versão relacionadas às APIs do lado do servidor da Adobe Target.
title: Notas de versão relacionadas ao Adobe Target Node.js SDK.
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: 21c49efb4b5de0ae14215712f4ec87b4759f29e1
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 1%

---


# Notas de versão - SDK Node.js do Target

Notas de versão relacionadas ao SDK [Node.js do](https://github.com/adobe/target-nodejs-sdk)Adobe Target.

O SDK do Público alvo Node.js permite que você implante no lado do [!DNL Target] servidor.

Esse SDK do Node.js ajuda você a se integrar facilmente [!DNL Target] com outras [!DNL Adobe Experience Cloud] soluções, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]e [!DNL Adobe Audience Manager].

O SDK do Node.js apresenta práticas recomendadas e remove complexidades ao integrar-se [!DNL Target] por meio de nossa API de delivery para que suas equipes de engenharia possam se concentrar na lógica comercial.

Saiba mais sobre o SDK do Público alvo Node.js no Blog técnico do Adobe - [Abrir Sourcing the New Adobe Target Node.js SDK](https://medium.com/adobetech/open-sourcing-the-new-adobe-target-node-js-sdk-b6feafd828bc).

## Versão 1.0.0 (9 de outubro de 2019)

As seções a seguir fornecem mais informações sobre a versão 1.0.0 do SDK do Público alvo Node.js:

### Adição de

* Suporte à API do Delivery de Visualização de público alvo v1, incluindo carregamento de página e pré-busca de Visualização.
* Suporte total para fornecer todos os tipos de ofertas criadas no Visual Experience Composer (VEC).
* Suporte para busca prévia e notificações para otimização de desempenho ao armazenar conteúdo pré-buscado em cache.
* Suporte para otimizar o desempenho em [!DNL Target] integrações híbridas via `serverState` quando [!DNL Target] é implantado tanto no lado do servidor quanto no lado do cliente.

   Estamos introduzindo uma configuração chamada `serverState` que contém experiências recuperadas pelo lado do servidor, para que o at.js v2.2+ não faça uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.

* Aberto originado no GitHub como SDK [do](https://github.com/adobe/target-nodejs-sdk)Público alvo Node.js.
* Novo método [da API](https://github.com/adobe/target-nodejs-sdk/blob/master/README.md#targetclientsendnotifications) sendNotifications() para enviar notificações exibidas/clicadas [!DNL Target] para conteúdo pré-buscado via [getOffers()](https://github.com/adobe/target-nodejs-sdk/blob/master/README.md#targetclientsendnotifications).
* Criação simplificada de solicitações de API de Delivery de Visualização, com preenchimento automático de campo interno com padrões (por exemplo, `request.id`, `request.context`etc.).
* Validação dos argumentos do método da API do SDK.
* Atualização do README, amostras e testes de unidade.
* Novo fluxo CI configurado usando ações GitHub.
* CoC adicionado, diretrizes de contribuição, RP e modelos de edição

### Alterado 

* Projeto renomeado para `target-nodejs-sdk`.
* Observação importante, substituindo a API BatchMbox v2 do Público alvo pela API Delivery do Público alvo v1.
* [os argumentos do método](https://github.com/adobe/target-nodejs-sdk/blob/master/README.md#targetclientcreate) da API create() foram modificados, removendo o aninhamento redundante (consulte a declaração do método antigo [aqui](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientcreate)).
* [os argumentos do método](https://github.com/adobe/target-nodejs-sdk/blob/master/README.md#targetclientgetoffers) da API getOffers() foram modificados (consulte a declaração do método antigo [aqui](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffers)).
* O método `getTargetCookieName()` API foi substituído pelo `TargetCookieName` acessador. Consulte Acessadores do utilitário [TargetClient](https://github.com/adobe/target-nodejs-sdk/blob/master/README.md#targetclient-utility-accessors).
* O método `getTargetLocationHintCookieName()` API foi substituído pelo `TargetLocationHintCookieName` acessador.  Consulte Acessadores do utilitário [TargetClient](https://github.com/adobe/target-nodejs-sdk/blob/master/README.md#targetclient-utility-accessors).

### Removido

* Suporte à API Público alvo BatchMbox v2.
* O método [da API](https://www.npmjs.com/package/@adobe/target-node-client#targetnodeclientgetoffer) getOffer() foi removido. Em vez disso, use o método [da API](https://github.com/adobe/target-nodejs-sdk/blob/master/README.md#targetclientgetoffers) getOffers().

