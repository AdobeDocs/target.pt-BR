---
description: Informações sobre a implementação do Adobe Target para Web no lado do cliente.
title: Implementar o Adobe Target para Web no lado do cliente
topic: Padrão
uuid: 8ed04881-3dd9-496f-9c9c-feb9c740ed80
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# Visão geral: implementar o Target para Web no lado do cliente

Em uma implementação no lado do cliente do [!DNL Adobe Target], o [!DNL Target] fornece as experiências associadas a uma atividade diretamente para o navegador do cliente. O navegador decide qual experiência será exibida e realiza a ação. Com uma implementação no lado do cliente, você pode usar um editor WYSIWYG, o [Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md) (VEC) ou uma interface não visual, o [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md), para criar experiências de atividade e personalização.

Para implementar no lado do cliente do [!DNL Adobe Target], você deve usar a biblioteca [at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md) ou mbox.js.

>[!NOTE]
>
>A biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem [implantar a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) ou [migrar da mbox.js para a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).
