---
keywords: serverstate;targetGlobalSettings;targetglobalsettings;globalSettings;globalsettings;global settings;at.js;functions;function;clientCode;clientcode;serverDomain;serverdomain;cookieDomain;cookiedomain;crossDomain;crossdomain;timeout;globalMboxAutoCreate;visitorApiTimeout;defaultContentHiddenStyle;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optoutEnabled;optout;opt out;selectorsPollingTimeout;dataProviders
description: Informações sobre a função targetGlobalSettings() da biblioteca at.js de JavaScript do Adobe Target.
title: Informações sobre a função targetGlobalSettings() da biblioteca at.js de JavaScript do Adobe Target.
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: 5042acd5b646d3debf0d2be79bf317401a98763e

---


# targetGlobalSettings()

Você pode substituir as configurações na biblioteca at.js usando `targetGlobalSettings()`, em vez de definir as configurações na [!DNL Target] interface do usuário Standard/Premium ou usar REST APIs.

Há casos de uso, especialmente quando at.js for entregue via [!DNL Dynamic Tag Management] (DTM) quando você desejar anular algumas das configurações.

## Configurações {#section_42C759AE9B524A43B8659018677224B8}

É possível anular pelas seguintes configurações:

| Configurações | Tipo | Valor padrão | Descrição |
|--- |--- |--- |--- |
| serverState | Consulte &quot;serverState&quot; abaixo. | Consulte &quot;serverState&quot; abaixo. | Consulte &quot;serverState&quot; abaixo. |
| clientCode | String | Valor definido via IU | Representa o código de cliente |
| serverDomain | String | Valor definido via IU | Representa o servidor do Target Edge |
| cookieDomain | String | Se possível, defina para o domínio de nível superior | Representa o domínio usado ao salvar cookies |
| crossDomain | String | Valor definido via IU | Indica se o monitoramento de domínio cruzado está ativado ou não.<br>Os valores permitidos são:<ul><li>desativado</li><li>ativado</li><li>somente x</li></ul> |
| timeout | Número | Valor definido via IU | Representa o tempo limite da solicitação do Target Edge |
| globalMboxAutoCreate | Booleano | Valor definido via IU | Indica se a solicitação global de mbox deve ser disparada ou não |
| visitorApiTimeout | Número | 2000 ms = 2 s | Representa o tempo limite da solicitação da API de visitante |
| ativado | Booleano | true | Quando ativada, uma solicitação do Target para recuperar experiências e a manipulação do DOM para renderizar as experiências é executada automaticamente. Além disso, as chamadas do Target podem ser executadas manualmente via `getOffer(s)` / `applyOffer(s)`<br>Quando desativadas, as solicitações do Target não são executadas automática ou manualmente |
| pageLoadEnabled | Booleano | true | Quando ativado, recupera automaticamente experiências que devem ser retornadas ao carregar a página |
| viewsEnabled | Booleano | true | Quando ativado, recupera automaticamente as exibições que devem ser retornadas no carregamento da página. As exibições são suportadas em at.js 2.somente *x* |
| defaultContentHiddenStyle | String | visibility: hidden | Usado apenas para mboxes de encapsulamento que usam DIV com nome de classe &quot;mboxDefault&quot; e são executadas via `mboxCreate()`, `mboxUpdate()` ou `mboxDefine()` para ocultar conteúdo padrão |
| defaultContentVisibleStyle | String | visibility: visible | Usado apenas para mboxes de encapsulamento que usam DIV com nome de classe &quot;mboxDefault&quot; e são executadas via `mboxCreate()`, `mboxUpdate()` ou `mboxDefine()` para revelar uma oferta aplicada, caso exista, ou conteúdo padrão |
| bodyHiddenStyle | String | body { opacity: 0 } | Usado apenas quando `globalMboxAutocreate === true` para minimizar a chance de cintilação.<br>Para obter mais informações, consulte [Como o at.js gerencia a cintilação](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md). |
| bodyHidingEnabled | Booleano | true | Usado para controlar a cintilação quando `target-global-mbox` é usada para entregar ofertas criadas no Visual Experience Composer, também conhecido como ofertas visuais |
| imsOrgId | String | ID da ORG IMS | Representa a ID da ORG IMS |
| secureOnly | Booleano | false | Indica se a at.js deve usar somente HTTPS ou pode alternar entre HTTP e HTTPS com base no protocolo da página. |
| overrideMboxEdgeServer | Booleano | true (true que começa com a at.js versão 1.6.2) | Indica se devemos usar o domínio `<clientCode>.tt.omtrdc.net` ou o domínio `mboxedge<clusterNumber>.tt.omtrdc.net`.<br>Se este valor for true, o domínio `mboxedge<clusterNumber>.tt.omtrdc.net` será salvo em um cookie |
| overrideMboxEdgeServerTimeout | Número | 1860000 => 31 minutos | Indica a vida útil do cookie que contém o valor `mboxedge<clusterNumber>.tt.omtrdc.net`. |
| optoutEnabled | Booleano | false | Indica se o Target deve chamar a função `isOptedOut()` da API de visitante. Isso é parte da ativação do gráfico de dispositivos. |
| selectorsPollingTimeout | Número | 5000 ms = 5 s | Na at.js 0.9.6, o Target apresentou essa nova configuração que pode ser anulada via `targetGlobalSettings`.<br>`selectorsPollingTimeout` representa quanto tempo o cliente está disposto a esperar até que todos os elementos identificados por seletores sejam exibidos na página.<br>Atividades criadas pelo Visual Experience Composer (VEC) têm ofertas que contêm seletores. |
| dataProviders | Consulte &quot;Provedores de dados&quot; abaixo. | Consulte &quot;Provedores de dados&quot; abaixo. | Consulte &quot;Provedores de dados&quot; abaixo. |

## Uso {#section_9AD6FA3690364F7480C872CB55567FB0}

Esta função pode ser definida antes que at.js seja carregada ou em **[!UICONTROL Configurar]** > **[!UICONTROL Implementação]** > **[!UICONTROL Editar configurações da at.js]** > **[!UICONTROL Configurações do código]** > **[!UICONTROL Cabeçalho da biblioteca]**.

O campo Cabeçalho da biblioteca permite que você entre no JavaScript do formulário gratuito. O código de personalização deve ser semelhante ao seguinte exemplo:

```
window.targetGlobalSettings = {  
   timeout: 200, // using custom timeout  
   visitorApiTimeout: 500, // using custom API timeout  
   enabled: document.location.href.indexOf('https://www.adobe.com') >= 0 // enabled ONLY on adobe.com  
};
```

## Provedores de dados {#data-providers}

Essa configuração permite que clientes reúnam dados de provedores de dados de terceiros, como Demandbase, BlueKai e serviços personalizados, além de enviar os dados ao Target como parâmetros da mbox na solicitação global da mbox. Ela é compatível com a coleta de dados de múltiplos provedores via solicitações síncronas e assíncronas. Usar esta abordagem facilita o gerenciamento de cintilação ou conteúdo padrão da página, enquanto inclui tempos limites independentes para cada provedor para limitar o impacto sobre o desempenho da página

>[!NOTE]
>
>Os provedores de dados exigem o [!DNL at.js] 1.3 ou posterior.

Os seguintes vídeos contêm mais informações:

| Vídeo | Descrição |
|--- |--- |
| [Uso de provedores de dados do Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-feature-video-use.html) | Os provedores de dados são uma função que permite passar dados de terceiros facilmente para o Target. Um terceiro pode ser um serviço de clima, um DMP ou até mesmo o seu próprio serviço Web. É possível então usar esses dados para criar públicos-alvo, conteúdo de direcionamento e enriquecer o perfil do visitante. |
| [Implementação de provedores de dados no Adobe Target](https://helpx.adobe.com/target/kt/using/dataProviders-atjs-technical-video-implement.html) | Detalhes de implementação e exemplos de como usar o recurso de provedores de dados do Adobe Target para recuperar dados de provedores de dados de terceiros e passá-los na solicitação do Target. |

A configuração `window.targetGlobalSettings.dataProviders` é uma matriz de provedores de dados.

Cada provedor de dados tem a seguinte estrutura:

| Chave | Tipo | Descrição |
|--- |--- |--- |
| name | String | Nome do provedor. |
| version | String | Versão do provedor. Essa tecla será usada para evolução do provedor. |
| timeout | Número | Representa o tempo limite do provedor se essa for uma solicitação de rede.  Essa tecla é opcional. |
| provider | Função | A função que contém a lógica de obtenção de dados do provedor.<br>A função tem um único parâmetro obrigatório: `callback`. O parâmetro retorno de chamada é uma função que só deve ser invocada quando os dados forem obtidos com êxito ou houver um erro.<br>O retorno de chamada espera dois parâmetros:<ul><li>error: Indica que ocorreu um erro. Se tudo estiver OK, este parâmetro deve ser definido como nulo.</li><li>parâmetros: Um objeto JSON, representando os parâmetros que serão enviados em uma solicitação do Target.</li></ul> |

O exemplo a seguir mostra onde o provedor de dados está usando a execução sincrônica:

```
var syncDataProvider = { 
  name: "simpleDataProvider", 
  version: "1.0.0", 
  provider: function(callback) { 
    callback(null, {t1: 1}); 
  } 
}; 
  
window.targetGlobalSettings = { 
  dataProviders: [ 
    syncDataProvider 
  ] 
};
```

Após at.js processar `window.targetGlobalSettings.dataProviders`, a solicitação do Target conterá um novo parâmetro: `t1=1`.

O que segue é um exemplo se os parâmetros que você deseja adicionar à solicitação do Target forem obtidos de um serviço de terceiros, como Bluekai, Demandbase e daí por diante:

```
var blueKaiDataProvider = { 
   name: "blueKai", 
   version: "1.0.0", 
   provider: function(callback) { 
      // simulating network request 
     setTimeout(function() { 
       callback(null, {t1: 1, t2: 2, t3: 3}); 
     }, 1000); 
   } 
} 
  
window.targetGlobalSettings = { 
   dataProviders: [ 
      blueKaiDataProvider 
   ] 
};
```

Após at.js processar `window.targetGlobalSettings.dataProviders`, a solicitação do Target conterá novos parâmetros: `t1=1`, `t2=2` e `t3=3`.

O exemplo a seguir usa provedores de dados para coletar dados da API de tempo e enviá-los como parâmetros em uma solicitação do Target. A solicitação do Target terá parâmetros adicionais, como `country` e `weatherCondition`.

```
var weatherProvider = { 
      name: "weather-api", 
      version: "1.0.0", 
      timeout: 2000, 
      provider: function(callback) { 
        var API_KEY = "caa84fc6f5dc77b6372d2570458b8699"; 
        var lat = 44.426767399999996; 
        var lon = 26.1025384; 
        var url = "//api.openweathermap.org/data/2.5/weather?lang=en"; 
        var data = { 
          lat: lat, 
          lon: lon, 
          appId: API_KEY 
        } 
 
        $.ajax({ 
          type: "GET", 
                url: url, 
          dataType: "json", 
          data: data, 
          success: function(data) { 
            console.log("Weather data", data); 
            callback(null, { 
              country: data.sys.country, 
              weatherCondition: data.weather[0].main 
            }); 
          }, 
          error: function(err) { 
            console.log("Error", err); 
            callback(err); 
          } 
        });         
      } 
    }; 
 
    window.targetGlobalSettings = { 
      dataProviders: [weatherProvider] 
    };
```

Leve em consideração o seguinte ao trabalhar com a configuração `dataProviders`:

* Se os provedores de dados adicionados a `window.targetGlobalSettings.dataProviders` forem assíncronos, serão executados em paralelo. A solicitação da API de visitante será executada em paralelo com funções adicionadas a `window.targetGlobalSettings.dataProviders` para permitir um tempo mínimo de espera.
* at.js não tentará armazenar os dados em cache. Se o provedor de dados obtiver os dados apenas uma vez, deverá certificar-se de que os dados estão armazenados em cache e, quando a função de provedor for invocada, servir os dados do cache para a segunda invocação.

## serverState {#server-state}

`serverState` é uma configuração disponível em at.js v2.2+ que pode ser usada para otimizar o desempenho da página quando uma integração híbrida do Target é implementada. A integração híbrida significa que você está usando o at.js v2.2+ no lado do cliente e a API de entrega ou um SDK do Target no lado do servidor para fornecer experiências. `serverState` oferece ao at.js v2.2+ a capacidade de aplicar experiências diretamente do conteúdo obtido no lado do servidor e retornado ao cliente como parte da página que está sendo fornecida.

### Pré-requisitos

Você deve ter uma integração híbrida de [!DNL Target].

* **Do lado** do servidor:  Você deve usar a nova API [de](https://developers.adobetarget.com/api/delivery-api/) entrega ou SDKs [](https://developers.adobetarget.com/api/delivery-api/#section/SDKs)do Target.
* **Cliente**: Você deve usar [a versão 2.2 ou posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)do at.js.

### Amostras de código

Para entender melhor como isso funciona, consulte os exemplos de código abaixo que você teria em seu servidor. O código supõe que você esteja usando o SDK [do](https://github.com/adobe/target-nodejs-sdk)Target Node.js.

```
// First, we fetch the offers via Target Node.js SDK API, as usual
const targetResponse = await targetClient.getOffers(options);
// A successfull response will contain Target Delivery API request and response objects, which we need to set as serverState
const serverState = {
  request: targetResponse.request,
  response: targetResponse.response
};
// Finally, we should set window.targetGlobalSettings.serverState in the returned page, by replacing it in a page template, for example
const PAGE_TEMPLATE = `
<!doctype html>
<html>
<head>
  ...
  <script>
    window.targetGlobalSettings = {
      overrideMboxEdgeServer: true,
      serverState: ${JSON.stringify(serverState, null, " ")}
    };
  </script>
  <script src="at.js"></script>
</head>
...
</html>
`;
// Return PAGE_TEMPLATE to the client ...
```

Uma amostra de `serverState` objeto JSON para exibição de busca prévia é exibida da seguinte maneira:

```
{
 "request": {
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "context": {
   "channel": "web",
   "timeOffsetInMinutes": 0
  },
  "experienceCloud": {
   "analytics": {
    "logging": "server_side",
    "supplementalDataId": "7D3AA246CC99FD7F-1B3DD2E75595498E"
   }
  },
  "prefetch": {
   "views": [
    {
     "address": {
      "url": "my.testsite.com/"
     }
    }
   ]
  }
 },
 "response": {
  "status": 200,
  "requestId": "076ace1cd3624048bae1ced1f9e0c536",
  "id": {
   "tntId": "08210e2d751a44779b8313e2d2692b96.21_27"
  },
  "client": "testclient",
  "edgeHost": "mboxedge21.tt.omtrdc.net",
  "prefetch": {
   "views": [
    {
     "name": "home",
     "key": "home",
     "options": [
      {
       "type": "actions",
       "content": [
        {
         "type": "setHtml",
         "selector": "#app > DIV.app-container:eq(0) > DIV.page-container:eq(0) > DIV:nth-of-type(2) > SECTION.section:eq(0) > DIV.container:eq(1) > DIV.heading:eq(0) > H1.title:eq(0)",
         "cssSelector": "#app > DIV:nth-of-type(1) > DIV:nth-of-type(1) > DIV:nth-of-type(2) > SECTION:nth-of-type(1) > DIV:nth-of-type(2) > DIV:nth-of-type(1) > H1:nth-of-type(1)",
         "content": "<span style=\"color:#FF0000;\">Latest</span> Products for 2020"
        }
       ],
       "eventToken": "t0FRvoWosOqHmYL5G18QCZNWHtnQtQrJfmRrQugEa2qCnQ9Y9OaLL2gsdrWQTvE54PwSz67rmXWmSnkXpSSS2Q==",
       "responseTokens": {
        "profile.memberlevel": "0",
        "geo.city": "dublin",
        "activity.id": "302740",
        "experience.name": "Experience B",
        "geo.country": "ireland"
       }
      }
     ],
     "state": "J+W1Fq18hxliDDJonTPfV0S+mzxapAO3d14M43EsM9f12A6QaqL+E3XKkRFlmq9U"
    }
   ]
  }
 }
}
```

Depois que a página é carregada no navegador, o at.js aplica todas as [!DNL Target] ofertas `serverState` imediatamente, sem acionar chamadas de rede contra a [!DNL Target] borda. Além disso, o at.js oculta apenas os elementos DOM para os quais [!DNL Target] as ofertas estão disponíveis no conteúdo obtido no lado do servidor, afetando positivamente o desempenho da carga da página e a experiência do usuário final.

### Notas importantes

Considere o seguinte ao usar `serverState`:

* No momento, o at.js v2.2 suporta apenas a entrega de experiências via serverState para:

   * Atividades criadas pela VEC que são executadas no carregamento da página.
   * Exibições pré-buscadas.

      No caso de SPAs que usam [!DNL Target] Exibições e `triggerView()` na API at.js, o at.js v2.2 armazena em cache o conteúdo de todas as Exibições pré-buscadas no lado do servidor e as aplica assim que cada Exibição é acionada `triggerView()`, novamente sem acionar chamadas adicionais de busca de conteúdo para o Target.

   * **Observação**:  Atualmente, as mboxes recuperadas no servidor não são suportadas em `serverState`.

* Ao aplicar `serverState `ofertas, o at.js leva em consideração `pageLoadEnabled` e `viewsEnabled` configurações, por exemplo, as ofertas de carregamento de página não serão aplicadas se a `pageLoadEnabled` configuração for falsa.

   Para ativar essas configurações, ative a alternância em Configuração do **[UICONTROL > Implementação > Editar configurações > Carregamento de página ativado]**.

   ![Configurações Ativadas para Carregamento de Página](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

### Recursos adicionais

Para saber mais sobre como `serverState` funciona, consulte os seguintes recursos:

* [Código de exemplo](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Aplicativo de amostra de aplicativo de página única (SPA) com `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
