---
description: 'Informações sobre a função targetPageParamsAll() para at.js. '
keywords: Targetpageparamsall; targetpageparamsall; Pageparamsall; pageparamsall; params de página; parâmetros de página; at. js; funções; função
seo-description: Informações sobre a função targetPageParamsAll() da biblioteca at.js de JavaScript do Adobe Target.
seo-title: Informações sobre a função targetPageParamsAll() da biblioteca at.js de JavaScript do Adobe Target.
solution: Target
subtopic: Introdução
title: targetPageParamsAll()
topic: Padrão
translation-type: tm+mt
source-git-commit: ef2c4ac78fef5889d5a6e9e053dfd36b77919dd4

---


# targetPageParamsAll()

Este método permite anexar parâmetros a todos os mboxes de fora do código da solicitação.

Isso é muito útil para incluir o mesmo conjunto de parâmetros em múltiplas chamadas da mbox. A função precisa ser definida pelo cliente. Ela deve retornar uma matriz de parâmetros que serão transmitidos a todas as solicitações de mbox na página. Esta função pode ser definida antes que at.js seja carregada ou em **[!UICONTROL Configurar]** &gt; **[!UICONTROL Implementação]** &gt; **[!UICONTROL Editar configurações da at.js]** &gt; **[!UICONTROL Configurações do código]** &gt; **[!UICONTROL Cabeçalho da biblioteca]**.

Você pode transmitir parâmetros para target-global-mbox usando a função targetPageParamsAll() de qualquer uma das seguintes maneiras:

* Uma lista delimitada por ampersand
* Uma matriz
* Um objeto JSON

## Exemplos

Lista delimitada por ampersand (os valores devem ser codificados por URL):

```
function targetPageParamsAll() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Matriz (os valores não precisam ser codificados por URL):

```
targetPageParamsAll = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (os valores não precisam ser codificados por URL):

```
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
