---
keywords: Automated Personalization;ap;carregar dados;dados offline;algoritmo de personalização;direcionamento automático;direcionamento automático;práticas recomendadas
description: Saiba como carregar dados offline, como informações de CRM, ao criar modelos de personalização no Adobe [!DNL Target] Atividades do Automated Personalization (AP).
title: Como posso fazer upload de dados para algoritmos de personalização?
feature: Automated Personalization
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 7c15a0795e94b6c6317cb5b4018899be71f03a40
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 37%

---

# Carregar dados para o [!DNL Target] algoritmos de personalização

Dados offline, como informações de CRM ou pontuações de propensão de churn do cliente, podem ser incrivelmente valiosos ao criar modelos de personalização no [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) atividades.

Há várias maneiras de inserir dados em algoritmos de [!UICONTROL Personalização automatizada] (AP) e [!UICONTROL Direcionamento automático. ] Além dos métodos em [Métodos para colocar os dados no Target](https://experienceleague.corp.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}, Experience Cloud shared audiences (Adobe Analytics, Audience Management){target=_blank} e os públicos-alvo de relatório na atividade também são usados em nossos algoritmos.

Para obter informações sobre os dados coletados e usados automaticamente pelos algoritmos de Personalização automatizada e Direcionamento automático, consulte [Coleção de dados de personalização automatizada](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Práticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

A lista a seguir apresenta as práticas recomendadas para fazer o upload de dados para os algoritmos de personalização do Target:

* Quanto mais dados de alta qualidade estiverem disponíveis para os algoritmos de personalização do Target, melhor será a qualidade dos modelos resultantes em suas atividades de AP e de Direcionamento automático.
* Limite o uso de vários scripts de perfil ou atributos que atendem o mesmo propósito.
* Não passe uma ID exclusiva, como uma ID de sessão, se não for necessária.
* Analise quais dados o Target coleta automaticamente ( [Coleta de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) para que você não envie informações duplicadas. Por exemplo, o Target usa endereços IP para determinar os códigos postais de visitantes. Não é necessário transmitir essas informações como uma variável separada.
* Não transmita vários valores no mesmo atributo/variável. Se várias variáveis forem concatenadas, os algoritmos de personalização do Target tratarão cada string como um valor único, reduzindo o valor das informações para personalização.
* Use uma convenção de nomenclatura memorável e significativa para tornar seus  [Relatórios de insights de personalização](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mais fáceis de entender.
