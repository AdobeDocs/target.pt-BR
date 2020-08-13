---
keywords: mobile;tntVal;analytics;adobe analytics;integration;sdk;mobile sdk;
description: Esta seção descreve como enviar informações de atividade do aplicativo móvel Adobe Target para a Adobe Analytics para segmentação postAhoc.
title: Enviar informações de atividade da Adobe Target para a Adobe Analytics
feature: mobile implementation
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 34%

---


# Enviar informações da atividade ao Adobe Analytics{#send-activity-information-to-adobe-analytics}

This section describes how to send [!DNL Target] mobile app activity information to Adobe [!DNL Analytics] for post hoc segmentation.

**Pré-requisitos**

* This integration requires that [!DNL Analytics] and [!DNL Target] are implemented using the mobile SDK.
* Ensure that your report suite is enabled to receive activity information from [!DNL Target].

   This is usually done by adding the [!DNL Target] client code to the [!DNL Analytics] report suite. Isso já pode estar ativado se você estiver usando a integração SiteCatalyst-Test&amp;Target para atividades da web. Se tiver dúvidas sobre essa etapa, entre em contato com o Atendimento ao Cliente da Adobe.

1. Obtenha as informações da atividade.

   If you include a string like the following in your experience content, [!DNL Target] returns the activity information that you can send to [!DNL Analytics]:

   ```
   ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}
   ```

   Substitua o texto do código json da experiência por algo como o seguinte exemplo:

   ```
   { 
     "tntVal": ${campaign.id}:${campaign.recipe.id}:${campaign.recipe.trafficType}", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

   In this example, a node with the variable `tntVal` is added to obtain the activity information. Adicione um código simular para as outras experiências, com um título e mensagem apropriados.

   Essa cadeia de caracteres fornece um número (como 115110:0:0) na resposta do [!DNL Target]. Isso indica a ID da atividade, a ID da experiência e o tipo de tráfego. The following is a sample response from [!DNL Target]:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Analise o objeto JSON.

   Parse the response that came back from [!DNL Target] in the callback. You can use `NSJSONSerialization` to parse this response and store it in a dictionary or an array.

   Consulte a documentação [](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) NSJSONSerialization para obter mais informações.

1. Envie os dados ao [!DNL Analytics].

   Adicione as informações da atividade analisada (como `tntVal` na resposta acima) ao seu objeto de dados de contexto em uma chamada do [!DNL Analytics] This [!DNL Analytics] call containing the context data can be fired immediately or it can wait until the next [!DNL Analytics] call is fired.

   Por exemplo, essa chamada pode ser disparada no retorno da chamada `targetLoadRequest`:

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`é uma chave de evento reservada no SDK para dispositivos móveis. The post-classification of the `tntVal` variable in [!DNL Analytics] works in the same way in the mobile SDK as it does on the web (JavaScript). After the information is processed in [!DNL Analytics], you should see activity and experience names in the [!DNL Analytics] interface.

