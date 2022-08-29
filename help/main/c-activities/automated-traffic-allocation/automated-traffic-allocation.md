---
keywords: alocação automática de tráfego, direcionamento, Aumentar contagem e manter o usuário na atividade, alocação de tráfego, alocação automática, alocação automática
description: Saiba como usar uma atividade de alocação automática no Adobe [!DNL Target] que identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor.
title: O que é uma atividade de alocação automática?
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 66c662e367b64ca51c5d9246cb097a12755d9aff
workflow-type: tm+mt
source-wordcount: '3567'
ht-degree: 50%

---

# Visão geral da [!UICONTROL Alocação automática]

Um [!UICONTROL Alocação automática] atividade em [!DNL Adobe Target] identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor a fim de aumentar as conversões enquanto o teste continua a ser executado e aprendido.

Ao criar uma atividade A/B usando o fluxo de trabalho guiado de três etapas, é possível escolher a variável [!UICONTROL Alocação automática para a melhor experiência] opção.

## O desafio {#section_85D5A03637204BACA75E19646162ACFF}

Os testes A/B padrão têm um custo inerente. Você deve gastar o tráfego para medir o desempenho de cada experiência e, por meio de análise, descobrir a experiência vencedora. A distribuição do tráfego permanece fixa mesmo depois de você reconhecer que algumas experiências estão superando outras. Além disso, é complicado descobrir o tamanho da amostra, e a atividade deve ser executada em sua totalidade para que você possa agir em um vencedor. E ainda há uma chance de o vencedor identificado não ser um verdadeiro vencedor.

## A solução: [!UICONTROL Alocação automática] {#section_98388996F0584E15BF3A99C57EEB7629}

[!UICONTROL A alocação automática reduz esse custo e a sobrecarga de determinar uma experiência vencedora. ] [!UICONTROL A alocação automática monitora o desempenho da métrica de meta de todas as experiências e envia mais novos participantes para as experiências de alto desempenho proporcionalmente. ] Há tráfego suficiente reservado para explorar as outras experiências. Você pode ver os benefícios do teste nos resultados, mesmo enquanto a atividade está em execução: a otimização e o aprendizado ocorrem paralelamente.

[!UICONTROL A alocação automática move os visitantes para experiências vencedoras gradativamente, em vez de exigir que você aguarde o fim de uma atividade para determinar um vencedor. ] Você se beneficia do incentivo mais rapidamente porque os participantes da atividade que teriam sido enviados para experiências de menor sucesso recebem experiências vencedoras potenciais.

Um teste A/B normal em [!DNL Target] mostra apenas comparações emparelhadas de desafiantes com controle. Por exemplo, se uma atividade tiver experiências: A, B, C e D, onde A é o controle, um [!DNL Target] O teste A/B compararia A versus B, A versus C e A versus D.

Nesses testes, a maioria dos produtos, incluindo [!DNL Target]use um [Teste t do galês](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} para produzir confiança baseada em valor p. Este valor de confiança é então usado para determinar se o desafiante é suficientemente diferente do controle. No entanto, [!DNL Target] O não executa automaticamente as comparações implícitas (B versus C, B versus D e C versus D) necessárias para encontrar a &quot;melhor&quot; experiência. Como resultado, o profissional de marketing deve analisar manualmente os resultados para determinar a &quot;melhor&quot; experiência.

[!UICONTROL A alocação automática executa todas as comparações implícitas entre as experiências e produz um vencedor &quot;verdadeiro&quot;. ] Não há noção de experiência de &quot;controle&quot; no teste.

[!UICONTROL Alocação automática] aloca novos visitantes de forma inteligente para experiências até que o intervalo de confiança da melhor experiência não se sobreponha ao intervalo de confiança de qualquer outra experiência. Normalmente, esse processo pode produzir falsos positivos, mas [!UICONTROL Alocação automática] O usa intervalos de confiança com base em [Desigualdade de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29) que compensa avaliações repetidas. Neste ponto, há um verdadeiro vencedor. When [!UICONTROL Alocação automática] para, desde que não haja uma dependência de tempo substancial para os visitantes que chegam à página, há pelo menos 95% de chance de que [!UICONTROL Alocação automática] retorna uma experiência cuja resposta verdadeira não seja pior do que 1% (relativa) menos do que a verdadeira resposta da experiência vencedora.

## Quando usar [!UICONTROL Alocação automática] versus A/B ou [!UICONTROL Automated Personalization] {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* Use **[!UICONTROL Alocação automática]** quando quiser otimizar sua atividade a partir do início e identificar as experiências vencedoras o mais rapidamente possível. Quando experiências de alto desempenho são proporcionadas com mais frequência, o desempenho geral da atividade aumenta.
* Use um padrão **[Use o teste A/B](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)** quando quiser caracterizar o desempenho de todas as experiências antes de otimizar o site. Um teste A/B ajuda a classificar todas as experiências, enquanto que [!UICONTROL Alocação automática] O encontra os melhores desempenhos, mas não garante a diferenciação entre os de desempenho mais baixo.
* Use [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) quando quiser algoritmos de otimização da mais alta complexidade, como modelos de aprendizado automatizado que fazem previsões com base em atributos de perfil individuais. [!UICONTROL Alocação automática] observa o comportamento agregado das experiências (assim como testes A/B padrão) e não diferencia os visitantes.

## Principais benefícios {#section_0913BF06F73C4794862561388BBDDFF0}

* Mantém o rigor de um teste A/B
* Encontra um vencedor estatisticamente significativo mais rapidamente do que um teste A/B manual
* Fornece um lift médio de campanha maior que de um teste A/B manual

## Terminologia {#section_670F8785BA894745B43B6D4BFF953188}

Os termos a seguir são úteis quando falamos [!UICONTROL Alocação automática]:

**Multi-armed bandit:** Uma abordagem [multi-armed bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit) à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado.

## Como o algoritmo funciona {#section_ADB69A1C7352462D98849F2918D4FF7B}

A lógica geral subjacente [!UICONTROL Alocação automática] incorpora o desempenho medido (como a taxa de conversão) e os intervalos de confiança dos dados cumulativos. Ao contrário de um teste A/B padrão em que o tráfego é dividido igualmente entre experiências, [!UICONTROL Alocação automática] altera a alocação de tráfego entre experiências.

* 80% dos visitantes são alocados usando a lógica inteligente descrita abaixo.
* 20% dos visitantes são distribuídos aleatoriamente em todas as experiências para se adaptarem à mudança de comportamento do visitante.

A abordagem multi-armed bandit mantém algumas experiências livre para exploração ao mesmo tempo em que aproveita as experiências que têm um bom desempenho. Mais novos visitantes são colocados em experiências de melhor desempenho enquanto preservam a capacidade de reagir a mudanças nas condições. Esses modelos são atualizados pelo menos uma vez por hora para garantir a reação do modelo aos dados mais recentes.

À medida que mais visitantes entram na atividade, algumas experiências começam a ter mais êxito, e mais tráfego é enviado para as experiências bem-sucedidas. 20% do tráfego continua sendo distribuído aleatoriamente para explorar todas as experiências. Se uma das experiências de baixo desempenho começar a funcionar melhor, mais tráfego será alocado para essa experiência. Ou, se o sucesso de uma atividade de desempenho mais alto diminui, menos tráfego será alocado para essa experiência. Por exemplo, se um evento faz com que os visitantes procurem informações diferentes no site de sua mídia, ou se as vendas no fim de semana em seu site de vendas oferecem resultados diferentes.

A ilustração a seguir representa como pode ser o desempenho do algoritmo durante um teste com quatro experiências:

![](assets/auto-allocate.png)

A ilustração mostra como o tráfego alocado para cada experiência progride ao longo de várias rodadas do tempo de atividade até que um vencedor claro seja determinado.

| Arredondar | Descrição |
|--- |--- |
| ![Aquecimento](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png) | **Rodada de aquecimento (0):** durante a rodada de aquecimento, cada experiência recebe a mesma distribuição de tráfego até que cada experiência na atividade tenha um mínimo de 1.000 visitantes e 50 conversões.<ul><li>Experiência A=25%</li><li>Experiência B=25%</li><li>Experiência C=25%</li><li>Experiência D=25%</li></ul>Após cada experiência receber 1.000 visitantes e 50 conversões, o Target inicia a alocação automática de tráfego. Todas as alocações acontecem em rodadas e duas experiências são escolhidas para cada rodada.<br>Apenas duas experiências avançam para a próxima rodada: D e C.<br>Seguir em frente significa que as duas experiências recebem 80% do tráfego igualmente. As outras duas experiências continuam a participar, mas são servidas apenas como parte da alocação de tráfego aleatório de 20% à medida que novos visitantes entram na atividade.<br>Todas as alocações são atualizadas a cada hora (mostradas por arredondamentos ao longo do eixo x acima). Após cada rodada, os dados acumulados são comparados. |
| ![Rodada 1](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png) | **Rodada 1:** nesta rodada, 80% do tráfego é alocado às experiências C e D (40% cada). 20% do tráfego é alocado aleatoriamente para experiências A, B, C e D (5% cada). Durante esta rodada, a experiência A tem um excelente desempenho.<ul><li>O algoritmo escolhe a experiência D para avançar para a próxima rodada porque tem a taxa de conversão mais alta (conforme indicado por na escala vertical de cada atividade).</li><li>O algoritmo escolhe a experiência A para avançar também porque tem o limite superior mais alto do intervalo de confiança de 95% de Bernstein das experiências restantes.</li></ul>As experiências D e A seguem em frente. |
| ![Rodada 2](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png) | **Rodada 2:** nesta rodada, 80% do tráfego é alocado às experiências A e D (40% cada). 20% do tráfego é alocado aleatoriamente, portanto, isso significa que A, B, C e D recebem 5% cada um. Durante esta rodada, a experiência B tem um excelente desempenho.<ul><li>O algoritmo escolhe a experiência D para avançar para a próxima rodada porque tem a taxa de conversão mais alta (conforme indicado por na escala vertical de cada atividade).</li><li>O algoritmo escolhe a experiência B para avançar também porque tem o limite superior mais alto do intervalo de confiança de 95% de Bernstein das experiências restantes.</li></ul>As experiências D e B seguem em frente. |
| ![Rodada 3](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png) | **Rodada 3:** nesta rodada, 80% do tráfego é alocado às experiências B e D (40% cada). 20% do tráfego é alocado aleatoriamente, portanto, isso significa que A, B, C e D recebem 5% cada um. Durante esta ronda, a experiência D continua a ter um bom desempenho e a experiência C tem um excelente desempenho.<ul><li>O algoritmo escolhe a experiência D para avançar para a próxima rodada porque tem a taxa de conversão mais alta (conforme indicado por na escala vertical de cada atividade).</li><li>O algoritmo escolhe a experiência C para avançar também porque tem o limite superior mais alto do intervalo de confiança de 95% de Bernstein das experiências restantes.</li></ul>As experiências D e C seguem em frente. |
| ![Rodada 4](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png) | **Rodada 4:** nesta rodada, 80% do tráfego é alocado às experiências C e D (40% cada). 20% do tráfego é alocado aleatoriamente, portanto, isso significa que A, B, C e D recebem 5% cada um. Durante esta rodada, a experiência C tem um excelente desempenho.<ul><li>O algoritmo escolhe a experiência C para avançar para a próxima rodada porque tem a taxa de conversão mais alta (conforme indicado por na escala vertical de cada atividade).</li><li>O algoritmo escolhe a experiência D para avançar também porque tem o limite superior mais alto do intervalo de confiança de 95% de Bernstein das experiências restantes.</li></ul>As experiências C e D seguem em frente. |
| ![Rodada n](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png) | **Rodada n**: Conforme a atividade avança, uma experiência de alto desempenho começa a surgir e o processo continua até que haja uma experiência vencedora. Quando o intervalo de confiança da experiência com a taxa de conversão mais alta não coincide com o intervalo de confiança de qualquer outra experiência, ele é rotulado como vencedor. A [símbolo é exibido na página da atividade vencedora](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) e na [!UICONTROL Atividade] lista.<ul><li>O algoritmo escolhe a experiência C como o vencedor claro</li></ul>Nesse ponto, o algoritmo serve 80% do tráfego para a experiência C, enquanto 20% do tráfego continua a ser servido aleatoriamente para todas as experiências (A, B, C e D). No total, C recebe 85% do tráfego. No caso improvável de que o intervalo de confiança do vencedor comece a se sobrepor novamente, o algoritmo reverte para o comportamento da rodada 4 acima.<br>**Importante:** se você escolhesse manualmente um vencedor no início do processo, teria sido fácil escolher a experiência errada. Por esse motivo, é uma prática recomendada esperar até que o algoritmo determine a experiência vencedora. |

>[!NOTE]
>
>Se uma atividade tiver apenas duas experiências, ambas as experiências receberão tráfego igual até [!DNL Target] encontra uma experiência vencedora com 75% de confiança. Nesse momento, dois terços do tráfego são alocados para o vencedor e um terço para o perdedor. Depois disso, quando uma experiência atinge 95% de confiança, 90% do tráfego é alocado ao vencedor e 10% é alocado ao perdedor. [!DNL Target] O sempre mantém algum tráfego sendo enviado para a experiência &quot;perdedora&quot; para evitar falsos positivos no final (ou seja, manter alguma exploração).

Depois de um [!UICONTROL Alocação automática] estiver ativada, as seguintes operações da interface do usuário não serão permitidas:

* Alternar o modo &quot;Alocação de tráfego&quot; para &quot;Manual&quot;
* Alterar o tipo de métrica de meta
* Alterar as opções no painel &quot;Configurações avançadas&quot;

## Veja como a alocação automática funciona

Para obter mais informações, consulte [A alocação automática pode fornecer resultados de teste mais rápidos e receita maior do que um teste manual](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md)

## Avisos {#section_5C83F89F85C14FD181930AA420435E1D}

**O [!UICONTROL Alocação automática] O recurso funciona com apenas uma configuração de métrica avançada: [!UICONTROL Aumentar a contagem e manter o usuário na atividade]**

As seguintes configurações avançadas de métrica não são suportadas: [!UICONTROL Contagem de incrementos], [!UICONTROL Liberar usuário], [!UICONTROL Permitir Reentrada e Aumentar Contagem]e [!UICONTROL Liberar usuário e impedir reentrada].

**Visitantes que retornam com frequência podem aumentar as taxas de conversão da experiência.**

Se um visitante que vê a experiência A retorna com frequência e faz conversão várias vezes, a Índice de conversão (CR) da experiência A aumenta artificialmente. Compare esse resultado com a experiência B, onde os visitantes são convertidos, mas não retornam com frequência. Como resultado, o CR da experiência A parece melhor do que o CR da experiência B, de modo que os novos visitantes têm mais probabilidade de ser alocados a A do que a B. Se você optar por contar uma vez por participante, o CR de A e o CR de B podem ser idênticos.

Se visitantes recorrentes são distribuídos aleatoriamente, seu efeito nas taxas de conversão tem mais probabilidade de ser uniformizado. Para amenizar esse efeito, considere alterar o método de contagem da métrica de meta para contar somente uma vez por participante.

**Diferencia entre os profissionais de alto desempenho, não entre os de baixo desempenho.**

[!UICONTROL A alocação automática é boa em diferenciar entre experiências de alto desempenho (e encontrar uma vencedora). ] Pode ser que algumas vezes não haja diferenciação suficiente entre as experiências de desempenho inferior.

Se quiser produzir uma diferenciação estatisticamente significativa entre todas as experiências, considere usar o modo de alocação de tráfego manual.

**As taxas de conversão associadas ao tempo (ou que variam de acordo com o contexto) podem distorcer as quantidades de alocação.**

Alguns fatores que podem ser ignorados durante um teste A/B padrão, pois afetam todas as experiências igualmente, não podem ser ignorados em um [!UICONTROL Alocação automática] teste. O algoritmo está sujeito às taxas de conversão observadas. Estes são exemplos de fatores que podem afetar o desempenho das experiências de maneira uniforme:

* Experiências com relevância contextual variável (tempo, local, gênero e assim por diante).

   Por exemplo:

   * &quot;Graças a Deus é sexta-feira&quot; resulta em maiores conversões na sexta-feira
   * &quot;Impulsione sua segunda-feira&quot; tem conversão mais alta na segunda-feira
   * &quot;Prepare-se para um inverno da costa leste&quot; oferece conversão mais alta na costa leste ou em locais afetados pelo inverno

O uso de experiências com relevância contextual variável pode distorcer os resultados em uma [!UICONTROL Alocação automática] teste mais do que em um teste A/B porque o teste A/B analisa os resultados durante um período mais longo.

* Experiências com atrasos de conversão variáveis, possivelmente devido à urgência da mensagem.

   Por exemplo, &quot;O desconto de 30% termina hoje&quot; avisa o visitante para converter hoje, mas &quot;50% de desconto na primeira compra&quot; não cria o mesmo senso de urgência.

## Perguntas frequentes {#section_0E72C1D72DE74F589F965D4B1763E5C3}

Consulte as seguintes perguntas frequentes e respostas ao trabalhar com a [!UICONTROL Alocação automática] atividades:

### Does [!UICONTROL Analytics para Target] Suporte (A4T) [!UICONTROL Alocação automática] atividades?

Sim. Para obter mais informações, consulte [Suporte ao A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

### Os visitantes recorrentes são realocados automaticamente a experiências de alto desempenho?

Não. Somente novos visitantes são alocados automaticamente. Os visitantes recorrentes continuam vendo sua experiência original para proteger a validade do teste A/B.

### Como o algoritmo lida com falsos positivos?

O algoritmo garante uma confiança de 95% ou taxa de 5% de falso-positivo, se você esperar até que o emblema vencedor apareça.

### Quando [!UICONTROL Alocação automática] começar a alocar tráfego?

O algoritmo começa a funcionar depois que todas as experiências na atividade têm um mínimo de 1.000 visitantes e 50 conversões.

### Qual é o nível de dinamismo do aproveitamento pelo algoritmo?

80% do tráfego é veiculado usando [!UICONTROL Alocação automática] e 20% do tráfego é distribuído aleatoriamente. Quando um vencedor é identificado, todos os 80% do tráfego vão para ele, enquanto todas as experiências continuam recebendo tráfego como parte dos 20%, incluindo a experiência vencedora.

### As experiências perdedoras são exibidas?

Sim. A abordagem multi-armed bandit garante que pelo menos 20% do tráfego seja reservado para explorar a mudança nos padrões ou nas taxas de conversão em todas as experiências.

### O que acontece com atividades com longos atrasos de conversão?

Desde que todas as experiências que estão sendo otimizadas passem por atrasos semelhantes, o comportamento é o mesmo de uma atividade com um ciclo de conversão mais rápido. No entanto, é necessário mais tempo para atingir o limite de conversão 50 antes do início do processo de alocação de tráfego.

### Como [!UICONTROL Alocação automática] diferente de [!UICONTROL Automated Personalization]?

[!UICONTROL A personalização automatizada usa os atributos de perfil de cada visitante para determinar a melhor experiência. ] Ao fazer isso, ela não apenas otimiza, mas também personaliza a atividade para esse usuário.

[!UICONTROL Alocação automática], por outro lado, é um teste A/B que produz um vencedor agregado (a experiência mais popular, mas não necessariamente a experiência mais eficaz para cada visitante).

### Os visitantes recorrentes aumentam a taxa de conversão em minha métrica de sucesso?

Atualmente, a lógica favorece visitantes que convertem rapidamente ou visitam com mais frequência, pois esses visitantes aumentam temporariamente a taxa de conversão geral da experiência à qual pertencem. O algoritmo se ajusta frequentemente, então o aumento na taxa de conversão é amplificado a cada instantâneo. Se o site recebe vários visitantes recorrentes, suas conversões podem aumentar potencialmente a taxa de conversão geral da experiência à qual eles pertencem. Há uma boa chance de os visitantes recorrentes serem distribuídos aleatoriamente; nesse caso, o efeito agregado (maior incentivo) é uniformizado. Para amenizar esse efeito, considere alterar o método de contagem da métrica de sucesso para contar somente uma vez por participante.

### Posso usar a calculadora de tamanho de amostra ao usar [!UICONTROL Alocação automática] para estimar quanto tempo a atividade leva para identificar o vencedor?

Você pode usar o [calculadora de tamanho da amostra](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=pt-BR) para obter uma estimativa de quanto tempo o teste será executado. (Assim como em testes A/B tradicionais, aplique a correção de Bonferroni se estiver testando mais de duas ofertas ou mais de uma métrica/hipótese de conversão.) Essa calculadora foi projetada para o tradicional teste A/B de horizonte fixo e fornece apenas uma estimativa. Uso da calculadora para um [!UICONTROL Alocação automática] atividade é opcional porque [!UICONTROL Alocação automática] declara um vencedor para você. Você não precisa escolher um ponto fixo no tempo para ver os resultados do teste. Os valores fornecidos são sempre estatisticamente válidos. Em nossos experimentos, encontramos o seguinte:
* Ao testar exatamente duas experiências, [!UICONTROL Alocação automática] encontra um vencedor mais rapidamente do que o teste de horizonte fixo (ou seja, o período sugerido pela calculadora de tamanho de amostra) quando a diferença de desempenho entre experiências é grande. No entanto, [!UICONTROL Alocação automática] pode exigir mais tempo para identificar um vencedor quando a diferença de desempenho entre as experiências é pequena. Nesses casos, os testes com horizonte fixo teriam normalmente terminado sem um resultado estatisticamente significativo.
* Ao testar mais de duas experiências, [!UICONTROL Alocação automática] encontra um vencedor mais rapidamente do que um teste de horizonte fixo (ou seja, o período sugerido pela calculadora de tamanho de amostra) quando uma única experiência executa fortemente todas as outras experiências. Quando duas ou mais experiências estão &quot;vencendo&quot; em relação a outras experiências, mas estão estreitamente relacionadas entre si, [!UICONTROL Alocação automática] pode exigir mais tempo para determinar qual é superior. Nesses casos, os testes de horizonte fixo tipicamente teriam terminado ao concluir que as experiências &quot;vencedoras&quot; eram melhores do que as experiências de desempenho mais baixo, mas não identificaram qual era superior.

### Devo remover uma experiência com baixo desempenho de uma [!UICONTROL Alocação automática] atividade para acelerar o processo de decisão de um vencedor?

Não há motivo para remover uma experiência com baixo desempenho. [!UICONTROL Alocação automática] O fornece automaticamente experiências de alto desempenho com mais frequência e retorna experiências de baixo desempenho com menos frequência. Deixar uma experiência com baixo desempenho na atividade não afeta significativamente a velocidade para determinar um vencedor.

20% dos visitantes são atribuídos aleatoriamente em todas as experiências. A quantidade de tráfego veiculada para uma experiência com baixo desempenho é mínima (20% dividido pelo número de experiências).

### Posso mudar a métrica de meta para o meio de uma [!UICONTROL Alocação automática] atividade ? {#change-metric}

[!DNL Adobe] não recomenda alterar a métrica de meta até o meio de uma atividade. Embora seja possível alterar a métrica de meta durante uma atividade utilizando a interface do usuário [!DNL Target], você sempre deve iniciar uma nova atividade. [!DNL Adobe] O não garante o que acontece se você alterar a métrica de meta em uma atividade após a execução.

Esta recomendação se aplica às atividades de [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

### Posso alterar a fonte de relatórios no meio de uma atividade de [!UICONTROL Alocação automática]? {#change-reporting}

[!DNL Adobe] não recomenda alterar a fonte de relatórios até o meio de uma atividade . Embora seja possível alterar a fonte de relatórios (de [!DNL Target] para A4T ou vice-versa) durante uma atividade usando o [!DNL Target] Na interface do usuário, você sempre deve iniciar uma nova atividade. [!DNL Adobe] O não garante o que acontece se você alterar a fonte de relatórios em uma atividade após sua execução.

Esta recomendação se aplica às atividades de [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

### Posso usar o [!UICONTROL Redefinir dados de relatório] durante a execução de uma [!UICONTROL Alocação automática] atividade ?

Usar o [!UICONTROL Redefinir dados de relatório] opção para [!UICONTROL Alocação automática] não é sugerida. Embora remova os dados de relatório visíveis, essa opção não remove todos os registros de treinamento do [!UICONTROL Alocação automática] modelo. Em vez de usar o [!UICONTROL Redefinir dados de relatório] opção para [!UICONTROL Alocação automática] , crie uma nova atividade e desative a atividade original. (Esta orientação também se aplica a [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] atividades.)

### Como [!UICONTROL Alocação automática] criar modelos em relação a ambientes?

[!UICONTROL Alocação automática] O cria modelos com base no tráfego e no comportamento de conversão registrados somente no ambiente padrão. Por padrão, [!UICONTROL Produção] é o ambiente padrão, mas o ambiente padrão pode ser alterado em [!DNL Target] [Administração > Ambientes](/help/main/administrating-target/environments.md).

Se uma ocorrência ocorrer em outro ambiente (não padrão), o tráfego será distribuído de acordo com o comportamento de conversão observado no ambiente padrão. O resultado dessa ocorrência (conversão ou não conversão) é registrado para fins de relatório, mas não é considerado na variável [!UICONTROL Alocação automática] modelo.

Ao selecionar outro ambiente, o relatório mostra o tráfego e as conversões desse ambiente. O ambiente padrão selecionado para um relatório é o padrão em toda a conta selecionado. O ambiente padrão não pode ser definido com base em atividades.

### Uma atividade de [!UICONTROL Alocação automática] pode ajustar a janela de pesquisa ao longo de um teste para considerar a mudança de tendências com o passar do tempo?

Por exemplo, a atividade pode considerar o mês de dezembro para decidir como alocar o tráfego, em vez de consultar os dados de visitante de setembro (quando o teste começou)?

Não, [!UICONTROL Alocação automática] O considera o desempenho de toda a atividade.

### A [!UICONTROL Alocação automática] mostra uma experiência vencedora a um visitante recorrente se a experiência vencedora for diferente do que o visitante viu ao se qualificar para a atividade?

[!UICONTROL Alocação automática] O usa a decisão aderente pelos mesmos motivos que [!UICONTROL Teste A/B] As atividades do são aderentes. A alocação de tráfego funciona somente para novos visitantes.

## Vídeos de treinamento {#section_893E5B36DC4A415C9B1D287F51FCCB83}

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Fluxo de trabalho da atividade - Direcionamento (2:14) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre a configuração da alocação de tráfego.

* Designar um público-alvo para sua atividade
* Controle do tráfego
* Selecione seu método de alocação de tráfego
* Aloque o tráfego entre diferentes experiências

>[!VIDEO](https://video.tv.adobe.com/v/17385)

### Criação de testes A/B (8:36) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo monstra como criar um teste A/B usando o fluxo de trabalho orientado de três etapas do Target. [!UICONTROL Alocação automática] O é discutido a partir de 4:45.

* Crie uma atividade A/B em [!DNL Adobe Target]
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
