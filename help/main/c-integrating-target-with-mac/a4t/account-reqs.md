---
keywords: Analytics como fonte de geração de relatórios;a4t;A4T;requisitos
description: Saiba como configurar os requisitos da conta de usuário necessários para criar uma atividade do Adobe Analytics no Adobe [!DNL Target] uso do Analytics para [!DNL Target] (A4T).
title: Quais requisitos de permissão de usuário são necessários para o A4T?
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 34%

---

# Exigências de permissão do usuário

Informações sobre os requisitos da conta de usuário para criar uma atividade baseada em [!DNL Adobe Analytics] no [!DNL Adobe Target] (A4T).

Para poder selecionar um conjunto de relatórios ao definir uma atividade do [!DNL Analytics], você precisa de uma conta de usuário do [!DNL Analytics] e de uma conta de usuário do [!DNL Target].

Suas contas de usuário devem ser configuradas conforme descrito nas seguintes seções:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Conclua as seguintes tarefas no [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com):

### Vincular contas da solução à Adobe ID

Suas contas de usuário do [!DNL Analytics] e do [!DNL Target] devem estar vinculadas a sua Adobe ID.

Para obter mais informações, consulte [Organizações e vinculação de contas](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=en).

### Configurar a associação do grupo da Experience Cloud

Você deve ser um membro de um ou mais grupos do [!DNL Experience Cloud] com acesso ao [!DNL Analytics] e [!DNL Target].

Para obter mais informações, consulte [Gerenciar usuários e produtos do Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Para usar o A4T em um conjunto de relatórios específico, você deve ter acesso a esse conjunto de relatórios e conceder acesso ao [!DNL Web Services Access] grupo.

1. Entrada **[!UICONTROL Admin Console]**, clique em um [!DNL Analytics] perfil do produto e clique no link **[!UICONTROL Permissões]** guia.

   Você pode ver a quais conjuntos de relatórios o perfil tem acesso.

1. Verifique se o conjunto de relatórios ao qual você deseja ter acesso está [!DNL Target] O é um dos listados no perfil do produto do qual você faz parte.

   A ilustração a seguir é um exemplo de um perfil de produto que tem acesso a todos os conjuntos de relatórios:

   ![Guia Permissão de Admin Console](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. Configure o acesso ao [!UICONTROL Acesso aos serviços da Web] grupo.

   O acesso à [!UICONTROL Acesso aos serviços da Web] agrupar em [!DNL Analytics] é necessário para poder usar [!DNL Analytics] como fonte de relatórios para [!DNL Target].


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

Nenhum privilégio adicional é necessário.
