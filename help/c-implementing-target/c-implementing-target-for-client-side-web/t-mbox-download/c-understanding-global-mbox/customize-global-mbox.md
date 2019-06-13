---
description: Informações para ajudar você a personalizar uma mbox global para at.js e mbox.js
keywords: mbox global; personalizar mbox global; editar mbox.js; editar at.js; at.js; implementar mbox.js; implementar o at.js
seo-description: Informações para ajudar você a personalizar uma mbox global para at.js e mbox.js
seo-title: Personalizar uma mbox global
solution: Target
subtopic: Introdução
title: Personalizar uma mbox global
topic: Padrão
uuid: 0f784d6e-8f36-4c26-adbf-0d56b7d6d390
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Personalizar uma mbox global{#customize-a-global-mbox}

Informações para ajudar você a personalizar uma mbox global para at.js e mbox.js

1. Edite a mbox.js

   Vá para **[!UICONTROL Target]** &gt; **[!UICONTROL Configurar]** &gt; **[!UICONTROL Implementação]**.

   * Para mbox.js, clique em **[!UICONTROL Editar configurações mbox.js]**.
   * Para [!DNL at.js]**, selecione[!UICONTROL at.js]** sob Método de implementação, depois clique em **[!UICONTROL Editar configurações mbox.js]**.
   ![](assets/step-1-edit-mboxjs.png)

1. Edite [!DNL mbox.js] ou [!DNL at.js].

   Desabilite **[!UICONTROL Criar mbox global automaticamente]**, depois adicione o nome da mbox global personalizada que gostaria de usar para entregar atividades do [!DNL Target Standard/Premium]. Essa mbox global personalizada também será usada para rastreamento de cliques.

   ![](assets/step-2-edit-mboxjs-or-atjs.png)

   Clique em **[!UICONTROL Salvar]ao terminar.**
1. Implemente a biblioteca [!DNL mbox.js] ou [!DNL at.js] no seu site.

* Para mbox.js, consulte [Implementação da mbox.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md#task_4EAE26BB84FD4E1D858F411AEDF4B420).
* Para at.js, consulte [Implementação da at.js](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17).

1. Organize a transição com seu lançamento.

   Assim que estiver pronto para que o [!DNL Target Standard/Premium] comece a usar sua mbox global para todas atividades dali em diante, você pode prosseguir com esta etapa.

   Atualize o nome da mbox global personalizada para o mesmo nome usado no passo 2 acima.

   ![](assets/step-4-time-the-transition-with-your-release.png)

   >[!IMPORTANT]
   >
   >Quando você salvar, todas atividades em sua conta sincronizam com essa mbox. Se essa mbox não está no seu site, todas atividades param de funcionar.

   Clique em **[!UICONTROL Salvar]**.
