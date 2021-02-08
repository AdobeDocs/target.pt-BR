---
keywords: conteúdo, ativos, administração de conteúdo, ofertas, administração de ativos, inserção do modo de seleção, modo de seleção
description: Saiba como gerenciar ofertas de código e imagem usando a biblioteca do Oferta no Adobe Target.
title: Como gerenciar Ofertas de código e imagem?
feature: Experiences and Offers
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 37%

---


# Ofertas

Use a biblioteca [!UICONTROL Oferta] em [!DNL Adobe Target] para gerenciar a oferta do código e o conteúdo da oferta da imagem.

1. Clique em **[!UICONTROL Ofertas]** para abrir a biblioteca.

   A biblioteca contém as ofertas que foram configuradas por [!DNL Target Standard/Premium] [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) e APIs. As ofertas criadas em [!DNL Target Classic] ou outras soluções são editáveis [!DNL Target Standard/Premium].

   A página [!UICONTROL Oferta] tem duas guias no lado direito: [!UICONTROL Ofertas de código] e [!UICONTROL Ofertas de imagem] que permitem visualização ofertas por tipo.

   ![Página ofertas mostrando as guias Ofertas de código e Ofertas de imagem](/help/c-experiences/c-manage-content/assets/offers-page.png)

1. (Opcional) Clique na lista suspensa **[!UICONTROL Tipo]** para filtrar ofertas por tipo (Oferta HTML, [Fragmentos de experiência](/help/c-experiences/c-manage-content/aem-experience-fragments.md), [Redirecionar Oferta](/help/c-experiences/c-manage-content/offer-redirect.md), [Oferta remota](/help/c-experiences/c-manage-content/about-remote-offers.md), [Ofertas JSON](/help/c-experiences/c-manage-content/create-json-offer.md) e [Pastas](/help/c-experiences/c-manage-content/create-content-folder.md)).

   ![](assets/offers_filter.png)

1. (Opcional) Clique na lista suspensa **[!UICONTROL Origem]** para filtrar ofertas por origem (Adobe Target, Adobe Target Classic e Adobe Experience Manager).

1. (Opcional) Execute tarefas adicionais passando o mouse sobre a oferta ou pasta desejada na guia [!UICONTROL Ofertas de código] e, em seguida, clicando no ícone desejado.

   ![Opções de ofertas de código](assets/offer-picker-large.png)

   As opções incluem:

   * Visualização (para obter mais informações, consulte [Visualizando definições de oferta](#section_6B059DD121434E6292CAB393507D010E) abaixo.)
   * Editar
   * Copiar 
   * Mover (Por exemplo, para mover um ou mais itens para uma pasta, clique no ícone **[!UICONTROL Mover]** para o item desejado, clique na pasta desejada e, em seguida, clique em **[!UICONTROL Soltar]**.)
   * Excluir

   Dependendo das suas permissões, talvez você não veja ícones para todas as opções. Por exemplo, um usuário com permissões [!UICONTROL Observer] não tem direitos para usar a opção [!UICONTROL Copiar].

   Para obter informações detalhadas sobre as tarefas que você pode executar em ofertas e pastas, consulte [Trabalhar com conteúdo na biblioteca de ativos](/help/c-experiences/c-manage-content/assets-working.md).

1. (Opcional) Execute tarefas adicionais passando o mouse sobre a oferta ou pasta de imagem desejada na guia [!UICONTROL Ofertas de imagem] e, em seguida, clicando no ícone desejado.

   ![Opções de Ofertas de imagem](/help/c-experiences/c-manage-content/assets/image-offers-icons.png)

   As opções incluem:

   * Selecionar
   * Baixar
   * Propriedades da exibição
   * Editar
   * Anotar
   * Copiar 

   Para obter informações detalhadas sobre as tarefas que você pode executar em ofertas e pastas, consulte [Trabalhar com conteúdo na biblioteca de ativos](/help/c-experiences/c-manage-content/assets-working.md).

## Exibindo definições de oferta {#section_6B059DD121434E6292CAB393507D010E}

Você pode visualização detalhes de definição de oferta em um cartão pop-up na biblioteca [!UICONTROL Oferta] sem abrir a oferta.

Por exemplo, o seguinte cartão de definição de oferta para uma oferta HTML é acessado passando o mouse sobre uma oferta na lista [!UICONTROL Content] e, em seguida, clicando no ícone de informações:

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
* Enviar ID de sessão mbox (Ligado ou Desligado)

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

## Vídeo de treinamento: o repositório de conteúdo  ![Etiqueta de visão geral](/help/assets/overview.png)

Este vídeo inclui informações sobre o gerenciamento de ofertas.

* Conexão entre a [biblioteca de ativos da Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) e a biblioteca de conteúdo do Target
* Ofertas HTML personalizadas
* Ofertas HTML personalizadas no Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)