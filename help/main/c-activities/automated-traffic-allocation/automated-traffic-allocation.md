---
keywords: alocação automática de tráfego;direcionamento;Aumentar contagem e manter usuário na atividade;alocação de tráfego;alocação automática;alocação automática
description: Saiba como usar um [!UICONTROL Alocação automática] atividade no [!DNL Adobe Target] que identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor.
title: O que é uma [!UICONTROL Alocação automática] Atividade?
feature: Auto-Allocate
exl-id: 2d1ddd71-2ca6-4f00-9d0c-eb25ede8fdb8
source-git-commit: 1b1b2271738d12f8da4e695900b70e280f50d8cf
workflow-type: tm+mt
source-wordcount: '3574'
ht-degree: 43%

---

# Visão geral da [!UICONTROL Alocação automática]

Um [!UICONTROL Alocação automática] atividade no [!DNL Adobe Target] O identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor a fim de aumentar as conversões enquanto o teste continua a ser executado e aprendido.

Enquanto [criação de uma atividade A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) usando o fluxo de trabalho guiado de três etapas, escolha o **[!UICONTROL Alocar automaticamente para a melhor experiência]** opção no **[!UICONTROL Direcionamento]** página (etapa 2).

## O desafio {#section_85D5A03637204BACA75E19646162ACFF}

Os testes A/B padrão têm um custo inerente. Você deve gastar o tráfego para medir o desempenho de cada experiência e, por meio de análise, descobrir a experiência vencedora. A distribuição do tráfego permanece fixa mesmo depois de você reconhecer que algumas experiências estão superando outras. Além disso, é complicado descobrir o tamanho da amostra, e a atividade deve ser executada em sua totalidade para que você possa agir em um vencedor. E ainda há uma chance do vencedor identificado não ser um verdadeiro vencedor.

## A solução: [!UICONTROL Alocação automática] {#section_98388996F0584E15BF3A99C57EEB7629}

Um [!UICONTROL Alocação automática] A atividade do reduz esse custo e a sobrecarga de determinar uma experiência vencedora. [!UICONTROL A alocação automática monitora o desempenho da métrica de meta de todas as experiências e envia mais novos participantes para as experiências de alto desempenho proporcionalmente. ] Há tráfego suficiente reservado para explorar as outras experiências. Você pode ver os benefícios do teste nos resultados, mesmo enquanto a atividade está em execução: a otimização e o aprendizado ocorrem paralelamente.

[!UICONTROL A alocação automática move os visitantes para experiências vencedoras gradativamente, em vez de exigir que você aguarde o fim de uma atividade para determinar um vencedor. ] Você se beneficia do incentivo mais rapidamente porque os participantes da atividade que teriam sido enviados para experiências de menor sucesso recebem experiências vencedoras potenciais.

Um teste A/B normal em [!DNL Target] mostra somente comparações emparelhadas de desafiantes com o controle. Por exemplo, se uma atividade tiver experiências: A, B, C e D, onde A é o controle, uma atividade normal [!DNL Target] O teste A/B compararia A versus B, A versus C e A versus D.

Nesses testes, a maioria dos produtos, incluindo [!DNL Target], use um [Teste t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} para produzir confiança baseada em valores p. Este valor de confiança é então usado para determinar se o desafiante é suficientemente diferente do controle. No entanto, [!DNL Target] O não executa automaticamente as comparações implícitas (B versus C, B versus D e C versus D) necessárias para encontrar a &quot;melhor&quot; experiência. Como resultado, o profissional de marketing deve analisar manualmente os resultados para determinar a &quot;melhor&quot; experiência.

[!UICONTROL A alocação automática executa todas as comparações implícitas entre as experiências e produz um vencedor &quot;verdadeiro&quot;. ] Não há noção de experiência de &quot;controle&quot; no teste.

[!UICONTROL Alocação automática] aloca de forma inteligente novos visitantes para experiências até que o intervalo de confiança da melhor experiência não se sobreponha ao intervalo de confiança de qualquer outra experiência. Normalmente, esse processo pode produzir falsos positivos, mas [!UICONTROL Alocação automática] usa intervalos de confiança com base no [Desigualdade de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_%28probability_theory%29){target=_blank} que compensa avaliações repetidas. Neste ponto, há um verdadeiro vencedor. Quando [!UICONTROL Alocação automática] para, desde que não haja uma dependência de tempo substancial para os visitantes que chegam à página, há pelo menos 95% de chance [!UICONTROL Alocação automática] retorna uma experiência cuja resposta verdadeira não é pior que 1% (relativa) menos que a resposta verdadeira da experiência vencedora.

## Quando usar [!UICONTROL Alocação automática] versus [!UICONTROL Teste A/B] ou [!UICONTROL Automated Personalization] atividades {#section_3F73B0818A634E4AAAA60A37B502BFF9}

* Use **[!UICONTROL Alocação automática]** quando quiser otimizar sua atividade a partir do início e identificar as experiências vencedoras o mais rapidamente possível. Ao veicular experiências de alto desempenho com mais frequência, o desempenho geral da atividade é aumentado.
* Usar um padrão **[Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md#task_05E33EB15C4D4459B5EAFF90A94A7977)** quando quiser caracterizar o desempenho de todas as experiências antes de otimizar o site. Um teste A/B ajuda a classificar todas as suas experiências, enquanto [!UICONTROL Alocação automática] O encontra os melhores desempenhos, mas não garante a diferenciação entre os de menor desempenho.
* Uso [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) quando quiser algoritmos de otimização da mais alta complexidade, como modelos de aprendizado automatizado que fazem previsões com base em atributos de perfil individuais. [!UICONTROL Alocação automática] A analisa o comportamento agregado das experiências (assim como testes A/B padrão) e não diferencia os visitantes.

## Principais benefícios do [!UICONTROL Alocação automática] {#section_0913BF06F73C4794862561388BBDDFF0}

* Mantém o rigor de um teste A/B
* Encontra um vencedor estatisticamente significativo mais rapidamente do que um teste A/B manual
* Fornece um lift médio de campanha maior que de um teste A/B manual

## Terminologia {#section_670F8785BA894745B43B6D4BFF953188}

Os termos a seguir são úteis ao discutir [!UICONTROL Alocação automática]:

**Multi-armed bandit:** Uma abordagem [multi-armed bandit](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado.

## Como o algoritmo funciona {#section_ADB69A1C7352462D98849F2918D4FF7B}

A lógica geral por trás [!UICONTROL Alocação automática] incorpora o desempenho medido (como a taxa de conversão) e os intervalos de confiança dos dados cumulativos. Ao contrário de um teste A/B padrão, em que o tráfego é dividido uniformemente entre as experiências, [!UICONTROL Alocação automática] altera a alocação de tráfego entre as experiências.

* 80% dos visitantes são alocados usando a lógica inteligente descrita abaixo.
* 20% dos visitantes são atribuídos aleatoriamente em todas as experiências para se adaptar à mudança de comportamento do visitante.

A abordagem multi-armed bandit mantém algumas experiências livre para exploração ao mesmo tempo em que aproveita as experiências que têm um bom desempenho. Mais novos visitantes são colocados em experiências de melhor desempenho enquanto preservam a capacidade de reagir a mudanças nas condições. Esses modelos são atualizados pelo menos uma vez por hora para garantir a reação do modelo aos dados mais recentes.

À medida que mais visitantes entram na atividade, algumas experiências começam a ter mais êxito, e mais tráfego é enviado para as experiências bem-sucedidas. 20% do tráfego continua sendo distribuído aleatoriamente para explorar todas as experiências. Se uma das experiências de baixo desempenho começar a funcionar melhor, mais tráfego será alocado para essa experiência. Ou, se o sucesso de uma atividade de desempenho mais alto diminui, menos tráfego será alocado para essa experiência. Por exemplo, se um evento faz com que os visitantes procurem informações diferentes no site de sua mídia, ou se as vendas no fim de semana em seu site de vendas oferecem resultados diferentes.

A ilustração a seguir representa como o algoritmo pode ser executado durante um teste com quatro experiências (clique para expandir a ilustração):

![alocar imagem automaticamente](assets/auto-allocate.png){width="600" zoomable="yes"}

A ilustração mostra como o tráfego alocado para cada experiência progride ao longo de várias rodadas do tempo de atividade até que um vencedor claro seja determinado.

| Arredondar | Descrição |
|--- |--- |
| ![Aquecimento](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-0.png){width="200" zoomable="yes"} | **Rodada de aquecimento (0):** durante a rodada de aquecimento, cada experiência recebe a mesma distribuição de tráfego até que cada experiência na atividade tenha um mínimo de 1.000 visitantes e 50 conversões.<ul><li>Experiência A=25%</li><li>Experiência B=25%</li><li>Experiência C=25%</li><li>Experiência D=25%</li></ul>Depois que cada experiência recebe 1.000 visitantes e 50 conversões, [!DNL Target] inicia a alocação automática de tráfego. Todas as alocações acontecem em rodadas e duas experiências são escolhidas para cada rodada.<br>Somente duas experiências avançam para a próxima rodada: D e C.<br>Seguir em frente significa que as duas experiências recebem 80% do tráfego igualmente. As outras duas experiências continuam a participar, mas são servidas apenas como parte da alocação de tráfego aleatório de 20% à medida que novos visitantes entram na atividade.<br>Todas as alocações são atualizadas a cada hora (mostradas por arredondamentos ao longo do eixo x acima). Após cada rodada, os dados acumulados são comparados. |
| ![Rodada 1](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-1.png){width="200" zoomable="yes"} | **Rodada 1:** nesta rodada, 80% do tráfego é alocado às experiências C e D (40% cada). 20% do tráfego é alocado aleatoriamente para experiências A, B, C e D (5% cada). Durante esta rodada, a experiência A tem um excelente desempenho.<ul><li>O algoritmo escolhe a experiência D para avançar para a próxima rodada porque tem a taxa de conversão mais alta (conforme indicado pela escala vertical de cada atividade).</li><li>O algoritmo escolhe a experiência A para avançar também porque tem o limite superior mais alto do intervalo de confiança de 95% de Bernstein das experiências restantes.</li></ul>As experiências D e A seguem em frente. |
| ![Rodada 2](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-2.png){width="200" zoomable="yes"} | **Rodada 2:** nesta rodada, 80% do tráfego é alocado às experiências A e D (40% cada). 20% do tráfego é alocado aleatoriamente, portanto, isso significa que A, B, C e D recebem 5% cada um. Durante esta rodada, a experiência B tem um excelente desempenho.<ul><li>O algoritmo escolhe a experiência D para avançar para a próxima rodada porque tem a taxa de conversão mais alta (conforme indicado pela escala vertical de cada atividade).</li><li>O algoritmo escolhe a experiência B para avançar também porque tem o limite superior mais alto do intervalo de confiança de 95% de Bernstein das experiências restantes.</li></ul>As experiências D e B seguem em frente. |
| ![Rodada 3](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-3.png){width="200" zoomable="yes"} | **Rodada 3:** nesta rodada, 80% do tráfego é alocado às experiências B e D (40% cada). 20% do tráfego é alocado aleatoriamente, portanto, isso significa que A, B, C e D recebem 5% cada um. Durante esta ronda, a experiência D continua a ter um bom desempenho e a experiência C tem um excelente desempenho.<ul><li>O algoritmo escolhe a experiência D para avançar para a próxima rodada porque tem a taxa de conversão mais alta (conforme indicado pela escala vertical de cada atividade).</li><li>O algoritmo escolhe a experiência C para avançar também porque tem o limite superior mais alto do intervalo de confiança de 95% de Bernstein das experiências restantes.</li></ul>As experiências D e C seguem em frente. |
| ![Rodada 4](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-4.png){width="200" zoomable="yes"} | **Rodada 4:** nesta rodada, 80% do tráfego é alocado às experiências C e D (40% cada). 20% do tráfego é alocado aleatoriamente, portanto, isso significa que A, B, C e D recebem 5% cada um. Durante esta rodada, a experiência C tem um excelente desempenho.<ul><li>O algoritmo escolhe a experiência C para avançar para a próxima rodada porque tem a taxa de conversão mais alta (conforme indicado pela escala vertical de cada atividade).</li><li>O algoritmo escolhe a experiência D para avançar também porque tem o limite superior mais alto do intervalo de confiança de 95% de Bernstein das experiências restantes.</li></ul>As experiências C e D seguem em frente. |
| ![Rodada n](/help/main/c-activities/automated-traffic-allocation/assets/aa-phase-n.png){width="200" zoomable="yes"} | ***Rodada n***: Conforme a atividade avança, uma experiência de alto desempenho começa a surgir e o processo continua até que haja uma experiência vencedora. Quando o intervalo de confiança da experiência com a taxa de conversão mais alta não coincide com o intervalo de confiança de qualquer outra experiência, ele é rotulado como vencedor. A [o selo é exibido na página da atividade vencedora](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) e no [!UICONTROL Atividade] lista.<ul><li>O algoritmo escolhe a experiência C como o vencedor claro.</li></ul>Nesse ponto, o algoritmo serve 80% do tráfego para a experiência C, enquanto 20% do tráfego continua a ser servido aleatoriamente para todas as experiências (A, B, C e D). No total, C recebe 85% do tráfego. No caso improvável de que o intervalo de confiança do vencedor comece a se sobrepor novamente, o algoritmo reverte para o comportamento da rodada 4 acima.<P>**Importante:** se você escolhesse manualmente um vencedor no início do processo, teria sido fácil escolher a experiência errada. Por esse motivo, é uma prática recomendada esperar até que o algoritmo determine a experiência vencedora. |

>[!NOTE]
>
>Se uma atividade tiver apenas duas experiências, ambas as experiências obterão tráfego igual até [!DNL Target] O encontra uma experiência vencedora com 75% de confiança. Nesse ponto, dois terços do tráfego é alocado para o vencedor e um terço para o perdedor. Depois disso, quando uma experiência atingir a confiança de 95%, 90% do tráfego será alocado ao vencedor e 10% será alocado ao perdedor. [!DNL Target] sempre envia algum tráfego para a experiência &quot;perdedora&quot; para evitar falsos positivos no final (ou seja, manter alguma exploração).

Depois de um [!UICONTROL Alocação automática] atividade estiver ativada, as seguintes operações do Tar[!DNL]obter interface do usuário não é permitido:

* Alternar o modo &quot;Alocação de tráfego&quot; para &quot;Manual&quot;
* Alterar o tipo de métrica de meta
* Alterar opções na &quot;[!UICONTROL Configurações avançadas]Painel &quot;

## Veja como a Alocação automática funciona

Para obter mais informações, consulte [A Alocação automática pode fornecer resultados de teste mais rápidos e receita maior do que um teste manual](/help/main/c-activities/automated-traffic-allocation/faster-results-higher-revenue.md).

## Avisos {#section_5C83F89F85C14FD181930AA420435E1D}

Considere as informações a seguir ao trabalhar com o [!UICONTROL Alocação automática]:

### A variável [!UICONTROL Alocação automática] O recurso funciona somente com uma configuração de métrica avançada: [!UICONTROL Incrementar contagem e manter usuário em atividade]

As seguintes configurações avançadas de métrica não são compatíveis: [!UICONTROL Incrementar contagem], [!UICONTROL Liberar usuário], [!UICONTROL Permitir reentrada e incrementar contagem], e [!UICONTROL Liberar Usuário e Impedir Reentrada].

### Visitantes que retornam com frequência podem aumentar as taxas de conversão da experiência.

Se um visitante que vê a experiência A retorna com frequência e faz conversão várias vezes, a Índice de conversão (CR) da experiência A aumenta artificialmente. Compare esse resultado com a experiência B, em que os visitantes convertem, mas não retornam com frequência. Como resultado, o CR da experiência A fica melhor que o CR da experiência B, portanto, novos visitantes têm mais probabilidade de ser alocados para A do que para B. Se você optar por contar uma vez por participante, o CR de A e o CR de B podem ser idênticos.

Se visitantes recorrentes são distribuídos aleatoriamente, seu efeito nas taxas de conversão tem mais probabilidade de ser uniformizado. Para amenizar esse efeito, considere alterar o método de contagem da métrica de meta para contar somente uma vez por participante.

### Diferencia entre os profissionais de alto desempenho, não entre os de baixo desempenho.

[!UICONTROL A alocação automática é boa em diferenciar entre experiências de alto desempenho (e encontrar uma vencedora). ] Pode ser que algumas vezes não haja diferenciação suficiente entre as experiências de desempenho inferior.

Se você quiser produzir uma diferenciação estatisticamente significativa entre todas as experiências, considere usar o modo de alocação de tráfego manual.

### As taxas de conversão associadas ao tempo (ou que variam de acordo com o contexto) podem distorcer as quantidades de alocação.

Alguns fatores que podem ser ignorados durante um teste A/B padrão porque afetam todas as experiências igualmente não podem ser ignorados em uma [!UICONTROL Alocação automática] atividade. O algoritmo está sujeito às taxas de conversão observadas.

Estes são exemplos de fatores que podem afetar o desempenho das experiências de maneira uniforme:

* Experiências com relevância contextual variável (tempo, local, gênero etc.).

  Por exemplo:

   * &quot;Graças a Deus é sexta-feira&quot; resulta em maiores conversões na sexta-feira.
   * &quot;Impulsione sua segunda-feira&quot; tem conversão mais alta na segunda-feira.
   * &quot;Prepare-se para um inverno na costa leste&quot; fornece uma conversão mais alta em locais da costa leste ou afetados pelo inverno.

  Usar experiências com relevância contextual variável pode distorcer os resultados em uma [!UICONTROL Alocação automática] teste mais do que em um teste A/B, pois o teste A/B analisa os resultados por um período mais longo.

* Experiências com atrasos de conversão variáveis, possivelmente devido à urgência da mensagem.

  Por exemplo, &quot;O desconto de 30% termina hoje&quot; avisa o visitante para converter hoje, mas &quot;50% de desconto na primeira compra&quot; não cria o mesmo senso de urgência.

## Perguntas frequentes {#section_0E72C1D72DE74F589F965D4B1763E5C3}

Consulte as seguintes perguntas frequentes e respostas ao trabalhar com o [!UICONTROL Alocação automática] atividades:

### Faz [!UICONTROL Analytics for Target] Suporte ao (A4T) [!UICONTROL Alocação automática] atividades?

Sim. Para obter mais informações, consulte [Suporte ao A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

### Os visitantes recorrentes são realocados automaticamente a experiências de alto desempenho?

Não. Somente novos visitantes são alocados automaticamente. Os visitantes recorrentes continuam a ver sua experiência original para proteger a validade do teste A/B.

### Como o algoritmo lida com falsos positivos?

O algoritmo garante uma confiança de 95% ou taxa de 5% de falso-positivo, se você esperar até que o emblema vencedor apareça.

### Quando o faz [!UICONTROL Alocação automática] começar a alocar tráfego?

O algoritmo começa a funcionar depois que todas as experiências na atividade têm um mínimo de 1.000 visitantes e 50 conversões.

### Qual é o nível de dinamismo do aproveitamento pelo algoritmo?

80% do tráfego é distribuído usando [!UICONTROL Alocação automática] e 20% do tráfego é distribuído aleatoriamente. Quando um vencedor é identificado, 80% do tráfego é direcionado a ele, enquanto todas as experiências continuam a receber algum tráfego como parte dos 20%, incluindo a experiência vencedora.

### As experiências perdedoras são exibidas?

Sim. A abordagem multi-armed bandit garante que pelo menos 20% do tráfego seja reservado para explorar a mudança nos padrões ou nas taxas de conversão em todas as experiências.

### O que acontece com atividades com longos atrasos de conversão?

Desde que todas as experiências que estão sendo otimizadas passem por atrasos semelhantes, o comportamento é o mesmo de uma atividade com um ciclo de conversão mais rápido. No entanto, demora mais para atingir o limite de 50 conversões antes do início do processo de alocação de tráfego.

### Como o [!UICONTROL Alocação automática] diferente de [!UICONTROL Automated Personalization]?

[!UICONTROL A personalização automatizada usa os atributos de perfil de cada visitante para determinar a melhor experiência. ] Ao fazer isso, ela não apenas otimiza, mas também personaliza a atividade para esse usuário.

[!UICONTROL Alocação automática]O, por outro lado, é um teste A/B que produz um vencedor agregado (a experiência mais popular, mas não necessariamente a experiência mais eficaz para cada visitante).

### Os visitantes recorrentes aumentam a taxa de conversão em minha métrica de sucesso?

Atualmente, a lógica favorece visitantes que convertem rapidamente ou visitam com mais frequência, pois esses visitantes inflam temporariamente o índice de conversão geral da experiência à qual pertencem. O algoritmo se ajusta frequentemente, então o aumento na taxa de conversão é amplificado a cada instantâneo. Se o site receber vários visitantes recorrentes, suas conversões poderão aumentar o índice de conversão geral da experiência à qual pertencem. Há uma boa chance de os visitantes recorrentes serem distribuídos aleatoriamente; nesse caso, o efeito agregado (maior incentivo) é uniformizado. Para amenizar esse efeito, considere alterar o método de contagem da métrica de sucesso para contar somente uma vez por participante.

### Posso usar a calculadora de tamanho de amostra ao usar [!UICONTROL Alocação automática] para estimar quanto tempo a atividade leva para identificar o vencedor?

É possível usar o existente [!DNL Adobe Target] [Calculadora de tamanho da amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) para obter uma estimativa da duração da execução do teste. (Assim como no teste A/B tradicional, aplique a correção de Bonferroni se estiver testando mais de duas ofertas ou mais de uma métrica/hipótese de conversão.) Essa calculadora foi projetada para testes A/B tradicionais de horizonte fixo e fornece apenas uma estimativa. Usar a calculadora para um [!UICONTROL Alocação automática] A atividade é opcional porque [!UICONTROL Alocação automática] declara um vencedor para você. Você não precisa escolher um ponto fixo no tempo para ver os resultados do teste. Os valores fornecidos são sempre estatisticamente válidos.

Interno [!DNL Adobe] experimentos descobriram o seguinte:

* Ao testar exatamente duas experiências, [!UICONTROL Alocação automática] O encontra um vencedor mais rapidamente do que o teste de horizonte fixo (ou seja, o intervalo de tempo sugerido pela calculadora de tamanho de amostra) quando a diferença de desempenho entre as experiências é grande. No entanto, [!UICONTROL Alocação automática] O pode exigir tempo extra para identificar um vencedor quando a diferença de desempenho entre experiências for pequena. Nesses casos, os testes de horizonte fixo normalmente terminariam sem um resultado estatisticamente significativo.
* Ao testar mais de duas experiências, [!UICONTROL Alocação automática] O encontra um vencedor mais rapidamente do que o teste de horizonte fixo (ou seja, o intervalo de tempo sugerido pela calculadora de tamanho de amostra) quando uma única experiência supera em muito o desempenho de todas as outras experiências. Quando duas ou mais experiências estão &quot;vencendo&quot; em relação a outras experiências, mas estão intimamente relacionadas umas com as outras, [!UICONTROL Alocação automática] pode exigir tempo extra para determinar qual é superior. Nesses casos, os testes de horizonte fixo normalmente terminariam concluindo que as experiências &quot;vencedoras&quot; eram melhores do que as experiências de baixo desempenho, mas não tinham identificado qual era superior.

### Devo remover uma experiência com baixo desempenho de um [!UICONTROL Alocação automática] atividade para acelerar o processo de decisão de um vencedor?

Não há motivo para remover uma experiência com baixo desempenho. [!UICONTROL Alocação automática] O fornece automaticamente experiências de alto desempenho com mais frequência e as com baixo desempenho com menos frequência. Deixar uma experiência com baixo desempenho na atividade não afeta significativamente a velocidade para determinar um vencedor.

20% dos visitantes são atribuídos aleatoriamente em todas as experiências. A quantidade de tráfego veiculada para uma experiência com baixo desempenho é mínima (20% dividido pelo número de experiências).

### Posso alterar a métrica de meta durante uma [!UICONTROL Alocação automática] atividade? {#change-metric}

[!DNL Adobe] O não recomenda alterar a métrica de meta durante uma atividade. Embora seja possível alterar a métrica de meta durante uma atividade utilizando a interface do usuário [!DNL Target], você sempre deve iniciar uma nova atividade. [!DNL Adobe] O não garante o que acontece se você alterar a métrica de meta em uma atividade após sua execução.

Esta recomendação se aplica às atividades de [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

### Posso alterar a fonte de relatórios no meio de uma atividade de [!UICONTROL Alocação automática]? {#change-reporting}

[!DNL Adobe] O não recomenda que você altere a fonte de relatórios no meio de uma atividade. Embora seja possível alterar a fonte de relatórios (de [!DNL Target] A4T ou o oposto) durante uma atividade utilizando o método [!DNL Target] Interface do usuário do, você sempre deve iniciar uma nova atividade do. [!DNL Adobe] O não garante o que acontece se você alterar a fonte de relatórios em uma atividade após sua execução.

Esta recomendação se aplica às atividades de [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

### Posso usar o [!UICONTROL Redefinir dados de relatório] durante a execução de um [!UICONTROL Alocação automática] atividade?

Usar o [!UICONTROL Redefinir dados de relatório] opção para [!UICONTROL Alocação automática] não é sugerido. Embora ela remova os dados do relatório visíveis, essa opção não remove todos os registros de treinamento do [!UICONTROL Alocação automática] modelo. Em vez de usar o [!UICONTROL Redefinir dados de relatório] opção para [!UICONTROL Alocação automática] crie uma nova atividade e desative a atividade original. (As presentes orientações aplicam-se igualmente aos [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] atividades.)

### Como o [!UICONTROL Alocação automática] criar modelos em relação aos ambientes?

[!UICONTROL Alocação automática] O cria modelos com base no comportamento de tráfego e conversão registrado somente no ambiente padrão. Por padrão, [!UICONTROL Produção] é o ambiente padrão, mas ele pode ser alterado em [!DNL Target] ([Administração > Ambientes](/help/main/administrating-target/environments.md)).

Se uma ocorrência ocorrer em outro ambiente (não padrão), o tráfego será distribuído de acordo com o comportamento de conversão observado no ambiente padrão. O resultado dessa ocorrência (conversão ou não conversão) é registrado para fins de relatório, mas não considerado na variável [!UICONTROL Alocação automática] modelo.

Ao selecionar outro ambiente, o relatório mostra o tráfego e as conversões desse ambiente. O ambiente selecionado padrão para um relatório é o padrão em toda a conta selecionado. O ambiente padrão não pode ser definido com base na atividade.

### Pode um [!UICONTROL Alocação automática] atividade ajustar a janela de pesquisa ao longo de um teste para considerar a mudança de tendências ao longo do tempo?

Por exemplo, a atividade pode considerar o mês de dezembro para decidir como alocar o tráfego, em vez de analisar os dados do visitante de setembro (quando o teste começou)?

Não, [!UICONTROL Alocação automática] O considera o desempenho de toda a atividade.

### A [!UICONTROL Alocação automática] mostra uma experiência vencedora a um visitante recorrente se a experiência vencedora for diferente do que o visitante viu ao se qualificar para a atividade?

[!UICONTROL Alocação automática] O usa a decisão adesiva pelos mesmos motivos que [!UICONTROL Teste A/B] as atividades são aderentes. A alocação de tráfego funciona somente para novos visitantes.

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

* Criar uma atividade A/B no [!DNL Adobe Target]
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
