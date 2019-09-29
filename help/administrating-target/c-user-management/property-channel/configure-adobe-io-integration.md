---
description: Informações sobre como conceder acesso às integrações de E/S da Adobe a todos os espaços de trabalho com a função desejada.
keywords: integração;funções;permissões de usuário;console de administração
seo-description: Informações sobre como conceder acesso às integrações de E/S existentes da Adobe a todos os espaços de trabalho com a função desejada no Adobe Target
seo-title: Conceder acesso às áreas de trabalho às integrações de E/S da Adobe e atribuir funções no Adobe Target
solution: Target
subtopic: Introdução
title: Conceder acesso às integrações de E/S da Adobe para espaços de trabalho e atribuir funções
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) Conceda acesso de integração de E/S da Adobe a espaços de trabalho e atribua funções

[!UICONTROL As Permissões] Enterprise permitem que [!DNL Target] os clientes usem uma única organização, mas as dividam em espaços de trabalho para equipes ou fluxos de trabalho diferentes.

>[!NOTE]
>
>A funcionalidade Propriedades e permissões está disponível como parte da solução do [Target Premium](/help/c-intro/intro.md#premium). Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

O recurso Permissões  corporativas facilita o dimensionamento efetivo de programas de otimização entre equipes. Embora o recurso estivesse disponível na [!DNL Target] interface do usuário, as APIs administrativas não tinham o suporte correspondente até o início de 2019. Na versão [!DNL Target] de fevereiro de 2019, a Adobe atualizou as APIs de administração para que você possa usar a conta de integração para acessar todos os espaços de trabalho criados em sua organização. Assim, embora anteriormente, as APIs administrativas eram restritas apenas ao espaço de trabalho padrão, a atualização de fevereiro de 2019 concedeu acesso a todos os espaços de trabalho com acesso ao [!UICONTROL Aprovador] .

Com a versão [!DNL Target] de setembro de 2019, as Permissões [!DNL Target] para  empresas fornecem aos clientes os seguintes controles de acesso:

* Você pode escolher os espaços de trabalho aos quais a integração pode ser aplicada
* Você pode aplicar uma função à integração de E/S da Adobe: [!UICONTROL Aprovador], [!UICONTROL Editor]ou [!UICONTROL Observador].

Esta atualização suporta os seguintes casos de uso:

* Conceda à integração de E/S da Adobe acesso a todos os espaços de trabalho com a função de [!UICONTROL Observador] para fins de relatório sem direitos para criar ou editar recursos.
* Conceda à integração de E/S da Adobe o acesso a espaços de trabalho selecionados com a função apropriada para permitir que uma equipe central faça alterações orientadas por API em apenas alguns espaços de trabalho.
* Permitir que cada equipe proprietária de seu espaço de trabalho tenha sua própria integração sempre que a equipe estiver pronta para explorar APIs e escolher a função de acordo.
* Combine qualquer um dos cenários acima.

**Ação Necessária**: Os clientes que atualmente estão aproveitando as APIs para operações CRUD em recursos (atividades, públicos-alvo, ofertas e relatórios) em todos os espaços de trabalho precisam conceder acesso à integração de E/S existente da Adobe a todos os espaços de trabalho com a função desejada conforme o caso de uso. Para fazer isso, selecione cada Perfil [!DNL Target] de [!UICONTROL produto no] e adicione as integrações na guia [!DNL Adobe Admin Console] Integração  . Antes da versão de setembro, todas as integrações operavam usando o acesso do [!UICONTROL Aprovador] , independentemente da escolha feita na lista suspensa Função [!UICONTROL do] produto. Agora você pode escolher a função desejada.

>[!NOTE]
>
>Se essa ação não for executada, após a versão de setembro de 2019, os controles de acesso serão ativados e você observará o acesso apenas ao espaço de trabalho padrão se for assim que você estiver configurado no momento. [!DNL Target] Não há qualquer reação adversa ao estabelecimento prévio de integrações. Quanto mais cedo fizeres esta mudança, melhor. Dependendo do número de espaços de trabalho em sua organização, esse processo leva apenas alguns cliques para adicionar uma integração existente em espaços de trabalho com a função desejada.

**Para conceder acesso às integrações de E/S da Adobe aos espaços de trabalho e atribuir funções:**

1. Abra o **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Clique na guia **[!UICONTROL Produtos]** e selecione o nome do produto desejado.

   ![Escolha o produto no Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Selecione o espaço de trabalho desejado (Perfil do produto).

   ![Selecione o perfil do produto](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Guia Integrações](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Condicional) Para adicionar uma nova integração, clique em **[!UICONTROL Adicionar integração]**, selecione a integração desejada e clique em **[!UICONTROL Salvar]**.

1. Na lista suspensa Função **[!UICONTROL do]** produto, selecione a função desejada para esse espaço de trabalho:

   * [!UICONTROL Aprovador]
   * [!UICONTROL Editor]
   * [!UICONTROL Observador]
   ![Escolha a função Perfil do Produto](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
