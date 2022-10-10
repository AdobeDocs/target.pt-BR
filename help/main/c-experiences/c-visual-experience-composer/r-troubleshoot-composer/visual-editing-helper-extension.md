---
keywords: vec;visual experience composer; vec;iframe;extensão;navegador
description: Descubra por que alguns sites podem não abrir de forma confiável no [!UICONTROL Visual Experience Composer] (VEC). O [!UICONTROL Auxiliar de edição visual] a extensão do navegador permite carregar sites de maneira confiável no VEC.
title: Como usar o [!UICONTROL Auxiliar de edição visual] Extensão?
feature: Visual Experience Composer (VEC)
source-git-commit: 6fd90da68bfe9a78202e9289dc639d41e3daa48f
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 26%

---

# [!UICONTROL Auxiliar de edição visual] extensão

O [!DNL Adobe Experience Cloud] [!UICONTROL Auxiliar de edição visual] a extensão do navegador para Google Chrome permite carregar sites de maneira confiável no [!UICONTROL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) para criar e controlar a qualidade das experiências da Web com rapidez.

>[!IMPORTANT]
>
>Esta nova extensão substitui a anterior [Extensão de navegador do Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md).

## Motivos pelos quais alguns sites podem não abrir de forma confiável no VEC

* O site tem políticas de segurança estritas.
* O site está em um iframe.
* O site de controle de qualidade ou estágio do cliente não está disponível para o mundo externo (o site é interno).

O [!DNL Adobe Experience Cloud] [!UICONTROL Auxiliar de edição visual] extensão do navegador para Chrome resolve problemas de carregamento de site para os quais os clientes agora dependem do [!DNL Target] [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou extensões de terceiros, como Requestly.

## Benefícios do uso da variável [!UICONTROL Auxiliar de edição visual] extensão

* Todos os cabeçalhos de edição de iframe, como `X-Frame-Options` e `Content-Security-Policy`, são implicitamente removidas do site. Não há necessidade de criar regras Requestly complicadas.
* Se uma página da Web ainda não contiver a biblioteca do at.js [!DNL Target], você poderá usar a extensão e inserir a biblioteca para poder criar experiências no site. Em seguida, você pode criar atividades, além de QA, usando links de visualização.

Usar o [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec), a extensão não injeta at.js, mas a funcionalidade Cookie SameSite ainda está presente. Para inserir at.js na página da Web, desative o EEC.

* [Visores móveis](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) são compatíveis mesmo sem o [!UICONTROL Enhanced Experience Composer] (CEE)
* Os clientes novos do [!DNL Target] podem usar a extensão para experimentar com [!DNL Target] mesmo se os desenvolvedores de TI ainda não tiverem implementado o [!DNL Target] em seus sites.
* Os parceiros que servem vários sites e contas do [!DNL Target] de vários clientes agora têm um mecanismo simples para suportar o carregamento do VEC, em vez de gerenciar várias regras em ferramentas de terceiros.

## Obtenha e instale o [!UICONTROL Auxiliar de edição visual] extensão do navegador

1. Navegue até o [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper] extensão do navegador na Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-experience-cloud-vi/kgmjjkfjacffaebgpkpcllakjifppnca){target=_blank}.
1. Clique em **[!UICONTROL Adicionar ao Chrome]** > **[!UICONTROL Adicionar extensão]**.
1. Abra o VEC em [!DNL Target].
1. Para usar a extensão, clique no link [!UICONTROL Auxiliar de edição visual] ícone de extensão do navegador ( ![Ícone da extensão de edição visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/visual-editing-helper.png) ) na barra de ferramentas do navegador Chrome, no VEC ou no Modo de QA.

   O [!UICONTROL Auxiliar de edição visual] é ativado automaticamente quando um site é aberto na [!UICONTROL Target] VEC para criação de energia. A extensão não tem configurações condicionais. A extensão lida com todas as configurações automaticamente, incluindo as configurações de cookies do SameSite.

   Para obter mais informações sobre o `SameSite=None` correção do navegador de atributo, consulte &quot;Como as políticas de imposição de cookies do Google Chrome SameSite recentemente anunciadas afetam o VEC e o EEC?&quot; em [Solução de problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md).

## Notas

* Para [!DNL Target], a extensão carrega a versão mais recente do at.js disponível no [!DNL Target] Interface do usuário em [!UICONTROL Administração] > [!UICONTROL Implementação] O e a at.js baixam as bibliotecas de criação.
* Ao usar a extensão para inserir o at.js enquanto estiver no [Modo de QA](/help/main/c-activities/c-activity-qa/activity-qa.md), é necessário abrir outra guia do Chrome. Essa guia do Chrome deve ser autenticada na mesma [!DNL Adobe Experience Cloud] organização na qual você criou a atividade.
* As mensagens a seguir ajudam a manter você informado:

   * Se você tentar carregar um site usando o VEC que não é carregado, uma mensagem será exibida sugerindo que você instale o [!UICONTROL Auxiliar de edição visual] extensão do navegador.
   * Se at.js ou alloy.js ainda não estiver implementado no site, uma mensagem será exibida no VEC sugerindo que você instale a extensão.
* Se você tentar usar a nova extensão e, em seguida, voltar para a [extensão antiga](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) e [!DNL Target] falha ao carregar seu site, apague todos os dados do navegador e desative a nova extensão.




