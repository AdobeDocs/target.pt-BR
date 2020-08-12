---
keywords: vec;visual experience composer; vec;iframe;extension;browser
description: Informações para usar a extensão do navegador do Adobe Target Visual Experience Composer (VEC) Helper para carregar sites de maneira confiável no VEC a fim de criar e testar rapidamente experiências de QA.
title: Extensão de ajuda do Adobe Target Visual Experience Composer (VEC)
feature: null
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 94%

---


# Extensão de ajuda do Visual Experience Composer

A extensão do navegador [!DNL Adobe Target] do Visual Experience Composer (VEC) Helper para Google Chrome permite carregar sites de maneira confiável no VEC a fim de criar rapidamente e testar experiências da Web.

Motivos pelos quais alguns sites podem não abrir de forma confiável no VEC:

* O site tem políticas de segurança estritas.
* O site está em um iframe.
* A biblioteca do at.js ainda não está implementada no site.
* O site de QA e/ou etapas do cliente não está disponível para o mundo externo (o site é interno).

A extensão de navegador VEC Helper para o Chrome resolve problemas de carregamento de site para os quais os clientes agora dependem do [!DNL Target] [!UICONTROL Enhanced Experience Composer] ou extensões de terceiros, como Requestly

Benefícios do uso da extensão do VEC Helper:

* Todos os cabeçalhos de interrupção de iframe, como X-Frame-Opções e Conteúdo-Segurança-Política, são removidos implicitamente do site. Não é mais necessário criar regras Solicitáveis complexas para fazer isso.
* Se uma página da Web ainda não contiver a biblioteca JavaScript do at.js [!DNL Target], você poderá usar a extensão e inserir a biblioteca para poder criar experiências no site. Em seguida, você pode criar atividades, além de QA, usando links de visualização.
* Os Visores móveis são suportados mesmo sem o [!UICONTROL Enhanced Experience Composer] (EEC).
* Os clientes novos do [!DNL Target] podem usar a extensão para experimentar com [!DNL Target] mesmo se os desenvolvedores de TI ainda não tiverem implementado o [!DNL Target] em seus sites.
* Os parceiros que servem vários sites e contas do [!DNL Target] de vários clientes agora têm um mecanismo simples para suportar o carregamento do VEC, em vez de gerenciar várias regras em ferramentas de terceiros.

## Obter e instalar a extensão do navegador VEC Helper

1. Navigate to the [Adobe Target VEC Helper browser extension in the Chrome Web Store](https://chrome.google.com/webstore/detail/adobe-target-vec-helper/ggjpideecfnbipkacplkhhaflkdjagak).
1. Clique em [!UICONTROL Adicionar ao Chrome > Adicionar extensão].
1. Para usar a extensão, clique no ícone de extensão do navegador do VEC Helper (![ícone do VEC Helper](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension.png)) na barra de ferramentas do navegador Chrome no VEC ou no [Modo de QA](/help/c-activities/c-activity-qa/activity-qa.md).

A ilustração a seguir mostra o VEC Helper com a configuração [!UICONTROL Inserir bibliotecas do Target] ativada:

![VEC Helper 1](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-help-extension-1.png)

A ilustração a seguir mostra o VEC Helper perguntando se você deseja inserir bibliotecas do [!DNL Target] na página para ativar a criação:

![VEC Helper 2](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/vec-helper.png)

## Notas

* Sua implementação deve usar a biblioteca at.js do [!DNL Target]. Não é possível usar uma implementação mbox.js com a extensão.
* O sinalizador [!UICONTROL Inserir bibliotecas do Target] na extensão está desativado por padrão. Você pode ativar esse sinalizador se desejar usar o VEC em um site que ainda não foi implementado para [!DNL Target].

   Esteja ciente de que esse sinalizador é uma configuração global. O sinalizador é ativado ou desativado para todos os sites abertos no VEC. Assim, por exemplo, se você definir esse sinalizador como Ativado e abrir um site que já esteja implementado com o at.js, você receberá uma mensagem informando que o at.js já está carregado. É possível que a maioria dos clientes já tenha o at.js implementado em suas páginas e usará a configuração padrão de desativado.

* The extension loads the latest version of at.js that is available from the [!DNL Target UI] in [!UICONTROL Administration > Implementation].
* Ao usar a extensão para inserir o at.js enquanto estiver no [Modo de QA](/help/c-activities/c-activity-qa/activity-qa.md), é necessário abrir outra guia do Chrome. Essa guia do Chrome deve ser autenticada na mesma organização de [!DNL Adobe Experience Cloud] na qual você criou a atividade.
* As mensagens a seguir ajudam a manter você informado:

   * Caso tente carregar um site usando o VEC que não é carregado, uma mensagem será exibida sugerindo que você instale a extensão de navegador VEC Helper.
   * Se o at.js ainda não estiver implementado no site, uma mensagem será exibida no VEC sugerindo que você instale a extensão.
   * Se a extensão estiver ativada e promovendo o carregamento, as mensagens serão exibidas quando a extensão injetar a biblioteca do at.js (se necessário) ou ajudar a abrir o site de forma confiável no VEC.