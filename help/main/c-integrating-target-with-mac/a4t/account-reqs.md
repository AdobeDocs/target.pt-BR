---
keywords: Analytics como fonte de geração de relatórios;a4t;A4T;requisitos
description: Saiba como configurar os requisitos da conta de usuário necessários para criar uma atividade baseada no Adobe Analytics no Adobe [!DNL Target] usando o Analytics for [!DNL Target] (A4T).
title: Quais requisitos de permissão de usuário são necessários para o A4T?
feature: Analytics for Target (A4T)
solution: Target,Analytics
exl-id: f56fc525-92da-4814-86c1-18b3a2765f37
TQID: https://experienceleague.adobe.com/SGNIoARqe3yN4WvKF4JPIp0t0JCMiSgj--zrjt-ZXJQ
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 307
ht-degree: 31%

---

# Exigências de permissão do usuário

Informações sobre os requisitos da conta de usuário para criar uma atividade baseada em [!DNL Adobe Analytics] no [!DNL Adobe Target] (A4T).

Para poder selecionar um conjunto de relatórios ao definir uma atividade do [!DNL Analytics], você precisa de uma conta de usuário do [!DNL Analytics] e de uma conta de usuário do [!DNL Target].

Suas contas de usuário devem ser configuradas conforme descrito nas seguintes seções:

## Adobe Experience Cloud {#section_3931A2FAD38F4A4FA92CC77B92AF3F0D}

Conclua as seguintes tarefas no [!DNL Adobe Experience Cloud] [Admin Console](https://adminconsole.adobe.com):

### Vincular contas da solução à Adobe ID

Suas contas de usuário do [!DNL Analytics] e do [!DNL Target] devem estar vinculadas a sua Adobe ID.

Para obter mais informações, consulte [Organizações e vinculação de contas](https://experienceleague.adobe.com/docs/core-services/interface/administration/organizations.html?lang=pt-BR).

### Configurar a associação do grupo da Experience Cloud

Você deve ser um membro de um ou mais grupos do [!DNL Experience Cloud] com acesso ao [!DNL Analytics] e [!DNL Target].

Para obter mais informações, consulte [Gerenciar usuários e produtos da Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/admin-getting-started.html?lang=pt-BR).

## Adobe Analytics {#section_8F404FDE9A634534AB0AA4CB3075582B}

Para usar o A4T em um conjunto de relatórios específico, você deve ter acesso a esse conjunto de relatórios e conceder acesso ao grupo [!DNL Web Services Access].

1. No **[!UICONTROL Admin Console]**, clique em um perfil de produto [!DNL Analytics] e na guia **[!UICONTROL Permissões]**.

   Você pode ver a quais conjuntos de relatórios o perfil tem acesso.

1. Verifique se o conjunto de relatórios ao qual você deseja ter acesso no [!DNL Target] está listado no perfil de produto do qual você faz parte.

   A ilustração a seguir é um exemplo de um perfil de produto que tem acesso a todos os conjuntos de relatórios:

   ![Guia de Permissão do Admin Console](/help/main/c-integrating-target-with-mac/a4t/assets/permissions-tab.png)

1. Configure o acesso ao grupo [!UICONTROL Acesso aos Serviços da Web].

   O acesso ao grupo [!UICONTROL Acesso aos Serviços da Web] em [!DNL Analytics] é necessário para usar [!DNL Analytics] como a fonte de relatórios para [!DNL Target].


## Adobe [!DNL Target] {#section_26BA212D8D40443E9EE2AB327091425C}

Nenhum privilégio adicional é necessário.
