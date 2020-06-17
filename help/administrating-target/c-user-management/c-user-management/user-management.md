---
keywords: add user;manage user;user permissions
description: É possível adicionar usuários e gerenciar suas permissões no Adobe Admin Console.
title: Usuários
subtopic: Getting Started
topic: Standard
uuid: 9b311dd3-b8fa-483d-aedd-96761cfcd67e
translation-type: tm+mt
source-git-commit: ca91c67f13dfc9b338d2f316af3c62b871bdcfa6
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Usuários{#users}

You can add users and manage their permissions in the [!DNL Adobe Admin Console].

>[!NOTE]
>
>A funcionalidade [!UICONTROL Propriedades] e [!UICONTROL permissões] está disponível como parte da solução do [!DNL Target] Premium. Não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.
>You can tell whether your organization has a Standard or Premium license by clicking the [!UICONTROL Administration] link at the top of the [!DNL Target] UI.
>
>* **[!DNL Target]Clientes **padrão: Se você visualizar a guia[!UICONTROL Usuários]([!UICONTROL Administração > Usuários]) (e não a guia**[!UICONTROL Propriedades ]**), sua organização tem uma licença[!DNL Target]Padrão. [!Os clientes do DNL Target Standard devem seguir as instruções neste artigo para adicionar usuários e atribuir permissões no[!DNL Adobe Admin Console].
   >
   >
* **[!DNL Target]Clientes **Premium: Se você visualizar a guia[!UICONTROL Usuários]e a guia[!UICONTROL Propriedades]([!UICONTROL Administração > Propriedades]), sua organização tem uma licença[!DNL Target]Premium.[!DNL Target]Os clientes Premium devem seguir as instruções em[permissões de usuário do Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md)e[definir permissões corporativas](/help/administrating-target/c-user-management/property-channel/properties-overview.md)para adicionar usuários e atribuir permissões no[!DNL Adobe Admin Console].
>
>
Para obter informações detalhadas sobre como gerenciar usuários e permissões, consulte [Gerenciar produtos e perfis](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) no Guia *do Usuário* Enterprise &amp; Teams.

Ao começar com [!DNL Adobe Target], você encontrará IDs (terminando em Adobe.com) preenchidas previamente em sua conta do [!DNL Adobe Experience Cloud]. These IDs are for members of [!DNL Adobe] teams so that they can assist you with your new account and with your use of [!DNL Adobe Target], should you need help. Para obter assistência, entre em contato com as equipes da Adobe da maneira usual.

You will not see the new user listed on the [!UICONTROL Users] page until the user logs in using his or her [!DNL Adobe Experience Cloud] account and then logs in to [!DNL Target Standard/Premium].

Por padrão, todos os usuários do [!DNL Target] começam com permissões de observador.

Admin users are identified in the [!UICONTROL Users] list. Entre em contato com um dos usuários administradores do sistema se precisar alterar seu nível de acesso.

## Acessar o Adobe Admin Console {#access}

Para tarefas executadas no Adobe Admin Console, acesse o console seguindo estas etapas:

1. Em [!DNL Target], clique em **[!UICONTROL Administração]** > **[!UICONTROL Usuários]** > Gerenciamento **** de usuários.

   Ou

   Go to [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), then sign in using your Adobe ID, if you have not already logged in.

1. (Condicional) Se tiver acesso ao [!DNL Admin Console for Enterprise] para mais de uma organização, clique no avatar do usuário no canto direito ou na barra de navegação superior e selecione a organização desejada.

## Add users {#add-users}

Todo o gerenciamento de usuários deve ser executado no [!DNL Adobe Admin Console for Enterprise]. Entretanto, todos os seus usuários existentes no [!DNL Target] serão migrados do [!DNL Target] para o [!DNL Admin Console for Enterprise].

1. [No Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Usuários]** > **[!UICONTROL Usuários]** para criar novos usuários ou editar usuários existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Create user groups {#user-groups}

É possível criar grupos de usuários, como Desenvolvedores, Analistas, Profissionais de marketing, Executivos, etc., e atribuir privilégios a vários produtos e espaços de trabalho da Adobe. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da Adobe pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

1. [No Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Usuários]** > Grupos **[!UICONTROL de]** usuários para criar novos grupos de usuários ou editar grupos existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Specify roles and permissions {#roles-permissions}

Somente administradores de sistema podem definir funções de usuário no [!DNL Target]. For example, a Standard approver user cannot change an observer to an approver, without also having [!DNL Experience Cloud] Admin rights.

Os usuários administradores de sistema devem adicionar usuários ao sistema. Os usuários não são adicionados automaticamente. They are invited by email from the [!DNL Experience Cloud] and must confirm their email addresses before their accounts are registered.

1. [](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)No Admin Console, clique em **[!UICONTROL Produtos]** e selecione o nome do produto desejado.

   ![Guia Produtos](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Clique na área de trabalho desejada (por exemplo, Área de trabalho padrão).

   ![Espaço de trabalho padrão](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   A guia [!UICONTROL Usuários] exibe todos os usuários nesse espaço de trabalho.

   ![usuários de configuração](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Selecione a função de permissões desejada (Aprovador, Editor, ou Observador) usando a lista suspensa para cada usuário na coluna [!UICONTROL Função do produto].

   ![lista suspensa Função do produto](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Função | Descrição |
   |--- |--- |
   | Aprovador | Pode criar, editar e ativar ou parar atividades. |
   | Editor | Pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
   | Observador | Pode exibir atividades, mas não pode criá-las ou editá-las. |
   | Editor | Semelhante à função Observador (pode visualização atividades, mas não pode criá-las ou editá-las). No entanto, a função Editor tem permissão adicional para ativar o atividade. |

Para obter mais informações, consulte [Gerenciar permissões e funções do produto no Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) no *Guia do usuário da empresa*.

## Training video: How to Configure Target Workspaces ![Tutorial badge](/help/assets/tutorial.png)

Objetivos de aprendizagem:

* Acesse o Adobe Admin Console na interface do Adobe Target (três maneiras)
* Configure um espaço de trabalho no Adobe Admin Console
   * Adicionar usuários a espaços de trabalho
   * Adicionar propriedades aos espaços de trabalho
* Compreenda espaços de trabalho padrão

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
