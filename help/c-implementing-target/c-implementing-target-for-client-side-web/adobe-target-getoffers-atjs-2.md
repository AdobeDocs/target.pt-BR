---
description: 'Informações sobre a função adobe.target.getOffers(options) para at.js. '
keywords: adobe.target.notification; elemento; seletor; notificação; extensão
seo-description: Informações sobre a função adobe.target.getOffers(options) da biblioteca at.js de JavaScript do Adobe Target.
seo-title: Informações sobre a função adobe.target.getOffers(options) da biblioteca at.js de JavaScript do Adobe Target.
solution: Target
subtopic: Introdução
title: adobe.target.getOffers(options)
topic: Padrão
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# adobe.target.getOffers(options) - at.js 2.x

Essa função permite que você recupere várias ofertas passando em várias mboxes. Além disso, várias ofertas podem ser recuperadas para todas as exibições em atividades ativas.

>[!NOTE]
>
>Essa função foi introduzida com a at.js 2.x. Essa função não está disponível para a at.js versão 1.*x*.

| Chave | Tipo | Obrigatório? | Descrição |
| --- | --- | --- | --- |
| consumerId | String | Não | O valor padrão é a mbox global do cliente se não for fornecida. Essa chave é usada para gerar a ID de dados complementares usada para integração A4T. |
| solicitação | Objeto | Sim | Consulte Tabela de solicitações abaixo. |
| timeout | Número | Não | tempo limite da solicitação. Se não for especificado, o tempo limite padrão da at.js será usado. |

## Solicitação

| Nome do campo | Obrigatório? | Limitações | Descrição |
| --- | --- | --- | --- |
| solicitação &gt; id | Não |  | Um de `tntId`, `thirdPartyId` ou `marketingCloudVisitorId` é obrigatório. |
| Solicitação &gt; id &gt; thirdPartyId | Não | Tamanho máximo = 128 |  |  |
| Request &gt; experiencecloud | Não |  |  |
| Request &gt; experiencecloud &gt; analytics | Não |  | Integração do Adobe Analytics |
| Solicitação &gt; experiencecloud &gt; analytics &gt; registro | Não | O seguinte deve ser implementado na página:<ul><li>Serviço de ID de visitante</li><li>Appmeasurement. js</li></ul> | The following values are supported:<br>**client_side**: When specified, an analytics payload will be returned to the caller which should be used to send to Adobe Analytics via the Data Insertion API.<br>**server_ side**: Esse é o valor padrão em que o backend do Target e do Analytics usará a SDID para unir as chamadas para fins de relatório. |
| Request &gt; pré-busca | Não |  |  |
| Solicitação &gt; pré-busca &gt; exibições | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome`<=` 128<br>Tamanho do valor `<=` 5000<br>O nome não deve começar com "perfil"<br>Nomes não permitidos: "orderId", "orderTotal", "productPurchasedId" | Transmita os parâmetros a serem usados para recuperar exibições relevantes nas atividades ativas. |
| Solicitação &gt; pré-busca &gt; exibições &gt; profileParameters | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=` 5000 <br>O nome não deve começar com "perfil" | Transmita os parâmetros a serem usados para recuperar exibições relevantes nas atividades ativas. |
| Solicitação &gt; pré-busca &gt; exibições &gt; produto | Não |  |  |
| Solicitação &gt; pré-busca &gt; exibições &gt; produto -&gt; id | Não | Não deixar em branco<br>tamanho máximo = 128 | Transmita as IDs do produto a serem usadas para recuperar exibições relevantes nas atividades ativas. |
| Solicitação &gt; pré-busca &gt; exibições &gt; produto &gt; categoryId | Não | Não deixar em branco<br>tamanho máximo = 128 | Transmita as IDs de categoria do produto a serem usadas para recuperar exibições relevantes nas atividades. |
| Solicitação &gt; pré-busca &gt; exibições &gt; ordem | Não |  |  |
| Solicitação &gt; pré-busca &gt; exibições &gt; ordem &gt; id | Não | Tamanho máximo = 250 | Transmita as IDs da ordem a serem usadas para recuperar exibições relevantes nas atividades ativas. |
| Solicitação &gt; pré-busca &gt; exibições &gt; ordem &gt; total | Não | Total`>=` 0 | Transmita os totais da ordem a serem usados para recuperar exibições relevantes nas atividades ativas. |
| Solicitação &gt; pré-busca &gt; exibições &gt; ordem &gt; purchasedProductIds | Não | Nenhum valor em branco<br>Tamanho máximo de cada valor 50<br>Concatenado e separado por vírgula<br>Tamanho total das IDs do produto `<=` 250 | Transmita as IDs do produto adiquirido a serem usadas para recuperar exibições relevantes nas atividades ativas. |
| Solicitação &gt; executar | Não |  |  |
| Solicitação &gt; executar &gt; pageLoad | Não |  |  |
| Solicitação &gt; executar &gt; pageLoad &gt; parâmetros | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=` 5000<br>O nome não deve começar com "perfil".<br>Nomes não permitidos: "orderId", "orderTotal", "productPurchasedId" | Recupere as ofertas com os parâmetros especificados quando a página for carregada. |
| Solicitação &gt; executar &gt; pageLoad &gt; profileParameters | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=`256<br>O nome não deve começar com "perfil". | Recupere as ofertas com os parâmetros do perfil especificados quando a página for carregada. |
| Solicitação &gt; executar &gt; pageLoad &gt; produto | Não |  |  |
| Solicitação &gt; executar &gt; pageLoad &gt; produto -&gt; id | Não | Não deixar em branco<br>Tamanho máximo = 128 | Recupere as ofertas com as IDs do produto especificadas quando a página for carregada. |
| Solicitação &gt; executar &gt; pageLoad &gt; produto &gt; categoryId | Não | Não deixar em branco<br>Tamanho máximo = 128 | Recupere as ofertas com as IDs de categoria do produto especificadas quando a página for carregada. |
| Solicitação &gt; executar &gt; pageLoad &gt; ordem | Não |  |  |
| Solicitação &gt; executar &gt; pageLoad &gt; order &gt; id | Não | Tamanho máximo = 250 | Recupere as ofertas com as IDs da ordem especificadas quando a página for carregada. |
| Solicitação &gt; executar &gt; pageLoad &gt; ordem &gt; total | Não | `>=` 0 | Recupere as ofertas com os totais da ordem especificados quando a página for carregada. |
| Solicitação &gt; executar &gt; pageLoad &gt; ordem &gt; purchasedProductIds | Não | Nenhum valor em branco<br>Tamanho máximo de cada valor 50<br>Concatenado e separado por vírgula<br>Tamanho total das IDs do produto `<=` 250 | Recupere as ofertas com as IDs do produto adquirido especificadas quando a página for carregada. |
| Solicitação &gt; executar &gt; mboxes | Não | Tamanho máximo = 50<br>Sem elementos nulos |  |
| Solicitação &gt; executar &gt; mboxes &gt; mbox | Sim | Não deixar em branco<br>Nenhum sufixo '-clicado'<br>Tamanho máximo = 250<br>Caracteres permitidos: `'-, ._\/=:;&!@#$%^&*()_+|?~[]{}'` | Nome da mbox. |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; índice | Sim | Não nulo<br>Exclusivo<br>`>=` 0 | Observe que o índice não representa a ordem em que as mboxes serão processadas. Da mesma forma que em uma página da Web com diversas mboxes regionais, a ordem em que serão processadas não pode ser especificada. |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; parâmetros | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=` 5000<br>O nome não deve começar com "perfil".<br>Nomes não permitidos: "orderId", "orderTotal", "productPurchasedId" | Recupere as ofertas de determinada mbox com os parâmetros especificados. |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; profileParameters | Não | Contagem máxima 50<br>Não deixar o nome em branco<br>Tamanho do nome `<=` 128<br>Tamanho do valor `<=`256<br>O nome não deve começar com "perfil". | Recupere as ofertas de determinada mbox com os parâmetros do perfil especificados. |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; produto | Não |  |  |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; produto &gt; id | Não | Não deixar em branco<br>Tamanho máximo = 128 | Recupere as ofertas de determinada mbox com as IDs do produto especificadas. |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; produto &gt; categoryId | Não | Não deixar em branco<br>Tamanho máximo = 128 | Recupere as ofertas de determinada mbox com as IDs de categoria do produto especificadas. |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; ordem | Não |  |  |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; ordem &gt; id | Não | Tamanho máximo = 250 | Recupere as ofertas de determinada mbox com as IDs da ordem especificadas. |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; ordem &gt; total | Não | `>=` 0 | Recupere as ofertas de determinada mbox com os totais da ordem especificados. |
| Solicitação &gt; executar &gt; mboxes &gt; mbox &gt; ordem &gt; purchasedProductIds | Não | Nenhum valor em branco<br>Tamanho máximo de cada valor = 50<br>Concatenado e separado por vírgula<br>Tamanho total das IDs do produto `<=` 250 | Recupere as ofertas de determinada mbox com as IDs do produto adquirido da ordem especificadas. |

## Chamada `getOffers()` para todas as exibições

```
adobe.target.getOffers({
    prefetch: {
      views: []
    }
  }
});
```

## Chamada `getOffers()` para recuperar as exibições mais recentes com os parâmetros e parâmetros do perfil transmitidos

```
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

## Chamada `getOffers()` para recuperar as mboxes com os parâmetros e parâmetros do perfil transmitidos.

```
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

## Chamar getoffers () para recuperar a carga do Analytics no lado do cliente

```
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

```
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

The payload can then be forwarded to Adobe Analytics via the [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Buscar e renderizar dados de várias mboxes via getOffers() e applyOffers() {#multiple}

A at.js 2.x permite buscar várias mboxes por meio da API de `getOffers()`. Você também pode buscar dados de várias mboxes e, em seguida, usar o `applyOffers()` para renderizá-los em diferentes locais identificados por um seletor de CSS.

O exemplo a seguir mostra uma página HTML simples com a at.js 2.x implementada:

```
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

```
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

* mbox1 &gt; CSS selector #container1
* mbox2 &gt; CSS selector #container2
* mbox3 &gt; CSS selector #container3

Este exemplo usa a variável de contagem para criar os seletores de CSS. Em um cenário real, você pode usar um mapeamento diferente entre o seletor de CSS e a mbox.

Observe que este exemplo usa `prefetch > mboxes`, mas você também pode usar `execute > mboxes`. Certifique-se de que, se você usar a pré-busca em `getOffers()`, também deverá usá-la na invocação de `applyOffers()`.
