---
keywords: vec;visual experience composer; vec;iframe;extensão;navegador
description: Descubra por que alguns sites podem não abrir de maneira confiável no Visual Experience Composer (VEC). A extensão de navegador VEC Helper permite carregar sites de maneira confiável no VEC.
title: Como uso a extensão de ajuda do Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 3f38db69-046d-42c9-8c09-eca11d404b12
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '787'
ht-degree: 57%

---

# Extensão de ajuda do Visual Experience Composer

O [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) A extensão do navegador de ajuda para o Google Chrome permite carregar os sites de maneira confiável no VEC a fim de criar e controlar a qualidade das experiências da Web com rapidez.

>[!NOTE]
>
>O navegador VEC Helper é uma extensão do Chrome. Essa extensão não é necessária ao usar o Mozilla Firefox.

## Motivos pelos quais alguns sites podem não abrir de forma confiável no VEC

* O site tem políticas de segurança estritas.
* O site está em um iframe.
* A biblioteca do at.js ainda não está implementada no site.
* O site de QA e/ou etapas do cliente não está disponível para o mundo externo (o site é interno).
* Você está usando o Google Chrome 80+ com políticas aprimoradas de imposição de cookies SameSite. Para obter mais informações, consulte [Como as políticas de imposição de cookies do Google Chrome SameSite recentemente anunciadas afetam o VEC e o EEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

A extensão de navegador VEC Helper para o Chrome resolve problemas de carregamento de site para os quais os clientes agora dependem do [!DNL Target] [Enhanced Experience Composer](/help/main/administrating-target/visual-experience-composer-set-up.md#eec) ou extensões de terceiros, como Requestly.

## Benefícios do uso da extensão do VEC Helper

* Todos os cabeçalhos de interrupção de iframe, como X-Frame-Opções e Conteúdo-Segurança-Política, são removidos implicitamente do site. Não há mais necessidade de criar regras Requestly complicadas.
* Se uma página da Web ainda não contiver a biblioteca JavaScript do at.js [!DNL Target], você poderá usar a extensão e inserir a biblioteca para poder criar experiências no site. Em seguida, você pode criar atividades, além de QA, usando links de visualização.

   Observe que, usando o Enhanced Experience Composer (EEC), a extensão não injeta at.js, mas a funcionalidade de Cookie SameSite ainda está presente. Para inserir at.js na página da Web, desative o EEC.

* [Visores móveis](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md) são compatíveis mesmo sem o [!UICONTROL Enhanced Experience Composer] (CEE)
* Os clientes novos do [!DNL Target] podem usar a extensão para experimentar com [!DNL Target] mesmo se os desenvolvedores de TI ainda não tiverem implementado o [!DNL Target] em seus sites.
* Os parceiros que servem vários sites e contas do [!DNL Target] de vários clientes agora têm um mecanismo simples para suportar o carregamento do VEC, em vez de gerenciar várias regras em ferramentas de terceiros.

## Obter e instalar a extensão do navegador VEC Helper

1. Navegue até o [Extensão de navegador Adobe Target VEC Helper na Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Clique em **[!UICONTROL Adicionar ao Chrome > Adicionar extensão]**.
1. Abra o VEC em [!DNL Target].
1. Para usar a extensão, clique no ícone de extensão do navegador do VEC Helper (![ícone do VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) na barra de ferramentas do navegador Chrome no VEC ou no [Modo de QA](/help/main/c-activities/c-activity-qa/activity-qa.md).
1. (Condicional) Deslize o **[!UICONTROL Inserir bibliotecas do Target]** alterne para a posição &quot;ativada&quot; se a página da Web ainda não contiver a variável [!DNL Target] Biblioteca de JavaScript da at.js.

   A ilustração a seguir mostra o VEC Helper com a configuração [!UICONTROL Inserir bibliotecas do Target] ativada:

   ![VEC Helper 1](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   A ilustração a seguir mostra o VEC Helper perguntando se você deseja inserir bibliotecas do [!DNL Target] na página para ativar a criação:

   ![VEC Helper 2](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Condicional) Deslize o **[!UICONTROL Cookies]** alterne para a posição &quot;ativada&quot; para adicionar automaticamente a variável `SameSite=None` correção do navegador de atributos.

   ![Os cookies são alternados na extensão de assistente do VEC](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Para obter mais informações sobre o `SameSite=None` correção do navegador de atributo, consulte &quot;Como as políticas de imposição de cookies do Google Chrome SameSite recentemente anunciadas afetam o VEC e o EEC?&quot; em [Solução de problemas relacionados ao Visual Experience Composer e ao Enhanced Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

## Notas

* O sinalizador [!UICONTROL Inserir bibliotecas do Target] na extensão está desativado por padrão. Você pode ativar esse sinalizador se desejar usar o VEC em um site que ainda não foi implementado para [!DNL Target].

   Esse sinalizador é uma configuração global. O sinalizador é ativado ou desativado para todos os sites abertos no VEC. Assim, por exemplo, se você definir esse sinalizador como &quot;ativado&quot; e abrir um site que já esteja implementado com a at.js, você receberá uma mensagem informando que a at.js já está carregada. O Adobe antecipa que a maioria dos clientes já tenha o at.js implementado em suas páginas e use a configuração padrão de &quot;desativado&quot;.

* A extensão carrega a versão mais recente do at.js disponível no [!DNL Target UI] em [!UICONTROL Administração > Implementação].
* Ao usar a extensão para inserir o at.js enquanto estiver no [Modo de QA](/help/main/c-activities/c-activity-qa/activity-qa.md), é necessário abrir outra guia do Chrome. Essa guia do Chrome deve ser autenticada na mesma organização de [!DNL Adobe Experience Cloud] na qual você criou a atividade.
* As mensagens a seguir ajudam a manter você informado:

   * Caso tente carregar um site usando o VEC que não é carregado, uma mensagem será exibida sugerindo que você instale a extensão de navegador VEC Helper.
   * Se o at.js ainda não estiver implementado no site, uma mensagem será exibida no VEC sugerindo que você instale a extensão.
   * Se a extensão estiver ativada e promovendo o carregamento, as mensagens serão exibidas quando a extensão injetar a biblioteca do at.js (se necessário) ou ajudar a abrir o site de forma confiável no VEC.