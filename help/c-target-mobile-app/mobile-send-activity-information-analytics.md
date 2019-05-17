---
description: Essa seção descreve como enviar informações de atividade do aplicativo para dispositivos móveis do Target para o Adobe Analytics para segmentação postAhoc.
seo-description: Essa seção descreve como enviar informações de atividade do aplicativo para dispositivos móveis do Target para o Adobe Analytics para segmentação postAhoc.
seo-title: Enviar informações da atividade ao Adobe Analytics
title: Enviar informações da atividade ao Adobe Analytics
uuid: 2ca1ebfe-5008-4a73-a032-1ad81f062925
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Enviar informações da atividade ao Adobe Analytics{#send-activity-information-to-adobe-analytics}

Essa seção descreve como enviar informações de atividade do aplicativo para dispositivos móveis do Target para o Adobe Analytics para segmentação postAhoc.

**Pré-requisitos**

* Essa integração exige que o Analytics e o Target sejam implementados usando o SDK móvel.
* Verifique se o conjunto de relatórios está ativado para receber informações de Atividade do Target.

   Isso normalmente é feito adicionando o código de cliente do Target ao conjunto de relatórios do Analytics. Isso já pode estar ativado se você estiver usando a integração SiteCatalyst-Test&amp;Target para atividades da web. Se tiver dúvidas sobre essa etapa, entre em contato com o Atendimento ao Cliente da Adobe.

1. Obtenha as informações da atividade.

   Se você incluir uma cadeia de caracteres como a seguinte no conteúdo da experiência, o Target retornará as informações da campanha que você pode enviar ao Analytics:

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

   Neste exemplo, um nó com a variável &#39; `tntVal`&#39; é adicionado para obter as informações da Atividade. Adicione um código simular para as outras experiências, com um título e mensagem apropriados.

   Essa cadeia de caracteres fornece um número (como 115110:0:0) na resposta do Target. Isso indica a ID da atividade, a ID da experiência e o Tipo de tráfego. Este é um exemplo de resposta do Target:

   ```
   { 
     "tntVal": 115110:0:0", 
     "title":"Welcome Message", 
     "message":"Get Free Shipping Today!" 
   }
   ```

1. Analise o objeto JSON.

   Analise a resposta recebida do Target no retorno de chamada. Você pode usar NSJSONSerialization para analisar essa resposta e armazená-la em um diretório ou matriz.

   Consulte a documentação [nsjsonserialization](https://developer.apple.com/library/ios/documentation/Foundation/Reference/NSJSONSerialization_Class/#//apple_ref/occ/clm/NSJSONSerialization/JSONObjectWithData:options:error) para obter mais informações.
1. Envie os dados ao Analytics.

   Adicione as informações da atividade analisada (como `tntVal` na resposta acima) ao seu objeto de dados de contexto em uma chamada do Analytics. Essa chamada do Analytics contendo os dados de contexto pode ser disparada imediatamente ou por aguardar até o disparo da próxima chamada do Analytics.

   Por exemplo, essa chamada pode ser disparada no retorno da chamada `targetLoadRequest`:

   ```
   [ADBMobile trackAction:@"Welcome Screen"  
         data:@{@"&&tnt" : tntVal from response}];
   ```

   >[!NOTE]
   >
   >`&&tnt`é uma chave de evento reservada no SDK para dispositivos móveis. A classificação posterior da variável `tntVal` no Analytics funciona no SDK móvel da mesma maneira que na web (JavaScript). Quando a informação for processada no Analytics, você deverá ver os nomes da atividade e da experiência na interface do Analytics.

