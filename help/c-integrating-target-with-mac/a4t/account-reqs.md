---
keywords: Analytics como fonte de relatórios;a4t;A4T;requirements
description: Saiba como configurar os requisitos de conta de usuário necessários para criar uma atividade baseada em Adobe Analytics no Adobe Target usando o Analytics para Públicos alvos (A4T).
title: Quais são os requisitos de permissão de usuário necessários para o A4T?
feature: Analytics for Target (A4T)
solution: Target,Analytics
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '280'
ht-degree: 38%

---


# Exigências de permissão do usuário

Informações sobre os requisitos da conta de usuário para criar uma atividade baseada em [!DNL Adobe Analytics] no [!DNL Adobe Target] (A4T).

Para poder selecionar um conjunto de relatórios ao definir uma atividade do [!DNL Analytics], você precisa de uma conta de usuário do [!DNL Analytics] e de uma conta de usuário do [!DNL Target].

Suas contas de usuário devem ser configuradas conforme descrito nas seguintes seções:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Conclua as seguintes tarefas no [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com):

### Vincular contas da solução à Adobe ID

Suas contas de usuário do [!DNL Analytics] e do [!DNL Target] devem estar vinculadas a sua Adobe ID.

Para obter mais informações, consulte [Organizações e vinculação de contas](https://docs.adobe.com/help/en/core-services/interface/manage-users-and-products/organizations.html).

### Configurar a associação do grupo da Experience Cloud

Você deve ser um membro de um ou mais grupos do [!DNL Experience Cloud] com acesso ao [!DNL Analytics] e [!DNL Target].

Para obter mais informações, consulte [Gerenciar usuários e produtos do Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Configure o acesso ao conjunto de relatórios [!DNL Analytics]:

Para usar o A4T em um determinado conjunto de relatórios, é necessário ter acesso a esse conjunto de relatórios.

1. Em **[!UICONTROL Admin Console]**, clique em um perfil de produto [!DNL Analytics] e, em seguida, clique na guia **[!UICONTROL Permissões]**.

   Em seguida, é possível ver a quais conjuntos de relatórios o perfil tem acesso.

1. Verifique se o conjunto de relatórios ao qual você deseja ter acesso em [!DNL Target] é um dos listados no perfil de produto do qual você faz parte.

   A ilustração a seguir é um exemplo de um perfil de produto que tem acesso a todos os conjuntos de relatórios:

   ![Guia Permissão de Admin Console](/help/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

## Adobe Target {#section_26BA212D8D40443E9EE2AB327091425C}

Nenhum privilégio adicional é necessário.
