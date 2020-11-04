---
keywords: reports;block ip address;block visitor from ip address;download reports;csv;reporting
description: Os relatórios fornecem informações sobre o desempenho de suas atividades Adobe Target
title: Relatórios
feature: reports
topic: Standard
uuid: 8d20f4e7-72fd-4872-a21f-54ce16a2d2ab
translation-type: tm+mt
source-git-commit: e18f18e6d6e0b8fc6eb5ada845e2fe5377d6c5d0
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 66%

---


# Relatórios{#reports}

Reports provide information about the progress and results of your [!DNL Adobe Target] activities that help you make decisions based on your data. Os dados do relatório podem ajudá-lo a decidir quando encerrar uma atividade, mostrar qual experiência de oferta é a vencedora e fornecer insights ou aprendizados necessários para determinar as próximas ações.

## Exibir um relatório {#section_C4591A32F6D04C95A1AD5A377C27C28B}

1. Clique em **[!UICONTROL Atividades]** e depois clique na atividade desejada na lista.

   Se você tem muitas atividades, você pode filtrar a lista selecionando opções nas listas suspensas [!UICONTROL Tipo], [!UICONTROL Status], [!UICONTROL Fonte de geração de relatórios], [!UICONTROL Experience Composer], [!UICONTROL Tipo de métrica] e [!UICONTROL Fonte da atividade].

   Por exemplo, você poderia selecionar [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] na lista suspensa [!UICONTROL Tipo] e [!UICONTROL Ao vivo] na lista suspensa de [!UICONTROL Status] para exibir somente os testes A/B e as atividades de Direcionamento de experiência que estão em um estado ativo.

   A ilustração a seguir mostra a lista suspensa [!UICONTROL Tipo] com dois tipos selecionados:  [!UICONTROL A/B Test] and [!UICONTROL Experience Targeting]. Observe que os três tipos de testes A/B (Manual, [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)e [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md)) são selecionados por padrão. Você pode desmarcar um ou mais tipos conforme necessário.

   ![Filtrar relatórios por tipo](/help/c-reports/assets/report_filters-new.png)

1. Clique na guia **[!UICONTROL Relatórios]**.

   Cada relatório inclui uma legenda para ajudá-lo a entender o relatório.

   ![Legenda do relatório](/help/c-reports/assets/report_menu_bar-new.png)

   A legenda exibe as seguintes informações:

   * O status da atividade, incluindo o intervalo de datas quando a atividade for executada.
   * The [projected winning experience](/help/c-activities/automated-traffic-allocation/determine-winner.md) (if available).

   >[!NOTE]
   >
   >Os resultados da experiência são exibidos depois de, ao menos, um participante ter visto a experiência.

1. (Opcional) [Configure o relatório](../c-reports/c-report-settings/report-settings.md#concept_4BB6A7FDAB6F4806A632F9CD989B8BFA) conforme desejado.
1. (Opcional) [Baixe o relatório no formato CSV](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) para análise no Excel e em outras ferramentas.

   As opções disponíveis são as seguintes:

   * [!UICONTROL Exportar relatório para CSV]
   * [!UICONTROL Exportar detalhes do pedido para CSV]

1. (Opcional) Clique nos ícones de **[!UICONTROL Exibição em tabela]** e **[!UICONTROL Exibição em gráfico]** para trocar entre os formatos de relatório.

   ![Ícones de visualização de tabela e gráfico](/help/c-reports/assets/table-and-graph-icons.png)

   Dependendo do tipo de relatório selecionado, outras visualizações e relatórios podem estar disponíveis:

   | Tipo de relatório | Exibir |
   | --- | --- |
   | [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) | Clique nos ícones Segmentos **** automatizados ou Atributos **** importantes.<ul><li>The [Automated Segments report](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) shows how different visitors respond differently to the offers/experiences in your AP/AT activity. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) shows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.</li></ul> |
   | [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Além dos relatórios [Resumo da](/help/c-reports/reports-ap.md)Automated Personalization, você pode clicar nos ícones Segmentos **** automatizados ou Atributos **** importantes.<ul><li>The [Automated Segments report](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md) shows how different visitors respond differently to the offers/experiences in your AP/AT activity. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.</li><li>The [Important Attributes report](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md) hows how, in different activities, different attributes are more (or less) important to how the model decides to personalize. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.</li></ul> |
   | [Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Além do relatório [Desempenho da](/help/c-reports/experience-performance-report.md)experiência, você pode clicar no ícone Contribuição [da](/help/c-reports/location-contribution-report.md) localização para alternar o relatório para mostrar a contribuição por localização. |

## Additional reporting information for specific activity types {#section_DFE037B9E1C345D3B3BDFCB3AC0359CA}

Além das informações gerais de relatórios neste tópico e seus subtópicos, informações adicionais específicas para os tipos de atividades individuais em outro tópico nesse guia:

| Tipo de atividade | Detalhes |
|--- |--- |
| [Teste A/B](/help/c-activities/t-test-ab/test-ab.md) | Para compreender os aumentos e a confiança e as abordagens estatísticas usadas no [!DNL Target], consulte [Planejar um teste A/B](/help/c-activities/t-test-ab/sample-size-determination.md). |
| [Interpretar relatórios de autoalocação](/help/c-activities/automated-traffic-allocation/determine-winner.md) | Interprete os resultados de uma atividade A/B de [!UICONTROL Autoalocação] examinando indicadores importantes, incluindo incentivo e confiança, na [!DNL Target] interface do usuário. |
| [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT) | Informações sobre o relatório de [!UICONTROL Resumo ]das atividades de AT. Para obter mais informações, consulte [Relatório de resumo do direcionamento automático](/help/c-reports/auto-target-summary-report.md).<br>Informações sobre os dois relatórios de [!UICONTROL Insights de personalização] das atividades de AT e AP: relatório de [!UICONTROL Segmentos automatizados] e relatório de [!UICONTROL Atributos importantes]. Para obter mais informações, consulte [Relatórios de insights de personalização](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) | Informações sobre os dois relatórios de [!UICONTROL Resumo da personalização automatizada] das atividades de AP: relatório de [!UICONTROL Nível de atividade] e relatório de [!UICONTROL Nível de oferta]. Para obter mais informações, consulte [Relatórios de resumo da personalização automatizada](/help/c-reports/reports-ap.md).<br>Informações sobre os dois relatórios de [!UICONTROL Insights de personalização] das atividades de AT e AP: relatório de [!UICONTROL Segmentos automatizados] e relatório de [!UICONTROL Atributos importantes]. Para obter mais informações, consulte [Relatórios de insights de personalização](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md). |
| [Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md) (MVT) | Informações sobre os dois relatórios para atividades do MVT: relatório de [!UICONTROL desempenho da experiência] e relatório de [!UICONTROL contribuição de localização]. Para obter mais informações, consulte [Relatório de desempenho da experiência](/help/c-reports/experience-performance-report.md) (MVT) e [Relatório de contribuição da localização](/help/c-reports/location-contribution-report.md) (MVT). |
| [Adobe Analytics como origem de relatório do Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) | Informações sobre o uso do [!DNL Adobe Analytics] como a fonte de relatórios do [!DNL Target]. O A4T fornece acesso aos relatórios do [!DNL Analytics] para as atividades do [!DNL Target]. Para obter mais informações, consulte [Relatórios do Analytics para Target (A4T)](/help/c-reports/analytics-for-target-a4t-reporting.md). |

## Bloquear dados do relatórios de endereços IP especificados

Você pode bloquear a contagem de visitantes de endereços IP específicos nos relatórios. Isso é útil, por exemplo, para bloquear dados de relatórios de seus visitantes internos.

[Entre em contato com o Client Care para configurar filtros IP. ](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) Essa filtragem não se aplica ao usar  [Analytics for Target](../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE) (A4T) como a sua fonte de geração de relatório.
