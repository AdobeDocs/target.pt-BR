---
keywords: targetPageParamsAll; targetpageparamsall; PageParamsAll; pageparamsall; parâmetros da página; parâmetros da página; at.js; funções; função
description: Use a função targetPageParamsAll() da biblioteca JavaScript do Adobe Target at.js para anexar parâmetros a todas as mboxes de fora do código de solicitação.
title: Como uso a função targetPageParamsAll()?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '169'
ht-degree: 71%

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
