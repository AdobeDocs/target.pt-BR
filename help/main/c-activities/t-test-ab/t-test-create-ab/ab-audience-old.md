---
keywords: público-alvo; selecionar público-alvo; escolher público-alvo; Seletores
description: O público-alvo determina quais visitantes do site são inseridos na atividade Adobe [!DNL Target] .
title: Como selecionar um público-alvo em uma atividade A/B  [!DNL Target] ?
feature: A/B Tests
exl-id: 281ae227-c593-4b71-ad12-865430b332be
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 64%

---

# Seleção do público-alvo

O público-alvo determina quais visitantes do site são inseridos na atividade [!DNL Adobe Target].

>[!NOTE]
>
>Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

1. Na caixa [!UICONTROL Audience], clique no ícone **[!UICONTROL Edit]** (as reticências verticais) e clique em **[!UICONTROL Replace Audience]**.

   ![Opção Substituir público-alvo](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/replace-audience.png)

   Por padrão, todos os visitantes são seu público-alvo. No entanto, você pode mudar o público-alvo. Os públicos-alvo são selecionados na biblioteca de público-alvo ou você pode criar um público-alvo com apenas uma atividade. A biblioteca de público-alvo contém públicos que foram definidos previamente, inclusive alguns comuns que são predefinidos como parte de [!DNL Target].

1. Selecione ou crie o público-alvo desejado:

   * Selecionar um público-alvo da biblioteca
   * [Combinar vários públicos](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5)
   * [Criar um novo público](/help/main/c-target/c-audiences/create-audience.md#task_1D507519D3AD4390B507F188BD294DC1)
   * [Criar um público somente atividade](/help/main/c-target/creating-activity-only-audience.md#concept_A6BADCF530ED4AE1852E677FEBE68483).

   Para um teste A/B sem direcionamento específico de público, escolha o padrão, [!UICONTROL All Visitors].

   Você também pode editar ou copiar um público-alvo passando o cursor do mouse sobre o público-alvo desejado na caixa de diálogo [!UICONTROL Add Audience], conforme mostrado abaixo.

   Copiar um público-alvo é útil se você deseja criar outro semelhante para um público-alvo existente. Você pode fazer uma cópia do público-alvo, fazer suas edições e salvá-lo como um público-alvo novo. Essa funcionalidade de passar o mouse sobre o item também existe em outros tipos de atividade.

   ![Cursor do mouse sobre o público-alvo](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audience_picker_hover-new.png)

   Ao criar um público-alvo, você pode selecionar um local (mbox) e especificar os parâmetros para esse local. Em [!UICONTROL Custom Parameters], selecione a mbox e especifique os parâmetros desejados.

   >[!NOTE]
   >
   >Os públicos-alvo são importados automaticamente em segundo plano quando você abre a lista de públicos-alvo e os públicos importados foram criados há mais de 10 minutos.

1. (Condicional) Especifique a porcentagem de visitantes qualificados a serem incluídos na atividade.

   Por exemplo, você pode optar por incluir 50% de todos os visitantes.

   ![Porcentagem de público-alvo](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/audperc-new.png)

   Você também pode optar por permitir que o Target [aloque tráfego automaticamente](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Uso do Audiences no Adobe Target (6:21) ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo explica como usar os públicos-alvo no [!DNL Target Standard/Premium].

* Explique o termo &quot;público-alvo&quot;
* Explicar as duas maneiras como o público-alvo é usado para otimização
* Encontre públicos-alvo na lista de públicos-alvo
* Segmente uma atividade para um público-alvo
* Use públicos-alvo para relatórios passivos em uma atividade

>[!VIDEO](https://video.tv.adobe.com/v/30984?captions=por_br)

### Fluxo de trabalho da atividade - Direcionamento (2:14) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre a configuração de públicos-alvo.

* Designar um público-alvo para sua atividade
* Controle do tráfego
* Selecione seu método de alocação de tráfego
* Aloque o tráfego entre diferentes experiências

>[!VIDEO](https://video.tv.adobe.com/v/17385)

Para obter informações detalhadas, consulte [Públicos-alvo](/help/main/c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).
