---
keyword: traffic estimate;traffic estimator
description: Como o teste multivariado compara várias experiências, é importante saber qual é a quantidade de tráfego necessária para oferecer resultados significativos. O Adobe Target Traffic Estimator usa estatísticas sobre sua página e o número de experiências testadas para estimar a quantidade de tráfego e a duração do teste necessário para que o teste seja bem-sucedido.
title: Estimar o tráfego necessário para um teste bem-sucedido
feature: mvt
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 93%

---


# Estimar o tráfego necessário para um teste bem-sucedido

Como o teste multivariado compara várias experiências, é importante saber qual é a quantidade de tráfego necessária para oferecer resultados significativos. O Avaliador de tráfego usa estatísticas sobre a página e a quantidade de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessárias para que o teste seja bem-sucedido.

O Avaliador de tráfego prevê o tamanho da amostra necessária para assegurar o seguinte:

* 95% de confiança

   Isso significa que a oportunidade de relatar um falso positivo se não houver elevação real será de 5% (100% - nível de confiança).
* 80% de poder estatístico

   Isso significa que o teste tem uma probabilidade de 80% de detectar uma verdadeira elevação de 25% ou mais.
* 25% no mínimo de elevação detectável confiável

   O Target calcula a quantidade de tráfego necessária para ter uma possibilidade de 80% de detectar uma elevação verdadeira de 25% ou mais.

O teste usa a correção de Bonferroni para corrigir para várias comparações. Esse método é conhecido por ser conservador, pois é balanceado pela aplicação de uma elevação mínima detectável confiável grande.

O Avaliador de tráfego também fornece um feedback que informa se você tem tráfego suficiente para que o teste que criou seja bem-sucedido.

1. No Criador de experiências, clique no ícone **[!UICONTROL Tráfego]**.

   O Avaliador de tráfego é aberto. Você pode clicar no ícone **[!UICONTROL Tráfego]** novamente para ocultar o Estimador de tráfego.

   ![](assets/estimatorempty.png)

1. Forneça a taxa de conversão típica, os visitantes estimados por dia e a duração do teste.

   * [!UICONTROL Número de combinações de conteúdo]: calculado automaticamente com base no número de experiências que estão sendo criadas como parte da atividade após as exclusões.
   * [!UICONTROL Taxa de conversão típica]: a taxa de conversão é expressa como uma porcentagem, com base na estimativa ou dados anteriores do sistema de análise
   * [!UICONTROL Visitantes estimados por dia]: essa é a quantidade de visitantes que provavelmente visualizarão essa página com base nos critérios de direcionamento. Isso pode se basear nos dados da análise.
   * [!UICONTROL Duração do teste]: a quantidade de dias de duração da execução da atividade.

   O Avaliador de tráfego usa essas estatísticas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   Próximo da parte superior do Avaliador de tráfego, os valores inseridos são calculados, e os resultados são exibidos.

   ![](assets/estimatorinsufficient.png)

   A estimativa muda, à medida que você muda os números. Por exemplo, se você estiver testando um número grande de experiências e sua taxa de conversão e impressões for muito baixa, o Avaliador de tráfego mostrará por quanto tempo o teste terá que ser executado para ser bem-sucedido. Ou, se o tráfego for baixo, o Avaliador de tráfego poderá sugerir um número mais baixo de experiências para você poder executar o teste durante o número desejado de dias.

   Caso não tenha tráfego suficiente, você pode fazer uma ou ambas as opções a seguir:

   * Reduza o número de combinações de ofertas e o número de locais.
   * Aumente a duração do teste.

   Ajuste os números até que o Avaliador de tráfego indique que você tem tráfego suficiente, então, crie seu teste de acordo.

   ![](assets/estimatorok.png)

