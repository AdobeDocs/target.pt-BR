---
description: Informações sobre as tarefas necessárias para adicionar usuários à sua implementação do Target; criar espaços de trabalho, grupos de usuários e propriedades; atualizar sua implementação do Target para incluir o parâmetro at_property; e especificar funções e permissões.
keywords: adicionar usuário; projeto; grupo de usuários; propriedades; espaço de trabalho; gerenciar propriedade; propriedade; at_ property; funções; permissões
seo-description: Informações sobre as tarefas necessárias para adicionar usuários à sua implementação do Adobe Target; criar espaços de trabalho, grupos de usuários e propriedades; atualizar sua implementação do Target para incluir o parâmetro at_property; e especificar funções e permissões.
seo-title: Configuração de permissões empresariais
solution: Target
subtopic: Introdução
title: Configuração de permissões empresariais
title-outputclass: premium
topic: Premium
uuid: 2f44ecd5-5c43-49c3-b1c3-58d28531c859
badge: premium
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![PREMIUM](/help/assets/premium.png) Configurar permissões corporativas{#configure-enterprise-permissions}

Informações sobre as tarefas necessárias para adicionar usuários à sua implementação do Target; criar espaços de trabalho, grupos de usuários e propriedades; atualizar sua implementação do Target para incluir o parâmetro `at_property`; e especificar funções e permissões.

>[!NOTE]
>
>A funcionalidade Propriedades e permissões está disponível como parte da solução do [Target Premium](/help/c-intro/intro.md#premium). Eles não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

A tabela a seguir lista as tarefas que você deve realizar para criar propriedades e atribuir funções e permissões de usuário. Consulte as seções abaixo para obter mais informações sobre cada tarefa.

| Tarefa | Realizada em |
|--- |--- |
| 1. Adicionar usuários (Opcional) | [!DNL Adobe Admin Console for Enterprise] |
| 2. Crie um espaço de trabalho (Perfil do produto) | [!DNL Adobe Admin Console for Enterprise] |
| 3. Criar grupos de usuários (Opcional) | [!DNL Adobe Admin Console for Enterprise] |
| 4. Criar propriedades | [!DNL Target] Interface do usuário |
| 5: atualizar sua implementação para incluir o parâmetro `at_property` | Interface do usuário do [!DNL Target], funções do at.js, [!DNL Adobe Launch] ou [!DNL Dynamic Tag Management] |
| 6: Especificar funções e permissões | [!DNL Adobe Admin Console for Enterprise] |

Para essas tarefas realizadas no Adobe Admin Console for Enterprise, acesse o console seguindo essas etapas:

1. Go to [https://adminconsole.adobe.com/enterprise](https://adminconsole.adobe.com/enterprise/) &gt; sign in using your Adobe ID, if you have not already logged in.

   Ou

   If you are already logged in to the Experience Cloud, go to [https://www.experiencecloud.adobe.com](https://experiencecloud.adobe.com), then click the [!UICONTROL App] icon in the top navigation bar &gt; click **[!UICONTROL Admin]** on the right side.

1. (Condicional) Se tiver acesso ao [!DNL Admin Console for Enterprise] para mais de uma organização, clique no avatar do usuário no canto direito ou na barra de navegação superior e selecione a organização desejada.

## Etapa 1. Adicione usuários (Opcional) {#section_A92AF0F921B743FEB9E9033433BD816A}

Quando você começa a usar a nova funcionalidade [!UICONTROL Propriedades], todo o gerenciamento de usuário deve ser realizado no [!DNL Adobe Admin Console for Enterprise]. Entretanto, todos os seus usuários existentes no [!DNL Target] serão migrados do [!DNL Target] para o [!DNL Admin Console for Enterprise].

1. [No Admin Console](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_79796E0227D048F59BAE0AB02E544EBE), clique na guia **[!UICONTROL Usuários]** na parte superior da página &gt; **[!UICONTROL Adicionar usuários]** para criar novos usuários ou editar usuários existentes.
1. Siga as instruções em [Gerenciar usuários e grupos na Experience Cloud](https://helpx.adobe.com/enterprise/help/users.html) no *Guia do usuário da empresa*.

## Etapa 2: Crie um espaço de trabalho (Perfil do produto) {#section_B82EB409B67C4D9D9D20CE30E48DB1DC}

Um espaço de trabalho (Perfil de produto) permite que uma organização atribua um conjunto específico de usuários a um conjunto específico de propriedades. De muitas formas, um espaço de trabalho é semelhante a um conjunto de relatórios no [!DNL Analytics].

As organizações podem começar a tirar vantagem da funcionalidade de permissões empresariais criando novos espaços de trabalho dentro do Admin Console, atribuindo propriedades do Target a esses espaços de trabalho e movendo usuários da configuração "Espaço de trabalho padrão" para esses novos espaços de trabalho de acesso limitado.

Os clientes podem usar esses espaços de trabalho para separar o acesso a diferentes equipes por região, por unidade de negócios, por seção do site ou por qualquer outro método escolhido.

Os usuários podem fazer parte de vários espaços de trabalho e podem até ter diferentes funções dentro de cada um deles.

1. No Admin Console, clique em **[!UICONTROL Produtos]**, depois selecione o nome do produto desejado.

   ![espaço de trabalho](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

1. Crie o espaço de trabalho desejado (Perfil do produto):

   * **Acesso padrão:** Todas as atividades existentes serão combinadas em um único projeto chamado "Acesso padrão". Isso não terá nenhum impacto sobre os clientes. Todas as funcionalidades e funções de usuário continuarão exatamente iguais, pois são anteriores a essa alteração.

      Todas as atividades criadas por meio do [!DNL Adobe Experience Manager] (AEM), do [!DNL Adobe Mobile Services] e do [!DNL Target Classic] também farão parte do espaço de trabalho "Acesso padrão". Você não pode mover projetos de "Acesso padrão" para outro projeto atualmente.

   * **Novos espaços de trabalho (Perfis de produto):** Você pode começar a utilizar nova funcionalidade de permissões fazendo o seguinte:

      * Criar novos espaços de trabalho dentro do [!DNL Admin Console for Enterprise].
      * Atribuir propriedades do Target aos espaços de trabalho.
   Você pode usar esses espaços de trabalho para dividir o acesso a diferentes equipes por região, por unidades de negócios, por seção do site ou por qualquer outro método que você escolher. Os usuários podem fazer parte de vários espaços de trabalho e podem ter diferentes funções dentro de cada um deles.

1. Siga as instruções em [Criar e gerenciar configurações de produto](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) no *Guia do usuário da empresa*.

>[!NOTE]
>Veja o vídeo de treinamento abaixo para obter mais informações sobre como configurar espaços de trabalho.

### Obtain your Workspace ID {#workspace-id}

Você precisará passar a ID do espaço de trabalho para utilizar as Permissões empresariais nas [APIs do Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md).

1. No [Adobe Admin Console](https://adminconsole.adobe.com), clique na guia [!UICONTROL Produtos] e depois no produto, no menu esquerdo, para exibir a lista da PLC(workspace).
1. Clique na PLC(workspace) desejada e localize a ID de "perfis" no URL, como mostrado abaixo.

   ![workspaceID](/help/administrating-target/c-user-management/property-channel/assets/workspace-id-newest.png)

## Etapa 3. Criar grupos de usuários (Opcional) {#section_5F5CB9AA7A9F4D26953E22016DA59605}

É possível criar grupos de usuários, como Desenvolvedores, Analistas, Profissionais de marketing, Executivos, etc., e atribuir privilégios a vários produtos e espaços de trabalho da Adobe. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da Adobe pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

1. No Admin Console, clique na guia **[!UICONTROL Usuários]** na parte superior da página &gt; **[!UICONTROL Grupos de usuários]** para criar novos grupos de usuários ou editar grupos existentes.
1. Siga as instruções em [Gerenciar usuários e grupos de uma configuração de produto](https://helpx.adobe.com/enterprise/help/manage-products-and-configurations.html) no *Guia do usuário da empresa*.

## Etapa 4. Criar propriedades {#section_E8F2C92BE0F4466AB87604059C9CF3FD}

As propriedades são ativadas adicionando um par de nome/valor específico como um parâmetro em qualquer chamada (mbox, api, etc.) ao Target.

As propriedades pertencem a canais específicos (Web, dispositivos móveis, email e API/Outros).

**Dica**: veja o vídeo de treinamento abaixo para obter mais informações sobre como criar propriedades.

1. Em [!DNL Target], clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Propriedades]** para exibir a lista [!UICONTROL Propriedades].
1. Clique em **Criar propriedade**.

   ![Caixa de diálogo Nova propriedade](/help/administrating-target/c-user-management/property-channel/assets/new_property1.png)

   Preencha os campos:

   * **Canal:** Selecione o canal desejado para a propriedade: Web, Aplicativo móvel, Email ou Outro/API (por exemplo, uma caixa de conjunto ou um console playstation).
   * **Nome: (obrigatório):** especifique um nome descritivo para o grupo.
   * **Descrição:** especifique uma descrição opcional para a propriedade.

1. Clique em **[!UICONTROL Gerar código]** para gerar o código que você utilizará enquanto realiza as etapas em [5: Atualize sua implementação para incluir o parâmetro at_property](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_9B17A59807A94712BE642942442EBBC8).
1. Copie o código para a área de transferência.
1. Clique em **[!UICONTROL Salvar]ao concluir.**

>[!NOTE]
>Veja o vídeo de treinamento abaixo para obter mais informações sobre a criação de propriedades.

## Etapa 5: atualize sua implementação para incluir o parâmetro at_ property {#section_9B17A59807A94712BE642942442EBBC8}

Para usar a funcionalidade de permissões de usuário do [!DNL Target], você deve adicionar o parâmetro `at_property` para qualquer chamada que esteja acessando o Target (mbox, api, etc.).

**Para obter o código do parâmetro`at_property`:**

1. (Condicional) Use o código de implementação que você gerou e salvou sua área de transferência enquanto realizava as etapas em [4. Crie propriedades](../../../administrating-target/c-user-management/property-channel/properties-overview.md#section_E8F2C92BE0F4466AB87604059C9CF3FD) e prossiga para a etapa 2.

   Ou

   Em [!DNL Target], clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Propriedades]** para exibir a lista [!UICONTROL Propriedades].

   1. Passe o seu ponteiro do mouse sobre a coluna [!UICONTROL Última atualização] para a propriedade desejada ser exibida e clique no ícone do [!UICONTROL código].

      ![Código de focalização da propriedade](/help/administrating-target/c-user-management/property-channel/assets/code_property_new.png)

   1. Clique com o botão direito no código de implementação destacado para copiá-lo para sua área de transferência.

      ![Código de propriedade](/help/administrating-target/c-user-management/property-channel/assets/code_property_2_new.png)

1. Atualize sua implementação do Target com o código de implementação obtido na etapa anterior.

   Há várias maneiras de atualizar sua implementação do [!DNL Target]. Por exemplo, é possível usar os métodos a seguir em páginas da Web:

   * **Por meio de um "Parâmetro global em[!DNL Adobe Launch]:**

      For more information, see [Add Global Mbox Params](https://docs.adobelaunch.com/extension-reference/web/adobe-target-extension#add-global-mbox-params) in the *Adobe Experience Platform Launch* documentation.

   * **Por meio de um "Parâmetro global" em[!DNL Dynamic Tag Management]:**

      ![](assets/property_token_2.png)

      Para obter mais informações, consulte [Parâmetros globais - Adobe Target](https://docs.adobe.com/content/help/en/dtm/using/tools-reference/target.html#global-parameters---adobe-target) na *Documentação de produto do Dynamic Tag Management*.

   * **Pela função targetPageParams():** coloque o seguinte código no <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> tags, acima da referência de at.js ou mbox.js.

      ![](assets/property_token_1.png)

      Para obter mais informações sobre como fazer isso com o at.js, consulte [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md).

   * **Por meio da função mboxCreate():**

      ![](assets/property_token_3.png)

      Para obter mais informações sobre como fazer isso com a at.js, consulte [targetPageParams()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) e  [mboxCreate(mbox,params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md).

## Etapa 6: especificar funções e permissões {#section_8C425E43E5DD4111BBFC734A2B7ABC80}

1. No Admin Console, clique em **[!UICONTROL Produtos]**, depois selecione o nome do produto desejado.

   ![Workspace](/help/administrating-target/c-user-management/c-user-management/assets/workspace-new.png)

   >[!NOTE]
   >
   >The Properties and Permissions functionality applies to [Target Standard/Premium](/help/c-intro/intro.md#premium) only. Não é possível usar essa funcionalidade com [!DNL Target Classic].

1. Clique no nome do perfil desejado.
1. Clique em **[!UICONTROL Usuários]**.

   The [!UICONTROL Users] tab displays all of the users in that workspace.

   ![Configurar usuários](/help/administrating-target/c-user-management/property-channel/assets/configuration_users_new.png)

1. Selecione a função de permissões desejada (Aprovador, Editor, ou Observador) usando a lista suspensa para cada usuário na coluna [!UICONTROL Função do produto].

   | Função | Descrição |
   |--- |--- |
   | Observador | Pode exibir atividades, mas não pode criá-las ou editá-las. |
   | Editor | Pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
   | Aprovador | Pode criar, editar e ativar ou parar atividades. |

   Para obter mais informações, consulte [Gerenciar permissões e funções do produto no Admin Console](https://helpx.adobe.com/enterprise/help/manage-permissions-and-roles.html) no *Guia do usuário da empresa*.

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Como configurar espaços de trabalho do Target (6:55)

Este vídeo explica como criar espaços de trabalho.

* Acessar o Adobe Admin Console a partir da interface do Adobe Target (3 maneiras)
* Configure um espaço de trabalho no Adobe Admin Console

   * Adicionar usuários a espaços de trabalho
   * Adicionar propriedades aos espaços de trabalho

* Compreenda espaços de trabalho padrão

>[!VIDEO](https://video.tv.adobe.com/v/19463/?captions=por_br)

### Como criar propriedades no Adobe Target (3:05)

* Como criar uma propriedade na interface do [!DNL Adobe Target]
* Como gerar um token de propriedade para incluir na sua implementação de propriedade
* Familiarize-se com os três métodos de implementação:

   * Web
   * Aplicativo móvel
   * Email, definir caixa superior ou chamadas da API

>[!VIDEO](https://video.tv.adobe.com/v/18990/?captions=por_br)
