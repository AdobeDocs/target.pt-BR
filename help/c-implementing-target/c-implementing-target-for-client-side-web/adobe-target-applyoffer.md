---
keywords: adobe.target.applyOffer; applyOffer; applyoffer; aplicar oferta; at.js; funções; função
description: Use a função adobe.target.applyOffer() da biblioteca de JavaScript Adobe [!DNL Target] at.js para aplicar o conteúdo da resposta.
title: Como uso a função adobe.target.applyOffer() ?
feature: 'at.js '
role: Developer
exl-id: d230d48f-0d6c-4f55-96a0-681dd31e8d16
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 73%

---

# adobe.target.applyOffer(options)

Essa função é para aplicar o conteúdo de resposta com [!DNL Adobe Target].

>[!NOTE]
>
>`applyOffer` exige o `mbox` parâmetro. Se não houver nome de mbox definido, um erro ocorrerá.

O parâmetro de opções é obrigatório e tem a seguinte estrutura:

| Chave | Tipo | Obrigatório | Descrição |
|--- |--- |--- |--- |
| mbox | String | Sim | Nome da mbox<br>Com a at.js 1.3.0 (e posteriores), o Target exige que a tecla mbox seja usada. Essa chave era exigida anteriormente, mas o Target agora a aplica para garantir que tenha a validação adequada e que os clientes estejam usando a função corretamente. |
| selector | String   ou elemento DOM | Não | Elemento HTML ou seletor CSS usado para identificar o elemento HTML onde o Target deve posicionar o conteúdo da oferta. Se o seletor não for fornecido, o Target presumirá que o elemento HTML deve usar o HEAD HTML. |
| Oferta | Matriz | Sim | Uma ação de matriz que deve ser aplicada ao elemento. |

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
