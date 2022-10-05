---
keywords: relatórios, metodologia estatística, cálculos estatísticos, estatísticas, estatística, média, taxa de conversão, receita por visitante, rpv, intervalo de confiança, aumento, teste de solch t, cálculos offline
description: Saiba mais sobre os cálculos estatísticos usados no manual [!UICONTROL Teste A/B] atividades em [!DNL Adobe Target].
title: Como posso saber mais sobre os cálculos estatísticos usados em [!UICONTROL Teste A/B] Atividades?
feature: Reports
source-git-commit: 4baa78ac1119e86002c415f09b9481ad351fdcfc
workflow-type: tm+mt
source-wordcount: '1096'
ht-degree: 2%

---

# Cálculos estatísticos em testes A/Bn

Este artigo documenta os cálculos estatísticos detalhados usados nos testes manuais A/Bn em [!DNL Adobe Target]. As definições são fornecidas para [!UICONTROL Índice de conversão], [!UICONTROL Intervalo de confiança da taxa de conversão], [!UICONTROL Lift], [!UICONTROL Intervalo de confiança para aumento]e [!UICONTROL Confiança].

>[!NOTE]
>
>As informações contidas neste artigo substituem a variável *Cálculos do Adobe Target para testes A/B* arquivo pdf anteriormente disponível para download neste site.

![Relatório de destino mostrando o [!UICONTROL Índice de conversão], [!UICONTROL Média de aumento e intervalo de confiança]e [!UICONTROL Confiança] de uma atividade de Teste A/B.](/help/main/c-reports/statistical-methodology/img/target_report.png)

## Desempenho médio

A seção a seguir explica os cálculos usados na ilustração anterior.

### Taxa de conversão e campanhas de Receita por visitante (RPV)

A ilustração a seguir mostra [!UICONTROL Índice de conversão], [!UICONTROL Intervalo de confiança da taxa de conversão]e o número de [!UICONTROL Conversões] em [!DNL Target] relatório. Por exemplo, a primeira linha mostra que para a Experiência A: o [!UICONTROL Índice de conversão] é 25,81% com uma [!UICONTROL Intervalo de confiança] de ±7,7% e 32 conversões foram registradas. Considerando que 124 visitantes viram a experiência, isso equivale a 32/124 = 25,81%.

<p style="text-align:center;"><img width="25%" src="img/conv_rate.png"></p>

A taxa de conversão ou **média**, *μ<sub>ν</sub>* para cada experiência *ν* em um experimento é definido como uma proporção da soma da métrica com o número de unidades atribuídas a essa métrica, *N<sub>ν</sub>*:

<p style="text-align:center;"><img width="125px" src="img/mean_definition.png"></p>

Aqui,

* *Y<sub>iν</sub>* é o valor da métrica para cada unidade *i*, que foi atribuído a uma determinada experiência *ν*.

* A soma sobre unidades *i* depende da escolha da metodologia de contagem.

   * If *[!UICONTROL Visitantes]* é usada como metodologia de contagem, cada unidade é um visitante único definido como um participante exclusivo na atividade durante a vida útil da atividade.
   * If *[!UICONTROL Visitas]* é usada como metodologia de contagem, cada unidade é uma visita única definida como um participante exclusivo em uma experiência durante uma [!DNL Target] sessão (com uma `sessionId`). Quando a variável `sessionId` for alterada ou o visitante atingir a etapa de conversão, uma nova visita será contada.
   * If *[!UICONTROL Impressões da atividade]* é usada como metodologia de contagem, cada unidade é uma impressão exclusiva definida como cada vez que um visitante carrega qualquer página da atividade.

## [!UICONTROL Intervalo de confiança da média]/[!UICONTROL Índice de conversão]

O intervalo de confiança da taxa de conversão é intuitivamente definido como o intervalo de possíveis taxas de conversão consistente com os dados subjacentes.

Ao executar experimentos, a taxa de conversão de uma determinada experiência é uma *estimativa* da taxa de conversão &quot;true&quot;. Para quantificar a incerteza desta estimativa, [!DNL Target] O usa um intervalo de confiança. [!DNL Target] sempre relata um intervalo de confiança de 95%, o que significa que, a longo prazo, 95% dos intervalos de confiança calculados incluem a taxa de conversão verdadeira da experiência.

Um intervalo de confiança de 95% da taxa de conversão *μ<sub>ν</sub>* é definido como o intervalo de valores:

<p style="text-align:center;"><img width="30%" src="img/confidence_interval.png"></p>

em que o erro padrão para a média é definido como

<p style="text-align:center;"><img width="75px" src="img/se_conv_continuous.png"></p>

Se for utilizada uma estimativa imparcial do desvio-padrão da amostra:

<p style="text-align:center;"><img width="200px" src="img/stdev_definition.png"></p>

Observe que, quando a campanha é uma campanha de taxa de conversão (ou seja, a métrica de conversão é binária), o erro padrão reduz para:

<p style="text-align:center;"><img width="150px" src="img/se_conv.png"></p>

## Aumento

A ilustração a seguir mostra [!UICONTROL Lift] e [!UICONTROL Intervalo de confiança do aumento] em [!DNL Target] Relatório. O número representa a média do intervalo dos limites de aumento, e a seta reflete se o aumento é positivo ou negativo. A seta é exibida em cinza até que a confiança passe 95%. Depois que a confiança ultrapassa o limite, a seta fica verde ou vermelha com base em um aumento positivo ou negativo.

<p style="text-align:center;"><img width="35%" src="img/lift.png"></p>

O aumento entre uma experiência  *ν* e a experiência de controlo *ν<sub>0</sub>* é o &quot;delta&quot; relativo em taxas de conversão, definidas como

<p style="text-align:center;"><img width="15%" src="img/lift_definition.png"></p>

em que as taxas de conversão individuais são as definidas acima. Mais simplesmente,

```
Lift(Experience N) = (Performance_Experience_N - Performance_Control)/ Performance_Control
```

Se a taxa de conversão da experiência de controle *ν<sub>0</sub>* for 0, não haverá aumento.

## [!DNL Confidence Interval of Lift]

O boxplot no [!UICONTROL Média de aumento e intervalo de confiança] representa o valor médio e 95% [!UICONTROL Intervalo de confiança do aumento]. O boxplot é cinza quando há qualquer sobreposição no intervalo de confiança de uma determinada experiência sem controle com o intervalo de confiança da experiência de controle e fica verde ou vermelho quando o intervalo de confiança de determinada experiência está acima ou abaixo do intervalo de confiança da experiência de controle.

O erro padrão do aumento entre uma experiência  *ν* e a experiência de controlo  *ν<sub>0</sub>* é definido como:

<p style="text-align:center;"><img width="35%" src="img/se_lift.png" alt="métrica-média"></p>

Em seguida, o Intervalo de confiança de 95% do aumento é:

<p style="text-align:center;"><img width="40%" src="img/lift_CI.png"></p>

Esse cálculo usa o método &quot;Delta&quot; e é descrito [mais detalhadamente neste documento](/help/main/assets/confidence_interval_lift.pdf)

## [!UICONTROL Confiança]

A última coluna mostra a confiança em um [!DNL Target] relatório. A confiança de uma experiência é uma probabilidade (denotada como um percentual) de obter um resultado menos extremo do que aquele que é realmente observado, visto que a hipótese nula é verdadeira. Em termos de valores p, a confiança exibida é *1 - valor p*. Intuitivamente, maior confiança significa que é menos provável que a experiência de controle e não controle tenha taxas de conversão iguais.

Em [!DNL Target], de duas caudas **Teste t do galês** é realizada entre a experiência de ensaio e a experiência de controlo para testar se os meios de ensaio e de controlo são os mesmos. Porque normalmente não sabemos se os tamanhos das amostras e as variações de dois grupos são os mesmos antes de executar o experimento, e [!DNL Target] além disso, permite que você tenha porcentagens desiguais de tráfego enviadas para cada experiência, não supomos que a variação para cada experiência seja igual. Assim, o teste t de Welch é escolhido em vez do teste t de Estudante.

Para executar o teste t de Welch, começamos primeiro a calcular a estatística t e os graus de liberdade, e depois executamos um teste t de duas caudas para gerar o valor p. Por fim, calculamos a confiança com base no valor p.

O *t*-a estatística é definida como a diferença entre os meios de quaisquer duas variáveis aleatórias independentes, *ν* e *ν<sub>0</sub>*, dividido pelo erro padrão da diferença:

<p style="text-align:center;"><img width="100px" src="img/t_value.png"></p>

em que *μ<sub>v</sub>* e *μ<sub>v0</sub>* são os meios de *ν*  e *ν<sub>0</sub>* respectivamente, e o erro padrão da diferença entre *μ<sub>v</sub>* e *μ<sub>v0</sub>* são dadas por:

<p style="text-align:center;"><img width="150px" src="img/standard_error_diff.png"></p>

em que *σ<sup>2</sup><sub>v</sub>* e *σ<sup>2</sup><sub>v<sub>0</sub></sub>* são as variações de duas experiências *ν*  e *ν<sub>0</sub>* respectivamente, e *N<sub>v</sub>* e *N<sub>v<sub>0</sub></sub>* são tamanhos de amostra para *ν* e *ν<sub>0</sub>* respectivamente.

Para o teste t de Welch, o grau de liberdade é calculado do seguinte modo:

<p style="text-align:center;"><img width="180px" src="img/degree_of_freedom.png"></p>

e grau de liberdade *ν*  e *ν<sub>0</sub>* são definidas como:

<p style="text-align:center;"><img width="100px" src="img/df_v.png"></p>

<p style="text-align:center;"><img width="100px" src="img/df_v0.png"></p>

Em seguida, o valor p pode ser calculado a partir da área na cauda do *t*- distribuição:

<p style="text-align:center;"><img width="20%" src="img/p_value.png"></p>

Por último, a confiança reportada em [!DNL Target] é definido como:

<p style="text-align:center;"><img width="20%" src="img/confidence.png"></p>

## Execução de cálculos offline

O [download do relatório de CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) inclui apenas dados brutos e não inclui métricas calculadas, como receita por visitante, aumento ou confiança usada para testes A/B.

Para calcular essas quantidades estatísticas, faça o download do [Calculadora de confiança completa](/help/main/assets/complete_confidence_calculator.xlsx) Arquivo do Excel para inserir o valor da atividade.