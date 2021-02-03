---
keywords: adobe.target.getOffer;getOffer;getoffer;obter oferta;at.js;funções;função
description: Informações sobre a função adobe.target.getOffer(options) da biblioteca at.js de JavaScript do Adobe Target.
title: Adobe.Target.Getoffer(Options)
feature: at.js
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 96%

---


# adobe.target.getOffer(options)

Esta função envia uma solicitação para obter uma oferta do Target.

Use com `adobe.target.applyOffer()` para processar a resposta ou use sua própria manipulação de sucesso. O parâmetro de opções é obrigatório e tem a seguinte estrutura:

| Chave | Tipo | Obrigatório | Descrição |
|--- |--- |--- |--- |
| mbox | String | Sim | Nome da mbox |
| params | Objeto | Não | Parâmetros de mbox. Um objeto de pares de valores-chave que tem a seguinte estrutura:<br>`{ "param1": "value1", "param2": "value2"}` |
| success | Função | Sim | Retorno de chamada para execução quando recebemos uma resposta do servidor. A função de retorno de chamada bem-sucedida receberá um único parâmetro que represente uma variedade de objetos em oferta. Este é um exemplo de retorno de chamada:<br>`function handleSuccess(response){......}`<br>Consulte Respostas abaixo para obter detalhes. |
| error | Função | Sim | Retorno de chamada para execução quando recebemos um erro. Há alguns casos que são considerados errôneos:<ul><li>Código do status de HTTP diferente de 200 OK</li><li>Não foi possível analisar a resposta. Por exemplo, nós mal construímos JSON ou HTML ao invés de JSON.</li><li>A resposta contém a tecla &quot;erro&quot;. Por exemplo, uma exceção foi lançada no Edge e não foi possível processar a solicitação apropriadamente. Podemos receber um erro quando uma mbox está bloqueada e não é possível recuperar o conteúdo dela, etc. A função de retorno de chamada de erro receberá dois parâmetros: status e erro. Veja um exemplo de retorno de chamada de erro:   `function handleError(status, error){......}`</li></ul>Veja as respostas com erro abaixo para obter mais informações. |
| timeout | Número | Não | Tempo limite em milissegundos. Se não especificado, o tempo limite padrão em at.js será utilizado.<br>O tempo limite padrão pode ser definido na  [!DNL Target] interface em  [!UICONTROL Administração > Implementação]. |

## Exemplos {#section_97C2D2E03E6549BEA7F4873E3F5E4A0D}

Adicionar parâmetros com getOffer() e usar applyOffer() para método bem-sucedido:

```javascript
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Adicionar parâmetros e parâmetros de perfil com getOffer() e usar applyOffer() para método bem-sucedido:

```javascript
adobe.target.getOffer({   
  "mbox": "target-global-mbox", 
  "params": { 
     "a": 1, 
     "b": 2, 
     "profile.age": 27, 
     "profile.gender": "male" 
  }, 
  "success": function(offer) {           
        adobe.target.applyOffer( {  
           "mbox": "target-global-mbox", 
           "offer": offer  
        } ); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

Usar tempo limite personalizado e método bem-sucedido personalizado com getOffer():

&quot;YOUR_OWN_CUSTOM_HANDLING_FUNCTION&quot; é um placeholder para uma função que o cliente definiria.

```javascript
adobe.target.getOffer({     
  "mbox": "target-global-mbox",   
  "success": function(offer) { 
    YOUR_OWN_CUSTOM_HANDLING_FUNCTION(offer);   
  }, 
  "error": function(status, error) {                 
    console.log('Error', status, error);   
  },   
  "timeout": 2000 
});
```

## Respostas   {#section_CF9FD236EF794620BCBF84EB80160183}

O parâmetro de resposta passado para o retorno de chamada de sucesso será uma variedade de ações. Uma ação é um objeto que geralmente tem o seguinte formato:

| Nome | Tipo | Descrição |
|--- |--- |--- |
| action | String | Tipo de ação a ser aplicada ao elemento identificado. |
| selector | Sequência | Representa um seletor do Sizzle. |
| cssSelector | String | Seletor nativo DOM, usado para pré-ocultação de elemento. |
| content | String | O conteúdo a ser aplicado ao elemento identificado. |

## Exemplo

```javascript
{ 
    "sessionId": "1444512212156-384616", 
    "tntId": "1444512212156-384616.17_35", 
    "offers": [{ 
        "plugins": ["<script type=\"text/javascript\">\r\n/*mboxHighlight+ (1of2) v1 ==> Response Plugin*/\r\nwindow.ttMETA=(typeof(window.ttMETA)!='undefined')?window.ttMETA:[];window.ttMETA.push({'mbox':'target-global-mbox','campaign':'at: redirect ootb','experience':'Experience B','offer':'/at_redirect_ootb/experiences/1/pages/0/1442082890250'});window.ttMBX=function(x){var mbxList=[];for(i=0;i<ttMETA.length;i++){if(ttMETA[i].mbox==x.getName()){mbxList.push(ttMETA[i])}}return mbxList[x.getId()]}\r\n</script>"], 
        "actions": { 
            "content": [{ 
                "passMboxSession": false, 
                "selector": "body", 
                "action": "redirect", 
                "url": "https://example.com/04.html", 
                "includeAllUrlParameters": true 
            }] 
        } 
    }] 
}
```

## Respostas de erro {#section_1ACCE79AF2CB4FA2AD1371EA06AF129F}

Os parâmetros &quot;status&quot; e &quot;erro&quot; passados para o retorno de chamada de erro terão o seguinte formato:

| Nome | Tipo | Descrição |
|--- |--- |--- |
| status | String | Representa o status do erro. Este parâmetro pode ter os seguintes valores:<ul><li>timeout: Indica que o tempo limite para a solicitação foi excedido.</li><li>parseerror: Indica que a resposta não pôde ser analisada, por exemplo, se recebermos um texto HTML ou sem formatação em vez de JSON.</li><li>error: Indica um erro geral, como o recebimento do status HTTP diferente de 200 OK</li></ul> |
| erro | String | Contém dados adicionais, como mensagem de exceção ou qualquer outra coisa que possa ser útil para solução de problemas. |