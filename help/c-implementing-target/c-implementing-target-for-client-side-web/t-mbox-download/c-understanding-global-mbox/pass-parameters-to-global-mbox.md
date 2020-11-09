---
keywords: global mbox parameters;targetPageParams;query string;array;json;dtm;dynamic tag management
description: A função targetPageParams do JavaScript é usada para passar parâmetros para o mbox global. Isso é necessário em qualquer situação na qual informações adicionais de direcionamento/contexto devam ser passadas para o Target.
title: Envio de parâmetros para uma mbox global
feature: null
subtopic: Getting Started
topic: Standard
uuid: 058f0ef5-037a-4daf-8a1e-a9c7ecc7f0bd
translation-type: tm+mt
source-git-commit: a05d2a28b7bea3aa559cd0174930af10c6d94134
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 78%

---


# Envio de parâmetros para uma mbox global{#pass-parameters-to-a-global-mbox}

A função `targetPageParams` do JavaScript é usada para passar parâmetros para o mbox global. Isso é necessário em qualquer situação na qual informações adicionais de direcionamento/contexto devam ser passadas para o [!DNL Target].

For example, in a [!DNL Recommendations] activity, use the parameters to represent the current product or category that is being viewed.

O código para chamar a função JavaScript deve vir antes da mbox global na página, independentemente de a mbox global ser acionada como parte do at.js ou ser incluída manualmente no código da página.

>[!NOTE]
>
>If you want to add parameters to all mboxes on the page, not just to the global mbox, use the [targetPageParamsAll()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) function.

Você pode transmitir parâmetros para `target-global-mbox`usando a função `targetPageParams()`de qualquer uma das seguintes maneiras:

* Uma matriz
* Um objeto JSON
* Uma lista delimitada por ampersand

Use esses três métodos para verificar se os parâmetros estão sendo enviados corretament. Você também pode ser capaz de verificar o envio de parâmetros usando o [depurador da Adobe Experience Cloud](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html).

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