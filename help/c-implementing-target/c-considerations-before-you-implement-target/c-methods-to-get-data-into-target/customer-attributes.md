---
keywords: implementar; implementação; configuração; configuração; atributos do cliente
description: Obtenha dados em [!DNL Target] usando atributos do cliente.
title: Como obtenho dados no [!DNL Target] usando atributos do cliente?
feature: Implementação
role: Developer
exl-id: b6c4a286-7994-492d-bde9-346af7aa314f
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 56%

---

# Atributos do cliente

Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à [!DNL Adobe Experience Cloud]. Após o upload, use os dados em [!DNL Adobe Analytics] e [!DNL Adobe Target].

Os clientes do Target Standard podem aplicar cinco atributos, os clientes do Target Premium podem aplicar 200 atributos.

## Formato

Um arquivo .csv com Experience Cloud IDs (ECIDs) e os pares de nome/valor de atributo são carregados por FTP ou manualmente na interface de usuário da Experience Cloud.

## Exemplo de casos de uso

Seu CRM ou outros sistemas internos armazenam informações valiosas que deseja compartilhar com a Adobe Experience Cloud, incluindo Target e Analytics.

## Benefícios do método

Carregar os dados do cliente cria uma entrada de perfil para que o visitante no Target, mesmo se o Target ainda precisar visualizar o visitante.

Os mesmos dados estão automaticamente disponíveis no Target e no Analytics.

O FTP pode ser um método de implementação mais simples que a API.

## Avisos

Os clientes do Target Standard podem aplicar cinco atributos, os clientes do Target Premium podem aplicar 200 atributos

Podem atualizar valores via Atributos do cliente, não nas páginas.

Requer a implementação da Experience Cloud ID (ECID).

## Exemplos de código

Os detalhes podem ser encontrados em [Criar uma fonte de atributo do cliente e fazer upload do arquivo de dados](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Links para informações relevantes

[Crie uma fonte de atributo do cliente e faça upload do arquivo de dados](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).
