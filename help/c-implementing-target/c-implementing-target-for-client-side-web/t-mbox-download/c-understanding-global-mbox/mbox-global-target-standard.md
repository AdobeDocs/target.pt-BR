---
keywords: mbox global; target classic; usar mbox global do target classic
description: Saiba como usar uma mbox global herdada para suas atividades do Adobe [!DNL Target] se já tiver criado uma mbox global em suas páginas para suas implementações herdadas.
title: Posso usar uma mbox global de uma implementação existente?
feature: 'at.js '
role: Developer
exl-id: 1eb6836b-6b3c-4494-af67-cd72a4f357e2
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 36%

---

# Usar uma mbox global de uma implementação existente

Por padrão, [!DNL Target] cria uma mbox global chamada target-global-mbox, que é usada para executar atividades criadas em [!DNL Target]. No entanto, se você já criou uma mbox global em suas páginas para suas implementações existentes, você pode usar essa mbox para suas atividades no [!DNL Target].

>[!NOTE]
>
>Você só pode ter uma mbox por conta.

Para usar sua mbox global existente no [!DNL Target] e em sua implementação existente, você deve definir alguns parâmetros.

1. Vá para [!DNL Target] e clique em **[!UICONTROL Administration]** > **[!UICONTROL Implementation]**.

   Por padrão, **[!UICONTROL Page load enabled (Autocreate global mbox]** é ativado e a mbox global personalizada é chamada `target-global-mbox`.

1. Se você deseja usar uma mbox existente, desative **[!UICONTROL Page load enabled (Auto create global mbox]**) e especifique o nome de uma mbox global criada anteriormente no campo **[!UICONTROL Global Mbox]**.

   A lista suspensa [!UICONTROL Mbox global] lista todas as mboxes na sua conta. Se você quiser usar uma mbox que ainda não existe, crie a mbox.

1. Clique em **[!UICONTROL Salvar]**.

   As configurações da mbox.js para sua conta são atualizadas.

1. Baixe o novo arquivo at.js e cite-o em seu site.

   Todas as atividades existentes foram atualizadas para usar a mbox global especificada, inclusive as atividades que foram anteriormente criadas e implementadas.

## Resolução de problemas na implementação da mbox global

As seguintes perguntas frequentes podem ser usadas para solucionar problemas de sua implementação da mbox global:

### Por que a mbox global não está carregando ou por que há uma latência no carregamento da mbox global quando a página carrega?

Certifique-se de que a referência da at.js seja a primeira chamada do JavaScript na página. Para outras soluções para este problema, consulte [Perguntas frequentes sobre a mbox global](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/global-mbox-frequently-asked-questions.md).
