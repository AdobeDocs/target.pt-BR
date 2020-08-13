---
keywords: integration;roles;user permissions;admin console
description: Informações sobre a concessão de acesso às integrações do Adobe I/O existentes para todos os espaços de trabalho com a função desejada no Adobe Target
title: Conceder acesso às integrações do Adobe I/O para espaços de trabalho e atribuir funções no Adobe Target
feature: user management
subtopic: Getting Started
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '615'
ht-degree: 88%

---


# ![PREMIUM](/help/assets/premium.png) Conceder acesso às integrações do Adobe I/O para espaços de trabalho e atribuir funções

As [!UICONTROL Permissões empresariais] possibilitam [!DNL Target] que os clientes usem uma única organização, mas a dividam em espaços de trabalho para suas diferentes equipes ou fluxos de trabalho.

>[!NOTE]
>
>A funcionalidade Propriedades e permissões está disponível como parte da solução do [Target Premium](/help/c-intro/intro.md#premium). Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

O recurso [!UICONTROL Permissões empresariais] facilita a escala eficaz de programas de otimização em equipes. Embora o recurso estivesse disponível na [!DNL Target] interface do usuário, as APIs de administrador não tinham o suporte correspondente até a versão anterior em 2019. Na versão [!DNL Target] de fevereiro de 2019, a Adobe atualizou as APIs de administrador para que você possa usar a conta de integração para acessar todos os espaços de trabalho criados em sua organização. Portanto, enquanto as APIs de administrador estavam restritas apenas ao espaço de trabalho padrão, a atualização de fevereiro de 2019 concedeu acesso a todos os espaços de trabalho com acesso de [!UICONTROL Aprovador].

With the [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] provides customers with the following access controls:

* É possível escolher os espaços de trabalho aos quais a integração pode ser aplicada
* Você pode aplicar uma função à integração do Adobe I/O: [!UICONTROL Aprovador], [!UICONTROL Editor] ou [!UICONTROL Observador].

Esta atualização oferece suporte para os seguintes casos de uso:

* Conceda acesso à integração do Adobe I/O a todas os espaços de trabalho com a função de [!UICONTROL Observador] para fins de relatório, sem direitos para criar ou editar recursos.
* Conceda acesso à integração do Adobe I/O para selecionar espaços de trabalho com a função apropriada para permitir que uma equipe central faça alterações orientadas por API em apenas alguns espaços de trabalho.
* Permita que cada equipe que possui seu espaço de trabalho tenha sua própria integração sempre que estiver pronta para explorar APIs e escolher a função de acordo.
* Misture e associe qualquer cenário acima.

**Ação necessária**: os clientes que atualmente usam APIs para operações CRUD em recursos (atividades, públicos, ofertas e relatórios) em todos os espaços de trabalho precisam conceder acesso à integração do Adobe I/O existente à para todos os espaços de trabalho com a função desejada de acordo com o caso de uso. Você pode fazer isso selecionando cada [!DNL Target] [!UICONTROL Perfil de produto] no [!DNL Adobe Admin Console] e adicionando as integrações na guia [!UICONTROL Integração]. Antes da versão de setembro, todas as integrações operavam usando o acesso de [!UICONTROL Aprovador], independentemente da escolha efetuada na lista suspensa [!UICONTROL Função do produto]. Agora você pode escolher a função desejada.

>[!NOTE]
>
>Se essa ação não for executada, após a [!DNL Target] versão de setembro de 2019, os controles de acesso serão ativados e você observará o acesso somente ao espaço de trabalho padrão, se esta for a sua configuração atual. Não há reações adversas ao configurar integrações antecipadamente. Quanto antes você efetuar essa alteração, melhor. Dependendo do número de espaços de trabalho em sua organização, esse processo leva apenas alguns cliques para adicionar uma integração existente em espaços de trabalho com a função desejada.

**Para conceder acesso às integrações do Adobe I/O para espaços de trabalho e atribuir funções:**

1. Open the **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Clique na guia **[!UICONTROL Produtos]** e selecione o nome do produto desejado.

   ![Escolha o produto no Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Selecione o espaço de trabalho desejado (Perfil do produto).

   ![Selecione o perfil do produto](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Clique na guia **[!UICONTROL Integrações]**.

   ![Guia Integrações](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Condicional) Para adicionar uma nova integração, clique em **[!UICONTROL Adicionar integração]**, selecione a integração desejada e clique em **[!UICONTROL Salvar]**.

1. Na lista suspensa **[!UICONTROL Função do produto]**, selecione a função desejada para esse espaço de trabalho:

   | Função | Descrição |
   |--- |--- |
   | Aprovador | Pode criar, editar e ativar ou parar atividades. |
   | Editor | Pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
   | Observador | Pode exibir atividades, mas não pode criá-las ou editá-las. |
   | Editor | Semelhante à função Observador (pode visualização atividades, mas não pode criá-las ou editá-las). No entanto, a função Editor tem permissão adicional para ativar o atividade. |
