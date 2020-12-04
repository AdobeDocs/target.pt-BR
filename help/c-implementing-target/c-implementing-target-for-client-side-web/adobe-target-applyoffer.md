---
keywords: adobe.target.applyOffer;applyOffer;applyoffer;apply offer;at.js;functions;function
description: Informações sobre a função adobe.target.applyOffer(options) da biblioteca at.js de JavaScript do Adobe Target.
title: adobe.target.applyOffer(options)
feature: client-side
translation-type: tm+mt
source-git-commit: a841c492e5d9e4bfedb20133ba32e37daf738c57
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 100%

---


# adobe.target.applyOffer(options)

Esta função aplica o conteúdo de resposta.

>[!NOTE]
>
>`applyOffer` exige o `mbox` parâmetro. Se não houver nome de mbox definido, um erro ocorrerá.

O parâmetro de opções é obrigatório e tem a seguinte estrutura:

| Chave | Tipo | Obrigatório | Descrição |
|--- |--- |--- |--- |
| mbox | String | Sim | Nome da mbox<br>Com a at.js 1.3.0 (e posteriores), o Target exige que a tecla mbox seja usada. Essa chave era exigida anteriormente, mas o Target agora a aplica para garantir que tenha a validação adequada e que os clientes estejam usando a função corretamente. |
| selector | String   ou elemento DOM | Não | Elemento HTML ou seletor CSS usado para identificar o elemento HTML onde o Target deve posicionar o conteúdo da oferta. Se nenhum seletor for fornecido, o Target presume que o elemento HTML que devemos usar é HTML HEAD. |
| offer | Matriz | Sim | Uma ação de matriz que deve ser aplicada ao elemento. |

## Exemplo {#section_D8D6A17B73DE4542937CDB687193A5CC}

O exemplo a seguir mostra como usar `getOffer` e `applyOffer` juntos:

```javascript
adobe.target.getOffer({   
  "mbox": "mbox",   
  "success": function(offers) {           
        adobe.target.applyOffer( {  
           "mbox": "mbox", 
           "offer": offers  
        } ); 
  },   
  "error": function(status, error) {           
      if (console && console.log) { 
        console.log(status); 
        console.log(error); 
      } 
  }, 
 "timeout": 5000 
}); 
```
