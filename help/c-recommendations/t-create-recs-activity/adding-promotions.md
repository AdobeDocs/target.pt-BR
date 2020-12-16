---
keywords: promotions;front promotions;back promotions;promotions type;list of items;promote by attribute;promote a collection
description: Adicione itens promovidos e controle o posicionamento nos designs do Adobe Target Recommendations. É possível adicionar promoções estáticas e dinâmicas.
title: Adicione promoções em designs do Adobe Target Recommendations.
feature: recs creation
translation-type: tm+mt
source-git-commit: 180a8064019e8d4a44db13923aad7422f67ccf3f
workflow-type: tm+mt
source-wordcount: '679'
ht-degree: 60%

---


# ![PREMIUM](/help/assets/premium.png) Adicionar promoções

Adicione itens promovidos e controle o posicionamento nos designs do Adobe Target Recommendations. É possível adicionar promoções estáticas e dinâmicas.

>[!IMPORTANT]
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Usar as regras de inclusão estática e dinâmica](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

Quando você cria uma atividade do [!DNL Recommendations], tem a opção de incluir itens promovidos no design do [!DNL Recommendations]. As promoções usam os espaços disponíveis em um design e têm precedência sobre as recomendações de back-up e os resultados de critérios. Por exemplo, se seu design tiver seis espaços e você usar dois deles para promoções, quatro espaços estarão disponíveis para os itens recomendados com base em critérios.

As promoções são deduplicadas em relação aos itens recomendados pelos critérios para a atividade; portanto, um determinado item não aparecerá duas vezes em uma bandeja de recomendação.

É possível promover itens específicos, promover itens dinamicamente, promover itens com base em atributos ou promover coleções.

![](assets/add_promotion_toggles.png)

>[!NOTE]
>
>O uso de promoções altera a estrutura e a saída do CSV. Essas alterações podem afetar qualquer processo externo que envolva CSV, como email.

1. Na página **[!UICONTROL Opções]**, clique no botão de alternância **[!UICONTROL Promoção principal]** ou **[!UICONTROL Promoção secundária]**.

   A ilustração a seguir mostra o botão [!UICONTROL Promoção principal] na posição &quot;Ligado&quot;.

   ![Adicionar opções de Promoção principal](/help/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   É possível inserir promoções antes *e* depois dos resultados dos seus critérios.
1. Defina o número de espaços de design a serem usados para os itens promovidos.

   É possível usar até 20 espaços, dependendo do design do [!DNL Recommendations]. Cada espaço usado fica indisponível para as recomendações retornadas com base nos seus critérios.

1. Defina uma data de início e uma data de término para os itens promovidos.

   Se você não definir uma data de início, a promoção começará imediatamente. Se você não definir uma data de término, a promoção será executada indefinidamente.

1. Selecione um **[!UICONTROL Tipo de promoção]**.

   * Selecione **[!UICONTROL Lista de itens]** e insira os valores de `entity.id`, separados por vírgulas, dos itens específicos que você deseja promover.

   * Selecione **[!UICONTROL Promover por atributo]** e adicione as regras para definir os atributos dos itens que deseja remover.

      Se você selecionar Promover por atributo, poderá criar correspondências dinâmicas. Para obter mais informações, consulte [Usar as regras de inclusão estática e dinâmica](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Selecione **[!UICONTROL Promover uma coleção]** e escolha a coleção de itens que deseja promover.

      É possível criar novas coleções para usar em promoções. Consulte [Criar uma coleção](/help/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) para obter mais informações.
   Se você escolher **[!UICONTROL Lista de itens]** como **[!UICONTROL Tipo de promoção]**, poderá marcar a caixa de seleção **[!UICONTROL Randomizar pedido de item]**, se desejar.

   A ordem de classificação padrão para [!UICONTROL Lista de Itens] é baseada na ordem que você digitou na interface do Público alvo ou na API. Se sua lista incluir mais itens do que o número de slots definidos para promoções, a opção [!UICONTROL Randomizar ordem de item] aleatorizará os itens promovidos exibidos no design. Escolher essa opção resulta em [!DNL Target] selecionar aleatoriamente os itens habilitados para promoções no modelo a partir de todo o conjunto de promoções em cada ocorrência.

   Se as entidades não tiverem um atributo `entity.value` (por exemplo, se você não vender produtos), você poderá passar um valor numérico para o atributo `entity.value`, como a data de publicação. Nesse caso, os itens promovidos podem ser promovidos com base na data de publicação mais recente, em ordem decrescente. O atributo `entity.value` é do tipo duplo; não aceita cordas.

   Se você selecionou a opção **[!UICONTROL Promover por atributo]** ou **[!UICONTROL Promover uma coleção]**, a opção para randomizar a ordem não é aplicável.

   Ao promover itens específicos usando as opções [!UICONTROL Promover por atributo] ou [!UICONTROL Promover uma coleção], a ordem padrão na qual os itens são apresentados é baseada no atributo `entity.value`, em ordem numérica decrescente.

   A tabela a seguir ilustra as diferenças entre essas opções:

   | Tipo de promoção | Classificação padrão | Classificação de backup | Opção de filtragem dinâmica |
   | --- | --- | --- | --- |
   | Lista de itens | Pedido inserido na interface de usuário/API do Público alvo | Aleatório (quando selecionado por interface de usuário/API | Não |
   | Promover por atributo | `entity.value` (ordem decrescente) | Aleatório em cada solicitação (quando nenhum atributo `entity.value` está presente) | Sim |
   | Promover uma coleção | `entity.value` (ordem decrescente) | Aleatório em cada solicitação (quando nenhum atributo `entity.value` está presente) | Não |

1. Clique em **[!UICONTROL Salvar]**.

As promoções são aplicadas a todas as experiências na atividade.
