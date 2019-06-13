---
description: 'Informações sobre a função targetPageParams() para at.js. '
keywords: adobe.target.notification; elemento; seletor; notificação; extensão
seo-description: Informações sobre a função targetPageParams() da biblioteca at.js de JavaScript do Adobe Target.
seo-title: Informações sobre a função targetPageParams() da biblioteca at.js de JavaScript do Adobe Target.
solution: Target
subtopic: Introdução
title: targetPageParams()
topic: Padrão
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# targetPageParams() {#reference_B235C9F6DA79449ABE3E23F914FEABAE}

Este método permite anexar parâmetros ao mbox global de fora do código da solicitação.

Esta função é muito útil para incluir o mesmo conjunto de parâmetros em múltiplas chamadas da mbox. A função precisa ser definida pelo cliente. Ela deve retornar uma matriz de parâmetros que serão transmitidos apenas à solicitação global da mbox. Esta função pode ser definida antes que at.js seja carregada ou em **[!UICONTROL Configurar]** &gt; **[!UICONTROL Implementação]** &gt; **[!UICONTROL Editar configurações da at.js]** &gt; **[!UICONTROL Configurações do código]** &gt; **[!UICONTROL Cabeçalho da biblioteca]**.

Você pode transmitir parâmetros para target-global-mbox usando a função `targetPageParams()` de qualquer uma das seguintes maneiras:

* Uma lista delimitada por ampersand
* Uma matriz
* Um objeto JSON

## Exemplos

Lista delimitada por ampersand (os valores devem ser codificados por URL):

```
function targetPageParams() { 
    return "param1=value1&param2=value2&p3=hello%20world"; 
}
```

Matriz (os valores não precisam ser codificados por URL):

```
targetPageParams = function() { 
     return ["a=1", "b=2", "c=hello world"]; 
};
```

JSON (os valores não precisam ser codificados por URL):

```
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
