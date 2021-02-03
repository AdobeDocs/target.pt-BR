---
keywords: targetPageParamsAll; targetpageparamsall; PageParamsAll; pageparamsall; parâmetros da página; parâmetros da página; at.js; funções; função
description: Informações sobre a função targetPageParamsAll() da biblioteca at.js de JavaScript do Adobe Target.
title: Targetpageparamsall()
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '152'
ht-degree: 87%

---


# targetPageParamsAll()

Este método permite anexar parâmetros a todos os mboxes de fora do código da solicitação.

Isso é muito útil para incluir o mesmo conjunto de parâmetros em múltiplas chamadas da mbox. A função precisa ser definida pelo cliente. Ela deve retornar uma matriz de parâmetros que serão transmitidos a todas as solicitações de mbox na página. Esta função pode ser definida antes do at.js ser carregado ou em **[!UICONTROL Administration]** > **[!UICONTROL Implementação]** > **[!UICONTROL Editar]** > **[!UICONTROL Definições de Código]** > **[!UICONTROL Cabeçalho da Biblioteca]**.

Você pode transmitir parâmetros para target-global-mbox usando a função targetPageParamsAll() de qualquer uma das seguintes maneiras:

* Uma lista delimitada por ampersand
* Uma matriz
* Um objeto JSON

## Exemplos

Lista delimitada por ampersand (os valores devem ser codificados por URL):

```javascript
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Matriz (os valores não precisam ser codificados por URL):

```javascript
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (os valores não precisam ser codificados por URL):

```javascript
targetPageParamsAll = function() { 
  return { 
    "a": 1, 
    "b": 2, 
    "profile": { 
        "age": 26, 
        "country": { 
          "city": "San Francisco" 
        } 
      } 
  }; 
};
```
