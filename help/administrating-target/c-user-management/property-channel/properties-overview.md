---
keywords: add user;project;user group;properties;workspace;manage property;property;at_property;roles;permissions
description: Informações sobre as tarefas necessárias para adicionar usuários à sua implementação do Adobe Target; criar espaços de trabalho, grupos de usuários e propriedades; atualizar sua implementação do Target para incluir o parâmetro at_property; e especificar funções e permissões.
title: Configuração de permissões empresariais
feature: null
subtopic: Getting Started
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1476'
ht-degree: 69%

---


# ![PREMIUM](/help/assets/premium.png) Configurar permissões corporativas{#configure-enterprise-permissions}

Information about the tasks required to add users to your [!DNL Target] implementation; create workspaces, user groups, and properties; update your [!DNL Target] implementation to include the `at_property` parameter; and specify roles and permissions.

>[!NOTE]
>
>A funcionalidade Propriedades e permissões está disponível como parte da solução do [Target Premium](/help/c-intro/intro.md#premium). Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

A tabela a seguir lista as tarefas que você deve realizar para criar propriedades e atribuir funções e permissões de usuário. Consulte as seções abaixo para obter mais informações sobre cada tarefa.

| Tarefa | Realizada em |
|--- |--- |
| 1. Adicionar usuários (Opcional) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Crie um espaço de trabalho (Perfil do produto) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Criar grupos de usuários (Opcional) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Criar propriedades | [!DNL Target] Interface do usuário |
| 5: atualizar sua implementação para incluir o parâmetro `at_property` | Interface do usuário do [!DNL Target], funções do at.js, [!DNL Adobe Launch] ou [!DNL Dynamic Tag Management] |
| 6: Especificar funções e permissões | [!DNL Adobe Admin Console for Enterprise] |

For those tasks performed in the [!DNL Adobe Admin Console for Enterprise], access the console by following these steps:

1. No Adobe Target, clique em **[!UICONTROL Administração]** > **[!UICONTROL Propriedades]** > **[!UICONTROL Atribuir propriedades a espaços de trabalho]**.

   Ou

   Go to [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) > sign in using your Adobe ID, if you have not already logged in.


1. (Condicional) Se tiver acesso ao [!DNL Admin Console for Enterprise] para mais de uma organização, clique no avatar do usuário no canto direito ou na barra de navegação superior e selecione a organização desejada.

## Etapa 1. Add users (Optional) {#section_A92AF0F921B743FEB9E9033433BD816A}

Quando você começa a usar a nova funcionalidade [!UICONTROL Propriedades], todo o gerenciamento de usuário deve ser realizado no [!DNL Adobe Admin Console for Enterprise]. Entretanto, todos os seus usuários existentes no [!DNL Target] serão migrados do [!DNL Target] para o [!DNL Admin Console for Enterprise].

1. [No Admin Console](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), clique na guia **[!UICONTROL Usuários]** na parte superior da página > **[!UICONTROL Adicionar usuários]** para criar novos usuários ou editar usuários existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Etapa 2. Create a workspace (product profile) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Uma área de trabalho (perfil de produto) permite que uma organização atribua um conjunto específico de usuários a um conjunto específico de propriedades. De muitas formas, um espaço de trabalho é semelhante a um conjunto de relatórios no [!DNL Analytics].

Organizations can begin taking advantage of Enterprise permissions functionality by creating new workspaces within [!DNL Admin Console], assigning [!DNL Target] properties to these workspaces, and moving users from the &quot;Default Workspace&quot; configuration to these newer, limited-access workspaces.

Os clientes podem usar esses espaços de trabalho para separar o acesso a diferentes equipes por região, por unidades de negócios, por seção do site ou por qualquer outro método que escolherem.

Os usuários podem fazer parte de vários espaços de trabalho e podem até ter diferentes funções dentro de cada um deles.

1. No [!DNL Admin Console], clique em **[!UICONTROL Produtos]** e selecione o nome do produto desejado.

   ![espaço de trabalho](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Crie o espaço de trabalho desejado (Perfil do produto):

   * **Acesso padrão:** Todas as atividades existentes serão combinadas em um único projeto chamado &quot;Acesso padrão&quot;. Isso não terá nenhum impacto sobre os clientes. Todas as funcionalidades e funções de usuário continuarão exatamente iguais, pois são anteriores a essa alteração.

      Todas as atividades criadas por meio do [!DNL Adobe Experience Manager] (AEM), do [!DNL Adobe Mobile Services] e do [!DNL Target Classic] também farão parte do espaço de trabalho &quot;Acesso padrão&quot;. Você não pode mover projetos de &quot;Acesso padrão&quot; para outro projeto atualmente.

   * **Novos espaços de trabalho (Perfis de produto):** Você pode começar a utilizar nova funcionalidade de permissões fazendo o seguinte:

      * Criar novos espaços de trabalho dentro do [!DNL Admin Console for Enterprise].
      * Atribuir propriedades do Target aos espaços de trabalho.

   Você pode usar esses espaços de trabalho para dividir o acesso a diferentes equipes por região, por unidades de negócios, por seção do site ou por qualquer outro método que você escolher. Os usuários podem fazer parte de vários espaços de trabalho e podem ter diferentes funções dentro de cada um deles.

1. Siga as instruções em [Criar e gerenciar configurações de produto](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) no *Guia do usuário da empresa*.

>[!NOTE]
>Veja o vídeo de treinamento abaixo para obter mais informações sobre como configurar espaços de trabalho.

### Obtain your workspace ID {#workspace-id}

Você precisará passar a ID do espaço de trabalho para utilizar as Permissões empresariais nas [APIs do Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).

1. No [Adobe Admin Console](https://adminconsole.adobe.com), clique na guia [!UICONTROL Produtos] e depois no produto, no menu esquerdo, para exibir a lista da PLC(workspace).
1. Clique na PLC(workspace) desejada e localize a ID de &quot;perfis&quot; no URL, como mostrado abaixo.

   ![workspaceID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Etapa 3. Create user groups (Optional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

É possível criar grupos de usuários, como Desenvolvedores, Analistas, Profissionais de marketing, Executivos, etc., e atribuir privilégios a vários produtos e espaços de trabalho da Adobe. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da Adobe pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

1. No Admin Console, clique na guia **[!UICONTROL Usuários]** na parte superior da página > **[!UICONTROL Grupos de usuários]** para criar novos grupos de usuários ou editar grupos existentes.
1. Siga as instruções em [Gerenciar usuários e grupos de uma configuração de produto](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) no *Guia do usuário da empresa*.

## Etapa 4. Create properties {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

As propriedades são ativadas adicionando um par de nome/valor específico como parâmetro com qualquer chamada (chamada de Público alvo, chamada de api etc.) ao Target.

As propriedades pertencem a canais específicos (Web, dispositivos móveis, email e API/Outros).

**Dica**: veja o vídeo de treinamento abaixo para obter mais informações sobre como criar propriedades.

1. In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.
1. Clique em **Criar propriedade**.

   ![Caixa de diálogo Nova propriedade](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   Preencha os campos:

   * **Nome da propriedade (obrigatório):** Especifique um nome descritivo para a propriedade.
   * **Descrição:** especifique uma descrição opcional para a propriedade.
   * **Canal:** Selecione o canal desejado para a propriedade: Web, Aplicativo móvel, E-mail, ou Outro/API (por exemplo, um conversor ou um console PlayStation).

1. Click **[!UICONTROL Copy]** to copy the code to your clipboard that you&#39;ll use while performing the steps in [5: Update Your Implementation to Include the at_property Parameter](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Clique em **[!UICONTROL Salvar]** ao concluir.

>[!NOTE]
>Veja o vídeo de treinamento abaixo para obter mais informações sobre a criação de propriedades.

## Step 5: Update your implementation to include the at_property parameter {#section_9B17A59807A94712BE642942442EBBC8}

To use the [!DNL Target] user-permissions functionality, you must add the `at_property` parameter to any call that is hitting [!DNL Target] (Target call, api call, etc.).

**Para obter o código do parâmetro`at_property`:**

1. (Condicional) Use o código de implementação que você gerou e salvou sua área de transferência enquanto realizava as etapas em [4. Crie propriedades](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) e prossiga para a etapa 2.

   Ou

   In [!DNL Target], click **[!UICONTROL Administration]** > **[!UICONTROL Properties]** to display the [!UICONTROL Properties] list.

   1. Passe o seu ponteiro do mouse sobre a coluna [!UICONTROL Última atualização] para a propriedade desejada ser exibida e clique no ícone do [!UICONTROL código].

      ![Código de focalização da propriedade](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Clique com o botão direito no código de implementação destacado para copiá-lo para sua área de transferência.

      ![Código de propriedade](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. Update your [!DNL Target] implementation with the implementation code obtained in the previous step.

   Há várias maneiras de atualizar sua implementação do [!DNL Target]. Por exemplo, é possível usar os métodos a seguir em páginas da Web:

   * **Por meio de um &quot;Parâmetro global&quot; em[!DNL Adobe Launch]:**

      For more information, see [Add Global Target Params](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) in the *Adobe Experience Platform Launch* documentation.

   * **Por meio de um &quot;Parâmetro global&quot; em[!DNL Dynamic Tag Management]:**

      ![](assets/property_token_2.png)

      Para obter mais informações, consulte [Parâmetros globais - Adobe Target](https://docs.adobe.com/content/help/en/dtm/using/tools-reference/target.html#global-parameters---adobe-target) na *Documentação de produto do Dynamic Tag Management*.

   * **Pela função targetPageParams():** coloque o seguinte código no <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> tags, acima da referência de at.js ou mbox.js.

      ![](assets/property_token_1.png)

      Para obter mais informações sobre como fazer isso com o at.js, consulte [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md).

   * **Por meio da função mboxCreate():**

      ![](assets/property_token_3.png)

      Para obter mais informações sobre como fazer isso com a at.js, consulte  [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) e  [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md).

## Step 6: Specify roles and permissions {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. No Admin Console, clique em **[!UICONTROL Produtos]** e selecione o nome do produto desejado.

   ![Workspace](/help/administrating-target/c-user-management/c-user-management/assets/workspace-publisher.png)

1. Clique no nome do perfil desejado (por exemplo, Área de trabalho padrão).

   ![Espaço de trabalho padrão](/help/administrating-target/c-user-management/c-user-management/assets/default-workspace-new.png)

1. Clique em **[!UICONTROL Usuários]**.

   A guia [!UICONTROL Usuários] exibe todos os usuários nesse espaço de trabalho.

   ![usuários de configuração](/help/administrating-target/c-user-management/c-user-management/assets/configuration_users-new-publisher.png)

1. Select the desired permissions role (Approver, Editor, Observer, or Publisher) by using the drop-down list for each user in the [!UICONTROL Product Role] column.

   ![Lista suspensa Função do produto](/help/administrating-target/c-user-management/c-user-management/assets/product-role-new.png)

   | Função | Descrição |
   |--- |--- |
   | Aprovador | Pode criar, editar e ativar ou parar atividades. |
   | Editor | Pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
   | Observador | Pode exibir atividades, mas não pode criá-las ou editá-las. |
   | Editor | Semelhante à função Observador (pode visualização atividades, mas não pode criá-las ou editá-las). No entanto, a função Editor tem permissão adicional para ativar o atividade. |

   Para obter mais informações, consulte [Gerenciar permissões e funções do produto no Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) no *Guia do usuário da empresa*.

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

>[!NOTE]
>
>A interface do usuário do menu [!DNL Target] Administração [!UICONTROL (anteriormente] Configuração ) foi reprojetada para melhorar o desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário no produto. As informações contidas nos vídeos que se seguem são geralmente corretas; no entanto, as opções podem estar em locais ligeiramente diferentes. Os vídeos atualizados serão publicados em breve.

### Como configurar espaços de trabalho do Público alvo (6:55) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo explica como criar espaços de trabalho.

* Acessar o Adobe Admin Console a partir da interface do Adobe Target (3 maneiras)
* Configure um espaço de trabalho no Adobe Admin Console

   * Adicionar usuários a espaços de trabalho
   * Adicionar propriedades aos espaços de trabalho

* Compreenda espaços de trabalho padrão

>[!VIDEO](https://video.tv.adobe.com/v/19463/)

### How to Create Properties in Adobe Target (3:05) ![Tutorial badge](/help/assets/tutorial.png)

* Como criar uma propriedade na interface do [!DNL Adobe Target]
* Como gerar um token de propriedade para incluir na sua implementação de propriedade
* Familiarize-se com os três métodos de implementação:

   * Web
   * Aplicativo móvel
   * Email, definir caixa superior ou chamadas da API

>[!VIDEO](https://video.tv.adobe.com/v/18990/)
