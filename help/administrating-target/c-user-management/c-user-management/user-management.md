---
description: É possível adicionar usuários e gerenciar suas permissões no Adobe Admin Console.
keywords: adicionar usuário;gerenciar usuário;permissões do usuário
seo-description: É possível adicionar usuários e gerenciar suas permissões no Adobe Admin Console.
seo-title: Usuários
solution: Target
subtopic: Introdução
title: Usuários
topic: Padrão
uuid: 9 b 311 dd 3-b 8 fa -483 d-aedd -96761 cfcd 67 e
translation-type: tm+mt
source-git-commit: 7b944c5452969ce66f1386eb93378d7bf612beb4

---


# Usuários{#users}

É possível adicionar usuários e gerenciar suas permissões no Adobe Admin Console.

>[!NOTE]
>
>A funcionalidade [!UICONTROL Propriedades] e [!UICONTROL permissões] está disponível como parte da solução do [!DNL Target] Premium. Elas não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.
>É possível saber se sua organização tem uma licença Standard ou Premium clicando no link [!UICONTROL Configurar] na parte superior da interface do usuário do [!DNL Target].
>
>**[!DNL Target]Clientes padrão**: se você exibir a guia [!UICONTROL Usuários] ([!UICONTROL Configuração &gt; Usuários]), sua organização terá uma licença do [!DNL Target] Standard. [!Os clientes do DNL Target Standard devem seguir as instruções neste artigo para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
>
>**[!DNL Target]Clientes Premium**: se você exibir a guia [!UICONTROL Propriedades] ([!UICONTROL Configuração &gt; Propriedades]), sua organização tem uma licença [!DNL Target] Premium. [!DNL Target] Os clientes Premium devem seguir as instruções em [permissões de usuário do Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md) e [definir permissões corporativas](/help/administrating-target/c-user-management/property-channel/properties-overview.md) para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].

Somente usuários administradores de sistema podem adicionar usuários e gerenciar suas permissões. A função de administrador do sistema é atribuída no nível da [!DNL Experience Cloud]. As funções da [!DNL Experience Cloud] são separadas das funções gerenciadas em cada solução.

Ao começar com [!DNL Adobe Target], você encontrará IDs (terminando em Adobe.com) preenchidas previamente em sua conta do [!DNL Adobe Experience Cloud]. Essas IDs são para que membros das equipes da Adobe possam ajudá-lo com sua nova conta e com a utilização do [!DNL Adobe Target], se necessário. Para obter assistência, entre em contato com as equipes da Adobe da maneira usual.

Você não verá o novo usuário listado na página [!UICONTROL Usuários] até que o usuário faça logon usando sua conta da Adobe Experience Cloud e, em seguida, faça logon no [!DNL Target Standard/Premium], clicando no cartão [!DNL Target].

Por padrão, todos os usuários do [!DNL Target] começam com permissões de observador.

Os usuários administradores de sistema são identificados na lista de usuários. Entre em contato com um desses usuários administradores de sistema se precisar alterar seu nível de acesso.

## Acessar o Adobe Admin Console {#section_79796E0227D048F59BAE0AB02E544EBE}

Para tarefas executadas no Adobe Admin Console, acesse o console seguindo estas etapas:

1. Acesse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/) &gt; faça logon usando sua Adobe ID, caso ainda não tenha se conectado.

   Ou

   Se você já estiver conectado à Experience Cloud, vá para [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com)e clique no ícone [!UICONTROL Aplicativo] na barra de navegação superior &gt; clique **[!UICONTROL em Admin]** no lado direito.

1. (Condicional) Se tiver acesso ao [!DNL Admin Console for Enterprise] para mais de uma organização, clique no avatar do usuário no canto direito ou na barra de navegação superior e selecione a organização desejada.

## Adicionar usuários {#section_A92AF0F921B743FEB9E9033433BD816A}

Todo o gerenciamento de usuários deve ser executado no [!DNL Adobe Admin Console for Enterprise]. Entretanto, todos os seus usuários existentes no [!DNL Target] serão migrados do [!DNL Target] para o [!DNL Admin Console for Enterprise].

1. [No Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique **[!UICONTROL em Usuários]** &gt; **[!UICONTROL Usuários]** para criar novos usuários ou editar usuários existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Criar grupos de usuários {#section_5F5CB9AA7A9F4D26953E22016DA59605}

É possível criar grupos de usuários, como Desenvolvedores, Analistas, Profissionais de marketing, Executivos, etc., e atribuir privilégios a vários produtos e espaços de trabalho da Adobe. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da Adobe pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

1. [No Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique **[!UICONTROL em Usuários]** &gt; Grupos **[!UICONTROL de usuários]** para criar novos grupos de usuários ou editar grupos existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Especificar funções e permissões {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

Somente administradores de sistema podem definir funções de usuário no [!DNL Target]. Por exemplo, um usuário aprovador do Standard não pode alterar um observador para um aprovador, sem ter direitos de Admin da Experience Cloud.

Os usuários administradores de sistema devem adicionar usuários ao sistema. Os usuários não são adicionados automaticamente. Eles são convidados por um email da Experience Cloud e devem confirmar seus endereços antes que suas contas sejam registradas.

1. [No Admin Console](../../../administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Produtos]** e selecione o nome do produto desejado.

   ![Guia Produtos](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Clique no nome da configuração desejada.
1. Clique em **[!UICONTROL Usuários]**.

   A guia [!UICONTROL Usuários] exibe todos os usuários nessa área de trabalho.

   ![usuários de configuração](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new.png)

1. Selecione a função de permissões desejada (Observador, Editor ou Aprovador) usando a lista suspensa de cada usuário na coluna [!UICONTROL Função do produto].

   | Função | Descrição |
   |--- |--- |
   | Observador | Pode exibir atividades, mas não pode criá-las ou editá-las. |
   | Editor | pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
   | Aprovador | Pode criar, editar e ativar ou parar atividades. |

Para obter mais informações, consulte [Gerenciar permissões e funções do produto no Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) no *Guia do usuário da empresa*.

## Vídeo de treinamento: Como configurar espaços de trabalho do Target

Objetivos de aprendizagem:

* Acesse o Adobe Admin Console na interface do Adobe Target (três formas)
* Configurar uma área de trabalho no Adobe Admin Console
   * Adicionar usuários a espaços de trabalho
   * Adicionar propriedades aos espaços de trabalho
* Compreenda espaços de trabalho padrão

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
