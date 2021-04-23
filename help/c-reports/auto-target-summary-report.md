---
keywords: relatórios, direcionamento automático, direcionamento automático, AT, relatório
description: Saiba como interpretar o relatório de Resumo do direcionamento automático no Adobe Target. Você pode alternar para os relatórios de Segmentos automatizados e Atributos importantes desse relatório.
title: Como uso o relatório de resumo do direcionamento automático?
feature: Relatórios
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '691'
ht-degree: 54%

---

# ![](/help/assets/premium.png) PREMIUMAuto-Target Resumo

Informações sobre como interpretar os relatórios de [!UICONTROL Resumo do Direcionamento automático] em [!DNL Adobe Target].

>[!NOTE]
>
>O [!UICONTROL Direcionamento automático] está disponível como parte da solução do [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] como uma licença do [Target Premium](/help/c-intro/intro.md#premium).

Para exibir os relatórios de [!UICONTROL Resumo do direcionamento automático]:

1. Na página [!UICONTROL Atividades], clique na atividade [!UICONTROL Direcionamento automático] desejada.

   Se você tiver muitas atividades, poderá filtrar a lista selecionando opções no [!UICONTROL Tipo], [!UICONTROL Status], [!UICONTROL Propriedade], [!UICONTROL Fonte de relatórios], [!UICONTROL Experience Composer], [!UICONTROL Tipo de métrica], e [!UICONTROL Listas suspensas da Fonte de Atividade].

1. Clique na guia [!UICONTROL Reports] e, em seguida, clique no ícone desejado:

   * Exibição em tabela 
   * Exibição em gráfico
   * Segmentos automatizados
   * Atributos importantes

## Exibição em tabela 

A ilustração a seguir mostra como um relatório de resumo típico se parece em [!UICONTROL Visualização de tabela] ao visualizar um relatório de atividade de [!UICONTROL Direcionamento automático]:

![Relatório de exibição de tabela do Direcionamento automático](/help/c-reports/assets/at-table-view.png)

Algumas dicas e considerações ao interpretar seus relatórios de [!UICONTROL Direcionamento automático]:

* As várias linhas na tabela ajudam você a entender o desempenho da atividade.

   * As duas primeiras linhas na tabela na página de relatórios mostram os resultados de um teste A/B entre os visitantes que foram atribuídos ao controle (ou seja, experiências apresentadas aleatoriamente) e os visitantes que foram atribuídos ao algoritmo de personalização. Essas informações podem ser usadas para medir o desempenho do algoritmo de personalização em comparação com o controle apresentado aleatoriamente.
   * As linhas restantes mostram resultados em nível de experiência. Para cada experiência, há uma comparação entre a resposta média dos visitantes que mostraram essa experiência como um controle apresentado aleatoriamente e a resposta média dos visitantes que mostraram a experiência usando o algoritmo de personalização.

* O ícone de verificação verde ao lado de cada experiência no relatório indica que um modelo personalizado de aprendizagem de máquina foi gerado para essa experiência. O ícone do relógio indica que não foi fornecido tráfego suficiente para construir o modelo.

   * Como o modelo é construído por experiência, é possível ver um modelo para algumas experiências com uma marca verde e outras com um ícone de relógio.
   * Neste caso, para aumentar a velocidade da atividade com modelos construídos para todas as experiências, o tráfego adicional é enviado para experiências com modelos não construídos.
   * Deve haver pelo menos duas experiências com modelos construídos (marca de seleção verde) para que a personalização comece.

* Comparar a taxa de conversão da experiência A com a da experiência B não é a comparação correta em [!UICONTROL Direcionamento automático]. A questão é se a experiência A tem um desempenho melhor quando é apresentada de maneira inteligente versus uma maneira aleatória (em outras palavras, versus o controle). Os profissionais de marketing também devem ter cautela ao interpretar os aumentos de experiências individuais, porque o algoritmo de personalização está tentando otimizar a métrica de sucesso em toda a atividade, não em cada experiência individual.
* Experiências com o aumento mais alto podem ser entendidas como tendo a maior diferenciação dentro da população. Esse é o algoritmo que encontrou um segmento que gosta mais dessa experiência em particular.
* As várias colunas na tabela mostram o número de visitas, a taxa de conversão, o aumento médio e o nível de confiança e a confiança. Para obter mais informações, consulte [Incentivo médio, Limites de incentivo e Intervalo de confiança](/help/c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md).

## Exibição em gráfico

A ilustração a seguir mostra como um relatório de resumo típico se parece em [!UICONTROL Visualização de gráfico] ao visualizar um relatório de atividade de [!UICONTROL Direcionamento automático]:

![Relatório de exibição de gráfico de direcionamento automático](/help/c-reports/assets/at-graph-view.png)

Como mostrado abaixo, você pode usar as duas listas suspensas para escolher as métricas desejadas, a metodologia de contagem e muito mais. Consulte [Visão geral das configurações de relatório](/help/c-reports/c-report-settings/report-settings.md) para obter mais informações:

![Relatório de exibição de gráfico de direcionamento automático](/help/c-reports/assets/at-graph-view-2.png)

## Segmentos automatizados

Clique no ícone [!UICONTROL Segmentos automatizados]. Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

![Ícone de segmentos automatizados](/help/c-reports/assets/icon-automated-sements.png)

Para obter mais informações, consulte [Relatório de segmentos automatizados](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Clique no ícone [!UICONTROL Atributos importantes]. Este relatório mostra como, em atividades diferentes, atributos diferentes são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

![Ícone de atributos importantes](/help/c-reports/assets/icon-important-attributes.png)

Para obter mais informações, consulte [Relatório de atributos importantes](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md).
