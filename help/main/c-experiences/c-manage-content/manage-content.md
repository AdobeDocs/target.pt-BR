---
keywords: conteúdo, ativos, administração de conteúdo, ofertas, administração de ativos, inserção do modo de seleção, modo de seleção
description: Saiba como gerenciar ofertas de código e imagem usando a biblioteca de ofertas no Adobe Target.
title: Como gerenciar ofertas de código e imagem?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f93e33e91fb7be9c0d1772a2014864b46c1dfe47
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 16%

---

# Ofertas

Use o [!UICONTROL Offers] biblioteca em [!DNL Adobe Target] para gerenciar a oferta de código e o conteúdo de oferta de imagem.

1. Clique em **[!UICONTROL Offers]** para abrir a biblioteca.

   A biblioteca contém as ofertas que foram configuradas por [!DNL Target Standard/Premium] [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) e APIs. As ofertas criadas em [!DNL Target Classic] ou outras soluções são editáveis [!DNL Target Standard/Premium].

   A variável [!UICONTROL Offers] A página tem duas guias no lado direito: [!UICONTROL Code Offers] e [!UICONTROL Image Offers] que permitem exibir ofertas por tipo.

   ![Página Ofertas mostrando as guias Ofertas de código e Ofertas de imagem](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Opcional) Clique no link **[!UICONTROL Type]** lista suspensa para filtrar ofertas por tipo (HTML Offer, [Fragmentos de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Redirecionar oferta](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md), e [Pastas](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![imagem offers_filter](assets/offers_filter.png)

1. (Opcional) Clique no link **[!UICONTROL Source]** para filtrar ofertas por origem (Adobe Target, Adobe Target Classic e Adobe Experience Manager).

1. (Opcional) Execute tarefas adicionais passando o cursor do mouse sobre a oferta ou a pasta desejada no [!UICONTROL Code Offers] e, em seguida, clicando no ícone desejado.

   ![Opções de Ofertas de código](assets/offer-picker-large.png)

   As opções incluem:

   * Exibir (Para obter mais informações, consulte [Exibição de definições de oferta](#section_6B059DD121434E6292CAB393507D010E) abaixo.)
   * Editar
   * Copiar 
   * Mover (por exemplo, para mover um ou mais itens para uma pasta, clique no **[!UICONTROL Move]** para o item desejado, clique na pasta desejada e clique em **[!UICONTROL Drop]**.)
   * Excluir

   Dependendo das suas permissões, talvez você não veja ícones para todas as opções. Por exemplo, um usuário com [!UICONTROL Observer] permissões não tem os direitos para usar o [!UICONTROL Copy] opção.

   Para obter informações detalhadas sobre as tarefas que você pode executar em ofertas e pastas, consulte [Trabalhar com conteúdo na biblioteca de ativos](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Opcional) Execute tarefas adicionais passando o cursor do mouse sobre a oferta de imagem ou pasta desejada no [!UICONTROL Image Offers] e, em seguida, clicando no ícone desejado.

   ![Opções de Ofertas de imagem](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   As opções incluem:

   * Selecionar
   * Baixar
   * Propriedades da exibição
   * Editar
   * Anotar
   * Copiar 

   Para obter informações detalhadas sobre as tarefas que você pode executar em ofertas e pastas, consulte [Trabalhar com conteúdo na biblioteca de ativos](/help/main/c-experiences/c-manage-content/assets-working.md).

   >[!NOTE]
   >
   >As ofertas de imagem não fazem parte da [Permissões de usuário empresarial](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) modelo.


## Exibição de definições de oferta {#section_6B059DD121434E6292CAB393507D010E}

É possível exibir os detalhes da definição de oferta em um cartão pop-up na [!UICONTROL Offers] sem abrir a oferta.

Por exemplo, o seguinte cartão de definição de oferta para uma oferta HTML é acessado clicando no ícone de informações:

![imagem offer-card-html](assets/offer-card-html-new.png)

As informações a seguir estão disponíveis:

* Nome
* ID da oferta
* Tipo
* Última modificação

Clique em [!UICONTROL View Full Details] link para exibir o conteúdo da oferta e as atividades que fazem referência a uma oferta de código. Dessa forma, é possível evitar um impacto nas outras atividades ao editar as ofertas. As informações incluem [!UICONTROL Live Activities] e [!UICONTROL Inactive Activities].

As informações disponíveis em cada cartão variam dependendo do tipo de oferta: HTML Offer, [Fragmentos de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Redirecionar oferta](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md)ou [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md).

A funcionalidade de detalhes da oferta não se aplica a ofertas de imagem.

<!--

## Training video: The Content Repository ![Overview badge](/help/main/assets/overview.png)

This video includes information about managing offers.

* Connection between the [Experience Cloud Asset Library](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) and the Target Content Library 
* Custom HTML Offers 
* Custom HTML Offer in the [!UICONTROL Visual Experience Composer]

>[!VIDEO](https://video.tv.adobe.com/v/17387)

-->
