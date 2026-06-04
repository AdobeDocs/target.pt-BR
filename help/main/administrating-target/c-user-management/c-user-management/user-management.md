---
keywords: adicionar usuário;gerenciar usuário;permissões do usuário
description: Saiba como usar o  [!DNL Adobe Admin Console]  para gerenciar usuários(as) e suas permissões e direitos no  [!DNL Adobe Target Standard].
title: Como adicionar usuários e gerenciar permissões em uma conta do  [!DNL Target Standard] ?
feature: Administration & Configuration
role: Admin
exl-id: 535c28c7-179d-4edc-b140-880b9dfe1d59
TQID: https://experienceleague.adobe.com/DdNQ81TpmyIRuPkmy4OIOq43CXwaMtm-uH2HtPjdx10
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: dfc8a233-f2b5-4811-bf63-b4262aebc5a5
subfeature_v2: id: c011fe9c-b94b-4a88-93d8-f2acece55112id: cd7b6938-5837-4ee0-9790-5840997133d9id: cf6b8469-14d0-4c0e-90ee-fb54066a035eid: faed1c89-faf7-4df1-910d-a88263e03b15id: fc9c2184-9102-403f-bd6c-0055021e4bea
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 925
ht-degree: 60%

---

# Usuários

Para contas do [!DNL Target Standard], é possível adicionar usuários e gerenciar suas permissões no [!DNL Adobe Admin Console].

>[!NOTE]
>
>A funcionalidade [!UICONTROL Propriedades] e [!UICONTROL Permissões] está disponível como parte da solução [!DNL Target Premium]. Elas não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.
>
>É possível saber se sua organização tem uma licença do [!UICONTROL Standard] ou do [!UICONTROL Premium] clicando no link [!UICONTROL Administração] na parte superior da interface do usuário do [!DNL Target].
>
>* Clientes **[!DNL Target][!UICONTROL Standard]**: se você vir a guia [!UICONTROL Usuários] ([!UICONTROL Administração > Usuários]) (e não a guia **[!UICONTROL Propriedades]**), sua organização tem uma licença [!DNL Target] [!UICONTROL Standard]. [!DNL Target] Os clientes do [!UICONTROL Standard] devem seguir as instruções neste artigo para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
>
>* Clientes do **[!DNL Target]Premium**: se você vir a guia [!UICONTROL Usuários] e a guia [!UICONTROL Propriedades] ([!UICONTROL Administração > Propriedades]), sua organização tem uma licença Premium do [!DNL Target]. [!DNL Target] Os clientes Premium devem seguir as instruções em [Permissões de usuário empresarial](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) e [Configurar permissões empresariais](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md) para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].
>
>Para obter informações detalhadas sobre como gerenciar usuários e permissões, consulte [Gerenciar produtos e perfis](https://helpx.adobe.com/pt/enterprise/using/manage-products-and-profiles.html) no *Guia do usuário para empresas e equipes*.

Ao começar com [!DNL Adobe Target], você encontrará IDs (terminando em Adobe.com) preenchidas previamente em sua conta do [!DNL Adobe Experience Cloud]. Essas IDs são para que membros de equipes do [!DNL Adobe] possam ajudá-lo com sua nova conta e com a utilização do [!DNL Adobe Target], se for necessário. Para obter assistência, entre em contato com as equipes da Adobe da maneira usual.

Você não verá novos usuários listados na página [!UICONTROL Usuários] até que eles façam logon usando sua conta do [!DNL Adobe Experience Cloud] e, em seguida, façam logon no [!DNL Target].

Por padrão, todos os usuários do [!DNL Target] começam com permissões de [!UICONTROL Observador].

Os usuários administradores são identificados na lista [!UICONTROL Usuários]. Entre em contato com um desses usuários administradores de sistema se precisar alterar seu nível de acesso.

## Visualização de informações do usuário no [!DNL Target]

É possível visualizar uma lista de usuários atuais na interface do [!DNL Target], incluindo suas funções por espaço de trabalho e endereços de email.

Para exibir a página [!UICONTROL Usuários], clique em **[!UICONTROL Administração]** > **[!UICONTROL Usuários]**.

>[!NOTE]
>
>Para gerenciar usuários existentes ou adicionar novos usuários, você deve usar o [!UICONTROL Adobe Admin Console], conforme explicado abaixo.

## Acesse o [!DNL Adobe Admin Console] {#access}

Para tarefas executadas no [!DNL Adobe Admin Console], acesse o console seguindo estas etapas:

1. Em [!DNL Target], clique em **[!UICONTROL Administração]** > **[!UICONTROL Usuários]** > **[!UICONTROL Gerenciamento de Usuários]**.

   Ou

   Acesse [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/), faça logon usando sua Adobe ID, caso ainda não tenha se conectado.

1. (Condicional) Se tiver acesso ao [!DNL Admin Console for Enterprise] para mais de uma organização, clique no avatar do usuário no canto direito ou na barra de navegação superior e selecione a organização desejada.

## Adicionar usuários {#add-users}

Todo o gerenciamento de usuários deve ser executado no [!DNL Adobe Admin Console for Enterprise]. Entretanto, todos os seus usuários existentes no [!DNL Target] serão migrados do [!DNL Target] para o [!DNL Admin Console for Enterprise].

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Usuários]** > **[!UICONTROL Usuários]** para criar novos usuários ou editar usuários existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/pt/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Criar grupos de usuários {#user-groups}

É possível criar grupos de usuários, como Desenvolvedores, Analistas, Profissionais de marketing, Executivos etc. e atribuir privilégios em vários produtos e espaços de trabalho da [!DNL Adobe]. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da [!DNL Adobe] pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Usuários]** > **[!UICONTROL Grupos de Usuários]** para criar novos grupos de usuários ou editar grupos existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/pt/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Especificar funções e permissões {#roles-permissions}

Somente administradores de sistema podem definir funções de usuário no [!DNL Target]. Por exemplo, um usuário aprovador do [!UICONTROL Standard] não pode alterar um observador para um aprovador, sem ter direitos de administrador do [!DNL Experience Cloud].

Os usuários administradores de sistema devem adicionar usuários ao sistema. Os usuários não são adicionados automaticamente. Eles são convidados por um email da [!DNL Experience Cloud] e devem confirmar seus endereços antes que suas contas sejam registradas.

>[!NOTE]
>
>Para exibir atividades em [!DNL Target], os usuários devem ser atribuídos diretamente a um espaço de trabalho com pelo menos a função [!UICONTROL Observador]. A atribuição por meio de grupos de usuários sozinha é insuficiente. Geralmente, é recomendável conceder aos usuários acesso ao espaço de trabalho padrão.

1. [No Admin Console](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#section_79796E0227D048F59BAE0AB02E544EBE), clique em **[!UICONTROL Produtos]**, depois selecione o nome do produto desejado.

1. Clique no espaço de trabalho desejado (por exemplo, Espaço de trabalho padrão).

   A guia [!UICONTROL Usuários] exibe todos os usuários nesse espaço de trabalho.

1. Selecione a função de permissões desejada ([!UICONTROL Aprovador], [!UICONTROL Editor], [!UICONTROL Observador] ou [!UICONTROL Publicador]) usando a lista suspensa para cada usuário na coluna [!UICONTROL Função do Produto].

   | Função | Descrição |
   |--- |--- |
   | [!UICONTROL Aprovador] | Pode criar, editar, ativar ou parar atividades. |
   | [!UICONTROL Editor] | Pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
   | [!UICONTROL Observador] | Pode exibir atividades, mas não pode criá-las ou editá-las. |
   | [!UICONTROL Publicador] | Semelhante à função [!UICONTROL Observador] (pode exibir atividades, mas não pode criá-las ou editá-las). No entanto, a função [!UICONTROL Editor] tem a permissão adicional para ativar atividades. |

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
>A interface do usuário do menu [!DNL Target] [!UICONTROL Administração] (antiga [!UICONTROL Configuração]) foi reprojetada para fornecer desempenho aprimorado, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário em todo o produto. As informações do vídeo a seguir são corretas; no entanto, as opções podem estar em locais um pouco diferentes. Os vídeos atualizados serão publicados em breve.

>[!VIDEO](https://video.tv.adobe.com/v/19463/)
