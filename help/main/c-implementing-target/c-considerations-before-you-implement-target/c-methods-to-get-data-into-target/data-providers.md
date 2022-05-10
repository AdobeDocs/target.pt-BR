---
keywords: implementar; implementação; configuração; configurar; provedores de dados
description: Obter dados em [!DNL Target] uso de provedores de dados.
title: Como obter dados sobre [!DNL Target] Usando provedores de dados?
feature: Implementation
role: Developer
exl-id: 05fe9190-4d36-43e2-9fc7-c354a6821bfb
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 67%

---

# Provedores de dados

Os provedores de dados são um recurso que permite que você transfira dados de terceiros facilmente para o [!DNL Adobe Target].

Observação: Os provedores de dados exigem a at.js 1.3 ou posterior.

## Formato

A configuração `window.targetGlobalSettings.dataProviders` é uma matriz de provedores de dados.

Para obter mais informações sobre a estrutura de cada provedor de dados, consulte [Provedores de dados](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

## Exemplo de casos de uso

Colete dados de terceiros, como um serviço meteorológico, um DMP ou até mesmo seu próprio serviço da Web. É possível então usar esses dados para criar públicos-alvo, conteúdo de direcionamento e enriquecer o perfil do visitante.

## Benefícios do método

Essa configuração permite que clientes reúnam dados de provedores de dados de terceiros, como Demandbase, BlueKai e serviços personalizados, além de enviar os dados ao Target como parâmetros da mbox na solicitação global da mbox.

Ela é compatível com a coleta de dados de múltiplos provedores via solicitações síncronas e assíncronas.

Usar esta abordagem facilita o gerenciamento de cintilação ou conteúdo padrão da página, enquanto inclui tempos limites independentes para cada provedor para limitar o impacto sobre o desempenho da página

## Avisos

Se os provedores de dados tiverem sido adicionados a `window.targetGlobalSettings.dataProviders` são assíncronas, são executadas em paralelo. A solicitação da API de visitante é executada em paralelo com funções adicionadas a `window.targetGlobalSettings.dataProviders` para permitir um tempo mínimo de espera.

A at.js não tenta armazenar os dados em cache. Se o provedor de dados obtiver os dados apenas uma vez, deverá certificar-se de que os dados estão armazenados em cache e, quando a função de provedor for invocada, servir os dados do cache para a segunda invocação.

## Exemplos de código

Vários exemplos podem ser encontrados em [Provedores de dados](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

## Links para informações relevantes

Documentação: [Provedores de dados](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

## Vídeos de treinamento:

* [Uso de provedores de dados do Adobe Target](https://helpx.adobe.com/br/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implementação de provedores de dados no Adobe Target](https://helpx.adobe.com/br/target/kt/using/dataProviders-atjs-technical-video-implement.html)