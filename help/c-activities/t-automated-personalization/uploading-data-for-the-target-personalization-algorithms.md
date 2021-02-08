---
keywords: Automated Personalization;ap;upload de dados;dados offline;algoritmo de personalização;público alvo automático;público alvo automático;práticas recomendadas
description: Saiba como fazer upload de dados offline, como informações de CRM, ao criar modelos de personalização no Adobe Target Automated Personalization (AP) atividade.
title: Como posso carregar dados para algoritmos de personalização?
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 77%

---


# Carregar dados para os algoritmos de personalização do Target

Os dados offline, como informações de CRM ou pontuações de propensão de churn do cliente, podem ser incrivelmente valiosos ao criar modelos de personalização em [!DNL Adobe Target] [!UICONTROL Automated Personalization] (AP) atividades.

Há várias maneiras de inserir dados em algoritmos de [!UICONTROL Personalização automatizada] (AP) e [!UICONTROL Direcionamento automático. ] Além dos métodos em  [Métodos para inserir dados no Target](/help/c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17), os públicos-alvo compartilhados da Experience Cloud (Adobe Analytics, Gerenciamento de público-alvo) e os públicos-alvo de relatório na atividade também são utilizados em nossos algoritmos.

Para obter informações sobre os dados coletados e usados automaticamente pelos algoritmos de Personalização automatizada e Direcionamento automático, consulte [Coleção de dados de personalização automatizada](/help/c-activities/t-automated-personalization/ap-data.md).

## Práticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

A lista a seguir apresenta as práticas recomendadas para fazer o upload de dados para os algoritmos de personalização do Target:

* Quanto maior a quantidade de dados de alta qualidade disponíveis para os algoritmos de personalização do Target, melhor a qualidade dos modelos resultantes nas atividades de AP e Auto Target.
* Limite o uso de vários scripts de perfil ou atributos que atendem o mesmo propósito.
* Não transmita uma ID única, como uma ID de sessão, se não for necessário.
* Analise quais dados o Target coleta automaticamente (  [Coleta de dados para os algoritmos de personalização do Target](/help/c-activities/t-automated-personalization/ap-data.md)), de modo que você não envie informações duplicadas. Por exemplo, o Target usa endereços IP para determinar os códigos postais de visitantes. Não é necessário transmitir essas informações como uma variável separada.
* Não transmita vários valores no mesmo atributo/variável. Se várias variáveis estiverem concatenadas, os algoritmos de personalização do Target vão tratar cada cadeia de caracteres como um valor único, reduzindo o valor das informações da personalização.
* Use uma convenção de nomenclatura memorável e significativa para tornar seus  [Relatórios de insights de personalização](/help/c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mais fáceis de entender.

