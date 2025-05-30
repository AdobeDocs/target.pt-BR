---
keywords: espaços de trabalho;gerenciar propriedade;permissões;configuração do produto;perfil do produto;funções;projeto;observador;editor;aprovador;editor;workspaces;manage property;permissions;product configuration;product profile;roles;project;observer;editor;approver;publisher
description: Learn how to create separate workspaces (product profiles) and then assign users different roles and permissions for individual pages, properties, or web sites.
title: What Are Enterprise User Permissions and How Do I Use Them?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 838abe87-dba7-4274-97b4-31a7905846dc
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '3165'
ht-degree: 48%

---

# Permissões de usuário empresarial

As permissões de usuários corporativos são um meio de administrar formalmente o acesso de usuários corporativos a [!DNL Adobe Target]. Adicione usuários ao [!DNL Target], atribua permissões com base em suas funções e crie espaços de trabalho para equipes com base em diferentes departamentos, localidades globais, canais e outros agrupamentos lógicos. Você pode atribuir aos usuários as funções de [!UICONTROL Observer], [!UICONTROL Editor], [!UICONTROL Approver] ou [!UICONTROL Publisher].

{{permissions-update}}

## Determine se você tem acesso a permissões de usuário do Enterprise

>[!NOTE]
>
>[!UICONTROL Properties and Permissions] functionality is available as part of the [!DNL Target] Premium solution. Elas não estão disponíveis no [!DNL Target] Standard sem uma licença do [!DNL Target] Premium.
>
>Sua implementação do [!DNL Target] pode usar qualquer versão do at.js ou [!DNL Adobe Experience Platform Web SDK].

É possível saber se sua organização tem uma licença Standard ou Premium clicando no link [!UICONTROL Administration] na parte superior da interface do usuário do [!DNL Target].

* Clientes **[!DNL Target Standard]**: se você vir a guia [!UICONTROL Users] ([!UICONTROL Administration > Users]) (e não a guia [!UICONTROL Properties]), sua organização tem uma licença [!DNL Target Standard]. [!DNL Target Standard] clientes devem seguir as instruções em [Usuários](/help/main/administrating-target/c-user-management/c-user-management/user-management.md) para adicionar usuários e atribuir permissões no [!DNL Adobe Admin Console].

* Clientes **[!DNL Target Premium]**: se você vir a guia [!UICONTROL Properties] ([!UICONTROL Administration > Properties]) e a guia [!UICONTROL Users], sua organização tem uma licença [!DNL Target Premium]. Os clientes da [!DNL Target Premium] devem seguir as instruções neste artigo e em [Configurar permissões corporativas](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

## Before you get started with enterprise permissions

>[!IMPORTANT]
>
>Ensure that you read the [Caveats](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#section_9714311B1CD9497A86F4910F8AE635E2) section below before proceeding with enterprise permissions.

## Terms and definitions used in this section {#section_F8D229544FEA41C3BC2EFD1F95AA0116}

The following terms are used throughout this section and might be new to users wanting to use the Properties and Permissions functionality in [!DNL Target] Premium.

### Propriedade

As propriedades têm natureza semelhante às propriedades em [!DNL Adobe Experience Platform], na medida em que usam um trecho de código exclusivo para diferenciá-las.

Uma propriedade da Web é uma biblioteca de regras e um código incorporado. Uma propriedade da Web pode ser qualquer agrupamento de um ou mais domínios e subdomínios.

As propriedades são habilitadas com a adição de um par nome/valor específico como parâmetro com qualquer chamada (chamada do Target, chamada da api e assim por diante) para [!DNL Target].

As propriedades pertencem a canais específicos (Web, celular, email ou API/Outros).

### Espaço de trabalho (perfil do produto) {#workspace}

Um espaço de trabalho permite que uma organização atribua um conjunto específico de usuários a um conjunto específico de propriedades. De muitas formas, um espaço de trabalho é semelhante a um conjunto de relatórios no [!DNL Adobe Analytics].

Observação: os espaços de trabalho são conhecidos como [!UICONTROL Product Profiles] no [!DNL Adobe Admin Console for Enterprise].

Se você fizer parte de uma organização multinacional, poderá ter um espaço de trabalho para suas páginas da Web, propriedades ou sites na Europa e outro espaço de trabalho para suas páginas, propriedades ou sites da Web nos EUA. Se fizer parte de uma organização multimarcas, poderá ter um espaço de trabalho separado para cada uma de suas marcas.

Os usuários podem fazer parte de vários espaços de trabalho e podem até ter diferentes funções dentro de cada um deles.

Os usuários podem ter diferentes modos de exibição do [!DNL Adobe Target] ao se moverem entre espaços de trabalho, de modo semelhante a como [!DNL Analytics] usuários têm diferentes modos de exibição do [!DNL Analytics] ao se moverem entre Conjuntos de Relatórios.

Os espaços de trabalho podem incluir públicos completamente diferentes, ofertas de código e atividades.

Todos os públicos-alvo e atividades criados antes da nova migração do modelo de Permissões empresariais são agrupados no &quot;Workspace padrão&quot;, discutido abaixo.

Todas as atividades criadas por meio do [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] e [!DNL Adobe Target Classic] fazem parte do &quot;Workspace Padrão&quot;.

### Espaço de trabalho padrão

Todos os espaços de trabalho existentes (perfis de produto) no [!DNL Admin Console] são mesclados em um único espaço de trabalho chamado &quot;Workspace padrão&quot; durante a migração de sua organização para o novo modelo de Permissões empresariais.

>[!IMPORTANT]
>
>Não exclua o Espaço de trabalho padrão.

Todas as funções de usuário e o acesso a todas as funcionalidades do [!DNL Target] permanecem inalterados como estavam antes da migração para o novo modelo de Permissões empresariais.

### Grupos de usuários

Você pode criar grupos de usuários, como desenvolvedores, analistas, profissionais de marketing e executivos. Em seguida, você pode atribuir privilégios a vários produtos e espaços de trabalho da Adobe. A atribuição de todos os privilégios apropriados a um novo membro da equipe em diferentes produtos da Adobe pode ser tão fácil quanto adicioná-lo a um grupo de usuários específico.

### Funções e permissões {#roles-permissions}

Roles and permissions determine the access levels that users have to create and manage activities in your [!DNL Target] implementation. In [!DNL Target], roles include the following:

| Função | Descrição |
|--- |--- |
| [!UICONTROL Approver] | Pode criar, editar, ativar ou parar atividades. |
| [!UICONTROL Editor] | Pode criar e editar atividades antes de serem ativadas, mas não pode aprovar a inicialização de uma atividade. |
| [!UICONTROL Observer] | Pode visualizar atividades, mas não pode criá-las ou editá-las. |
| [!UICONTROL Publisher] | Semelhante à função [!UICONTROL Observer] (pode exibir atividades, mas não pode criá-las ou editá-las). No entanto, a função [!UICONTROL Publisher] tem a permissão adicional para ativar atividades. |

### Canal

Canal refere-se ao tipo de conteúdo onde suas atividades do [!DNL Target] são entregues: páginas da Web, aplicativos móveis, mensagens de email e assim por diante.

Quando você cria uma atividade, ela é criada no espaço de trabalho selecionado no momento. Você vê as opções de seleção de canal na primeira caixa de diálogo que permite escolher o canal desejado para a atividade: Web, Aplicativo móvel, Email ou Outro/API.

## Visão geral de permissões {#section_DC2172520DA84605B218A5E9FB6D187A}

As informações a seguir explicam a forma como as permissões eram aplicadas anteriormente no [!DNL Target] e como são aplicadas usando as funcionalidades [!UICONTROL Properties] e [!UICONTROL Permissions].

A nova funcionalidade [!UICONTROL Permissions] permite criar projetos diferentes (chamados de &quot;Perfis de produto&quot; no [!DNL Adobe Admin Console for Enterprise]). Os projetos permitem atribuir permissões diferentes para um único usuário que impõem direitos de acesso para cada projeto. Esses projetos distintos podem ser comparados à maneira como os conjuntos de relatórios funcionam no [!DNL Adobe Analytics]. Cada projeto pode ter usuários específicos com funções específicas que se aplicam a um conjunto de propriedades. O resultado é que os clientes podem restringir o acesso de exibição, edição e aprovação aos usuários com base na região, no ambiente (desenvolvimento/armazenamento temporário/produção), no canal ou em outros critérios personalizados, conforme mostrado abaixo:

![imagem de permissões](assets/permissions.png)

Por exemplo, um usuário específico pode ter acesso de &quot;aprovação&quot; nos sites das Américas, mas apenas de &quot;visualização&quot; no aplicativo móvel Europeu. Esse mesmo usuário pode não ter acesso para ver as atividades oferecidas nas propriedades da Web e de dispositivos móveis na região APAC.

The [!DNL Target] [!UICONTROL Permissions] model has the following permission roles (Observer, Editor, Approver, and Observer). The Observer role is not shown in illustrations in this article.

![permissions_1 image](assets/permissions_1.png)

Cada função tem diferentes níveis de permissões:

| Função | Descrição |
|--- |--- |
| Aprovador | Pode criar, editar, ativar ou parar atividades. |
| Editor | Pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
| Observador | Pode exibir atividades, mas não pode criá-las ou editá-las. |
| Editor | Semelhante à função de Observador (pode exibir atividades, mas não pode criá-las ou editá-las). No entanto, a função Editor tem a permissão adicional para ativar atividades. |

É importante observar que a função de cada usuário se aplica a todas as páginas, propriedades ou sites da conta que incluam tags do [!DNL Target], conforme mostrado abaixo:

![permissions_2 image](assets/permissions_2.png)

The new [!DNL Target] [!UICONTROL Permissions] model has the same three permission roles (Observer, Editor, and Approver); however, you can assign a user&#39;s permissions roles separately for individual pages, properties, or sites, as shown below:

![permissions_3 image](assets/permissions_3.png)

Neste exemplo, Jan tem permissões de Aprovador para a página inicial dos EUA e o site dos EUA, bem como permissões de Observador para o site da França.

Além disso, Jan não pode ver as páginas, propriedades ou sites em [!DNL Target] para os quais não tem permissão, conforme mostrado abaixo:

![permissões_4 imagem](assets/permissions_4.png)

Neste exemplo, Jan não pode ver as páginas dos produtos, o site da Rússia e o site de carreiras.

## Cenários de caso de uso {#section_F3CE8576959E4F4CB13BEEED38311DD8}

Os seguintes casos de uso podem ser úteis para entender como as propriedades, projetos, funções e permissões podem ajudá-lo a atingir suas metas de marketing como [!DNL Target]:

### Organização multinacional

Se você fizer parte de uma organização multinacional, poderá ter um espaço de trabalho para suas páginas da Web, propriedades ou sites na Europa e outro espaço de trabalho para suas páginas, propriedades ou sites da Web nos EUA. 
Após uma reorganização, usando as pessoas das ilustrações acima, você pode configurar espaços de trabalho e permissões semelhantes aos seguintes:

* **Jan**: Jan é a responsável pela otimização no Centro de excelência das páginas, propriedades e sites dos Estados Unidos de sua organização. Ela provavelmente tem direitos de administrador do sistema na Adobe Experience Cloud.

  Em sua função, ela tem permissões de Aprovador para a página inicial dos EUA e o site dos EUA. Com a permissão do Aprovador, ela pode criar, editar e ativar ou parar atividades.

  Jan também consulta a equipe de otimização na França e, portanto, tem permissões de Observador para o site da França que lhe dão acesso somente leitura às atividades. Jan pode exibir atividades, mas não pode criá-las ou editá-las.

  Como Jan não tem nenhuma função que exija que ela veja as Páginas dos produtos, o site da Rússia ou o site de carreiras, ela não consegue ver as atividades desses sites.

* **Ernie**: Ernie é um gerente de marketing da organização responsável pelo marketing nos Estados Unidos.

  Como Ernie é relativamente novo na organização e inexperiente com o Target, ele tem permissões de editor para a página inicial dos EUA, o site dos EUA e as páginas dos produtos. Com permissões de Editor, Ernie pode criar e editar atividades antes que elas entrem ao vivo. Ele não pode aprovar a inicialização de uma atividade — alguém com permissão de Aprovação, como Jan, deve aprovar a atividade antes que ela possa ser colocada em produção.

  Como Ernie não tem nenhuma função que exija que ele veja o site da Rússia, o site da França ou o site de carreiras, ele não consegue ver as atividades desses sites.

* **Diana**: Diana agora é Analista da organização e recebeu permissões de Observador para a página inicial dos EUA, o site dos EUA, as páginas dos produtos, o site da Rússia e o site da França que lhe dão acesso somente leitura às atividades. Diana pode exibir atividades, mas não pode criá-las ou editá-las.

  Como Diana não tem nenhuma função que exija que ela veja o site de carreiras, ela não consegue ver as atividades desses sites.

### Organização multimarcas

Se você fizer parte de uma organização multimarcas, poderá ter um espaço de trabalho separado para as páginas da Web, propriedades ou sites de cada marca.

Após uma reorganização, usando as pessoas das ilustrações acima, você pode configurar projetos e permissões semelhantes aos seguintes:

* **Jan**: Jan é a Chefe de Otimização no Centro de Excelência de uma organização de cuidados de saúde que opera nos ramos de produtos hospitalares e de consumo. Ela provavelmente tem direitos de administrador do sistema na Adobe Experience Cloud.

  Em sua função, ela tem permissões de Aprovador para o site do Hospital. Com a permissão do Aprovador, ela pode criar, editar e ativar ou parar atividades.

  Jan também consulta a equipe de otimização no ramo de produtos de consumo e, portanto, tem permissões de Observador para esse site que lhe dão acesso somente leitura às atividades. Jan pode exibir atividades, mas não pode criá-las ou editá-las.

* **Ernie**: Ernie é um gerente de marketing da organização responsável pelo marketing no espaço do produto do consumidor.

  Como Ernie é relativamente novo na organização e inexperiente com o Target, ele tem permissão de Editor para o Site do consumidor. Com permissões de Editor, Ernie pode criar e editar atividades antes que elas entrem ao vivo. Ele não pode aprovar a inicialização de uma atividade — alguém com permissões de Aprovação para o Site do Consumidor, mas não Jan neste cenário, deve aprovar a atividade antes que ela possa ser colocada em produção.

  Como Ernie não tem nenhuma função que exija que ele veja o site do hospital, ele não consegue ver as atividades desse site.

* **Diana**: Diana agora é uma analista da organização e recebeu permissões de observador para o site do hospital e do consumidor que dá acesso somente leitura às atividades. Diana pode exibir atividades, mas não pode criá-las ou editá-las.

## Pontos de contato de Propriedade e Permissões da interface do usuário do Target {#section_3414371393BB42999A268628B5456EC9}

A nova funcionalidade de Permissões pode ser vista em vários locais na interface do usuário do [!DNL Target].

* Lista suspensa do **Workspace (Perfil do Produto):** A lista suspensa do Workspace é exibida na parte superior das páginas [!UICONTROL Activities], [!UICONTROL Audiences] e [!UICONTROL Offers]. Selecione o espaço de trabalho desejado para filtrar a lista e exibir somente itens no espaço de trabalho selecionado.

* **Criação da atividade:** quando você cria uma atividade, ela é criada no espaço de trabalho selecionado no momento. Você vê as opções de seleção de canal na primeira caixa de diálogo que permite escolher o canal desejado para a atividade: Web, Aplicativo móvel, Email ou Outro/API.

* **Criação de público-alvo:** Quando você cria um público-alvo, ele é criado no espaço de trabalho selecionado no momento.
* **Lista de públicos-alvo:** Você pode mover públicos-alvo entre espaços de trabalho usando a opção [!UICONTROL More Actions] > [!DNL Move] na página [!UICONTROL Audiences].
* **Criação da oferta:** quando você cria uma oferta, ela é criada no espaço de trabalho selecionado no momento.
* Página **Propriedades (Administração > Propriedades):** Você pode usar a caixa [!UICONTROL Search] para pesquisar a lista [!UICONTROL Property].

## Avisos {#section_9714311B1CD9497A86F4910F8AE635E2}

Consider the following when using or configuring properties and permissions in [!DNL Target] Premium:

* **Importante**: não exclua espaços de trabalho com atividades. Se você excluir um espaço de trabalho com atividades do, trabalhe com o Atendimento ao cliente para recuperar essas atividades.
* Ao utilizar a exibição Todos os espaços de trabalho:

   * Você pode ver atividades, públicos-alvo e ofertas de todos os espaços de trabalho que você tem as funções e permissões corretas para acessar.
   * Ao selecionar a exibição [!UICONTROL All My Workspaces], uma nova coluna é adicionada à página Atividades, Públicos-alvo e Ofertas. Essa coluna lista o espaço de trabalho do item e sua permissão de usuário associada a esse item (Observador, Editor ou Aprovador),
   * Ao criar uma atividade, público-alvo ou oferta na exibição Todos os espaços de trabalho, você deve selecionar o espaço de trabalho onde o item será criado. Somente esses espaços de trabalho podem ser selecionados para o qual você tem a permissão de Editor ou Aprovador.
   * Ao copiar uma atividade, público-alvo ou oferta na exibição Todos os espaços de trabalho, você deve selecionar o espaço de trabalho onde o item será copiado. Somente esses espaços de trabalho podem ser selecionados para o qual você tem a permissão de Editor ou Aprovador.

* Qualquer configuração nas [!UICONTROL Administration] páginas a seguir pode ser controlada por qualquer [!UICONTROL Approver] em qualquer espaço de trabalho:

   * Visual Experience Composer
   * Relatório
   * Configuração do Scene7
   * Implementação
   * Propriedades
   * Hosts
   * Ambientes
   * Tokens de resposta
   * Usuários

* Os usuários não podem mover recursos de um espaço de trabalho (perfil do produto) para outro. Entretanto, é possível copiar.
* Ao visualizar públicos-alvo da página [!DNL Audiences], ela carrega mais lentamente do que o esperado. Se você interagir com a barra de pesquisa de alguma forma, os públicos-alvo serão exibidos mais rapidamente. Esse problema é conhecido e será corrigido em uma atualização futura. Esse problema não afeta a seleção de públicos-alvo durante o fluxo de trabalho de criação de atividades.
* Os seguintes recursos fazem parte do novo modelo de Permissões empresariais:

   * Atividades, públicos-alvo e oferta de código criados em [!DNL Target Standard/Premium] estarão disponíveis para uso depois que o cliente for habilitado para permissões. (Observação: os clientes devem ter direito a [!DNL Target Premium].)
   * As propriedades podem ser adicionadas às atividades existentes no Workspace padrão; no entanto, essa abordagem está sujeita a alterações.
   * Somente os novos recursos (como atividades, ofertas de código e públicos-alvo) criados no Target Premium (após a ativação das Permissões empresariais) estão disponíveis para restringir por permissões.
   * Os recursos externos estão disponíveis somente para os usuários do Espaço de trabalho padrão. A função de um usuário no Espaço de trabalho padrão se aplica globalmente (a todas as solicitações e recursos do Target).

* Os recursos a seguir *não* fazem parte do novo modelo de Permissões empresariais:

   * Ofertas de imagem
   * Todos os recursos do Recommendations, incluindo Biblioteca de critérios, Biblioteca de design, Catálogo, Configuração de recomendações.
   * Existing resources (such as activities, code offers, and audiences) created within Target Premium before enabling Enterprise Permissions can be copied but cannot be moved to other workspaces.
   * Activities, audiences, code offers, image offers, or any other resource created using the following solutions or methods cannot be controlled by the Enterprise Permissions model, but are part of the Default Workspace: Target Classic, Adobe Experience Manager (AEM), Adobe Mobile Services, and resources created via API. Os recursos criados por meio da API incluem atividades, públicos-alvo, ofertas de código e ofertas de imagem).
   * Ofertas de imagem (os ativos armazenados em `https://[tenantName].marketing.adobe.com/content/mac/[tenantName]/target/offers.html#image-library` não podem ser controlados no momento pelo modelo de Permissões empresariais.
   * O clickTracking e os redirecionamentos funcionam quando o link ou a página de destino fazem parte de uma propriedade incluída na atividade. Além disso, clickTracking pode não funcionar ao usar a função `targetPageParams()`. A função recomendada é `targetPageParamsAll()`.

  Atualmente, o [!DNL Target] exige que um token `at_property` esteja presente nas páginas em que ocorre o rastreamento. Se o token for (1) não presente, (2) não detectado no momento da configuração da atividade (no VEC) ou (3) não passado para a chamada do Target clickTracking por meio da função `targetPageParamsAll()`, a métrica não será aumentada e exibida como &quot;0&quot;.

  O mesmo se aplica às atividades que usam redirecionamentos. A página de destino deve ter um token `at_property` e ser reconhecida no momento da configuração dentro do VEC.

  Em uma versão futura, o Target funcionará em páginas em que nenhum token `at_property` está presente ou páginas em que um token diferente de `at_property` estiver presente.

* A funcionalidade Permissões de usuário do Enterprise não é compatível com chamadas de API do Adobe Developer.

## Perguntas frequentes {#faqs}

As perguntas frequentes sobre as permissões empresariais incluem o seguinte:

### O que acontece se um usuário tiver várias funções e permissões? {#multiple-roles}

Se um usuário tiver várias funções e permissões, a função com as permissões de hirer será aplicada. Por exemplo, se um usuário tiver as funções [!UICONTROL Observer] e [!UICONTROL Approver], a função [!UICONTROL Approver] será aplicada.

### Posso mover uma atividade de um espaço de trabalho para outro?

Infelizmente, não é possível mover atividades de um espaço de trabalho para outro. No entanto, é possível copiar uma atividade para qualquer espaço de trabalho sabendo que os dados de relatórios não são transferidos. Para obter mais informações, consulte &quot;Copiando/editando uma atividade ao usar espaços de trabalho&quot; em [Copiando/editando uma atividade ao usar espaços de trabalho](/help/main/c-activities/edit-activity.md#section_45A92E1DD3934523B07E71EF90C4F8B6).

As atividades criadas antes da migração continuam sendo executadas da mesma maneira no Espaço de trabalho padrão, a menos que sejam editadas e atribuídas a propriedades. As atividades em uma propriedade de honra específica do espaço de trabalho atribuídas a esse espaço de trabalho e, portanto, o comportamento podem não permanecer o mesmo de antes da migração.

### Posso mover um público-alvo de um espaço de trabalho para outro? {#move-audience}

Sim, você pode mover públicos entre espaços de trabalho usando a opção [!UICONTROL More Actions] na página [!UICONTROL Audiences].

1. Clique no botão **[!UICONTROL More Actions]** (as três elipses) e clique em **[!UICONTROL Move]**.

   ![Mais Ações > Mover](/help/main/administrating-target/c-user-management/property-channel/assets/move-audience.png)

1. Selecione o espaço de trabalho desejado na lista suspensa **[!UICONTROL Workspace]** e clique em **[!UICONTROL Move]**.

   ![Selecione o público desejado para mover para o novo espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/assets/workspace-move.png)

>[!NOTE]
>
>Você deve ter os direitos apropriados para editar um público-alvo. In addition, the audience must not be used in other activities. Se o público-alvo estiver sendo usado em outras atividades e você ainda quiser movê-lo para outro local de trabalho, remova-o das outras atividades em que está sendo usado.

### Por que recebo uma mensagem de erro indicando que nenhuma propriedade está associada a essa atividade, mesmo que haja uma propriedade atribuída?

If you implemented [!DNL Target] with tags in [!DNL Adobe Experience Platform] and get an error message indicating that there is no property associated with the activity, pass the `at_property` parameter with the `targetPageParams` function.

### As conversões de rastreamento de cliques são registradas se uma página redirecionada e o URL da atividade pertencerem a propriedades diferentes?

O rastreamento de cliques não é registrado quando a página e o URL da atividade pertencerem a propriedades diferentes.

Considere a seguinte situação

* A página 1 pertence à Propriedade 1.
* A página 2 pertence à Propriedade 2.
* Na atividade, a Página 1 redireciona para a Página 2, que contém rastreamento de cliques.

When a visitor opens Page1 in a browser, the visitor is redirected to Page2. Como a Página 2 não está qualificada para fornecer a atividade, sua chamada do Target não terá rastreamentos de cliques na resposta.

Se a página de redirecionamento e o URL da atividade pertencerem à mesma propriedade, o rastreamento de cliques funcionará como esperado. Para obter mais informações, consulte [Rastreamento de cliques](/help/main/c-activities/r-success-metrics/click-tracking.md).

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Training Video: Enterprise Permissions Training Video ![Overview badge](/help/main/assets/overview.png)

Objetivos de aprendizagem:

* Os três níveis de função que os usuários do Adobe Target podem ter
* Os conceitos de Propriedades e Espaços de trabalho e como esses limites e agrupamentos funcionam para permitir o controle sobre os níveis de acesso dos usuários
* Exemplos de diferentes propriedades para sua organização considerar

>[!VIDEO](https://video.tv.adobe.com/v/19042/)

### Office hours: [!DNL Target] Premium Workspaces

Este vídeo é uma gravação de &quot;No expediente&quot;, uma iniciativa da equipe de Atendimento ao cliente da Adobe.

* Criação de um espaço de trabalho (perfil do produto)
* Criação de propriedades
* Adição de usuários
* Atualização da implementação

>[!NOTE]
>
>A interface do usuário de menu do [!DNL Target] [!UICONTROL Administration] (antigo [!UICONTROL Setup]) foi reprojetada para fornecer melhor desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário no produto. As informações do vídeo a seguir estão corretas; no entanto, as opções podem estar em locais um pouco diferentes.

>[!VIDEO](https://video.tv.adobe.com/v/23643/)
