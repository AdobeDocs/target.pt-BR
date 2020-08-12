---
description: Dados offline, como informações de CRM ou pontuações de tendência de perda de clientes, podem ser extremamente valiosos ao criar modelos de personalização.
title: Upload de dados para os algoritmos de personalização do Target
feature: null
uuid: eb0938b9-7f35-4bb5-ac4b-260b2144db5b
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 100%

---


# Carregar dados para os algoritmos de personalização do Target{#upload-data-for-target-s-personalization-algorithms}

Dados offline, como informações de CRM ou pontuações de tendência de perda de clientes, podem ser extremamente valiosos ao criar modelos de personalização.

Há várias maneiras de inserir dados em algoritmos de Personalização automatizada (AP) e Direcionamento automático. Além dos métodos em  [Métodos para inserir dados no Target](../../c-implementing-target/c-considerations-before-you-implement-target/c-methods-to-get-data-into-target/methods-to-get-data-into-target.md#concept_0069C0EFB56C4700BB33F2F35C2B9B17), os públicos-alvo compartilhados da Experience Cloud (Adobe Analytics, Gerenciamento de público-alvo) e os públicos-alvo de relatório na atividade também são utilizados em nossos algoritmos.

Para obter informações sobre os dados coletados e usados automaticamente pelos algoritmos de Personalização automatizada e Direcionamento automático, consulte [Coleção de dados de personalização automatizada](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

## Práticas recomendadas {#section_DE96C7B7D114491DBB67FB5B7DA3D37B}

A lista a seguir apresenta as práticas recomendadas para fazer o upload de dados para os algoritmos de personalização do Target:

* Quanto maior a quantidade de dados de alta qualidade disponíveis para os algoritmos de personalização do Target, melhor a qualidade dos modelos resultantes nas atividades de AP e Auto Target.
* Limite o uso de vários scripts de perfil ou atributos que atendem o mesmo propósito.
* Não transmita uma ID única, como uma ID de sessão, se não for necessário.
* Analise quais dados o Target coleta automaticamente (  [Coleta de dados para os algoritmos de personalização do Target](../../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058)), de modo que você não envie informações duplicadas. Por exemplo, o Target usa endereços IP para determinar os códigos postais de visitantes. Não é necessário transmitir essas informações como uma variável separada.
* Não transmita vários valores no mesmo atributo/variável. Se várias variáveis estiverem concatenadas, os algoritmos de personalização do Target vão tratar cada cadeia de caracteres como um valor único, reduzindo o valor das informações da personalização.
* Use uma convenção de nomenclatura memorável e significativa para tornar seus  [Relatórios de insights de personalização](../../c-reports/c-personalization-insights-reports/personalization-insights-reports.md#concept_A897070E1EDC403EB84CFB7A6ECAD767) mais fáceis de entender.

