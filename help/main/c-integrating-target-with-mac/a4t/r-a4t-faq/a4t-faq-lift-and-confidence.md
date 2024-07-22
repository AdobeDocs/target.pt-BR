---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; aumento; ad hoc; construtor de relatórios; confiança
description: Encontre respostas para perguntas sobre aumento e confiança ao usar o Analytics for [!DNL Target] (A4T). O A4T permite usar os relatórios do Analytics para  [!DNL Target]  atividades.
title: Onde posso encontrar informações sobre aumento e confiança com o A4T?
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
source-git-commit: aff96eca1380f4274dba0c1567f6e41d42f4b5ab
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 15%

---

# Aumento e Confiança - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre aumento e confiança ao usar o [!DNL Adobe Analytics] como fonte de relatórios para o [!DNL Adobe Target] (A4T).

## Posso realizar cálculos offline para o A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

+++Resposta
Você pode realizar cálculos offline para o A4T, mas isso requer uma etapa com as exportações de dados no [!DNL Analytics]. Para obter mais informações, consulte [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## Como o aumento é calculado? {#section_8CAE788EED5646C4B1D64A0D22070734}

+++Resposta
Aumento é a diferença percentual entre os resultados da página de controle e uma variante de teste bem-sucedida.

+++

## Como a confiança é calculada?  {#section_97DB24D833E742988318CA65DA65DAD9}

+++Resposta
O nível de confiança é uma probabilidade, expressa como uma porcentagem, que é igual a `1 - p-value`, onde `p-value` é computado a partir de um teste t. Consulte [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

+++

## Por que não posso ver o aumento e a confiança nas métricas calculadas?  {#lift-confidence}

+++Resposta
No momento, as métricas calculadas não são compatíveis com as funções de aumento e confiança. O Analytics calcula métricas em nível agregado, em vez de em nível de visitante. A confiança, em particular, é um cálculo em nível de visitante.

Eventos não calculados (padrão) são aceitos em incentivo e confiança. Eles se tornam o numerador na função lift; o numerador não pode ser um cálculo em si. O denominador são as métricas de normalização (impressões, visitas ou visitantes). Alguns exemplos de eventos padrão incluem pedidos, receita, conversões de atividade, eventos personalizados 1-1000 e assim por diante. Métricas de otimização comuns, como taxa de conversa (Pedidos/Visitante) e RPV (Receita/Visitante) são compatíveis com aumento e confiança.

Exemplos de métricas ou casos de uso não compatíveis incluem:

* Valor médio de pedido (Receita/Pedido, por visitante). Não há suporte para AOV porque o numerador é uma métrica calculada. Em vez disso, a recomendação é considerar as duas métricas influenciadoras do AOV - Receita por visitantes e Taxa de conversão.
* Métricas calculadas que são a soma dos eventos padrão. Por exemplo, você pode rastrear dez formulários de cliente potencial diferentes em dez eventos separados e depois adicioná-los juntos para obter o envio total de clientes potenciais. Um método recomendado para rastrear esses eventos é implementar um único evento de envio de lead no Analytics e usar um eVar para coletar o tipo de formulário de lead. O uso desse método requer menos variáveis e garante que você possa usar a métrica de envio de cliente potencial único em funções de aumento e confiança.

+++

## Como o A4T gerencia os cálculos de confiança?  {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

+++Resposta
[!DNL Adobe Analytics] trata todas as métricas como não binárias e, portanto, calcula os valores de confiança/p de uma maneira diferente do uso de métricas binárias em um teste t regular. Especificamente, os cálculos usados pelo A4T permitem que cada usuário tenha um resultado de métrica contínua (não apenas 1 ou 0 para cada usuário), de modo que a variação (ou, de forma relativa, o desvio padrão) para cada experiência deve ser calculada adequadamente. Pedidos extremos não são considerados. Além disso, o cálculo de confiança não aplica uma correção Bonferroni para várias ofertas.

+++

## O aumento e a confiança funcionam na Ad Hoc e Report Builder? Se não é nativo, posso fazer isso sozinho? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

+++Resposta
O incentivo e a confiança não funcionam na Ad Hoc ou no Report Builder e não podem ser calculados por conta própria para variáveis contínuas. É possível calcular manualmente para métricas binárias.
+++
