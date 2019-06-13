---
description: Por padrão, o Target Standard cria uma mbox global chamada target-global-mbox, usada para executar atividades criadas no Target Standard. No entanto, se você já criou uma mbox global em suas páginas para suas implementações existentes, você pode usar essa mbox para suas atividades no Target Standard.
keywords: mbox global; target classic; usar mbox global do target classic
seo-description: Por padrão, o Target Standard cria uma mbox global chamada target-global-mbox, usada para executar atividades criadas no Target Standard. No entanto, se você já criou uma mbox global em suas páginas para suas implementações existentes, você pode usar essa mbox para suas atividades no Target Standard.
seo-title: Usar uma mbox global de uma implementação existente
solution: Target
subtopic: Introdução
title: Usar uma mbox global de uma implementação existente
topic: Padrão
uuid: 31b03dab-99da-4040-bab6-4f5cb452ffdc
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Usar uma mbox global de uma implementação existente{#use-a-global-mbox-from-a-legacy-implementation}

Por padrão, o Target Standard cria uma mbox global chamada target-global-mbox, usada para executar atividades criadas no Target Standard. No entanto, se você já criou uma mbox global em suas páginas para suas implementações existentes, você pode usar essa mbox para suas atividades no Target Standard.

>[!NOTE]
>
>Você só pode ter uma mbox por conta.

Para usar sua mbox global existente no [!DNL Target Standard] e em sua implementação existente, você deve definir alguns parâmetros.

1. Vá até [!DNL Target Standard] e clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Implementação]**.

   Por padrão, a opção [!UICONTROL Criar mbox global automaticamente] está ativada, e a mbox global é chamada de `target-global-mbox`.
1. Caso queira utilizar uma mbox já existente, desative a opção [!UICONTROL Criar mbox global automaticamente] e especifique o nome da mbox global existente no campo [!UICONTROL Mbox global personalizada.]

   As listas suspensas [!UICONTROL Mbox global personalizada] listam todas mboxes na sua conta. Se você deseja usar uma mbox que ainda não existe, crie a mbox no Target Classic.
1. Clique em **[!UICONTROL Salvar]**.

   As configurações da mbox.js para sua conta são atualizadas.
1. Baixe o novo arquivo mbox.js e cite-o em seu site.

   Após ter atualizado seu site de produção com o novo arquivo mbox.js, você está pronto para definir suas preferências.
1. Clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Preferências]**.
1. No campo [!UICONTROL Mbox global personalizada], especifique o nome da mbox global selecionada na página de Implementação.
1. Clique em **[!UICONTROL Enviar]**.

   Todas as atividades existentes foram atualizadas para usar a mbox global especificada, inclusive as atividades que foram anteriormente criadas e implementadas.
   **Resolução de problemas na implementação de mbox global** *Por que a mbox global não está carregando ou por que há uma latência no carregamento da mbox global quando a página carrega?*

Certifique-se de que a referência mbox.js é a primeira chamada JavaScript na página. Para outras soluções para este problema, consulte [Implementação do Mbox.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).
