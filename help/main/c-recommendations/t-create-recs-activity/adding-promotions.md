---
keywords: promoções;promoções frontais;promoções traseiras;tipo de promoções;lista de itens;promover por atributo;promover uma coleção
description: Saiba como adicionar itens promovidos e controlar seu posicionamento nos designs do Adobe [!DNL Target] Recommendations. É possível adicionar promoções estáticas e dinâmicas.
title: Como adicionar promoções em designs do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
TQID: 'https://experienceleague.adobe.com/tAfKOzwjnUJgypDh-4LdVukNlTVwMS4UkvcNmCaCV0E'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '695'
ht-degree: 3%
---
# Adicionar promoções {#add-promotions}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como adicionar itens promovidos a um design [!DNL Recommendations] e como sua ordem de classificação é determinada.

>[!ENDSHADEBOX]

As promoções colocam itens específicos em um design [!DNL Recommendations], além dos itens recomendados pelos critérios. Eles usam slots disponíveis no design e têm prioridade sobre os resultados dos critérios e as recomendações de backup. Por exemplo, se um design tiver seis slots e dois deles forem usados para promoções, quatro slots permanecerão para itens recomendados com base em critérios.

As promoções são deduplicadas em relação aos itens recomendados pelos critérios para a atividade, de modo que um determinado item não aparece duas vezes em uma bandeja de recomendação.

![Alterar caixa de diálogo de promoção com os botões Promoção principal e Promoção secundária desativados](assets/add_promotion_toggles.png)

>[!NOTE]
>
>O uso de promoções altera a estrutura e a saída do CSV. Essas alterações podem afetar qualquer processo externo que envolva CSV, como email.

## Adicionar uma promoção {#add-promotion}

Uma promoção define quais itens são promovidos, quantos espaços de design eles usam e o período durante o qual são exibidos.

1. Na página **[!UICONTROL Opções]**, clique no botão de alternância **[!UICONTROL Promoção principal]** ou **[!UICONTROL Promoção secundária]**.

   A ilustração a seguir mostra o botão **[!UICONTROL Promoção principal]** na posição &quot;Ativado&quot;. As promoções podem ser inseridas antes e depois dos resultados dos critérios.

   ![A caixa de diálogo Alterar promoção com o botão Promoção principal ativado, mostrando o Número de Slots de Design, o Agendamento e as opções de Tipo de promoção](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

1. Defina o **[!UICONTROL Número de slots de design]** a serem usados para os itens promovidos.

   Até 20 slots podem ser usados, dependendo do design do [!DNL Recommendations]. Cada slot usado fica indisponível para as recomendações retornadas com base nos critérios.

1. Defina uma data de **Início** e uma data de **Término** para os itens promovidos.

   Se nenhuma data de início for definida, a promoção começará imediatamente. Se nenhuma data final for definida, a promoção será executada indefinidamente.

1. Selecione um **[!UICONTROL Tipo de promoção]**:

   * **[!UICONTROL Lista de itens]**: insira os `entity.id` valores dos itens a serem promovidos, separados por vírgulas.
   * **[!UICONTROL Promover por atributo]**: adicione regras para definir os atributos dos itens a serem promovidos. Essa opção permite correspondências dinâmicas por meio de regras de inclusão estáticas e dinâmicas. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Usar regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#inclusion-rules).
   * **[!UICONTROL Promover uma coleção]**: escolha a coleção de itens a serem promovidos. Novas coleções podem ser criadas para promoções. Consulte [Criar uma coleção](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08).

   O tipo de promoção também determina a ordem de classificação dos itens promovidos. Consulte [Tipos de promoção e ordem de classificação](#promotion-sort-order).

   ![Altere a caixa de diálogo de promoção com as opções de Tipo de promoção destacadas: Lista de itens, Promover por atributo e Promover uma coleção](/help/main/c-recommendations/t-create-recs-activity/assets/promotion_type.png)

1. Clique em **[!UICONTROL Salvar]**.

As promoções são aplicadas a todas as experiências na atividade.

## Tipos de promoção e ordem de classificação {#promotion-sort-order}

A ordem de classificação dos itens promovidos depende do tipo de promoção, como mostra a tabela a seguir.

| Tipo de promoção | Classificação padrão | Classificação de backup | Opção de filtragem dinâmica |
| --- | --- | --- | --- |
| **[!UICONTROL Lista de itens]** | Pedido inserido na interface ou API [!DNL Target] | Aleatório (quando selecionado por meio da interface ou da API) | Não |
| **[!UICONTROL Promover por atributo]** | `entity.value` (ordem decrescente) | Sem aleatoriedade | Sim |
| **[!UICONTROL Promover uma coleção]** | `entity.value` (ordem decrescente) | Sem aleatoriedade | Não |

* **[!UICONTROL Lista de Itens]**: a ordem de classificação padrão é a ordem inserida na interface ou API [!DNL Target]. A caixa de seleção **[!UICONTROL Randomizar a Ordem dos Itens]** está disponível para este tipo. Quando a lista inclui mais itens do que o número de espaços definido para as promoções, essa opção torna aleatório quais itens promovidos são exibidos no design. Em cada ocorrência, [!DNL Target] seleciona aleatoriamente os itens habilitados para promoções no modelo de todo o conjunto de promoções.
* **[!UICONTROL Promover por Atributo]** e **[!UICONTROL Promover uma Coleção]**: a ordem padrão é baseada no atributo `entity.value`, em ordem numérica decrescente. A aleatoriedade do pedido não é aplicável.

Se as entidades não tiverem um atributo `entity.value` (por exemplo, a empresa não vende produtos), um valor numérico como a data de publicação poderá ser passado para o atributo `entity.value`. Os itens promovidos são ordenados pela data de publicação mais recente, em ordem decrescente. O atributo `entity.value` é do tipo double e não aceita cadeias de caracteres.
