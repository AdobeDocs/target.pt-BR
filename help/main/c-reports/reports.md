---
keywords: relatórios;bloquear endereço ip;bloquear visitante do endereço ip;baixar relatórios;relatórios;reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: Saiba como usar os recursos de relatórios no Adobe [!DNL Target] para examinar o desempenho de suas atividades. Tome decisões melhores com base em seus dados para aumentar o ROI.
title: Como visualizar relatórios?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: a7a03cba466fbe7abfc8eb1f80292e1a2de7fe2d
workflow-type: tm+mt
source-wordcount: '807'
ht-degree: 41%

---

# Relatórios

Os relatórios fornecem informações sobre o progresso e os resultados do [!DNL Adobe Target] atividades que ajudam você a tomar decisões baseadas em seus dados. Os dados dos relatórios podem ajudá-lo a decidir quando finalizar uma atividade, mostrar a experiência ou a oferta vencedora e fornecer os insights ou os aprendizados necessários para determinar as próximas ações.

## Exibir um relatório {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Clique em **[!UICONTROL Activities]** e depois clique na atividade desejada na lista.

   Se você tiver muitas atividades, pode filtrar a lista selecionando opções na [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], e [!UICONTROL Activity Source] listas suspensas.

   Por exemplo, você poderia selecionar [!UICONTROL A/B Test] e [!UICONTROL Experience Targeting] do [!UICONTROL Type] lista suspensa e [!UICONTROL Live] do [!UICONTROL Status] para exibir somente testes A/B e atividades de Direcionamento de experiência que estejam no estado ativo.

   A ilustração a seguir mostra o [!UICONTROL Type] lista suspensa com dois tipos selecionados: [!UICONTROL A/B Test] e [!UICONTROL Experience Targeting]. Observe que os três tipos de testes A/B (Manual, [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)e [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) são selecionados por padrão. Você pode desmarcar um ou mais tipos conforme necessário.

   ![Filtrar relatórios por tipo](/help/main/c-reports/assets/report_filters-new.png)

1. Clique em **[!UICONTROL Reports]** guia.

   Cada relatório inclui uma legenda para ajudá-lo a entender o relatório.

   ![Legenda do relatório](/help/main/c-reports/assets/report_menu_bar-new.png)

   A legenda exibe as seguintes informações:

   * O status da atividade, incluindo o intervalo de datas quando a atividade for executada.
   * A variável [experiência vencedora projetada](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (se disponível).

   >[!NOTE]
   >
   >Os resultados da experiência são exibidos depois de, ao menos, um participante ter visto a experiência.

1. (Opcional) [Configure o relatório](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) conforme desejado.
1. (Opcional) [Baixe o relatório no formato CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) para análise no Excel e em outras ferramentas.

   As opções disponíveis são as seguintes:

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Opcional) Clique no link **[!UICONTROL Table View]** e **[!UICONTROL Graph View]** para alternar entre os formatos de relatório.

   ![Ícones de exibição de Tabela e Gráfico](/help/main/c-reports/assets/table-and-graph-icons.png)

   Dependendo do tipo de relatório selecionado, outras exibições e relatórios podem estar disponíveis:

   | Tipo de relatório | Exibir |
   | --- | --- |
   | [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Clique em **[!UICONTROL Automated Segments]** ou **[!UICONTROL Important Attributes]** ícones.<ul><li>A variável [Relatório de Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.</li><li>A variável [Relatório de atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) mostra como, em atividades diferentes, atributos distintos são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.</li></ul> |
   | [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Além do [Relatórios de resumo do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md), você pode clicar no botão **[!UICONTROL Automated Segments]** ou **[!UICONTROL Important Attributes]** ícones.<ul><li>A variável [Relatório de Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.</li><li>A variável [Relatório de atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) mostra como, em atividades diferentes, atributos distintos são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.</li></ul> |
   | [Teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Além do [Relatório de desempenho da experiência](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), você pode clicar no botão [Contribuição de localização](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ícone para que o relatório mostre a contribuição por localização. |

## Informações adicionais sobre relatórios para tipos de atividades específicas {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Além das informações gerais de relatórios neste tópico e seus subtópicos, informações adicionais específicas para os tipos de atividades individuais em outro tópico nesse guia:

| Tipo de atividade | Detalhes |
|--- |--- |
| [Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) | Para compreender os aumentos e a confiança e as abordagens estatísticas usadas no [!DNL Target], consulte [Planejar um teste A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpretar relatórios de autoalocação](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interpretar os resultados de um [!UICONTROL Auto-Allocate] atividade A/B, examinando indicadores importantes, incluindo o aumento e a confiança, [!DNL Target] IU. |
| [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Informações sobre o [!UICONTROL Summary] relatório de atividades de AT. Para obter mais informações, consulte [Relatório de resumo do direcionamento automático](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Informações sobre os dois [!UICONTROL Personalization Insights] relatórios para atividades de AT e AP: [!UICONTROL Automated Segments] relatório e [!UICONTROL Important Attributes] relatório. Para obter mais informações, consulte [Relatórios de insights de personalização](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Personalização automatizada](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Informações sobre os dois [!UICONTROL Automated Personalization Summary] relatórios para atividades de AP: [!UICONTROL Activity Level] relatório e [!UICONTROL Offer Level] relatório. Para obter mais informações, consulte [Relatórios de resumo da personalização automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Informações sobre os dois [!UICONTROL Personalization Insights] relatórios para atividades de AT e AP: [!UICONTROL Automated Segments] relatório e [!UICONTROL Important Attributes] relatório. Para obter mais informações, consulte [Relatórios de insights de personalização](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Informações sobre os dois relatórios para atividades do MVT: [!UICONTROL Experience Performance] relatório e [!UICONTROL Location Contribution] relatório. Para obter mais informações, consulte [Relatório de desempenho da experiência](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) e [Relatório de contribuição da localização](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics como origem de relatório do Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informações sobre o uso do [!DNL Adobe Analytics] como a fonte de relatórios do [!DNL Target]. O A4T fornece acesso aos relatórios do [!DNL Analytics] para as atividades do [!DNL Target]. Para obter mais informações, consulte [Relatórios do Analytics para Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] relatórios no [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Informações sobre a integração entre [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} e [!DNL Target] que fornece ferramentas poderosas de análise e economia de tempo para o seu programa de otimização. |

## Bloquear dados de relatório de endereços IP especificados

Você pode bloquear a contagem de visitantes de endereços IP específicos nos relatórios. Isso é útil, por exemplo, para bloquear dados de relatórios de seus visitantes internos.

[Entre em contato com o Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar filtros IP. Essa filtragem não se aplica ao usar [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como sua fonte de geração de relatórios.
