---
keywords: Automated Personalization;ap;carregar dados;dados offline;algoritmo de personalização;direcionamento automático;direcionamento automático;práticas recomendadas
description: Saiba como carregar dados offline ao criar modelos de personalização nas atividades de  [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático].
title: Como posso fazer upload de dados para algoritmos do Personalization?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
TQID: https://experienceleague.adobe.com/B1vwWrii4DfQzXftwcmgzbhBkDAZFo5mDRn3a7dULj0
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 323
ht-degree: 12%

---

# Carregar dados para os algoritmos de personalização do [!DNL Target]

Dados offline, como informações de CRM ou pontuações de propensão de churn do cliente, podem ser extremamente valiosos na criação de modelos de personalização nas atividades de [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático].

Há várias maneiras de inserir dados em algoritmos de personalização do [!UICONTROL Automated Personalization] (AP) e do [!UICONTROL Direcionamento automático]. Além dos métodos em [Métodos para obter dados no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}, [!DNL Experience Cloud] públicos-alvo compartilhados ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]) e públicos-alvo de relatório na atividade também são usados em algoritmos [!DNL Target].

Para obter informações sobre os dados coletados e usados automaticamente pelos [!UICONTROL algoritmos de personalização do Automated Personalization] e do [!UICONTROL Direcionamento automático], consulte [Coleta de Dados do Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Práticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

A lista a seguir apresenta as práticas recomendadas para carregar dados para algoritmos de personalização do [!DNL Target]:

* Quanto mais dados de alta qualidade estiverem disponíveis para os algoritmos de personalização do [!DNL Target], melhor será a qualidade dos modelos resultantes nas suas atividades do [!UICONTROL Automated Personalization] e do [!UICONTROL Direcionamento automático].
* Limite o uso de vários scripts de perfil ou atributos que atendem o mesmo propósito.
* Não passe uma ID exclusiva, como uma ID de sessão, se não for necessária.
* Revise quais dados [!DNL Target] coletam automaticamente ( [Coleta de dados para os algoritmos Personalization do Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) para que você não envie informações duplicadas. Por exemplo, [!DNL Target] usa endereços IP para determinar os códigos postais de visitantes. Não é necessário transmitir essas informações como uma variável separada.
* Não transmita vários valores no mesmo atributo ou variável. Se várias variáveis forem concatenadas, os algoritmos de personalização do [!DNL Target] tratarão cada cadeia de caracteres como um valor único, reduzindo o valor das informações para personalização.
* Use uma convenção de nomenclatura memorável e significativa para tornar seus [Relatórios do Personalization Insights](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mais compreensíveis.
