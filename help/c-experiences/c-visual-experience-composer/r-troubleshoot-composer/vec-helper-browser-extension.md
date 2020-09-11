---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Informações para usar a extensão do navegador do Adobe Target Visual Experience Composer (VEC) Helper para carregar sites de maneira confiável no VEC a fim de criar e testar rapidamente experiências de QA.
title: Extensão de ajuda do Adobe Target Visual Experience Composer (VEC)
feature: vec
topic: Standard
translation-type: tm+mt
source-git-commit: 73af03c895ce98e5b6762950e8cd638d7bef0990
workflow-type: tm+mt
source-wordcount: '880'
ht-degree: 59%

---


# Extensão de ajuda do Visual Experience Composer

The [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) Helper browser extension for Google Chrome lets you load websites reliably within the VEC to rapidly author and QA web experiences.

>[!NOTE]
>
>O navegador VEC Helper é uma extensão do Chrome. Essa extensão não é necessária ao usar o Mozilla Firefox.

## Motivos pelos quais alguns sites podem não abrir de forma confiável no VEC

* O site tem políticas de segurança estritas.
* O site está em um iframe.
* A biblioteca do at.js ainda não está implementada no site.
* O site de QA e/ou etapas do cliente não está disponível para o mundo externo (o site é interno).
* Você está usando o Google Chrome 80+ com políticas aprimoradas de aplicação de cookies do SameSite. Para obter mais informações, consulte [Como as políticas de aplicação de cookies do Google Chrome SameSite, anunciadas recentemente, afetam a VEC e a EEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite)?

A extensão de navegador VEC Helper para o Chrome resolve problemas de carregamento de site para os quais os clientes agora dependem do [!DNL Target] [Enhanced Experience Composer](/help/administrating-target/visual-experience-composer-set-up.md#eec) ou extensões de terceiros, como Requestly.

## Benefícios do uso da extensão do VEC Helper

* Todos os cabeçalhos de interrupção de iframe, como X-Frame-Opções e Conteúdo-Segurança-Política, são removidos implicitamente do site. Não é mais necessário criar regras Solicitáveis complexas para fazer isso.
* Se uma página da Web ainda não contiver a biblioteca JavaScript do at.js [!DNL Target], você poderá usar a extensão e inserir a biblioteca para poder criar experiências no site. Em seguida, você pode criar atividades, além de QA, usando links de visualização.

   Observe que ao usar o Enhanced Experience Composer (EEC), a extensão não injeta o at.js, mas a funcionalidade do mesmo cookie de site ainda está presente. Para injetar o at.js na página Web, desligue a CEE.

* [Os visores](/help/c-experiences/c-visual-experience-composer/mobile-viewports.md) móveis são suportados mesmo sem o [!UICONTROL Enhanced Experience Composer] (EEC).
* Os clientes novos do [!DNL Target] podem usar a extensão para experimentar com [!DNL Target] mesmo se os desenvolvedores de TI ainda não tiverem implementado o [!DNL Target] em seus sites.
* Os parceiros que servem vários sites e contas do [!DNL Target] de vários clientes agora têm um mecanismo simples para suportar o carregamento do VEC, em vez de gerenciar várias regras em ferramentas de terceiros.

## Obter e instalar a extensão do navegador VEC Helper

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Clique em **[!UICONTROL Adicionar ao Chrome > Adicionar extensão]**.
1. Abra o VEC em [!DNL Target].
1. Para usar a extensão, clique no ícone de extensão do navegador do VEC Helper (![ícone do VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) na barra de ferramentas do navegador Chrome no VEC ou no [Modo de QA](/help/c-activities/c-activity-qa/activity-qa.md).
1. (Condicional) Deslize as bibliotecas **[!UICONTROL de Públicos alvos]** injetáveis para alternar para a posição &quot;ligado&quot; se a página da Web ainda não contiver a biblioteca JavaScript do [!DNL Target] at.js.

   A ilustração a seguir mostra o VEC Helper com a configuração [!UICONTROL Inserir bibliotecas do Target] ativada:

   ![VEC Helper 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

   A ilustração a seguir mostra o VEC Helper perguntando se você deseja inserir bibliotecas do [!DNL Target] na página para ativar a criação:

   ![VEC Helper 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

1. (Condicional) Deslize a alternância de **[!UICONTROL Cookies]** para a posição &quot;ligado&quot; para adicionar automaticamente a correção do navegador do atributo SameSite=None e especifique o nome e o domínio do cookie.

   ![Os cookies alternam na extensão auxiliar VEC](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/cookies-vec-helper.png)

   Os links a seguir fornecem informações adicionais:

   * Para obter mais informações sobre a correção do navegador de atributos SameSite=None, consulte &quot;Como as políticas de aplicação de cookies do Google Chrome SameSite recentemente anunciadas afetam o VEC e EEC?&quot; in [Troubleshooting Issues Related to the Visual Experience Composer and Enhanced Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/issues-related-to-the-visual-experience-composer-vec-and-enhanced-experience-composer-eec.md#samesite).

   * O nome do cookie é &quot;mbox&quot; e o domínio do cookie é o segundo e o mais alto nível dos domínios dos quais você serve a mbox. O cookie é sempre um cookie próprio porque é disponibilizado pelo domínio de sua companhia. Exemplo: `mycompany.com`. Para obter mais informações, consulte Cookies [da](https://docs.adobe.com/content/help/en/core-services/interface/ec-cookies/cookies-target.html) Adobe Target no Guia *do usuário da interface do* Experience Cloud.

## Notas

* Sua implementação deve usar a biblioteca at.js do [!DNL Target]. Não é possível usar uma implementação mbox.js com a extensão.
* O sinalizador [!UICONTROL Inserir bibliotecas do Target] na extensão está desativado por padrão. Você pode ativar esse sinalizador se desejar usar o VEC em um site que ainda não foi implementado para [!DNL Target].

   Esteja ciente de que esse sinalizador é uma configuração global. O sinalizador é ativado ou desativado para todos os sites abertos no VEC. Portanto, por exemplo, se você definir esse sinalizador como &quot;ativado&quot; e abrir um site que já esteja implementado com o at.js, você receberá uma mensagem informando que o at.js já está carregado. Nós prevemos que a maioria dos clientes já terá o at.js implementado em suas páginas e usará a configuração padrão de &quot;off&quot;.

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* Ao usar a extensão para inserir o at.js enquanto estiver no [Modo de QA](/help/c-activities/c-activity-qa/activity-qa.md), é necessário abrir outra guia do Chrome. Essa guia do Chrome deve ser autenticada na mesma organização de [!DNL Adobe Experience Cloud] na qual você criou a atividade.
* As mensagens a seguir ajudam a manter você informado:

   * Caso tente carregar um site usando o VEC que não é carregado, uma mensagem será exibida sugerindo que você instale a extensão de navegador VEC Helper.
   * Se o at.js ainda não estiver implementado no site, uma mensagem será exibida no VEC sugerindo que você instale a extensão.
   * Se a extensão estiver ativada e promovendo o carregamento, as mensagens serão exibidas quando a extensão injetar a biblioteca do at.js (se necessário) ou ajudar a abrir o site de forma confiável no VEC.

