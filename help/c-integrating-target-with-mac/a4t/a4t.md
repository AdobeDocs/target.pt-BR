---
description: O "Analytics for Target" (A4T) da Adobe é uma integração entre soluções que permite criar atividades com base nas métricas de conversão e nos segmentos de público-alvo do Analytics. Essa integração permite usar os relatórios do Analytics para analisar seus resultados. Se usar o Analytics como fonte de relatórios para uma atividade, todos os relatórios e segmentações dessa atividade serão baseados nos dados coletados pelo Analytics.
keywords: a4t; analytics; analytics para target; fonte de relatórios do analytics; adobe analytics como fonte de relatório para o target
seo-description: O "Analytics for Target" (A4T) da Adobe é uma integração entre soluções que permite criar atividades com base nas métricas de conversão e nos segmentos de público-alvo do Analytics. Essa integração permite usar os relatórios do Analytics para analisar seus resultados. Se usar o Analytics como fonte de relatórios para uma atividade, todos os relatórios e segmentações dessa atividade serão baseados nos dados coletados pelo Analytics.
seo-title: Adobe Analytics como origem de relatório do Adobe Target (A4T)
solution: Target
subtopic: Teste multivariado
title: Adobe Analytics como origem de relatório do Adobe Target (A4T)
topic: Padrão
uuid: 616798a6-1587-410f-9ac6-473beb39e3fc
translation-type: tm+mt
source-git-commit: 7c94222aff59f92031f84436da5f8733d92be4b7

---


# Adobe Analytics como origem de relatório do Adobe Target (A4T){#adobe-analytics-as-the-reporting-source-for-adobe-target-a-t}

O "Analytics for Target" (A4T) da Adobe é uma integração entre soluções que permite criar atividades com base nas métricas de conversão e nos segmentos de público-alvo do Analytics. A integração A4T permite que você use os relatórios do Analytics para examinar os resultados. Se usar o Analytics como fonte de relatórios para uma atividade, todos os relatórios e segmentações dessa atividade serão baseados nos dados coletados pelo Analytics.

## Visão Geral do A4T {#section_92B66069210C40DBA937790E8CC596CF}

A integração do Analytics for Target entre o Analytics e o Target fornece ferramentas poderosas de análise e economia de tempo para o seu programa de otimização.

Os três principais benefícios de usar dados do Analytics no Target são:

* Os profissionais de marketing podem aplicar dinamicamente as métricas de sucesso ou os segmentos de relatórios do Analytics aos relatórios de atividades do Target a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Uma única fonte de dados elimina a variação que ocorre ao coletar dados em dois sistemas separados.
* A sua implementação do Adobe Analytics existente coleta todos os dados necessários. Não há necessidade de implementar as mboxes nas páginas com o único objetivo de coletar dados para os relatórios. Contudo, ainda é recomendável implementar uma mbox de confirmação de pedido para atividades de personalização automatizada (AP).

>[!IMPORTANT]
>
>Antes de começar a usar A4T, você precisa solicitar que sua conta seja provisionada para a integração. Use [este formulário](https://www.adobe.com/go/audiences) para solicitar o aprovisionamento.
>
>A integração que habilita o Adobe Analytics como fonte de dados para o Adobe Target (A4T) representa a próxima geração do Test&amp;Target para o plug-in do SiteCatalyst. Este plug-in foi descontinuado, mas ainda é suportado para os clientes que já o utilizam.

Se você usar o Analytics como a fonte para geração de relatórios de uma atividade, todo o processo de geração de relatórios e segmentação dessa atividade será baseado no Analytics.

Todas as métricas do Analytics, incluindo as métricas calculadas, estão disponíveis no Target Standard/Premium e no relatório do Target Activities no Analytics. Da mesma forma, qualquer segmento disponível no Analytics pode ser aplicado a ambas as soluções. Você pode aplicar a métrica ou público-alvo ao relatório no Target Standard/Premium após iniciar o teste ou mesmo após sua conclusão.

Todas as métricas estão incluídas, incluindo as métricas personalizadas ou calculadas que estão integradas no Analytics.

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

Tenha os seguintes pontos em mente ao considerar o uso do A4T:

* Para usar o Adobe Analytics como a fonte de relatórios para o Adobe Target, você e sua empresa devem ter acesso ao Adobe Analytics e Adobe Target. [Entre em contato com o seu representante de conta,](../../cmp-resources-and-contact-information.md#concept_34A1CA16F2244D42930BB77846A5ABBB) caso precise de uma solução.
* A fonte de relatórios é definida para cada atividade. O Target continua a coletar dados para usar em relatórios, e os dados do Target ainda estão disponíveis caso prefira basear uma atividade em dados coletados por Target.
* Você deve usar uma fonte de relatórios ou outra. Você não pode coletar dados para uma única atividade de ambas as fontes.
* Ao usar o A4T, todas as métricas de sucesso disponíveis para suas atividades são métricas do Analytics. No entanto, sua métrica de meta pode ser baseada em uma chamada mbox. Por exemplo, você pode usar os recursos de rastreamento de cliques integrados do Target com o A4T em vez de precisar implementar o código de rastreamento de cliques do Analytics.
* Ao exibir relatórios de uma atividade A4T na interface do usuário do Target, você está visualizando dados do Analytics. Por exemplo, se você usar a métrica de visitantes no Target, estará usando a métrica de visitantes do Analytics, não a do Target, que atualmente é chamada de Participantes. Esta diferença é especialmente importante para as métricas básicas de tráfego (visitantes, visitas, visualizações de página) e para as métricas de conversão.
* Quaisquer atividades do Target existentes continuam a usar a coleta de dados do Target e não são afetadas pela habilitação do A4T.
* Apenas uma métrica baseada em mbox é permitida ao usar o Analytics como fonte de relatórios.
* Uma chamada de servidor para servidor do Target para o Analytics envia informações de atividade e experiência para o Analytics. Esta integração não resulta em chamadas de servidor adicionais para o Target ou Analytics.

## Tipos de atividades suportadas {#section_F487896214BF4803AF78C552EF1669AA}

A tabela a seguir mostra quais tipos de atividade são compatíveis com o Analytics como fonte de relatório (A4T):

| Tipos de atividades | O A4T é compatível? | Observações, se aplicável |
|--- |--- |--- |
| Atividade A/B com divisão manual de tráfego | Sim |  |
| Atividade A/B com alocação automática | Não |  |
| Atividade A/B com direcionamento automático | Não |  |
| Direcionamento de experiência (XT) | Sim |  |
| Teste multivariado (MVT) | Sim | Exige métrica de meta baseada em mbox para obter o relatório de Contribuição de elementos.  Atualmente, o Relatório de contribuição de elementos não suporta métricas do Analytics. |
| Atividade de personalização automatizada (AP) | Não |  |
| Atividade do Recommendations | Sim |  |
| Aplicativo móvel | Sim | Compatível com o Mobile Services SDK, versão 4.13.1 ou superior.  Para obter mais informações, consulte a [documentação do Mobile Services](https://marketing.adobe.com/resources/help/en_US/mobile/). |
| Email | Não |  |
| API de entrega do lado do servidor | Sim | Para obter mais informações, consulte o [Servidor: implementar o Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| SDK do NodeJS | Sim | Para obter mais informações, consulte o [Servidor: implementar o Target](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| AEM 6.1 (ou anterior) Integração dos Serviços em Nuvem | Não |  |
| AEM 6.2 (ou posterior) Integração dos Serviços em Nuvem | Sim | Para obter mais informações, consulte [Integração com o Adobe Target](https://helpx.adobe.com/experience-manager/6-2/sites/administering/using/target.html) na documentação do Adobe Experience Manager 6.2. |
| Qualquer atividade usando uma Oferta de redirecionamento | Sim | Existem requisitos mínimos mais rigorosos para o uso de Ofertas de redirecionamento com o A4T. Para obter mais informações, consulte [Ofertas de redirecionamento - Perguntas frequentes do A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md). |
| Node.JS | Sim |  |

Como todos os tipos de atividade ainda não compatíveis com o A4T, é recomendável manter ou implementar mboxes de conversão importantes, como a mbox "orderConfirmPage".

## Exemplos de relatórios do A4T {#section_F0A43A1CB2F04E8282B909E4D7034361}

Para exibir os relatórios do A4T no [!DNL Target]**, clique em[!UICONTROL Atividades]**, clique na atividade desejada da lista que usa o [!DNL Analytics] com sua fonte de geração de relatórios &gt; em seguida, clique na guia **[!UICONTROL Relatórios].**

>[!NOTE]
>
>Você pode usar a lista suspensa [!UICONTROL Fonte de relatórios] na parte superior da página [!UICONTROL Atividades] para exibir somente as atividades que usam [!DNL Analytics] como fonte de relatórios.

Você pode alternar entre a Visualização de tabela e [!UICONTROL Visualização de gráfico] do relatório clicando no ícone apropriado na parte superior direita do relatório.

A ilustração a seguir mostra a [!UICONTROL Visualização de gráfico] de um relatório do A4T com a lista suspensa de [!UICONTROL Métrica de relatórios] exibindo as métricas de meta disponíveis do [!DNL Analytics]:

![](assets/a4t_report_graph1.png)

A ilustração a seguir mostra a [!UICONTROL Visualização de gráfico] de um relatório do A4T com a lista suspensa de [!UICONTROL Público-alvo] exibindo os públicos-alvo disponíveis do [!DNL Analytics]:

![](assets/a4t_report_graph2.png)

A ilustração a seguir mostra a [!UICONTROL Visualização de tabela] de um relatório do A4T:

![](assets/a4t_report_table.png)

Para exibir o relatório no [!DNL Analytics] em vez de no [!DNL Target], clique em **[!UICONTROL Exibir no Analytics]** na parte superior do relatório.

## Tutorial do Analytics &amp; Target: práticas recomendadas para análise {#section_3438E6E77A464424B717A4FD333B84B2}

Abra o tutorial do [Analytics &amp; Target: práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido pela Adobe Experience League.

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Analytics for Target (A4T) (4:32)

Este vídeo explica como usar o Adobe Analytics como fonte de relatórios no Adobe Target para orientar a análise do seu programa de otimização.

* Explique o que é o A4T e porque você o usaria
* Explique como o A4T funciona
* Entenda os pré-requisitos necessários antes de utilizar o A4T

>[!VIDEO](https://video.tv.adobe.com/v/17384?captions=por_br)

### Integração do Analytics/Target (A4T) (40:33)

Este vídeo é uma gravação de "[Horas do Office](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)", uma iniciativa liderada pela equipe de Atendimento ao cliente da Adobe.

* Como configurar e validar o funcionamento da integração
* Como funciona a integração
* Saiba mais sobre os relatórios adequados para usar no Analytics
* Respostas às perguntas comuns sobre o A4T

[Integração do Analytics/Target (A 4 T) Office](https://helpx.adobe.com/customer-care-office-hours/target/analytics-target-A4T-integration.html)