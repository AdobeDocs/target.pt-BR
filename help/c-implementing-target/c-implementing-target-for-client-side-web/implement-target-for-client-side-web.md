---
keywords: implementar; implementação; at.js; adobe experience platform web sdk; aep web sdk
description: Saiba como implementar a biblioteca JavaScript do Adobe [!DNL Target] for client-side web using the Adobe Experience Platform Web SDK  (AEP Web SDK) or the [!DNL Target] at.js.
title: Como implementar [!DNL Target] para Web no lado do cliente
feature: 'at.js '
role: Developer
exl-id: 34c1e39b-acae-4547-b67f-584bcd59913f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 17%

---

# Visão geral: implementar [!DNL Target] para Web no lado do cliente

Em uma implementação no lado do cliente do [!DNL Adobe Target], o [!DNL Target] fornece as experiências associadas a uma atividade diretamente para o navegador do cliente. O navegador decide qual experiência será exibida e realiza a ação. Com uma implementação no lado do cliente, você pode usar um editor WYSIWYG, o [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou uma interface não visual, o [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md), para criar experiências de atividade e personalização.

Para implementar [!DNL Adobe Target] no lado do cliente, você deve usar uma das seguintes bibliotecas JavaScript:

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Biblioteca de JavaScript at.js do Target](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: A partir de 31 de março de 2021, o  [!DNL Adobe Target] não será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites.
>
>* **Adobe Experience Platform Web SDK**: O  [!UICONTROL Adobe Experience Platform Web ] SDK permite interagir com os vários serviços na  [!DNL Experience Cloud] (incluindo  [!DNL Target]) por meio da Adobe Experience Edge Network. Se você optar por migrar para o [!DNL Adobe Experience Platform Web SDK], consulte [O que é Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) no *Guia do SDK da Web*.
   >
   >
* **at.js**: A biblioteca at.js de JavaScript oferece muitas vantagens em relação à mbox.js. Entre outros benefícios, a at.js melhora os tempos de carregamento de página para implementações da Web, melhora a segurança e fornece opções de implementações melhores para aplicativos de página única. Se você optar por migrar para at.js, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e [Adobe Target Skill Builder: Bate-papo do desenvolvedor, migre a mbox.js do Adobe Target para at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Embora a mbox.js seja compatível no momento (até 31 de março de 2021), não fornecemos atualizações de recursos para essa biblioteca desde julho de 2017. Ao mover todos os clientes para o [!UICONTROL Adobe Experience Platform Web SDK] ou at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferecer o suporte que você espera do Adobe.
