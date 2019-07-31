---
description: Informações sobre a concessão de integrações existentes da Adobe I/O a todas as áreas de trabalho com a função desejada.
keywords: integração; funções; permissões do usuário; admin console
seo-description: Informações sobre a concessão de integrações existentes da Adobe I/O a todas as áreas de trabalho com a função desejada no Adobe Target
seo-title: Conceder acesso a integrações de E/S da Adobe a espaços de trabalho e atribuir funções no Adobe Target
solution: Target
subtopic: Introdução
title: Conceder acesso a espaços de trabalho à Adobe I/O e atribuir funções
translation-type: tm+mt
source-git-commit: b88460fbd90168ddc19cbae1939b47ac69a854a8

---


# ![PREMIUM](/help/assets/premium.png) concede acesso de integrações de E/S da Adobe a espaços de trabalho e atribui funções

[!UICONTROL As Permissões empresariais] permitem [!DNL Target] que os clientes usem uma única organização, mas dividam-a em espaços de trabalho para equipes ou fluxos de trabalho diferentes.

>[!NOTE]
>
>A funcionalidade Propriedades e permissões está disponível como parte da solução do [Target Premium](/help/c-intro/intro.md#premium). Eles não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

The [!UICONTROL Enterprise Permissions] feature facilitates effective scaling of optimization programs across teams. Although the feature was available in the [!DNL Target] UI, the Admin APIs lacked the corresponding support until earlier in 2019. In the [!DNL Target] February 2019 release, Adobe updated the Admin APIs so that you can use the integration account to access all workspaces created in your organization. So, while earlier, Admin APIs were restricted to just the default workspace, the February 2019 update granted access to all workspaces with [!UICONTROL Approver] access.

With the upcoming [!DNL Target] September 2019 release, [!DNL Target] [!UICONTROL Enterprise Permissions] will provide customers with the following access controls:

* É possível escolher as áreas de trabalho para as quais a integração pode ser aplicada
* You can apply a role to the Adobe I/O integration: [!UICONTROL Approver], [!UICONTROL Editor], or [!UICONTROL Observer].

Esta atualização oferece suporte para os seguintes casos de uso:

* Grant the Adobe I/O integration access to all workspaces with the [!UICONTROL Observer] role for reporting purposes with no rights to create or edit resources.
* Conceda à integração da Adobe I/O o acesso para selecionar espaços de trabalho com a função apropriada para permitir que uma equipe central faça alterações orientadas por API em apenas algumas áreas de trabalho.
* Permita que cada equipe proprietária de sua área de trabalho tenha a sua própria integração sempre que a equipe estiver pronta para explorar apis e escolher a função de acordo.
* Misture e corresponda a qualquer cenário acima.

**Ação necessária**: Os clientes que atualmente utilizam apis para operações CRUD em recursos (atividades, públicos, ofertas e relatórios) precisam conceder acesso de integração existente à Adobe I/O a todas as áreas de trabalho com a função desejada de acordo com o caso de uso. You can do so by selecting each [!DNL Target] [!UICONTROL Product Profile] in the [!DNL Adobe Admin Console] and adding the integration(s) in the [!UICONTROL Integration] tab. Prior to the September release, all integrations operated using [!UICONTROL Approver] access, regardless of choice made from the [!UICONTROL Product Role] drop-down list. Agora você pode escolher a função desejada.

This action should be performed before **September 4, 2019** to not face any disruption on your end. If this action is not performed, after the [!DNL Target] September 2019 release, the access controls will activate and you will observe access to just the default workspace if that's how you are currently set up. Não há nenhuma reação negativa à configuração de integrações antecipadamente, conforme as diretrizes acima. Quanto mais cedo você efetuar essa alteração, melhor. Pouco tempo é necessário para configurar isso, dependendo do número de espaços de trabalho em sua organização. Esse processo utiliza apenas alguns cliques para adicionar uma integração existente em espaços de trabalho com a função desejada.

**Para conceder acesso a integrações de E/S da Adobe a espaços de trabalho e atribuir funções:**

1. Open the **[!DNL[Adobe Admin Console](https://adminconsole.adobe.com)]**.

1. Click the **[!UICONTROL Products]** tab, then select the name of the desired product.

   ![Escolha o produto no Adobe Admin Console](/help/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Selecione a área de trabalho desejada (Perfil de produto).

   ![Selecione o perfil de produto](/help/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Click the **[!UICONTROL Integrations]** tab.

   ![Guia Integrações](/help/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. From the **[!UICONTROL Product Role]** drop-down list, select the desired role for that workspace:

   *[!UICONTROL Approver]
*[!UICONTROL Editor]
*[!UICONTROL Observer]

   ![Escolher função do perfil do produto](/help/administrating-target/c-user-management/property-channel/assets/product-profile-role.png)