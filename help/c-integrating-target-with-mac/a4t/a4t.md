---
keywords: a4t;analytics;analytics for target;analytics reporting source;adobe analytics as the reporting source for target
description: O "Analytics for Target" (A4T) da Adobe é uma integração entre soluções que permite criar atividades com base nas métricas de conversão e nos segmentos de público-alvo do Analytics. Essa integração permite usar os relatórios do Analytics para analisar seus resultados. Se usar o Analytics como fonte de relatórios para uma atividade, todos os relatórios e segmentações dessa atividade serão baseados nos dados coletados pelo Analytics.
title: Adobe Analytics como origem de relatório do Adobe Target (A4T)
feature: a4t general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1269'
ht-degree: 47%

---


# Adobe Analytics como origem de relatório do Adobe Target (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

[!DNL Adobe Analytics for Target] (A4T) é uma integração entre soluções que permite criar atividades com base em métricas de [!DNL Analytics] conversão e segmentos de audiência. The A4T integration lets you use [!DNL Analytics] reports to examine your results. If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics] data collection.

## Visão geral do A4T {#section_92B66069210C40DBA937790E8CC596CF}

The [!DNL Analytics for Target] integration between [!DNL Analytics] and [!DNL Target] provides powerful analysis and timesaving tools for your optimization program.

The three primary benefits of using [!DNL Analytics] data in [!DNL Target] are:

* Marketers can dynamically apply [!DNL Analytics] success metrics or reporting segments to [!DNL Target] activity reports at any time. Não há necessidade de especificar tudo antes de executar a atividade.
* Uma única fonte de dados elimina a variação que ocorre ao coletar dados em dois sistemas separados.
* Your existing [!DNL Analytics] implementation collects all required data. Não há necessidade de implementar as mboxes nas páginas com o único objetivo de coletar dados para os relatórios. Although, it is still recommended that you implement an order confirmation mbox for [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) activities.

>[!IMPORTANT]
>
>Antes de começar a usar A4T, você precisa solicitar que sua conta seja provisionada para a integração. Use [este formulário](https://www.adobe.com/go/audiences) para solicitar o aprovisionamento.
>
>The integration that enables [!DNL Analytics] as the data source for [!DNL Target] (A4T) represents the next generation of the Test&amp;Target to SiteCatalyst plug-in. Este plug-in foi descontinuado, mas ainda é suportado para os clientes que já o utilizam.

If you use [!DNL Analytics] as the reporting source for an activity, all reporting and segmentation for that activity is based on [!DNL Analytics].

All [!DNL Analytics] metrics, including calculated metrics, are available in [!DNL Target] and the [!UICONTROL Target Activities] report in [!DNL Analytics]. Likewise, any segment available in [!DNL Analytics] can be applied to both solutions. You can apply the metric or audience to the report in [!DNL Target] after the activity has started, or even after the activity has completed.

Todas as métricas estão incluídas, incluindo as métricas personalizadas ou calculadas que estão integradas no [!DNL Analytics].

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

Tenha os seguintes pontos em mente ao considerar o uso do A4T:

* To use [!DNL Analytics] as the reporting source for [!DNL Target], both you and your company must have access to [!DNL Analytics] and to [!DNL Target]. [Entre em contato com o seu representante de conta,](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) caso precise de uma solução.
* A fonte de relatórios é definida para cada atividade. [!DNL Target] continua a coletar dados para uso no relatórios e [!DNL Target] os dados ainda estarão disponíveis se você preferir basear uma atividade em dados coletados pelo [!DNL Target].
* Você deve usar uma fonte de relatórios ou outra. Você não pode coletar dados para uma única atividade de ambas as fontes.
* When using A4T, all success metrics available to your activities are [!DNL Analytics] metrics. No entanto, sua métrica de meta pode ser baseada em uma chamada mbox. For example, you can use Target&#39;s out-of-the-box click-tracking capabilities with A4T instead of having to implement [!DNL Analytics] click-tracking code.
* When viewing reporting of an A4T activity in the [!DNL Target] UI, you are viewing [!DNL Analytics] data. For example, if you use the [!UICONTROL Visitor] metric in [!DNL Target], you are using the [!DNL Analytics] [!UICONTROL Visitor] metric, not the [!DNL Target] [!UICONTROL Visitors] metric, which is now called [!UICONTROL Entrants]. This difference is especially important for basic traffic metrics ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) and conversion metrics.
* Any existing [!DNL Target] activities continue to use [!DNL Target] data collection and are not affected by enabling A4T.
* Only one mbox-based metric is allowed when using [!DNL Analytics] as the reporting source.
* A server-to-server call from [!DNL Target] to [!DNL Analytics] sends activity and experience information to [!DNL Analytics]. This integration does not result in additional server calls for either [!DNL Target] or [!DNL Analytics].

   Em algumas situações, a chamada de classificação de [!DNL Target] para [!DNL Analytics] pode falhar e as atividades não exibem dados em [!DNL Analytics]. Se isso acontecer, consulte [Solução de problemas do Analytics e da integração de Públicos alvos (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Você também pode [entrar em contato com o Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obter assistência adicional.

## Supported activity types {#section_F487896214BF4803AF78C552EF1669AA}

The following table shows you which activity types support [!DNL Analytics] as the reporting source in [!DNL Target] (A4T):

| Tipos de atividades | O A4T é compatível? | Observações, se aplicável |
|--- |--- |--- |
| Atividade A/B com divisão manual de tráfego | Sim |  |
| Atividade A/B com alocação automática | Sim | Consulte Suporte [do Analytics para Públicos alvos (A4T) para Autoalocar e Público alvo automático de atividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa). |
| Atividade A/B com direcionamento automático | Sim | Consulte Suporte [do Analytics para Públicos alvos (A4T) para Autoalocar e Público alvo automático de atividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa). |
| Direcionamento de experiência (XT) | Sim |  |
| Teste multivariado (MVT) | Sim | Requires mbox-based goal metric goal to get the [!UICONTROL Element Contribution] report.  The [!UICONTROL Element Contribution] report does not currently support [!DNL Analytics] metrics. |
| Atividade de personalização automatizada (AP) | Não |  |
| Atividade do Recommendations | Sim |  |
| Aplicativo móvel | Sim | Compatível com o Mobile Services SDK, versão 4.13.1 ou superior.  Para obter mais informações, consulte a [documentação do Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html). |
| Email | Não |  |
| API de entrega do lado do servidor | Sim | Para obter mais informações, consulte o [Servidor: implementar o Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK do NodeJS | Sim | Para obter mais informações, consulte o [Servidor: implementar o Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| AEM 6.1 (ou anterior) Integração dos Serviços em Nuvem | Não |  |
| AEM 6.2 (ou posterior) Integração dos Serviços em Nuvem | Sim | For more information, see [Integrating with Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) in the [!DNL Adobe Experience Manager] 6.2 documentation. |
| Qualquer atividade usando uma oferta de redirecionamento | Sim | Existem requisitos mínimos mais rigorosos para o uso de Ofertas de redirecionamento com o A4T. Para obter mais informações, consulte [Ofertas de redirecionamento - Perguntas frequentes do A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Sim |  |

Because all activity types do not yet support A4T, it is recommended that you keep or implement important conversion mboxes, such as the `orderConfirmPage` mbox.

## Examples of A4T reports {#section_F0A43A1CB2F04E8282B909E4D7034361}

To view A4T reports in [!DNL Target], click **[!UICONTROL Activities]**, click the desired activity from the list that uses [!DNL Analytics] as its reporting source, then click the **[!UICONTROL Reports]** tab.

>[!NOTE]
>
>Você pode usar a lista suspensa [!UICONTROL Fonte de relatórios] na parte superior da página [!UICONTROL Atividades] para exibir somente as atividades que usam [!DNL Analytics] como fonte de relatórios.

You can toggle between the [!UICONTROL Table View] and [!UICONTROL Graph View] of the report by clicking the appropriate icon at the top right side of the report.

A ilustração a seguir mostra a [!UICONTROL Visualização de gráfico] de um relatório do A4T com a lista suspensa de [!UICONTROL Métrica de relatórios] exibindo as métricas de meta disponíveis do [!DNL Analytics]:

![](assets/a4t_report_graph1.png)

A ilustração a seguir mostra a [!UICONTROL Visualização de gráfico] de um relatório do A4T com a lista suspensa de [!UICONTROL Público-alvo] exibindo os públicos-alvo disponíveis do [!DNL Analytics]:

![](assets/a4t_report_graph2.png)

A ilustração a seguir mostra a [!UICONTROL Visualização de tabela] de um relatório do A4T:

![](assets/a4t_report_table.png)

Para exibir o relatório no [!DNL Analytics] em vez de no [!DNL Target], clique em **[!UICONTROL Exibir no Analytics]** na parte superior do relatório.

## Tutorial do Analytics &amp; Target: práticas recomendadas para análise {#section_3438E6E77A464424B717A4FD333B84B2}

Open the [Analytics &amp; Target: Best Practices for Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, provided by [!DNL Adobe Experience League].

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste tópico.

### Etiqueta de ![visão geral do Analytics para Públicos alvos (A4T) (4:32)](/help/assets/overview.png)

This video explains how to use [!DNL Analytics] as a reporting source in [!DNL Target] to drive the analysis of your optimization program.

* Explique o que é o A4T e porque você o usaria
* Explique como o A4T funciona
* Entenda os pré-requisitos necessários antes de utilizar o A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Analytics / Integração de Públicos alvos (A4T) (40:33) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo é uma gravação de &quot;[Horas do Office](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)&quot;, uma iniciativa liderada pela equipe de Atendimento ao cliente da Adobe.

* Como configurar e validar o funcionamento da integração
* Como funciona a integração
* Saiba mais sobre os relatórios adequados para usar no Analytics
* Respostas às perguntas comuns sobre o A4T

[Horas do Office para Integração de Públicos alvos/Análises (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)