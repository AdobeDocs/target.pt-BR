---
keywords: adobe.target.getOffers;getOffers;getoffers;obter ofertas;at.js; funções;função
description: Use a função adobe.target.getOffers() e suas opções para a biblioteca at.js do Adobe Target acionar solicitações para obter várias ofertas do Target. (at.js 2.x)
title: Como uso a função adobe.target.getOffers() ?
feature: 'at.js '
role: Developer
exl-id: ed5f06c8-d837-4ea1-a857-c6c46424aa1f
translation-type: tm+mt
source-git-commit: 82c66de1d4a6680392b7e73759dc824c4df22d2f
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 89%

---

# adobe.target.getOffers() - at.js 2.x

Essa função permite que você recupere várias ofertas passando em várias mboxes. Além disso, várias ofertas podem ser recuperadas para todas as exibições em atividades ativas.

>[!NOTE]
>
>Essa função foi introduzida com a at.js 2.x. Essa função não está disponível para a at.js versão 1.*x*.

| Chave | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| consumerId | String | Não | O valor padrão é a mbox global do cliente se não for fornecida. Essa chave é usada para gerar a ID de dados complementares usada para integração A4T. Esta chave é uma cadeia de caracteres exclusiva por visitante. |
| decisioningMethod | String | Não | &quot;lado do servidor&quot;, &quot;no dispositivo&quot;, &quot;híbrido&quot; |
| solicitação | Objeto | Sim | Consulte Tabela de solicitações abaixo. |
| timeout | Número | Não | tempo limite da solicitação. Se não for especificado, o tempo limite padrão da at.js será usado. |

## Solicitação

>[!NOTE]
>
>Consulte a [Documentação da API de entrega](http://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) para obter informações sobre os tipos aceitáveis para todos os campos listados abaixo.

| Nome do campo | Obrigatório? | Limitações | Descrição |
| --- | --- | --- | --- |
| solicitação > id | Não |  | Um de `tntId`, `thirdPartyId` ou `marketingCloudVisitorId` é obrigatório. |
| Solicitação > id > thirdPartyId | Não | Tamanho máximo = 128 |  |  |
| Request > experienceCloud | Não |  |  |
| Request > experienceCloud > analytics | Não |  | Integração do Adobe Analytics |
| Request > experienceCloud > analytics > logging | Não | O seguinte deve ser implementado na página:<ul><li>Serviço de ID de visitante</li><li>AppMeasurement.js</li></ul> | Os seguintes valores são suportados:<br>**client_side**: quando especificado, uma carga de análise será retornada ao chamador que deve ser usada para enviar ao Adobe Analytics por meio da API de inserção de dados.<br>**server_side**: esse é o valor padrão em que o back-end do Target e do Analytics usará a SDID para unir as chamadas para fins de relatório. |
| Solicitação > pré-busca | Não |  |  |
| Solicitação > pré-busca > exibições | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome`<=` 128<br>Tamanho do valor `<=` 5000<br>O nome não deve começar com &quot;perfil&quot;<br>Nomes não permitidos: &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot; | Transmita os parâmetros a serem usados para recuperar exibições relevantes nas atividades ativas. |
| Solicitação > pré-busca > exibições > profileParameters | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=` 5000 <br>O nome não deve começar com &quot;perfil&quot; | Transmita os parâmetros a serem usados para recuperar exibições relevantes nas atividades ativas. |
| Solicitação > pré-busca > exibições > produto | Não |  |  |
| Solicitação > pré-busca > exibições > produto -> id | Não | Não deixar em branco<br>tamanho máximo = 128 | Transmita as IDs do produto a serem usadas para recuperar exibições relevantes nas atividades ativas. |
| Solicitação > pré-busca > exibições > produto > categoryId | Não | Não deixar em branco<br>tamanho máximo = 128 | Transmita as IDs de categoria do produto a serem usadas para recuperar exibições relevantes nas atividades. |
| Solicitação > pré-busca > exibições > ordem | Não |  |  |
| Solicitação > pré-busca > exibições > ordem > id | Não | Tamanho máximo = 250 | Transmita as IDs da ordem a serem usadas para recuperar exibições relevantes nas atividades ativas. |
| Solicitação > pré-busca > exibições > ordem > total | Não | Total`>=` 0 | Transmita os totais da ordem a serem usados para recuperar exibições relevantes nas atividades ativas. |
| Solicitação > pré-busca > exibições > ordem > purchasedProductIds | Não | Nenhum valor em branco<br>Tamanho máximo de cada valor 50<br>Concatenado e separado por vírgula<br>Tamanho total das IDs do produto `<=` 250 | Transmita as IDs do produto adquirido a serem usadas para recuperar exibições relevantes nas atividades ativas. |
| Solicitação > executar | Não |  |  |
| Solicitação > executar > pageLoad | Não |  |  |
| Solicitação > executar > pageLoad > parâmetros | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=` 5000<br>O nome não deve começar com &quot;perfil&quot;.<br>Nomes não permitidos: &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot; | Recupere as ofertas com os parâmetros especificados quando a página for carregada. |
| Solicitação > executar > pageLoad > profileParameters | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=`256<br>O nome não deve começar com &quot;perfil&quot;. | Recupere as ofertas com os parâmetros do perfil especificados quando a página for carregada. |
| Solicitação > executar > pageLoad > produto | Não |  |  |
| Solicitação > executar > pageLoad > produto -> id | Não | Não deixar em branco<br>Tamanho máximo = 128 | Recupere as ofertas com as IDs do produto especificadas quando a página for carregada. |
| Solicitação > executar > pageLoad > produto > categoryId | Não | Não deixar em branco<br>Tamanho máximo = 128 | Recupere as ofertas com as IDs de categoria do produto especificadas quando a página for carregada. |
| Solicitação > executar > pageLoad > ordem | Não |  |  |
| Solicitação > executar > pageLoad > order > id | Não | Tamanho máximo = 250 | Recupere as ofertas com as IDs da ordem especificadas quando a página for carregada. |
| Solicitação > executar > pageLoad > ordem > total | Não | `>=` 0 | Recupere as ofertas com os totais da ordem especificados quando a página for carregada. |
| Solicitação > executar > pageLoad > ordem > purchasedProductIds | Não | Nenhum valor em branco<br>Tamanho máximo de cada valor 50<br>Concatenado e separado por vírgula<br>Tamanho total das IDs do produto `<=` 250 | Recupere as ofertas com as IDs do produto adquirido especificadas quando a página for carregada. |
| Solicitação > executar > mboxes | Não | Tamanho máximo = 50<br>Sem elementos nulos |  |
| Solicitação > executar > mboxes > mbox | Sim | Não deixar em branco<br>Nenhum sufixo &#39;-clicado&#39;<br>Tamanho máximo = 250<br>Caracteres permitidos: `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | Nome da mbox. |
| Solicitação > executar > mboxes > mbox > índice | Sim | Não nulo<br>Exclusivo<br>`>=` 0 | Observe que o índice não representa a ordem em que as mboxes serão processadas. Da mesma forma que em uma página da Web com diversas mboxes regionais, a ordem em que serão processadas não pode ser especificada. |
| Solicitação > executar > mboxes > mbox > parâmetros | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=` 5000<br>O nome não deve começar com &quot;perfil&quot;.<br>Nomes não permitidos: &quot;orderId&quot;, &quot;orderTotal&quot;, &quot;productPurchasedId&quot; | Recupere as ofertas de determinada mbox com os parâmetros especificados. |
| Solicitação > executar > mboxes > mbox > profileParameters | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=`256<br>O nome não deve começar com &quot;perfil&quot;. | Recupere as ofertas de determinada mbox com os parâmetros do perfil especificados. |
| Solicitação > executar > mboxes > mbox > produto | Não |  |  |
| Solicitação > executar > mboxes > mbox > produto > id | Não | Não deixar em branco<br>Tamanho máximo = 128 | Recupere as ofertas de determinada mbox com as IDs do produto especificadas. |
| Solicitação > executar > mboxes > mbox > produto > categoryId | Não | Não deixar em branco<br>Tamanho máximo = 128 | Recupere as ofertas de determinada mbox com as IDs de categoria do produto especificadas. |
| Solicitação > executar > mboxes > mbox > ordem | Não |  |  |
| Solicitação > executar > mboxes > mbox > ordem > id | Não | Tamanho máximo = 250 | Recupere as ofertas de determinada mbox com as IDs da ordem especificadas. |
| Solicitação > executar > mboxes > mbox > ordem > total | Não | `>=` 0 | Recupere as ofertas de determinada mbox com os totais da ordem especificados. |
| Solicitação > executar > mboxes > mbox > ordem > purchasedProductIds | Não | Nenhum valor em branco<br>Tamanho máximo de cada valor = 50<br>Concatenado e separado por vírgula<br>Tamanho total das IDs do produto `<=` 250 | Recupere as ofertas de determinada mbox com as IDs do produto adquirido da ordem especificadas. |

## Chame getOffers() para todas as exibições

```javascript
adobe.target.getOffers({
    request: {
      prefetch: {
        views: [{}]
    }
  }
});
```

## getCallOffers() para tomar uma decisão no dispositivo

```javascript
adobe.target.getOffers({ 

  decisioningMethod:"on-device", 
  request: { 
    execute: { 
      mboxes: [ 
        { 
          index: 0, 
          name: "homepage" 
        } 
      ] 
    } 
 } 
}); 
```

## Chame getOffers() para recuperar as exibições mais recentes com os parâmetros e parâmetros do perfil transmitidos

```javascript
adobe.target.getOffers({
  request: {
    "prefetch": {
      "views": [
        {
          "parameters": {
            "ad": "1"
          },
          "profileParameters": {
            "age": 23
          }
        }
      ]
    }
  }
});
```

## Chame getOffers() para recuperar mboxes com parâmetros e parâmetros de perfil passados.

```javascript
adobe.target.getOffers({
  request: {
    execute: {
      mboxes: [
        {
          index: 0,
          name: "first-mbox"
        },
        {
          index: 1,
          name: "second-mbox",
          parameters: {
            a: 1
          },
          profileParameters: {
            b: 2
          }
        }
      ]
    }
  }
});
```

## Chame getOffers() para recuperar a carga do Analytics no cliente

```javascript
adobe.target.getOffers({
      request: {
        experienceCloud: {
          analytics: {
            logging: "client_side"
          }
        },
        prefetch: {
          mboxes: [{
            index: 0,
            name: "a1-serverside-xt"
          }]
        }
      }
    })
    .then(console.log)
```

**Resposta**:

```javascript
{
  "prefetch": {
    "mboxes": [{
      "index": 0,
      "name": "a1-serverside-xt",
      "options": [{
        "content": "<img src=\"http://s7d2.scene7.com/is/image/TargetAdobeTargetMobile/L4242-xt-usa?tm=1490025518668&fit=constrain&hei=491&wid=980&fmt=png-alpha\"/>",
        "type": "html",
        "eventToken": "n/K05qdH0MxsiyH4gX05/2qipfsIHvVzTQxHolz2IpSCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
        "responseTokens": {
          "profile.memberlevel": "0",
          "geo.city": "bucharest",
          "activity.id": "167169",
          "experience.name": "USA Experience",
          "geo.country": "romania"
        }
      }],
      "analytics": {
        "payload": {
          "pe": "tnt",
          "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
        }
      }
    }]
  }
}
```

A carga pode ser encaminhada para o Adobe Analytics por meio da [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Buscar e renderizar dados de várias mboxes via getOffers() e applyOffers() {#multiple}

A at.js 2.x permite buscar várias mboxes por meio da API de `getOffers()`. Você também pode buscar dados de várias mboxes e, em seguida, usar o `applyOffers()` para renderizá-los em diferentes locais identificados por um seletor de CSS.

O exemplo a seguir mostra uma página HTML simples com a at.js 2.x implementada:

```html
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>at.js 2.x, multiple selectors and multiple mboxes</title>
  <script src="at.js"></script>
</head>
<body>
  <div id="container1">Default content 1</div>
  
  <div id="container2">Default content 2</div>

  <div id="container3">Default content 3</div>
</body>
</html>
```

Suponha que você tenha três contêineres que deseja modificar por meio do conteúdo recebido do [!DNL Target]. É possível criar uma única solicitação para três mboxes em que cada mbox tem conteúdo para renderizar no respectivo contêiner.

A solicitação e o código de renderização podem ser semelhantes ao seguinte exemplo:

```javascript
adobe.target.getOffers({
  request: {
    prefetch: {
      mboxes: [
        {
          index: 0,
          name: "mbox1"
        },
        {
          index: 1,
          name: "mbox2"
        },
        {
          index: 2,
          name: "mbox3"
        }
      ]
    }
  }
})
.then(response => {
  // get all mboxes from response
  const mboxes = response.prefetch.mboxes;
  let count = 1;

  mboxes.forEach(el => {
    adobe.target.applyOffers({
      selector: "#container" + count,
      response: {
        prefetch: {
          mboxes: [el]
        }
      }
    });

    count += 1;
  });
});
```

Na seção `request > prefetch > mboxes`, há três mboxes diferentes. Se a solicitação for concluída com sucesso, você receberá a resposta do `response > prefetch > mboxes` para cada mbox. Depois de ter as respostas e os locais que deseja usar para renderização, você pode chamar `applyOffers()` para renderizar o conteúdo recuperado de [!DNL Target]. Neste exemplo, há o seguinte mapeamento:

* mbox1 > CSS selector #container1
* mbox2 > CSS selector #container2
* mbox3 > CSS selector #container3

Este exemplo usa a variável de contagem para criar os seletores de CSS. Em um cenário real, você pode usar um mapeamento diferente entre o seletor de CSS e a mbox.

Observe que este exemplo usa `prefetch > mboxes`, mas você também pode usar `execute > mboxes`. Certifique-se de que, se você usar a pré-busca em `getOffers()`, também deverá usá-la na invocação de `applyOffers()`.

## Chame getOffers() para executar um pageLoad

O exemplo a seguir mostra como executar um pageLoad usando getOffers() com o at.js 2.*x* 

```javascript
adobe.target.getOffers({
    request: {
        execute: {
            pageLoad: {
                parameters: {}
            }
        }
    }
});
```
