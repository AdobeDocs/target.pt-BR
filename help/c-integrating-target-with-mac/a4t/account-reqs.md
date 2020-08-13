---
keywords: Analytics as reporting source;a4t;A4T
description: Requisitos da conta do usuário para criar uma atividade do Adobe Analytics no Adobe Target (A4T).
title: Exigências de permissão do usuário
feature: a4t implementation
solution: Target,Analytics
topic: Reports and analytics
uuid: cf359bcd-547e-4f8f-bcf6-e646245bb9ce
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 63%

---


# Exigências de permissão do usuário {#user-permission-requirements}

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

For more information, see [Manage Experience Cloud users and products](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Conclua as seguintes tarefas em [!DNL Adobe Analytics]:

### Configurar o acesso ao conjunto de relatórios do Analytics

Before creating or viewing reports for an [!DNL Analytics]-powered activity, you must be a member of the **[!UICONTROL All Report Access]** group, or a member of a group that has access to at least one report in the report suite that you want to use. Se não consegue exibir os relatórios, verifique se você é membro de um desses grupos.

Para obter mais informações, consulte perfis e grupos [de](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/admin-getting-started.html#section_AB50558124D541CF80A0D3D76D35A4BF)produtos.

### Configurar o acesso ao Grupo de acesso aos serviços da Web

Você deve fazer parte do grupo de acesso aos serviços da Web no [!DNL Analytics] para usar o [!DNL Analytics] como a fonte de relatórios para o [!DNL Target].

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Nenhum privilégio adicional é necessário.
