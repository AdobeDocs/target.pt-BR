---
keywords: implementação; mbox.js; biblioteca de manipulação de dom; target. js; visual experience composer; iframe; sites angulares; aplicativos de página única; aplicativo de página única; SPA
description: Saiba mais sobre a implementação herdada da mbox.js do Adobe Target. Migrar para o SDK da Web da Adobe Experience Platform (AEP Web SDK) ou para a versão mais recente da at.js.
title: O que a biblioteca mbox.js do Target faz?
feature: 'at.js '
role: Desenvolvedor
exl-id: 62f0cbd2-17f0-43f4-98d3-ea39f314525e
translation-type: tm+mt
source-git-commit: 0a685427a047bfc0a2f5e81525b32df70af6d69f
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 74%

---

# O que a mbox.js faz{#what-mbox-js-does}

As informações são fornecidas para ajudar sua equipe técnica a compreender a implementação da mbox.js e como ela pode afetar seu site.

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: A partir de 31 de março de 2021, o  [!DNL Adobe Target] não será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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
