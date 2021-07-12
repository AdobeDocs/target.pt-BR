---
keywords: mbox global; personalizar mbox global; editar at.js; at.js; implementar o at.js
description: Saiba como personalizar uma mbox global para at.js na página Administração-Implementação no Adobe Target.
title: Como personalizar uma mbox global?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: fb0a62ecc5609e7b8ef5f6a4fb5a94f8ba025fec
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 22%

---

# Personalizar uma mbox global

Informações para ajudar você a personalizar uma mbox global para at.js.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.

1. Desative **[!UICONTROL Page load enabled (Auto create global mbox)]** e adicione o nome da mbox global personalizada que gostaria de usar para entregar atividades de [!DNL Target].

   >[!IMPORTANT]
   >
   >A alteração é salva automaticamente ao selecionar uma mbox global diferente.

   Essa mbox global personalizada também será usada para rastreamento de cliques.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Implemente a biblioteca [!DNL at.js] em seu site.

   Consulte [Como implantar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) para obter mais informações.

1. Organize a transição com seu lançamento.

   Quando estiver pronto para que [!DNL Target] comece a usar sua mbox global para todas atividades no futuro, você pode prosseguir com esta etapa.

   Atualize o nome da mbox global personalizada para o mesmo nome usado no passo 2 acima.

   >[!IMPORTANT]
   >
   >Todas as atividades em sua conta sincronizam com essa mbox. Se essa mbox não estiver no seu site, todas atividades param de funcionar.
