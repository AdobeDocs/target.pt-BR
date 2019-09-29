---
description: 'Dois relatórios especializados estão disponíveis para usuários de atividades de Personalização automatizada (AP) e Direcionamento automático (AT): os relatórios de Segmentos automatizados e atributos importantes.'
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, direcionamento automático, direcionamento automático, relatório do direcionamento automático, relatório de direcionamento automático, personalização, insights, segmentos automatizados, perguntas frequentes, perguntas frequentes, atributos importantes
seo-description: 'Dois relatórios especializados estão disponíveis para usuários de atividades de Personalização automatizada (AP) e Direcionamento automático (AT): os relatórios de Segmentos automatizados e atributos importantes.'
seo-title: Relatórios de insights de personalização
solution: Target
title: Relatórios de insights de personalização
title-outputclass: premium
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
badge: premium
translation-type: tm+mt
source-git-commit: c0d0ae6bcd401777169e74b93a4fb18f1a9b24dc

---


# ![PREMIUM](/help/assets/premium.png) Relatórios de insights de personalização{#personalization-insights-reports}

Dois relatórios especializados estão disponíveis para usuários de atividades de Automated Personalization (AP) e Direcionamento automático (AT): os relatórios de segmentos automatizados e atributos importantes.

>[!NOTE]
>
>As atividades de AP e AT estão disponíveis como parte da solução [!DNL Target Premium]. Não estão incluídos com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium].
>
>Os relatórios de insights de personalização estão disponíveis apenas para atividades de AP e AT que usam uma meta de otimização de conversão. As atividades em que a meta de otimização foi alterada para a conversão da receita após a atividade já estar ativa também não são compatíveis.
>
>Os relatórios de insights de personalização são suportados somente no [ambiente padrão](../../administrating-target/hosts.md).
>
>Os relatórios de Insights de Personalização são gerados somente para atividades que estão no status Online e foram ativados e recebem tráfego por pelo menos 15 dias.

## Visão geral dos relatórios de insights de personalização {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

O objetivo dos relatórios de [!UICONTROL insights de personalização] é fornecer mais informações sobre como os modelos de personalização do Target por trás de suas atividades de AP e AT personalizam o tráfego de visitantes. O [algoritmo Random Forest](/help/c-activities/t-automated-personalization/algo-random-forest.md) é a base para os modelos de personalização do Target.

Como a meta dos relatórios de Insights de personalização é entender como os modelos de personalização do Target decidiram enviar qual visitante para que parte do conteúdo, os relatórios de Insights de personalização refletem apenas um subsegmento de todo o tráfego distribuído pela atividade de AP ou AT. Especificamente, os dois relatórios refletem todo o tráfego que usou o modelo de personalização. Ou seja, os relatórios de Insights de personalização não consideram o tráfego de controle ou o tráfego distribuído pelo modelo vencedor global.

Dois relatórios de insights de personalização estão disponíveis:

| Relatório | Detalhes |
|--- |--- |
| Segmentos automatizados | Visitantes diferentes respondem de forma distinta às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade. |
| Atributos importantes | Em atividades diferentes, atributos distintos são mais ou menos importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa. |

## Interpretação de atributos em insights de personalização {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Há dois tipos de atributos representados nos [!UICONTROL Insights de personalização] que são usados nos modelos de AP ou Direcionamento automático:

* **Atributos coletados automaticamente pelo Target:** o Target usa um conjunto de dados básico para criar seus algoritmos de personalização em atividades de AP e AT, que são refletidas nos Insights de personalização. Consulte [Coleta de dados para algoritmos de personalização do Target](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058) para obter os tipos de dados, atributos de exemplo e sua convenção de nomenclatura do [!UICONTROL Insights de personalização]. Observe que, embora esses atributos sejam considerados, os modelos de uma atividade individual podem não usar todos esses atributos no modelo final.
* **Atributos passados para o Target:** consulte [Fazer upload de dados para os algoritmos de personalização do Target](../../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

O Target fornece muitas maneiras de passar os dados adicionais para o Target, a fim de enriquecer o conjunto de dados básico usado para criar seus algoritmos de personalização em atividades de AP e de AT:

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados |
|--- |--- |--- |
| Atributos de perfil, incluindo scripts de perfil, API de atualização do perfil e atributos de perfil na página | Qualquer informação que você decidiu incluir no perfil de usuário do Target.<br>Essas informações podem vir de scripts de perfil, de informações carregadas usando a API de atualização de perfil ou de parâmetros de perfil na mbox contendo o prefixo "perfil". | `Custom - Profile - [parameter name]` |
| Parâmetros da página (também denominados "parâmetros de mbox") | Pares de nomes/valores passados diretamente pelo código de página, que não são armazenados no perfil do visitante para uso futuro. | `Custom - Mbox Parameter - [parameter name]` |
| Atributos do cliente | Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, aproveite os dados no Adobe Analytics e no Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Públicos-alvo compartilhados (Adobe Audience Manager ou Adobe Analytics) | Os públicos-alvo criados por meio do Adobe Audience Manager ou do Adobe Analytics e compartilhados com o Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Públicos-alvo/segmentos dos relatórios na atividade | Os públicos-alvo definidos na atividade de AP ou de Direcionamento automático durante a configuração nas "Metas e métricas". | `Custom - Reporting Segment - [segment name]` |

## Vídeo de treinamento: Uso de relatórios de insights de personalização

>[!VIDEO](https://video.tv.adobe.com/v/25601/?captions=por_br)

Para obter mais informações, consulte [Uso dos relatórios de insights de personalização no Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).
