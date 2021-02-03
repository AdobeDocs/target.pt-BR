---
keywords: implementar;implementação;at.js;adobe experience platform web sdk;aep web sdk
description: Informações sobre a implementação do Adobe Target para Web do cliente usando o at.js.
title: Implementação da Adobe Target para a Web do cliente
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 18%

---


# Visão geral: implementar o Target para Web no lado do cliente

Em uma implementação no lado do cliente do [!DNL Adobe Target], o [!DNL Target] fornece as experiências associadas a uma atividade diretamente para o navegador do cliente. O navegador decide qual experiência será exibida e realiza a ação. Com uma implementação no lado do cliente, você pode usar um editor WYSIWYG, o [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou uma interface não visual, o [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md), para criar experiências de atividade e personalização.

Para implementar [!DNL Adobe Target] no cliente, você deve usar uma das seguintes bibliotecas JavaScript:

* [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md)
* [Público alvo da biblioteca JavaScript do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md)

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites.
>
>* **Adobe Experience Platform Web SDK**: O  [!UICONTROL Adobe Experience Platform Web ] SDK permite que você interaja com os vários serviços no  [!DNL Experience Cloud] (incluindo  [!DNL Target]) por meio da Adobe Experience Edge Network. Se você optar por migrar para [!DNL Adobe Experience Platform Web SDK], consulte [O que é Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) no *Guia do SDK da Web*.
   >
   >
* **at.js**: A biblioteca JavaScript do at.js oferece muitas vantagens em relação ao mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única. Se você optar por migrar para at.js, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e [Adobe Target Skill Builder: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Embora a mbox.js seja atualmente suportada (até 31 de março de 2021), não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. Ao mover todos os clientes para o [!UICONTROL Adobe Experience Platform Web SDK] ou o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta o suporte que você espera do Adobe.
