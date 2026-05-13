---
keywords: qa, lado do servidor, lado do servidor, visualização, visualização de links
description: Saiba como usar as URLs de controle de qualidade do Adobe [!DNL Target] com entrega do lado do servidor para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.
title: Usar o Posso executar o controle de qualidade de atividade com entrega do lado do servidor?
feature: Activities
exl-id: eb6965be-92a6-452d-ac01-7ae1533239cc
TQID: https://experienceleague.adobe.com/zZJmFqpXtAigTiEWMZhRqXBJqvG3ANLussSPE3-NoDA
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 408
ht-degree: 51%

---

# Usar o controle de qualidade de atividade com entrega do lado do servidor

Use URLs de controle de qualidade com entrega do lado do servidor no [!DNL Adobe Target] para realizar o controle de qualidade das atividades com facilidade utilizando links de visualização que nunca mudam, direcionamento opcional de público-alvo e relatórios de controle de qualidade que permanecem segmentados a partir dos dados de atividade em tempo real.

A implementação padrão do Controle de qualidade de atividade oferece suporte à passagem de `qa_mode` parâmetros por meio de `pageUrl` parâmetros. Essa abordagem é conveniente para chamadas [!DNL Target] padrão/ajax. No entanto, para chamadas de servidor para servidor, isso não é a melhor abordagem para um caso SDK do Adobe Mobile, quando `pageUrl` não está disponível.

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
| token | Token criptografado | Nenhum.<br>Não pode ficar em branco. | Uma entidade criptografada que contém a lista de IDs de atividade que podem ser executadas no Controle de Qualidade da Atividade.<br>Regras de validação: deve ser um token criptografado pertencente ao cliente especificado na solicitação [!DNL Target]. Todas as atividades especificadas no token devem pertencer ao cliente. |
| bypassEntryAudience | Booleano | Falso | Especifica se os direcionamentos de etapas de entrada de atividades de controle de qualidade devem ser avaliados ou se devem ser considerados como correspondentes. |
| listedActivitiesOnly | Booleano | Falso | Especifica se as atividades de QA devem ser executadas isoladamente ou se devem ser avaliadas como atividades ativas para o ambiente atual. |
| evaluateAsTrueAudienceIds | Lista de IDs | Lista vazia. | Lista de IDs de público-alvo que devem sempre ser avaliadas como verdadeiras no escopo da solicitação [!DNL Target]. |
| evaluateAsFalseAudienceIds | Lista de IDs | Lista vazia. | Lista de IDs de público-alvo que devem sempre ser avaliadas como falsas no escopo da solicitação [!DNL Target]. |
| activityIndex | Número inteiro | Nulo.<br>Não pode ficar vazio. | O índice de atividade no token criptografado. Se activityIndex estiver fora dos limites da atividade no token ou se for nulo, ele será ignorado. O índice começa com 1.<br>Regras de validação: deve ter pelo menos um índice de atividade e deve fazer referência a uma atividade especificada no token. |
| experienceIndex | Número inteiro | Nulo. | Quando especificado, seleciona uma experiência por índice na definição da atividade. Se não especificado ou fora dos limites, ele retornará à estratégia de seleção de experiência da atividade. Regras de validação - O índice começa com 1: podem ser nulas ou devem fazer referência a uma experiência na atividade. |
