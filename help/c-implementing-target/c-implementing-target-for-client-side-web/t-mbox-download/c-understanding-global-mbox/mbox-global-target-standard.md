---
keywords: global mbox;target classic;use global mbox from target classic
description: Por padrão, o Target Standard cria uma mbox global chamada target-global-mbox, usada para executar atividades criadas no Target Standard. No entanto, se você já criou uma mbox global em suas páginas para suas implementações existentes, você pode usar essa mbox para suas atividades no Target Standard.
title: Usar uma mbox global de uma implementação existente
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '309'
ht-degree: 52%

---


# Usar uma mbox global de uma implementação existente{#use-a-global-mbox-from-a-legacy-implementation}

By default, [!DNL Target] creates a global mbox called target-global-mbox, which is used to run activities created in [!DNL Target]. No entanto, se você já criou uma mbox global em suas páginas para suas implementações existentes, você pode usar essa mbox para suas atividades no [!DNL Target].

>[!NOTE]
>
>Você só pode ter uma mbox por conta.

Para usar sua mbox global existente no [!DNL Target] e em sua implementação existente, você deve definir alguns parâmetros.

1. Go to [!DNL Target], then click **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   By default, **[!UICONTROL Page load enabled (Auto-create global mbox]** is enabled, and the custom global mbox is named `target-global-mbox`.

1. If you want to use an existing mbox, disable **[!UICONTROL Page load enabled (Auto-create global mbox]**, and specify the name of a previously created global mbox in the **[!UICONTROL Global Mbox]** field.

   The [!UICONTROL Global Mbox] drop-down lists all mboxes in your account. Se você quiser usar uma mbox que ainda não existe, crie a mbox.

1. Clique em **[!UICONTROL Salvar]**.

   As configurações da mbox.js para sua conta são atualizadas.

1. Baixe o novo arquivo at.js e consulte-o no seu site.

   Todas as atividades existentes foram atualizadas para usar a mbox global especificada, inclusive as atividades que foram anteriormente criadas e implementadas.

## Solução de problemas da implementação global da mbox

As perguntas frequentes a seguir podem ser usadas para solucionar problemas na implementação da mbox global:

### Por que a mbox global não está carregando ou por que há uma latência no carregamento da mbox global quando a página carrega?

Verifique se a referência do at.js é a primeira chamada do JavaScript na página. Para obter outras soluções para esse problema, consulte Perguntas [frequentes sobre a mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md)global.
