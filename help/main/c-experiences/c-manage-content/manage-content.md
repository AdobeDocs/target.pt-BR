---
keywords: conteúdo, ativos, administração de conteúdo, ofertas, administração de ativos, inserção do modo de seleção, modo de seleção
description: Saiba como gerenciar ofertas de código e imagem usando a biblioteca de ofertas no Adobe Target.
title: Como gerencio ofertas de código e imagem?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 37%

---

# Ofertas

Use o [!UICONTROL Ofertas] biblioteca em [!DNL Adobe Target] para gerenciar a oferta de código e o conteúdo da oferta de imagem.

1. Clique em **[!UICONTROL Ofertas]** para abrir a biblioteca.

   A biblioteca contém as ofertas que foram configuradas por [!DNL Target Standard/Premium] [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) e APIs. As ofertas criadas em [!DNL Target Classic] ou outras soluções são editáveis [!DNL Target Standard/Premium].

   O [!UICONTROL Ofertas] tem duas guias no lado direito: [!UICONTROL Ofertas de código] e [!UICONTROL Ofertas de imagem] que permitem exibir ofertas por tipo.

   ![Página Ofertas mostrando as guias Ofertas de código e Ofertas de imagem](/help/main/c-experiences/c-manage-content/assets/offers-page.png)

1. (Opcional) Clique no botão **[!UICONTROL Tipo]** lista suspensa para filtrar ofertas por tipo (HTML Offer, [Fragmentos de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), [Oferta de redirecionamento](/help/main/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md), [Ofertas JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md)e [Pastas](/help/main/c-experiences/c-manage-content/create-content-folder.md)).

   ![](assets/offers_filter.png)

1. (Opcional) Clique no botão **[!UICONTROL Origem]** lista suspensa para filtrar ofertas por origem (Adobe Target, Adobe Target Classic e Adobe Experience Manager).

1. (Opcional) Execute tarefas adicionais passando o mouse sobre a oferta ou pasta desejada na [!UICONTROL Ofertas de código] e, em seguida, clicando no ícone desejado.

   ![Opções de ofertas de código](assets/offer-picker-large.png)

   As opções incluem:

   * Exibir (para obter mais informações, consulte [Exibição de definições de ofertas](#section_6B059DD121434E6292CAB393507D010E) abaixo.)
   * Editar
   * Copiar 
   * Mover (Por exemplo, para mover um ou mais itens para uma pasta, clique no botão **[!UICONTROL Mover]** ícone para o item desejado, clique na pasta desejada, em seguida, clique em **[!UICONTROL Largar]**.)
   * Excluir

   Dependendo das suas permissões, talvez você não veja ícones para todas as opções. Por exemplo, um usuário com [!UICONTROL Observador] permissões não tem os direitos de usar o [!UICONTROL Copiar] opção.

   Para obter informações detalhadas sobre as tarefas que você pode executar em ofertas e pastas, consulte [Trabalhar com conteúdo na biblioteca de ativos](/help/main/c-experiences/c-manage-content/assets-working.md).

1. (Opcional) Execute tarefas adicionais passando o mouse sobre a oferta ou pasta de imagem desejada na [!UICONTROL Ofertas de imagem] e, em seguida, clicando no ícone desejado.

   ![Opções de Ofertas de imagem](/help/main/c-experiences/c-manage-content/assets/image-offers-icons.png)

   As opções incluem:

   * Selecionar
   * Baixar
   * Propriedades da exibição
   * Editar
   * Anotar
   * Copiar 

   Para obter informações detalhadas sobre as tarefas que você pode executar em ofertas e pastas, consulte [Trabalhar com conteúdo na biblioteca de ativos](/help/main/c-experiences/c-manage-content/assets-working.md).

## Exibição de definições de ofertas {#section_6B059DD121434E6292CAB393507D010E}

Você pode exibir os detalhes da definição de oferta em um cartão pop-up na [!UICONTROL Ofertas] biblioteca sem abrir a oferta.

Por exemplo, o seguinte cartão de definição de oferta para uma oferta do HTML é acessado ao passar o mouse sobre uma oferta na [!UICONTROL Conteúdo] e, em seguida, clicando no ícone de informações:

![](assets/offer-card-html.png)

As informações a seguir estão disponíveis:

* Nome
* Fonte
* Tipo
* ID da oferta
* Caminho da oferta
* Última modificação

Clique na guia [!UICONTROL Utilização da oferta] para visualizar as atividades que fazem referência a uma oferta de código no cartão pop-up de definição de cada oferta. Esta funcionalidade não se aplica às ofertas de imagem. Dessa forma, é possível evitar um impacto nas outras atividades ao editar as ofertas. As informações incluem [!UICONTROL Atividades ao vivo] e [!UICONTROL Atividades inativas].

![](assets/offer-card-usage.png)

A seguir, um cartão de definição de oferta para uma Oferta de redirecionamento:

![](assets/offer-card-redirect.png)

As informações a seguir estão disponíveis:

* Nome
* Fonte
* Tipo
* ID da oferta
* Caminho da oferta
* Última modificação
* Redirecionar url
* Incluir todos os parâmetros de URL (Ligado ou Desligado)
* Envio da ID de sessão da mbox (Ativada ou Desativada)

A seguir, um cartão de definição de oferta para uma Oferta remota:

![](assets/offer-card-remote.png)

As informações a seguir estão disponíveis:

* Nome
* Fonte
* Tipo
* ID da oferta
* Caminho da oferta
* Última modificação
* Redirecionar tipo de URL
* URL absoluto ou relativo

## Vídeo de treinamento: o repositório de conteúdo ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo inclui informações sobre o gerenciamento de ofertas.

* Conexão entre a [biblioteca de ativos da Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) e a biblioteca de conteúdo do Target
* Ofertas HTML personalizadas
* Ofertas HTML personalizadas no Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)
