---
keywords: reports;auto-target;auto target;AT;report
description: Informações sobre como interpretar o relatório Resumo do Público alvo automático no Adobe Target.
title: Relatório de Resumo do direcionamento automático
feature: reports
subtopic: Multivariate Test
topic: Standard
uuid: a30fa886-e8df-408f-bbc9-11a917a592d8
translation-type: tm+mt
source-git-commit: 56c77e1a7b5dd4e64f59b0416a16c3039a649ba3
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 57%

---


# ![Relatório de Resumo do Público alvo automático PREMIUM](/help/assets/premium.png){#auto-target-summary-report}

Information about how to interpret the [!UICONTROL Auto-Target Summary] reports in [!DNL Adobe Target].

>[!NOTE]
>
>O [!UICONTROL Direcionamento automático] está disponível como parte da solução do [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] como uma licença do [Target Premium](/help/c-intro/intro.md#premium).

Para exibir os relatórios de Resumo [!UICONTROL de Públicos alvos] automáticos:

1. Na página [!UICONTROL Atividade] , clique na atividade de Público alvo  automático desejada.

   If you have many activities, you can filter the list by selecting options from the [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Property], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], and [!UICONTROL Activity Source] drop-down lists.

1. Clique na guia [!UICONTROL Relatórios] e, em seguida, clique no ícone desejado:

   * Exibição em tabela 
   * Exibição em gráfico
   * Segmentos automatizados
   * Atributos importantes

## Exibição em tabela 

A ilustração a seguir mostra a aparência de um relatório resumido típico na Visualização [!UICONTROL da] tabela ao exibir um relatório de atividade [!UICONTROL de Público alvo] automático:

![Relatório de visualização da tabela de Público alvo automático](/help/c-reports/assets/at-table-view.png)

Some tips and considerations as you interpret your [!UICONTROL Auto-Target] reports:

* As várias linhas na tabela ajudam você a entender o desempenho da atividade.

   * As duas primeiras linhas na tabela na página de relatórios mostram os resultados de um teste A/B entre os visitantes que foram atribuídos ao controle (ou seja, experiências apresentadas aleatoriamente) e os visitantes que foram atribuídos ao algoritmo de personalização. Essas informações podem ser usadas para medir o desempenho do algoritmo de personalização em comparação com o controle apresentado aleatoriamente.
   * As linhas restantes mostram resultados em nível de experiência. Para cada experiência, há uma comparação entre a resposta média dos visitantes que mostraram essa experiência como um controle apresentado aleatoriamente e a resposta média dos visitantes que mostraram a experiência usando o algoritmo de personalização.

* O ícone de verificação verde ao lado de cada experiência no relatório indica que um modelo personalizado de aprendizagem de máquina foi gerado para essa experiência. O ícone do relógio indica que não foi fornecido tráfego suficiente para construir o modelo.

   * Como o modelo é construído por experiência, é possível ver um modelo para algumas experiências com uma marca verde e outras com um ícone de relógio.
   * Neste caso, para aumentar a velocidade da atividade com modelos construídos para todas as experiências, o tráfego adicional é enviado para experiências com modelos não construídos.
   * Deve haver pelo menos duas experiências com modelos construídos (marca de seleção verde) para que a personalização comece.

* Comparing the conversion rate of experience A with that of experience B is not the right comparison in [!UICONTROL Auto-Target]. A questão é se a experiência A tem um desempenho melhor quando é apresentada de maneira inteligente versus uma maneira aleatória (em outras palavras, versus o controle). Os profissionais de marketing também devem ter cautela ao interpretar os aumentos de experiências individuais, porque o algoritmo de personalização está tentando otimizar a métrica de sucesso em toda a atividade, não em cada experiência individual.
* Experiências com o aumento mais alto podem ser entendidas como tendo a maior diferenciação dentro da população. Esse é o algoritmo que encontrou um segmento que gosta mais dessa experiência em particular.
* As várias colunas da tabela mostram o número de visitas, a taxa de conversão, o nível médio de incentivo e confiança e a confiança. Para obter mais informações, consulte [Incentivo médio, Limites de incentivo e Intervalo de confiança](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Exibição em gráfico

A ilustração a seguir mostra a aparência de um relatório resumido típico na Visualização [!UICONTROL de] gráfico ao exibir um relatório de atividade [!UICONTROL de Público alvo] automático:

![Relatório de visualização do gráfico de Público alvo automático](/help/c-reports/assets/at-graph-view.png)

Como mostrado abaixo, você pode usar as duas listas suspensas para escolher as métricas desejadas, a metodologia de contagem e muito mais. Consulte Visão geral [das configurações do](/help/c-reports/c-report-settings/report-settings.md) relatório para obter mais informações:

![Relatório de visualização do gráfico de Público alvo automático](/help/c-reports/assets/at-graph-view-2.png)

## Segmentos automatizados

Clique no ícone Segmentos  automatizados. Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

![Ícone Segmentos automatizados](/help/c-reports/assets/icon-automated-sements.png)

Para obter mais informações, consulte Relatório [de segmentos](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md)automatizados.

## Atributos importantes

Clique no ícone Atributos  importantes. Este relatório mostra como, em atividades diferentes, atributos diferentes são mais (ou menos) importantes para como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

![Ícone de atributos importantes](/help/c-reports/assets/icon-important-attributes.png)

Para obter mais informações, consulte Relatório [de atributos](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md)importantes.
