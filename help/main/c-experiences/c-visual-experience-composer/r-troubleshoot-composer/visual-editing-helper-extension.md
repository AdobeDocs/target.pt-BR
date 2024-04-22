---
keywords: vec;visual experience composer; vec;iframe;extensão;navegador;perguntas frequentes
description: Descubra por que alguns sites podem não abrir de forma confiável no [!UICONTROL Visual Experience Composer] (VEC). A variável [!UICONTROL Visual Editing Helper] A extensão do navegador permite carregar sites de maneira confiável no VEC.
title: Como usar o [!UICONTROL Visual Editing Helper] Extensão?
feature: Visual Experience Composer (VEC)
exl-id: e5aeb8b9-fab5-4ad4-882e-2106d2c9daab
source-git-commit: 8edae6a197a3ac82b85fcce4d99c8b0d5f45c712
workflow-type: tm+mt
source-wordcount: '672'
ht-degree: 64%

---

# [!UICONTROL Visual Editing Helper] extensão

A variável [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensão do navegador para [!DNL Google Chrome] permite carregar sites de maneira confiável na [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) para criar e controlar a qualidade das experiências da Web com rapidez.

>[!IMPORTANT]
>
>Esta nova extensão substitui a [extensão de navegador Auxiliar do VEC do Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md). Consulte a Nota importante na parte superior desse artigo. Devido aos aprimoramentos de segurança no Manifest v3, [!DNL Adobe] requer o download desta nova extensão para continuar a criar visualmente seus sites no [!DNL Target].

## Motivos pelos quais alguns sites podem não abrir de forma confiável no VEC

* O site tem políticas de segurança estritas.
* O site está em um iframe.
* O site de controle de qualidade e/ou preparo do cliente não está disponível para partes externas (o site é interno).

A variável [!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensão de navegador para resolver problemas de carregamento de site para os quais os clientes agora dependem do [!DNL Target] [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou extensões de terceiros, como Requestly.

## Benefícios do uso do [!UICONTROL Visual Editing Helper] extensão

* Todos os cabeçalhos de interrupção de iframe, como `X-Frame-Options` e `Content-Security-Policy`, são removidos implicitamente do site. Não há necessidade de criar regras complicadas do Requestly.
* Se uma página da Web ainda não contiver a biblioteca de at.js do [!DNL Target], você poderá usar a extensão e inserir a biblioteca para poder criar experiências no site. Em seguida, você pode criar atividades, além de controle de qualidade, usando links de visualização.

  Ao usar o [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), a extensão não insere a at.js, mas a funcionalidade de cookie SameSite ainda está presente. Para inserir a at.js na página da Web, desative o EEC.

* [Visores móveis](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) são compatíveis mesmo sem o [!UICONTROL Enhanced Experience Composer] (CEE).
* Os clientes novos do [!DNL Target] podem usar a extensão para experimentar com [!DNL Target] mesmo se os desenvolvedores de TI ainda não tiverem implementado o [!DNL Target] em seus sites.
* Os parceiros que servem vários sites e contas do [!DNL Target] de vários clientes agora têm um mecanismo simples para suportar o carregamento do VEC, em vez de gerenciar várias regras em ferramentas de terceiros.

## Obtenha e instale o [!UICONTROL Visual Editing Helper] extensão do navegador

1. Navegue até a [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensão de navegador na Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Clique em **[!UICONTROL Add to Chrome]** > **[!UICONTROL Add Extension]**.
1. Abra o VEC no [!DNL Target].
1. Para usar a extensão, clique no link [!UICONTROL Visual Editing Helper] ícone de extensão do navegador ( ![Ícone da Extensão de edição visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) na barra de ferramentas do navegador Chrome, no VEC ou no Modo de controle de qualidade.

   A variável [!UICONTROL Visual Editing Helper] é automaticamente ativado quando um site é aberto na [!UICONTROL Target] VEC para habilitar a criação. A extensão não tem configurações condicionais. A extensão lida com todas as configurações automaticamente, incluindo as configurações de cookies SameSite.

   Para obter mais informações sobre a correção de navegador do atributo `SameSite=None`, consulte “Como as políticas de aplicação de cookies SameSite do Google Chrome recentemente anunciadas afetam o VEC e o EEC?” em [Solução de problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Notas

* Para [!DNL Target], a extensão carrega a versão mais recente da at.js disponível no [!DNL Target] Interface do usuário no [!UICONTROL Administration] > [!UICONTROL Implementation] e a at.js baixa as bibliotecas de criação.
* Ao usar a extensão para inserir a at.js enquanto estiver no [Modo de QA](/help/main/c-activities/c-activity-qa/activity-qa.md), é necessário abrir outra guia do Chrome. Essa guia do Chrome deve ser autenticada na mesma organização da [!DNL Adobe Experience Cloud] em que você criou a atividade.
* As mensagens a seguir ajudam a manter você informado:

   * Caso a tentativa de carregar um site usando o VEC falhe, uma mensagem será exibida sugerindo que você instale o [!UICONTROL Visual Editing Helper] extensão do navegador.
   * Se a at.js ou alloy.js ainda não estiver implementada no site, uma mensagem será exibida no VEC sugerindo que você instale a extensão.
* Se você tentar usar a nova extensão e, em seguida, voltar para a [extensão antiga](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) e o [!DNL Target] falhar ao carregar seu site, apague todos os dados do navegador e desative a nova extensão.

## Perguntas frequentes

### A extensão, quando ativa, faz qualquer coisa quando usada fora do [!DNL Adobe Target] ou [!UICONTROL Adobe Journey Optimizer] (AJO)?

A extensão é ativada somente quando o site em questão é carregado dentro de um iframe nos produtos [!DNL Adobe] ([!DNL Target], [!DNL AJO]). Fora desse fluxo, a extensão não tenta adicionar, remover ou modificar nenhum cabeçalho nem inserir um código dentro do site.

### O que a extensão faz quando está ativa no VEC do [!DNL Adobe Target]?

Quando um site é carregado dentro de um iframe nos produtos [!DNL Adobe] ([!DNL Target], [!DNL AJO]), a extensão insere o código (fornecido junto com a extensão) no site e baixa os arquivos de ajuda da [!DNL Adobe] CDN para permitir a criação visual.
