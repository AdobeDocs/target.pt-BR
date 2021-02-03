---
keywords: implementação;mbox;download mbox.js;download api;mbox.js api
description: Para usar o Adobe Target Standard ou o Público alvo Premium, adicione uma linha de código para chamar mbox.js.
title: Implementação da mbox.js
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 50%

---


# Implementação da mbox.js

Para usar [!DNL Adobe Target Standard] ou [!DNL Target Premium], adicione uma linha de código para chamar mbox.js.

Você pode usar qualquer uma das duas referências de biblioteca: o [!DNL Adobe Experience Platform Web SDK] ou [!DNL at.js]. [Os benefícios do at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) jsexplica as diferenças entre as bibliotecas mbox.js e at.js.

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implemente o Público alvo para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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