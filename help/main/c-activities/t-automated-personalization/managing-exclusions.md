---
keywords: deduplicação;permitir duplicatas;excluir ofertas duplicadas;personalização automatizada;não permitir ofertas duplicadas;excluir;conteúdo padrão;grupo de exclusão;
description: Gerenciar exclusões no [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) atividades. Crie grupos de exclusão e exclua ofertas duplicadas, experiências específicas e conteúdo padrão.
title: Como gerenciar exclusões no [!UICONTROL Automated Personalization] Atividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
solution: Target,Analytics
exl-id: d9e9f2a2-5914-4b81-acae-eaf388646652
source-git-commit: b5f06878a6ca8b4c571bfe05a52bfb3f471a697e
workflow-type: tm+mt
source-wordcount: '1011'
ht-degree: 58%

---

# Gerenciar exclusões

Gerencie exclusões criando grupos de exclusão e excluindo ofertas duplicadas, experiências específicas e o conteúdo padrão no [!UICONTROL Automated Personalization] (AP) atividades no [!DNL Adobe Target].

## Criar grupos de exclusão {#task_AAAA6C7239A84F7696C8492F04B575A2}

Criar grupos de exclusão no [!UICONTROL Automated Personalization] (AP) Atividades para garantir que as experiências com as ofertas designadas sejam excluídas automaticamente.

Os grupos de exclusão são uma maneira excelente de garantir que as ofertas incompatíveis não sejam apresentadas na mesma experiência em diferentes locais. Por exemplo, suponha que você tenha duas ofertas: uma é para um desconto de 20% para todas as mercadorias e a outra é para um desconto de 15%. Você nunca quer que essas duas ofertas sejam apresentadas aos visitantes na mesma experiência. Se você adicionar essas duas ofertas a um grupo de exclusão, poderá garantir que essa situação nunca seja o caso.

Você também pode limitar quais públicos-alvo podem ver as ofertas específicas nas atividades de AP. Para obter mais informações, consulte [Ofertas de Personalização automatizada do Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).

**Para criar um grupo de exclusão:**

1. Ao [criar ou editar uma atividade de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), clique em **[!UICONTROL Gerenciar conteúdo]** na barra de cabeçalho.

   ![Link Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

1. No [!UICONTROL Gerenciar conteúdo] , clique em **[!UICONTROL Grupos de exclusão]**.

   ![Caixa de diálogo Gerenciar conteúdo > Grupos de exclusão](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create-new.png)

   Se você criou previamente os grupos de exclusão, eles são exibidos na lista. Se você ainda não criou um grupo de exclusão, será solicitado a criar um.

1. Clique em **[!UICONTROL Criar grupo de exclusão.]**

   ![Caixa de diálogo Criar grupo de exclusão](/help/main/c-activities/t-automated-personalization/assets/exclusion_group_create_dialog-new.png)

1. (Obrigatório) Especifique um nome descritivo para o grupo de exclusão.

   Um nome descritivo ajuda você e outras pessoas a localizarem e compreenderem rapidamente o propósito de um grupo.

1. Localize e selecione as ofertas desejadas que deseja adicionar ao grupo de exclusão.

   Você pode selecionar várias ofertas do mesmo local em um grupo de exclusão.

1. Clique em **[!UICONTROL Salvar]**.

As ofertas no grupo de exclusão são excluídas automaticamente das mesmas experiências a partir de agora.

## Excluir ofertas duplicadas {#concept_4EF78013F80E48EFA024AE0274C9F037}

Evita a duplicação das ofertas da biblioteca de ofertas, quando usadas em locais diferentes nas atividades de [!UICONTROL Personalização automatizada].

Você pode ter uma atividade, por exemplo, seis locais na página com 12 ofertas. Há uma chance de que a mesma oferta possa ser colocada em um ou mais locais na atividade. Esse recurso evita a exibição e ofertas duplicadas ao mesmo tempo em locais diferentes, dentro da mesma atividade.

Clique em **[!UICONTROL Configurar]** opção de engrenagem > **[!UICONTROL Ofertas duplicadas]** e, em seguida, clique em **[!UICONTROL Permitir duplicados]** ou **[!UICONTROL Não permitir duplicados]**.

![Opções de ofertas duplicadas](/help/main/c-activities/t-automated-personalization/assets/duplicate_offers-new.png)

## Excluir experiências especificas {#task_C17D36EF58AF4908B17A3D84CA6DE85A}

Exclua experiências específicas se quiser excluir determinadas combinações de ofertas da [!UICONTROL Automated Personalization] atividade.

Pode haver determinadas combinações que não funcionam juntas ou você pode estar limitando o número de experiências testadas para diminuir os requisitos de tráfego para sua atividade.

1. Ao [criar ou editar uma atividade de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), clique em **Gerenciar conteúdo** na barra de cabeçalho.

   ![Link Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   A lista [!UICONTROL Experiências] mostra cada experiência gerada com permutas de todas as opções de conteúdo e locais.

1. Exclua as experiências, conforme desejado.

   Você pode excluir as experiências específicas ao passar o cursor do mouse sobre a experiência desejada e clicar no ícone de exclusão.

   ![Excluir experiência ao passar o cursor do mouse](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_1a.png)

   Ou você pode excluir em lote as experiências marcando a caixa de seleção das experiências relevantes e, em seguida, clicando no **[!UICONTROL Excluir]** no canto superior direito da caixa de diálogo. A variável [!UICONTROL Excluir] O ícone é exibido quando uma ou mais experiências são marcadas.

   ![Exclusão em lote de experiências](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_2a.png)

   É possível filtrar essa exibição de lista para ver apenas as atividades excluídas ou incluídas, clicando na lista suspensa [!UICONTROL Status].

   As experiências agora são excluídas da atividade e suas [!UICONTROL Status] mostrar como [!UICONTROL Excluído].

   ![Experiências excluídas](/help/main/c-activities/t-automated-personalization/assets/exclude_exp_3a.png)

## Excluir conteúdo padrão {#task_DCB4528989DF4C05A3A4729E5891D18F}

Às vezes, você pode não querer incluir seu conteúdo padrão como parte de sua [!UICONTROL Automated Personalization] atividade. A maneira pela qual você acessa essa configuração é diferente da criação de grupos de exclusão. Você pode usar esse método para ter somente uma oferta (diferente do conteúdo padrão) em uma localização, como parte da sua atividade de AP.

Excluir o conteúdo padrão é uma excelente maneira de alterar a aparência do restante da página, a fim de adequar as ofertas que você estiver testando com a atividade de AP. Por exemplo, pressuponha que você deseja corresponder a paleta de cores das ofertas que está testando, poderia alterar a cor do fundo da sua página e excluir a cor do fundo padrão.

**Para excluir o conteúdo padrão usando o Visual Experience Composer (VEC):**

1. Enquanto [criação ou edição de uma atividade de AP](/help/main/c-activities/t-automated-personalization/create-ap-activity.md), selecione o conteúdo que deseja substituir e clique em para acessar **[!UICONTROL Alterar texto/HTML]**, **[!UICONTROL Alterar imagem]** ou **[!UICONTROL Alterar cor de fundo]**.
1. Na caixa de diálogo, crie seu novo conteúdo e desmarque **Incluir** à direita do conteúdo padrão (ou desmarque Imagem/Vídeo padrão na tela de Conteúdo selecionado).

   Dependendo do tipo de conteúdo ou oferta, a variável [!UICONTROL Incluir] A caixa de seleção está em um local ligeiramente diferente.

   Para conteúdo de texto/HTML:

   ![Incluir caixa de seleção na caixa de diálogo Editar texto/HTML](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_1a.png)

   Para conteúdo de imagem/vídeo:

   ![Incluir caixa de seleção na caixa de diálogo Selecionar conteúdo](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_2a.png)

   Para cor do fundo:

   ![Incluir caixa de seleção na caixa de diálogo Editar cor do fundo](/help/main/c-activities/t-automated-personalization/assets/exclude_content_vec_3a.png)

1. Clique em **[!UICONTROL Salvar]**.

   Você pode visualizar as experiências criadas nas ofertas que especificou em [!UICONTROL Gerenciar conteúdo]. Você percebe que nenhuma experiência é criada no [!UICONTROL Gerenciar conteúdo] usando a oferta padrão excluída.

   ![imagem exclude_content_vec_4](assets/exclude_content_vec_4.png)

**[!UICONTROL Para excluir o conteúdo usando o Experience Composer baseado em formulário]:**

1. Ao criar ou editar uma atividade de AP, clique em **[!UICONTROL Alterar texto/HTML]** ou **[!UICONTROL Alterar oferta de imagem]** em **[!UICONTROL Conteúdo]**.
1. Na caixa de diálogo, crie seu novo conteúdo e desmarque **[!UICONTROL Incluir]** à direita do conteúdo padrão (ou desmarque Imagem/Vídeo padrão na tela de Conteúdo selecionado).

   Dependendo do tipo de conteúdo ou oferta, a variável [!UICONTROL Incluir] A caixa de seleção está em um local ligeiramente diferente.

   Para conteúdo de texto/HTML:

   ![imagem exclude_content_form_1](assets/exclude_content_form_1.png)

   Para conteúdo de imagem/vídeo:

   ![imagem exclude_content_form_2](assets/exclude_content_form_2.png)

1. Clique em **[!UICONTROL Salvar]**.

   Você pode visualizar as experiências criadas nas ofertas que especificou em [!UICONTROL Gerenciar conteúdo]. Você percebe que nenhuma experiência é criada no [!UICONTROL Gerenciar conteúdo] usando a oferta padrão excluída.

   ![imagem exclude_content_form_3](assets/exclude_content_form_3.png)
