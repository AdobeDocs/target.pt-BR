---
keywords: a4t; analytics; analytics para target; fonte de relatórios do analytics; adobe analytics como fonte de relatórios para target; atjs; at.js; adobe experience platform web sdk; platform web sdk; platform sdk
description: Use [!DNL Analytics] para [!DNL Target] (A4T) para criar atividades baseadas em [!DNL Analytics] métricas de conversão e segmentos de público-alvo e use [!DNL Analytics] relatórios para examinar os resultados.
title: O que é [!DNL Analytics] para [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: 5bb80b03-8209-4932-a838-0e11c5865133
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1125'
ht-degree: 30%

---

# [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T)

[!DNL Adobe Analytics for Target] (A4T) é uma integração entre soluções que permite criar atividades com base em [!DNL Analytics] métricas de conversão e segmentos de público-alvo. A integração A4T permite usar [!DNL Analytics] relatórios para examinar seus resultados. Se você usar [!DNL Analytics] como fonte de relatórios para uma atividade, todos os relatórios e segmentações dessa atividade são baseados em [!DNL Analytics] coleta de dados.

## Visão geral {#section_92B66069210C40DBA937790E8CC596CF}

O [!DNL Analytics for Target] integração entre [!DNL Analytics] e [!DNL Target] O fornece ferramentas eficientes de análise e economia de tempo para seu programa de otimização.

Os três principais benefícios do uso [!DNL Analytics] em [!DNL Target] são:

* Os profissionais de marketing podem aplicar dinamicamente [!DNL Analytics] métricas de sucesso ou segmentos de relatórios para [!DNL Target] relatórios de atividade a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Uma única fonte de dados elimina a variação que ocorre ao coletar dados em dois sistemas separados.
* Seu existente [!DNL Analytics] A implementação coleta todos os dados necessários. Não há necessidade de implementar as mboxes nas páginas com o único objetivo de coletar dados para os relatórios.

Se você usar [!DNL Analytics] como fonte de relatórios para uma atividade, todos os relatórios e segmentações dessa atividade são baseados em [!DNL Analytics].

Todos [!DNL Analytics] métricas, incluindo métricas calculadas, estão disponíveis em [!DNL Target] e [!UICONTROL Atividades do Target] relatório em [!DNL Analytics], com uma exceção. As métricas calculadas para [!UICONTROL Lift e Confidence] não são compatíveis. Da mesma forma, qualquer segmento disponível no [!DNL Analytics] podem ser aplicadas a ambas as soluções. Você pode aplicar a métrica ou o público-alvo ao relatório em [!DNL Target] após o início da atividade ou mesmo após a conclusão da atividade.

Cada métrica é incluída, incluindo qualquer métrica personalizada ou calculada que esteja incorporada [!DNL Analytics].

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

Tenha os seguintes pontos em mente ao considerar o uso do A4T:

* Para usar [!DNL Analytics] como fonte de relatórios para [!DNL Target], você e sua empresa devem ter acesso ao [!DNL Analytics] e [!DNL Target]. [Entre em contato com o seu representante de conta,](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) caso precise de uma solução.
* A fonte de relatórios é definida para cada atividade. [!DNL Target] A continua coletando dados para usar em relatórios e [!DNL Target] os dados ainda estarão disponíveis se você preferir basear uma atividade em dados coletados por [!DNL Target].
* Use uma fonte de relatórios ou a outra. Você não pode coletar dados para uma única atividade de ambas as fontes.
* Ao usar o A4T, todas as métricas de sucesso disponíveis para suas atividades são [!DNL Analytics] métricas. No entanto, sua métrica de meta pode ser baseada em uma chamada de mbox se estiver usando a at.js. Por exemplo, você pode usar os recursos de rastreamento de cliques predefinidos do Target com o A4T em vez de precisar implementar [!DNL Analytics] código de rastreamento de cliques.
* Ao exibir relatórios de uma atividade A4T no [!DNL Target] Interface do usuário, você está visualizando [!DNL Analytics] dados. Por exemplo, se você usar a variável [!UICONTROL Visitante] em [!DNL Target], você está usando o [!DNL Analytics] [!UICONTROL Visitante] , não a [!DNL Target] [!UICONTROL Visitantes] métrica, que agora é chamada de [!UICONTROL Participantes]. Essa diferença é especialmente importante para as métricas básicas de tráfego ([!UICONTROL Visitantes], [!UICONTROL Visitas], [!UICONTROL Exibições de página]) e métricas de conversão.
* Qualquer [!DNL Target] as atividades continuam a usar [!DNL Target] coleta de dados e não são afetados pela ativação do A4T.
* Somente uma métrica baseada em mbox é permitida durante o uso do A4T.
* Uma chamada de servidor para servidor de [!DNL Target] para [!DNL Analytics] envia informações de atividade e experiência para o [!DNL Analytics]. Essa integração não resulta em chamadas de servidor extras para [!DNL Target] ou [!DNL Analytics].

   Em algumas situações, as classificações de [!DNL Target] para [!DNL Analytics] falha e as atividades não mostram dados em [!DNL Analytics]. Consulte [Solução de problemas na integração do Analytics e do Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Você também pode [entre em contato com o Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obter mais assistência.

## Implementar o A4T

Para obter informações sobre a implementação do A4T com a at.js e o [!DNL Adobe Experience Platform Web SDK], consulte [Analytics para [!DNL Target] implementação](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md).

## Tipos de atividades suportadas {#section_F487896214BF4803AF78C552EF1669AA}

As seções a seguir contêm informações sobre os tipos de atividades compatíveis ao usar o [!DNL Adobe Experience Platform Web SDK] ou at.js:

| Tipos de atividades | O A4T é compatível? | Observações, se aplicável |
|--- |--- |--- |
| [Atividade A/B com divisão manual de tráfego](/help/main/c-activities/t-test-ab/test-ab.md) | Sim |  |
| [Atividade A/B com alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Sim | Consulte [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) |
| [Atividade A/B com direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Sim | Consulte [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md). |
| [Direcionamento de experiência (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sim |  |
| [Teste multivariado (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sim | Requer métrica de meta baseada em mbox para obter o [!UICONTROL Contribuição de elemento] relatório. O [!UICONTROL Contribuição de elemento] no momento, o relatório não é compatível [!DNL Analytics] métricas. |
| [Atividade de personalização automatizada (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Não |  |
| [Atividade do Recommendations](/help/main/c-recommendations/recommendations.md) | Sim |  |
| [Qualquer atividade que use uma oferta de redirecionamento](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md) | Sim |

Como todos os tipos de atividades ainda não são compatíveis com o A4T, é recomendável manter ou implementar mboxes de conversão importantes, como `orderConfirmPage` mbox.

## Exemplos de relatórios do A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Para exibir relatórios do A4T em [!DNL Target], clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista que usa [!DNL Analytics] como sua fonte de relatórios, em seguida, clique no botão **[!UICONTROL Relatórios]** guia .

>[!NOTE]
>
>Você pode usar o [!UICONTROL Fonte de geração de relatórios] lista suspensa na parte superior do [!UICONTROL Atividades] para exibir somente as atividades que usam o A4T.

Você pode alternar entre as variáveis [!UICONTROL Exibição em tabela] e [!UICONTROL Exibição em gráfico] do relatório clicando no ícone apropriado no lado superior direito do relatório.

A ilustração a seguir mostra a [!UICONTROL Visualização de gráfico] de um relatório do A4T com a lista suspensa de [!UICONTROL Métrica de relatórios] exibindo as métricas de meta disponíveis do [!DNL Analytics]:

![](assets/a4t_report_graph1.png)

A ilustração a seguir mostra a [!UICONTROL Visualização de gráfico] de um relatório do A4T com a lista suspensa de [!UICONTROL Público-alvo] exibindo os públicos-alvo disponíveis do [!DNL Analytics]:

![](assets/a4t_report_graph2.png)

A ilustração a seguir mostra a [!UICONTROL Visualização de tabela] de um relatório do A4T:

![](assets/a4t_report_table.png)

Para exibir o relatório no [!DNL Analytics] em vez de no [!DNL Target], clique em **[!UICONTROL Exibir no Analytics]** na parte superior do relatório.

## Tutorial do Analytics &amp; Target: práticas recomendadas para análise {#section_3438E6E77A464424B717A4FD333B84B2}

Abra o [Analytics &amp; Target: Práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, fornecido por [!DNL Adobe Experience League].

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste tópico.

### Analytics for Adobe Target (A4T) (4:32) ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo explica como usar o [!DNL Analytics] como fonte de relatórios em [!DNL Target] para conduzir a análise do seu programa de otimização.

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
>* [Analytics para [!DNL Target] implementação](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md): Contém informações de implementação para at.js e o SDK da Web da plataforma.
>* [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md)
>* [O que é o SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html): Contém informações de visão geral sobre o SDK da Web da plataforma.
>* [Visão geral do Target](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html): Contém informações específicas para [!DNL Target] e [!DNL Platform Web SDK].

