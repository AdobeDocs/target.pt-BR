---
keywords: Automated Personalization;ap;carregar dados;dados offline;algoritmo de personalização;direcionamento automático;direcionamento automático;práticas recomendadas
description: Saiba como fazer upload de dados offline ao criar modelos de personalização no [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] atividades.
title: Como posso fazer upload de dados para algoritmos de personalização?
feature: Automated Personalization, Auto-Target
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
exl-id: c750e0e5-8ebd-49a2-9705-05f593aaf0b9
source-git-commit: 3f64da1c9a1146e4d2d9389d6d5ce764764d2d9c
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 25%

---

# Carregar dados para o [!DNL Target] algoritmos de personalização

Dados offline, como informações de CRM ou pontuações de propensão de churn do cliente, podem ser incrivelmente valiosos ao criar modelos de personalização no [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] atividades.

Há várias maneiras de inserir dados em algoritmos de [!UICONTROL Personalização automatizada] (AP) e [!UICONTROL Direcionamento automático. ] Além dos métodos em [Métodos para colocar os dados no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html){target=_blank}, [!DNL Experience Cloud] públicos-alvo compartilhados ([!UICONTROL Adobe Analytics], [!DNL Audience Manager]), e os públicos-alvo do relatório na atividade também são usados no [!DNL Target] algoritmos.

Para obter informações sobre os dados coletados e usados automaticamente pelos [!UICONTROL algoritmos de Personalização automatizada] e [!UICONTROL Direcionamento automático], consulte [Coleta de dados de personalização automatizada](/help/main/c-activities/t-automated-personalization/ap-data.md).

## Práticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

A lista a seguir apresenta as práticas recomendadas para o upload de dados do [!DNL Target] algoritmos de personalização:

* Quanto mais dados de alta qualidade estiverem disponíveis para [!DNL Target] algoritmos de personalização, quanto melhor a qualidade dos modelos resultantes em seu [!UICONTROL Automated Personalization] e [!UICONTROL Direcionamento automático] atividades.
* Limite o uso de vários scripts de perfil ou atributos que atendem o mesmo propósito.
* Não passe uma ID exclusiva, como uma ID de sessão, se não for necessária.
* Analisar quais dados [!DNL Target] coleta automaticamente ( [Coleta de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md)) para que você não envie informações duplicadas. Por exemplo, [!DNL Target] O usa endereços IP para determinar os códigos postais dos visitantes. Não é necessário transmitir essas informações como uma variável separada.
* Não transmita vários valores no mesmo atributo ou variável. Se várias variáveis forem concatenadas, [!DNL Target] os algoritmos de personalização tratam cada string como um valor único, reduzindo o valor das informações para personalização.
* Use uma convenção de nomenclatura memorável e significativa para tornar seus  [Relatórios de insights de personalização](/help/main/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mais fáceis de entender.
