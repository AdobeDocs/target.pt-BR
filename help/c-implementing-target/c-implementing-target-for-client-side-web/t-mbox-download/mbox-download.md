---
keywords: implementação; mbox; baixar mbox.js; api de download; api mbox.js
description: Saiba mais sobre a implementação herdada da mbox.js do Adobe Target. Migrar para o SDK da Web da Adobe Experience Platform (AEP Web SDK) ou para a versão mais recente da at.js.
title: Como implementar [!DNL Target] com a mbox.js?
feature: 'at.js '
role: Developer
exl-id: 105095d7-8e29-413b-a7f4-e46e2e30e91f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 47%

---

# Implementação da mbox.js

Para usar [!DNL Adobe Target Standard] ou [!DNL Target Premium], adicione uma linha de código para chamar a mbox.js.

Você pode usar qualquer uma das duas referências da biblioteca: o [!DNL Adobe Experience Platform Web SDK] ou [!DNL at.js]. [Vantagens da at.](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) js explica as diferenças entre as bibliotecas da mbox.js e da at.js.

>[!IMPORTANT]
>
>**Fim da vida útil** da mbox.js: A partir de 31 de março de 2021, o  [!DNL Adobe Target] não será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas da mbox.js normalmente falharão e afetarão suas páginas que têm [!DNL Target] atividades em execução ao veicular conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca at.js de JavaScript antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implementar o Target para web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

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
