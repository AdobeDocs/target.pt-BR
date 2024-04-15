---
keywords: conteúdo, ativos, administração de conteúdo, ofertas, administração de ativos, inserção do modo de seleção, modo de seleção
description: Saiba como gerenciar ofertas de código e imagem usando a biblioteca de ofertas.
title: Como gerenciar ofertas de código e imagem?
feature: Experiences and Offers
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#beta newtab=true" tooltip="O que são recursos beta no  [!DNL Adobe Target]."
hide: true
hidefromtoc: true
source-git-commit: fb6383c86503ac9a8313aed65418e9564c93aa1c
workflow-type: tm+mt
source-wordcount: '597'
ht-degree: 29%

---

# Ofertas

Use o [!UICONTROL Offers] biblioteca em [!DNL Adobe Target] para gerenciar a oferta de código e o conteúdo de oferta de imagem.

>[!NOTE]
>
>Este artigo contém informações sobre o [!DNL Target] funcionalidade que atualmente faz parte de um programa Beta. A variável [!DNL Adobe Target] A equipe do geralmente ativa novos recursos para clientes selecionados para fins de teste e feedback. Após a conclusão do período de teste, esses recursos serão habilitados para todos os clientes no futuro [!DNL Target Standard/Premium] versões e anunciadas nas notas de versão.

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

Por exemplo, o cartão de definição de oferta a seguir para uma oferta HTML é acessado ao passar o mouse sobre uma oferta no [!UICONTROL Content] e, em seguida, clicando no ícone de informações:

![imagem offer-card-html](assets/offer-card-html.png)

As informações a seguir estão disponíveis:

* Nome
* Fonte
* Tipo
* ID da oferta
* Caminho da oferta
* Última modificação

Clique em [!UICONTROL Offer Usage] para exibir as atividades que fazem referência a uma oferta de código no cartão pop-up de definição de cada oferta. Esta funcionalidade não se aplica às ofertas de imagem. Dessa forma, é possível evitar um impacto nas outras atividades ao editar as ofertas. As informações incluem [!UICONTROL Live Activities] e [!UICONTROL Inactive Activities].

![imagem offer-card-usage](assets/offer-card-usage.png)

A seguir, um cartão de definição de oferta para uma Oferta de redirecionamento:

![imagem offer-card-redirect](assets/offer-card-redirect.png)

As informações a seguir estão disponíveis:

* Nome
* Fonte
* Tipo
* ID da oferta
* Caminho da oferta
* Última modificação
* Redirecionar url
* Incluir todos os parâmetros de URL (Ligado ou Desligado)
* Envio da ID de sessão da mbox (Ativado ou Desativado)

A seguir, um cartão de definição de oferta para uma Oferta remota:

![imagem remota de cartão de oferta](assets/offer-card-remote.png)

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