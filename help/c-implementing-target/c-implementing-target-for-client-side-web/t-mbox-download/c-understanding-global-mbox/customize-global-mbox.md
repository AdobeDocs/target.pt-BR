---
keywords: global mbox;customize global mbox;edit at.js;at.js;implement at.js
description: Informações que ajudam a personalizar uma mbox global para at.js.
title: Personalizar uma mbox global
feature: null
subtopic: Getting Started
topic: Standard
uuid: 0f784d6e-8f36-4c26-adbf-0d56b7d6d390
translation-type: tm+mt
source-git-commit: 8bf89f30fec597b983067ec4604dba09a9ec2832
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 59%

---


# Personalizar uma mbox global{#customize-a-global-mbox}

Informações que ajudam a personalizar uma mbox global para at.js.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.

1. Disable **[!UICONTROL Page load enabled (Auto create global mbox)]**, then add the name of the custom global mbox that you would like to use to deliver activities from [!DNL Target].

   Essa mbox global personalizada também será usada para rastreamento de cliques.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Clique em **[!UICONTROL Salvar]** ao terminar.

1. Implement the [!DNL at.js] library on your site.

   Consulte [Como implantar o at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) para obter mais informações.

1. Organize a transição com seu lançamento.

   Assim que estiver pronto para que o [!DNL Target] comece a usar sua mbox global para todas atividades dali em diante, você pode prosseguir com esta etapa.

   Atualize o nome da mbox global personalizada para o mesmo nome usado no passo 2 acima.

   >[!IMPORTANT]
   >
   >Quando você salvar, todas atividades em sua conta sincronizam com essa mbox. Se essa mbox não está no seu site, todas atividades param de funcionar.

