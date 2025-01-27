---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Saiba como usar o Avaliador de tráfego que permite saber se você tem tráfego suficiente para que sua atividade do  [!DNL Adobe Target] [!UICONTROL Multivariate Test] seja bem-sucedida.
title: Quanto tráfego é necessário para uma atividade de [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
hide: true
hidefromtoc: true
source-git-commit: 4805da617962e29794bd3af16138f3887ad250d0
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 21%

---

# Estimar o tráfego necessário para uma atividade [!UICONTROL Multivariate Test] bem-sucedida

Como o teste multivariado compara várias experiências, é importante saber qual é a quantidade de tráfego necessária para oferecer resultados significativos. O [!UICONTROL Traffic Estimator] usa estatísticas sobre sua página e o número de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessárias para tornar o teste bem-sucedido.

O [!UICONTROL Traffic Estimator] prevê o tamanho de amostra necessário para garantir o seguinte:

* 95% de confiança. Essa estatística significa que a chance de relatar um falso positivo se não houver aumento real é de 5% (100% - nível de confiança).
* 80% de potência estatística. Essa estatística significa que o teste tem uma probabilidade de 80% de detectar um aumento real de 25% ou mais.
* 25% de aumento mínimo detectável com confiança. [!DNL Target] calcula a quantidade de tráfego necessária para ter 80% de chance de detectar um aumento real de 25% ou mais.

O teste usa a correção de Bonferroni para corrigir para várias comparações. Esse método é conhecido por ser conservador, pois é balanceado pela aplicação de uma elevação mínima detectável confiável grande.

O [!UICONTROL Traffic Estimator] também fornece feedback que permite saber se você tem tráfego suficiente para o teste que você projetou para ter sucesso.

1. Na página [!UICONTROL Experiences] de [!UICONTROL Visual Experience Composer] em uma atividade [!UICONTROL Multivariate], clique no ícone **[!UICONTROL Traffic]** ( ![Ícone do Avaliador de Tráfego](/help/main/assets/icons/Gauge2.svg) ) no canto superior esquerdo da página [!UICONTROL Experiences].

   O [!UICONTROL Traffic Estimator] se abre.

   ![Interface de usuário do Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Você pode clicar no ícone novamente para ocultar o [!UICONTROL Traffic Estimator].

   Próximo à parte superior de [!UICONTROL Traffic Estimator], os valores inseridos são calculados e os resultados são mostrados.

1. (Condicional) Forneça a taxa de conversão típica, os visitantes estimados por dia e a duração do teste.

   * **[!UICONTROL Number of Content Combinations]**: calculado automaticamente com base no número de experiências que estão sendo criadas como parte da atividade após as exclusões.
   * **[!UICONTROL Typical Conversion Rate]**: A taxa de conversão é expressa como uma porcentagem, com base na estimativa ou dados passados do sistema de análise.
   * **[!UICONTROL Estimated Visitors Per Day]**: esse é o número de visitantes que provavelmente visualizarão essa página com base nos critérios de direcionamento. Isso pode se basear nos dados da análise.
   * **[!UICONTROL Test Duration]**: a quantidade de dias de duração da execução da atividade.

   O [!UICONTROL Traffic Estimator] usa essas estatísticas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   A estimativa muda, à medida que você muda os números. Por exemplo, se você estiver testando muitas experiências e sua taxa de conversão e impressões estiverem muito baixas, o [!UICONTROL Traffic Estimator] mostra por quanto tempo o teste deve ser executado para ser bem-sucedido. Ou, se o tráfego for baixo, o [!UICONTROL Traffic Estimator] pode sugerir um número menor de experiências para que você possa executar o teste o número desejado de dias.

   Caso não tenha tráfego suficiente, você pode fazer uma ou ambas as opções a seguir:

   * Reduza o número de combinações de ofertas e o número de locais.
   * Aumente a duração do teste.

   Ajuste os números até que [!UICONTROL Traffic Estimator] indique que você tem tráfego suficiente e, em seguida, crie seu teste de acordo.
