---
keywords: analytics for target;a4t;analytics as the reporting source
description: Usar o Analytics como sua fonte de geração de relatórios para o Target (A4T) dá a você acesso aos relatórios do Analytics de suas atividades do Target.
title: Relatórios do A4T
feature: a4t reports
subtopic: Multivariate Test
topic: Standard
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 37%

---


# Relatórios do A4T{#a-t-reporting}

Using [!DNL Analytics] as your reporting source for [!DNL Target] (A4T) gives you access to [!DNL Analytics] reports for your [!DNL Target] activities.

You can view reports for your activities in both [!DNL Analytics] and [!DNL Target].

For reporting best practices using [!DNL Analytics] for [!DNL Target], [visit this Adobe Spark page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Visão geral {#section_035A62D65608423285D8A5A54731E2C5}

Both [!DNL Analytics] and [!DNL Target] reports measure entrants (the people who enter the tests), rather than visitors to the site.

Every time a visitor sees activity content on the page, [!DNL Target] makes a direct server-to-server call to [!DNL Analytics], including which activity and experience the visitor saw. [!DNL Target] também chama [!DNL Analytics] sempre que a conversão é feita. [!DNL Analytics] adiciona a conversão como um novo [!DNL Analytics] evento específico chamado &quot;Conversão de Atividade&quot;, que é rastreado junto com outros dados coletados por [!DNL Analytics].

When the [!UICONTROL Select] operation is used and you sort on *Entrants*, then only experiences that received entrants during the selected time period are displayed in the reports.

>[!NOTE]
>
>Reports powered by [!DNL Target] have a latency of four minutes. For activities powered by A4T, in both the [!DNL Target] and [!DNL Analytics] reports, it can take up to 24 hours after the activity is initially saved before the report data can be broken down by experiences. Os dados coletados nas primeiras 24 horas ainda são precisos e são atribuídos à experiência correta.

## Relatórios no Analytics  {#analytics}

Em [!DNL Analytics]geral, há várias dimensões e métricas disponibilizadas depois que a integração A4T é ativada.

### Dimensões

* [!UICONTROL Analytics for Público alvo] - a ID pai transmitida pela integração. O formato dessa dimensão é `Activity ID:Experience ID:3rd ID`. As dimensões abaixo são classificações dessa dimensão.
* [!UICONTROL Atividades do Target]
* [!UICONTROL Experiências target]
* [!UICONTROL Atividade] do público alvo > [!UICONTROL Experiência]
* [!UICONTROL 3ª ID] - pode ser ignorada

### Métricas

* [!UICONTROL Impressões] de atividade - Corresponde ao número de [!UICONTROL participantes] no [!DNL Target] relatório.
* [!UICONTROL Conversões] de atividade - Corresponde ao número de Conversões  personalizadas no [!DNL Target] relatório.

Em [!DNL Analysis Workspace], use o painel [!UICONTROL Analytics for Público alvo] para analisar suas [!DNL Target] atividades e experiências com incentivo e confiança. Para obter mais informações, consulte Painel [do](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics para Públicos alvos (A4T) no Guia *de ferramentas do* Analytics.

>[!IMPORTANT]
>
>If your [!UICONTROL Target Activities] report in [!DNL Analytics] lists &quot;unspecified&quot; instead of listing your activities, an update is required to your provisioned account. Entre em contato com o Atendimento ao cliente para resolver esse problema.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by Adobe Experience League.

## Relatórios no Target  {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] is used as the reporting source, reports in [!DNL Target] show the data gathered from [!DNL Analytics]. The report differs somewhat from other [!DNL Target] reports:

* The [!UICONTROL Audiences] list shows the audiences available to your [!DNL Analytics] report suite.
* The [!UICONTROL Metric] list shows every metric available through [!DNL Analytics].

   Todas as métricas estão disponíveis, incluindo as métricas personalizadas ou calculadas que estão integradas no [!DNL Analytics].

   Esteja ciente de que qualquer número que aumente é mostrado como positivos no relatório, mesmo quando um aumento for realmente indesejado. Por exemplo, mesmo que você queira uma taxa de rejeição mais baixa, a taxa de rejeição mais alta é mostrada como vencedora com o maior incentivo. Considere essas métricas de métricas semelhantes, bem como sua preferência por diminuir ou aumentar os números, ao tomar decisões baseadas nos relatórios.

You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the test has completed. Você não precisa saber exatamente o que deseja medir com antecedência.

Click to view the full [!DNL Analytics] report directly from the activity report page.

## Criação da atividade {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante a criação da atividade, você deve especificar uma meta para a atividade na página [!UICONTROL Configurações]. Esta meta torna-se a métrica padrão para o relatório e é sempre listada como a primeira opção no seletor de métricas. Não é possível selecionar os segmentos para os relatórios, como você faria para uma atividade padrão do Target. A test with [!DNL Analytics] uses [!DNL Adobe Analytics] segments rather than [!DNL Target] audiences.

## Performing offline calculations for Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics].

Para obter mais informações, consulte [Execução de cálculos offline no Analytics for Target (A4T)](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B) em.
