---
keywords: biblioteca de conteúdo; ativos; anotar; copiar; excluir ativo; baixar ativo; editar conteúdo; compartilhar cartão; exibir propriedades do conteúdo
description: Saiba como gerenciar ofertas de código e imagem no Adobe [!DNL Target] Biblioteca de ofertas. Saiba como visualizar os detalhes de uma oferta e como editar, copiar, mover ou excluir ofertas.
title: Como trabalho com conteúdo na biblioteca de ofertas?
feature: Experiences and Offers
exl-id: 2668ba68-29c8-4c3f-bebc-ba62760a8a61
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '766'
ht-degree: 37%

---

# Trabalhar com conteúdo na biblioteca de ativos

Informações sobre as tarefas que você pode executar em um ativo na Biblioteca de conteúdo em [!DNL Adobe Target] incluindo anotação, cópia, exclusão, download, edição, compartilhamento e exibição de propriedades.

1. Clique em **[!UICONTROL Ofertas]** > **[!UICONTROL Ofertas de código]** ou **[!UICONTROL Ofertas de imagem]**.

   ![Guias Ofertas de código e Ofertas de imagem](/help/main/c-experiences/c-manage-content/assets/offers-both.png)

   Para obter mais informações sobre como pesquisar a biblioteca de ofertas e criar Coleções inteligentes, consulte [Filtro e conteúdo de pesquisa](/help/main/c-experiences/c-manage-content/filter-and-search-content.md#concept_3B59B8F025BF4CEA82ECC5199D365276).

1. (Opcional) Alternar entre as [!UICONTROL Exibição de cartão] e [!UICONTROL Exibição de lista], clique no botão [!UICONTROL Exibição de cartão] ou o [!UICONTROL Exibição de lista] ícone no canto superior direito da biblioteca de conteúdo. Você também pode usar [!UICONTROL Exibir configurações] para configurar ainda mais as colunas ao visualizar o [!UICONTROL Exibição de lista].

   A ilustração a seguir mostra as opções disponíveis ao visualizar o [!UICONTROL Exibição de lista]:

   ![Opções de Exibição de lista](/help/main/c-experiences/c-manage-content/assets/view-settings-options.png)

1. Execute a ação desejada, conforme explicado nas seguintes seções:

## Opções de ofertas de código

Ao visualizar o [!UICONTROL Ofertas de código] Você pode executar as seguintes ações em um item ao passar o mouse sobre uma oferta ou pasta e selecionar o ícone apropriado.

![Ícones de flutuação na guia Ofertas de código](/help/main/c-experiences/c-manage-content/assets/code-offers-hover-icons.png)

* **Informações**: Exibir as informações da oferta.
* **Editar**: Edite a pasta ou oferta.
* **Copiar**: Copie a oferta. Copiar e editar a oferta permite criar facilmente uma nova oferta semelhante.
* **Mover**: Clique no ícone Mover , navegue até o local onde deseja mover a oferta ou pasta e clique no link **[!UICONTROL Largar]** ícone . Por exemplo, você pode mover uma ou mais pastas para dentro de outra pasta para criar subpastas. Clique em [!UICONTROL Limpar seleção] para desmarcar as ofertas ou pastas que você selecionou.
* **Excluir**: Exclua a oferta ou pasta. Consulte [Considerações ao excluir itens](#delete).

## Opções de Ofertas de imagem

Ao visualizar o [!UICONTROL Ofertas de imagem] Você pode executar as seguintes ações em um item ao passar o mouse sobre uma oferta ou pasta e selecionar o ícone apropriado.

A ilustração a seguir mostra os ícones de flutuação ao visualizar o [!UICONTROL Exibição de cartão].

![Ícones de flutuação na guia Ofertas de imagem quando estiver na Exibição de cartão](/help/main/c-experiences/c-manage-content/assets/image-offers-hover-icons.png)

A ilustração a seguir mostra os ícones de flutuação ao visualizar o [!UICONTROL Exibição de lista]. Para exibir os ícones, clique em um item na lista.

![Ícones de flutuação na guia Ofertas de imagem na Exibição de lista](/help/main/c-experiences/c-manage-content/assets/list-view-hover.png)

* **Selecionar**: Selecione uma ou mais pastas nas quais executar as seguintes ações:

   * Baixar
   * Copiar
   * Mover
   * Excluir (Consulte [Considerações ao excluir itens](#delete).)

   Selecione uma ou mais ofertas de imagem nas quais executar as seguintes ações:

   * Compartilhar
   * Baixar
   * Propriedades da exibição
   * Editar
   * Anotar
   * Mover 


* **Baixar**: Baixe a oferta de imagem ou a pasta e seu conteúdo.
* **Propriedades da exibição**: Exibir as propriedades do item. Certifique-se de clicar no botão [!UICONTROL Básico] e a guia [!UICONTROL Avançado] para exibir todas as informações disponíveis. Clique no ícone de Lápis na página de propriedades para editar as propriedades e adicionar mais informações. Você pode adicionar informações de metadados, status de publicação e dados da licença.
* **Mais ações**: Exibir opções adicionais quando em [!UICONTROL Exibição de cartão].
* **Editar**: Edite a pasta ou oferta.
* **Anotar**: Adicione uma observação ao ativo. Clique no ativo, selecione a área que deseja anotar e digite a sua observação.
* **Copiar**: Copie a oferta. Copiar e editar a oferta permite criar facilmente uma nova oferta semelhante.

## Considerações ao excluir itens {#delete}

* É possível excluir uma pasta inteira que contenha qualquer quantidade de ativos e subpastas. Esse recurso está disponível na interface do usuário do Target, assim como na interface do usuário dos ativos da Adobe Experience Cloud.
* Se você excluir uma pasta com um grande número de imagens, o processo em execução em segundo plano pode levar algum tempo (vários minutos) antes que a interface do usuário seja atualizada para mostrar o estado final. O tempo necessário é em função do número de imagens, não do tamanho delas. Uma boa estimativa é de dez minutos para 2.000 imagens. Você pode continuar com outros trabalhos e verificar o estado final depois de alguns minutos para confirmar a exclusão.
* As pastas que não estão vazias na biblioteca de Oferta de imagens podem ser excluídas. Se todas as imagens da pasta não forem referenciadas em nenhuma atividade, a pasta inteira e seu conteúdo serão excluídos. Se algumas imagens da pasta forem referenciadas em qualquer atividade, todas as imagens não referenciadas serão excluídas, mas as imagens e pastas referenciadas que contêm essas imagens serão mantidas.

## Vídeo de treinamento: O repositório de conteúdo ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo inclui informações sobre o gerenciamento de conteúdo. (4:56)

* Conexão entre a [biblioteca de ativos da Experience Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/creative-cloud.html) e a biblioteca de conteúdo do Target
* Ofertas HTML personalizadas
* Ofertas HTML personalizadas no Visual Experience Composer

>[!VIDEO](https://video.tv.adobe.com/v/17387)
