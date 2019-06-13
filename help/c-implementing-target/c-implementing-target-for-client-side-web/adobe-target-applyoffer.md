---
description: 'Informações sobre a função adobe.target.applyOffer(options) para at.js. '
keywords: adobe.target.notification; elemento; seletor; notificação; extensão
seo-description: Informações sobre a função adobe.target.applyOffer(options) da biblioteca at.js de JavaScript do Adobe Target.
seo-title: Informações sobre a função adobe.target.applyOffer(options) da biblioteca at.js de JavaScript do Adobe Target.
solution: Target
subtopic: Introdução
title: adobe.target.applyOffer(options)
topic: Padrão
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# adobe.target.applyOffer(options) {#reference_BBE83F513B5B4E03BBC3F50D90864245}

Esta função aplica o conteúdo de resposta.

>[!NOTE]
>
>`applyOffer` exige o `mbox` parâmetro. Se não houver nome de mbox definido, um erro ocorrerá.

O parâmetro de opções é obrigatório e tem a seguinte estrutura:

| Chave | Tipo | Obrigatório | Descrição |
|--- |--- |--- |--- |
| mbox | String | Sim | Nome da mbox<br>Com a at.js 1.3.0 (e posteriores), o Target exige que a tecla mbox seja usada. Essa chave era exigida anteriormente, mas o Target agora a aplica para garantir que tenha a validação adequada e que os clientes estejam usando a função corretamente. |
| selector | String ou elemento DOM | Não | Elemento HTML ou seletor CSS usado para identificar o elemento HTML onde o Target deve posicionar o conteúdo da oferta. Se nenhum seletor for fornecido, o Target presume que o elemento HTML que devemos usar é HTML HEAD. |
| offer | Matriz | Sim | Uma ação de matriz que deve ser aplicada ao elemento. |

## Exemplo {#section_D8D6A17B73DE4542937CDB687193A5CC}

O exemplo a seguir mostra como usar `getOffer` e `applyOffer` juntos:

```
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
