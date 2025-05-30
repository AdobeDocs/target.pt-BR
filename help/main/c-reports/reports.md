---
keywords: relatórios;bloquear endereço ip;bloquear visitante do endereço ip;baixar relatórios;relatórios;reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: Otimize suas atividades dominando os recursos de relatórios do  [!DNL Adobe Target] para aprimorar a tomada de decisões e aumentar o ROI.
title: Como visualizar relatórios?
feature: Reports
exl-id: c5710eb3-0c72-47f8-870d-df50453ecf08
source-git-commit: bd65cb9339dbe4b79d26c314cfb81d1fc7226fd2
workflow-type: tm+mt
source-wordcount: '814'
ht-degree: 26%

---

# Relatórios

Os relatórios fornecem informações sobre o progresso e os resultados das atividades do [!DNL Adobe Target] que ajudam a tomar decisões baseadas em dados. Os dados dos relatórios podem ajudá-lo a decidir quando finalizar uma atividade, mostrar a experiência ou a oferta vencedora e fornecer os insights ou os aprendizados necessários para determinar as próximas ações.

## Exibir um relatório {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Clique em **[!UICONTROL Activities]** e depois clique na atividade desejada na lista.

   Se você tiver muitas atividades, clique no ícone Filtrar ( ![Ícone Filtrar](/help/main/assets/icons/Filter.svg) ) para filtrar a lista selecionando opções nas listas [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], [!UICONTROL Decisioning Method] e [!UICONTROL Activity Source].

   Por exemplo, você poderia selecionar [!UICONTROL A/B Test] e [!UICONTROL Experience Targeting] na lista suspensa [!UICONTROL Type] e [!UICONTROL Live] na lista suspensa [!UICONTROL Status] para exibir somente as atividades [!UICONTROL A/B Test] e [!UICONTROL Experience Targeting] que estão em estado ativo.

   A ilustração a seguir mostra a lista suspensa [!UICONTROL Type] com dois tipos selecionados: [!UICONTROL A/B Test] e [!UICONTROL Experience Targeting]. Observe que os três tipos de testes A/B (Manual, [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)e [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)) são selecionados por padrão. Você pode desmarcar um ou mais tipos conforme necessário.

   ![Filtrar relatórios por tipo](/help/main/c-reports/assets/report-filters-refresh.png)

1. Clique na atividade desejada da lista para exibir sua página [!UICONTROL Overview].

1. Clique na guia **[!UICONTROL Reports]** no painel esquerdo.

   ![Relatório A/B](/help/main/c-reports/assets/reports-refresh.png)

   Cada relatório inclui uma legenda para ajudá-lo a entender o relatório.

   A legenda exibe as seguintes informações:

   * O status da atividade, incluindo o intervalo de datas quando a atividade for executada.
   * A [experiência vencedora projetada](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) (se disponível).

   >[!NOTE]
   >
   >Os resultados da experiência são exibidos depois de, ao menos, um participante ter visto a experiência.

1. (Opcional) [Configure o relatório](/help/main/c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) clicando no ícone Configurações de Relatório ( ![ícone Configurações de Relatório](/help/main/assets/icons/Setting.svg) ).
1. (Opcional) Clique no ícone Baixar relatórios ( ![ícone Baixar relatórios](/help/main/assets/icons/Download.svg) ) para [baixar o relatório no formato CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) para análise no Excel e em outras ferramentas.

   As opções disponíveis são as seguintes:

   * [!UICONTROL Export Report to CSV]
   * [!UICONTROL Export Order Details to CSV]

1. (Opcional) Clique nos ícones **[!UICONTROL Table View]** ( ![Exibição em tabela](/help/main/assets/icons/Table.svg) ) e **[!UICONTROL Graph View]** ( ![Exibição em gráfico](/help/main/assets/icons/GraphTrend.svg) ) para alternar entre os formatos de relatório.

   Dependendo do tipo de relatório selecionado, outras exibições e relatórios podem estar disponíveis:

   | Tipo de relatório | Exibir |
   | --- | --- |
   | [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Clique nos ícones **[!UICONTROL Automated Segments]** ( ![Relatório de segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) ou **[!UICONTROL Important Attributes]** ( ![Ícone de atributos importantes](/help/main/assets/icons/ViewList.svg) ).<ul><li>O [[!UICONTROL Automated Segments] relatório](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) mostra como visitantes diferentes respondem de forma diferente às ofertas e experiências na sua atividade [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target]. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização [!DNL Target], responderam às ofertas e experiências na atividade.</li><li>O [[!UICONTROL Important Attributes] relatório](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) mostra como, em atividades diferentes, atributos distintos são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.</li></ul> |
   | [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Além dos [[!UICONTROL Automated Personalization Summary] relatórios](/help/main/c-reports/personalization-reports/reports-ap.md), você pode clicar nos ícones **[!UICONTROL Automated Segments]** ( ![Relatório de Segmentos Automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) ou **[!UICONTROL Important Attributes]** ( ![Ícone de Atributos Importantes](/help/main/assets/icons/ViewList.svg) ).<ul><li>O [[!UICONTROL Automated Segments] relatório](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md) mostra como visitantes diferentes respondem de forma diferente às ofertas e experiências na sua atividade [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Target]. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização [!DNL Target], responderam às ofertas e experiências na atividade.</li><li>O [[!UICONTROL Important Attributes] relatório](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md) mostra como, em atividades diferentes, atributos distintos são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.</li></ul> |
   | [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Além do relatório [[!UICONTROL Experience Performance]](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), você pode clicar no ícone [[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ( ![Contribuição de localização](/help/main/assets/icons/LocationContribution.svg) ) para que o relatório mostre a contribuição por localização. |

## Informações adicionais sobre relatórios para tipos de atividades específicas {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Além das informações gerais de relatórios neste tópico e seus subtópicos, informações adicionais específicas para os tipos de atividades individuais em outro tópico nesse guia:

| Tipo de atividade | Detalhes |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | Para compreender os aumentos e a confiança e as abordagens estatísticas usadas no [!DNL Target], consulte [Planejar um teste A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpretar [!UICONTROL Auto-Allocate] relatórios](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) | Interprete os resultados de uma atividade A/B [!UICONTROL Auto-Allocate] examinando indicadores importantes, incluindo aumento e confiança, na interface do usuário do [!DNL Target]. |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (ÀS) | Informações sobre o relatório [!UICONTROL Summary] de atividades de AT. Para obter mais informações, consulte [[!UICONTROL Auto-Target Summary] Relatório](/help/main/c-reports/personalization-reports/auto-target-summary-report.md).<br>Informações sobre os dois relatórios [!UICONTROL Personalization Insights] das atividades de AT e AP: relatório [!UICONTROL Automated Segments] e relatório [!UICONTROL Important Attributes]. Para obter mais informações, consulte [Relatórios de insights de personalização](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Informações sobre os dois relatórios [!UICONTROL Automated Personalization Summary] para atividades de AP: relatório [!UICONTROL Activity Level] e relatório [!UICONTROL Offer Level]. Para obter mais informações, consulte [Relatórios de resumo da personalização automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).<br>Informações sobre os dois relatórios [!UICONTROL Personalization Insights] das atividades de AT e AP: relatório [!UICONTROL Automated Segments] e relatório [!UICONTROL Important Attributes]. Para obter mais informações, consulte [Relatórios de insights de personalização](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Informações sobre os dois relatórios para atividades MVT: relatório de [!UICONTROL Experience Performance] e relatório de [!UICONTROL Location Contribution]. Para obter mais informações, consulte [Relatório de desempenho da experiência](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md) (MVT) e [Relatório de contribuição da localização](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) (MVT). |
| [[!DNL Adobe Analytics] como Source de relatórios para Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informações sobre o uso de [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Target] (A4T). O A4T fornece acesso aos relatórios do [!DNL Analytics] para as atividades do [!DNL Target]. Para obter mais informações, consulte [Relatórios do Analytics para Target (A4T)](/help/main/c-reports/analytics-for-target-a4t-reporting.md). |
| [[!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) | Informações sobre a integração entre o [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/pt-br/docs/customer-journey-analytics){target=_blank} e o [!DNL Target] que fornece ferramentas poderosas de análise e economia de tempo para o seu programa de otimização. |

## Bloquear dados de relatório de endereços IP especificados

Você pode bloquear a contagem de visitantes de endereços IP específicos nos relatórios. Essa opção é útil, por exemplo, para bloquear dados de relatórios de seus visitantes internos.

[Contate o Atendimento ao Cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) para configurar filtros IP. Esta filtragem não se aplica ao usar o [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como sua fonte de geração de relatórios.
