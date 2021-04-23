---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; aumento; ad hoc; construtor de relatórios; confiança
description: Encontre respostas para perguntas sobre aumento e confiança ao usar o Analytics para  [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] atividades.
title: Onde posso encontrar informações sobre aumento e confiança com o A4T?
feature: Analytics for Target (A4T)
exl-id: 42fd179b-944a-4a0a-b299-85ea4a7ea244
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 41%

---

# Aumento e Confiança - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre aumento e confiança ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T).

## Posso realizar cálculos offline para o A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics]. Para obter mais informações, consulte &quot;Realização de cálculos off-line do Analytics para Target (A4T)&quot; em [Nível de confiança e Intervalo de confiança](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Como o aumento é calculado? {#section_8CAE788EED5646C4B1D64A0D22070734}

Aumento é a diferença percentual entre os resultados da página de controle e uma variante de teste bem-sucedida.

## Como a confiança é calculada?   {#section_97DB24D833E742988318CA65DA65DAD9}

O nível de confiança é a probabilidade de a taxa de conversão medida diferir da taxa de conversão da página de campeão por outros motivos que não o acaso.

## Por que não posso ver o aumento e a confiança nas métricas calculadas?   {#lift-confidence}

No momento, as métricas calculadas não são compatíveis com funções de incentivo e confiança. O Analytics calcula métricas em um nível agregado, e não em um nível de visitante. A confiança, em particular, é um cálculo no nível do visitante.

Eventos não calculados (padrão) são aceitos no incentivo e na confiança. Eles se tornam o numerador na função de elevação; o numerador não pode ser um cálculo em si. O denominador é a métrica de normalização (impressões, visitas ou visitantes). Alguns exemplos de eventos padrão incluem pedidos, receita, conversões de atividade, eventos personalizados 1-1000 e assim por diante. Métricas de otimização comuns, como taxa de conversa (Pedidos/Visitante) e RPV (Receita/Visitante) são suportadas em incentivo e confiança.

Exemplos de métricas ou casos de uso não suportados incluem:

* Valor Médio de Pedido (Receita/Pedido, por Visitante). Não há suporte para AOV porque o numerador é uma métrica calculada. Em vez disso, a recomendação é considerar as duas métricas influentes de AOV - Receita por visitante e Taxa de conversão.
* Métricas calculadas que são a soma dos eventos padrão. Por exemplo, você pode rastrear dez formulários de lead diferentes em dez eventos separados e adicioná-los juntos para obter o total de envios de lead. Um método recomendado para rastrear esses eventos é implementar um único evento de envio de lead no Analytics e, em seguida, usar um eVar para coletar o tipo de formulário de lead. O uso desse método requer menos variáveis e garante que você possa usar a única métrica de envio de lead nas funções de lift e confiança.

## Como o A4T gerencia os cálculos de confiança?   {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

O A4T usa cálculos de métricas não binárias com a soma dos dados quadrados. A variação é calculada usando a soma dos dados quadrados. Pedidos extremos não são considerados. Além disso, o cálculo da confiança não aplica uma correção de Bonferroni para várias ofertas.

## O aumento e a confiança funcionam na Ad Hoc e Report Builder? Se não é nativo, posso fazer isso sozinho? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

O aumento e a confiança não funcionam na Ad Hoc ou no Report Builder e não podem ser calculados para variáveis contínuas. É possível calcular manualmente para métricas binárias.
