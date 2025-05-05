---
keywords: integração; funções; permissões do usuário; admin console
description: Saiba como conceder acesso às integrações de Adobe I/O existentes para todos os espaços de trabalho com a função desejada no Adobe Target.
title: Como Conceder Acesso ao Adobe I/O para Espaços de Trabalho e Atribuir Funções?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Administration & Configuration
role: Admin
exl-id: 62f6399f-c590-470c-ac3b-e0c84db63112
source-git-commit: fa11f93058b69e5e59e0ee20c65cffa4a1344ca0
workflow-type: tm+mt
source-wordcount: '610'
ht-degree: 59%

---

# Conceder acesso às integrações do Adobe I/O para espaços de trabalho e atribuir funções

O [!UICONTROL Enterprise Permissions] permite que clientes do [!DNL Target] usem uma única organização, mas a dividam em espaços de trabalho para suas diferentes equipes ou fluxos de trabalho.

>[!NOTE]
>
>A funcionalidade Propriedades e permissões está disponível como parte da solução do [Target Premium](/help/main/c-intro/intro.md#premium). Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

O recurso [!UICONTROL Enterprise Permissions] facilita a escala eficaz de programas de otimização em equipes. Embora o recurso estivesse disponível na [!DNL Target] interface do usuário, as APIs de administrador não tinham o suporte correspondente até a versão anterior em 2019. Na versão [!DNL Target] de fevereiro de 2019, a Adobe atualizou as APIs de administrador para que você possa usar a conta de integração para acessar todos os espaços de trabalho criados em sua organização. Portanto, enquanto as APIs de administrador estavam restritas apenas ao espaço de trabalho padrão, a atualização de fevereiro de 2019 concedeu acesso a todos os espaços de trabalho com acesso [!UICONTROL Approver].

Com a versão [!DNL Target] de setembro de 2019, o [!DNL Target] [!UICONTROL Enterprise Permissions] fornece aos clientes os seguintes controles de acesso:

* É possível escolher os espaços de trabalho aos quais a integração pode ser aplicada
* Você pode aplicar uma função à integração de Adobe I/O: [!UICONTROL Approver], [!UICONTROL Editor] ou [!UICONTROL Observer].

Esta atualização oferece suporte para os seguintes casos de uso:

* Conceda acesso à integração de Adobe I/O a todos os espaços de trabalho com a função [!UICONTROL Observer] para fins de relatório, sem direitos para criar ou editar recursos.
* Conceda acesso à integração do Adobe I/O para selecionar espaços de trabalho com a função apropriada para permitir que uma equipe central faça alterações orientadas por API em apenas alguns espaços de trabalho.
* Permita que cada equipe que possui seu espaço de trabalho tenha sua própria integração sempre que estiver pronta para explorar APIs e escolher a função de acordo.
* Misture e associe qualquer cenário acima.

**Ação necessária**: os clientes que atualmente usam APIs para operações CRUD em recursos (atividades, públicos, ofertas e relatórios) em todos os espaços de trabalho precisam conceder acesso à integração do Adobe I/O existente à para todos os espaços de trabalho com a função desejada de acordo com o caso de uso. Você pode fazer isso selecionando cada [!DNL Target] [!UICONTROL Product Profile] em [!DNL Adobe Admin Console] e adicionando as integrações na guia [!UICONTROL Integration]. Antes da versão de setembro, todas as integrações operavam usando o acesso [!UICONTROL Approver], independentemente da escolha efetuada na lista suspensa [!UICONTROL Product Role]. Agora você pode escolher a função desejada.

>[!NOTE]
>
>Se essa ação não for executada, após a [!DNL Target] versão de setembro de 2019, os controles de acesso serão ativados e você observará o acesso somente ao espaço de trabalho padrão, se esta for a sua configuração atual. Não há reações adversas ao configurar integrações antecipadamente. Quanto antes você efetuar essa alteração, melhor. Dependendo do número de espaços de trabalho na organização, esse processo utiliza apenas alguns cliques para adicionar uma integração existente em espaços de trabalho com a função desejada.

**Para conceder acesso às integrações do Adobe I/O para espaços de trabalho e atribuir funções:**

1. Abra o **[Adobe Admin Console](https://adminconsole.adobe.com)**.

1. Clique na guia **[!UICONTROL Products]** e selecione o nome do produto desejado.

   ![Escolha o produto no Adobe Admin Console](/help/main/administrating-target/c-user-management/property-channel/assets/io-choose-product.png)

1. Selecione o espaço de trabalho desejado (Perfil do produto).

   ![Selecione o perfil do produto](/help/main/administrating-target/c-user-management/property-channel/assets/io-select-product-profile.png)

1. Clique na guia **[!UICONTROL Integrations]**.

   ![Guia Integrações](/help/main/administrating-target/c-user-management/property-channel/assets/integrations-tab.png)

1. (Condicional) Para adicionar uma nova integração, clique em **[!UICONTROL Add Integration]**, selecione a integração desejada e clique em **[!UICONTROL Save]**.

1. Na lista suspensa **[!UICONTROL Product Role]**, selecione a função desejada para esse espaço de trabalho:

   | Função | Descrição |
   |--- |--- |
   | Aprovador | Pode criar, editar, ativar ou parar atividades. |
   | Editor | Pode criar e editar atividades antes que elas entrem ao vivo, mas não pode aprovar a inicialização de uma atividade. |
   | Observador | Pode exibir atividades, mas não pode criá-las ou editá-las. |
   | Editor | Semelhante à função de Observador (pode exibir atividades, mas não pode criá-las ou editá-las). No entanto, a função Editor tem a permissão adicional para ativar atividades. |
