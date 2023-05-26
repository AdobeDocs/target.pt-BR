---
keywords: alocação automática de tráfego;direcionamento;vencedor;garantia estatística;confiança;determinar vencedor;aumento;confiança;padrão;experiência padrão;alocação automática;alocação automática
description: Saiba como interpretar os resultados de uma atividade A/B de Alocação automática no Adobe [!DNL Target] examinando indicadores importantes, incluindo o aumento e a confiança.
title: Como Interpreto Os Relatórios De Alocação Automática?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
source-git-commit: 4564e0b95bbd19f20c75e5e83d452d12a5403083
workflow-type: tm+mt
source-wordcount: '1222'
ht-degree: 44%

---

# Interpretar relatórios de autoalocação

Interpretar os resultados de um [!UICONTROL Alocação automática] Atividade de A/B no [!UICONTROL Adobe Target] examinando indicadores importantes, incluindo o aumento e a confiança.

Muitos profissionais de marketing cometem o erro de declarar prematuramente uma experiência vencedora antes dos resultados indicarem claramente o vencedor. Agora facilitamos para você determinar o vencedor.

>[!NOTE]
>
>Para obter informações gerais sobre como declarar um vencedor, consulte [Dez erros comuns em testes A/B e como evitá-los](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identificar a experiência vencedora {#section_24007470CF5B4D30A06610CE8DD23CE3}

Ao usar o recurso [!UICONTROL Alocação automática], o [!DNL Target] exibe um emblema na parte superior da página da atividade, indicando &quot;Ainda não há vencedor&quot; até que a atividade atinja o número mínimo de conversões com confiança suficiente.

![Sem selo de Vencedor](/help/main/c-activities/automated-traffic-allocation/assets/no-winner.png)

Quando um vencedor claro é declarado, o [!DNL Target] exibe &quot;Vencedor: Experiência X&quot;.

![imagem do vencedor](assets/winner.png)

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
>O Target mostra um vencedor após um número mínimo predefinido de conversões; no entanto, a decisão final de escolher o vencedor deve sempre estar nos resultados do [!DNL Adobe Target] Calculadora de tamanho da amostra. [!DNL Target] O não considera as taxas de conversão básicas de um site e outros aspectos importantes que são alimentados na calculadora para determinar a duração da atividade. Como resultado, o Target pode exibir um vencedor antes do que o garantido com base em um número mínimo de conversões. Para obter mais informações, consulte [Calculadora de tamanho da amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Entender os relatórios de aumento e confiança nas atividades de Alocação automática {#lift-confidence}

Nas atividades de Alocação automática, a primeira experiência (por padrão, chamada de Experiência A) é sempre definida como uma experiência de &quot;Controle&quot; na guia Relatórios. Essa experiência não é tratada como um verdadeiro controle estatístico no modelo usado para determinar o desempenho das experiências, mas é tratada como uma referência ou linha de base para alguns números no relatório.

O valor numérico &quot;Lift&quot; e os limites de 95% para cada experiência são sempre calculados com referência à experiência &quot;Control&quot; definida. A experiência de &quot;Controle&quot; definida não pode ter aumento relativo a si mesma. Portanto, um valor &quot;—&quot; em branco é relatado para essa experiência. Ao contrário dos testes A/B, nos testes de Alocação automática, se uma experiência tiver um desempenho pior do que o controle definido, um valor de aumento negativo não será relatado; em vez disso, &quot;—&quot; será exibido.

As barras de Intervalo de confiança exibidas representam o intervalo de confiança de 95% em torno da estimativa média da taxa de conversão de uma experiência. Eles também são codificados por cores em relação à experiência &quot;Controle&quot; definida. A barra de experiência &quot;Controle&quot; está sempre em cinza. As partes dos intervalos de confiança abaixo do intervalo de confiança da experiência &quot;Controle&quot; são coloridas em vermelho e as partes dos intervalos de confiança acima da experiência &quot;Controle&quot; são coloridas em verde.

Um vencedor é encontrado quando o Intervalo de confiança de 95% da experiência principal não se sobrepõe a nenhuma outra experiência. A experiência vencedora é designada com um selo de estrela verde à esquerda do nome da experiência e no banner &quot;Vencedor&quot;. Quando nenhuma estrela estiver visível, o banner exibirá &quot;Ainda não há vencedor&quot; e um vencedor ainda não foi encontrado.

Um número de &quot;Confiança&quot; também é relatado ao lado da experiência principal ou vencedora no momento. Esse número é relatado somente até que a confiança da experiência líder atinja pelo menos 60%. Se exatamente duas experiências estiverem presentes no experimento de Alocação automática, esse número representará o nível de confiança de que a experiência está tendo um desempenho melhor do que a outra experiência. Se mais de duas experiências estiverem presentes no experimento de Alocação automática, esse número representará o nível de confiança de que a experiência está tendo um desempenho melhor do que a experiência de &quot;Controle&quot; definida. Se a experiência de &quot;Controle&quot; estiver ganhando, nenhum valor de &quot;Confiança&quot; será relatado.

## Perguntas frequentes {#section_C8E068512A93458D8C006760B1C0B6A2}

Considere as seguintes respostas às perguntas frequentes:

### Já passaram alguns dias na atividade. Por que todos os valores de confiança ainda estão mostrando 0%?

Qualquer um dos motivos a seguir descreve por que 0% é exibido na coluna [!UICONTROL Confiança] do relatório para todas as atividades:

* Testes A/B manuais e Alocação automática usam estatísticas diferentes para exibir valores de confiança.

   Os testes A/B manuais usam valores p com base em [Teste t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Um valor P é a probabilidade de encontrar a diferença observada (ou uma mais extrema) entre uma experiência e o controle, visto que, na realidade, não há essa diferença. Esses valores P podem ser usados somente para determinar se os dados observados estão consistentes, visto que a experiência e o controle são iguais. Esses valores não podem ser usados para determinar se uma experiência é diferente de outra experiência (não de controle).

   A Alocação automática mostra a probabilidade de uma determinada experiência ser um verdadeiro vencedor em todas as experiências na atividade. Isso significa que apenas uma experiência vencedora (que provavelmente será a vencedora) terá um valor de confiança diferente de zero. Todos os outros são mais propensos a serem perdedores e exibirão 0%.

* A Alocação automática começa a mostrar confiança somente após a experiência vencedora reunir 60% de confiança. Normalmente, esses níveis de confiança aparecem em cerca de metade do tempo que um teste A/B normal levaria para ser concluído (embora isso não seja garantido). Para determinar por quanto tempo um teste A/B normal seria executado, use o [!DNL Adobe Target] [Calculadora de tamanho da amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): taxa de conversão do controle de plug em &quot;Índice de conversão da linha de base&quot;, &quot;5%&quot; para &quot;Aumento&quot; e 95% para &quot;Confiança&quot;. Normalmente, a confiança começa a aparecer depois que cada experiência acumulou pelo menos 50% das amostras necessárias por experiência. Isso lhe dará uma ideia de quando a confiança começará a aparecer.

* Se o relatório mostrar 0% em todo o quadro, é provável que seja muito cedo para a atividade.

### Os emblemas “Sem vencedor”, “Vencedor” e “estrela” estão disponíveis para atividades de [!UICONTROL Alocação automática] que usam o [!UICONTROL Analytics como fonte de relatórios] (A4T)?

Os emblemas &quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot; não estão disponíveis no momento no [!UICONTROL A4T] painel no [!DNL Analysis Workspace]. Esses emblemas também não estarão disponíveis se o mesmo relatório for visualizado em [!DNL Target]. Um emblema de &quot;estrela&quot; vencedor mostrado em um [!DNL Target] relatório para um [!UICONTROL Alocação automática] A atividade usando A4T deve ser ignorada.

Para obter mais informações sobre essa e outras limitações e observações, consulte [Alocação automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) in *Suporte do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades*.


