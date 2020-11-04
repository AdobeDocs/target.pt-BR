---
keywords: Targeting;AP reports;automated personalization reports;auto-target;auto target;auto target report;auto-target report;personalization;insights;automated segments;faq;frequently asked questions;important attributes
description: 'Dois relatórios especializados estão disponíveis para usuários de atividades de Personalização automatizada (AP) e Direcionamento automático (AT): os relatórios de Segmentos automatizados e atributos importantes.'
title: Relatórios de insights de personalização
feature: reports
uuid: 2507a7a6-d229-412a-a992-5777b45c80e7
translation-type: tm+mt
source-git-commit: 6278a01928fcb9dd0b34d7a8b5313f09f1e8da0f
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 71%

---


# ![PREMIUM](/help/assets/premium.png) Relatórios de insights de personalização{#personalization-insights-reports}

Dois relatórios especializados estão disponíveis para usuários de atividades de [!UICONTROL Automated Personalization] (AP) e Direcionamento automático (AT): os relatórios de [!UICONTROL Segmentos automatizados] e atributos importantes.

>[!NOTE]
>
>Considere o seguinte ao usar relatórios de Insights de personalização:
>
>* As atividades de AP e AT estão disponíveis como parte da solução [!DNL Target Premium]. Não estão incluídos com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium].
   >
   >
* [!UICONTROL Os relatórios de insights de personalização estão disponíveis apenas para atividades de AP e AT que usam uma meta de otimização de conversão. ] As atividades em que a meta de otimização foi alterada para a conversão da receita após a atividade já estar ativa também não são compatíveis.
   >
   >
* [!UICONTROL Os relatórios de Insights] de personalização estão disponíveis somente se o Objetivo  principal estiver selecionado na lista suspensa Métrica [!UICONTROL de] relatório.
   >
   >
* Os relatórios de insights de personalização são suportados somente no [ambiente padrão](../../administrating-target/hosts.md).
   >
   >
* [!UICONTROL Os relatórios de Insights] de personalização são gerados somente para atividades que estão no status [!UICONTROL Live] e foram ativados e recebem tráfego por pelo menos 15 dias.


## Visão geral dos relatórios de insights de personalização {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

O objetivo dos relatórios de [!UICONTROL insights de personalização] é fornecer mais informações sobre como os modelos de personalização do Target por trás de suas atividades de AP e AT personalizam o tráfego de visitantes.  The [Random Forest algorithm](/help/c-activities/t-automated-personalization/algo-random-forest.md) is the basis for the [!DNL Target] personalization models.

Because the goal of the [!UICONTROL Personalization Insights] reports is to understand how the [!DNL Target] personalization models decided to send which visitor to what piece(s) of content, the [!UICONTROL Personalization Insights] reports reflect only a sub-segment of all the traffic served by your AP or AT activity. Especificamente, os dois relatórios refletem todo o tráfego que usou o modelo de personalização. Ou seja, os relatórios de [!UICONTROL Insights de personalização] não consideram o tráfego de controle ou o tráfego distribuído pelo modelo vencedor global.

Dois relatórios de Insights [!UICONTROL de] personalização estão disponíveis:

| Relatório | Detalhes |
|--- |--- |
| [!UICONTROL Segmentos automatizados] | Visitantes diferentes respondem de forma distinta às ofertas/experiências na atividade de AP/AT. This report shows how different automated segments defined by the [!DNL Target] personalization models responded to the offers/experiences in the activity. |
| [!UICONTROL Atributos importantes] | Em atividades diferentes, atributos distintos são mais ou menos importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa. |

## Interpretação de atributos em insights de personalização {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Há dois tipos de atributos representados nos [!UICONTROL Insights de personalização] que são usados nos modelos de AP ou Direcionamento automático:

* **Atributos coletados automaticamente pelo :**[!DNL Target]o Target usa um conjunto de dados básico para criar seus algoritmos de personalização em atividades de AP e AT, que são refletidas nos Insights de personalização. Consulte [Coleta de dados para algoritmos de personalização do Target](/help/c-activities/t-automated-personalization/ap-data.md) para obter os tipos de dados, atributos de exemplo e sua convenção de nomenclatura do [!UICONTROL Insights de personalização]. Observe que, embora esses atributos sejam considerados, os modelos de uma atividade individual podem não usar todos esses atributos no modelo final.
* **Atributos passados para o Target:** consulte  [Fazer upload de dados para os algoritmos de personalização do Target](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target]O fornece muitas maneiras de passar os dados adicionais para o , a fim de enriquecer o conjunto de dados básico usado para criar seus algoritmos de personalização em atividades de AP e de AT:[!DNL Target]

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados |
|--- |--- |--- |
| Atributos de perfil, incluindo scripts de perfil, API de atualização do perfil e atributos de perfil na página | Qualquer informação que você decidiu incluir no perfil de usuário do Target.<br>Essas informações podem vir de scripts de perfil, de informações carregadas usando a API de atualização de perfil ou de parâmetros de perfil na mbox contendo o prefixo &quot;perfil&quot;. | `Custom - Profile - [parameter name]` |
| Parâmetros da página (também denominados &quot;parâmetros de mbox&quot;) | Pares de nomes/valores passados diretamente pelo código de página, que não são armazenados no perfil do visitante para uso futuro. | `Custom - Mbox Parameter - [parameter name]` |
| Atributos do cliente | Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, aproveite os dados no Adobe Analytics e no Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Públicos-alvo compartilhados (Adobe Audience Manager ou Adobe Analytics) | Os públicos-alvo criados por meio do Adobe Audience Manager ou do Adobe Analytics e compartilhados com o Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Públicos-alvo/segmentos dos relatórios na atividade | Os públicos-alvo definidos na atividade de AP ou de Direcionamento automático durante a configuração nas &quot;Metas e métricas&quot;. | `Custom - Reporting Segment - [segment name]` |

## Vídeo de treinamento: Uso de relatórios de insights de personalização ![Crachá do tutorial](/help/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Para obter mais informações, consulte [Uso dos relatórios de insights de personalização no Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Blogs Adobe

* Parte 1: [Tirando o mistério da mágica da personalização acionada por IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Parte 2: [Uma espiada atrás da cortina do AI para personalização no Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Parte 3: [MAGIX — a solução para o problema da caixa preta da personalização acionada por AI](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
