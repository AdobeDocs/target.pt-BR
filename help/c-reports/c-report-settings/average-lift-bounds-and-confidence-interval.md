---
keywords: Target, relatórios, configurações de relatório, ambiente, aumento, limite de incentivo, variação, confiança, controle
description: Saiba como interpretar relatórios Adobe [!DNL Target] que incluem pontos de dados e representações de visualização para ajudá-lo a entender os limites de aumento e o nível de confiança de suas atividades.
title: Como visualizar o aumento médio, os limites de aumento e o intervalo de confiança?
feature: Relatórios
exl-id: 0453aec1-cca5-462c-8eed-0d40bb4cf323
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '817'
ht-degree: 73%

---

# Média de aumento, Limites de aumento e Intervalo de confiança

Os relatórios incluem vários pontos de dados e representações de visualização que ajudam a entender os limites de aumento e o nível de confiança associados à sua atividade [!DNL Adobe Target] para ajudar você a determinar com mais precisão um vencedor.

>[!NOTE]
>
>Esse recurso está disponível somente ao visualizar relatórios na [!UICONTROL Exibição de tabela]. Este recurso não está disponível para atividades que usam o [Analytics como fonte de relatórios (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Interpretar os dados {#section_62C0D7E76F3D49A7B3C371C82AEF27D5}

A ilustração a seguir mostra informações sobre [!UICONTROL Limites de incentivo e Nível de confiança]:

![Relatório de Incentivo médio e Nível de confiança](/help/c-reports/c-report-settings/assets/lift-screenshot-new.png)

As informações de lift e confiança na interface do usuário de relatórios [!DNL Target] incluem:

### Aumento

O número grande e a seta refletem o valor esperado do aumento. Esse número é o ponto médio do intervalo dos limites de aumento. A seta de aumento esperado é exibida em cinza até que a confiança passe 95%. Após esse limite, a seta é exibida em vermelho ou verde com base no aumento negativo ou positivo, respectivamente.

### Limites de aumento

Este é o intervalo de confiança de 95% do aumento. Ele é exibido como um intervalo abaixo da média de aumento. Consulte [Exemplo de cálculo](#example) abaixo para obter um exemplo de como esses limites de aumento são calculados.

### Gráfico de caixa

O boxplot na interface [!DNL Target] representa o valor esperado e o intervalo de confiança de 95% da métrica de sucesso em questão. Pense nisso como uma maneira gráfica de exibir as informações de aumento e os limites de aumento.

Há algumas maneiras principais de [!DNL Target] ajudar você a interpretar as informações de confiança, uma delas é a cor. O gráfico exibe qualquer sobreposição no intervalo de confiança de uma experiência específica com o intervalo de confiança do controle em cinza e qualquer faixa do intervalo de confiança de uma experiência específica acima ou abaixo do intervalo de confiança de controle como verde ou vermelho, respectivamente.

O comprimento da barra do boxplot representa o tamanho do intervalo de confiança de uma maneira fácil de entender. À medida que você coleta mais dados em sua atividade, a barra é alterada. O intervalo de confiança é derivado da variação e do tamanho da amostra (número de visitantes). Quanto menor a variação e quanto maior o tamanho da amostra, mais estreito o seu intervalo de confiança.

### Confiança

A confiança de uma experiência ou oferta representa a probabilidade de que o aumento da experiência/oferta associada sobre a experiência/oferta de controle seja &quot;real&quot; (não causado aleatoriamente). Normalmente, 95% é o nível de confiança recomendado para o aumento ser considerado significativo.

## Como são calculados os limites de aumento? {#section_1D360781D972483693680BE0F07AEAD1}

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

## Exemplo de cálculo {#example}

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
>Espere pequena variações entre os cálculos manuais usando as fórmulas acima e os números exibidos no relatório. A diferença pode ser atribuída ao fato de que os números de exibições de página usados nos cálculos manuais são arredondados. O aumento mostrado no relatório [!DNL Target] é baseado nos números exatos obtidos do engajamento total e da contagem de engajamento. Os números de engajamento podem ser obtidos por meio da API de relatórios de desempenho.

## Quando os limites de aumento não são exibidos? {#section_C5622E1E94684DAD937249B51A9E42CC}

Em certos casos, [!DNL Target] não exibe os limites de aumento:

* Para qualquer atividade, quando o número total de visitas ou visitantes for menor que 30.
* Para atividades de [!UICONTROL Alocação automática], nenhum limite de aumento é exibido até que uma experiência tenha atingido 60% de confiança.
