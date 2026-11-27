---
keywords: várias páginas; teste de jornada; atividade multipáginas
description: Saiba como criar uma atividade multipáginas no Adobe [!DNL Target] que permite criar uma história em várias páginas, com um design específico para cada página.
title: Como criar uma atividade multipáginas?
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
TQID: 'https://experienceleague.adobe.com/ZFqgbNp-sLF-ahG-uXKvWY0XPcxO0oZScGkpNX8hDHY'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c18d9e03-ac7d-4811-9c92-3e92ddc70ade
    internal-label: Mobile experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '374'
ht-degree: 13%
---
# Atividade multipáginas {#multipage-activity}

>[!BEGINSHADEBOX]

**Nesta página:** Aprenda a usar uma atividade multipáginas para criar uma história em várias páginas, com um design específico para cada página.

>[!ENDSHADEBOX]

Uma atividade multipáginas no [!DNL Adobe Target] cria uma história em várias páginas, com um design específico para cada página.

Por exemplo, uma oferta de frete gratuito com compras acima de uma determinada quantidade pode ser testada. A oferta pode aparecer na landing page, em uma página de categoria e em determinadas páginas de produto, com um tamanho diferente e em um local diferente em cada tipo de página. Uma oferta proeminente pode ser exibida na página inicial e depois reforçada com ofertas menores em outras páginas relevantes.

Uma atividade multipáginas também pode definir diferentes layouts para desktops e sites móveis não responsivos. Se o site tiver um site móvel separado, como [!DNL m.mysite.com], em vez de [!DNL `www.mysite.com`], crie uma atividade multipáginas, adicione [!DNL m.mysite.com] como páginas separadas e aplique a edição móvel para fazer as alterações apropriadas na versão da área de trabalho e na versão móvel na mesma experiência. Para sites móveis responsivos, use a [edição de experiência móvel](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md).

>[!NOTE]
>
>Atividades multipáginas são projetadas para atividades nas quais a mesma oferta tem uma aparência diferente em várias páginas. Se a oferta parecer a mesma em todas as páginas, um [teste](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages) de modelo será mais eficiente.

As regras de modelo podem ser especificadas para cada página no teste de várias páginas. Por exemplo, um teste multipáginas pode ser executado em toda a página inicial e em todas as páginas de categoria aplicando regras de modelo à página de categoria no teste multipáginas. Consulte [Incluir a mesma experiência em páginas semelhantes](/help/main/c-experiences/c-visual-experience-composer/temtest.md#similar-pages).

## Adicionar páginas a uma atividade {#add-pages}

Cada página adicionada à atividade pode ter seu próprio design da oferta.

1. Clique no ícone **[!UICONTROL Configurar]** ( ![Ícone Configurar](/help/main/assets/icons/Setting.svg) ).

1. Clique em **[!UICONTROL Adicionar mais páginas]**.

   Um painel de **[!UICONTROL Páginas]** é exibido no lado esquerdo da tela.

   ![Ícone Configurar](assets/vec_edit_4.png)

1. Especifique as páginas e defina a página padrão.

   Clique em **[!UICONTROL Adicionar página]** ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) para adicionar uma página adicional, especifique o nome e a URL da página e clique em **[!UICONTROL Salvar]**.

1. Use o [!UICONTROL Visual Experience Composer] para criar a aparência da oferta em cada página.
