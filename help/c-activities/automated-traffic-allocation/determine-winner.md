---
description: Determine um vencedor em uma atividade de Alocação automática A/B exibindo indicadores na interface do usuário do Target.
keywords: alocação automática de tráfego, direcionamento, vencedor, garantia estatística, confiança, determinar vencedor
seo-description: Determine um vencedor em uma atividade de Alocação automática A/B exibindo indicadores na interface do usuário do Target.
seo-title: Determinar um vencedor
solution: Target
title: Determinar um vencedor
topic: Padrão
uuid: 0bcc11b2-44bd-450c-a504-a8ff7a4d72e6
translation-type: tm+mt
source-git-commit: e313aeade9c9b4f775c79193b7bfa364dd0fde87

---


# Determinar um vencedor{#determine-a-winner}

Determine um vencedor em uma atividade de Alocação automática A/B exibindo indicadores na interface do usuário do Target.

Muitos profissionais de marketing cometem o erro de declarar prematuramente uma experiência vencedora antes dos resultados indicarem claramente o vencedor. Agora facilitamos para você determinar o vencedor.

## Exibir o emblema do vencedor na interface do usuário do Target {#section_24007470CF5B4D30A06610CE8DD23CE3}

Ao usar o recurso [!UICONTROL Alocação automática], o [!DNL Target] exibe um emblema na parte superior da página da atividade, indicando "Ainda não há vencedor" até que a atividade atinja o número mínimo de conversões com confiança suficiente.

![Sem selo de Vencedor](/help/c-activities/automated-traffic-allocation/assets/no-winner.png)

Quando um vencedor claro é declarado, o [!DNL Target] exibe "Vencedor: Experiência X".

![](assets/auto_traffic_winner.png)

>[!NOTE]
>
>As atividades de alocação automática são projetadas para encontrar a melhor experiência entre todas as opções e não apenas para fazer comparações emparelhadas com controle.

## Garantias estatísticas da alocação automática {#section_7AF3B93E90BA4B80BC9FC4783B6A389C}

No final de uma atividade A/B, a Alocação automática garante que o vencedor determinado tenha uma taxa de falso-positivo eficaz de 5%. Isso significa que apenas 5% do tempo, o vencedor determinado não é realmente a melhor experiência entre todas as experiências na atividade. Para um teste A/A (com experiências idênticas), concluímos um teste com menos de 5% do tempo. O comportamento esperado para um teste A/A (com experiências idênticas) é para ser executado indefinidamente e, portanto, o emblema do vencedor nunca deve aparecer.

Não usamos a confiança baseada em valor p para alocação automática.

A coluna Confiança em uma atividade de Alocação automática (ilustrada abaixo) exibe a probabilidade de uma experiência ser a vencedora com margem de erro de 1% (ou seja, o algoritmo usa um efeito mínimo detectável de 1% entre a melhor e a segunda melhor taxa de conversão). Observe que o algoritmo usa [Desigualdade de Bernstein](https://en.wikipedia.org/wiki/Bernstein_inequalities_(probability_theory)) para computar esta probabilidade.

Testes A/B normais calculam a confiança com base nos valores de p. A Alocação automática não usa valores p. Os valores de P calculam "vagamente" a probabilidade de que uma determinada experiência seja diferente do controle. Esses valores p podem ser usados apenas para determinar se uma experiência pode ser diferente do controle. Esses valores não podem ser usados para determinar se uma experiência é diferente de outra experiência (não de controle).

A ilustração a seguir mostra uma atividade que ainda não tem vencedor:

![](assets/no_winner.png)

A ilustração a seguir mostra uma atividade que tem vencedor:

![](assets/winner_found.png)

## Perguntas frequentes {#section_C8E068512A93458D8C006760B1C0B6A2}

**Já passaram alguns dias na atividade. Por que todos os valores de confiança ainda estão mostrando 0%?**

Qualquer um dos motivos a seguir descreve por que 0% é exibido na coluna [!UICONTROL Confiança] do relatório para todas as atividades:

* Testes A/B manuais e Alocação automática usam estatísticas diferentes para exibir valores de confiança.

   Os testes manuais A/B usam valores p baseados no [teste t de Estudante](https://en.wikipedia.org/wiki/Student%27s_t-test). Um valor P é a probabilidade de encontrar a diferença observada (ou uma mais extrema) entre uma experiência e o controle, visto que, na realidade, não há essa diferença. Esses valores P podem ser usados somente para determinar se os dados observados estão consistentes, visto que a experiência e o controle são iguais. Esses valores não podem ser usados para determinar se uma experiência é diferente de outra experiência (não de controle).

   A Alocação automática mostra a probabilidade de uma determinada experiência ser um verdadeiro vencedor em todas as experiências na atividade. Isso significa que apenas uma experiência vencedora (que provavelmente será a vencedora) terá um valor de confiança diferente de zero. Todos os outros são mais propensos a serem perdedores e exibirão 0%.

* A Alocação automática começa a mostrar confiança somente após a experiência vencedora reunir 60% de confiança. Esses níveis de confiança normalmente aparecem em cerca de metade do tempo que um teste A/B normal levaria para ser concluído (embora isso não seja garantido). To determine how long a normal A/B test would run, please use a [sample size calculator](https://docs.adobe.com/content/target-microsite/testcalculator.html): plug control's conversion-rate in "Baseline conversion rate," "5%" for "Lift," and 95% for "Confidence." Normalmente, a confiança começa a aparecer depois que cada experiência acumulou pelo menos 50% das amostras necessárias por experiência. Isso lhe dará uma ideia de quando a confiança começará a aparecer.
* Se o relatório mostrar 0% em todo o quadro, é provável que seja muito cedo para a atividade.

