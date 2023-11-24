---
keywords: adicionar usuário;gerenciar usuário;permissões do usuário
description: Saiba como usar o  [!DNL Adobe Admin Console]  para gerenciar usuários(as) e suas permissões e direitos no  [!DNL Adobe Target Standard].
title: Como adicionar usuários e gerenciar permissões em uma conta do  [!DNL Target Standard] ?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: d40c25f75103327e749ad864b17df926cb323be0
workflow-type: ht
source-wordcount: '897'
ht-degree: 100%

---

# Usuários

Para contas do [!DNL Target Standard], é possível adicionar usuários e gerenciar suas permissões no [!DNL Adobe Admin Console].

>[!NOTE]
>
>As funcionalidades [!UICONTROL Propriedades] e [!UICONTROL Permissões] estão disponíveis como parte da solução do [!DNL Target Premium]. Elas não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.
>
>É possível saber se sua empresa tem uma licença [!UICONTROL Standard] ou [!UICONTROL Premium] clicando no link [!UICONTROL Administração] na parte superior da interface do [!DNL Target].
>
>* **[!DNL Target]Clientes [!UICONTROL Standard]**: se você vir a guia [!UICONTROL Usuários] ([!UICONTROL Administração > Usuários]) (e não a guia **[!UICONTROL Propriedades]**), então sua organização tem uma licença do [!DNL Target] [!UICONTROL Standard]. [!DNL Target]Clientes [!UICONTROL Standard] precisam seguir as instruções neste artigo para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
>
>* **[!DNL Target]Clientes Premium**: se você vir a guia [!UICONTROL Usuários] e a guia [!UICONTROL Propriedades] ([!UICONTROL Administração > Propriedades]), sua organização tem uma licença [!DNL Target] Premium. Os clientes do [!DNL Target] Premium devem seguir as instruções em [Permissões de usuário do Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) e [Configurar permissões do Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
>
>Para obter informações detalhadas sobre como gerenciar usuários e permissões, consulte [Gerenciar produtos e perfis](https://helpx.adobe.com/pt/enterprise/using/manage-products-and-profiles.html) no *Guia do usuário para empresas e equipes*.

Ao começar com [!DNL Adobe Target], você encontrará IDs (terminando em Adobe.com) preenchidas previamente em sua conta do [!DNL Adobe Experience Cloud]. Essas IDs são para que membros de equipes do [!DNL Adobe] possam ajudá-lo com sua nova conta e com a utilização do [!DNL Adobe Target], se for necessário. Para obter assistência, entre em contato com as equipes da Adobe da maneira usual.

Você não verá novos usuários listados na página [!UICONTROL Usuários] até que a pessoa faça logon usando a conta da [!DNL Adobe Experience Cloud] e, em seguida, faça logon no [!DNL Target].

Por padrão, todos os usuários do [!DNL Target] começam com permissões de [!UICONTROL Observador].

Os usuários administradores são identificados na lista [!UICONTROL Usuários]. Entre em contato com um desses usuários administradores de sistema se precisar alterar seu nível de acesso.

## Visualização de informações do usuário no [!DNL Target]

É possível visualizar uma lista de usuários atuais na interface do [!DNL Target], incluindo suas funções por espaço de trabalho e endereços de email.

Para exibir a página [!UICONTROL Usuários], clique em **[!UICONTROL Administração]** > **[!UICONTROL Usuários]**.

![Lista de usuários no Target](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Para gerenciar usuários existentes ou adicionar novos usuários, é necessário usar o [!UICONTROL Adobe Admin Console], conforme explicado abaixo.

## Acesse o [!DNL Adobe Admin Console] {#access}

Para tarefas executadas no [!DNL Adobe Admin Console], acesse o console seguindo estas etapas:

1. No [!DNL Target], clique em **[!UICONTROL Administração]** > **[!UICONTROL Usuários]** > **[!UICONTROL Gerenciamento de usuários]**.

   Ou

   Acesse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), faça logon usando sua Adobe ID, caso ainda não tenha se conectado.

1. (Condicional) Se tiver acesso ao [!DNL Admin Console for Enterprise] para mais de uma organização, clique no avatar do usuário no canto direito ou na barra de navegação superior e selecione a organização desejada.

## Adicionar usuários {#add-users}

Todo o gerenciamento de usuários deve ser executado no [!DNL Adobe Admin Console for Enterprise]. Entretanto, todos os seus usuários existentes no [!DNL Target] serão migrados do [!DNL Target] para o [!DNL Admin Console for Enterprise].

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Usuários]** > **[!UICONTROL Usuários]** para criar novos usuários ou editar usuários existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/pt/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Criar grupos de usuários {#user-groups}

É possível criar grupos de usuários, como Desenvolvedores, Analistas, Profissionais de marketing, Executivos etc. e atribuir privilégios em vários produtos e espaços de trabalho da [!DNL Adobe]. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da [!DNL Adobe] pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Usuários]** > **[!UICONTROL Grupo de usuários]** para criar novos grupos de usuários ou editar grupos existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/pt/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Especificar funções e permissões {#roles-permissions}

Somente administradores de sistema podem definir funções de usuário no [!DNL Target]. Por exemplo, um usuário aprovador [!UICONTROL Standard] não pode alterar um observador para um aprovador sem ter os direitos de Administrador na [!DNL Experience Cloud].

Os usuários administradores de sistema devem adicionar usuários ao sistema. Os usuários não são adicionados automaticamente. Eles são convidados por um email da [!DNL Experience Cloud] e devem confirmar seus endereços antes que suas contas sejam registradas.

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Produtos]** e selecione o nome do produto desejado.

   ![Guia Produtos](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Clique no espaço de trabalho desejado (por exemplo, Espaço de trabalho padrão).

   ![Espaço de trabalho padrão](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   A guia [!UICONTROL Usuários] exibe todos os usuários nesse espaço de trabalho.

   ![usuários de configuração](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Selecione a função de permissões desejada ([!UICONTROL Aprovador], [!UICONTROL Editor], [!UICONTROL Observador] ou [!UICONTROL Publicador]) usando a lista suspensa para cada usuário na coluna [!UICONTROL Função do produto].

   ![Lista suspensa Função do produto](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Função | Descrição |
   |--- |--- |
   | [!UICONTROL Aprovador] | Pode criar, editar, ativar ou parar atividades. |
   | [!UICONTROL Editor] | Pode criar e editar atividades antes de serem ativadas, mas não pode aprovar a inicialização de uma atividade. |
   | [!UICONTROL Observador] | Pode visualizar atividades, mas não pode criá-las ou editá-las. |
   | [!UICONTROL Publicador] | Semelhante à função de [!UICONTROL Observador] (pode visualizar atividades, mas não pode criá-las ou editá-las). No entanto, a função [!UICONTROL Publicador] tem a permissão adicional para ativar atividades. |

Para obter mais informações, consulte [Gerenciar permissões e funções do produto no Admin Console](https://helpx.adobe.com/pt/enterprise/help/manage-permissions-and-roles.html) no *Guia do usuário da empresa*.

## Vídeo de treinamento: Como configurar espaços de trabalho do Adobe Target ![Selo do tutorial](/help/main/assets/tutorial.png)

Objetivos de aprendizagem:

* Acesse o Adobe Admin Console na interface do Adobe Target (três maneiras)
* Configure um espaço de trabalho no Adobe Admin Console
   * Adicionar usuários a espaços de trabalho
   * Adicionar propriedades aos espaços de trabalho
* Compreenda espaços de trabalho padrão

>[!NOTE]
>
>A IU do menu [!DNL Target] [!UICONTROL Administração] (antiga [!UICONTROL Configuração]) foi redesenhada para fornecer desempenho aprimorado, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário em todo o produto. As informações do vídeo a seguir são corretas; no entanto, as opções podem estar em locais um pouco diferentes. Os vídeos atualizados serão publicados em breve.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
