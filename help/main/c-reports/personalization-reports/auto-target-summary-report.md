---
keywords: relatórios, direcionamento automático, direcionamento automático, AT, relatório
description: Saiba como interpretar o relatório de Resumo do direcionamento automático no Adobe Target. Você pode alternar para os relatórios de Segmentos automatizados e Atributos importantes desse relatório.
title: Como uso o relatório de resumo do direcionamento automático?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 098fcc0e-8e17-4898-ab2f-ec74472562ff
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 53%

---

# Relatório de Resumo do direcionamento automático

Informações sobre como interpretar o [!UICONTROL Resumo do direcionamento automático] relatórios em [!DNL Adobe Target].

>[!NOTE]
>
>O [!UICONTROL Direcionamento automático] está disponível como parte da solução do [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] como uma licença do [Target Premium](/help/main/c-intro/intro.md#premium).

Para exibir o [!UICONTROL Resumo do direcionamento automático] relatórios:

1. No [!UICONTROL Atividades] clique no [!UICONTROL Direcionamento automático] atividade .

   Se você tiver muitas atividades, poderá filtrar a lista selecionando opções no [!UICONTROL Tipo], [!UICONTROL Status], [!UICONTROL Propriedade], [!UICONTROL Fonte de geração de relatórios], [!UICONTROL Experience Composer], [!UICONTROL Tipo de métrica]e [!UICONTROL Fonte da atividade] listas suspensas.

1. Clique no botão [!UICONTROL Relatórios] e clique no ícone desejado:

   * Exibição em tabela 
   * Exibição em gráfico
   * Segmentos automatizados
   * Atributos importantes

## Exibição em tabela 

A ilustração a seguir mostra a aparência de um relatório de resumo típico em [!UICONTROL Exibição em tabela] ao visualizar uma [!UICONTROL Direcionamento automático] relatório da atividade:

![Relatório de exibição de tabela do Direcionamento automático](/help/main/c-reports/assets/at-table-view.png)

Algumas dicas e considerações ao interpretar seu [!UICONTROL Direcionamento automático] relatórios:

* As várias linhas na tabela ajudam você a entender o desempenho da atividade.

   * As duas primeiras linhas na tabela na página de relatórios mostram os resultados de um teste A/B entre os visitantes que foram atribuídos ao controle (ou seja, experiências apresentadas aleatoriamente) e os visitantes que foram atribuídos ao algoritmo de personalização. Essas informações podem ser usadas para medir o desempenho do algoritmo de personalização em comparação com o controle apresentado aleatoriamente.
   * As linhas restantes mostram resultados em nível de experiência. Para cada experiência, há uma comparação entre a resposta média dos visitantes que mostraram essa experiência como um controle apresentado aleatoriamente e a resposta média dos visitantes que mostraram a experiência usando o algoritmo de personalização.

* O ícone de verificação verde ao lado de cada experiência no relatório indica que um modelo personalizado de aprendizagem de máquina foi gerado para essa experiência. O ícone do relógio indica que não foi fornecido tráfego suficiente para construir o modelo.

   * Como o modelo é construído por experiência, é possível ver um modelo para algumas experiências com uma marca verde e outras com um ícone de relógio.
   * Neste caso, para aumentar a velocidade da atividade com modelos construídos para todas as experiências, o tráfego adicional é enviado para experiências com modelos não construídos.
   * Deve haver pelo menos duas experiências com modelos construídos (marca de seleção verde) para que a personalização comece.

* Comparar a taxa de conversão da experiência A com a experiência B não é a comparação correta em [!UICONTROL Direcionamento automático]. A questão é se a experiência A tem um desempenho melhor quando é apresentada de maneira inteligente versus uma maneira aleatória (em outras palavras, versus o controle). Os profissionais de marketing também devem ter cautela ao interpretar os aumentos de experiências individuais, porque o algoritmo de personalização está tentando otimizar a métrica de sucesso em toda a atividade, não em cada experiência individual.
* Experiências com o aumento mais alto podem ser entendidas como tendo a maior diferenciação dentro da população. Esse é o algoritmo que encontrou um segmento que gosta mais dessa experiência em particular.
* As várias colunas na tabela mostram o número de visitas, a taxa de conversão, o aumento médio e o nível de confiança e a confiança. Para obter mais informações, consulte [Cálculos estatísticos em testes A/B](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Exibição em gráfico

A ilustração a seguir mostra a aparência de um relatório de resumo típico em [!UICONTROL Exibição em gráfico] ao visualizar uma [!UICONTROL Direcionamento automático] relatório da atividade:

![Relatório de exibição de gráfico de direcionamento automático](/help/main/c-reports/assets/at-graph-view.png)

Como mostrado abaixo, você pode usar as duas listas suspensas para escolher as métricas desejadas, a metodologia de contagem e muito mais. Consulte [Visão geral das configurações de relatório](/help/main/c-reports/c-report-settings/report-settings.md) para obter mais informações:

![Relatório de exibição de gráfico de direcionamento automático](/help/main/c-reports/assets/at-graph-view-2.png)

## Segmentos automatizados

Clique no botão [!UICONTROL Segmentos automatizados] ícone . Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

![Ícone de segmentos automatizados](/help/main/c-reports/assets/icon-automated-sements.png)

Para obter mais informações, consulte [Relatório de Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Clique no botão [!UICONTROL Atributos importantes] ícone . Este relatório mostra como, em atividades diferentes, atributos diferentes são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

![Ícone de atributos importantes](/help/main/c-reports/assets/icon-important-attributes.png)

Para obter mais informações, consulte [Relatório de atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).
