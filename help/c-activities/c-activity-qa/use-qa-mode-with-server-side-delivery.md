---
keywords: qa;server side;server-side;preview;preview links
description: Use os URLs de QA da Adobe Target com delivery do lado do servidor para realizar um controle de qualidade de atividade completo e fácil com links de pré-visualização que nunca mudam, direcionamento opcional de audiência e relatórios de controle de qualidade que permaneça segmentado dos dados de atividade ativa.
title: Usar o controle de qualidade de atividade com entrega do lado do servidor
feature: Activities
translation-type: tm+mt
source-git-commit: 1c5fd1062da5f90f24720fc3deb67f7f3b05aee9
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 72%

---


# Usar o controle de qualidade de atividade com entrega do lado do servidor

Use URLs de QA com delivery do lado do servidor em [!DNL Adobe Target] para realizar um controle de qualidade de atividade completo e fácil com links de pré-visualização que nunca mudam, direcionamento de audiência opcional e relatórios de controle de qualidade que permaneça segmentado dos dados de atividade ativa.

A implementação padrão do Controle de qualidade de atividade é compatível com a transferência de parâmetros `qa_mode` por meio de parâmetros `pageUrl`. Essa abordagem é conveniente para chamadas padrão/ajax [!DNL Target]. No entanto, para chamadas de servidor para servidor, isso não é a melhor abordagem para um caso SDK do Adobe Mobile, quando `pageUrl` não está disponível.

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

A tabela a seguir explica os detalhes da solicitação do lado do servidor:

| Parâmetro | Tipo | Valor padrão | Descrição |
|--- |--- |--- |--- |
| token | Token criptografado | Nenhum.<br>Não pode estar em branco. | Uma entidade criptografada que contém a lista de IDs de atividade que podem ser executadas no Controle de qualidade de atividade.<br>[!DNL Target]Regras de validação: deve ser um token criptografado pertencente ao cliente especificado na solicitação Todas as atividades especificadas no token devem pertencer ao cliente. |
| bypassEntryAudience | Booleano | Falso | Especifica se os direcionamentos de etapas de entrada de atividades de controle de qualidade devem ser avaliados ou se devem ser considerados como correspondentes. |
| listedActivitiesOnly | Booleano | Falso | Especifica se as atividades de QA devem ser executadas isoladamente ou se devem ser avaliadas como atividades ativas para o ambiente atual. |
| evaluateAsTrueAudienceIds | Lista de IDs | Lista vazia. | Lista de IDs de audiência que devem ser sempre avaliadas como true no escopo da solicitação [!DNL Target]. |
| evaluateAsFalseAudienceIds | Lista de IDs | Lista vazia. | Lista de IDs de audiência que devem ser sempre avaliadas como falsas no escopo da solicitação [!DNL Target]. |
| activityIndex | Número inteiro | Nulo.<br>Não pode estar em branco. | O índice de atividade no token criptografado. Se activityIndex estiver fora dos limites da atividade no token ou se for nulo, ele será ignorado. O índice começa com 1.<br>Regras de validação: deve ter pelo menos um índice de atividade e deve fazer referência a uma atividade especificada no token. |
| experienceIndex | Número inteiro | Nulo. | Quando especificado, seleciona uma experiência por índice na definição da atividade. Se não especificado ou fora dos limites, ele retornará à estratégia de seleção de experiência da atividade. Regras de validação - O índice começa com 1: podem ser nulas ou devem fazer referência a uma experiência na atividade. |