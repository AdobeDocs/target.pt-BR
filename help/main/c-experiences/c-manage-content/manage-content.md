---
keywords: conteúdo, ativos, administração de conteúdo, ofertas, administração de ativos, inserção do modo de seleção, modo de seleção
description: Descubra como gerenciar ofertas de código e imagem com eficiência usando a biblioteca [!UICONTROL Offers].
title: Como gerenciar ofertas de código e imagem?
feature: Experiences and Offers
exl-id: d8c24656-64d6-4a4b-a5f2-bcde57180007
source-git-commit: f034aba7fe4f54b937dee0846140af140052694c
workflow-type: tm+mt
source-wordcount: '812'
ht-degree: 8%

---

# Ofertas

Descubra como gerenciar com eficiência as ofertas de código e imagem usando a biblioteca [!UICONTROL Offers] no [!DNL Adobe Target].

Para exibir a biblioteca [!UICONTROL Offers], clique na guia **[!UICONTROL Offers]** na parte superior da interface do usuário do [!DNL Target].

![Página de ofertas](/help/main/c-experiences/c-manage-content/assets/offers-page-new.png)

A biblioteca [!UICONTROL Offers] contém ofertas que foram configuradas via [!DNL Target Standard/Premium], [!DNL Target Classic], [!DNL Adobe Experience Manager] (AEM), [!DNL Adobe Mobile Services] (AMS) e APIs. As ofertas criadas em [!DNL Target Classic] ou outras soluções são editáveis [!DNL Target Standard/Premium].

A biblioteca [!UICONTROL Offers] fornece uma visão geral de todas as ofertas de código e imagem e permite executar várias ações:

| Elemento | Descrição |
|--- |--- |
| Painel de navegação esquerdo | Alternar entre exibir [!UICONTROL Code Offers] ou [!UICONTROL Image Offers]. |
| [!UICONTROL Show Folders] / [!UICONTROL Hide Folders]<P>![Ícone Mostrar Filtros/Ocultar Filtros](/help/main/assets/icons/RailLeft.svg) | Clique no ícone **[!UICONTROL Show Folders]** ou **[!UICONTROL Hide Folders]** para alternar entre a exibição da estrutura de pastas de ofertas ou a não exibição da estrutura de pastas.<P>Para obter mais informações, consulte [Criar pastas de ofertas](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| Ícone do [!UICONTROL Show filters]<P>![Ícone Mostrar Filtros](/help/main/assets/icons/Filter.svg) | Clique no ícone **[!UICONTROL Show filters]** para filtrar ofertas de [!UICONTROL Type], [!UICONTROL Source] e [!UICONTROL AEM Type].<P>Para obter mais informações, consulte [Aplicar filtros à lista de Ofertas](#filters) abaixo. |
| Pesquisar campos | Use os campos **[!UICONTROL Search in]** para localizar rapidamente uma oferta ou reduzir o número de ofertas exibidas na biblioteca [!UICONTROL Offers]. Você pode pesquisar por [!UICONTROL Offer Name], [!UICONTROL AEM Paths] ou [!UICONTROL AEM Tags]. As opções de pesquisa são persistentes na sessão. |
| [!UICONTROL Create Folder] | Clique em **[!UICONTROL Create Folder]** para criar pastas na biblioteca [!UICONTROL Offer] para conter ofertas de código, ofertas de imagem, bem como outras pastas para criar uma estrutura de subpastas.<P>Para obter mais informações, consulte [Criar pastas de ofertas](/help/main/c-experiences/c-manage-content/create-content-folder.md). |
| [!UICONTROL [!UICONTROL Create Offer]] | Clique em **[!UICONTROL Create Offer]** para criar uma oferta.<P>Para obter mais informações sobre como criar os vários tipos de oferta, consulte: <ul><li>Oferta HTML</li><li>[Oferta JSON](/help/main/c-experiences/c-manage-content/create-json-offer.md)</li><li>[Oferta de redirecionamento](/help/main/c-experiences/c-manage-content/offer-redirect.md)</li><li>[Oferta remota](/help/main/c-experiences/c-manage-content/about-remote-offers.md)</li></ul> |
| Caixas de seleção de operações em massa<P>![Ícone de Operações em Massa](/help/main/assets/icons/Rectangle.svg) | Clique nas caixas de seleção [!UICONTROL Bulk Operations] para executar operações em massa em todas as ofertas ou ofertas selecionadas.<P>Para obter uma lista de ações disponíveis (dependendo das suas permissões e do status da oferta), consulte [Executar ações rápidas](#quick-actions) abaixo. |
| [!UICONTROL Name] | O nome de cada oferta.<P>Clique no ícone **[!UICONTROL Quick Info]** ( ![Ícone de Informações Rápidas](/help/main/assets/icons/InfoOutline.svg) ) ao lado de cada nome de oferta para exibir mais informações sobre ela em um cartão pop-up, incluindo a ID da oferta, o tipo, a data da última modificação da oferta, por quem e muito mais.<p>Clique no ícone **[!UICONTROL More Actions]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado de cada nome de oferta para abrir um menu que permite executar ações rápidas em uma atividade. As seguintes ações estão disponíveis (dependendo das suas permissões e do status da oferta): [!UICONTROL Edit], [!UICONTROL Copy], [!UICONTROL Delete] e [!UICONTROL Move]. Para obter mais informações sobre cada ação, consulte [Executar ações rápidas](#quick-actions) abaixo.<P>Clique no cabeçalho da tabela para classificar a lista alfabeticamente em ordem crescente ou decrescente por nome. |
| [!UICONTROL Type] | O tipo de oferta: [!UICONTROL HTML Offers], [[!UICONTROL Redirect Offers]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offers]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) e [[!UICONTROL JSON Offers]](/help/main/c-experiences/c-manage-content/create-json-offer.md). |
| [!UICONTROL Source] | Mostra onde a oferta foi criada: [!DNL Adobe Target], [!DNL Adobe Target Classic] e [!DNL Adobe Experience Manager]. |
| [!UICONTROL Last updated] | Exibe a data e a hora em que a oferta foi modificada pela última vez e por quem.<P>Clique no cabeçalho da tabela para classificar a lista em ordem crescente ou decrescente por data. |

## Aplicar filtros à biblioteca de ofertas {#filters}

Clique no ícone **[!UICONTROL Show filters]** ( ![Ícone Mostrar Filtros na página Ofertas](/help/main/assets/icons/Filter.svg)) para filtrar ofertas por [!UICONTROL Type], [!UICONTROL Source] e [!UICONTROL AEM Type].

O ícone **[!UICONTROL Show filters]** permite filtrar ofertas pelas seguintes categorias:

* **[!UICONTROL Type]**: [!UICONTROL HTML Offer], [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md) e [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md).

* **[!UICONTROL Source]**: [!DNL Adobe Target], [!DNL Adobe Target Classic] e [!DNL Adobe Experience Manager].

* **Tipo de AEM**: [Fragmentos de conteúdo](/help/main/c-integrating-target-with-mac/aem/content-fragments-aem.md) e [Fragmentos de experiência](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md). Para obter mais informações sobre os diferentes tipos de fragmento, consulte a [visão geral dos Fragmentos de experiência e Fragmentos de conteúdo do AEM](/help/main/c-integrating-target-with-mac/aem/aem-experience-and-content-fragments.md).

Os filtros são persistentes na sessão.

## Executar ações rápidas {#quick-actions}

Você pode executar as seguintes ações rápidas clicando no ícone apropriado:

### Informações rápidas

Clique no ícone **[!UICONTROL Quick Info]** ( ![Ícone de Informações Rápidas](/help/main/assets/icons/InfoOutline.svg) ) ao lado de cada nome de oferta para exibir mais informações sobre ela em um cartão pop-up, incluindo a ID da oferta, o tipo, a data da última modificação da oferta, por quem e muito mais. As opções disponíveis dependem do tipo de oferta: [!UICONTROL HTML Offer], [[!UICONTROL JSON Offer]](/help/main/c-experiences/c-manage-content/create-json-offer.md), [[!UICONTROL Redirect Offer]](/help/main/c-experiences/c-manage-content/offer-redirect.md), [[!UICONTROL Remote Offer]](/help/main/c-experiences/c-manage-content/about-remote-offers.md).

### Mais ações

As ações disponíveis para [!UICONTROL Code Offers] e para [!UICONTROL Image Offers] são ligeiramente diferentes. As seguintes seções contêm mais informações:

#### [!UICONTROL Code Offer] opções

Clique no ícone **[!UICONTROL More actions]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado de cada nome de oferta para abrir um menu que permite executar ações rápidas em uma atividade.

As seguintes ações estão disponíveis (dependendo das suas permissões e do status da oferta):

* [!UICONTROL Edit]
* [!UICONTROL Copy]
* [!UICONTROL Delete]
* [!UICONTROL Move] (Por exemplo, para mover um ou mais itens para uma pasta, clique em **[!UICONTROL Move]** próximo ao item desejado, clique na pasta desejada e em **[!UICONTROL Move]**.)

Dependendo das suas permissões, talvez você não veja ícones para todas as opções. Por exemplo, um usuário com permissões [!UICONTROL Observer] não tem direitos para usar a opção [!UICONTROL Copy].

Para obter informações detalhadas sobre as tarefas que você pode executar em ofertas e pastas, consulte [Trabalhar com conteúdo na biblioteca de Ativos](/help/main/c-experiences/c-manage-content/assets-working.md).

#### [!UICONTROL Image Offer] opções

Execute tarefas adicionais passando o cursor do mouse sobre a oferta de imagem ou pasta desejada na guia [!UICONTROL Image Offers] e clicando no ícone desejado.

As opções incluem:

* [!UICONTROL Select]
* [!UICONTROL Download]
* [!UICONTROL View Properties]
* [!UICONTROL More Actions]
* [!UICONTROL Edit]
* [!UICONTROL Annotate]
* [!UICONTROL Copy]

Para obter informações detalhadas sobre as tarefas que você pode executar em ofertas e pastas, consulte [Trabalhar com conteúdo na biblioteca de Ativos](/help/main/c-experiences/c-manage-content/assets-working.md).

>[!NOTE]
>
>As ofertas de imagem não fazem parte do modelo [Permissões de Usuário Corporativo](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

## Exibição de definições de oferta {#section_6B059DD121434E6292CAB393507D010E}

Para exibir os detalhes da definição de oferta em um cartão pop-up na biblioteca [!UICONTROL Offers] sem abrir a oferta, clique no ( ![ícone Informações Rápidas](/help/main/assets/icons/InfoOutline.svg) ).

As informações a seguir estão disponíveis:

* [!UICONTROL Name]
* [!UICONTROL Offer ID]
* [!UICONTROL Type]
* [!UICONTROL Last Modified]

Clique no link [!UICONTROL View Full Details] para exibir os atributos e as atividades da oferta que fazem referência a uma oferta de código no cartão pop-up de definição de cada oferta. Esta funcionalidade não se aplica às ofertas de imagem. Dessa forma, é possível evitar um impacto nas outras atividades ao editar as ofertas. As informações incluem detalhes de [!UICONTROL Live Activities] e [!UICONTROL Inactive Activities].
