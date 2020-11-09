---
keywords: Analytics as reporting source;a4t;A4T;requirements
description: Requisitos da conta do usuário para criar uma atividade do Adobe Analytics no Adobe Target (A4T).
title: Exigências de permissão do usuário
feature: a4t implementation
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 49%

---


# Exigências de permissão do usuário

Informações sobre os requisitos da conta de usuário para criar uma atividade baseada em [!DNL Adobe Analytics] no [!DNL Adobe Target] (A4T).

Para poder selecionar um conjunto de relatórios ao definir uma atividade do [!DNL Analytics], você precisa de uma conta de usuário do [!DNL Analytics] e de uma conta de usuário do [!DNL Target].

Suas contas de usuário devem ser configuradas conforme descrito nas seguintes seções:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Conclua as seguintes tarefas no [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com):

### Vincular contas da solução à Adobe ID

Suas contas de usuário do [!DNL Analytics] e do [!DNL Target] devem estar vinculadas a sua Adobe ID.

For more information, see [Organizations and account linking](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Configurar a associação do grupo da Experience Cloud

Você deve ser um membro de um ou mais grupos do [!DNL Experience Cloud] com acesso ao [!DNL Analytics] e [!DNL Target].

For more information, see [Manage Experience Cloud users and products](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Configure access to the [!DNL Analytics] report suite:

Para usar o A4T em um determinado conjunto de relatórios, é necessário ter acesso a esse conjunto de relatórios.

1. No **[!UICONTROL Admin Console]**, clique em um perfil de [!DNL Analytics] produto e, em seguida, clique na guia **[!UICONTROL Permissões]** .

   Em seguida, é possível ver a quais conjuntos de relatórios o perfil tem acesso.

1. Certifique-se de que o conjunto de relatórios ao qual você deseja ter acesso [!DNL Target] seja um dos listados no perfil do produto do qual você faz parte.

   A ilustração a seguir é um exemplo de um perfil de produto que tem acesso a todos os conjuntos de relatórios:

   ![Guia Permissão de Admin Console](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Nenhum privilégio adicional é necessário.
