---
keywords: implementar; implementação; at.js; adobe experience platform web sdk; aep web sdk
description: Saiba como implementar o Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] Biblioteca de JavaScript da at.js.
title: Como implementar [!DNL Target] para Web do lado do cliente
feature: at.js
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
source-git-commit: bef2b493e8964f468d4f766c932a96d32e994a03
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 47%

---

# Visão geral: implementar [!DNL Target] para Web no lado do cliente

Em uma implementação no lado do cliente do [!DNL Adobe Target], o [!DNL Target] fornece as experiências associadas a uma atividade diretamente para o navegador do cliente. O navegador decide qual experiência será exibida e realiza a ação. Com uma implementação no lado do cliente, você pode usar um editor WYSIWYG, o [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou uma interface não visual, o [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md), para criar experiências de atividade e personalização.

Para implementar [!DNL Adobe Target] no cliente, você deve usar uma das seguintes bibliotecas JavaScript:

* [SDK da Web da Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Biblioteca de JavaScript at.js do Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**Fim da vida útil da**: a partir de 31 de março de 2021, o [!DNL Adobe Target] não oferecerá mais suporte à biblioteca de mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js vão resultar em falha e afetar suas páginas com atividades do [!DNL Target] em execução ao veicular conteúdo padrão. A Adobe recomenda que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites.
>
>* **Adobe Experience Platform Web SDK**: O [!UICONTROL Adobe Experience Platform Web SDK] permite interagir com os vários serviços no [!DNL Experience Cloud] (incluindo [!DNL Target]) pela Adobe Experience Edge Network. Se você optar por migrar para o [!DNL Adobe Experience Platform Web SDK], consulte [O que é o SDK da Web da Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) no *Guia do SDK da Web*.
>
>* **at.js**: A biblioteca JavaScript da at.js melhora os tempos de carregamento de página para implementações da Web, melhora a segurança e fornece opções de implementações melhores para aplicativos de página única. Se você optar por migrar para a at.js, consulte [Como A At.js Funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e [Adobe Target Skill Builder: Bate-papo do desenvolvedor, migre a mbox.js do Adobe Target para at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).


