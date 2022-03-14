---
keywords: a/b;a/a;aa;
description: Saiba o que é um teste A/A, por que você pode querer executar um teste A/A, por quanto tempo deve executar o teste e como interpretar os resultados.
title: O que é Teste A/A?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 1%

---

# Teste A/A

Antes de executar um teste A/A no seu site usando [!DNL Adobe Target], é importante entender o que é um teste A/A, por que você pode querer executar um teste A/A, por quanto tempo deve executar o teste e como interpretar os resultados.

## O que é teste A/A?

Antes de explicar o teste A/A, é bom revisar o teste A/B para que possamos discutir as diferenças.

Em um teste A/B padrão, o tráfego é alocado para duas ou mais experiências diferentes. Uma experiência é normalmente o &quot;controle&quot; e as variações da experiência são testadas em relação ao controle para ver qual experiência cria mais incentivo em uma determinada métrica.

No entanto, o teste A/A envolve a alocação de tráfego a duas experiências idênticas, normalmente com uma divisão de alocação de tráfego 50/50. Com um teste A/B padrão, você geralmente deseja descobrir um aumento na conversão. Isso difere de um teste A/A no qual sua meta normalmente é determinar que haja um *não* diferença no incentivo entre as experiências idênticas.

## Por que você gostaria de testar duas experiências idênticas e o que isso consegue?

Algumas organizações executam testes A/A ao implementar uma nova ferramenta de teste, como [!DNL Target]para determinar se:

* A atividade foi configurada corretamente
* O código foi implementado corretamente
* O relatório é preciso

Embora poucas organizações executem testes A/A, na verdade é uma boa prática executá-los como experimentos de &quot;sanidade&quot; para criar confiança após a implementação da ferramenta ou antes de executar testes A/B que possam afetar a conversão e a receita.

## Por que você pode ver incentivo para uma experiência quando as experiências são idênticas?

Há vários motivos pelos quais você pode ver o incentivo em uma experiência em vez de outra experiência (idêntica):

### O teste A/A foi monitorado continuamente

Um problema comum em executar qualquer tipo de teste, incluindo um teste A/A, é observar os resultados continuamente e interromper prematuramente um teste assim que você visualizar significância estatística e declarar uma experiência vencedora. Os analistas geralmente fazem o que é chamado de &quot;pico de dados&quot;. O pico de dados envolve observar os dados de teste precocemente e com frequência, enquanto tenta determinar qual experiência está tendo melhor desempenho. O risco é parar o teste prematuramente, o que pode invalidar os resultados.

Em um teste A/A, o pico de dados geralmente pode fazer com que os analistas vejam o aumento em uma experiência, quando, de fato, não deve haver diferença, pois as duas experiências são idênticas. Na verdade, com uma espionagem contínua, os testes A/A são na verdade _garantido_ para mostrar &quot;significância estatística&quot; (ou seja, uma confiança acima de um determinado limite, como 95%) em algum momento durante o teste.

Para evitar isso e como em um teste A/B regular, você deve decidir antecipadamente qual tamanho de amostra usar, com base no tamanho mínimo do efeito (o aumento mínimo abaixo do qual um efeito não é importante para sua empresa), energia e níveis de significância que você considera aceitáveis.

Em um teste A/A, o objetivo seria *not* consulte um resultado estatisticamente significativo depois que o teste atingir o tamanho de amostra desejado.

O [!UICONTROL Calculadora de tamanho da amostra do Adobe Target] O é uma ferramenta importante para ajudá-lo a determinar para qual tamanho de amostra você deve direcionar e por quanto tempo você deve executar o teste.

* [Calculadora de tamanho da Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

Além disso, consulte os seguintes artigos para obter informações sobre por quanto tempo você deve executar uma atividade, bem como outras dicas e truques úteis:

* [Por quanto tempo você deve executar um teste A/B?](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [Dez erros comuns em A/B e como evitá-los](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### A significância estatística afeta os resultados do teste

O nível de significância de um teste determina a probabilidade de o teste relatar uma diferença significativa nas taxas de conversão entre duas ofertas diferentes quando, de fato, não há diferença real. Isso é conhecido como falso positivo ou um erro do Tipo I. O nível de significância é um limite especificado pelo usuário e há uma compensação entre a tolerância para falsos positivos e o número de visitantes que devem ser incluídos no teste na escolha do nível de significância apropriado.

Um nível de significância comumente usado em testes A/A e A/B é 5%, o que corresponde a um nível de confiança de 95% (nível de confiança = 100% - nível de significância). Um nível de confiança de 95% significa que toda vez que você executa um teste, há uma chance de 5% de detectar um aumento estatisticamente significativo, mesmo que não haja diferença entre as experiências.

Suponha que você queira atingir um nível de confiança de 95% com seu teste A/A. Com um nível de confiança de 95%, testes A/A de 1 em 20 podem mostrar um aumento estatisticamente significativo nas conversões. Com um nível de confiança de 90%, 1 em 10 testes podem mostrar aumento nas conversões ao testar experiências idênticas.

## Prática recomendada

Se você decidir que um teste A/A é necessário em sua organização, esteja ciente de que as experiências idênticas podem mostrar temporariamente uma diferença do controle. Isso pode ser normal, dependendo do tempo em que o teste pode ser executado. A diferença deve diminuir, considerando mais tempo e visitantes.

A prática recomendada é usar a metodologia de teste A/B regular: decida com antecedência o tamanho da amostra com base no tamanho mínimo de efeito relevante, potência e significado desejados usando o [Calculadora de tamanho da Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Em seguida, permita tempo e visitantes adequados antes de chegar a qualquer conclusão e lembre-se de que, dependendo do nível de significância do seu teste, há uma chance de que uma experiência mostre uma diferença de aumento e até seja declarada a vencedora.
