---
description: Para usar o Target Standard ou Target Premium, adicione uma linha de código para chamar a mbox.js
keywords: Implementação; Mbox; baixar mbox.js; api de download; api mbox.js
seo-description: Para usar o Target Standard ou Target Premium, adicione uma linha de código para chamar a mbox.js
seo-title: Implementação da mbox.js
solution: Target
subtopic: Introdução
title: Implementação da mbox.js
topic: Padrão
uuid: aa53dfd4-db42-4a33-b561-7e84ca7e4497
translation-type: tm+mt
source-git-commit: ac86b0131b0c65f3367c47b3a1315c37d9b9aa93

---


# Implementação da mbox.js{#mbox-js-implementation}

Para usar o Target Standard ou Target Premium, adicione uma linha de código para chamar a mbox.js

Você pode usar qualquer uma das duas referências da biblioteca: [!DNL mbox.js] ou [!DNL at.js]. [Os benefícios do at. js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#benefits) explicam as diferenças entre as duas bibliotecas.

>[!NOTE]
>
>A biblioteca mbox.js ainda é suportada, mas não receberá atualizações. Todos os clientes devem migrar para a at.js. Para obter mais informações, consulte [Migrar para at.js do mbox.js](../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

A única referência para a [!DNL mbox.js] em cada página fornece as bibliotecas necessárias para todas suas atividades. A [!DNL mbox.js] chama o [!DNL Target] de cada página que referencia o arquivo [!DNL mbox.js]. Isso permite que o [!DNL Target] faça o seguinte:

* Entreguar atividades do Target
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