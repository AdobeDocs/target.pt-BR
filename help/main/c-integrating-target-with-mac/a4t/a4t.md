---
keywords: a4t;analytics;analytics for target;fonte de relatórios do analytics;adobe analytics como fonte derelatórios para o target;atjs;at.js;sdk da web da adobe experience platform;sdk da web da plataforma;sdk da plataforma
description: Use o  [!DNL Analytics]  for  [!DNL Target]  (A4T) para criar atividades baseadas em métricas de conversão e segmentos de público-alvo do  [!DNL Analytics]  e use relatórios do  [!DNL Analytics]  para examinar os resultados.
title: O que é  [!DNL Analytics]  for  [!DNL Target]  (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: f7bb9b5d6e96095a31f50f1976b87d9ee7b7eb51
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 80%

---

# [!DNL Adobe Analytics] como origem de relatório do [!DNL Adobe Target] (A4T)

O [!DNL Adobe Analytics for Target] (A4T) é uma integração entre soluções que permite criar atividades com base nas métricas de conversão e nos segmentos de público-alvo do [!DNL Analytics]. A integração A4T permite que você use os relatórios do [!DNL Analytics] para examinar os resultados. Se usar o [!DNL Analytics] como fonte de relatórios para uma atividade, todos os relatórios e segmentações dessa atividade serão baseados nos dados coletados pelo [!DNL Analytics].

## Visão geral {#section_92B66069210C40DBA937790E8CC596CF}

A integração [!DNL Analytics for Target] entre o [!DNL Analytics] e o [!DNL Target] fornece ferramentas poderosas de análise e economia de tempo para o seu programa de otimização.

Os três principais benefícios de usar dados do [!DNL Analytics] no [!DNL Target] são:

* Os profissionais de marketing podem aplicar dinamicamente as métricas de sucesso do ou os segmentos de relatórios do [!DNL Analytics] aos relatórios de atividades do [!DNL Target] a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Uma única fonte de dados elimina a variação que ocorre ao coletar dados em dois sistemas separados.
* A sua implementação do [!DNL Analytics] existente coleta todos os dados necessários. Não há necessidade de implementar as mboxes nas páginas com o único objetivo de coletar dados para os relatórios.

Se usar o [!DNL Analytics] como fonte de relatórios para uma atividade, todos os relatórios e segmentações dessa atividade serão baseados no [!DNL Analytics].

Todas as métricas [!DNL Analytics], inclusive métricas calculadas, estão disponíveis no [!DNL Target] e no relatório [!UICONTROL Target Activities] em [!DNL Analytics], com uma exceção. Não há suporte para as métricas calculadas para [!UICONTROL Lift & Confidence]. Da mesma forma, qualquer segmento disponível no [!DNL Analytics] pode ser aplicado a ambas as soluções. Você pode aplicar a métrica ou público-alvo ao relatório no [!DNL Target] após iniciar o teste ou mesmo após sua conclusão.

Todas as métricas estão incluídas, inclusive as métricas personalizadas ou calculadas que estão integradas no [!DNL Analytics].

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

Tenha os seguintes pontos em mente ao considerar o uso do A4T:

* Para usar o [!DNL Analytics] como a fonte de relatórios do [!DNL Target], você e sua empresa devem ter acesso ao [!DNL Analytics] e ao [!DNL Target]. [Entre em contato com o seu representante de conta,](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) caso precise de uma solução.
* A fonte de relatórios é definida para cada atividade. O [!DNL Target] continua a coletar dados para usar em relatórios, e os dados do [!DNL Target] ainda estão disponíveis caso você prefira basear uma atividade em dados coletados pelo [!DNL Target].
* Você deve usar uma fonte de relatórios ou outra. Você não pode coletar dados para uma única atividade de ambas as fontes.
* Ao usar o A4T, todas as métricas de sucesso disponíveis para suas atividades são métricas do [!DNL Analytics]. No entanto, sua métrica de meta pode ser baseada em uma chamada mbox se estiver usando at.js. Por exemplo, você pode usar os recursos de rastreamento de cliques integrados do Target com o A4T em vez de precisar implementar o código de rastreamento de cliques do [!DNL Analytics].
* Ao exibir relatórios de uma atividade do A4T na interface do usuário do [!DNL Target], você está visualizando dados do [!DNL Analytics]. Por exemplo, se você usar a métrica [!UICONTROL Visitor] em [!DNL Target], você está usando a métrica [!DNL Analytics] [!UICONTROL Visitor], não a métrica [!DNL Target] [!UICONTROL Visitors], que agora se chama [!UICONTROL Entrants]. Essa diferença é especialmente importante para as métricas básicas de tráfego ([!UICONTROL Visitors], [!UICONTROL Visits], [!UICONTROL Page Views]) e métricas de conversão.
* Quaisquer atividades do [!DNL Target] existentes continuam a usar a coleta de dados do [!DNL Target] e não são afetadas pela habilitação do A4T.
* Somente uma métrica baseada em mbox é permitida durante o uso do A4T.
* Uma chamada de servidor para servidor do [!DNL Target] para o [!DNL Analytics] envia informações de atividade e experiência para o [!DNL Analytics]. Esta integração não resulta em chamadas de servidor adicionais para o [!DNL Target] ou [!DNL Analytics].

  Em algumas situações, as classificações de [!DNL Target] para [!DNL Analytics] falha e as atividades não mostram dados no [!DNL Analytics]. Consulte [Solução de problemas na integração do Analytics e do Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Você também pode [entrar em contato com o Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obter mais assistência.

## Implementar o A4T

Para obter informações sobre a implementação do A4T com a at.js e o [!DNL Adobe Experience Platform Web SDK], consulte implamentação do [Analytics for  [!DNL Target] ](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Tipos de atividades aceitas {#section_F487896214BF4803AF78C552EF1669AA}

As seções a seguir contêm informações sobre os tipos de atividades compatíveis ao usar o [!DNL Adobe Experience Platform Web SDK] ou at.js:

| Tipos de atividades | O A4T é compatível? | Observações, se aplicável |
|--- |--- |--- |
| [Atividade A/B com divisão manual de tráfego](/help/main/c-activities/t-test-ab/test-ab.md) | Sim |  |
| [Atividade A/B com alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Sim | Consulte [Suporte do A4T para atividades de alocação automática e direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| [Atividade A/B com direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Sim | O suporte do A4T para atividades de Direcionamento automático agora é compatível com o [!DNL Platform Web SDK] e at.js. |
| [Direcionamento de experiência (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sim |  |
| [Teste multivariado (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sim | Exige métrica de meta baseada em mbox para obter o relatório [!UICONTROL Element Contribution]. No momento, o relatório [!UICONTROL Element Contribution] não oferece suporte a métricas [!DNL Analytics]. |
| [Atividade de Automated Personalization (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Não |  |
| [Atividade do Recommendations](/help/main/c-recommendations/recommendations.md) | Sim |  |
| [Qualquer atividade usando uma oferta de redirecionamento](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Sim |

Como todos os tipos de atividade ainda não aceitam o A4T, é recomendável que você mantenha ou implemente mboxes de conversão importantes, como a mbox `orderConfirmPage`.

## Exemplos de relatórios do A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Para exibir os relatórios do A4T em [!DNL Target], clique em **[!UICONTROL Activities]**, clique na atividade desejada da lista que usa [!DNL Analytics] como fonte de geração de relatórios e, em seguida, clique na guia **[!UICONTROL Reports]**.

>[!NOTE]
>
>Você pode usar a lista suspensa [!UICONTROL Reporting Source] na parte superior da página [!UICONTROL Activities] para exibir somente as atividades que usam o A4T.

Você pode alternar entre [!UICONTROL Table View] e [!UICONTROL Graph View] do relatório clicando no ícone apropriado na parte superior direita do relatório.

A ilustração a seguir mostra o [!UICONTROL Graph View] de um relatório do A4T com a lista suspensa [!UICONTROL Report Metric] exibindo as métricas de meta [!DNL Analytics] disponíveis:

![imagem a4t_report_graph1](assets/a4t_report_graph1.png)

A ilustração a seguir mostra o [!UICONTROL Graph View] de um relatório do A4T com a lista suspensa [!UICONTROL Audience] exibindo os públicos-alvo [!DNL Analytics] disponíveis:

![imagem a4t_report_graph2](assets/a4t_report_graph2.png)

A ilustração a seguir mostra o [!UICONTROL Table View] de um relatório do A4T:

![imagem a4t_report_table](assets/a4t_report_table.png)

Para exibir o relatório em [!DNL Analytics] em vez de em [!DNL Target], clique em **[!UICONTROL View in Analytics]** na parte superior do relatório.

## Tutorial do Analytics &amp; Target: práticas recomendadas para análise {#section_3438E6E77A464424B717A4FD333B84B2}

Abra o tutorial do [Analytics &amp; Target: práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido pela [!DNL Adobe Experience League].

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste tópico.

### Analytics for Adobe Target (A4T) (4:32) ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo explica como usar o [!DNL Analytics] como fonte de relatórios no [!DNL Target] para orientar a análise do seu programa de otimização.

* Explique o que é o A4T e porque você o usaria
* Explique como o A4T funciona
* Entenda os pré-requisitos necessários antes de utilizar o A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Integração do Analytics/Adobe Target (A4T) (40:33) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo é uma gravação de &quot;[Horas do Office](/help/main/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)&quot;, uma iniciativa liderada pela equipe de Atendimento ao cliente da Adobe.

* Como configurar e validar o funcionamento da integração
* Como funciona a integração
* Saiba mais sobre os relatórios adequados para usar no Analytics
* Respostas às perguntas comuns sobre o A4T

[Office Hours da integração do Analytics/Target (A4T)](https://helpx.adobe.com/br/customer-care-office-hours/target/analytics-target-A4T-integration.html)

>[!MORELIKETHIS]
>
>* Implementação do [Analytics for  [!DNL Target] ](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md): contém informações de implementação da at.js e do SDK da Web da plataforma.
>* [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [O que é o SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR): contém informações de visão geral sobre o SDK da Web da plataforma.
>* [Visão geral do Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html?lang=pt-BR): contém informações específicas do [!DNL Target] e [!DNL Platform Web SDK].
