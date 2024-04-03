---
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, direcionamento automático, direcionamento automático, relatório do direcionamento automático, relatório de direcionamento automático, personalização, insights, segmentos automatizados, perguntas frequentes, perguntas frequentes, atributos importantes
description: Saiba como usar os relatórios especializados para atividades de Automated Personalization (AP) e Direcionamento automático (AT) - Segmentos automatizados e atributos importantes.
title: Como usar os relatórios de insights de personalização?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 6c8f042acb257fc908349c679bf745e477f94af4
workflow-type: tm+mt
source-wordcount: '877'
ht-degree: 28%

---

# [!UICONTROL Personalization Insights] relatórios

Dois relatórios especializados estão disponíveis para usuários do [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] (AT) Atividades: a [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes] relatórios.

## Considerações

Considere o seguinte ao usar [!UICONTROL Personalization Insights] relatórios:

* As atividades de AP e AT estão disponíveis como parte da [[!DNL Target Premium] solução](/help/main/c-intro/intro.md#premium). Não estão incluídos com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

* [!UICONTROL Personalization Insights] Os relatórios do estão disponíveis somente para atividades de AP e AT configuradas da seguinte maneira:

   * [!DNL Target] relatórios > [!UICONTROL Conversion]

     Por exemplo:

     ![Relatórios do Target > Conversão](/help/main/c-reports/assets/conversion.png)

   * [!DNL Analytics] relatórios > [!DNL Conversion]

     Por exemplo:

     ![Relatórios Analíticos > Conversão](/help/main/c-reports/assets/analytics-reporting-conversion.png)

   * [!DNL Analytics] relatórios > [!UICONTROL Use an Analytics metric] > [!UICONTROL Maximize Visit Conversion Rate]

     Por exemplo:

     ![Use uma métrica do Analytics > Maximizar taxa de conversão de visitas](/help/main/c-reports/assets/maximize-visit-conversion-rate.png)

* As atividades em que a meta de otimização foi alterada para a conversão da receita após a atividade já estar ativa também não são compatíveis.

* [!UICONTROL Personalization Insights] Os relatórios do estão disponíveis somente se o [!UICONTROL Primary Goal] está selecionado no menu [!UICONTROL Report Metric] lista suspensa.

* [!UICONTROL Personalization Insights] Os relatórios do são compatíveis com o [ambiente padrão](/help/main/administrating-target/hosts.md) somente.

* [!UICONTROL Personalization Insights] os relatórios são gerados somente para atividades que estão na [!UICONTROL Live] e foram ativados e receberam tráfego por pelo menos 15 dias.

## Visão geral dos relatórios do Insights {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

A meta do [!UICONTROL Personalization Insights] relatórios é fornecer mais informações sobre a forma como os [!UICONTROL Target] os modelos de personalização por trás de suas atividades de AP e AT personalizam o tráfego de visitantes. A variável [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) é a base para a [!DNL Target] modelos de personalização.

Como a meta do [!UICONTROL Personalization Insights] relatórios é entender como a [!DNL Target] modelos de personalização decidiram enviar qual visitante para que parte do conteúdo, a [!UICONTROL Personalization Insights] Os relatórios do refletem somente um subsegmento de todo o tráfego distribuído pela atividade de AP ou AT. Especificamente, os dois relatórios refletem todo o tráfego que usou o modelo de personalização. Em outras palavras, [!UICONTROL Personalization Insights] Os relatórios do não consideram o tráfego de controle ou o tráfego distribuído pelo modelo vencedor global.

Dois [!UICONTROL Personalization Insights] Os relatórios do estão disponíveis:

| Relatório | Detalhes |
|--- |--- |
| [!UICONTROL Automated Segments] | Visitantes diferentes respondem de forma distinta às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados foram definidos pelo [!DNL Target] os modelos de personalização responderam às ofertas/experiências na atividade. |
| [!UICONTROL Important Attributes] | Em atividades diferentes, atributos distintos são mais ou menos importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa. |

## Interpretação de atributos em insights de personalização {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Há dois tipos de atributos representados no [!UICONTROL Personalization Insights] relatórios que são usados em seus modelos de AP ou de Direcionamento automático:

* **Atributos coletados automaticamente pelo Target:** [!DNL Target] O usa um conjunto de dados básico para criar seus algoritmos de personalização em atividades de AP e AT, que são refletidas nos Insights de personalização. Consulte [Coleta de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md) para tipos de dados, atributos de exemplo e seus [!UICONTROL Personalization Insights] convenção de nomenclatura. Observe que, embora esses atributos sejam considerados, os modelos de uma atividade individual podem não usar todos esses atributos no modelo final.
* **Atributos passados para o Target:** Consulte [Fazer upload de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target] O fornece várias maneiras de você transmitir dados adicionais para o [!DNL Target] para enriquecer o conjunto de dados básico usado para criar seus algoritmos de personalização em atividades de AP e AT:

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados |
|--- |--- |--- |
| Atributos de perfil, incluindo scripts de perfil, API de atualização do perfil e atributos de perfil na página | Qualquer informação que você decidiu incluir no perfil de usuário do Target.<br>Essas informações podem vir de scripts de perfil, de informações carregadas usando a API de atualização de perfil ou de parâmetros de perfil na mbox contendo o prefixo &quot;perfil&quot;. | `Custom - Profile - [parameter name]` |
| Parâmetros da página (também chamados de &quot;parâmetros de mbox&quot;) | Pares de nomes/valores passados diretamente pelo código de página, que não são armazenados no perfil do visitante para uso futuro. | `Custom - Mbox Parameter - [parameter name]` |
| Atributos do cliente | Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, aproveite os dados no Adobe Analytics e no Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Públicos-alvo compartilhados (Adobe Audience Manager ou Adobe Analytics) | Os públicos-alvo criados por meio do Adobe Audience Manager ou do Adobe Analytics e compartilhados com o Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Públicos-alvo compartilhados (Adobe Experience Platform/Real-time CDP) | Públicos-alvo criados por meio da Adobe Experience Platform/Real-time CDP e compartilhados com o Target via Destinos. | `Custom - Adobe Experience Platform Segment - [segment name]` |
| Atributos compartilhados (Adobe Experience Platform/Real-time CDP) | Atributos criados por meio da Adobe Experience Platform/Real-time CDP e compartilhados com o Target via Destinos. No momento, esse recurso está na versão beta. | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| Públicos-alvo/segmentos dos relatórios na atividade | Públicos-alvo definidos na atividade de AP ou Direcionamento automático durante a configuração em &quot;Metas e métricas&quot;. | `Custom - Reporting Segment - [segment name]` |

## Perguntas frequentes

Lista de perguntas frequentes sobre [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] [!UICONTROL Insights] relatórios.

### Por quanto tempo os dados duram [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] modelos persistem?

[!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] Os modelos do são treinados nos últimos 45 dias do comportamento do usuário (perfis de usuário, eventos de impressão e eventos de conversão) para a atividade.

[!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] Os modelos de retêm o comportamento do usuário, os registros de treinamento e os dados de decisão do modelo por 90 dias para produzir [!UICONTROL Insights] relatórios. Após 90 dias, os registros de treinamento e as decisões do modelo são descartados. [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] Os modelos do também retêm dados agregados de impressão e conversão de experiência/nível de oferta para fins de relatório por dois anos. Esses dados são somente dados de nível agregado e não contêm dados de perfil de nível individual.

## Vídeo de treinamento: uso de relatórios de Insights de personalização ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Para obter mais informações, consulte [Uso dos relatórios de insights de personalização no Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Blogs do Adobe

* Parte 1: [Como tirar o mistério da mágica da personalização orientada por IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Parte 2: [Uma espiada atrás da cortina de IA para personalização no Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Parte 3: [MAGIX — a solução para o problema da caixa preta da personalização orientada por IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
