---
keywords: alocação de tráfego automatizada, direcionamento, vencedor, garantia estatística, confiança, determinar vencedor, aumento, confiança, padrão, experiência padrão, alocação automática, alocação automática
description: Saiba como interpretar os resultados de uma atividade de Alocação automática A/B no Adobe [!DNL Target] examinando indicadores importantes, incluindo aumento e confiança.
title: Como interpreto os relatórios de alocação automática?
feature: Alocação automática
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: c78598da8f13f1e2c4489a317ce151779ca4be61
workflow-type: tm+mt
source-wordcount: '1136'
ht-degree: 47%

---

# Interpretar relatórios de autoalocação

Interprete os resultados de uma atividade A/B de [!UICONTROL Alocação automática] em [!UICONTROL Adobe Target] examinando indicadores importantes, incluindo aumento e confiança.

Muitos profissionais de marketing cometem o erro de declarar prematuramente uma experiência vencedora antes dos resultados indicarem claramente o vencedor. Agora facilitamos para você determinar o vencedor.

>[!NOTE]
>
>Para obter informações gerais sobre como declarar um vencedor, consulte [Dez erros comuns em testes A/B e como evitá-los](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identificar a experiência vencedora {#section_24007470CF5B4D30A06610CE8DD23CE3}

Ao usar o recurso [!UICONTROL Alocação automática], o [!DNL Target] exibe um emblema na parte superior da página da atividade, indicando &quot;Ainda não há vencedor&quot; até que a atividade atinja o número mínimo de conversões com confiança suficiente.

![Sem selo de Vencedor](/help/c-activities/automated-traffic-allocation/assets/no-winner.png)

Quando um vencedor claro é declarado, o [!DNL Target] exibe &quot;Vencedor: Experiência X&quot;.

![](assets/winner.png)

>[!NOTE]
>
>As atividades de alocação automática são projetadas para encontrar a melhor experiência entre todas as opções e não apenas para fazer comparações emparelhadas com controle.

## Garantias estatísticas da alocação automática {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

No final de uma atividade A/B, a Alocação automática garante que o vencedor determinado tenha uma taxa de falso-positivo eficaz de 5%. Isso significa que apenas 5% do tempo, o vencedor determinado não é realmente a melhor experiência entre todas as experiências na atividade. Para um teste A/A (com experiências idênticas), concluímos um teste com menos de 5% do tempo. O comportamento esperado para um teste A/A (com experiências idênticas) é para ser executado indefinidamente e, portanto, o emblema do vencedor nunca deve aparecer.

Não usamos a confiança baseada em valor p para alocação automática.

A coluna Confiança em uma atividade de Alocação automática (ilustrada abaixo) exibe a probabilidade de uma experiência ser a vencedora com margem de erro de 1% (ou seja, o algoritmo usa um efeito mínimo detectável de 1% entre a melhor e a segunda melhor taxa de conversão). Observe que o algoritmo usa [Desigualdade de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) para computar esta probabilidade.

Testes A/B normais calculam a confiança com base nos valores de p. A Alocação automática não usa valores p. Os valores de P calculam &quot;vagamente&quot; a probabilidade de que uma determinada experiência seja diferente do controle. Esses valores p podem ser usados apenas para determinar se uma experiência pode ser diferente do controle. Esses valores não podem ser usados para determinar se uma experiência é diferente de outra experiência (não de controle).

>[!IMPORTANT]
>
>O Target mostra um vencedor após um número mínimo predefinido de conversões; no entanto, a decisão final de escolher o vencedor deve sempre basear-se nos resultados da calculadora de tamanho da amostra do Adobe Target [. ](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=pt-BR) O Target não considera as taxas de conversão básicas de um site e outros aspectos importantes que são alimentados pela calculadora para determinar a duração da atividade. Como resultado, o Target pode exibir um vencedor mais cedo do que o esperado com base em um número mínimo de conversões. Para obter mais informações, consulte [Calculadora de tamanho de amostra](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Entender os relatórios de lift e confiança nas atividades de alocação automática {#lift-confidence}

Nas atividades de Alocação automática, a primeira experiência (por padrão, chamada Experiência A) é sempre definida como uma experiência de &quot;Controle&quot; na guia Relatórios . Esta experiência não é tratada como um verdadeiro controle estatístico na modelagem usada para determinar o desempenho das experiências, mas é tratada como uma referência ou uma linha de base para alguns valores no relatório.

O valor numérico &quot;Lift&quot; e os limites de 95% para cada experiência são sempre calculados com referência à experiência &quot;Control&quot; definida. A experiência de &quot;Controle&quot; definida não pode ter incentivo em relação a si mesma, portanto, um valor &quot;—&quot; em branco é reportado para essa experiência. Ao contrário dos testes A/B, nos testes de alocação automática, se uma experiência tiver um desempenho pior do que o controle definido, um valor de incentivo negativo não será reportado; em vez disso, &quot;—&quot; é exibido.

As barras de Intervalo de confiança exibidas representam o intervalo de confiança de 95% em torno da estimativa média da taxa de conversão de uma experiência. Eles também são codificados por cores em relação à experiência &quot;Controle&quot; definida. A barra da experiência de &quot;Controle&quot; fica sempre cinza. As partes dos intervalos de confiança abaixo do intervalo de confiança da experiência de &quot;Controle&quot; são coloridas em vermelho e as partes dos intervalos de confiança acima da experiência de &quot;Controle&quot; são coloridas em verde.

Um vencedor é encontrado quando o Intervalo de confiança de 95% da experiência líder não se sobrepõe a nenhuma outra experiência. A experiência vencedora é designada com um selo de estrela verde à esquerda do nome da experiência e no banner &quot;Vencedor&quot;. Quando nenhuma estrela é visível, o banner diz &quot;Ainda não há vencedor&quot; e um vencedor ainda não foi encontrado.

Um número de &quot;Confiança&quot; também é reportado ao lado da experiência líder ou vencedora atual. Esse número é relatado somente até que a Confiança da experiência líder atinja pelo menos 60%. Se exatamente duas experiências estiverem presentes no experimento de alocação automática, esse número representa o nível de confiança de que a experiência está tendo um desempenho melhor do que a outra experiência. Se mais de duas experiências estiverem presentes no experimento de alocação automática, esse número representa o nível de confiança de que a experiência está tendo um desempenho melhor do que a experiência de &quot;controle&quot; definida. Se a experiência de &quot;Controle&quot; estiver vencendo, nenhuma figura de &quot;Confiança&quot; será relatada.

## Perguntas frequentes {#section_C8E068512A93458D8C006760B1C0B6A2}

**Já passaram alguns dias na atividade. Por que todos os valores de confiança ainda estão mostrando 0%?**

Qualquer um dos motivos a seguir descreve por que 0% é exibido na coluna [!UICONTROL Confiança] do relatório para todas as atividades:

* Testes A/B manuais e Alocação automática usam estatísticas diferentes para exibir valores de confiança.

   Os testes manuais A/B usam valores p baseados no [teste t de Estudante](https://en.wikipedia.org/wiki/Student%27s_t-test). Um valor P é a probabilidade de encontrar a diferença observada (ou uma mais extrema) entre uma experiência e o controle, visto que, na realidade, não há essa diferença. Esses valores P podem ser usados somente para determinar se os dados observados estão consistentes, visto que a experiência e o controle são iguais. Esses valores não podem ser usados para determinar se uma experiência é diferente de outra experiência (não de controle).

   A Alocação automática mostra a probabilidade de uma determinada experiência ser um verdadeiro vencedor em todas as experiências na atividade. Isso significa que apenas uma experiência vencedora (que provavelmente será a vencedora) terá um valor de confiança diferente de zero. Todos os outros são mais propensos a serem perdedores e exibirão 0%.

* A Alocação automática começa a mostrar confiança somente após a experiência vencedora reunir 60% de confiança. Normalmente, esses níveis de confiança aparecem em cerca de metade do tempo que um teste A/B normal levaria para ser concluído (embora isso não seja garantido). Para determinar por quanto tempo um teste A/B normal seria executado, use uma [calculadora de tamanho de amostra](https://experienceleague.adobe.com/tools/calculator/testcalculator.html): taxa de conversão do controle de plug em &quot;Índice de conversão da linha de base&quot;, &quot;5%&quot; para &quot;Aumento&quot; e 95% para &quot;Confiança&quot;. Normalmente, a confiança começa a aparecer depois que cada experiência acumulou pelo menos 50% das amostras necessárias por experiência. Isso lhe dará uma ideia de quando a confiança começará a aparecer.
* Se o relatório mostrar 0% em todo o quadro, é provável que seja muito cedo para a atividade.
