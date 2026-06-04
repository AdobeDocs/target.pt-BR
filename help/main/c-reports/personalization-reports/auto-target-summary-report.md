---
keywords: relatórios;direcionamento automático;direcionamento automático;relatório;reports;auto-target;auto target;AT;report
description: Saiba como interpretar o relatório de Resumo do direcionamento automático no Adobe Target. Você pode alternar para os relatórios de Segmentos automatizados e Atributos importantes a partir desse relatório.
title: Como faço para usar o relatório de resumo do direcionamento automático?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
TQID: https://experienceleague.adobe.com/de9ST0undYRSL-BMmwEhvbU7PsfHgYieNAWY-qsQ-Z8
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 666
ht-degree: 35%

---

# [!UICONTROL Relatório de Resumo do direcionamento automático]

Informações sobre como interpretar os relatórios do [!UICONTROL Resumo do Direcionamento automático] em [!DNL Adobe Target].

>[!NOTE]
>
>O [!UICONTROL Direcionamento automático] está disponível como parte da solução [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] sem uma [licença do Target Premium](/help/main/c-intro/intro.md#premium).

Para exibir os relatórios do [!UICONTROL Resumo do Direcionamento automático]:

1. Na página [!UICONTROL Atividades], clique na atividade [!UICONTROL Direcionamento automático] desejada.

   Se você tiver muitas atividades, clique no ícone Filtro ( ![Ícone Filtro](/help/main/assets/icons/Filter.svg) ) para filtrar a lista selecionando opções nas listas suspensas [!UICONTROL Tipo], [!UICONTROL Status], [!UICONTROL Source de Relatórios], [!UICONTROL Experience Composer], [!UICONTROL Tipo de Métricas] e [!UICONTROL Source de Atividades].

1. Clique na guia **[!UICONTROL Relatórios]** e clique no ícone desejado:

   * **[!UICONTROL Modo de Exibição de Tabela]** ( ![ícone do Modo de Exibição de Tabela](/help/main/assets/icons/Table.svg) )
   * **[!UICONTROL Exibição em gráfico]** ( ![ícone de Exibição em gráfico](/help/main/assets/icons/GraphTrend.svg) )
   * **[!UICONTROL Segmentos automatizados]** ( ![relatório de Segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) )
   * [!UICONTROL Atributos importantes]** ( ![ícone de Atributos importantes](/help/main/assets/icons/ViewList.svg) )

## Exibição em tabela

Algumas dicas e considerações ao interpretar os relatórios do [!UICONTROL Direcionamento automático]:

* As várias linhas na tabela ajudam você a entender o desempenho da atividade.

   * As duas primeiras linhas na tabela na página do relatório mostram os resultados de um teste A/B entre os visitantes que foram atribuídos ao controle (ou seja, experiências disponibilizadas aleatoriamente) e os visitantes que foram atribuídos ao algoritmo de personalização. Essas informações podem ser usadas para medir o desempenho do algoritmo de personalização em comparação ao controle disponibilizado aleatoriamente.
   * As linhas restantes mostram resultados em nível de experiência. Para cada experiência, há uma comparação entre a resposta média dos visitantes que mostraram essa experiência como um controle apresentado aleatoriamente e a resposta média dos visitantes que mostraram a experiência usando o algoritmo de personalização.

* O ícone de verificação verde ao lado de cada experiência no relatório indica que um modelo personalizado de aprendizagem de máquina foi gerado para essa experiência. O ícone do relógio indica que não foi fornecido tráfego suficiente para construir o modelo.

   * Como o modelo é construído por experiência, é possível ver um modelo para algumas experiências com uma marca verde e outras com um ícone de relógio.
   * Neste caso, para aumentar a velocidade da atividade com modelos construídos para todas as experiências, o tráfego adicional é enviado para experiências com modelos não construídos.
   * Deve haver pelo menos duas experiências com modelos criados (marca de seleção verde) para que a personalização comece.

* Comparar o índice de conversão da experiência A com o da experiência B não é a comparação correta no [!UICONTROL Direcionamento automático]. A questão é se a experiência A tem um desempenho melhor quando é apresentada de maneira inteligente versus uma maneira aleatória (em outras palavras, versus o controle). Os profissionais de marketing também devem ter cautela ao interpretar os aumentos de experiências individuais, porque o algoritmo de personalização está tentando otimizar a métrica de sucesso em toda a atividade, não em cada experiência individual.
* Experiências com o aumento mais alto podem ser entendidas como tendo a maior diferenciação dentro da população. Ou seja, o algoritmo encontrou um segmento que mais gosta dessa experiência específica.
* As várias colunas na tabela mostram o número de visitas, a taxa de conversão, o nível médio de aumento e confiança e a confiança. Para obter mais informações, consulte [Cálculos estatísticos em testes A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Exibição em gráfico

Use as duas listas suspensas para escolher as métricas, a metodologia de contagem e muito mais. Consulte [Visão geral das configurações do relatório](/help/main/c-reports/c-report-settings/report-settings.md) para obter mais informações:

## Segmentos automatizados

Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização [!DNL Target], responderam às ofertas/experiências na atividade.

Para obter mais informações, consulte o [relatório de Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Este relatório mostra como, em atividades diferentes, atributos distintos são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

Para obter mais informações, consulte o [relatório de Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
