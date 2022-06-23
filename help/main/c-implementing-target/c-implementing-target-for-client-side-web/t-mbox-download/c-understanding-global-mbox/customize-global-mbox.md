---
keywords: mbox global; personalizar mbox global; editar at.js; at.js; implementar o at.js
description: Saiba como personalizar uma mbox global para at.js na página Administração-Implementação no Adobe Target.
title: Como personalizar uma mbox global?
feature: at.js
role: Developer
exl-id: 6d3eab89-818c-405c-81af-90dfbede7390
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 17%

---

# Personalizar uma mbox global

Informações para ajudar você a personalizar um [!DNL Adobe Target] mbox global para at.js.

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.

1. Desativar **[!UICONTROL Carregamento de página ativado (Criar mbox global automaticamente)]**, em seguida, adicione o nome da mbox global personalizada que você gostaria de usar para entregar atividades do [!DNL Target].

   >[!IMPORTANT]
   >
   >A alteração é salva automaticamente ao selecionar uma mbox global diferente.

   Essa mbox global personalizada também será usada para rastreamento de cliques.

   ![custom-global-mbox](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/assets/custom-global-mbox.png)

1. Implemente o [!DNL at.js] biblioteca do seu site.

   Consulte [Como implantar a at.js](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/how-to-deployatjs/) para obter mais informações.

1. Organize a transição com seu lançamento.

   Quando estiver pronto para [!DNL Target] para começar a usar sua mbox global para todas atividades no futuro, você pode prosseguir com esta etapa.

   Atualize o nome da mbox global personalizada para o mesmo nome usado no passo 2 acima.

   >[!IMPORTANT]
   >
   >Todas as atividades em sua conta sincronizam com essa mbox. Certifique-se de que a mbox global esteja presente no seu site para que as atividades continuem funcionando. Certifique-se de editar e salvar novamente as atividades afetadas que foram criadas com o Visual Experience Composer (VEC) que são sincronizadas com essa mbox. Não é necessário salvar novamente as atividades criadas no Experience Composer baseado em formulário ou por meio da API.

