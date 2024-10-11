---
keywords: alocação automática de tráfego;direcionamento;vencedor;garantia estatística;confiança;determinar vencedor;aumento;confiança;padrão;experiência padrão;alocação automática;alocação automática
description: Descubra como interpretar [!UICONTROL Auto-Allocate] resultados de atividade A/B, com foco em indicadores-chave como aumento e confiança.
title: Como Interpretar Relatórios De [!UICONTROL Auto-Allocate]?
feature: Auto-Allocate
hide: true
hidefromtoc: true
source-git-commit: 5fc18c6d3b493ea0a58048cc20ce3a6c2ffb7d14
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Interpretar relatórios de [!UICONTROL Auto-Allocate]

Interprete os resultados de uma atividade A/B [!UICONTROL Auto-Allocate] em [!UICONTROL Adobe Target] examinando indicadores importantes, incluindo aumento e confiança.

Muitos profissionais de marketing cometem o erro de declarar prematuramente uma experiência vencedora antes dos resultados indicarem claramente o vencedor. [!DNL Target] facilita a identificação do vencedor.

Para obter informações gerais sobre como declarar um vencedor, consulte [Dez erros comuns em testes A/B e como evitá-los](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identificar a experiência vencedora {#section_24007470CF5B4D30A06610CE8DD23CE3}

Ao usar o recurso [!UICONTROL Auto-Allocate], o [!DNL Target] exibe um emblema na parte superior da página da atividade, indicando &quot;Ainda não há vencedor&quot; até que a atividade atinja o número mínimo de conversões com confiança suficiente.

![Sem selo de Vencedor](/help/main/c-activities/automated-traffic-allocation/assets/no-winner-new.png)

Quando um vencedor claro é declarado, [!DNL Target] exibe o emblema &quot;Vencedor: Experiência *X*&quot;.

![Selo do vencedor](/help/main/c-activities/automated-traffic-allocation/assets/winner-new.png)

>[!NOTE]
>
>As atividades do [!UICONTROL Auto-Allocate] foram projetadas para encontrar a melhor experiência entre todas as opções, e não apenas para fazer comparações emparelhadas com controle.

## Garantias estatísticas de [!UICONTROL Auto-Allocate] {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

No final de uma atividade A/B, [!UICONTROL Auto-Allocate] garante que o vencedor determinado tenha uma taxa de 5% de falso-positivo. Isso significa que apenas 5% do tempo, o vencedor determinado não é realmente a melhor experiência entre todas as experiências na atividade. Para um [teste A/A](/help/main/c-activities/t-test-ab/aa-testing.md) (com experiências idênticas), [!DNL Target] conclui um teste menos de 5% do tempo. O comportamento esperado para um teste A/A (com experiências idênticas) é para ser executado indefinidamente e, portanto, o emblema do vencedor nunca deve aparecer.

[!DNL Target] não usa confiança baseada no valor p para [!UICONTROL Auto-Allocate].

A coluna [!UICONTROL Confidence] em uma atividade [!UICONTROL Auto-Allocate] exibe a probabilidade de uma experiência ser a vencedora dentro da margem de erro de 1%. O algoritmo usa um efeito mínimo detectável de 1% entre as melhores e as segundas melhores taxas de conversão. O algoritmo usa [Desigualdade de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) para calcular essa probabilidade.

Testes A/B normais calculam a confiança com base nos valores de p. [!UICONTROL Auto-Allocate] não usa valores p. Os valores de P calculam &quot;vagamente&quot; a probabilidade de que uma determinada experiência seja diferente do controle. Esses valores p podem ser usados apenas para determinar se uma experiência pode ser diferente do controle. Esses valores não podem ser usados para determinar se uma experiência é diferente de outra experiência (não de controle).

>[!IMPORTANT]
>
>[!DNL Target] mostra um vencedor após um número mínimo predefinido de conversões; no entanto, a decisão final de escolher o vencedor deve sempre estar nos resultados da Calculadora de Tamanho da Amostra [!DNL Adobe Target]. [!DNL Target] não considera as taxas de conversão base de um site e outros aspectos importantes que são alimentados na calculadora para determinar a duração da atividade. Como resultado, [!DNL Target] pode exibir um vencedor antes do garantido com base em um número mínimo de conversões. Para obter mais informações, consulte [Calculadora de Tamanho da Amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Entender os relatórios de aumento e confiança em [!UICONTROL Auto-Allocate] atividades {#lift-confidence}

Em [!UICONTROL Auto-Allocate] atividades, a primeira experiência (por padrão, chamada de Experiência A) é sempre definida como uma experiência de &quot;Controle&quot; na guia [!UICONTROL Reports]. Essa experiência não é tratada como um verdadeiro controle estatístico no modelo usado para determinar o desempenho das experiências, mas é tratada como uma referência ou linha de base para alguns números no relatório.

O valor numérico &quot;Lift&quot; e os limites de 95% para cada experiência são sempre calculados com referência à experiência &quot;Control&quot; definida. A experiência de &quot;Controle&quot; definida não pode ter aumento relativo a si mesma. Portanto, um valor &quot;—&quot; em branco é relatado para essa experiência. Ao contrário dos testes A/B, em [!UICONTROL Auto-Allocate] testes, se uma experiência tiver um desempenho pior do que o controle definido, um valor de aumento negativo não será relatado; em vez disso, &quot;—&quot; será exibido.

As [!UICONTROL Confidence Interval] barras exibidas representam o intervalo de confiança de 95% em torno da estimativa média da taxa de conversão de uma experiência. Essas barras também são codificadas por cores em relação à experiência &quot;Controle&quot; definida. A barra de experiência &quot;Controle&quot; está sempre em cinza. As partes dos intervalos de confiança abaixo do intervalo de confiança da experiência &quot;Controle&quot; são coloridas em vermelho e as partes dos intervalos de confiança acima da experiência &quot;Controle&quot; são coloridas em verde.

Um vencedor é encontrado quando os 95% [!UICONTROL Confidence Interval] da experiência principal não estão se sobrepondo a nenhuma outra experiência. A experiência vencedora é designada com um selo de estrela verde à esquerda do nome da experiência e no banner &quot;Vencedor&quot;. Quando nenhuma estrela estiver visível, o banner exibirá &quot;Ainda não há vencedor&quot; e um vencedor ainda não foi encontrado.

Um número de &quot;Confiança&quot; também é relatado ao lado da experiência principal ou vencedora no momento. Este número é relatado somente até que a [!UICONTROL Confidence] da experiência principal atinja pelo menos 60%. Se duas experiências estiverem presentes na atividade [!UICONTROL Auto-Allocate], esse número representará o nível de confiança de que a experiência está tendo um desempenho melhor do que a outra experiência. Se mais de duas experiências estiverem presentes na atividade [!UICONTROL Auto-Allocate], esse número representará o nível de confiança de que a experiência está tendo um desempenho melhor do que a experiência de &quot;Controle&quot; definida. Se a experiência de &quot;Controle&quot; estiver ganhando, nenhum valor de &quot;Confiança&quot; será relatado.

## Perguntas frequentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Considere as seguintes respostas às perguntas frequentes:

### Já se passaram alguns dias na atividade. Por que todos os valores de confiança ainda estão mostrando 0%?

Qualquer um dos motivos a seguir descreve por que 0% é exibido na coluna [!UICONTROL Confidence] do relatório para todas as atividades:

* Testes A/B manuais e [!UICONTROL Auto-Allocate] usam estatísticas diferentes para exibir [!UICONTROL Confidence] valores.

  Os testes A/B manuais usam valores p com base no [teste t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Um valor P é a probabilidade de encontrar a diferença observada (ou uma mais extrema) entre uma experiência e o controle, visto que, na realidade, não há essa diferença. Esses valores P podem ser usados somente para determinar se os dados observados estão consistentes, visto que a experiência e o controle são iguais. Esses valores não podem ser usados para determinar se uma experiência é diferente de outra experiência (não de controle).

  [!UICONTROL Auto-Allocate] mostra a probabilidade de uma determinada experiência ser um verdadeiro vencedor em todas as experiências na atividade. Somente uma experiência vencedora (que provavelmente será a vencedora) tem um valor de confiança diferente de zero. Todos os outros provavelmente serão perdedores e exibirão 0%.

* [!UICONTROL Auto-Allocate] começa a mostrar confiança somente depois que a experiência vencedora coleta 60% de confiança. Normalmente, esses níveis de confiança aparecem em cerca de metade do tempo que um teste A/B normal levaria para ser concluído (embora esse intervalo de tempo não seja garantido). Para determinar por quanto tempo um teste A/B normal seria executado, use a [!DNL Adobe Target] [Calculadora de Tamanho da Amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): taxa de conversão do controle de plug em &quot;Índice de conversão da linha de base&quot;, &quot;5%&quot; para &quot;Aumento&quot; e 95% para &quot;Confiança&quot;. Normalmente, a confiança começa a aparecer depois que cada experiência acumulou pelo menos 50% das amostras necessárias por experiência. Isso dá uma ideia de quando a confiança começa a aparecer.

* Se o relatório mostrar 0% em todo o quadro, é provável que seja muito cedo para a atividade.

### Os emblemas &quot;Sem vencedor&quot;, &quot;Vencedor&quot; e &quot;estrela&quot; estão disponíveis para atividades de [!UICONTROL Auto-Allocate] que usam [!UICONTROL Analytics as the reporting source] (A4T)?

Os emblemas &quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot; não estão disponíveis no painel [!UICONTROL A4T] em [!DNL Analysis Workspace]. Essas medalhas também não estarão disponíveis se o mesmo relatório for visualizado em [!DNL Target]. Um emblema de &quot;estrela&quot; vencedor mostrado em um relatório [!DNL Target] para uma atividade [!UICONTROL Auto-Allocate] usando A4T deve ser ignorado.

Para obter mais informações sobre esta e outras limitações e observações, consulte [Alocação automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) no *Suporte do A4T para [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] atividades*.