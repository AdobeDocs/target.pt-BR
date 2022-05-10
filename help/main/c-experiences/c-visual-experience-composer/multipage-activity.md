---
keywords: várias páginas; teste de jornada; atividade multipáginas
description: Saiba como criar uma atividade multipáginas no Adobe [!DNL Target] permite criar uma história em várias páginas, com um design específico para cada página.
title: Como criar uma atividade multipáginas?
feature: Visual Experience Composer (VEC)
exl-id: d000cc73-4729-4ce0-ab30-756dd3ca8545
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '377'
ht-degree: 85%

---

# Atividade multipáginas

Uma atividade multipáginas em [!DNL Adobe Target] permite criar uma história em várias páginas, com um design específico para cada página.

Por exemplo, você pode testar uma oferta de entrega gratuita para compras acima de um determinado valor. Talvez você queira que a oferta apareça na página de aterrissagem, na página de uma categoria e em algumas páginas de produtos, mas você quer em um tamanho diferente e em um local diferente em cada tipo de página. Você pode exibir uma oferta de destaque na página inicial e reforçar essa oferta com ofertas menores em outras páginas relevantes.

Você também pode usar uma atividade multipáginas para definir layouts diferentes para seus sites de desktop e de dispositivos móveis não responsivos. Se o site tiver um site móvel separado como [!DNL m.mysite.com], em vez de [!DNL `www.mysite.com`], você deve criar uma atividade [multipáginas](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md#concept_277E096063E14813AC5D8EDFA1D2ED48), adicionar [!DNL m.mysite.com] como páginas separadas e aplicar a edição móvel para fazer as alterações apropriadas na versão da área de trabalho e na versão móvel na mesma experiência. Para sites móveis responsivos, use a [edição de experiência móvel](/help/main/c-experiences/c-visual-experience-composer/mobile-viewports.md#concept_8E45527C4ABC41D59AA3553BEDC76FA5).

>[!NOTE]
>
>Atividades multipáginas são projetadas para atividades nas quais a mesma oferta tem uma aparência diferente em várias páginas. Se a oferta parecer a mesma em todas as páginas, um [teste](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781) de modelo será mais eficiente.

Você pode especificar as regras do modelo para cada página no teste de multipáginas. Por exemplo, você pode executar um teste de multipágina em toda a página inicial e em todas as páginas de categoria no teste de multipágina. Consulte [Incluir a mesma experiência em páginas semelhantes](/help/main/c-experiences/c-visual-experience-composer/temtest.md#task_2539D51A18044F82B0D9895636546781).

Para adicionar páginas a um teste:

1. Clique no ícone de engrenagem **[!UICONTROL Configurar]**.
1. Clique em **[!UICONTROL Adicionar mais páginas]**.

   Uma barra de navegação aparece à esquerda da tela.

   ![](assets/multipage_nav.png)

1. Use uma barra de navegação para especificar suas páginas e definir a página padrão.

   Clique em **[!UICONTROL Adicionar página]** para adicionar uma página adicional.

   Clique no ícone de três elipses verticais para exibir um menu de ação:

   ![](assets/multipage_menu.png)

   Use este menu para renomear as páginas, realizar um teste de redirecionamento de dentro da atividade de multipágina ou excluir a página.

1. Use o Visual Experience Composer para projetar o modo de exibição da oferta em cada página.