---
description: Informações sobre a concessão de integrações de integrações da Adobe/O a todas as áreas de trabalho com a função desejada.
keywords: integração; funções; permissões do usuário; admin console
seo-description: Informações sobre a concessão de integrações existentes da Adobe I/O a todas as áreas de trabalho com a função desejada no Adobe Target
seo-title: Conceder acesso a integrações de E/S da Adobe a espaços de trabalho e atribuir funções no Adobe Target
solution: Target
subtopic: Introdução
title: Conceder acesso a espaços de trabalho à Adobe I/O e atribuir funções
translation-type: tm+mt
source-git-commit: 13ad42da73dd3fcbf4e07be1de646e0eac8c991e

---


# ![PREMIUM](/help/assets/premium.png) concede acesso de integrações de E/S da Adobe a espaços de trabalho e atribui funções

[!UICONTROL As Permissões empresariais] permitem [!DNL Target] que os clientes usem uma única organização, mas dividam-a em espaços de trabalho para equipes ou fluxos de trabalho diferentes.

>[!NOTE]
>
>A funcionalidade Propriedades e permissões está disponível como parte da solução do [Target Premium](/help/c-intro/intro.md#premium). Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

O [!UICONTROL recurso Permissões] empresariais facilita a escala eficaz de programas de otimização em equipes. Embora o recurso esteja disponível na [!DNL Target] interface do usuário, as apis admin. ignoravam o suporte correspondente até a versão anterior em 2019. Na versão [!DNL Target] de fevereiro de 2019, a Adobe atualizou as apis de administração para que você possa usar a conta de integração para acessar todas as áreas de trabalho criadas em sua organização. Assim, enquanto anteriormente as apis de administração eram restritas somente à área de trabalho padrão, a atualização de fevereiro de 2019 concedeu acesso a todas as áreas de trabalho com [!UICONTROL acesso ao aprovador] .

Com a versão [!DNL Target] de setembro de 2019, as Permissões [!DNL Target][!UICONTROL empresariais] fornecem aos clientes os seguintes controles de acesso:

* É possível escolher as áreas de trabalho para as quais a integração pode ser aplicada
* Você pode aplicar uma função à integração da Adobe I/O: [!UICONTROL Aprovador], [!UICONTROL Editor]ou [!UICONTROL Observador].

Esta atualização oferece suporte para os seguintes casos de uso:

* Conceda acesso à integração da Adobe I/O a todas as áreas de trabalho com [!UICONTROL a] função Observador para fins de relatório sem direitos para criar ou editar recursos.
* Conceda à integração da Adobe I/O o acesso para selecionar espaços de trabalho com a função apropriada para permitir que uma equipe central faça alterações orientadas por API em apenas algumas áreas de trabalho.
* Permita que cada equipe proprietária de sua área de trabalho tenha a sua própria integração sempre que a equipe estiver pronta para explorar apis e escolher a função de acordo.
* Misture e corresponda a qualquer cenário acima.

**Ação necessária**: Os clientes que atualmente utilizam apis para operações CRUD em recursos (atividades, públicos, ofertas e relatórios) precisam conceder acesso de integração existente à Adobe I/O a todas as áreas de trabalho com a função desejada de acordo com o caso de uso. Você pode fazer isso selecionando cada [!DNL Target][!UICONTROL Perfil] de produto no [!DNL Adobe Admin Console] e adicionando as integrações na guia [!UICONTROL Integração] . Antes da versão de setembro, todas as integrações operadas usando [!UICONTROL o Aprovador] , independentemente da escolha efetuada na lista [!UICONTROL suspensa Função] do produto. Agora você pode escolher a função desejada.

>[!NOTE]
>
>Se essa ação não for executada, após a [!DNL Target] versão de setembro de 2019, os controles de acesso serão ativados e você observará o acesso somente à área de trabalho padrão se esta for a configuração atual. Não há nenhuma reação negativa à configuração de integrações antecipadamente. Quanto mais cedo você efetuar essa alteração, melhor. Dependendo do número de espaços de trabalho em sua organização, esse processo utiliza apenas alguns cliques para adicionar uma integração existente em espaços de trabalho com a função desejada.

**Para conceder acesso a integrações de E/S da Adobe a espaços de trabalho e atribuir funções:**

1. Abra o **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Clique na **[!UICONTROL guia Produtos]** e selecione o nome do produto desejado.

   ![Escolha o produto no Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Selecione a área de trabalho desejada (Perfil de produto).

   ![Selecione o perfil de produto](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Guia Integrações](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Condicional) Para adicionar uma nova integração, clique **[!UICONTROL em Adicionar integração]**, selecione a integração desejada e clique **[!UICONTROL em Salvar]**.

1. Na lista **[!UICONTROL suspensa Função]** do produto, selecione a função desejada para essa área de trabalho:

   * [!UICONTROL Aprovador]
   * [!UICONTROL Editor]
   * [!UICONTROL Observador]
   ![Escolher função do perfil do produto](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)
