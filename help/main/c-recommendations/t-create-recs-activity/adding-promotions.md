---
keywords: promoções;promoções frontais;promoções traseiras;tipo de promoções;lista de itens;promover por atributo;promover uma coleção
description: Saiba como adicionar itens promovidos e controlar seu posicionamento nos designs do Adobe [!DNL Target] Recommendations. É possível adicionar promoções estáticas e dinâmicas.
title: Como adicionar promoções em designs do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '637'
ht-degree: 40%

---

# Adicionar promoções

Adicione itens promovidos e controle o posicionamento nos designs do [!DNL Adobe Target Recommendations]. É possível adicionar promoções estáticas e dinâmicas.

>[!IMPORTANT]
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Usar regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

Quando você cria uma atividade do [!DNL Recommendations], tem a opção de incluir itens promovidos no design do [!DNL Recommendations]. As promoções usam os espaços disponíveis em um design e têm precedência sobre as recomendações de back-up e os resultados de critérios. Por exemplo, se seu design tiver seis espaços e você usar dois deles para promoções, quatro espaços estarão disponíveis para os itens recomendados com base em critérios.

As promoções são deduplicadas em relação aos itens recomendados pelos critérios para a atividade; portanto, um determinado item não aparecerá duas vezes em uma bandeja de recomendação.

É possível promover itens específicos, promover itens dinamicamente, promover itens com base em atributos ou promover coleções.

Opções de ![[!UICONTROL Front Promotion] e [!UICONTROL Back Promotion] na interface do usuário [!DNL Target]](assets/add_promotion_toggles.png)

>[!NOTE]
>
>O uso de promoções altera a estrutura e a saída do CSV. Essas alterações podem afetar qualquer processo externo que envolva CSV, como email.

1. Na página **[!UICONTROL Options]**, clique no botão de alternância **[!UICONTROL Front Promotion]** ou **[!UICONTROL Back Promotion]**.

   A ilustração a seguir mostra o botão [!UICONTROL Front Promotion] na posição &quot;Ligado&quot;.

   ![Adicionar opções de Promoção principal](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   É possível inserir promoções antes *e* depois dos resultados dos seus critérios.

1. Defina o número de espaços de design a serem usados para os itens promovidos.

   É possível usar até 20 espaços, dependendo do design do [!DNL Recommendations]. Cada espaço usado fica indisponível para as recomendações retornadas com base nos seus critérios.

1. Defina uma data de início e uma data de término para os itens promovidos.

   Se você não definir uma data de início, a promoção começará imediatamente. Se você não definir uma data de término, a promoção será executada indefinidamente.

1. Selecione um **[!UICONTROL Promotion Type]**.

   * Selecione **[!UICONTROL List of items]** e insira os valores de `entity.id`, separados por vírgulas, dos itens específicos que você deseja promover.

   * Selecione **[!UICONTROL Promote by attribute]** e adicione regras para definir os atributos dos itens que deseja promover.

     Se você selecionar [!UICONTROL Promote by Attribute], poderá criar correspondências dinâmicas. Para obter mais informações, consulte [Usar regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Selecione **[!UICONTROL Promote a collection]** e escolha a coleção de itens que deseja promover.

     É possível criar novas coleções para usar em promoções. Consulte [Criar uma coleção](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) para obter mais informações.

   Se você escolher **[!UICONTROL List of Items]** como **[!UICONTROL Promotion Type]**, poderá marcar a caixa de seleção **[!UICONTROL Randomize Item Order]**, se desejar.

   A ordem de classificação padrão para [!UICONTROL List of Items] é baseada na ordem inserida na interface ou API [!DNL Target]. Se sua lista incluir mais itens do que o número de espaços definido para as promoções, a opção [!UICONTROL Randomize Item Order] aleatoriamente tornará os itens promovidos exibidos em seu design. Escolher esta opção resulta em [!DNL Target] selecionando aleatoriamente os itens habilitados para promoções no modelo de todo o conjunto de promoções em cada ocorrência.

   Se suas entidades não tiverem um atributo `entity.value` (por exemplo, você não vende produtos), você poderá passar um valor numérico para o atributo `entity.value`, como a data de publicação. Nesse caso, os itens promovidos podem ser promovidos com base na data de publicação mais recente, em ordem decrescente. O atributo `entity.value` é do tipo double; ele não aceita cadeias de caracteres.

   Se você selecionou a opção **[!UICONTROL Promote by Attribute]** ou **[!UICONTROL Promote a Collection]**, a opção para tornar a ordem aleatória não é aplicável.

   Ao promover itens específicos usando as opções [!UICONTROL Promote by Attribute] ou [!UICONTROL Promote a Collection], a ordem padrão na qual os itens são apresentados é baseada no atributo `entity.value`, em ordem numérica decrescente.

   A tabela a seguir ilustra as diferenças entre essas opções:

   | Tipo de promoção | Classificação padrão | Classificação de backup | Opção de filtragem dinâmica |
   | --- | --- | --- | --- |
   | [!UICONTROL List of Items] | Pedido inserido na interface do usuário/API do Target | Aleatório (quando selecionado por meio da interface do usuário/API) | Não |
   | [!UICONTROL Promote by Attribute] | `entity.value` (ordem decrescente) | Sem aleatoriedade | Sim |
   | [!UICONTROL Promote a Collection] | `entity.value` (ordem decrescente) | Sem aleatoriedade | Não |

1. Clique em **[!UICONTROL Save]**.

As promoções são aplicadas a todas as experiências na atividade.
