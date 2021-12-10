---
keywords: promoções, promoções principais, promoções secundárias, tipo de promoções, lista de itens, promover por atributo, promover uma coleção
description: Saiba como adicionar itens promovidos e controlar o posicionamento no Adobe [!DNL Target] Designs do Recommendations. É possível adicionar promoções estáticas e dinâmicas.
title: Como adiciono promoções em designs Recommendations?
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
source-git-commit: 0d8d04091968923c7d343692140279c026d579f4
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 50%

---

# ![PREMIUM](/help/assets/premium.png) Adicionar promoções

Adicione itens promovidos e controle o posicionamento nos designs do [!DNL Adobe Target Recommendations]. É possível adicionar promoções estáticas e dinâmicas.

>[!IMPORTANT]
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Uso das regras de inclusão estática e dinâmica](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

Quando você cria uma atividade do [!DNL Recommendations], tem a opção de incluir itens promovidos no design do [!DNL Recommendations]. As promoções usam os espaços disponíveis em um design e têm precedência sobre as recomendações de back-up e os resultados de critérios. Por exemplo, se seu design tiver seis espaços e você usar dois deles para promoções, quatro espaços estarão disponíveis para os itens recomendados com base em critérios.

As promoções são deduplicadas em relação aos itens recomendados pelos critérios para a atividade; portanto, um determinado item não aparecerá duas vezes em uma bandeja de recomendação.

É possível promover itens específicos, promover itens dinamicamente, promover itens com base em atributos ou promover coleções.

![[!UICONTROL Promoção principal] e [!UICONTROL Promoção secundária] opções em [!DNL Target] interface](assets/add_promotion_toggles.png)

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

      Se você selecionar [!UICONTROL Promover por atributo], é possível criar correspondências dinâmicas. Para obter mais informações, consulte [Uso das regras de inclusão estática e dinâmica](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Selecione **[!UICONTROL Promover uma coleção]** e escolha a coleção de itens que deseja promover.

      É possível criar novas coleções para usar em promoções. Consulte [Criar uma coleção](/help/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) para obter mais informações.
   Se você escolher **[!UICONTROL Lista de itens]** como **[!UICONTROL Tipo de promoção]**, você pode selecionar a variável **[!UICONTROL Randomizar Ordem de Item]** , se desejar.

   A ordem de classificação padrão para [!UICONTROL Lista de itens] é baseada na ordem inserida na variável [!DNL Target] Interface do usuário ou API. Se a lista incluir mais itens do que o número de espaços definido para as promoções, a variável [!UICONTROL Randomizar Ordem de Item] opção randomiza os itens promovidos que são exibidos em seu design. Escolher essa opção resulta em [!DNL Target] selecionando aleatoriamente os itens habilitados para promoções no modelo a partir do conjunto de promoções inteiro em cada ocorrência.

   Se suas entidades não tiverem uma `entity.value` (por exemplo, você não vende produtos) é possível passar um valor numérico para a `entity.value` , como a data de publicação. Nesse caso, os itens promovidos podem ser promovidos com base na data de publicação mais recente, em ordem decrescente. O `entity.value` O atributo é do tipo double; ele não aceita cadeias de caracteres.

   Se você selecionou a variável **[!UICONTROL Promover por atributo]** ou **[!UICONTROL Promover uma coleção]** , a opção para tornar a ordem aleatória não é aplicável.

   Ao promover itens específicos usando a variável [!UICONTROL Promover por atributo] ou [!UICONTROL Promover uma coleção] , a ordem padrão em que os itens são apresentados é baseada na variável `entity.value` , em ordem numérica decrescente.

   A tabela a seguir ilustra as diferenças entre essas opções:

   | Tipo de promoção | Classificação padrão | Classificação de backup | Opção de filtragem dinâmica |
   | --- | --- | --- | --- |
   | [!UICONTROL Lista de itens] | Pedido inserido na interface/API do Target | Aleatório (quando selecionado por interface/API) | Não |
   | [!UICONTROL Promover por atributo] | `entity.value` (ordem decrescente) | Sem aleatoriedade | Sim |
   | [!UICONTROL Promover uma coleção] | `entity.value` (ordem decrescente) | Sem aleatoriedade | Não |

1. Clique em **[!UICONTROL Salvar]**.

As promoções são aplicadas a todas as experiências na atividade.
