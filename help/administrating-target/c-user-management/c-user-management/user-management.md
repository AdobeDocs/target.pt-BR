---
keywords: add user;manage user;user permissions
description: Você pode adicionar usuários ao Adobe Target e gerenciar suas permissões no Adobe Admin Console.
title: Usuários
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 9b57d5554884b06d278c3baef3b2c1d5f37bdeb5
workflow-type: tm+mt
source-wordcount: '896'
ht-degree: 46%

---


# Usuários{#users}

Você pode adicionar usuários e gerenciar suas permissões em [!DNL Adobe Admin Console].

>[!NOTE]
>
>A funcionalidade [!UICONTROL Propriedades] e [!UICONTROL permissões] está disponível como parte da solução do [!DNL Target] Premium. Não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.
>Você pode saber se sua organização tem uma licença Padrão ou Premium clicando no link [!UICONTROL Administração] na parte superior da interface do usuário [!DNL Target].
>
>* **[!DNL Target]Clientes** padrão: Se você vir a guia   Usuário ([!UICONTROL Administração > Usuários]) (e não a guia  **** Propriedades), sua organização tem uma licença  [!DNL Target] Padrão. [!DNL Target][!Os clientes do Standard devem seguir as instruções neste artigo para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
   >
   >
* **[!DNL Target]Clientes** Premium: Se você vir a guia   Usuário e a guia   Propriedades ([!UICONTROL Administração > Propriedades]), sua organização tem uma licença  [!DNL Target] Premium. [!DNL Target] Os clientes Premium devem seguir as instruções em [permissões de usuário do Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) e [definir permissões corporativas](/help/administrating-target/c-user-management/property-channel/properties-overview.md) para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
>
>
Para obter informações detalhadas sobre como gerenciar usuários e permissões, consulte [Gerenciar produtos e perfis](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html) no *Enterprise &amp; Teams User Guide*.

Ao começar com [!DNL Adobe Target], você encontrará IDs (terminando em Adobe.com) preenchidas previamente em sua conta do [!DNL Adobe Experience Cloud]. Essas IDs são para membros das equipes [!DNL Adobe] para que possam ajudá-lo com sua nova conta e com o uso de [!DNL Adobe Target], caso precise de ajuda. Para obter assistência, entre em contato com as equipes da Adobe da maneira usual.

Você não verá o novo usuário listado na página [!UICONTROL Usuários] até que o usuário faça logon usando sua conta [!DNL Adobe Experience Cloud] e faça logon em [!DNL Target Standard/Premium].

Por padrão, todos os usuários do [!DNL Target] começam com permissões de observador.

Os usuários administradores são identificados na lista [!UICONTROL Usuários]. Entre em contato com um dos usuários administradores do sistema se precisar alterar seu nível de acesso.

## Visualização de informações do usuário no Público alvo

Você pode visualização uma lista dos usuários atuais no ambiente do Público alvo, incluindo suas funções por espaço de trabalho e endereços de email diretamente do Público alvo interno.

Para visualização na página Usuários, clique em **[!UICONTROL Administração]** > **[!UICONTROL Usuários]**.

![Lista do usuário no Público alvo](/help/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Para gerenciar usuários existentes ou adicionar novos usuários, você deve usar o [!UICONTROL Adobe Admin Console], conforme explicado abaixo.

## Acessar o Adobe Admin Console {#access}

Para tarefas executadas no Adobe Admin Console, acesse o console seguindo estas etapas:

1. Em [!DNL Target], clique em **[!UICONTROL Administração]** > **[!UICONTROL Utilizadores]** > **[!UICONTROL Gestão de Utilizadores]**.

   Ou

   Vá para [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) e faça logon usando seu Adobe ID, caso ainda não tenha feito logon.

1. (Condicional) Se tiver acesso ao [!DNL Admin Console for Enterprise] para mais de uma organização, clique no avatar do usuário no canto direito ou na barra de navegação superior e selecione a organização desejada.

## Adicionar usuários {#add-users}

Todo o gerenciamento de usuários deve ser executado no [!DNL Adobe Admin Console for Enterprise]. Entretanto, todos os seus usuários existentes no [!DNL Target] serão migrados do [!DNL Target] para o [!DNL Admin Console for Enterprise].

1. [No Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em  **[!UICONTROL Usuários]**  >  **** Usuários para criar novos usuários ou editar usuários existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Criar grupos de usuários {#user-groups}

É possível criar grupos de usuários, como Desenvolvedores, Analistas, Profissionais de marketing, Executivos, etc., e atribuir privilégios a vários produtos e espaços de trabalho da Adobe. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da Adobe pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

1. [No Admin Console](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em  **[!UICONTROL Usuários]**  >  **** Grupos de usuários para criar novos grupos de usuários ou para editar grupos existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Especificar funções e permissões {#roles-permissions}

Somente administradores de sistema podem definir funções de usuário no [!DNL Target]. Por exemplo, um usuário aprovador do Standard não pode alterar um observador para um aprovador, sem ter também [!DNL Experience Cloud] direitos de administrador.

Os usuários administradores de sistema devem adicionar usuários ao sistema. Os usuários não são adicionados automaticamente. Eles são convidados por email do [!DNL Experience Cloud] e devem confirmar seus endereços de email antes que suas contas sejam registradas.

1. [](/help/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE)No Admin Console, clique em **[!UICONTROL Produtos]** e selecione o nome do produto desejado.

   ![Guia Produtos](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Clique na área de trabalho desejada (por exemplo, Área de trabalho padrão).

   ![Espaço de trabalho padrão](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   A guia [!UICONTROL Usuários] exibe todos os usuários nesse espaço de trabalho.

   ![usuários de configuração](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Selecione a função de permissões desejada (Aprovador, Editor, ou Observador) usando a lista suspensa para cada usuário na coluna [!UICONTROL Função do produto].

   ![Lista suspensa Função do produto](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Função | Descrição |
   |--- |--- |
   | Aprovador | Pode criar, editar e ativar ou parar atividades. |
   | Editor | Pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
   | Observador | Pode exibir atividades, mas não pode criá-las ou editá-las. |
   | Editor | Semelhante à função Observador (pode visualização atividades, mas não pode criá-las ou editá-las). No entanto, a função Editor tem permissão adicional para ativar o atividade. |

Para obter mais informações, consulte [Gerenciar permissões e funções do produto no Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) no *Guia do usuário da empresa*.

## Vídeo de treinamento: Como configurar espaços de trabalho do Público alvo ![Etiqueta do tutorial](/help/assets/tutorial.png)

Objetivos de aprendizagem:

* Acesse o Adobe Admin Console na interface do Adobe Target (três maneiras)
* Configure um espaço de trabalho no Adobe Admin Console
   * Adicionar usuários a espaços de trabalho
   * Adicionar propriedades aos espaços de trabalho
* Compreenda espaços de trabalho padrão

>[!NOTE]
>
>A interface do usuário do menu [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) foi reprojetada para melhorar o desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário no produto. As informações do vídeo a seguir são geralmente corretas; no entanto, as opções podem estar em locais ligeiramente diferentes. Os vídeos atualizados serão publicados em breve.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
