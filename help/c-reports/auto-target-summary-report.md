---
keywords: reports;auto-target;auto target;AT
description: Informações sobre como interpretar o relatório de Resumo do direcionamento automático.
title: Relatório de Resumo do direcionamento automático
subtopic: Multivariate Test
topic: Standard
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: tm+mt
source-git-commit: 3faba3d3158bed69ae5d756fb70c97d17110c1d8

---


# Relatório de Resumo do direcionamento automático{#auto-target-summary-report}

Informações sobre como interpretar os relatórios de Resumo de Segmentação Automática.

Para exibir os relatórios de Resumo de Segmentação Automática:

1. Na página [!UICONTROL Atividades] , clique na atividade de Segmentação automática desejada.

   Se você tiver muitas atividades, poderá filtrar a lista selecionando opções nas listas suspensas Tipo, Status, Propriedade, Fonte de relatórios, Criador de experiências, Tipo de métricas e Fonte de atividade.

1. Clique na guia [!UICONTROL Relatórios].

## Exibição em tabela 

A ilustração a seguir mostra a aparência de um relatório resumido típico em &quot;exibição de tabela&quot; ao usar o AutoTarget:

![Relatório de exibição de tabela de direcionamento automático](/help/c-reports/assets/at-table-view.png)

Algumas dicas e considerações ao interpretar seus relatórios de Direcionamento automático:

* As várias linhas na tabela ajudam a entender o desempenho da atividade.

   * As duas primeiras linhas na tabela na página de relatórios mostram os resultados de um teste A/B entre os visitantes que foram atribuídos ao controle (ou seja, experiências apresentadas aleatoriamente) e os visitantes que foram atribuídos ao algoritmo de personalização. Essas informações podem ser usadas para medir o desempenho do algoritmo de personalização em comparação com o controle apresentado aleatoriamente.
   * As linhas restantes mostram resultados em nível de experiência. Para cada experiência, há uma comparação entre a resposta média dos visitantes que mostraram essa experiência como um controle apresentado aleatoriamente e a resposta média dos visitantes que mostraram a experiência usando o algoritmo de personalização.

* O ícone de verificação verde ao lado de cada experiência no relatório indica que um modelo personalizado de aprendizagem de máquina foi gerado para essa experiência. O ícone do relógio indica que não foi fornecido tráfego suficiente para construir o modelo.

   * Como o modelo é construído por experiência, é possível ver um modelo para algumas experiências com uma marca verde e outras com um ícone de relógio.
   * Neste caso, para aumentar a velocidade da atividade com modelos construídos para todas as experiências, o tráfego adicional é enviado para experiências com modelos não construídos.
   * Deve haver pelo menos duas experiências com modelos construídos (marca de seleção verde) para que a personalização comece.

* Comparar a taxa de conversão da experiência A com a experiência B não é a comparação correta no Direcionamento automático. A questão é se a experiência A tem um desempenho melhor quando é apresentada de maneira inteligente versus uma maneira aleatória (em outras palavras, versus o controle). Os profissionais de marketing também devem ter cautela ao interpretar os aumentos de experiências individuais, porque o algoritmo de personalização está tentando otimizar a métrica de sucesso em toda a atividade, não em cada experiência individual.
* Experiências com o aumento mais alto podem ser entendidas como tendo a maior diferenciação dentro da população. Esse é o algoritmo que encontrou um segmento que gosta mais dessa experiência em particular.
* As várias colunas da tabela mostram o número de visitas, a taxa de conversão, o aumento médio e o nível de confiança e a confiança. Para obter mais informações, consulte [Incentivo médio, Limites de incentivo e Intervalo de confiança](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Exibição em gráfico

A ilustração a seguir mostra a aparência de um relatório resumido típico em &quot;exibição de gráfico&quot; ao usar o AutoTarget:

![Relatório de exibição de gráfico de direcionamento automático](/help/c-reports/assets/at-graph-view.png)

Como mostrado abaixo, você pode usar as duas listas suspensas para escolher as métricas desejadas, a metodologia de contagem e muito mais. Consulte Visão geral [das configurações do](/help/c-reports/c-report-settings/report-settings.md) relatório para obter mais informações:

![Relatório de exibição de gráfico de direcionamento automático](/help/c-reports/assets/at-graph-view-2.png)

## Segmentos automatizados

Clique no ícone Segmentos automatizados. Este relatório mostra como os diferentes visitantes respondem de forma diferente às ofertas/experiências em sua atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

![Ícone Segmentos automatizados](/help/c-reports/assets/icon-automated-sements.png)

Para obter mais informações, consulte Relatório [de segmentos](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatizados.

## Atributos importantes

Clique no ícone Atributos importantes. Este relatório mostra como, em diferentes atividades, os diferentes atributos são mais (ou menos) importantes para como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

![Ícone de atributos importantes](/help/c-reports/assets/icon-important-attributes.png)

Para obter mais informações, consulte Relatório [de atributos](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)importantes.
