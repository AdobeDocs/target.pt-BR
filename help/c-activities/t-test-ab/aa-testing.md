---
keywords: a/b;a/a;aa;
description: Saiba o que é um teste A/A, por que você pode querer executar um teste A/A, quanto tempo você deve executar o teste e como interpretar os resultados.
title: O que é Teste A/A?
feature: A/B Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '895'
ht-degree: 1%

---


# Teste A/A

Antes de executar um teste A/A em seu site usando [!DNL Adobe Target], é importante entender o que é um teste A/A, por que você pode querer executar um teste A/A, por quanto tempo deve executar o teste e como interpretar os resultados.

## O que é teste A/A?

Antes de explicar o teste A/A, é bom revisar o teste A/B para que possamos discutir as diferenças.

Em um teste A/B padrão, o tráfego é alocado para duas ou mais experiências diferentes. Uma experiência é normalmente o &quot;controle&quot; e as variações da experiência são testadas em relação ao controle para ver qual experiência cria mais incentivo em uma determinada métrica.

No entanto, o teste A/A envolve a alocação de tráfego para duas experiências idênticas, normalmente com uma divisão de alocação de tráfego 50/50. Com um teste A/B padrão, você geralmente deseja descobrir um aumento na conversão. Isso difere de um teste A/A no qual seu objetivo normalmente é determinar que há *no* diferença de incentivo entre as experiências idênticas.

## Por que você gostaria de testar duas experiências idênticas e o que isso consegue?

Algumas organizações executam testes A/A ao implementar uma nova ferramenta de teste, como [!DNL Target], para determinar se:

* A atividade foi configurada corretamente
* O código foi implementado corretamente
* O relatórios é preciso

Embora poucas organizações executem testes A/A, é uma boa prática executá-los como experimentos de &quot;sanidade&quot; para criar confiança após a implementação da ferramenta ou antes de realizar testes A/B que possam afetar a conversão e a receita.

## Por que você pode ver incentivo para uma experiência quando as experiências são idênticas?

Há várias razões pelas quais você pode ver o incentivo em uma experiência em vez de outra (idêntica) experiência:

### O teste A/A não era permitido para ser executado por tempo suficiente

Um problema comum ao executar qualquer tipo de teste, incluindo um teste A/A, é interromper prematuramente um teste e declarar uma experiência vencedora. Os analistas frequentemente fazem o que é chamado de &quot;pico de dados&quot;. O pico de dados envolve observar os dados de teste precocemente e com frequência, enquanto tenta determinar qual experiência tem melhor desempenho. O risco é parar o teste prematuramente, o que poderia invalidar os resultados.

Em um teste A/A, o pico de dados geralmente pode fazer com que os analistas vejam o aumento em uma experiência, quando presumem que não deve haver diferença, pois as duas experiências são idênticas. Em função do tempo e do número suficiente de visitas, a diferença de elevação deve diminuir.

Assim como com um teste A/B normal, você deve decidir antecipadamente qual tamanho da amostra usar, com base no tamanho mínimo do efeito, na energia e nos níveis de significância que você achar aceitáveis. Em um teste A/A, o objetivo seria *not* ver um resultado estatisticamente significativo depois que o teste atingisse o tamanho de amostra desejado.

A [!UICONTROL Calculadora de tamanho de amostra da Adobe Target] é uma ferramenta importante para ajudá-lo a determinar o tamanho de amostra que deve ser pretendido e por quanto tempo deve executar o teste.

* [Calculadora de tamanho da Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

Além disso, consulte os seguintes artigos para obter informações sobre quanto tempo você deve executar uma atividade, bem como outras dicas e truques úteis:

* [Por quanto tempo você deve executar um teste A/B?](/help/c-activities/t-test-ab/sample-size-determination.md)
* [Dez armadilhas A/B comuns e como evitá-las](/help/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### A significância estatística afeta seus resultados de teste

O nível de significância de um teste determina a probabilidade de o teste relatar uma diferença significativa nas taxas de conversão entre duas ofertas diferentes quando, de fato, não há diferença real. Isso é conhecido como falso positivo, ou um erro do Tipo I. O nível de significância é um limite especificado pelo usuário e há uma compensação entre a tolerância para falsos positivos e o número de visitantes que devem ser incluídos no teste para escolher o nível de significância apropriado.

Um nível de significância comumente usado nos testes A/A e A/B é de 5%, o que corresponde a um nível de confiança de 95% (nível de confiança = 100% - nível de significância). Um nível de confiança de 95% significa que cada vez que você executa um teste, há uma chance de 5% de detectar um aumento estatisticamente significativo mesmo que não haja diferença entre as experiências.

Suponha que você queira atingir um nível de confiança de 95% com seu teste A/A. Com um nível de confiança de 95%, testes A/A de 1 em 20 podem mostrar um aumento estatisticamente significativo nas conversões. Com um nível de confiança de 90%, 1 em 10 testes podem mostrar aumento nas conversões ao testar experiências idênticas.

## Prática recomendada

Se você decidir que um teste A/A é necessário em sua organização, esteja ciente de que as experiências idênticas podem mostrar temporariamente uma diferença do controle. Isso pode ser normal, dependendo do tempo em que o teste pode ser executado. A diferença deve diminuir, dado mais tempo e visitantes.

A prática recomendada é usar a metodologia de teste A/B regular: decida o tamanho da amostra antecipadamente com base no tamanho mínimo do efeito, na potência e na significância desejadas usando a [Calculadora de tamanho da Adobe Target](/help/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Em seguida, aguarde o tempo e visitantes adequados antes de chegar a qualquer conclusão, e lembre-se de que, dependendo do nível de significância do seu teste, há uma chance de que uma experiência mostre uma diferença de incentivo, e até mesmo seja declarada vencedora.
