---
keywords: Automated Personalization;ap;carregar dados;dados offline;algoritmo de personalização;direcionamento automático;direcionamento automático;práticas recomendadas
description: Saiba como carregar dados offline ao criar modelos de personalização nas atividades  [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target].
title: Como posso fazer upload de dados para algoritmos do Personalization?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 10%

---

# Carregar dados para os algoritmos de personalização do [!DNL Target]

Dados offline, como informações do CRM ou pontuações de propensão de churn do cliente, podem ser incrivelmente valiosos ao criar modelos de personalização em [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] atividades.

Há várias maneiras de inserir dados em algoritmos de personalização do [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target]. Além dos métodos em [Métodos para obter dados no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}, [!DNL Experience Cloud] públicos-alvo compartilhados ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) e públicos-alvo de relatório na atividade também são usados em algoritmos [!DNL Target].

Para obter informações sobre os dados coletados e usados automaticamente pelos algoritmos de personalização [!UICONTROL Automated Personalization] e [!UICONTROL Auto-Target], consulte [Coleção de dados do Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Práticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

A lista a seguir apresenta as práticas recomendadas para carregar dados para algoritmos de personalização do [!DNL Target]:

* Quanto mais dados de alta qualidade estiverem disponíveis para os algoritmos de personalização do [!DNL Target], melhor será a qualidade dos modelos resultantes nas suas atividades do [!UICONTROL Automated Personalization] e do [!UICONTROL Auto-Target].
* Limite o uso de vários scripts de perfil ou atributos que atendem o mesmo propósito.
* Não passe uma ID exclusiva, como uma ID de sessão, se não for necessária.
* Revise quais dados [!DNL Target] coletam automaticamente ( [Coleta de dados para os algoritmos Personalization do Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) para que você não envie informações duplicadas. Por exemplo, [!DNL Target] usa endereços IP para determinar os códigos postais de visitantes. Não é necessário transmitir essas informações como uma variável separada.
* Não transmita vários valores no mesmo atributo ou variável. Se várias variáveis forem concatenadas, os algoritmos de personalização do [!DNL Target] tratarão cada cadeia de caracteres como um valor único, reduzindo o valor das informações para personalização.
* Use uma convenção de nomenclatura memorável e significativa para tornar seus [Relatórios do Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mais compreensíveis.
