---
description: Os parâmetros personalizados são parâmetros de mbox. Se você passar algum parâmetro de mbox para mboxes, ou usar a função targetPageParams, esses parâmetros aparecerão aqui para uso em públicos-alvo.
keywords: parâmetros personalizados, parâmetros personalizados do target, targetpageparams, parâmetros mbox de segmentação
seo-description: Os parâmetros personalizados são parâmetros de mbox. Se você passar algum parâmetro de mbox para mboxes, ou usar a função targetPageParams, esses parâmetros aparecerão aqui para uso em públicos-alvo.
seo-title: Parâmetros personalizados no Adobe Target
solution: Target
title: Parâmetros personalizados
topic: Padrão
uuid: a9eb62a6-e86a-4e7b-922c-ad87570435ba
translation-type: tm+mt
source-git-commit: 2be27985953c06c6cde2090cf0bef896969f03a0

---


# Parâmetros personalizados{#custom-parameters}

Os parâmetros personalizados são parâmetros de mbox. Se você passar algum parâmetro de mbox para mboxes, ou usar a função targetPageParams, esses parâmetros aparecerão aqui para uso em públicos-alvo.

Para obter mais informações, consulte [Passagem de parâmetros a uma mbox global](https://marketing.adobe.com/resources/help/en_US/target/ov/c_pass_parameters_to_global_mbox.html).

Ao criar um público-alvo personalizado com base em um parâmetro de mbox, `mboxParameter` não solicita mais `mboxName`. O nome da mbox agora é opcional. Essa alteração permite usar parâmetros de várias mboxes ou referenciar um parâmetro que ainda não foi gravado na borda.

1. Na interface do [!DNL Target], clique em **[!UICONTROL Públicos-alvo]** &gt; **[!UICONTROL Criar público-alvo]**.
1. Dê um nome ao público-alvo.
1. Clique em **[!UICONTROL Adicionar regra]** &gt; **[!UICONTROL Personalizada]**.

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

O [cartão pop-up dos detalhes de definição](../../../c-target/c-audiences/audiences.md#section_11B9C4A777E14D36BA1E925021945780) do público-alvo mostra o nome do parâmetro na seção Regras. Não há referência à mbox usada para filtragem.

>[!NOTE]
>
>Para público-alvo personalizados criados antes do lançamento do Target 18.5.1 (22 de maio de 2018), os nomes de mbox não serão exibidos no cartão pop-up de definição do público-alvo. Você deve salvar novamente o público-alvo personalizado para obter o nome da mbox a ser exibido no cartão.

## Considerações {#considerations}

* Os públicos-alvo e as atividades são avaliados para uma mbox específica. Por exemplo, se a mbox global passar um certo parâmetro, mas a mbox regional não, a definição de metas de atividade/público-alvo não será qualificada para a mbox regional.

## Vídeo de treinamento: Criação de públicos-alvo

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392?captions=por_br)