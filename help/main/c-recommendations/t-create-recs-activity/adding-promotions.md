---
keywords: promoções;promoções frontais;promoções traseiras;tipo de promoções;lista de itens;promover por atributo;promover uma coleção
description: Saiba como adicionar itens promovidos e controlar seu posicionamento no Adobe [!DNL Target] designs do Recommendations. É possível adicionar promoções estáticas e dinâmicas.
title: Como adicionar promoções em designs do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Recommendations
exl-id: bd5e5e12-a712-4c4c-9cf8-6b0f4834067b
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 50%

---

# Adicionar promoções

Adicione itens promovidos e controle o posicionamento nos designs do [!DNL Adobe Target Recommendations]. É possível adicionar promoções estáticas e dinâmicas.

>[!IMPORTANT]
>
>As regras de exclusão estáticas e dinâmicas são recursos poderosos que podem ajudá-lo com seus esforços de marketing. Para obter informações detalhadas, exemplos e cenários de caso de uso, consulte [Uso das regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

Quando você cria uma atividade do [!DNL Recommendations], tem a opção de incluir itens promovidos no design do [!DNL Recommendations]. As promoções usam os espaços disponíveis em um design e têm precedência sobre as recomendações de back-up e os resultados de critérios. Por exemplo, se seu design tiver seis espaços e você usar dois deles para promoções, quatro espaços estarão disponíveis para os itens recomendados com base em critérios.

As promoções são deduplicadas em relação aos itens recomendados pelos critérios para a atividade; portanto, um determinado item não aparecerá duas vezes em uma bandeja de recomendação.

É possível promover itens específicos, promover itens dinamicamente, promover itens com base em atributos ou promover coleções.

![[!UICONTROL Promoção principal] e [!UICONTROL Promoção secundária] opções em [!DNL Target] IU](assets/add_promotion_toggles.png)

>[!NOTE]
>
>O uso de promoções altera a estrutura e a saída do CSV. Essas alterações podem afetar qualquer processo externo que envolva CSV, como email.

1. Na página **[!UICONTROL Opções]**, clique no botão de alternância **[!UICONTROL Promoção principal]** ou **[!UICONTROL Promoção secundária]**.

   A ilustração a seguir mostra o botão [!UICONTROL Promoção principal] na posição &quot;Ligado&quot;.

   ![Adicionar opções de Promoção principal](/help/main/c-recommendations/t-create-recs-activity/assets/add_promotion_front.png)

   É possível inserir promoções antes *e* depois dos resultados dos seus critérios.

1. Defina o número de espaços de design a serem usados para os itens promovidos.

   É possível usar até 20 espaços, dependendo do design do [!DNL Recommendations]. Cada espaço usado fica indisponível para as recomendações retornadas com base nos seus critérios.

1. Defina uma data de início e uma data de término para os itens promovidos.

   Se você não definir uma data de início, a promoção começará imediatamente. Se você não definir uma data de término, a promoção será executada indefinidamente.

1. Selecione um **[!UICONTROL Tipo de promoção]**.

   * Selecione **[!UICONTROL Lista de itens]** e insira os valores de `entity.id`, separados por vírgulas, dos itens específicos que você deseja promover.

   * Selecione **[!UICONTROL Promover por atributo]** e adicione as regras para definir os atributos dos itens que deseja remover.

      Se você selecionar [!UICONTROL Promover por atributo], você pode criar correspondências dinâmicas. Para obter mais informações, consulte [Uso das regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md#concept_4CB5C0FA705D4E449BD0B37B3D987F9F).

   * Selecione **[!UICONTROL Promover uma coleção]** e escolha a coleção de itens que deseja promover.

      É possível criar novas coleções para usar em promoções. Consulte [Criar uma coleção](/help/main/c-recommendations/c-products/collections.md#task_1256DFF6842141FCAADD9E1428EF7F08) para obter mais informações.
   Se você escolher **[!UICONTROL Lista de itens]** como o **[!UICONTROL Tipo de promoção]**, você pode selecionar a variável **[!UICONTROL Randomizar a Ordem dos Itens]** se desejar.

   A ordem de classificação padrão para [!UICONTROL Lista de itens] é baseado na ordem inserida no [!DNL Target] Interface do usuário ou API. Se sua lista incluir mais itens do que o número de espaços definido para as promoções, a variável [!UICONTROL Randomizar a Ordem dos Itens] Essa opção torna aleatórios os itens promovidos exibidos no design. A escolha dessa opção resulta em [!DNL Target] selecionar aleatoriamente os itens ativados para promoções no modelo a partir de todo o conjunto de promoções em cada ocorrência.

   Se suas entidades não tiverem uma `entity.value` atributo (por exemplo, você não vende produtos), é possível passar um valor numérico para a variável `entity.value` como a data de publicação. Nesse caso, os itens promovidos podem ser promovidos com base na data de publicação mais recente, em ordem decrescente. A variável `entity.value` o atributo é do tipo double; ele não aceita strings.

   Se você selecionou a variável **[!UICONTROL Promover por atributo]** ou **[!UICONTROL Promover uma coleção]** opção, a opção para tornar o pedido aleatório não é aplicável.

   Ao promover itens específicos usando o [!UICONTROL Promover por atributo] ou [!UICONTROL Promover uma coleção] opções, a ordem padrão na qual os itens são apresentados baseia-se na `entity.value` atributo, em ordem numérica decrescente.

   A tabela a seguir ilustra as diferenças entre essas opções:

   | Tipo de promoção | Classificação padrão | Classificação de backup | Opção de filtragem dinâmica |
   | --- | --- | --- | --- |
   | [!UICONTROL Lista de itens] | Pedido inserido na interface do usuário/API do Target | Aleatório (quando selecionado por meio da interface do usuário/API) | Não |
   | [!UICONTROL Promover por atributo] | `entity.value` (ordem decrescente) | Sem aleatoriedade | Sim |
   | [!UICONTROL Promover uma coleção] | `entity.value` (ordem decrescente) | Sem aleatoriedade | Não |

1. Clique em **[!UICONTROL Salvar]**.

As promoções são aplicadas a todas as experiências na atividade.
