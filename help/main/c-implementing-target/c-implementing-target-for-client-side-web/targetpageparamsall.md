---
keywords: targetPageParamsAll; targetpageparamsall; PageParamsAll; pageparamsall; parâmetros da página; parâmetros da página; at.js; funções; função
description: Use a função targetPageParamsAll() para o Adobe [!DNL Target] biblioteca JavaScript da at.js para anexar parâmetros a todas as mboxes de fora do código da solicitação.
title: Como uso a função targetPageParamsAll()?
feature: at.js
role: Developer
exl-id: 58fbb62e-30da-486f-b771-6452ad5e27e6
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 72%

---

# targetPageParamsAll()

Este método permite anexar parâmetros a todos os mboxes de fora do código da solicitação.

Isso é muito útil para incluir o mesmo conjunto de parâmetros em múltiplas chamadas da mbox. A função precisa ser definida pelo cliente. Ela deve retornar uma matriz de parâmetros que serão transmitidos a todas as solicitações de mbox na página. Essa função pode ser definida antes que at.js seja carregada ou em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]** > **[!UICONTROL Editar]** > **[!UICONTROL Configurações de código]** > **[!UICONTROL Cabeçalho da biblioteca]**.

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
