---
keywords: qa, lado do servidor, lado do servidor, visualização, visualização de links
description: Saiba como usar as URLs de controle de qualidade do Adobe [!DNL Target] com entrega do lado do servidor para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.
title: Usar o Posso executar o controle de qualidade de atividade com entrega do lado do servidor?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: 'https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: 6efa6b7a-8062-5c41-aef4-b4853cc306ae
    internal-label: Activities
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0a683f6e68bb7481b9e45c91a275a46b84a1ffd8
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 18%
---
# Usar o controle de qualidade de atividade com entrega do lado do servidor {#qa-server-side}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como passar parâmetros de controle de qualidade de atividade em uma chamada [!DNL Adobe Target] do lado do servidor, para testar atividades quando `pageUrl` não estiver disponível.

>[!ENDSHADEBOX]

A implementação padrão do Controle de qualidade de atividade oferece suporte à passagem de `qa_mode` parâmetros por meio de `pageUrl` parâmetros. Essa abordagem é conveniente para chamadas [!DNL Target] padrão/ajax. No entanto, não é adequado para chamadas de servidor para servidor, como uma implementação do Mobile SDK, em que `pageUrl` não está disponível. Nesses casos, transmita os parâmetros de controle de qualidade na própria solicitação, que mantém os mesmos links de visualização, direcionamento opcional de público-alvo e relatórios de controle de qualidade segmentados a partir dos dados de atividade em tempo real.

O código a seguir mostra o Controle de qualidade de atividade em uma chamada do lado do servidor:

```json
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

A tabela a seguir descreve os parâmetros de uma solicitação do lado do servidor:

| Parâmetro | Tipo | Valor padrão | Descrição |
|--- |--- |--- |--- |
| token | Token criptografado | Nenhum. Não pode estar vazio. | Uma entidade criptografada que contém a lista de IDs de atividade que podem ser executadas no Controle de Qualidade da Atividade.<br>Regras de validação: o token deve ser um token criptografado pertencente ao cliente especificado na solicitação [!DNL Target]. Todas as atividades especificadas no token devem pertencer ao cliente. |
| bypassEntryAudience | Booleano | Falso | Especifica se os alvos da etapa de entrada para atividades de controle de qualidade são avaliados ou considerados correspondentes. |
| listedActivitiesOnly | Booleano | Falso | Especifica se as atividades de controle de qualidade são executadas isoladamente ou são avaliadas como atividades ativas para o ambiente atual. |
| evaluateAsTrueAudienceIds | Lista de IDs | Lista vazia | Lista de IDs de público que são sempre avaliadas como verdadeiras no escopo da solicitação [!DNL Target]. |
| evaluateAsFalseAudienceIds | Lista de IDs | Lista vazia | Lista de IDs de público que são sempre avaliadas como falsas no escopo da solicitação [!DNL Target]. |
| activityIndex | Número inteiro | Null. Não pode estar vazio. | O índice de atividade no token criptografado. Se `activityIndex` for nulo ou estiver fora dos limites das atividades no token, ele será ignorado. O índice começa com 1.<br>Regras de validação: pelo menos um índice de atividade é necessário e deve fazer referência a uma atividade especificada no token. |
| experienceIndex | Número inteiro | Null | Quando especificado, seleciona uma experiência por índice na definição da atividade. Se não especificado ou fora dos limites, ele retorna à estratégia de seleção de experiência da atividade. O índice começa com 1.<br>Regras de validação: o valor pode ser nulo ou deve fazer referência a uma experiência na atividade. |
