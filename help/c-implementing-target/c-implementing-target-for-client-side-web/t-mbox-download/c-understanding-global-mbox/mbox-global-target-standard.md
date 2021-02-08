---
keywords: mbox global; target classic; usar mbox global do target classic
description: Saiba como usar uma mbox global legada para suas atividades Adobe Target se você já tiver criado uma mbox global em suas páginas para suas implementações herdadas.
title: Posso usar uma mbox global de uma implementação legada?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 36%

---


# Usar uma mbox global de uma implementação legada

Por padrão, [!DNL Target] cria uma mbox global chamada público alvo-global-mbox, que é usada para executar atividades criadas em [!DNL Target]. No entanto, se você já criou uma mbox global em suas páginas para suas implementações existentes, você pode usar essa mbox para suas atividades no [!DNL Target].

>[!NOTE]
>
>Você só pode ter uma mbox por conta.

Para usar sua mbox global existente no [!DNL Target] e em sua implementação existente, você deve definir alguns parâmetros.

1. Vá para [!DNL Target] e clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.

   Por padrão, **[!UICONTROL Carregamento de página ativado (Criar automaticamente mbox global]** é ativado e a mbox global personalizada é chamada `target-global-mbox`.

1. Se você quiser usar uma mbox existente, desative **[!UICONTROL Carregamento de página ativado (Criar mbox global automaticamente]**) e especifique o nome de uma mbox global criada anteriormente no campo **[!UICONTROL Mbox global]**.

   O menu suspenso [!UICONTROL Global Mbox] lista todas as mboxes na sua conta. Se você quiser usar uma mbox que ainda não existe, crie a mbox.

1. Clique em **[!UICONTROL Salvar]**.

   As configurações da mbox.js para sua conta são atualizadas.

1. Baixe o novo arquivo at.js e consulte-o no seu site.

   Todas as atividades existentes foram atualizadas para usar a mbox global especificada, inclusive as atividades que foram anteriormente criadas e implementadas.

## Solução de problemas da implementação global da mbox

As perguntas frequentes a seguir podem ser usadas para solucionar problemas na implementação da mbox global:

### Por que a mbox global não está carregando ou por que há uma latência no carregamento da mbox global quando a página carrega?

Verifique se a referência do at.js é a primeira chamada do JavaScript na página. Para obter outras soluções para esse problema, consulte [Perguntas frequentes sobre a mbox global](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
