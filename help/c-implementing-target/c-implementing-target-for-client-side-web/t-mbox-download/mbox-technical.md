---
keywords: implementation;mbox.js;dom manipulation library;target.js;visual experience composer;iframe;angular sites;single page applications;single page app;SPA
description: As informações são fornecidas para ajudar sua equipe técnica a compreender a implementação da mbox.js e como ela pode afetar seu site.
title: O que a mbox.js faz
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '304'
ht-degree: 100%

---


# O que a mbox.js faz{#what-mbox-js-does}

As informações são fornecidas para ajudar sua equipe técnica a compreender a implementação da mbox.js e como ela pode afetar seu site.

O Target Standard requer [!DNL mbox.js] versão 58 ou posterior. Para obter instruções sobre como baixar e atualizar [!DNL mbox.js], consulte [Implementação de mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).

Para o Target Standard, o arquivo [!DNL mbox.js] chama outro arquivo JavaScript, [!DNL target.js]. O arquivo [!DNL Target.js] é hospedado e atualizado automaticamente pela Adobe. Você não precisa fazer nada para atualizar [!DNL target.js] e não há nenhuma personalização específica do cliente.

O arquivo [!DNL Target.js] cria uma mbox chamada `target-global-mbox` na seção `<head>` da página.

O [!DNL Target.js] é chamado de [!DNL mbox.js] por uma linha de código JavaScript adicionada ao campo [!UICONTROL JavaScript Extra] em [!DNL mbox.js]. A única maneira de desativar [!DNL target.js] é não incluir essa linha de código. Isso desativa o [!DNL Target].

[!DNL Target.js] tem duas funções no [!DNL Target]:

* Manipulação de DOM
* Ativa elementos visuais do [!UICONTROL Visual Experience Composer]

## Manipulação de DOM {#section_169F8D4C077948DCB4F891ABBB03FF63}

[!DNL Target.js] controla a biblioteca de manipulação de DOM usada pelo Standard. Para exibir o conteúdo de um site, [!DNL target.js] referencia [!DNL sizzle.js] (version1.10.8-pre). [!DNL Sizzle.js] ativa os seletores de elemento HTML. Sem ser [!DNL sizzle.js], somente o JavaScript nativo é usado. Nenhuma jquery é necessária.

Além disso, o seguinte fragmento é usado para sondar o DOM:
 
`https://github.com/dperini/ContentLoaded`

## Target.js e o Visual Experience Composer {#section_2B3FF6AC5B8D431C83D9EDCF53CB1472}

Quando você usa o [!UICONTROL Visual Experience Composer] para configurar uma experiência para uma atividade, a página da Web é aberta em um iFrame. Quando o iFrame é carregado, o Standard envia uma chamada de API HTML5 `postMessage`. O arquivo [!DNL Target.js] detecta qualquer chamada de `postMessage` e inclui as seguintes bibliotecas JavaScript no site:

* Para geração de miniaturas: [!DNL https://html2canvas.hertzen.com/]
* Para consulta entre domínios: [!DNL Admin.js], [!DNL CDQ.base.js], [!DNL CDQ.host.js], [!DNL admin.css], usados para enviar mensagens no iFrames. Esses scripts permitem que a Adobe envie dados entre as páginas.

## Considerações para aplicativos de sites angulares e de página única   {#section_16D76F16077A434FAE8CEC6FD43BE6D7}

Se você estiver implementando o Target em um site Angular ou em qualquer aplicativo de página única (SPA), deve usar a biblioteca at.js em vez da mbox.js.

Para obter mais informações, consulte [Implementação da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).
