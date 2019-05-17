---
description: A função targetPageParams do JavaScript é usada para passar parâmetros para o mbox global. Isso é necessário em qualquer situação na qual informações adicionais de direcionamento/contexto devam ser passadas para o Target.
keywords: parâmetros de mbox global; targetPageParams; sequência de consulta; matriz; json; dtm; dynamic tag management
seo-description: A função targetPageParams do JavaScript é usada para passar parâmetros para o mbox global. Isso é necessário em qualquer situação na qual informações adicionais de direcionamento/contexto devam ser passadas para o Target.
seo-title: Envio de parâmetros para uma mbox global
solution: Target
subtopic: Introdução
title: Envio de parâmetros para uma mbox global
topic: Padrão
uuid: 058f0ef5-037a-4daf-8a1e-a9c7ecc7f0bd
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Envio de parâmetros para uma mbox global{#pass-parameters-to-a-global-mbox}

A função targetPageParams do JavaScript é usada para passar parâmetros para o mbox global. Isso é necessário em qualquer situação na qual informações adicionais de direcionamento/contexto devam ser passadas para o Target.

Por exemplo, em uma atividade do Recommendations, use os parâmetros para representar o produto ou categoria atual que está sendo visualizada.

O código para chamar a função do JavaScript deve vir antes da global mbox na página, independentemente de a mbox ser acionada como parte da mbox.js ou incluída manualmente no código da página.

>[!NOTE]
>
>Se você quiser adicionar parâmetros a todas as mboxes na página, não apenas à mbox global, use a [função targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) (somente no at.js).

Você pode transmitir parâmetros para `target-global-mbox`usando a função `targetPageParams()`de qualquer uma das seguintes maneiras:

* Uma matriz
* Um objeto JSON
* Uma lista delimitada por ampersand

Use esses três métodos para verificar se os parâmetros estão sendo enviados corretament. Você também pode ser capaz de verificar o envio de parâmetros usando o [depurador da Adobe Experience Cloud](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html).

Você deve definir a função JavaScript antes de adicionar a mbox global à página. O nome deve ser `targetPageParams`.

**String de consulta**

```
p1=v1&p2=v2&p3=hello%20world
```

* Nome: `targetPageParams`
* Valor de retorno: a &quot;&amp;&quot; parâmetros delimitados, com valores de parâmetro codificados por URL.

   Exemplo:

   Neste exemplo, p3 tem o valor `hello world`, que é codificado por URL.

Um exemplo de como deverá ser o código da página é mostrado a seguir:

```
<html> 
  <head> 
    <title>Title here..</title> 
    <script type="text/javascript"> 
        function targetPageParams() { 
           
<b>return "p1=v1&p2=v2&p3=hello%20world"</b>; 
        } 
    </script> 
    <script src="mbox.js" type="text/javascript"></script> 
  </head> 
  <body>Body here... 
  </body> 
</html>
```

Este exemplo envia os seguintes dados para a borda do mbox:

* p1=v1
* p2=v2
* p3=hello world

**Matriz**

```
<!--window.-->targetPageParams = function() { 
  return ["a=1", "b=2", "c=hello world"]; 
}; 
```

Os valores não precisam ser codificados por URL. Por exemplo, se um valor tiver um espaço, não há necessidade de codificar o espaço.

Este exemplo envia os seguintes dados para a borda do mbox:

* a=1
* b=2
* c=hello world

**JSON**

JSON é um modo poderoso de enviar os parâmetros. O Target usa as chaves de objeto JSON para achatar as estruturas complicadas em parâmetros simples.

```
<!--window.-->targetPageParams = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
                  "memberStatus": Gold, 
                  "country": { 
                                "city": "San Francisco" 
                            } 
              } 
  }; 
}; 
```

Os valores não precisam ser codificados por URL. Por exemplo, &quot;San Francisco&quot; não precisa de espaço para ser codificado. Um espaço é suficiente.

Este exemplo envia os seguintes dados para a borda do mbox:

* a=1
* b=2
* `profile.age`=26
* `profile.country.city`=São Francisco