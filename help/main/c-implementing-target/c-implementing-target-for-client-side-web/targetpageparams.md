---
keywords: targetPageParams; targetpageparams; pageParams; pageparams; parâmetros da página; parâmetros da página; at.js; funções; função
description: Use a função targetPageParams() para o Adobe [!DNL Target] biblioteca JavaScript da at.js para anexar parâmetros à mbox global de fora do código da solicitação.
title: Como uso a função targetPageParams()?
feature: at.js
role: Developer
exl-id: 0772b400-626c-45d8-a4b5-a12691978cf3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '167'
ht-degree: 72%

---

# targetPageParams()

Este método permite anexar parâmetros ao mbox global de fora do código da solicitação.

Esta função é muito útil para incluir o mesmo conjunto de parâmetros em múltiplas chamadas da mbox. A função precisa ser definida pelo cliente. Ela deve retornar uma matriz de parâmetros que serão transmitidos apenas à solicitação global da mbox. Essa função pode ser definida antes que at.js seja carregada ou em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** > **[!UICONTROL Editar]** > **[!UICONTROL Cabeçalho da biblioteca]**.

Você pode transmitir parâmetros para target-global-mbox usando a função `targetPageParams()` de qualquer uma das seguintes maneiras:

* Uma lista delimitada por ampersand
* Uma matriz
* Um objeto JSON

## Exemplos

Lista delimitada por ampersand (os valores devem ser codificados por URL):

```javascript
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Matriz (os valores não precisam ser codificados por URL):

```javascript
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (os valores não precisam ser codificados por URL):

```javascript
targetPageParams = function() { 
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
