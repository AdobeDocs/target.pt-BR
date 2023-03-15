---
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, direcionamento automático, direcionamento automático, relatório do direcionamento automático, relatório de direcionamento automático, personalização, insights, segmentos automatizados, perguntas frequentes, perguntas frequentes, atributos importantes
description: Saiba como usar os relatórios especializados para atividades de Automated Personalization (AP) e Direcionamento automático (AT) - Segmentos automatizados e atributos importantes.
title: Como uso os relatórios de insights de personalização?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 89295d95-f179-4277-ae63-453350e1bba8
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '908'
ht-degree: 51%

---

# Relatórios de insights de personalização

Dois relatórios especializados estão disponíveis para usuários de atividades de [!UICONTROL Automated Personalization] (AP) e Direcionamento automático (AT): os relatórios de [!UICONTROL Segmentos automatizados] e atributos importantes.

>[!NOTE]
>
>Considere o seguinte ao usar os relatórios dos Insights de personalização:
>
>* As atividades de AP e AT estão disponíveis como parte da solução [!DNL Target Premium]. Não estão incluídos com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium].
>
>* [!UICONTROL Os relatórios de insights de personalização estão disponíveis apenas para atividades de AP e AT que usam uma meta de otimização de conversão. ] As atividades em que a meta de otimização foi alterada para a conversão da receita após a atividade já estar ativa também não são compatíveis.
>
>* [!UICONTROL Insights de personalização] os relatórios só estarão disponíveis se a variável [!UICONTROL Meta principal] é selecionado no [!UICONTROL Métrica de relatório] lista suspensa.
>
>* Os relatórios de insights de personalização são suportados somente no [ambiente padrão](/help/main/administrating-target/hosts.md).
>
>* [!UICONTROL Insights de personalização] são gerados somente para atividades que estão no [!UICONTROL Ao vivo] e foram ativadas e recebem tráfego por pelo menos 15 dias.


## Visão geral dos relatórios de insights de personalização {#section_B47CD4A50FEB43D587F9FACD9FFD6D9D}

O objetivo dos relatórios de [!UICONTROL insights de personalização] é fornecer mais informações sobre como os modelos de personalização do Target por trás de suas atividades de AP e AT personalizam o tráfego de visitantes.  O [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) é a base para o [!DNL Target] modelos de personalização.

Porque o objetivo da [!UICONTROL Insights de personalização] para entender como a função [!DNL Target] os modelos de personalização decidiram enviar qual visitante para que parte do conteúdo, a variável [!UICONTROL Insights de personalização] Os relatórios refletem apenas um subsegmento de todo o tráfego distribuído pela atividade de AP ou AT. Especificamente, os dois relatórios refletem todo o tráfego que usou o modelo de personalização. Ou seja, os relatórios de [!UICONTROL Insights de personalização] não consideram o tráfego de controle ou o tráfego distribuído pelo modelo vencedor global.

Dois [!UICONTROL Insights de personalização] os relatórios estão disponíveis:

| Relatório | Detalhes |
|--- |--- |
| [!UICONTROL Segmentos automatizados] | Visitantes diferentes respondem de forma distinta às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados foram definidos pela variável [!DNL Target] modelos de personalização responderam às ofertas/experiências na atividade. |
| [!UICONTROL Atributos importantes] | Em atividades diferentes, atributos distintos são mais ou menos importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa. |

## Interpretação de atributos em insights de personalização {#section_B5C45E723EC941BDA2A7A642EEB30E4D}

Há dois tipos de atributos representados nos [!UICONTROL Insights de personalização] que são usados nos modelos de AP ou Direcionamento automático:

* **Atributos coletados automaticamente pelo :**[!DNL Target]o Target usa um conjunto de dados básico para criar seus algoritmos de personalização em atividades de AP e AT, que são refletidas nos Insights de personalização. Consulte [Coleta de dados para algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md) para obter os tipos de dados, atributos de exemplo e sua convenção de nomenclatura do [!UICONTROL Insights de personalização]. Observe que, embora esses atributos sejam considerados, os modelos de uma atividade individual podem não usar todos esses atributos no modelo final.
* **Atributos passados para o Target:** Consulte [Fazer upload de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

[!DNL Target]O fornece muitas maneiras de passar os dados adicionais para o , a fim de enriquecer o conjunto de dados básico usado para criar seus algoritmos de personalização em atividades de AP e de AT:[!DNL Target]

| Tipo de dados | Descrição | Convenção de nomenclatura do tipo de dados |
|--- |--- |--- |
| Atributos de perfil, incluindo scripts de perfil, API de atualização do perfil e atributos de perfil na página | Qualquer informação que você decidiu incluir no perfil de usuário do Target.<br>Essas informações podem vir de scripts de perfil, de informações carregadas usando a API de atualização de perfil ou de parâmetros de perfil na mbox contendo o prefixo &quot;perfil&quot;. | `Custom - Profile - [parameter name]` |
| Parâmetros da página (também denominados &quot;parâmetros de mbox&quot;) | Pares de nomes/valores passados diretamente pelo código de página, que não são armazenados no perfil do visitante para uso futuro. | `Custom - Mbox Parameter - [parameter name]` |
| Atributos do cliente | Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, aproveite os dados no Adobe Analytics e no Adobe Target. | `Custom - Customer Attributes - [parameter name]` |
| Públicos-alvo compartilhados (Adobe Audience Manager ou Adobe Analytics) | Os públicos-alvo criados por meio do Adobe Audience Manager ou do Adobe Analytics e compartilhados com o Target. | `Custom - Experience Cloud Segment - [segment name]` |
| Públicos-alvo compartilhados (Adobe Experience Platform/CDP em tempo real) | Públicos-alvo criados por meio da CDP em tempo real da Adobe Experience Platform e compartilhados com o Target via Destinos. | `Custom - Adobe Experience Platform Segment - [segment name]` |
| Atributos compartilhados (Adobe Experience Platform/CDP em tempo real) | Atributos criados por meio da CDP em tempo real da Adobe Experience Platform e compartilhados com o Target via Destinos. Esse recurso está atualmente na versão beta. | `Custom - Adobe Experience Platform Attribute - [attribute name]]` |
| Públicos-alvo/segmentos dos relatórios na atividade | Públicos-alvo definidos na atividade de AP ou de Direcionamento automático durante a configuração em &quot;Metas e métricas&quot;. | `Custom - Reporting Segment - [segment name]` |

## Perguntas frequentes

Lista de perguntas frequentes sobre [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] [!UICONTROL Insights] relatórios.

### Por quanto tempo os dados para modelos de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] persistem?

[!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] Os modelos são treinados nos últimos 45 dias de comportamento do usuário (perfis de usuário, eventos de impressão e eventos de conversão) para a atividade.

[!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] os modelos mantêm o comportamento do usuário, os registros de treinamento e os dados de decisão do modelo por 90 dias para produzir [!UICONTROL Insights] relatórios. Após 90 dias, os registros de treinamento e as decisões do modelo são descartados. [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] Os modelos também mantêm dados agregados de experiência/impressão de nível de oferta e conversão para fins de relatório por dois anos. Esses dados são apenas dados a nível de agregação e não contêm dados de perfil de nível individual.

## Vídeo de treinamento: Uso dos relatórios de insights de personalização ![Selo do tutorial](/help/main/assets/tutorial.png)

>[!VIDEO](https://video.tv.adobe.com/v/25601/)

Para obter mais informações, consulte [Uso dos relatórios de insights de personalização no Adobe Target](https://helpx.adobe.com/target/kt/using/personalization-insights-report-feature-video-use.html).

## Blogs Adobe

* Parte 1: [Tirando o mistério da mágica da personalização orientada por IA](https://theblog.adobe.com/taking-mystery-magic-ai-driven-personalization-part-1/)
* Parte 2: [Uma espiada por trás da cortina de IA para personalização no Adobe Target](https://theblog.adobe.com/a-peek-behind-the-curtain-of-ai-for-personalization-in-adobe-target/)
* Parte 3: [MAGIX — a solução para a edição do Black Box de personalização baseada em IA](https://theblog.adobe.com/magix-the-solution-to-the-black-box-issue-of-ai-driven-personalization/)
