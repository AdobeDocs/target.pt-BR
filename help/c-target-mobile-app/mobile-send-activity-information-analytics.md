---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: Saiba como enviar informações de atividade de aplicativos móveis da Adobe Target para a Adobe Analytics para segmentação pós-ad hoc.
title: Posso enviar informações de Atividade do aplicativo móvel para o Analytics?
feature: Implement Mobile
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 33%

---


# Enviar informações da atividade ao Adobe Analytics{#send-activity-information-to-adobe-analytics}

Esta seção descreve como enviar [!DNL Target] informações de atividade do aplicativo móvel para Adobe [!DNL Analytics] para segmentação posterior.

**Pré-requisitos**

* Essa integração exige que [!DNL Analytics] e [!DNL Target] sejam implementados usando o SDK móvel.
* Certifique-se de que seu conjunto de relatórios esteja habilitado para receber informações de atividade de [!DNL Target].

   Isso geralmente é feito adicionando o código do cliente [!DNL Target] ao conjunto de relatórios [!DNL Analytics]. Isso já pode estar ativado se você estiver usando a integração SiteCatalyst-Test&amp;Target para atividades da web. Se tiver dúvidas sobre essa etapa, entre em contato com o Atendimento ao Cliente da Adobe.

1. Obtenha as informações da atividade.

   Se você incluir uma string como a seguinte no conteúdo da sua experiência, [!DNL Target] retornará as informações de atividade que você pode enviar para [!DNL Analytics]:

   ```javascript
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Substitua o texto do código json da experiência por algo como o seguinte exemplo:

   ```javascript
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   Neste exemplo, um nó com a variável `tntVal` é adicionado para obter as informações de atividade. Adicione um código simular para as outras experiências, com um título e mensagem apropriados.

   Essa cadeia de caracteres fornece um número (como 115110:0:0) na resposta do [!DNL Target]. Isso indica a ID da atividade, a ID da experiência e o tipo de tráfego. A seguir está uma amostra de resposta de [!DNL Target]:

   ```javascript
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Analise o objeto JSON.

   Analise a resposta que retornou de [!DNL Target] no retorno de chamada. Você pode usar `NSJSONSerialization` para analisar essa resposta e armazená-la em um dicionário ou em uma matriz.

   Consulte a documentação [NSJSONSerialization](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) para obter mais informações.

1. Envie os dados ao [!DNL Analytics].

   Adicione as informações da atividade analisada (como `tntVal` na resposta acima) ao seu objeto de dados de contexto em uma chamada do [!DNL Analytics] Essa chamada [!DNL Analytics] que contém os dados de contexto pode ser acionada imediatamente ou pode aguardar até que a próxima chamada [!DNL Analytics] seja acionada.

   Por exemplo, essa chamada pode ser disparada no retorno da chamada `targetLoadRequest`:

   ```javascript
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`é uma chave de evento reservada no SDK para dispositivos móveis. A pós-classificação da variável `tntVal` em [!DNL Analytics] funciona da mesma maneira no SDK móvel que na Web (JavaScript). Depois que as informações forem processadas em [!DNL Analytics], você deverá ver os nomes de atividade e experiência na interface [!DNL Analytics].

