---
keywords: a/b;a/a;aa;
description: Saiba o que é um teste A/A, por que você pode querer executar um teste A/A, por quanto tempo deve executar o teste e como interpretar os resultados.
title: O que é Teste A/A?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 4e3a94554dd9c1e8cc6e98eda10d454536bc9b1f
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 1%

---

# Teste A/A

Antes de executar um teste A/A no seu site usando [!DNL Adobe Target], é importante entender o que é um teste A/A, por que você pode querer executar um teste A/A, por quanto tempo deve executar o teste e como interpretar os resultados.

## O que é teste A/A?

Antes de explicar o teste A/A, é bom revisar o teste A/B para que possamos discutir as diferenças.

In a standard A/B test, traffic is allocated to two or more different experiences. Uma experiência é normalmente o &quot;controle&quot; e as variações da experiência são testadas em relação ao controle para ver qual experiência cria mais incentivo em uma determinada métrica.

A/A testing, however, involves allocating traffic to two identical experiences, normally with a 50/50 traffic allocation split. With a standard A/B test, you typically want to discover a lift in conversion. Isso difere de um teste A/A no qual sua meta normalmente é determinar que haja um *não* diferença no incentivo entre as experiências idênticas.

## Why would you want to test two identical experiences and what does this accomplish?

Algumas organizações executam testes A/A ao implementar uma nova ferramenta de teste, como [!DNL Target]para determinar se:

* A atividade foi configurada corretamente
* O código foi implementado corretamente
* O relatório é preciso

Although few organizations run A/A tests, it is actually good practice to run them as “sanity” experiments to build trust after implementing the tool or before performing A/B tests that could impact conversion and revenue.

## Por que você pode ver incentivo para uma experiência quando as experiências são idênticas?

There are numerous reasons why you might see lift in one experience over the another (identical) experience:

### O teste A/A foi monitorado continuamente

Um problema comum em executar qualquer tipo de teste, incluindo um teste A/A, é observar os resultados continuamente e interromper prematuramente um teste assim que você visualizar significância estatística e declarar uma experiência vencedora. Analysts often do what is called “data peeking.” O pico de dados envolve observar os dados de teste precocemente e com frequência, enquanto tenta determinar qual experiência está tendo melhor desempenho. O risco é parar o teste prematuramente, o que pode invalidar os resultados.

Em um teste A/A, o pico de dados geralmente pode fazer com que os analistas vejam o aumento em uma experiência, quando, de fato, não deve haver diferença, pois as duas experiências são idênticas. Na verdade, com uma espionagem contínua, os testes A/A são na verdade _garantido_ para mostrar &quot;significância estatística&quot; (ou seja, uma confiança acima de um determinado limite, como 95%) em algum momento durante o teste.

Para evitar isso e como em um teste A/B regular, você deve decidir antecipadamente qual tamanho de amostra usar, com base no tamanho mínimo do efeito (o aumento mínimo abaixo do qual um efeito não é importante para sua empresa), energia e níveis de significância que você considera aceitáveis.

Em um teste A/A, o objetivo seria *not* consulte um resultado estatisticamente significativo depois que o teste atingir o tamanho de amostra desejado.

O [!UICONTROL Calculadora de tamanho da amostra do Adobe Target] O é uma ferramenta importante para ajudá-lo a determinar para qual tamanho de amostra você deve direcionar e por quanto tempo você deve executar o teste.

* [Adobe Target Size Calculator](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

Além disso, consulte os seguintes artigos para obter informações sobre por quanto tempo você deve executar uma atividade, bem como outras dicas e truques úteis:

* [Por quanto tempo você deve executar um teste A/B?](/help/c-activities/t-test-ab/sample-size-determination.md)
* [Dez erros comuns em A/B e como evitá-los](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### A significância estatística afeta os resultados do teste

The significance level of a test determines how likely it is that the test reports a significant difference in conversion rates between two different offers when, in fact, there is no real difference. Isso é conhecido como falso positivo ou um erro do Tipo I. O nível de significância é um limite especificado pelo usuário e há uma compensação entre a tolerância para falsos positivos e o número de visitantes que devem ser incluídos no teste na escolha do nível de significância apropriado.

Um nível de significância comumente usado em testes A/A e A/B é 5%, o que corresponde a um nível de confiança de 95% (nível de confiança = 100% - nível de significância). Um nível de confiança de 95% significa que toda vez que você executa um teste, há uma chance de 5% de detectar um aumento estatisticamente significativo, mesmo que não haja diferença entre as experiências.

Suponha que você queira atingir um nível de confiança de 95% com seu teste A/A. Com um nível de confiança de 95%, testes A/A de 1 em 20 podem mostrar um aumento estatisticamente significativo nas conversões. Com um nível de confiança de 90%, 1 em 10 testes podem mostrar aumento nas conversões ao testar experiências idênticas.

## Prática recomendada

Se você decidir que um teste A/A é necessário em sua organização, esteja ciente de que as experiências idênticas podem mostrar temporariamente uma diferença do controle. Isso pode ser normal, dependendo do tempo em que o teste pode ser executado. A diferença deve diminuir, considerando mais tempo e visitantes.

A prática recomendada é usar a metodologia de teste A/B regular: decida com antecedência o tamanho da amostra com base no tamanho mínimo de efeito relevante, potência e significado desejados usando o [Calculadora de tamanho da Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Then, allow adequate time and visitors before you reach any conclusions, and remember that depending on the significance level of your test, there is a chance that one experience will show a difference in lift, and even be declared the winner.
