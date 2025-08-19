---
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, direcionamento automático, direcionamento automático, relatório do direcionamento automático, relatório de direcionamento automático, personalização, insights, segmentos automatizados, perguntas frequentes, perguntas frequentes, atributos importantes
description: Saiba como usar os relatórios especializados para atividades de Automated Personalization (AP) e Direcionamento automático (AT) - Segmentos automatizados e atributos importantes.
title: Como usar os relatórios do Personalization Insights?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 28%

---

# [!UICONTROL Personalization Insights] relatórios

Dois relatórios especializados estão disponíveis para usuários de atividades do [!UICONTROL Automated Personalization] (AP) e do [!UICONTROL Auto-Target] (AT): os relatórios [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes].

## Considerações

Leve em consideração o seguinte ao usar relatórios de [!UICONTROL Personalization Insights]:

* As atividades de AP e AT estão disponíveis como parte da [[!DNL Target Premium] solução](/help/main/c-intro/intro.md#premium). Não estão incluídos com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

* [!UICONTROL Personalization Insights] relatórios estão disponíveis somente para atividades de AP e AT configuradas da seguinte maneira:

   * [!DNL Target] relatórios > [!UICONTROL Conversion]

     Por exemplo:

     ![Relatórios de público alvo > Conversão](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] relatórios > [!DNL Conversion]

     Por exemplo:

     ![Relatórios Analíticos > Conversão](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] relatórios > [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     Por exemplo:

     ![Usar uma métrica do Analytics > Maximizar taxa de conversão de visitas](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* As atividades em que a meta de otimização foi alterada para a conversão da receita após a atividade já estar ativa também não são compatíveis.

* [!UICONTROL Personalization Insights] relatórios estão disponíveis somente se [!UICONTROL Primary Goal] estiver selecionado na lista suspensa [!UICONTROL Report Metric].

* Há suporte para [!UICONTROL Personalization Insights] relatórios somente no [ambiente padrão](/help/main/administrating-target/hosts.md).

* Os relatórios [!UICONTROL Personalization Insights] são gerados apenas para atividades que estão no status [!UICONTROL Live] e foram ativadas e receberam tráfego por pelo menos 15 dias.

## Visão geral dos relatórios do Personalization Insights {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

O objetivo dos relatórios do [!UICONTROL Personalization Insights] é fornecer mais informações sobre como os modelos de personalização do [!UICONTROL Target] por trás de suas atividades de AP e AT personalizam o tráfego de visitantes. O [algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) é a base para os modelos de personalização [!DNL Target].

Como a meta dos relatórios do [!UICONTROL Personalization Insights] é entender como os modelos de personalização do [!DNL Target] decidiram enviar qual visitante para que parte do conteúdo, os relatórios do [!UICONTROL Personalization Insights] refletem apenas um subsegmento de todo o tráfego distribuído pela atividade de AP ou AT. Especificamente, os dois relatórios refletem todo o tráfego que usou o modelo de personalização. Em outras palavras, os relatórios [!UICONTROL Personalization Insights] não consideram o tráfego de controle ou o tráfego distribuído pelo modelo vencedor global.

Dois relatórios de [!UICONTROL Personalization Insights] estão disponíveis:

| Relatório | Detalhes |
|--- |--- |
| [!UICONTROL Automated Segments] | Visitantes diferentes respondem de forma distinta às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização [!DNL Target], responderam às ofertas/experiências na atividade. |
| [!UICONTROL Important Attributes] | Em atividades diferentes, atributos distintos são mais ou menos importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa. |

## Interpretação de atributos no Personalization Insights {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Há dois tipos de atributos representados nos relatórios do [!UICONTROL Personalization Insights] que são usados nos seus modelos de AP ou de Direcionamento automático:

* **Atributos coletados automaticamente pelo Target:** O [!DNL Target] usa um conjunto de dados básico para criar seus algoritmos de personalização em atividades de AP e AT, que são refletidas no Personalization Insights. Consulte [Coleta de dados para algoritmos Personalization do Target](/help/main/c-activities/t-automated-personalization/ap-data.md) para obter os tipos de dados, atributos de exemplo e sua convenção de nomenclatura [!UICONTROL Personalization Insights]. Observe que, embora esses atributos sejam considerados, os modelos de uma atividade individual podem não usar todos esses atributos no modelo final.
* **Atributos passados para o Destino:** Consulte [Carregando Dados para os Algoritmos Personalization de Destino](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

O [!DNL Target] fornece várias maneiras de você transmitir dados adicionais para o [!DNL Target] para enriquecer o conjunto de dados base usado para criar seus algoritmos de personalização em atividades de AP e AT:

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados |
|--- |--- |--- |
| Atributos de perfil, incluindo scripts de perfil, API de atualização do perfil e atributos de perfil na página | Qualquer informação que você decidiu incluir no perfil de usuário do Target.<br>Essas informações podem vir de scripts de perfil, de informações carregadas usando a API de atualização de perfil ou de parâmetros de perfil na mbox contendo o prefixo &quot;perfil&quot;. | `Custom - Profile - [parameter name]` |
| Parâmetros da página (também chamados de &quot;parâmetros de mbox&quot;) | Pares de nomes/valores passados diretamente pelo código de página, que não são armazenados no perfil do visitante para uso futuro. | `Custom - Mbox Parameter - [parameter name]` |
| Atributos do cliente | Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, aproveite os dados no Adobe Analytics e no Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Públicos-alvo compartilhados (Adobe Audience Manager ou Adobe Analytics) | Os públicos-alvo criados por meio do Adobe Audience Manager ou do Adobe Analytics e compartilhados com o Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Públicos-alvo compartilhados (Adobe Experience Platform/Real-time CDP) | Públicos-alvo criados por meio da Adobe Experience Platform/Real-time CDP e compartilhados com o Target via Destinos. | `Custom - Adobe Experience Platform Segment - [segment name]` |
| Atributos compartilhados (Adobe Experience Platform/Real-time CDP) | Atributos criados por meio da Adobe Experience Platform/Real-time CDP e compartilhados com o Target via Destinos. Este recurso atualmente está no Beta. | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| Públicos-alvo/segmentos dos relatórios na atividade | Públicos-alvo definidos na atividade de AP ou Direcionamento automático durante a configuração em &quot;Metas e métricas&quot;. | `Custom - Reporting Segment - [segment name]` |

## Perguntas frequentes

Lista de perguntas frequentes sobre os relatórios do [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] do [!UICONTROL Insights].

### Por quanto tempo os dados para modelos [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] persistem?

Os modelos do [!UICONTROL Automated Personalization] (AP) e do [!UICONTROL Auto-Target] são treinados nos últimos 45 dias de comportamento do usuário (perfis de usuário, eventos de impressão e eventos de conversão) para a atividade.

Os modelos [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] retêm o comportamento do usuário, registros de treinamento e dados de decisão do modelo por 90 dias para produzir relatórios [!UICONTROL Insights]. Após 90 dias, os registros de treinamento e as decisões do modelo são descartados. Os modelos [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] também retêm dados de impressão e conversão agregados da experiência/nível de oferta para fins de relatório por dois anos. Esses dados são somente dados de nível agregado e não contêm dados de perfil de nível individual.

## Vídeo de treinamento: usar os relatórios do Personalization Insights ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Para obter mais informações, consulte [Uso dos Relatórios do Personalization Insights no Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Blogs do Adobe

* Parte 1: [Tirando o mistério da mágica do Personalization movido por IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Parte 2: [Uma prévia da cortina de IA para o Personalization no Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Parte 3: [MAGIX — a solução para o problema da caixa preta do Personalization orientado por IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
