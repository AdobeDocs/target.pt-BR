---
keywords: at.js;sdk;release;updates;sdks;server side;serverside;server-side;java;java sdk
description: Notas de versão relacionadas ao Adobe Target Java SDK.
title: Notas de versão relacionadas ao Adobe Target Java SDK.
feature: release notes
topic: Standard
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 2%

---


# Notas de versão - SDK Java do Target

Notas de versão relacionadas ao [Público alvo Java SDK](https://github.com/adobe/target-java-sdk).

O [!DNL Target] Java SDK permite implantar o lado do [!DNL Target] servidor. Esse Java SDK ajuda você a se integrar facilmente [!DNL Target] com outras [!DNL Adobe Experience Cloud] soluções, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]e [!DNL Adobe Audience Manager].

O Java SDK apresenta práticas recomendadas e remove complexidades ao integrar-se [!DNL Target] por meio de nossa API de delivery, para que suas equipes de engenharia possam se concentrar na lógica comercial.

Saiba mais sobre o SDK Java do Público alvo no Adobe Tech Blog - Otimização do lado do [servidor com o novo SDK](https://medium.com/adobetech/server-side-optimization-with-the-new-target-java-sdk-421dc418a3f2)Java do Público alvo.

## Versão 1.1.0 (16 de dezembro de 2019)

A seção a seguir fornece mais informações sobre a versão 1.1.0 do SDK do Java do Público alvo:

### Adição de

* Suporte para configuração de proxy adicionado devido a uma contribuição de código aberto feita por @hisham-hassan.

## Versão 1.0.1 (11 de novembro de 2019)

A seção a seguir fornece mais informações sobre a versão 1.0.1 do SDK do Java do Público alvo:

### Fixo

* Envie uma ID de dados adicional em uma solicitação de Público alvo mesmo quando não houver cookie de API de Visitante presente.

## Versão 1.0.0 (31 de outubro de 2019)

As seções a seguir fornecem mais informações sobre a versão 1.0.0 do SDK Java do Público alvo:

### Adição de

* [Suporte à API](https://developers.adobetarget.com/api/delivery-api/) Delivery de Visualização de público alvo v1, incluindo o Carregamento de página e a pré-busca de Visualização.
   * Suporte total para fornecer todos os tipos de ofertas criadas no Visual Experience Composer (VEC).
* Suporte para busca prévia e notificações que permitem a otimização do desempenho ao armazenar conteúdo pré-buscado em cache.
* Suporte para otimizar o desempenho em integrações híbridas via [!DNL Target] , quando `serverState`[!DNL Target] é implantado tanto no lado do servidor quanto no lado do cliente.
   * Estamos introduzindo uma configuração chamada `serverState` que contém experiências recuperadas pelo lado do servidor, para que o at.js v2.2+ não faça uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.
* Aberto originado no GitHub como [Público alvo do Java SDK](https://github.com/adobe/target-java-sdk).
* Validação dos argumentos do método da API do SDK.
* Adicionados o README, amostras e testes de unidade.
* Adicionado o CoC, as diretrizes de contribuição, a RP e os modelos de edição.

