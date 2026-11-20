---
keywords: a/b;a/a;aa;
description: Saiba o que é um teste A/A, por que você pode querer executar um teste A/A, por quanto tempo você deve executar o teste e como interpretar os resultados.
title: O que é um teste A/A?
feature: A/B Tests
exl-id: 7489f4f5-3655-45f9-a743-651ba1c23c53
TQID: 'https://experienceleague.adobe.com/-kLz0mG8LaFqEbB-9M89vJWTFjfypupbcOQ3MjQz-jQ'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 7eede3484d524e87127de9147aa786484fc87c7d
workflow-type: tm+mt
source-wordcount: '915'
ht-degree: 1%
---
# Teste A/A {#aa-testing}

>[!BEGINSHADEBOX]

**Nesta página:** saiba o que é um teste A/A, por que você pode executar um teste, por que você pode ver o aumento entre experiências idênticas e a prática recomendada para executar um teste A/A em [!DNL Target].

>[!ENDSHADEBOX]

Um teste A/A divide o tráfego entre duas experiências idênticas, portanto, o teste é uma maneira de verificar se a atividade, a implementação e os relatórios funcionam conforme esperado. Mesmo assim, experiências idênticas podem, às vezes, mostrar uma diferença no aumento. Entender por que o ajuda a executar o teste e interpretar os resultados corretamente.

## O que é um teste A/A? {#what-is-aa}

Um teste A/A difere de um teste A/B padrão na maneira como o tráfego é alocado e no que você deseja aprender:

* **Teste A/B:** o tráfego está alocado a duas ou mais experiências diferentes. Normalmente, uma experiência é o &quot;controle&quot; e variações da experiência são testadas em relação ao controle para ver qual experiência cria mais aumento em determinada métrica. Normalmente, você quer descobrir um aumento na conversão.
* **Teste A/A:** o tráfego é alocado a duas experiências idênticas, normalmente com uma divisão de alocação de tráfego 50/50. Seu objetivo geralmente é determinar que há *não* diferença no aumento entre as experiências idênticas.

## Por que executar um teste A/A? {#why-aa}

Algumas organizações executam testes A/A ao implementar uma nova ferramenta de teste, como o [!DNL Target], para determinar se:

* A atividade foi configurada corretamente
* O código foi implementado corretamente
* Os relatórios são precisos

Embora poucas organizações executem testes A/A, é uma boa prática executá-los como experimentos de verificação de sanidade para criar confiança após a implementação da ferramenta ou antes de executar testes A/B que possam afetar a conversão e a receita.

## Por que experiências idênticas podem mostrar aumento {#why-lift}

Há dois motivos principais pelos quais você pode ver o aumento de uma experiência em relação a outra (idêntica) experiência:

### O teste A/A foi monitorado continuamente {#data-peeking}

Um problema comum na execução de qualquer tipo de teste, incluindo um teste A/A, é observar os resultados continuamente e interromper prematuramente um teste quando houver significância estatística e declarar uma experiência vencedora. Os analistas geralmente fazem o que se chama de &quot;espiada de dados&quot;. A espiada de dados envolve examinar os dados de teste antecipadamente e com frequência, enquanto tenta determinar qual experiência tem melhor desempenho. O risco é interromper o teste prematuramente, o que pode invalidar os resultados.

Em um teste A/A, a espiada de dados geralmente pode fazer com que os analistas vejam o aumento em uma experiência, quando, na verdade, não deve haver diferença, pois as duas experiências são idênticas. Na verdade, com a espiada contínua, os testes A/A são *garantidos* para mostrar &quot;significância estatística&quot; (ou seja, uma confiança acima de um determinado limite, como 95%) em algum ponto durante o teste.

### A significância estatística afeta os resultados dos testes {#statistical-significance}

O nível de importância de um teste determina a probabilidade de o teste relatar uma diferença significativa nos índices de conversão entre duas experiências diferentes quando, de fato, não há diferença real. Isso é conhecido como falso positivo ou erro Tipo I. O nível de significância é um limite especificado pelo usuário e há uma compensação entre a tolerância para falsos positivos e o número de visitantes que devem ser incluídos no teste ao escolher o nível de significância apropriado.

Um nível de significância comumente usado em testes A/A e A/B é de 5%, o que corresponde a um nível de confiança de 95% (nível de confiança = 100% - nível de significância). Um nível de confiança de 95% significa que, sempre que você executar um teste, há 5% de chance de detectar um aumento estatisticamente significativo, mesmo que não haja diferença entre as experiências.

Suponha que você deseje atingir um nível de confiança de 95% com seu teste A/A. Com um nível de confiança de 95%, um em cada 20 testes A/A pode mostrar aumento estatisticamente significativo nas conversões. Com um nível de confiança de 90%, um em cada dez testes pode mostrar aumento nas conversões ao testar experiências idênticas.

## Prática recomendada {#best-practice}

Se você decidir que um teste A/A é necessário em sua organização, esteja ciente de que as experiências idênticas podem mostrar temporariamente uma diferença em relação ao controle. Isso pode ser normal, dependendo do tempo que o teste tem permissão para ser executado. A diferença deve diminuir devido a mais tempo e visitantes. Dependendo do nível de importância do seu teste, também há a chance de uma experiência mostrar uma diferença no aumento e ser até mesmo declarada vencedora.

Use a metodologia de teste A/B regular:

1. Decida com antecedência qual tamanho de amostra usar, com base no tamanho mínimo de efeito (o aumento mínimo abaixo do qual um efeito não é importante para sua empresa), potência e níveis de significância que você acha aceitáveis. A **[!UICONTROL Calculadora de Tamanho da Amostra do Adobe Target]** é uma ferramenta importante para ajudá-lo a determinar o tamanho da amostra que você deve apontar e por quanto tempo você deve executar o teste. Consulte a [Calculadora de Tamanho da Amostra do Adobe Target](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6).

1. Permita o tempo e os visitantes adequados antes de chegar a qualquer conclusão. Em um teste A/A, o objetivo é *não* ver um resultado estatisticamente significativo depois que seu teste atingir o tamanho de amostra desejado.

Para obter informações sobre por quanto tempo você deve executar uma atividade e outras dicas e truques úteis, consulte os seguintes artigos:

* [Por quanto tempo você deve executar um teste A/B?](/help/main/c-activities/t-test-ab/sample-size-determination.md)
* [Dez erros comuns de A/B e como evitá-los](/help/main/c-activities/t-test-ab/common-ab-testing-pitfalls.md)
