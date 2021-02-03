---
keywords: mbox global;personalizar mbox global;editar at.js;at.js;implementar at.js
description: Informações que ajudam a personalizar uma mbox global para at.js.
title: Personalizar uma mbox global
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '170'
ht-degree: 55%

---


# Personalizar uma mbox global

Informações que ajudam a personalizar uma mbox global para at.js.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.

1. Desative **[!UICONTROL Carregamento de página ativado (Criar mbox global automaticamente)]** e adicione o nome da mbox global personalizada que você gostaria de usar para fornecer atividades de [!DNL Target].

   Essa mbox global personalizada também será usada para rastreamento de cliques.

   ![custom-global-mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Clique em **[!UICONTROL Salvar]** ao terminar.

1. Implemente a biblioteca [!DNL at.js] em seu site.

   Consulte [Como implantar at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md) para obter mais informações.

1. Organize a transição com seu lançamento.

   Assim que estiver pronto para que o [!DNL Target] comece a usar sua mbox global para todas atividades dali em diante, você pode prosseguir com esta etapa.

   Atualize o nome da mbox global personalizada para o mesmo nome usado no passo 2 acima.

   >[!IMPORTANT]
   >
   >Quando você salvar, todas atividades em sua conta sincronizam com essa mbox. Se essa mbox não está no seu site, todas atividades param de funcionar.

