---
description: Gerencie exclusões criando grupos de exclusão, excluindo ofertas duplicadas, excluindo experiências específicas e excluindo o conteúdo padrão nas atividades de Personalização automatizada (AP).
keywords: deduplicação; permitir duplicatas; excluir ofertas duplicadas; personalização automatizada; rejeitar ofertas duplicadas
seo-description: Gerencie exclusões criando grupos de exclusão, excluindo ofertas duplicadas, excluindo experiências específicas e excluindo o conteúdo padrão nas atividades de Personalização automatizada do Adobe Target (AP).
seo-title: Gerenciar exclusões
solution: Target,Analytics
title: Gerenciar exclusões
uuid: c67901d2-19cd-47d3-b8c4-abdcb046f404
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# ![Selo Premium](/help/assets/premium.png) Gerenciar exclusões{#manage-exclusions}

Gerencie exclusões criando grupos de exclusão, excluindo ofertas duplicadas, excluindo experiências específicas e excluindo o conteúdo padrão nas atividades de Personalização automatizada (AP).

## Create exclusion groups {#task_AAAA6C7239A84F7696C8492F04B575A2}

Crie grupos de exclusão em atividades de Personalização automatizada (AP) para garantir que as experiências com as ofertas designadas sejam excluídas automaticamente.

Os grupos de exclusão são uma maneira excelente de garantir que as ofertas incompatíveis não sejam apresentadas na mesma experiência em diferentes locais. Por exemplo, pressuponha que você tenha duas ofertas: uma de desconto de 20% para todas as mercadorias e outra de desconto de 15%. Você não gostaria que essas duas ofertas sejam apresentadas para os visitantes na mesma experiência. Se você adicionar essas duas ofertas a um grupo de exclusão, pode garantir que isso nunca ocorra.

Você também pode limitar quais públicos-alvo podem ver ofertas específicas nas atividades AP. For more information, see [Target Automated Personalization offers](/help/c-activities/t-automated-personalization/ap-target-offers.md).

**Para criar um grupo de exclusão:**

1. While [creating or editing an AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md), click **[!UICONTROL Manage Content]** in the header bar.

   ![Gerenciar link de conteúdo](/help/c-activities/t-automated-personalization/assets/manage-content.png)

1. Na caixa de diálogo [!UICONTROL Gerenciar conteúdo]**, clique em[!UICONTROL Grupo de exclusão]**.

   ![Caixa de diálogo Gerenciar conteúdo &gt; Grupos de exclusão](/help/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   Se você criou previamente os grupos de exclusão, eles são exibidos na lista. Se você ainda não criou um grupo de exclusão, será solicitado a criar um.

1. Clique em **[!UICONTROL Criar grupo de exclusão.]**

   ![Caixa de diálogo Criar grupo de exclusão](/help/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (Obrigatório) Especifique um nome descritivo para o grupo de exclusão.

   Um nome descritivo ajuda você e outras pessoas a localizarem e compreenderem rapidamente o propósito de um grupo.

1. Localize e selecione as ofertas desejadas que deseja adicionar ao grupo de exclusão.

   Você pode selecionar várias ofertas do mesmo local em um grupo de exclusão.

1. Clique em **[!UICONTROL Salvar]**.

As ofertas no grupo de exclusão serão automaticamente excluídas das mesmas experiência, a partir daí.

## Exclude duplicate offers {#concept_4EF78013F80E48EFA024AE0274C9F037}

Evita a duplicação das ofertas da biblioteca de ofertas, quando usadas em locais diferentes nas atividades de [!UICONTROL Personalização automatizada].

Você pode ter uma atividade, por exemplo, seis locais na página com 12 ofertas. Há uma chance de que a mesma oferta possa ser colocada em um ou mais locais na atividade. Esse recurso evita a exibição e ofertas duplicadas ao mesmo tempo em locais diferentes, dentro da mesma atividade.

Clique em **[!UICONTROL Configurar]** &gt; **[!UICONTROL Duplicar ofertas]** e clique em **[!UICONTROL Permitir duplicatas]** ou **[!UICONTROL Cancelar duplicatas]**.

![Opções de ofertas duplicadas](/help/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Exclude specific experiences {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Exclui experiências específicas se você deseja excluir determinadas combinações de ofertas na sua atividade de Personalização automatizada.

Pode haver certas combinações que não funcionam bem juntos, ou você pode limitar o número de experiências testadas para diminuir os requisitos de tráfego para sua atividade.

1. While [creating or editing an AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md), click **Manage Content** in the header bar.

   ![Gerenciar link de conteúdo](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   A lista [!UICONTROL Experiências] mostra cada experiência gerada com permutas de todas as opções de conteúdo e locais.

1. Exclua as experiências, conforme desejado.

   Você pode excluir as experiências específicas ao passar o cursor do mouse sobre a experiência desejada e clicar no ícone de exclusão.

   ![Excluir experiência ao passar o mouse](/help/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Or you can batch exclude/include experiences by selecting the checkbox for the relevant experiences and then clicking the **[UICONTROL Exclude]** icon in the top right corner of the dialog box. The [!UICONTROL Exclude] icon appears when one or more experiences are checked.

   ![Exclusão de experiências em lote](/help/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   É possível filtrar essa visualização de lista para ver apenas as atividades excluídas ou incluídas, clicando na lista suspensa [!UICONTROL Status].

   Agora, as experiências serão excluídas da atividade e seus [!UICONTROL Status] serão mostrados como [!UICONTROL Excluídos].

   ![Experiências excluídas](/help/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Exclude default content {#task_DCB4528989DF4C05A3A4729E5891D18F}

Em alguns casos, você pode não desejar incluir o conteúdo padrão como parte da sua Atividade personalizada. A maneira pela qual você acessa essa configuração é diferente da criação de grupos de exclusão. Você pode usar esse método para ter apenas uma oferta (diferente do conteúdo padrão) em um local como parte da atividade AP.

Excluir o conteúdo padrão é uma excelente forma de mudar a aparência do resto da página para ajustá-la às ofertas que você está testando com a atividade AP. Por exemplo, pressuponha que você deseja corresponder a paleta de cores das ofertas que está testando, poderia alterar a cor do fundo da sua página e excluir a cor do fundo padrão.

**Para excluir o conteúdo padrão usando o Visual Experience Composer (VEC):**

1. While [creating or editing an AP activity](/help/c-activities/t-automated-personalization/create-ap-activity.md), select the content you want to replace and click to access **[!UICONTROL Change Text/HTML]**, **[!UICONTROL Change Image]**, or **[!UICONTROL Change Background Color]**.
1. Na caixa de diálogo, crie seu novo conteúdo e desmarque **Incluir** à direita do conteúdo padrão (ou desmarque Imagem/Vídeo padrão na tela de Conteúdo selecionado).

   Dependendo do tipo de conteúdo/oferta, a caixa de seleção [!UICONTROL Incluir] fica em um local diferente.

   Para conteúdo de texto/HTML:

   ![Incluir caixa de seleção na caixa de diálogo Editar texto/HTML](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   Para conteúdo de imagem/vídeo:

   ![Incluir caixa de seleção na caixa de diálogo Selecionar conteúdo](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   Para cor do fundo:

   ![Incluir caixa de seleção na caixa de diálogo Editar cor do plano de fundo](/help/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Clique em **[!UICONTROL Salvar]**.

   Você pode visualizar as experiências criadas nas ofertas que especificou em [!UICONTROL Gerenciar conteúdo]. Você verá que nenhuma experiência é criada em [!UICONTROL Gerenciar conteúdo] usando a oferta padrão que você excluiu.

   ![](assets/exclude_content_vec_4.png)

**Para excluir o conteúdo usando o Experience Composer baseado em formulário:**

1. Ao criar ou editar uma atividade de AP, clique em **[!UICONTROL Alterar texto/HTML]** ou **[!UICONTROL Alterar oferta de imagem]** em **[!UICONTROL Conteúdo]**.
1. Na caixa de diálogo, crie seu novo conteúdo e desmarque **[!UICONTROL Incluir]à direita do conteúdo padrão (ou desmarque Imagem/Vídeo padrão na tela de Conteúdo selecionado).**

   Dependendo do tipo de conteúdo/oferta, a caixa de seleção Incluir fica em um local diferente.

   Para conteúdo de texto/HTML:

   ![](assets/exclude_content_form_1.png)

   Para conteúdo de imagem/vídeo:

   ![](assets/exclude_content_form_2.png)

1. Clique em **[!UICONTROL Salvar]**.

   Você pode visualizar as experiências criadas nas ofertas que especificou em [!UICONTROL Gerenciar conteúdo]. Você verá que nenhuma experiência é criada em [!UICONTROL Gerenciar conteúdo] usando a oferta padrão que você excluiu.

   ![](assets/exclude_content_form_3.png)
