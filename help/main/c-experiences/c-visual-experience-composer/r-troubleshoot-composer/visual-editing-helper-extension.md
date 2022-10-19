---
keywords: vec;visual experience composer; vec;iframe;extensão;navegador
description: Descubra por que alguns sites podem não abrir de forma confiável no [!UICONTROL Visual Experience Composer] (VEC). A extensão de navegador [!UICONTROL Auxiliar de edição visual] permite carregar sites de maneira confiável no VEC.
title: Como usar a extensão [!UICONTROL Auxiliar de edição visual]?
feature: Visual Experience Composer (VEC)
source-git-commit: 6fd90da68bfe9a78202e9289dc639d41e3daa48f
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 100%

---

# Extensão [!UICONTROL Auxiliar de edição visual]

A extensão de navegador da [!DNL Adobe Experience Cloud] para Google Chrome, [!UICONTROL Auxiliar de edição visual], permite carregar sites de maneira confiável no [!UICONTROL Visual Experience Composer] (VEC) do [!UICONTROL Adobe Target] para criar e controlar a qualidade das experiências da web com mais rapidez.

>[!IMPORTANT]
>
>Esta nova extensão substitui a [extensão de navegador Auxiliar do VEC do Target](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

## Motivos pelos quais alguns sites podem não abrir de forma confiável no VEC

* O site tem políticas de segurança estritas.
* O site está em um iframe.
* O site de controle de qualidade e/ou preparo do cliente não está disponível para partes externas (o site é interno).

A extensão de navegador da [!DNL Adobe Experience Cloud] para Google Chrome, [!UICONTROL Auxiliar de edição visual], resolve problemas de carregamento de site para os quais os clientes dependiam do [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) do [!DNL Target] ou de extensões de terceiros, como o Requestly.

## Benefícios do uso da extensão [!UICONTROL Auxiliar de edição visual]

* Todos os cabeçalhos de interrupção de iframe, como `X-Frame-Options` e `Content-Security-Policy`, são removidos implicitamente do site. Não há necessidade de criar regras complicadas do Requestly.
* Se uma página da Web ainda não contiver a biblioteca de at.js do [!DNL Target], você poderá usar a extensão e inserir a biblioteca para poder criar experiências no site. Em seguida, você pode criar atividades, além de controle de qualidade, usando links de visualização.

Ao usar o [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), a extensão não insere a at.js, mas a funcionalidade de cookie SameSite ainda está presente. Para inserir a at.js na página da Web, desative o EEC.

* [Visores móveis](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) são permitidos mesmo sem o [!UICONTROL Enhanced Experience Composer] (EEC).
* Os clientes novos do [!DNL Target] podem usar a extensão para experimentar com [!DNL Target] mesmo se os desenvolvedores de TI ainda não tiverem implementado o [!DNL Target] em seus sites.
* Os parceiros que servem vários sites e contas do [!DNL Target] de vários clientes agora têm um mecanismo simples para suportar o carregamento do VEC, em vez de gerenciar várias regras em ferramentas de terceiros.

## Obter e instalar a extensão de navegador [!UICONTROL Auxiliar de edição visual]

1. Navegue até a [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensão de navegador na Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Clique em **[!UICONTROL Adicionar ao Chrome]** > **[!UICONTROL Adicionar extensão]**.
1. Abra o VEC no [!DNL Target].
1. Para usar a extensão, clique no ícone da extensão de navegador [!UICONTROL Auxiliar de edição visual] (![ícone da extensão de edição visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png)) na barra de ferramentas do Chrome no VEC ou no modo de controle de qualidade.

   O [!UICONTROL Auxiliar de edição visual] é ativado automaticamente quando um site é aberto no VEC do [!UICONTROL Target] para permitir a criação. A extensão não tem configurações condicionais. A extensão lida com todas as configurações automaticamente, incluindo as configurações de cookies SameSite.

   Para obter mais informações sobre a correção de navegador do atributo `SameSite=None`, consulte “Como as políticas de aplicação de cookies SameSite do Google Chrome recentemente anunciadas afetam o VEC e o EEC?” em [Solução de problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Notas

* Para o [!DNL Target], a extensão carrega a versão mais recente da at.js disponível na interface do [!DNL Target] em [!UICONTROL Administração] > [!UICONTROL Implementação] e a at.js baixa as bibliotecas de criação.
* Ao usar a extensão para inserir a at.js enquanto estiver no [Modo de QA](/help/main/c-activities/c-activity-qa/activity-qa.md), é necessário abrir outra guia do Chrome. Essa guia do Chrome deve ser autenticada na mesma organização da [!DNL Adobe Experience Cloud] em que você criou a atividade.
* As mensagens a seguir ajudam a manter você informado:

   * Caso a tentativa de carregar um site usando o VEC falhe, uma mensagem será exibida sugerindo que você instale a extensão de navegador [!UICONTROL Auxiliar de edição visual].
   * Se a at.js ou alloy.js ainda não estiver implementada no site, uma mensagem será exibida no VEC sugerindo que você instale a extensão.
* Se você tentar usar a nova extensão e, em seguida, voltar para a [extensão antiga](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) e o [!DNL Target] falhar ao carregar seu site, apague todos os dados do navegador e desative a nova extensão.




