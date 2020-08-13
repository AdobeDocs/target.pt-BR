---
keywords: qa;server side;server-side;preview;preview links
description: Use URLs de controle de qualidade com entrega do lado do servidor para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.
title: Usar o controle de qualidade de atividade com entrega do lado do servidor
feature: qa
topic: Advanced,Standard,Classic
uuid: c1875243-e37f-4205-9e6b-6e96cadf4a7f
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 88%

---


# Usar o controle de qualidade de atividade com entrega do lado do servidor{#use-activity-qa-with-server-side-delivery}

Use URLs de controle de qualidade com entrega do lado do servidor para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.

A implementação padrão do Controle de qualidade de atividade é compatível com a transferência de parâmetros `qa_mode` por meio de parâmetros `pageUrl`. This approach is convenient for standard/ajax [!DNL Target] calls. No entanto, para chamadas de servidor para servidor, isso não é a melhor abordagem para um caso SDK do Adobe Mobile, quando `pageUrl` não está disponível.

O código a seguir mostra o Controle de qualidade de atividade em uma chamada do lado do servidor:

```
{
  "mbox" : "orderConfirmPage",
  "clientSideAnalyticsLogging": true,
  "clicked" : true,
  "tntId" : "12121212.17_01",
  "order" : {
    ...
  },
  "profileParameters" : {
    ...
  },
  "mboxParameters" : {
    ...
  },
  "requestLocation" : {
    ...
  },
  "qaMode" : {
    "token" : "<encrypted token string>",
    "bypassEntryAudience" : true,
    "listedActivitiesOnly" : true,
    "evaluateAsTrueAudienceIds" : [audienceId1, audienceId2...],
    "evaluateAsFalseAudienceIds" : [audienceId3, audienceId4...],
    "previewIndexes" : [
       {
         "activityIndex" : 1,
         "experienceIndex" : 1
       }
     ],
  },
  "mboxTrace" : true
}
```

A tabela a seguir explica os detalhes da solicitação do lado do servidor:

| Parâmetro | Tipo | Valor padrão | Descrição |
|--- |--- |--- |--- |
| token | Token criptografado | Nenhum.<br>Não pode estar em branco. | Uma entidade criptografada que contém a lista de IDs de atividade que podem ser executadas no Controle de qualidade de atividade.<br>[!DNL Target]Regras de validação: deve ser um token criptografado pertencente ao cliente especificado na solicitação Todas as atividades especificadas no token devem pertencer ao cliente. |
| bypassEntryAudience | Booleano | Falso | Especifica se os direcionamentos de etapas de entrada de atividades de controle de qualidade devem ser avaliados ou se devem ser considerados como correspondentes. |
| listedActivitiesOnly | Booleano | Falso | Especifica se as atividades de QA devem ser executadas isoladamente ou se devem ser avaliadas como atividades ativas para o ambiente atual. |
| evaluateAsTrueAudienceIds | Lista de IDs | Lista vazia. | List of audience IDs that should always be evaluated as true in the scope of the [!DNL Target] request. |
| evaluateAsFalseAudienceIds | Lista de IDs | Lista vazia. | List of audience IDs that should always be evaluated as false in the scope of the [!DNL Target] request. |
| activityIndex | Número inteiro | Nulo.<br>Não pode estar em branco. | O índice de atividade no token criptografado. Se activityIndex estiver fora dos limites da atividade no token ou se for nulo, ele será ignorado. O índice começa com 1.<br>Regras de validação: deve ter pelo menos um índice de atividade e deve fazer referência a uma atividade especificada no token. |
| experienceIndex | Número inteiro | Nulo. | Quando especificado, seleciona uma experiência por índice na definição da atividade. Se não especificado ou fora dos limites, ele retornará à estratégia de seleção de experiência da atividade. Regras de validação - O índice começa com 1: podem ser nulas ou devem fazer referência a uma experiência na atividade. |