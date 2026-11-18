---
keywords: estimativa de tráfego;avaliador de tráfego;estimativa;tráfego;confiança;potência estatística;aumento;taxa de conversão;visitantes por dia;duração;traffic estimate;traffic estimor;estimate;traffic;traffic;confidence;statistical power;lift;bonferroni;conversion rate;visitors per day;duration
description: Saiba como usar o Avaliador de tráfego que permite saber se você tem tráfego suficiente para sua atividade de [!DNL Adobe Target] [!UICONTROL Teste multivariado] ser bem-sucedida.
title: Quanto tráfego é necessário para uma atividade de [!UICONTROL Teste multivariado] (MVT)?
feature: Multivariate Tests
exl-id: 2b32f4a7-b9b4-40bf-a17b-88225bc88787
TQID: 'https://experienceleague.adobe.com/XHBXV7Jtvp87ve4NTd-016E2dFkHTbPu-8-nY8GE-VM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 8%
---
# Estimar o tráfego necessário para uma atividade de [!UICONTROL Teste multivariado] bem-sucedida {#traffic-estimator}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como usar o **[!UICONTROL Avaliador de Tráfego]** para verificar se a atividade de **[!UICONTROL Teste Multivariado]** tem tráfego suficiente para ser bem-sucedida.

>[!ENDSHADEBOX]

Um teste multivariado compara várias experiências, portanto, é importante saber quanto tráfego é necessário para fornecer resultados significativos. O **[!UICONTROL Avaliador de tráfego]** usa estatísticas sobre sua página e o número de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessárias para tornar o teste bem-sucedido. Ela também fornece feedback que permite saber se você tem tráfego suficiente para o teste que projetou para ser bem-sucedido.

O **[!UICONTROL Avaliador de Tráfego]** prevê o tamanho de amostra necessário para garantir o seguinte:

* **95% de confiança.** Essa estatística significa que a chance de relatar um falso positivo se não houver aumento real é de 5% (100% - nível de confiança).
* **80% de potência estatística.** Essa estatística significa que o teste tem uma probabilidade de 80% de detectar um aumento real de 25% ou mais.
* **Aumento mínimo confiável detectável de &lbrace;25%.** [!DNL Target] calcula a quantidade de tráfego necessária para ter 80% de chance de detectar um aumento real de 25% ou mais.

O teste usa a correção de Bonferroni para corrigir para várias comparações. Esse método é conhecido por ser conservador, pois é balanceado pela aplicação de uma elevação mínima detectável confiável grande.

## Usar o Avaliador de tráfego {#use-traffic-estimator}

Enquanto você cria um **[!UICONTROL Teste multivariado]**, o **[!UICONTROL Avaliador de tráfego]** permite verificar se o tráfego para a sua página é suficiente para o número de experiências que você planeja testar. Executar essa verificação antes de iniciar o teste ajuda a evitar um teste que não pode alcançar visitantes suficientes para produzir resultados significativos e mostra como ajustar o número de combinações ou a duração do teste se o tráfego não for suficiente.

1. Na página **[!UICONTROL Experiências]** do **[!UICONTROL Visual Experience Composer]** em uma atividade **[!UICONTROL Multivariada]**, clique no ícone **[!UICONTROL Tráfego]** ( ![ícone do Avaliador de Tráfego](/help/main/assets/icons/Gauge2.svg) ) no canto superior esquerdo da página.

   O **[!UICONTROL Avaliador de Tráfego]** se abre. Para ocultá-lo, clique no ícone novamente.

   ![Interface de usuário do Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/mvt-est.png)

   Próximo à parte superior do **[!UICONTROL Avaliador de tráfego]**, os valores inseridos são calculados e os resultados são mostrados.

1. (Opcional) Forneça a taxa de conversão típica, os visitantes estimados por dia e a duração do teste.

   O **[!UICONTROL Avaliador de Tráfego]** usa essas estatísticas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   | Métrica | Descrição |
   | --- | --- |
   | **[!UICONTROL Número de Combinações de Conteúdo]** | Essa métrica é calculada automaticamente com base no número de experiências que estão sendo criadas como parte da atividade, após as exclusões. |
   | **[!UICONTROL Taxa de conversão típica]** | Essa métrica é expressa como uma porcentagem, com base na estimativa ou dados anteriores do sistema de análise. |
   | **[!UICONTROL Visitantes estimados por dia]** | Essa métrica é o número de visitantes que provavelmente visualizarão essa página, com base nos critérios de direcionamento. Esse número pode ser baseado nos dados de análise. |
   | **[!UICONTROL Duração do teste]** | O número de dias de duração da execução da atividade. |

1. Revise os resultados. A estimativa muda, à medida que você muda os números.

   Por exemplo, se você estiver testando muitas experiências e sua taxa de conversão e impressões estiverem muito baixas, o **[!UICONTROL Avaliador de tráfego]** mostra por quanto tempo o teste deve ser executado para ser bem-sucedido. Ou, se o tráfego for baixo, o **[!UICONTROL Avaliador de tráfego]** pode sugerir um número menor de experiências, para que você possa executar o teste pelo número desejado de dias.

1. Se você não tiver tráfego suficiente, execute um ou ambos os procedimentos a seguir:

   * Reduza o número de combinações de ofertas e o número de locais.
   * Aumente a duração do teste.

1. Ajuste os números até que o **[!UICONTROL Avaliador de tráfego]** indique que você tem tráfego suficiente e, em seguida, crie seu teste adequadamente.
