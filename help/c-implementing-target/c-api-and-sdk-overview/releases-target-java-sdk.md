---
description: Notas de versão relacionadas ao Java SDK do Adobe Target
keywords: at.js;sdk;release;updates;sdks;server-side;server-side;server-side;java;java sdk
seo-description: Notas de versão relacionadas ao Java SDK do Adobe Target.
seo-title: Notas de versão relacionadas ao Java SDK do Adobe Target.
solution: Target
title: Notas de versão - Target Java SDK
topic: Padrão
translation-type: tm+mt
source-git-commit: 540367e4c49c712df98dc132bccf4f29b4d6f095

---


# Notas de versão - Target Java SDK

Notas de versão relacionadas ao [Target Java SDK](https://github.com/adobe/target-java-sdk).

O [!DNL Target] Java SDK permite implantar o lado do [!DNL Target] servidor. Esse Java SDK ajuda você a se integrar facilmente [!DNL Target] com outras [!DNL Adobe Experience Cloud] soluções, como [!DNL Adobe Experience Cloud Identity Service], [!DNL Adobe Analytics]e [!DNL Adobe Audience Manager].

O Java SDK apresenta práticas recomendadas e remove complexidades ao integrar-se [!DNL Target] por meio de nossa API de entrega, para que suas equipes de engenharia possam se concentrar na lógica comercial.

## Versão 1.0.0 (31 de outubro de 2019)

As seções a seguir fornecem mais informações sobre a versão 1.0.0 do Target Java SDK:

### Adição de

* [Suporte à API](https://developers.adobetarget.com/api/delivery-api/) de entrega de exibição do Target v1, incluindo pré-busca de carregamento e exibição de página.
   * Suporte total para fornecer todos os tipos de ofertas criadas no Visual Experience Composer (VEC).
* Suporte para busca prévia e notificações que permitem a otimização do desempenho ao armazenar conteúdo pré-buscado em cache.
* Suporte para otimizar o desempenho em integrações híbridas via [!DNL Target] , quando `serverState`[!DNL Target] é implantado tanto no lado do servidor quanto no lado do cliente.
   * Estamos introduzindo uma configuração chamada `serverState` que contém experiências recuperadas pelo lado do servidor, para que o at.js v2.2+ não faça uma chamada de servidor adicional para recuperar as experiências. Essa abordagem otimiza o desempenho de carregamento da página.
* Aberto originado no GitHub como [Target Java SDK](https://github.com/adobe/target-java-sdk).
* Validação dos argumentos do método da API do SDK.
* Adicionados o README, amostras e testes de unidade.
* Adicionado o CoC, as diretrizes de contribuição, a RP e os modelos de edição.

