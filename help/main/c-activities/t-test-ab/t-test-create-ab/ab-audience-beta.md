---
keywords: público-alvo; selecionar público-alvo; escolher público-alvo; Seletores
description: Defina quais visitantes do site ingressarão na sua atividade Adobe [!DNL Target] com base nos critérios de público-alvo.
title: Como selecionar um público-alvo em uma atividade A/B  [!DNL Target] ?
feature: A/B Tests
hide: true
hidefromtoc: true
source-git-commit: cc823f84fb93cbe2e55d394d0f6f4fe48bbd5293
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 12%

---

# Seleção do público-alvo

O público determina quais visitantes qualificados são inseridos na atividade [!DNL Adobe Target].

A etapa [!UICONTROL Targeting] do fluxo de trabalho guiado de três partes ao [criar uma atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab-beta.md) exibe um diagrama de fluxo que guia você pelas etapas de atribuição de um público-alvo e sua porcentagem de tráfego, selecionando o método de alocação de tráfego e especificando a alocação de tráfego para cada experiência na atividade.

![Etapa de direcionamento de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Para obter mais informações sobre todas as opções no diagrama de fluxo, consulte [Criar uma atividade de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab-beta.md).

## Selecionar um público-alvo para a atividade

1. Clique no controle **[!UICONTROL All Visitors]** para selecionar outro público-alvo para a atividade.

   O público-alvo [!UICONTROL All Visitors] está definido como padrão. Se você selecionar outro público-alvo, o nome dele será exibido no controle mais à esquerda.

   Para um teste A/B sem direcionamento específico de público, escolha o padrão, [!UICONTROL All Visitors].

   O quadro direito é exibido, permitindo adicionar ou excluir um público-alvo e atribuir a porcentagem de visitante à atividade.

1. Para alterar o público-alvo, clique no ícone **[!UICONTROL Replace]** ( ![Ícone Substituir](/help/main/assets/icons/Retweet.svg) ) no quadro direito.

1. Na caixa de diálogo [!UICONTROL Add Audience], [selecione o público desejado](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) e clique em **[!UICONTROL Assign Audience]**.

   Por padrão, todos os visitantes são seu público-alvo. No entanto, você pode mudar o público-alvo. Os públicos-alvo estão selecionados em [!UICONTROL Audience Library] ou você pode criar um público-alvo somente atividade. O [!UICONTROL Audience Library] contém públicos que foram definidos previamente, inclusive alguns comuns que são predefinidos como parte do [!DNL Target].

1. (Condicional) Clique em **Combinar públicos-alvo** para [criar um público-alvo que combine vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md).

1. (Condicional) Para criar um novo público-alvo que ainda não esteja no [!UICONTROL Audience Library], clique em **Criar público-alvo**. Durante o [fluxo de trabalho de criação de público](/help/main/c-target/c-audiences/audiences.md), você pode escolher entre as seguintes opções:

   * Crie um público-alvo sob demanda que seja salvo no [!UICONTROL Audience Library] que possa ser reutilizado em outras atividades
   * Crie um [público-alvo específico da atividade](/help/main/c-target/creating-activity-only-audience.md) que não seja salvo no [!UICONTROL Audience Library] e possa ser usado somente na atividade atual

1. Clique em **[!UICONTROL Visitor Percentage]** no painel direito e especifique a porcentagem de visitantes qualificados a serem incluídos na atividade.

1. Quando estiver satisfeito com seu público-alvo, clique em **[!UICONTROL Next]** para ir até a terceira etapa do fluxo de trabalho guiado em três etapas.

>[!NOTE]
>
>Os públicos-alvo são importados automaticamente em segundo plano quando você abre a lista de públicos-alvo e os públicos importados foram criados há mais de 10 minutos.

## Exibir informações de um público-alvo

1. Na caixa de diálogo [!UICONTROL Add Audiences], clique no ícone **[!UICONTROL Information]** ( ![Ícone de informações](/help/main/assets/icons/InfoOutline.svg) ) ao lado de um público-alvo para exibir detalhes sobre esse público-alvo, incluindo sua origem e atributos.

1. Clique em **[!UICONTROL View Full Details]** para exibir detalhes adicionais sobre o público. Os detalhes incluem os atributos do público-alvo; a descrição, o espaço de trabalho, o tipo e a fonte do público-alvo; e uma lista de atividades que fazem referência a esse público-alvo. Você pode ver informações sobre cada público-alvo, incluindo nome da atividade, status, espaço de trabalho e quando o público-alvo foi modificado pela última vez e por quem.

## Editar ou copiar um público-alvo

Você pode editar ou copiar um público-alvo clicando no ícone [!UICONTROL More Actions] ( ![ícone Mais Ações](/help/main/assets/icons/More.svg) ) ao lado do público-alvo desejado na caixa de diálogo [!UICONTROL Add Audience] e clicando em [!UICONTROL Edit] ou [!UICONTROL Copy].

Copiar um público-alvo é útil se você deseja criar outro semelhante para um público-alvo existente. Você pode fazer uma cópia do público-alvo, fazer suas edições e depois salvá-lo como um novo público-alvo.

