---
description: Este tópico contém respostas para as perguntas mais frequentes sobre aumento e confiança ao usar o Analytics como origem de geração de relatórios do Target (A4T).
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; aumento; ad hoc; construtor de relatórios; confiança
seo-description: Este tópico contém respostas para as perguntas mais frequentes sobre aumento e confiança ao usar o Analytics como origem de geração de relatórios do Target (A4T).
seo-title: Aumento e Confiança - Perguntas frequentes sobre o A4T
solution: Target
title: Aumento e Confiança - Perguntas frequentes sobre o A4T
topic: Padrão
uuid: 7d0402f3-d6f2-422e-b69c-86e10120ac83
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Aumento e Confiança - Perguntas frequentes sobre o A4T{#lift-and-confidence-a-t-faq}

Este tópico contém respostas para as perguntas mais frequentes sobre aumento e confiança ao usar o Analytics como origem de geração de relatórios do Target (A4T).

## Posso realizar cálculos offline para o A4T? {#section_55B5B750E17D414CAECBEECE27B15D81}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics]. Para obter mais informações, consulte "Realização de cálculos off-line do Analytics para Target (A4T)" em [Nível de confiança e Intervalo de confiança](../../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Como o aumento é calculado? {#section_8CAE788EED5646C4B1D64A0D22070734}

Aumento é a diferença percentual entre os resultados da página de controle e uma variante de teste bem-sucedida.

## Como a confiança é calculada? {#section_97DB24D833E742988318CA65DA65DAD9}

O nível de confiança é a probabilidade de a taxa de conversão medida diferir da taxa de conversão da página de campeão por outros motivos que não o acaso.

## Por que não posso ver o aumento e a confiança nas métricas calculadas? {#section_D3E44E24782A409DBD88AE4D1595CB58}

Atualmente, o aumento e a confiança não podem ser gerados para métricas calculadas. No entanto, na maioria dos casos, isso não deve ser um problema porque o aumento é normalizado pela métrica de normalização. Por exemplo, se você selecionar aumento para pedidos e a métrica de normalização for visitas, o aumento será calculado na proporção dos dois, que é a taxa de conversão.

## Como o A4T gerencia os cálculos de confiança? {#section_66115EAF1BA34F7A8FCED7B08DA4F99C}

O A4T usa cálculos de métricas não binárias com a soma dos dados quadrados. A variação é calculada usando a soma dos dados quadrados. Pedidos extremos não são levados em consideração.

Qualquer segmento do Analytics pode ser aplicado ao relatório. Essa é a maneira como você pode obter o "pedido extremo" entre outras opções do segmento. Uma métrica também pode ser construída para limitar as coisas, como quantas vezes um visitante converteu.

## O aumento e a confiança funcionam na Ad Hoc e Report Builder? Se não é nativo, posso fazer isso sozinho? {#section_D8BB69AE700B4C5CB5FD28DB51F9A4E9}

O aumento e a confiança não funcionam na Ad Hoc ou no Report Builder e não podem ser calculados para variáveis contínuas. É possível calcular manualmente para métricas binárias.
