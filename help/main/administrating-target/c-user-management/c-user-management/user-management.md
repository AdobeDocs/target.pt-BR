---
keywords: adicionar usuário;gerenciar usuário;permissões do usuário
description: Saiba como usar o  [!DNL Adobe Admin Console]  para gerenciar usuários(as) e suas permissões e direitos no  [!DNL Adobe Target Standard].
title: Como adicionar usuários e gerenciar permissões em uma conta do  [!DNL Target Standard] ?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
source-git-commit: d40c25f75103327e749ad864b17df926cb323be0
workflow-type: tm+mt
source-wordcount: '826'
ht-degree: 66%

---

# Usuários

Para contas do [!DNL Target Standard], é possível adicionar usuários e gerenciar suas permissões no [!DNL Adobe Admin Console].

>[!NOTE]
>
>A funcionalidade [!UICONTROL Properties] e [!UICONTROL Permissions] está disponível como parte da solução [!DNL Target Premium]. Elas não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.
>
>É possível saber se sua organização tem uma licença do [!UICONTROL Standard] ou do [!UICONTROL Premium] clicando no link [!UICONTROL Administration] na parte superior da interface do usuário do [!DNL Target].
>
>* **[!DNL Target][!UICONTROL Standard] Clientes**: se você vir a guia [!UICONTROL Users] ([!UICONTROL Administration > Users]) (e não a guia **[!UICONTROL Properties]**), sua organização tem uma licença [!DNL Target] [!UICONTROL Standard]. [!DNL Target] clientes do [!UICONTROL Standard] devem seguir as instruções neste artigo para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
>
>* Clientes do **[!DNL Target]Premium**: se você vir a guia [!UICONTROL Users] e a guia [!UICONTROL Properties] ([!UICONTROL Administration > Properties]), sua organização tem uma licença [!DNL Target] Premium. Os clientes do [!DNL Target] Premium devem seguir as instruções em [Permissões de usuário do Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) e [Configurar permissões do Enterprise](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
>
>Para obter informações detalhadas sobre como gerenciar usuários e permissões, consulte [Gerenciar produtos e perfis](https://helpx.adobe.com/pt/enterprise/using/manage-products-and-profiles.html) no *Guia do usuário para empresas e equipes*.

Ao começar com [!DNL Adobe Target], você encontrará IDs (terminando em Adobe.com) preenchidas previamente em sua conta do [!DNL Adobe Experience Cloud]. Essas IDs são para que membros de equipes do [!DNL Adobe] possam ajudá-lo com sua nova conta e com a utilização do [!DNL Adobe Target], se for necessário. Para obter assistência, entre em contato com as equipes da Adobe da maneira usual.

Você não verá novos usuários listados na página [!UICONTROL Users] até que eles façam logon usando sua conta [!DNL Adobe Experience Cloud] e, em seguida, façam logon no [!DNL Target].

Por padrão, todos os usuários do [!DNL Target] começam com [!UICONTROL Observer] permissões.

Os usuários administradores são identificados na lista [!UICONTROL Users]. Entre em contato com um desses usuários administradores de sistema se precisar alterar seu nível de acesso.

## Visualização de informações do usuário no [!DNL Target]

É possível visualizar uma lista de usuários atuais na interface do [!DNL Target], incluindo suas funções por espaço de trabalho e endereços de email.

Para exibir a página [!UICONTROL Users], clique em **[!UICONTROL Administration]** > **[!UICONTROL Users]**.

![Lista de usuários no Target](/help/main/administrating-target/c-user-management/c-user-management/assets/user-list-target.png)

>[!NOTE]
>
>Para gerenciar usuários existentes ou adicionar novos usuários, você deve usar o [!UICONTROL Adobe Admin Console], conforme explicado abaixo.

## Acesse o [!DNL Adobe Admin Console] {#access}

Para tarefas executadas no [!DNL Adobe Admin Console], acesse o console seguindo estas etapas:

1. Em [!DNL Target], clique em **[!UICONTROL Administration]** > **[!UICONTROL Users]** > **[!UICONTROL Users Management]**.

   Ou

   Acesse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), faça logon usando sua Adobe ID, caso ainda não tenha se conectado.

1. (Condicional) Se tiver acesso ao [!DNL Admin Console for Enterprise] para mais de uma organização, clique no avatar do usuário no canto direito ou na barra de navegação superior e selecione a organização desejada.

## Adicionar usuários {#add-users}

Todo o gerenciamento de usuários deve ser executado no [!DNL Adobe Admin Console for Enterprise]. Entretanto, todos os seus usuários existentes no [!DNL Target] serão migrados do [!DNL Target] para o [!DNL Admin Console for Enterprise].

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Users]** > **[!UICONTROL Users]** para criar novos usuários ou editar usuários existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/pt/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Criar grupos de usuários {#user-groups}

É possível criar grupos de usuários, como Desenvolvedores, Analistas, Profissionais de marketing, Executivos etc. e atribuir privilégios em vários produtos e espaços de trabalho da [!DNL Adobe]. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da [!DNL Adobe] pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Users]** > **[!UICONTROL User Groups]** para criar novos grupos de usuários ou editar grupos existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/pt/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Especificar funções e permissões {#roles-permissions}

Somente administradores de sistema podem definir funções de usuário no [!DNL Target]. Por exemplo, um usuário aprovador [!UICONTROL Standard] não pode alterar um observador para um aprovador, sem ter direitos de administrador [!DNL Experience Cloud].

Os usuários administradores de sistema devem adicionar usuários ao sistema. Os usuários não são adicionados automaticamente. Eles são convidados por um email da [!DNL Experience Cloud] e devem confirmar seus endereços antes que suas contas sejam registradas.

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Products]** e selecione o nome do produto desejado.

   ![Guia Produtos](/help/main/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Clique no espaço de trabalho desejado (por exemplo, Espaço de trabalho padrão).

   ![Espaço de trabalho padrão](/help/main/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

   A guia [!UICONTROL Users] exibe todos os usuários nesse espaço de trabalho.

   ![usuários de configuração](/help/main/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Selecione a função de permissões desejada ([!UICONTROL Approver], [!UICONTROL Editor], [!UICONTROL Observer] ou [!UICONTROL Publisher]) usando a lista suspensa para cada usuário na coluna [!UICONTROL Product Role].

   ![Lista suspensa Função do produto](/help/main/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Função | Descrição |
   |--- |--- |
   | [!UICONTROL Approver] | Pode criar, editar, ativar ou parar atividades. |
   | [!UICONTROL Editor] | Pode criar e editar atividades antes de serem ativadas, mas não pode aprovar a inicialização de uma atividade. |
   | [!UICONTROL Observer] | Pode visualizar atividades, mas não pode criá-las ou editá-las. |
   | [!UICONTROL Publisher] | Semelhante à função [!UICONTROL Observer] (pode exibir atividades, mas não pode criá-las ou editá-las). No entanto, a função [!UICONTROL Publisher] tem a permissão adicional para ativar atividades. |

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
>A interface do usuário de menu do [!DNL Target] [!UICONTROL Administration] (antigo [!UICONTROL Setup]) foi reprojetada para fornecer melhor desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário no produto. As informações do vídeo a seguir são corretas; no entanto, as opções podem estar em locais um pouco diferentes. Os vídeos atualizados serão publicados em breve.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
