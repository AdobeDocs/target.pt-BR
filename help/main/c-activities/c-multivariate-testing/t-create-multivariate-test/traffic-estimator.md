---
keyword: traffic estimate;traffic estimator;estimate;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Saiba como usar o Avaliador de tráfego que permite saber se você tem tráfego suficiente para sua atividade de  [!DNL Adobe Target] [!UICONTROL Teste multivariado] ser bem-sucedida.
title: Quanto tráfego é necessário para uma atividade de [!UICONTROL Teste multivariado] (MVT)?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 530
ht-degree: 19%

---

# Estimar o tráfego necessário para uma atividade de [!UICONTROL Teste multivariado] bem-sucedida

Como o teste multivariado compara várias experiências, é importante saber qual é a quantidade de tráfego necessária para oferecer resultados significativos. O [!UICONTROL Avaliador de tráfego] usa estatísticas sobre sua página e o número de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessárias para tornar o teste bem-sucedido.

O [!UICONTROL Avaliador de Tráfego] prevê o tamanho de amostra necessário para garantir o seguinte:

* 95% de confiança. Essa estatística significa que a chance de relatar um falso positivo se não houver aumento real é de 5% (100% - nível de confiança).
* 80% de potência estatística. Essa estatística significa que o teste tem uma probabilidade de 80% de detectar um aumento real de 25% ou mais.
* 25% de aumento mínimo detectável com confiança. [!DNL Target] calcula a quantidade de tráfego necessária para ter 80% de chance de detectar um aumento real de 25% ou mais.

O teste usa a correção de Bonferroni para corrigir para várias comparações. Esse método é conhecido por ser conservador, pois é balanceado pela aplicação de uma elevação mínima detectável confiável grande.

O [!UICONTROL Avaliador de tráfego] também fornece feedback que permite saber se você tem tráfego suficiente para o teste que você projetou para ter sucesso.

1. Na página [!UICONTROL Experiências] do [!UICONTROL Visual Experience Composer] em uma atividade [!UICONTROL Multivariada], clique no ícone **[!UICONTROL Tráfego]** ( ![ícone do Avaliador de Tráfego](/help/main/assets/icons/Gauge2.svg) ) no canto superior esquerdo da página [!UICONTROL Experiências].

   O [!UICONTROL Avaliador de Tráfego] se abre.

   ![Interface de usuário do Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Você pode clicar no ícone novamente para ocultar o [!UICONTROL Avaliador de tráfego].

   Próximo à parte superior do [!UICONTROL Avaliador de tráfego], os valores inseridos são calculados e os resultados são mostrados.

1. (Condicional) Forneça a taxa de conversão típica, os visitantes estimados por dia e a duração do teste.

   * **[!UICONTROL Número de combinações de conteúdo]**: calculado automaticamente com base no número de experiências que estão sendo criadas como parte da atividade após as exclusões.
   * **[!UICONTROL Taxa de conversão típica]**: a taxa de conversão é expressa como uma porcentagem, com base na estimativa ou dados anteriores do sistema de análise.
   * **[!UICONTROL Visitantes estimados por dia]**: essa é a quantidade de visitantes que provavelmente visualizarão essa página com base nos critérios de direcionamento. Isso pode se basear nos dados da análise.
   * **[!UICONTROL Duração do teste]**: a quantidade de dias de duração da execução da atividade.

   O [!UICONTROL Avaliador de Tráfego] usa essas estatísticas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   A estimativa muda, à medida que você muda os números. Por exemplo, se você estiver testando muitas experiências e sua taxa de conversão e impressões estiverem muito baixas, o [!UICONTROL Avaliador de tráfego] mostra por quanto tempo o teste deve ser executado para ser bem-sucedido. Ou, se o tráfego for baixo, o [!UICONTROL Avaliador de tráfego] pode sugerir um número menor de experiências para que você possa executar o teste pelo número desejado de dias.

   Caso não tenha tráfego suficiente, você pode fazer uma ou ambas as opções a seguir:

   * Reduza o número de combinações de ofertas e o número de locais.
   * Aumente a duração do teste.

   Ajuste os números até que o [!UICONTROL Avaliador de tráfego] indique que você tem tráfego suficiente e, em seguida, crie seu teste adequadamente.
