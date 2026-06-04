---
keywords: público-alvo; selecionar público-alvo; escolher público-alvo; Seletores
description: Defina quais visitantes do site ingressarão na sua atividade do Adobe [!DNL Target] com base nos critérios de público-alvo.
title: Como selecionar um público-alvo em uma atividade A/B  [!DNL Target] ?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
TQID: https://experienceleague.adobe.com/7W8BrRxk4mKlYlgGb-GSOuc0kRMRWBvSochz9STYrTs
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 575
ht-degree: 10%

---

# Seleção do público-alvo

O público determina quais visitantes qualificados são inseridos na atividade [!DNL Adobe Target].

A etapa [!UICONTROL Direcionamento] do fluxo de trabalho guiado de três partes ao [criar uma atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) exibe um diagrama de fluxo que guia você pelas etapas de atribuição de um público-alvo e sua porcentagem de tráfego, selecionando o método de alocação de tráfego e especificando a alocação de tráfego para cada experiência na atividade.

![Etapa de direcionamento de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/ab_flow-new-ui.png)

Para obter mais informações sobre todas as opções no diagrama de fluxo, consulte [Criar uma atividade de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).

## Selecionar um público-alvo para a atividade

1. Clique no controle **[!UICONTROL Todos os visitantes]** para selecionar outro público-alvo para a atividade.

   O público-alvo [!UICONTROL Todos os visitantes] está definido como padrão. Se você selecionar outro público-alvo, o nome dele será exibido no controle mais à esquerda.

   Para um teste A/B sem direcionamento específico de público, escolha o padrão, [!UICONTROL Todos os visitantes].

   O quadro direito é exibido, permitindo adicionar ou excluir um público-alvo e atribuir a porcentagem de visitante à atividade.

1. Para alterar o público-alvo, clique no ícone **[!UICONTROL Substituir]** ( ![Ícone Substituir](/help/main/assets/icons/Retweet.svg) ) no quadro direito.

1. Na caixa de diálogo [!UICONTROL Adicionar público-alvo], [selecione o público-alvo desejado](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) e clique em **[!UICONTROL Atribuir público-alvo]**.

   Por padrão, todos os visitantes são seu público-alvo. No entanto, você pode mudar o público-alvo. Os públicos-alvo estão selecionados na [!UICONTROL Biblioteca de público-alvo] ou você pode criar um público somente atividade. A [!UICONTROL Biblioteca de Público-Alvo] contém públicos que foram definidos previamente, inclusive alguns comuns que são pré-criados como parte de [!DNL Target].

1. (Condicional) Clique em **Combinar públicos-alvo** para [criar um público-alvo que combine vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md).

1. (Condicional) Para criar um novo público-alvo que ainda não esteja na [!UICONTROL Biblioteca de Público-alvo], clique em **Criar Público-alvo**, defina o público-alvo e clique em **[!UICONTROL Concluído]**.

   Durante o [fluxo de trabalho de criação de público](/help/main/c-target/c-audiences/audiences.md), você pode escolher entre as seguintes opções:

   * **[!UICONTROL Biblioteca de público-alvo]**: crie um público-alvo sob demanda que seja salvo na [!UICONTROL Biblioteca de público-alvo] e que possa ser reutilizado em outras atividades.
   * **[!UICONTROL Somente esta atividade]**: crie um [público-alvo específico da atividade](/help/main/c-target/creating-activity-only-audience.md) que não esteja salvo na [!UICONTROL Biblioteca de Público-alvo] e possa ser usado somente na atividade atual.

1. Clique em **[!UICONTROL Porcentagem de visitantes]** no painel direito e especifique a porcentagem de visitantes qualificados a serem incluídos na atividade.

1. Quando estiver satisfeito com seu público-alvo, clique em **[!UICONTROL Avançar]** para ir até a terceira etapa do fluxo de trabalho guiado em três etapas.

>[!NOTE]
>
>Os públicos-alvo são importados automaticamente em segundo plano quando você abre a lista [!UICONTROL Público-alvo] e os públicos importados foram criados há mais de 10 minutos.

## Exibir informações de um público-alvo

1. Na caixa de diálogo [!UICONTROL Adicionar públicos-alvo], clique no ícone **[!UICONTROL Informações]** ( ![ícone Informações](/help/main/assets/icons/InfoOutline.svg) ) ao lado de um público-alvo para exibir detalhes sobre ele, incluindo sua origem e atributos.

1. Clique em **[!UICONTROL Exibir Detalhes Completos]** para exibir detalhes adicionais sobre o público-alvo. Os detalhes incluem os atributos do público-alvo; a descrição, o espaço de trabalho, o tipo e a fonte do público-alvo; e uma lista de atividades que fazem referência a esse público-alvo. Você pode ver informações sobre cada público-alvo, incluindo nome da atividade, status, espaço de trabalho e quando o público-alvo foi modificado pela última vez e por quem.

## Editar ou copiar um público-alvo

Você pode editar ou copiar um público-alvo clicando no ícone [!UICONTROL Mais Ações] ( ![ícone Mais Ações](/help/main/assets/icons/More.svg) ) ao lado do público-alvo desejado na caixa de diálogo [!UICONTROL Adicionar Público-alvo] e clicando em [!UICONTROL Editar] ou [!UICONTROL Copiar].

Copiar um público-alvo é útil se você deseja criar outro semelhante para um público-alvo existente. Você pode fazer uma cópia do público-alvo, fazer suas edições e salvá-lo como um público-alvo novo.
