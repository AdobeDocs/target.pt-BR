---
keywords: relatórios;metodologia estatística;cálculos estatísticos;estatísticas;média;taxa de conversão;receita por visitante;rpv;intervalo de confiança;aumento;teste t de correção;cálculos offline
description: Saiba mais sobre os cálculos estatísticos usados no manual [!UICONTROL Teste A/B] atividades no [!DNL Adobe Target].
title: Como posso saber mais sobre os cálculos estatísticos usados no [!UICONTROL Teste A/B] Atividades?
feature: Reports
exl-id: 5f7377b9-0567-4b6f-8968-4696b2088d0a
source-git-commit: f997b6a0ea9e0cebf7b414c029971d8520f8b95f
workflow-type: tm+mt
source-wordcount: '1091'
ht-degree: 5%

---

# Cálculos estatísticos em testes A/Bn

Este artigo documenta os cálculos estatísticos detalhados usados em testes A/Bn manuais no [!DNL Adobe Target]. São previstas definições para [!UICONTROL Índice de conversão], [!UICONTROL Intervalo de confiança da taxa de conversão], [!UICONTROL Elevação], [!UICONTROL Intervalo de confiança para aumento], e [!UICONTROL Confiança].

>[!NOTE]
>
>As informações contidas neste artigo substituem o arquivo PDF *Cálculos do Adobe Target para testes A/B* anteriormente disponível para download neste site.

![Relatório de direcionamento mostrando o [!UICONTROL Índice de conversão], [!UICONTROL Intervalo médio de elevação e confiança], e [!UICONTROL Confiança] de uma atividade de Teste A/B.](/help/main/c-reports/statistical-methodology/img/target_report.png)

## Desempenho médio

A seção a seguir explica os cálculos usados na ilustração anterior.

### Taxa de conversão e Campanhas de receita por visitante (RPV)

A ilustração a seguir mostra [!UICONTROL Índice de conversão], [!UICONTROL Intervalo de confiança da taxa de conversão]e o número de [!UICONTROL Conversões] em um [!DNL Target] relatório. Por exemplo, a primeira linha mostra que para a Experiência A: a variável [!UICONTROL Índice de conversão] é de 25,81% com um [!UICONTROL Intervalo de confiança] de ±7,7% e 32 conversões foram registradas. Considerando que 124 visitantes visualizaram a experiência, isso equivale a 32/124 = 25,81%.

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

A taxa de conversão ou **média**, *μ<sub>ν</sub>*, para cada experiência *ν* em um experimento é definida como uma relação da soma da métrica com o número de unidades atribuídas a essa métrica, *N<sub>ν</sub>*:

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

Aqui,

* *Y<sub>ixvName</sub>* é o valor da métrica para cada unidade *i*, que foi atribuído a uma determinada experiência *ν*.

* A soma sobre unidades *i* depende da escolha da metodologia de contagem.

   * Se *[!UICONTROL Visitantes]* for usada como a metodologia de contagem, cada unidade será um visitante único definido como um participante único na atividade durante toda a vida útil da atividade.
   * Se *[!UICONTROL Visitas]* for usada como a metodologia de contagem, cada unidade será uma visita única definida como um participante único em uma experiência durante um [!DNL Target] sessão (com um único `sessionId`). Quando a variável `sessionId` for alterada ou o visitante atingir a etapa de conversão, uma nova visita será contada.
   * Se *[!UICONTROL Impressões da atividade]* é usada como a metodologia de contagem, cada unidade é uma impressão exclusiva definida como cada vez que um visitante carrega qualquer página da atividade.

## [!UICONTROL Intervalo de confiança da média]/[!UICONTROL Índice de conversão]

O intervalo de confiança da taxa de conversão é intuitivamente definido como um intervalo de taxas de conversão possíveis consistente com os dados subjacentes.

Ao executar experimentos, o índice de conversão de uma determinada experiência é um *estimativa* da taxa de conversão &quot;true&quot;. Para quantificar a incerteza nesta estimativa, [!DNL Target] usa um intervalo de confiança. [!DNL Target] sempre relata um intervalo de confiança de 95%, o que significa que, no final, 95% dos intervalos de confiança calculados incluem o índice de conversão verdadeiro da experiência.

Um intervalo de confiança de 95% da taxa de conversão *μ<sub>ν</sub>* é definido como o intervalo de valores:

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

Quando o erro-padrão da média é definido como

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

Se for utilizada uma estimativa imparcial do desvio-padrão da amostra:

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

Quando a campanha é uma campanha de taxa de conversão (ou seja, a métrica de conversão é binária), o erro padrão se reduz a:

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## Aumento

A ilustração a seguir mostra [!UICONTROL Elevação] e [!UICONTROL Intervalo de confiança do aumento] em um [!DNL Target] Relatório. O número representa a média do intervalo dos limites de aumento, e a seta reflete se o aumento é positivo ou negativo. A seta é exibida em cinza até que a confiança passe de 95%. Depois que a confiança ultrapassa o limite, a seta é verde ou vermelha com base em um aumento positivo ou negativo.

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

O aumento entre uma experiência  *ν* e a experiência de controle *ν<sub>0</sub>* é o &quot;delta&quot; relativo em taxas de conversão, definido como

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

Em que as taxas de conversão individuais são as definidas acima. De maneira mais simples,

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

Se o índice de conversão da experiência de controle *ν<sub>0</sub>* é 0, não há aumento.

## [!DNL Confidence Interval of Lift]

O gráfico de boxplot no [!UICONTROL Intervalo médio de elevação e confiança] representa o valor médio e 95% [!UICONTROL Intervalo de confiança do aumento]. O boxplot é cinza quando há qualquer sobreposição no intervalo de confiança de uma determinada experiência de não controle com o intervalo de confiança da experiência de controle. O boxplot é verde ou vermelho quando o intervalo de confiança da experiência é acima ou abaixo do intervalo de confiança da experiência de controle.

O erro padrão do aumento entre uma experiência  *ν* e a experiência de controle  *ν<sub>0</sub>* é definida como:

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="metric-average"></p>

Em seguida, o Intervalo de confiança de 95% do aumento é:

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

Esse cálculo usa o método &quot;Delta&quot; e é descrito [mais detalhes neste documento](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL Confiança]

A última coluna mostra a confiança em um [!DNL Target] relatório. A confiança de uma experiência é uma probabilidade (denotada como uma porcentagem) de obter um resultado menos extremo do que o observado, dada a hipótese nula ser verdadeira. Em termos de valores p, a confiança exibida é *1 - valor p*. Intuitivamente, maior confiança significa que é menos provável que a experiência de controle e não controle tenha taxas de conversão iguais.

Entrada [!DNL Target], um bicaudal **Teste t de Welch** é realizada entre a experiência de teste e a experiência de controle para testar se os meios das experiências de teste e controle são os mesmos. Porque geralmente não sabemos se o tamanho e as variações das amostras de dois grupos são os mesmos antes de executar o experimento, e [!DNL Target] Além disso, para que porcentagens desiguais de tráfego sejam enviadas para cada experiência, não pressupomos que a variação de cada experiência seja igual. Assim, o teste t de Welch é escolhido em vez do teste t de Student.

Para executar o teste t de Welch, primeiro começamos a calcular a estatística t e os graus de liberdade, em seguida, executamos um teste t de duas caudas para gerar o valor p. Por fim, calculamos a confiança com base no valor p.

A variável *t*-a estatística é definida como a diferença entre as médias de quaisquer duas variáveis aleatórias independentes, *ν* e *ν<sub>0</sub>*, dividido pelo erro padrão da diferença:

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

Onde *μ<sub>v</sub>* e *μ<sub>v0</sub>* são os meios de *ν*  e *ν<sub>0</sub>* respectivamente, e o erro-padrão da diferença entre os *μ<sub>v</sub>* e *μ<sub>v0</sub>* são dados por:

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

Onde *σ<sup>2</sup><sub>v</sub>* e *σ<sup>2</sup><sub>v<sub>0</sub></sub>* são as variações de duas experiências *ν*  e *ν<sub>0</sub>* respectivamente, e *N<sub>v</sub>* e *N<sub>v<sub>0</sub></sub>* são tamanhos de amostra para *ν* e *ν<sub>0</sub>* respectivamente.

Para o teste t de Welch, o grau de liberdade é calculado do seguinte modo:

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

E grau de liberdade para *ν*  e *ν<sub>0</sub>* são definidos como:

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

Então, o valor p pode ser calculado a partir da área na cauda da variável *t*-distribuição:

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

Por último, a confiança [!DNL Target] é definida como:

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## Execução de cálculos offline

O [download do relatório de CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) inclui apenas dados brutos e não inclui métricas calculadas, como receita por visitante, aumento ou confiança usada para testes A/B.

Para calcular essas quantidades estatísticas, baixe a variável [!DNL Target] [Calculadora de confiança completa](/help/main/assets/complete_confidence_calculator.xlsx) Arquivo do Excel para inserir o valor da atividade.
