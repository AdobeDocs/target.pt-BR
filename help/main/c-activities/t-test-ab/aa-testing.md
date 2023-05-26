---
keywords: a/b;a/a;aa;
description: Saiba o que é um teste A/A, por que você pode querer executar um teste A/A, por quanto tempo você deve executar o teste e como interpretar os resultados.
title: O que é um teste A/A?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '940'
ht-degree: 1%

---

# Teste A/A

Antes de executar um teste A/A no site usando [!DNL Adobe Target]Além disso, é importante entender o que é um teste A/A, por que você pode querer executar um teste A/A, por quanto tempo você deve executar o teste e como interpretar os resultados.

## O que é um teste A/A?

Antes de explicar o teste A/A, é bom revisar o teste A/B para que possamos discutir as diferenças.

Em um teste A/B padrão, o tráfego é alocado para duas ou mais experiências diferentes. Normalmente, uma experiência é o &quot;controle&quot; e variações da experiência são testadas em relação ao controle para ver qual experiência cria mais aumento em determinada métrica.

No entanto, o teste A/A envolve alocar o tráfego para duas experiências idênticas, normalmente com uma divisão de alocação de tráfego 50/50. Com um teste A/B padrão, normalmente é desejável descobrir um aumento na conversão. Isso é diferente de um teste A/A no qual seu objetivo geralmente é determinar que há *não* diferença de aumento entre as experiências idênticas.

## Por que você desejaria testar duas experiências idênticas e o que isso faz?

Algumas organizações executam testes A/A ao implementar uma nova ferramenta de teste, como [!DNL Target], para determinar se:

* A atividade foi configurada corretamente
* O código foi implementado corretamente
* Os relatórios são precisos

Embora poucas organizações executem testes A/A, na verdade, é uma boa prática executá-los como experimentos de &quot;sanidade&quot; para criar confiança após implementar a ferramenta ou antes de executar testes A/B que possam afetar a conversão e a receita.

## Por que você pode ver o aumento de uma experiência quando as experiências são idênticas?

Há vários motivos pelos quais você pode ver o aumento de uma experiência em relação a outra experiência (idêntica):

### O teste A/A foi monitorado continuamente

Um problema comum na execução de qualquer tipo de teste, incluindo um teste A/A, é observar os resultados continuamente e interromper prematuramente um teste assim que você vir significância estatística e declarar uma experiência vencedora. Os analistas geralmente fazem o que se chama de &quot;espiada de dados&quot;. A espiada de dados envolve examinar os dados de teste antecipadamente e com frequência, enquanto tenta determinar qual experiência tem melhor desempenho. O risco é interromper o teste prematuramente, o que pode invalidar os resultados.

Em um teste A/A, a espiada de dados geralmente pode fazer com que os analistas vejam o aumento em uma experiência, quando, na verdade, não deve haver diferença, pois as duas experiências são idênticas. Na verdade, com espiada contínua, os testes A/A são _garantido_ para mostrar &quot;significância estatística&quot; (ou seja, uma confiança acima de um determinado limite, como 95%) em algum momento durante o teste.

Para evitar isso, e assim como em um teste A/B regular, você deve decidir antecipadamente qual tamanho de amostra usar, com base no tamanho mínimo de efeito (o aumento mínimo abaixo do qual um efeito não é importante para sua empresa), potência e níveis de significância que você acha aceitáveis.

Em um teste A/A, o objetivo seria então *não* ver um resultado estatisticamente significativo depois de o teste ter atingido o tamanho de amostra desejado.

A variável [!UICONTROL Calculadora de tamanho da amostra do Adobe Target] O é uma ferramenta importante para ajudá-lo a determinar o tamanho da amostra que deve ser direcionado e por quanto tempo você deve executar o teste.

* [Calculadora de tamanho do Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6)

Além disso, consulte os seguintes artigos para obter informações sobre por quanto tempo você deve executar uma atividade, bem como outras dicas e truques úteis:

* [Por quanto tempo você deve executar um teste A/B?](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [Dez erros comuns de A/B e como evitá-los](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)

### A significância estatística afeta os resultados dos testes

O nível de importância de um teste determina a probabilidade de o teste relatar uma diferença significativa nas taxas de conversão entre duas ofertas diferentes quando, na verdade, não há diferença real. Isso é conhecido como falso positivo ou erro Tipo I. O nível de significância é um limite especificado pelo usuário e há uma compensação entre a tolerância para falsos positivos e o número de visitantes que devem ser incluídos no teste ao escolher o nível de significância apropriado.

Um nível de significância comumente usado em testes A/A e A/B é de 5%, o que corresponde a um nível de confiança de 95% (nível de confiança = 100% - nível de significância). Um nível de confiança de 95% significa que, sempre que você executar um teste, há 5% de chance de detectar um aumento estatisticamente significativo, mesmo que não haja diferença entre as experiências.

Suponha que você deseje atingir um nível de confiança de 95% com seu teste A/A. Com um nível de confiança de 95%, um em cada 20 testes A/A pode mostrar aumento estatisticamente significativo nas conversões. Com um nível de confiança de 90%, um em cada dez testes pode mostrar aumento nas conversões ao testar experiências idênticas.

## Prática recomendada

Se você decidir que um teste A/A é necessário em sua organização, esteja ciente de que as experiências idênticas podem mostrar temporariamente uma diferença em relação ao controle. Isso pode ser normal, dependendo do tempo que o teste tem permissão para ser executado. A diferença deve diminuir devido a mais tempo e visitantes.

A prática recomendada é usar uma metodologia de teste A/B regular: decida o tamanho da amostra antecipadamente com base em um tamanho de efeito relevante mínimo, na potência desejada e na importância usando o [Calculadora de tamanho do Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

Em seguida, aguarde o tempo necessário e os visitantes antes de chegar a qualquer conclusão e lembre-se de que, dependendo do nível de significância do seu teste, há a chance de uma experiência mostrar uma diferença de aumento e até mesmo ser declarada vencedora.
