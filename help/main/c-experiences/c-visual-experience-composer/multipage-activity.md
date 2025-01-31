---
keywords: várias páginas; teste de jornada; atividade multipáginas
description: Saiba como criar uma atividade multipáginas no Adobe [!DNL Target] que permite criar uma história em várias páginas, com um design específico para cada página.
title: Como criar uma atividade multipáginas?
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
source-git-commit: f968ec45f015fa0b195007f5790b9efb743c8b65
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 57%

---

# Atividade multipáginas

Uma atividade multipáginas no [!DNL Adobe Target] permite criar uma história em várias páginas, com um design específico para cada página.

Por exemplo, você pode testar uma oferta de entrega gratuita para compras acima de um determinado valor. Talvez você queira que a oferta apareça na página de aterrissagem, na página de uma categoria e em algumas páginas de produtos, mas você quer em um tamanho diferente e em um local diferente em cada tipo de página. Você pode exibir uma oferta de destaque na página inicial e reforçar essa oferta com ofertas menores em outras páginas relevantes.

Você também pode usar uma atividade multipáginas para definir layouts diferentes para seus sites de desktop e de dispositivos móveis não responsivos. Se o site tiver um site móvel separado como [!DNL m.mysite.com] em vez de [!DNL `www.mysite.com`], você deve criar uma [atividade multipáginas](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48), adicionar [!DNL m.mysite.com] como páginas separadas e aplicar a edição móvel para fazer as alterações apropriadas na versão da área de trabalho e na versão móvel na mesma experiência. Para sites móveis responsivos, use a [edição de experiência móvel](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5).

>[!NOTE]
>
>Atividades multipáginas são projetadas para atividades nas quais a mesma oferta tem uma aparência diferente em várias páginas. Se a oferta parecer a mesma em todas as páginas, um [teste](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) de modelo será mais eficiente.

Você pode especificar as regras do modelo para cada página no teste de multipáginas. Por exemplo, você pode executar um teste de multipágina em toda a página inicial e em todas as páginas de categoria no teste de multipágina. Consulte [Incluir a mesma experiência em páginas semelhantes](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Para adicionar páginas a um teste:

1. Clique no ícone **[!UICONTROL Configure]** ( ![Ícone Configurar](/help/main/assets/icons/Setting.svg) ).
1. Clique em **[!UICONTROL Add Additional Pages]**.

   Um painel [!UICONTROL Pages] é exibido no lado esquerdo da tela.

1. Especifique suas páginas e defina a página padrão.

   Clique em **[!UICONTROL Add Page]** ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) para adicionar uma página adicional, especifique o nome e a URL da página e clique em **[!UICONTROL Save]**.

1. Use o [!UICONTROL Visual Experience Composer] para criar a aparência da oferta em cada página.
