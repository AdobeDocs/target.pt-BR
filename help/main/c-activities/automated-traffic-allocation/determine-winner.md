---
keywords: alocação automática de tráfego;direcionamento;vencedor;garantia estatística;confiança;determinar vencedor;aumento;confiança;padrão;experiência padrão;alocação automática;alocação automática
description: Descubra como interpretar os resultados da atividade A/B de [!UICONTROL Alocação automática], com foco em indicadores-chave como aumento e confiança.
title: Como Interpreto Os Relatórios De [!UICONTROL Alocação Automática]?
feature: Auto-Allocate
exl-id: 4ed00eee-8939-4958-9be6-b45a8c08afbc
TQID: 'https://experienceleague.adobe.com/o4mFGMk-M5QUvJ57kYnfjMPvVZL8l6YegJQSJyHjAxc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 174d4631b6f4a481c039bd7fff52a8e70161e19e
workflow-type: tm+mt
source-wordcount: '1357'
ht-degree: 3%
---
# Interpretar relatórios de [!UICONTROL Alocação automática] {#interpret-auto-allocate-reports}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como identificar a experiência vencedora de uma atividade **[!UICONTROL Alocação automática]**, que as estatísticas garantem que o **[!UICONTROL Alocação automática]** fornece, e como ler os números de aumento e confiança no relatório.

>[!ENDSHADEBOX]

O relatório de uma atividade A/B de **[!UICONTROL Alocação automática]** em [!DNL Adobe Target] mostra se a atividade encontrou um vencedor e quão confiante [!DNL Target] é nesse resultado. Indicadores como o emblema vencedor, o incentivo e a confiança ajudam a interpretar os resultados.

Muitos profissionais de marketing cometem o erro de declarar prematuramente uma experiência vencedora antes que os resultados indiquem um vencedor claro. [!DNL Target] facilita a identificação do vencedor. Para obter informações gerais sobre como declarar um vencedor, consulte [Dez erros comuns em testes A/B e como evitá-los](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md).

## Identificar a experiência vencedora {#identify-winner}

Quando você usa o recurso **[!UICONTROL Alocação automática]**, o [!DNL Target] exibe um selo na parte superior da página de atividades. O selo indica &quot;Ainda não há vencedor&quot; até que a atividade atinja o número mínimo de conversões com confiança suficiente.

![Sem selo de Vencedor](/help/main/c-activities/automated-traffic-allocation/assets/no-winner-new.png)

Quando um vencedor claro é declarado, [!DNL Target] exibe o emblema &quot;Vencedor: Experiência *X*&quot;.

![Selo do vencedor](/help/main/c-activities/automated-traffic-allocation/assets/winner-new.png)

O selo vencedor também aparece no pop-up de informações de uma atividade na lista **[!UICONTROL Atividades]**, para que você possa ver o status de uma atividade **[!UICONTROL Alocação automática]** sem abri-la.

>[!NOTE]
>
>As atividades de **[!UICONTROL Alocação automática]** foram projetadas para encontrar a melhor experiência entre todas as opções, não apenas para fazer comparações emparelhadas com o controle.

## Garantias estatísticas de [!UICONTROL Alocação automática] {#statistical-guarantees}

No final de uma atividade A/B, a **[!UICONTROL Alocação automática]** garante que o vencedor determinado tenha uma taxa efetiva de falso-positivo de 5%. Isso significa que apenas 5% do tempo, o vencedor determinado não é realmente a melhor experiência entre todas as experiências na atividade.

Para um [teste A/A](/help/main/c-activities/t-test-ab/aa-testing.md) (com experiências idênticas), [!DNL Target] conclui um teste menos de 5% do tempo. O comportamento esperado para um teste A/A é executar indefinidamente, de modo que o símbolo vencedor nunca deve aparecer.

### Confiança e valores p {#confidence-p-values}

[!DNL Target] não usa confiança baseada em valor p para **[!UICONTROL Alocação automática]**. A coluna **[!UICONTROL Confiança]** em uma atividade de **[!UICONTROL Alocação automática]** exibe a probabilidade de uma experiência ser a vencedora dentro de uma margem de erro de 1%. O algoritmo usa um efeito mínimo detectável de 1% entre as melhores e as segundas melhores taxas de conversão, e usa a [Desigualdade de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) para calcular essa probabilidade.

Os testes A/B normais calculam a confiança com base em valores p, que calculam &quot;vagamente&quot; a probabilidade de uma determinada experiência ser diferente do controle. Esses valores p podem ser usados apenas para determinar se uma experiência pode ser diferente do controle. Eles não podem ser usados para determinar se uma experiência é diferente de outra experiência (não o controle).

>[!IMPORTANT]
>
>[!DNL Target] mostra um vencedor após um número mínimo predefinido de conversões. No entanto, a decisão final de escolher o vencedor deve sempre ser baseada nos resultados da Calculadora de tamanho da amostra [!DNL Adobe Target]. [!DNL Target] não considera as taxas de conversão base de um site e outros aspectos importantes que são alimentados na calculadora para determinar a duração da atividade. Como resultado, [!DNL Target] pode exibir um vencedor antes do garantido com base em um número mínimo de conversões. Para obter mais informações, consulte [Calculadora de Tamanho da Amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

## Entender os relatórios de incentivo e confiança {#lift-confidence}

A guia **[!UICONTROL Relatórios]** de uma atividade de **[!UICONTROL Alocação automática]** mostra os seguintes números:

| Figura | Descrição |
|---|---|
| **Experiência de controle** | A primeira experiência (chamada de Experiência A por padrão) é sempre definida como a experiência &quot;Controle&quot; na guia **[!UICONTROL Relatórios]**. Essa experiência não é tratada como um verdadeiro controle estatístico no modelo usado para determinar o desempenho das experiências, mas é tratada como uma referência ou linha de base para alguns números no relatório. |
| **Aumento** | O valor &quot;Lift&quot; e os limites de 95% de cada experiência são sempre calculados com referência à experiência &quot;Control&quot; definida. A experiência de &quot;Controle&quot; não pode ter aumento relativo a si mesma, portanto, o relatório mostra um valor &quot;—&quot; em branco para essa experiência.<br>Ao contrário dos testes A/B, nos testes **[!UICONTROL Alocação automática]**, se uma experiência tiver um desempenho pior do que o controle definido, um valor de aumento negativo não será relatado. Em vez disso, &quot;—&quot; é exibido. |
| **Intervalos de confiança** | As barras **[!UICONTROL Intervalo de confiança]** exibidas representam o intervalo de confiança de 95% em torno da estimativa média do índice de conversão de uma experiência. As barras são codificadas por cores em relação à experiência &quot;Controle&quot; definida:<ul><li>A barra da experiência de &quot;Controle&quot; é sempre cinza.</li><li>As partes dos intervalos de confiança abaixo do intervalo de confiança da experiência de &quot;Controle&quot; são vermelhas.</li><li>As partes dos intervalos de confiança acima do intervalo de confiança da experiência de &quot;Controle&quot; estão em verde.</li></ul> |
| **Vencedor** | Um vencedor é encontrado quando o **[!UICONTROL Intervalo de confiança]** de 95% da experiência principal não coincide com nenhuma outra experiência. A experiência vencedora é designada com um selo de estrela verde à esquerda do nome da experiência e no banner &quot;Vencedor&quot;. Quando nenhuma estrela estiver visível, o banner exibirá &quot;Ainda não há vencedor&quot; e um vencedor ainda não foi encontrado. |
| **Número de confiança** | Um número de &quot;Confiança&quot; também é relatado ao lado da experiência principal ou vencedora no momento. Este número é relatado somente até que a **[!UICONTROL Confiança]** da experiência principal atinja pelo menos 60%.<ul><li>Se duas experiências estiverem presentes na atividade **[!UICONTROL Alocação automática]**, o número representará o nível de confiança de que a experiência está tendo um desempenho melhor do que a outra experiência.</li><li>Se mais de duas experiências estiverem presentes, o número representará o nível de confiança de que a experiência está tendo um desempenho melhor do que a experiência de &quot;Controle&quot; definida.</li><li>Se a experiência de &quot;Controle&quot; estiver ganhando, nenhum valor de &quot;Confiança&quot; será relatado.</li></ul> |

## Perguntas frequentes {#faq}

Considere as respostas a seguir para perguntas frequentes.

+++ Já se passaram alguns dias na atividade. Por que todos os valores de confiança ainda estão mostrando 0%?

Qualquer um dos motivos a seguir descreve por que 0% é exibido na coluna **[!UICONTROL Confiança]** do relatório para todas as experiências:

* Testes A/B manuais e **[!UICONTROL Alocação automática]** usam estatísticas diferentes para exibir valores de **[!UICONTROL Confiança]**.

  Os testes A/B manuais usam valores p com base no [teste t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test). Um valor p é a probabilidade de encontrar a diferença observada (ou uma mais extrema) entre uma experiência e o controle, uma vez que, na realidade, não há essa diferença. Esses valores p podem ser usados apenas para determinar se os dados observados estão consistentes, visto que uma determinada experiência e o controle são iguais. Eles não podem ser usados para determinar se uma experiência é diferente de outra experiência (não o controle).

  **[!UICONTROL Alocação automática]** mostra a probabilidade de uma determinada experiência ser um verdadeiro vencedor em todas as experiências na atividade. Somente uma experiência vencedora (que provavelmente será a vencedora) tem um valor de confiança diferente de zero. Todos os outros provavelmente serão perdedores e exibirão 0%.

* A **[!UICONTROL Alocação automática]** começa a mostrar confiança somente depois que a experiência vencedora coleta 60% de confiança. Normalmente, esses níveis de confiança aparecem em cerca de metade do tempo que um teste A/B normal levaria para ser concluído (embora esse intervalo de tempo não seja garantido). Para determinar por quanto tempo um teste A/B normal seria executado, use a [!DNL Adobe Target] [Calculadora de Tamanho da Amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6): insira a taxa de conversão do controle em &quot;Taxa de conversão da linha de base&quot;, &quot;5%&quot; para &quot;Aumento&quot; e 95% para &quot;Confiança&quot;. Normalmente, a confiança começa a aparecer depois que cada experiência acumula pelo menos 50% das amostras necessárias por experiência. Isso dá uma ideia de quando a confiança começa a aparecer.

* Se o relatório mostrar 0% em todos os segmentos, é provável que seja muito cedo na atividade.

+++

+++ Os emblemas &quot;Sem vencedor&quot;, &quot;Vencedor&quot; e &quot;estrela&quot; estão disponíveis para atividades de [!UICONTROL Alocação automática] que usam o [!UICONTROL Analytics] como fonte de relatórios (A4T)?

Os emblemas &quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot; aparecem na janela pop-up de informações da atividade na lista **[!UICONTROL Atividades]**. Eles não aparecem no painel **[!UICONTROL A4T]** em [!DNL Analysis Workspace] ou quando você exibe o mesmo relatório em [!DNL Target]. Se um relatório [!DNL Target] de uma atividade A4T **[!UICONTROL Alocação automática]** mostrar um símbolo de &quot;estrela&quot; vencedor, ignore-o.

Para obter mais informações sobre esta e outras limitações e observações, consulte [Alocação automática](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md#aa) no *Suporte do A4T para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades*.

+++
