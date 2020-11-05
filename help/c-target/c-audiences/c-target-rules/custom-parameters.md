---
keywords: custom parameters;target custom parameters;targetpageparams;targeting mbox parameters
description: Os parâmetros personalizados são parâmetros de mbox. Se você passar algum parâmetro de mbox para mboxes, ou usar a função targetPageParams, esses parâmetros aparecerão aqui para uso em públicos-alvo.
title: Parâmetros personalizados no Adobe Target
feature: audiences
topic: Standard
uuid: a9eb62a6-e86a-4e7b-922c-ad87570435ba
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 90%

---


# Parâmetros personalizados{#custom-parameters}

Os parâmetros personalizados são parâmetros de mbox. Se você passar algum parâmetro de mbox para mboxes, ou usar a função targetPageParams, esses parâmetros aparecerão aqui para uso em públicos-alvo.

For more information, see [Pass parameters to a global mbox](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md).

Ao criar um público-alvo personalizado com base em um parâmetro de mbox, `mboxParameter` não solicita mais `mboxName`. O nome da mbox agora é opcional. Essa alteração permite usar parâmetros de várias mboxes ou referenciar um parâmetro que ainda não foi gravado na borda.

1. Na interface do [!DNL Target], clique em **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Criar público-alvo]**.
1. Dê um nome ao público-alvo.
1. Click **[!UICONTROL Add Rule]** > **[!UICONTROL Custom]**.

   Para selecionar o parâmetro desejado:

   * Ao criar um novo público-alvo, selecione um nome de parâmetro na lista, comece a digitar os primeiros caracteres do nome ou o nome completo do parâmetro desejado.
   * Caso lembre do nome da mbox, mas não do parâmetro, use a caixa de seleção para filtrar uma mbox conhecida que passe o parâmetro desejado.

   Com ambos os métodos, não há link entre a mbox e o parâmetro. O público-alvo funcionará de acordo com o parâmetro em todas as mboxes que passam esse parâmetro.

   Se você editar um público-alvo existente, os critérios de filtragem serão exibidos com o nome da mbox fornecido durante a criação.

1. Escolha um avaliador:

   * Contém (não diferencia maiúsculas de minúsculas)
   * Não contém (não diferencia maiúsculas de minúsculas)
   * Igual

   ![Público-alvo personalizado do parâmetro](/help/c-target/c-audiences/c-target-rules/assets/custom.png)

1. Inserir cada valor em uma nova linha.
1. (Opcional) Clique em **[!UICONTROL Adicionar regra]** e configure regras adicionais para o público-alvo.
1. Clique em **[!UICONTROL Salvar]**.

O [cartão pop-up dos detalhes de definição](/help/c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) do público-alvo mostra o nome do parâmetro na seção Regras. Não há referência à mbox usada para filtragem.

>[!NOTE]
>
>Para público-alvo personalizados criados antes do lançamento do Target 18.5.1 (22 de maio de 2018), os nomes de mbox não serão exibidos no cartão pop-up de definição do público-alvo. Você deve salvar novamente o público-alvo personalizado para obter o nome da mbox a ser exibido no cartão.

## Considerações {#considerations}

* Os públicos-alvo e as atividades são avaliados para uma mbox específica. Por exemplo, se a mbox global transmitir determinado parâmetro, mas a mbox regional não, o direcionamento de atividades/públicos-alvo não será qualificado para a mbox regional.
* A definição de metas não é avaliada em parâmetros internos da mbox, como mboxPC, mboxSession, mbox3rdPartyId, mboxMCSDID, mboxMCAVID, mboxMCGVID, mboxCount, mboxId e mboxVersion.

## Vídeo de treinamento: Criando o emblema ![do tutorial do Audiência](/help/assets/tutorial.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
