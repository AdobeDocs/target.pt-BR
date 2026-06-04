---
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, direcionamento automático, direcionamento automático, relatório do direcionamento automático, relatório de direcionamento automático, personalização, insights, segmentos automatizados, perguntas frequentes, perguntas frequentes, atributos importantes
description: Saiba como usar os relatórios especializados para atividades de Automated Personalization (AP) e Direcionamento automático (AT) - Segmentos automatizados e atributos importantes.
title: Como usar os relatórios do Personalization Insights?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
TQID: https://experienceleague.adobe.com/qDaIhyfV-m3oHJArqg8TKMAe-k5QwjEUjGzhZrPSTEI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
subfeature_v2: id: fff07a91-d479-45f4-ae95-9762e79b1b7c
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1023
ht-degree: 29%

---

# [!UICONTROL Relatórios do Personalization Insights]

Dois relatórios especializados estão disponíveis para usuários de atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] (AT): os relatórios de [!UICONTROL Segmentos automatizados] e [!UICONTROL Atributos importantes].

## Considerações

Considere o seguinte ao usar os [!UICONTROL relatórios do Personalization Insights]:

* As atividades de AP e AT estão disponíveis como parte da [[!DNL Target Premium] solução](/help/main/c-intro/intro.md#premium). Não estão incluídos com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

* Os relatórios do [!UICONTROL Personalization Insights] estão disponíveis apenas para atividades de AP e AT configuradas da seguinte forma:

   * [!DNL Target] relatórios > [!UICONTROL Conversão]

     Por exemplo:

     ![Relatórios de público alvo > Conversão](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] relatórios > [!DNL Conversion]

     Por exemplo:

     ![Relatórios Analíticos > Conversão](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] relatórios > [!UICONTROL Usar uma métrica do Analytics] > [!UICONTROL Maximizar o Índice de Conversão de Visitas]

     Por exemplo:

     ![Usar uma métrica do Analytics > Maximizar taxa de conversão de visitas](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* As atividades em que a meta de otimização foi alterada para a conversão da receita após a atividade já estar ativa também não são compatíveis.

* Os relatórios do [!UICONTROL Personalization Insights] só estarão disponíveis se a [!UICONTROL Meta primária] for selecionada na lista suspensa [!UICONTROL Métrica de relatório].

* Há suporte para os relatórios do [!UICONTROL Personalization Insights] somente no [ambiente padrão](/help/main/administrating-target/hosts.md).

* Os relatórios do [!UICONTROL Personalization Insights] são gerados apenas para atividades que estão no status [!UICONTROL Live] e foram ativadas e receberam tráfego por pelo menos 15 dias.

## Visão geral dos relatórios do Personalization Insights {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

O objetivo dos relatórios do [!UICONTROL Personalization Insights] é fornecer mais informações sobre como os modelos de personalização do [!UICONTROL Target] por trás de suas atividades de AP e AT personalizam o tráfego de visitantes. O [algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) é a base para os modelos de personalização [!DNL Target].

Como a meta dos relatórios do [!UICONTROL Personalization Insights] é entender como os modelos de personalização do [!DNL Target] decidiram enviar qual visitante para qual parte do conteúdo, os relatórios do [!UICONTROL Personalization Insights] refletem apenas um subsegmento de todo o tráfego distribuído pela sua atividade de AP ou AT. Especificamente, os dois relatórios refletem todo o tráfego que usou o modelo de personalização. Ou seja, os relatórios de [!UICONTROL Insights de personalização] não consideram o tráfego de controle ou o tráfego distribuído pelo modelo vencedor global.

Dois relatórios do [!UICONTROL Personalization Insights] estão disponíveis:

| Relatório | Detalhes |
|--- |--- |
| [!UICONTROL Segmentos automatizados] | Visitantes diferentes respondem de forma distinta às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização [!DNL Target], responderam às ofertas/experiências na atividade. |
| [!UICONTROL Atributos importantes] | Em atividades diferentes, atributos distintos são mais ou menos importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa. |

## Interpretação de atributos no Personalization Insights {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Há dois tipos de atributos representados nos [!UICONTROL Insights de personalização] que são usados nos modelos de AP ou Direcionamento automático:

* **Atributos coletados automaticamente pelo Target:** O [!DNL Target] usa um conjunto de dados básico para criar seus algoritmos de personalização em atividades de AP e AT, que são refletidas no Personalization Insights. Consulte [Coleta de dados para algoritmos Personalization do Target](/help/main/c-activities/t-automated-personalization/ap-data.md) para obter os tipos de dados, atributos de exemplo e sua convenção de nomenclatura do [!UICONTROL Personalization Insights]. Observe que, embora esses atributos sejam considerados, os modelos de uma atividade individual podem não usar todos esses atributos no modelo final.
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

Lista de perguntas frequentes sobre os relatórios [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] [!UICONTROL Insights].

### Por quanto tempo os dados para modelos [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] persistem?

Os modelos [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] são treinados nos últimos 45 dias de comportamento do usuário (perfis de usuário, eventos de impressão e eventos de conversão) para a atividade.

Os modelos [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] retêm o comportamento do usuário, registros de treinamento e dados de decisão do modelo por 90 dias para produzir relatórios de [!UICONTROL Insights]. Após 90 dias, os registros de treinamento e as decisões do modelo são descartados. Os modelos [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] também retêm dados de impressão e conversão agregados no nível de experiência/oferta para fins de relatório por dois anos. Esses dados são somente dados de nível agregado e não contêm dados de perfil de nível individual.

## Vídeo de treinamento: usar os relatórios do Personalization Insights ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Para obter mais informações, consulte [Uso dos Relatórios do Personalization Insights no Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Blogs do Adobe

* Parte 1: [Tirando o mistério da mágica do Personalization movido por IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Parte 2: [Uma prévia da cortina de IA para o Personalization no Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Parte 3: [MAGIX — a solução para o problema da caixa preta do Personalization orientado por IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
