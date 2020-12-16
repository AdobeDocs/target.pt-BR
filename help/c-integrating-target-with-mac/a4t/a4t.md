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

[!DNL Adobe Analytics for Target] (A4T) é uma integração entre soluções que permite criar atividades com base em métricas de  [!DNL Analytics] conversão e segmentos de audiência. A integração A4T permite que você use relatórios [!DNL Analytics] para examinar seus resultados. Se você usar [!DNL Analytics] como fonte de relatórios para uma atividade, todos os relatórios e segmentação dessa atividade serão baseados na coleta de dados [!DNL Analytics].

## Visão geral do A4T {#section_92B66069210C40DBA937790E8CC596CF}

A integração [!DNL Analytics for Target] entre [!DNL Analytics] e [!DNL Target] fornece ferramentas poderosas de análise e economia de tempo para o programa de otimização.

Os três principais benefícios do uso de dados [!DNL Analytics] em [!DNL Target] são:

* Os profissionais de marketing podem aplicar dinamicamente [!DNL Analytics] métricas de sucesso ou segmentos de relatórios a [!DNL Target] relatórios de atividade a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Uma única fonte de dados elimina a variação que ocorre ao coletar dados em dois sistemas separados.
* Sua implementação [!DNL Analytics] existente coleta todos os dados necessários. Não há necessidade de implementar as mboxes nas páginas com o único objetivo de coletar dados para os relatórios. Embora ainda seja recomendável implementar uma mbox de confirmação de pedido para [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) atividades.

>[!IMPORTANT]
>
>Antes de começar a usar A4T, você precisa solicitar que sua conta seja provisionada para a integração. Use [este formulário](https://www.adobe.com/go/audiences) para solicitar o aprovisionamento.
>
>A integração que habilita [!DNL Analytics] como fonte de dados para [!DNL Target] (A4T) representa a próxima geração do plug-in Test&amp;Público alvo para SiteCatalyst. Este plug-in foi descontinuado, mas ainda é suportado para os clientes que já o utilizam.

Se você usar [!DNL Analytics] como fonte de relatórios para uma atividade, todos os relatórios e segmentação dessa atividade serão baseados em [!DNL Analytics].

Todas as métricas [!DNL Analytics], incluindo métricas calculadas, estão disponíveis em [!DNL Target] e no relatório [!UICONTROL Atividades de Públicos alvos] em [!DNL Analytics]. Da mesma forma, qualquer segmento disponível em [!DNL Analytics] pode ser aplicado a ambas as soluções. Você pode aplicar a métrica ou a audiência ao relatório em [!DNL Target] após a atividade ter sido iniciada ou mesmo após a atividade ter sido concluída.

Todas as métricas estão incluídas, incluindo as métricas personalizadas ou calculadas que estão integradas no [!DNL Analytics].

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

Tenha os seguintes pontos em mente ao considerar o uso do A4T:

* Para usar [!DNL Analytics] como fonte de relatórios para [!DNL Target], você e sua empresa devem ter acesso a [!DNL Analytics] e a [!DNL Target]. [Entre em contato com o seu representante de conta,](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) caso precise de uma solução.
* A fonte de relatórios é definida para cada atividade. [!DNL Target] continua a coletar dados para uso no relatórios e  [!DNL Target] os dados ainda estarão disponíveis se você preferir basear uma atividade em dados coletados pelo  [!DNL Target].
* Você deve usar uma fonte de relatórios ou outra. Você não pode coletar dados para uma única atividade de ambas as fontes.
* Ao usar a A4T, todas as métricas de sucesso disponíveis para suas atividades são [!DNL Analytics] métricas. No entanto, sua métrica de meta pode ser baseada em uma chamada mbox. Por exemplo, você pode usar os recursos de rastreamento de cliques predefinidos do Público alvo com A4T em vez de precisar implementar [!DNL Analytics] código de rastreamento de cliques.
* Ao exibir o relatórios de uma atividade A4T na interface do usuário [!DNL Target], você está visualizando os dados [!DNL Analytics]. Por exemplo, se você usar a métrica [!UICONTROL Visitante] em [!DNL Target], estará usando a métrica [!DNL Analytics] [!UICONTROL Visitante], não a métrica [!DNL Target] [!UICONTROL Visitantes], que agora é chamada [!UICONTROL Participantes]. Essa diferença é especialmente importante para as métricas de tráfego básicas ([!UICONTROL Visitantes], [!UICONTROL Visitas], [!UICONTROL Visualizações de página]) e métricas de conversão.
* Qualquer atividade [!DNL Target] existente continua a usar a coleta de dados [!DNL Target] e não é afetada pela ativação da A4T.
* Somente uma métrica baseada em mbox é permitida ao usar [!DNL Analytics] como a fonte do relatórios.
* Uma chamada de servidor para servidor de [!DNL Target] para [!DNL Analytics] envia informações de atividade e experiência para [!DNL Analytics]. Essa integração não resulta em chamadas de servidor adicionais para [!DNL Target] ou [!DNL Analytics].

   Em algumas situações, a chamada de classificação de [!DNL Target] para [!DNL Analytics] pode falhar e o atividade não mostra dados em [!DNL Analytics]. Se isso acontecer, consulte [Solucionar problemas do Analytics e da integração de Públicos alvos (A4T)](/help/c-integrating-target-with-mac/a4t/c-a4t-troubleshooting/a4t-troubleshooting.md). Você também pode [entrar em contato com o Client Care](/help/cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) para obter assistência adicional.

## Tipos de atividade suportados {#section_F487896214BF4803AF78C552EF1669AA}

A tabela a seguir mostra quais tipos de atividade suportam [!DNL Analytics] como a fonte de relatórios em [!DNL Target] (A4T):

| Tipos de atividades | O A4T é compatível? | Observações, se aplicável |
|--- |--- |--- |
| Atividade A/B com divisão manual de tráfego | Sim |  |
| Atividade A/B com alocação automática | Sim | Consulte [Suporte do Analytics para Públicos alvos (A4T) para Autoalocar e Público alvo automático de atividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa). |
| Atividade A/B com direcionamento automático | Sim | Consulte [Suporte do Analytics para Públicos alvos (A4T) para Autoalocar e Público alvo automático de atividades](/help/c-integrating-target-with-mac/a4t/campaign-creation.md#a4t-aa). |
| Direcionamento de experiência (XT) | Sim |  |
| Teste multivariado (MVT) | Sim | Exige uma meta de métrica de meta baseada em mbox para obter o relatório [!UICONTROL Contribuição do elemento].  O relatório [!UICONTROL Contribuição do elemento] não suporta atualmente as métricas [!DNL Analytics]. |
| Atividade de personalização automatizada (AP) | Não |  |
| Atividade do Recommendations | Sim |  |
| Aplicativo móvel | Sim | Compatível com o Mobile Services SDK, versão 4.13.1 ou superior.  Para obter mais informações, consulte a [documentação do Mobile Services](https://experienceleague.adobe.com/docs/mobile-services/using/home.html). |
| Email | Não |  |
| API de entrega do lado do servidor | Sim | Para obter mais informações, consulte o [Servidor: implementar o Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK do NodeJS | Sim | Para obter mais informações, consulte o [Servidor: implementar o Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| AEM 6.1 (ou anterior) Integração dos Serviços em Nuvem | Não |  |
| AEM 6.2 (ou posterior) Integração dos Serviços em Nuvem | Sim | Para obter mais informações, consulte [Integração com o Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) na documentação [!DNL Adobe Experience Manager] 6.2. |
| Qualquer atividade usando uma oferta de redirecionamento | Sim | Existem requisitos mínimos mais rigorosos para o uso de Ofertas de redirecionamento com o A4T. Para obter mais informações, consulte [Ofertas de redirecionamento - Perguntas frequentes do A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Sim |  |

Como todos os tipos de atividade ainda não suportam A4T, é recomendável manter ou implementar mboxes de conversão importantes, como a mbox `orderConfirmPage`.

## Exemplos de relatórios A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Para visualização dos relatórios A4T em [!DNL Target], clique em **[!UICONTROL Atividade]**, clique na atividade desejada na lista que usa [!DNL Analytics] como sua fonte de relatórios e clique na guia **[!UICONTROL Relatórios]**.

>[!NOTE]
>
>Você pode usar a lista suspensa [!UICONTROL Fonte de relatórios] na parte superior da página [!UICONTROL Atividades] para exibir somente as atividades que usam [!DNL Analytics] como fonte de relatórios.

Você pode alternar entre [!UICONTROL Visualização de tabela] e [!UICONTROL Visualização de gráfico] do relatório clicando no ícone apropriado no lado superior direito do relatório.

A ilustração a seguir mostra a [!UICONTROL Visualização de gráfico] de um relatório do A4T com a lista suspensa de [!UICONTROL Métrica de relatórios] exibindo as métricas de meta disponíveis do [!DNL Analytics]:

![](assets/a4t_report_graph1.png)

A ilustração a seguir mostra a [!UICONTROL Visualização de gráfico] de um relatório do A4T com a lista suspensa de [!UICONTROL Público-alvo] exibindo os públicos-alvo disponíveis do [!DNL Analytics]:

![](assets/a4t_report_graph2.png)

A ilustração a seguir mostra a [!UICONTROL Visualização de tabela] de um relatório do A4T:

![](assets/a4t_report_table.png)

Para exibir o relatório no [!DNL Analytics] em vez de no [!DNL Target], clique em **[!UICONTROL Exibir no Analytics]** na parte superior do relatório.

## Tutorial do Analytics &amp; Target: práticas recomendadas para análise {#section_3438E6E77A464424B717A4FD333B84B2}

Abra o [Analytics &amp; Público alvo: Tutorial de práticas recomendadas para Análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido por [!DNL Adobe Experience League].

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste tópico.

### Analytics for Público alvo (A4T) (4:32) ![emblema de visão geral](/help/assets/overview.png)

Este vídeo explica como usar [!DNL Analytics] como uma fonte de relatórios em [!DNL Target] para direcionar a análise do programa de otimização.

* Explique o que é o A4T e porque você o usaria
* Explique como o A4T funciona
* Entenda os pré-requisitos necessários antes de utilizar o A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384)

### Integração do Analytics / Público alvo (A4T) (40:33) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo é uma gravação de &quot;[Horas do Office](/help/cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)&quot;, uma iniciativa liderada pela equipe de Atendimento ao cliente da Adobe.

* Como configurar e validar o funcionamento da integração
* Como funciona a integração
* Saiba mais sobre os relatórios adequados para usar no Analytics
* Respostas às perguntas comuns sobre o A4T

[Horas do Office para Integração de Públicos alvos/Análises (A4T)](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)