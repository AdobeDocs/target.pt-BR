---
keywords: implementation;mbox;download mbox.js;download api;mbox.js api
description: Para usar o Adobe Target Standard ou o Público alvo Premium, adicione uma linha de código para chamar mbox.js.
title: Implementação da mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 863c5137383d35b2eaa33082c2136b81793281ca
workflow-type: tm+mt
source-wordcount: '433'
ht-degree: 30%

---


# Implementação da mbox.js

Para usar [!DNL Adobe Target Standard] ou [!DNL Target Premium], adicione uma linha de código para chamar mbox.js.

Você pode usar qualquer uma das duas referências de biblioteca: o [!DNL Adobe Experience Platform Web SDK] ou [!DNL at.js]. [Os benefícios do at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsexplica as diferenças entre as bibliotecas mbox.js e at.js.

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão. Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites.
>
>* **Adobe Experience Platform Web SDK**: O  [!UICONTROL Adobe Experience Platform Web ] SDK permite que você interaja com os vários serviços no  [!DNL Experience Cloud] (incluindo  [!DNL Target]) por meio da Adobe Experience Edge Network. Se você optar por migrar para [!DNL Adobe Experience Platform Web SDK], consulte [O que é Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html), no *Guia do SDK da Web*. Consulte [Visão geral do Público alvo](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) para obter [!DNL Target] informações específicas.
   >
   >
* **at.js**: A biblioteca JavaScript do at.js oferece muitas vantagens em relação ao mbox.js. Entre outros benefícios, o at.js melhora o tempo de carregamento da página para implementações da Web, melhora a segurança e oferece melhores opções de implementação para aplicativos de página única. Se você optar por migrar para at.js, consulte [Como o At.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) e [Adobe Target Skill Builder: Bate-papo no desenvolvedor, migre o mbox.js do Adobe Target para o at.js](https://seminars.adobeconnect.com/ptdo6mfo6qn6/?proto=true).
>
>
Embora a mbox.js seja atualmente suportada (até 31 de março de 2021), não fornecemos atualizações de recursos para esta biblioteca desde julho de 2017. Ao mover todos os clientes para o [!UICONTROL Adobe Experience Platform Web SDK] ou o at.js, nossos engenheiros e funcionários de suporte poderão fornecer novas funcionalidades e oferta o suporte que você espera do Adobe.

A única referência para a [!DNL mbox.js] em cada página fornece as bibliotecas necessárias para todas suas atividades. A [!DNL mbox.js] chama o [!DNL Target] de cada página que referencia o arquivo [!DNL mbox.js]. Isso permite que o [!DNL Target] faça o seguinte:

* Entregar atividades do Target
* Rastreie cliques
* Rastreie a maioria das métricas de sucesso

>[!TIP]
>
>Para simplificar a implementação, você pode referenciar a [!DNL mbox.js] no seu cabeçalho global.

Você não precisa manter versões específicas de atividades diferentes do arquivo.

1. Referencie a [!DNL mbox.js] na seção `<head>` de cada página do seu site.

   `<script src="/ *`directory`*/ *`scripts`*/mbox.js"></script>`

   Onde ` *`directory`*/ *`scripts`*` é o diretório onde você salvou o [!DNL mbox.js] arquivo depois de baixá-lo. 
Se você já tiver mboxes na sua página de uma implementação existente, essas mboxes ainda poderão ser usadas na nova interface. O arquivo [!DNL mbox.js] atualizado ainda é necessário, mas essas mboxes podem ser selecionadas para atividades e editadas usando o [!UICONTROL Visual Experience Composer].