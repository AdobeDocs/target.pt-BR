---
keywords: faq;frequently asked questions;analytics for target;a4T;lift;ad hoc;report builder;confidence
description: Este tópico contém respostas para as perguntas mais frequentes sobre aumento e confiança ao usar o Analytics como origem de geração de relatórios do Target (A4T).
title: Aumento e Confiança - Perguntas frequentes sobre o A4T
topic: Standard
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: b5191230c76135d5299754e72c9651d018086e60

---


# Aumento e Confiança - Perguntas frequentes sobre o A4T{#lift-and-confidence-a-t-faq}

Este tópico contém respostas para as perguntas mais frequentes sobre aumento e confiança ao usar o Analytics como origem de geração de relatórios do Target (A4T).

## Posso realizar cálculos offline para o A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics]. Para obter mais informações, consulte &quot;Realização de cálculos off-line do Analytics para Target (A4T)&quot; em [Nível de confiança e Intervalo de confiança](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Como o aumento é calculado? {#section_8CAE788EED5646C4B1D64A0D22070734}

Aumento é a diferença percentual entre os resultados da página de controle e uma variante de teste bem-sucedida.

## Como a confiança é calculada?  {#section_97DB24D833E742988318CA65DA65DAD9}

O nível de confiança é a probabilidade de a taxa de conversão medida diferir da taxa de conversão da página de campeão por outros motivos que não o acaso.

## Por que não posso ver o aumento e a confiança nas métricas calculadas?  {#section_D3E44E24782A409DBD88AE4D1595CB58}

No momento, o incentivo e a confiança não são suportados com métricas calculadas. No entanto, na maioria dos casos isso não deve ser um problema, pois a taxa de conversão calculada no relatório A4T já é uma métrica calculada na qual o denominador é a métrica de normalização (instâncias, visitas, visitantes). Por exemplo, se você selecionar a métrica de ordens e a métrica de normalização for visitantes, a taxa de conversão (pedidos/visitante) será calculada automaticamente por meio do relatórios A4T. A métrica de incentivo resultante reflete a diferença nessa taxa de conversão entre as experiências de texto quando comparada ao padrão.

A maioria das métricas calculadas para otimização se enquadram em uma das duas categorias: Métricas de agregação e outros cálculos de conversão, como Valor médio do pedido (AOV).

Métricas de Agregação são usadas quando uma organização usa eventos únicos para capturar diferentes &quot;sabores&quot; da conversão de gravação. Por exemplo, se sua meta é promover envios de formulário de cliente potencial e você tem 10 formulários de cliente potencial diferentes, uma empresa pode criar eventos exclusivos para contar cada tipo de conversão de formulário. Para ver a quantidade total de todos os formulários de lead enviados, eles devem criar uma métrica calculada simples para adicioná-los todos juntos. Uma maneira melhor e mais moderna de rastrear isso é implementar um único evento de envio de cliente potencial no Analytics e, em seguida, usar uma eVar para coletar o tipo de formulário de cliente potencial. O uso desse método requer menos variáveis e elimina a necessidade de agregação de métricas individuais e você ainda tem a capacidade de ver a conversão holística do formulário de cliente potencial e dividi-lo por tipo de formulário de cliente potencial usando a eVar. Isso também elimina a necessidade de métricas de agregação ao avaliar o desempenho de uma Atividade de Público alvo.

Outra métrica calculada comum, Valor médio do pedido, não é atualmente suportada com incentivo e confiança porque a métrica de normalização não é padrão (instâncias, visitas, visitantes). Em vez disso, a recomendação é manter um olho nas duas métricas de influência da AOV, Receita por Visitante e Taxa de conversão.

## Como o A4T gerencia os cálculos de confiança?  {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

O A4T usa cálculos de métricas não binárias com a soma dos dados quadrados. A variação é calculada usando a soma dos dados quadrados. Pedidos extremos não são levados em consideração.

Qualquer segmento do Analytics pode ser aplicado ao relatório. Essa é a maneira como você pode obter o &quot;pedido extremo&quot; entre outras opções do segmento. Uma métrica também pode ser construída para limitar as coisas, como quantas vezes um visitante converteu.

## O aumento e a confiança funcionam na Ad Hoc e Report Builder? Se não é nativo, posso fazer isso sozinho? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

O aumento e a confiança não funcionam na Ad Hoc ou no Report Builder e não podem ser calculados para variáveis contínuas. É possível calcular manualmente para métricas binárias.
