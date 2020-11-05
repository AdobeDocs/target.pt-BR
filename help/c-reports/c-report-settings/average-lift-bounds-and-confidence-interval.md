---
keywords: Target;reports;report settings;environment;lift;lift bound;variance;confidence;control
description: Os relatórios incluem vários pontos de dados e representações de visualização que ajudam você a entender os limites de incentivo e o nível de confiança associados à atividade do Adobe Target para ajudar a determinar com mais precisão um vencedor.
title: Média de aumento, Limites de aumento e Intervalo de confiança
feature: report settings
uuid: 2899503a-d81e-4dc3-b258-a5ecafd1d1a4
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 73%

---


# Média de aumento, Limites de aumento e Intervalo de confiança

Os relatórios incluem vários pontos de dados e representações de visualização que ajudam você a entender os limites de incentivo e o nível de confiança associados à sua [!DNL Adobe Target] atividade para ajudar a determinar com mais precisão um vencedor.

>[!NOTE]
>
>This feature is available only when viewing reports in [!UICONTROL Table] View. Este recurso não está disponível para atividades que usam o [Analytics como fonte de relatórios (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Interpretar os dados {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

The following illustration shows [!UICONTROL Lift Bounds and Confidence Level] information:

![Relatório de Incentivo médio e Nível de confiança](/help/c-reports/c-report-settings/assets/lift-screenshot-new.png)

The lift and confidence information in the [!DNL Target] reporting UI includes:

### Aumento

O número grande e a seta refletem o valor esperado do aumento. Esse número é o ponto médio do intervalo dos limites de aumento. A seta de aumento esperado é exibida em cinza até que a confiança passe 95%. Após esse limite, a seta é exibida em vermelho ou verde com base no aumento negativo ou positivo, respectivamente.

### Limites de elevação

Este é o intervalo de confiança de 95% do aumento. Ele é exibido como um intervalo abaixo da média de aumento. See [Example calculation](#example) below for an example of how these lift bounds are calculated.

### Gráfico de in a box

The boxplot graph in the [!DNL Target] interface represents the expected value and 95% confidence interval of the success metric in question. Pense nisso como uma maneira gráfica de exibir as informações de aumento e os limites de aumento.

There are a few key ways [!DNL Target] helps you interpret the confidence information, one of which is color. O gráfico exibe qualquer sobreposição no intervalo de confiança de uma experiência específica com o intervalo de confiança do controle em cinza e qualquer faixa do intervalo de confiança de uma experiência específica acima ou abaixo do intervalo de confiança de controle como verde ou vermelho, respectivamente.

O comprimento da barra do boxplot representa o tamanho do intervalo de confiança de uma maneira fácil de entender. À medida que você coleta mais dados em sua atividade, a barra é alterada. O intervalo de confiança é derivado da variação e do tamanho da amostra (número de visitantes). Quanto menor a variação e quanto maior o tamanho da amostra, mais estreito o seu intervalo de confiança.

### Confiança

A confiança de uma experiência ou oferta representa a probabilidade de que o aumento da experiência/oferta associada sobre a experiência/oferta de controle seja &quot;real&quot; (não causado aleatoriamente). Normalmente, 95% é o nível de confiança recomendado para o aumento ser considerado significativo.

## How are lift bounds calculated? {#section_1D360781D972483693680BE0F07AEAD1}

Os limites de aumento representam os intervalos de confiança de 95% do aumento que a experiência ou oferta específica tem sobre a experiência de controle ou oferta. Falando vagamente, isso significa que o aumento real tem cerca de 95% de chance de estar entre esses limites.

Os limites de aumento são calculados usando a seguinte fórmula:

![](assets/lift_diagram.png)

Existe um cálculo adicional para chegar à entrada dos nossos limites de aumento:

* **valor t:** a estatística crítica para o nosso nível de confiança de 95% é de 1,96. Saiba mais sobre [os valores t aqui](https://en.wikipedia.org/wiki/T-statistic).
* **Variação do aumento:** A métrica de sucesso do Erro Padrão de Experiência N e a métrica de sucesso Erro Padrão da Experiência de Controle são necessárias para determinar a variação de aumento, que é calculada usando a seguinte fórmula (ilustrada caso a métrica de sucesso seja conversão).

   ![](assets/lift_variance.png)

* **Índice de conversão / Erro padrão da métrica de sucesso:** O erro padrão é calculado da mesma forma para a Experiência N e o Controle, usando a seguinte fórmula (ilustrada caso a métrica de sucesso seja conversão). Saiba mais sobre [erro padrão aqui](https://en.wikipedia.org/wiki/Standard_error).

   ![](assets/standard_error.png)

   >[!NOTE]
   >
   >O erro padrão para atividades de métricas de sucesso de receita é baseado na variação da amostra da receita.

## Example calculation {#example}

Vamos considerar um exemplo de atividade com duas experiências e os seguintes resultados:

| Experiência | Visitantes | Conversões | Índice de conversão |
|--- |--- |--- |--- |
| Experiência A (Controle) | 219, 328 | 2,466 | 1.12% |
| Experiência B | 218, 362 | 3,040 | 1.39% |

Com base em nossas fórmulas, podemos calcular as entradas necessárias para os limites de aumento.

**Erro padrão para Experiência A (Controle)**

![](assets/standard_error_A.png)

**Erro padrão para Experiência B**

![](assets/standard_error_B.png)

**Variação de aumento para Experiência B**

![](assets/lift_variance_B.png)

**Variação de aumento para Experiência B**

Aumento esperado para Experiência B:

![](assets/lift_bounds_B.png)

Portanto, os limites de aumento para a Experiência B podem ser:

![](assets/lift_bounds_B2.png)

>[!NOTE]
>
>Espere pequena variações entre os cálculos manuais usando as fórmulas acima e os números exibidos no relatório. A diferença pode ser atribuída ao fato de que os números de exibições de página usados nos cálculos manuais são arredondados. The lift shown in the [!DNL Target] report is based on the exact numbers obtained from the total engagement and the engagement count. Os números de engajamento podem ser obtidos por meio da API de relatórios de desempenho.

## When Are lift bounds not displayed? {#section_C5622E1E94684DAD937249B51A9E42CC}

In certain cases, [!DNL Target] does not display lift bounds:

* Para qualquer atividade, quando o número total de visitas ou visitantes for menor que 30.
* For [!UICONTROL Auto-Allocate] activities, no lift bounds are displayed until one experience has attained 60% confidence.
