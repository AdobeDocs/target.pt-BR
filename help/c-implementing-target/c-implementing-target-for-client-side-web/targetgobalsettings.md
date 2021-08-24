---
keywords: serverstate, targetGlobalSettings, targetglobalsettings, globalSettings, globalsettings, configurações globais, at.js, funções, função, clientCode, clientcode, serverDomain, serverdomain, cookieDomain, cookiedomain, crossDomain, crossDomain, timeout, globalMboxAutoCreate, visitorApiTimeout, defaultContentStent Estilo;defaultContentVisibleStyle;bodyHiddenStyle;bodyHidingEnabled;imsOrgId;secureOnly;overrideMboxEdgeServer;overrideMboxEdgeServerTimeout;optout;opt out;seletorsPollingTimeout;dataProviders;Hybrid Personalization device IdLifetime
description: Use a função targetGlobalSettings() para as APIs de Adobe [!DNL Target] at.js JavaScript library to override settings instead of using the [!DNL Target] UI ou REST.
title: Como uso a função targetGlobalSettings() ?
feature: at.js
role: Developer
exl-id: 14080cf6-6a15-4829-b95d-62c068898564
source-git-commit: eddde1bae345e2e28ca866662ba9664722dedecd
workflow-type: tm+mt
source-wordcount: '2317'
ht-degree: 31%

---

# targetGlobalSettings()

Você pode substituir as configurações na biblioteca at.js usando `targetGlobalSettings()`, em vez de definir as configurações na [!DNL Target] interface do usuário Standard/Premium ou usar REST APIs.

## Configurações {#section_42C759AE9B524A43B8659018677224B8}

É possível anular pelas seguintes configurações:

### bodyHiddenStyle

* **Tipo**: String
* **Valor** padrão: body { opacity: 0 }
* **Descrição**: Usado apenas quando  `globalMboxAutocreate === true` para minimizar a chance de cintilação.

   Para obter mais informações, consulte [Como o at.js gerencia a cintilação](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md).

### bodyHidingEnabled

* **Tipo**: Booleano
* **Valor** padrão: true
* **Descrição**: Usado para controlar a cintilação quando  `target-global-mbox` é usada para entregar ofertas criadas no Visual Experience Composer, também conhecido como ofertas visuais.

### clientCode

* **Tipo**: String
* **Valor** padrão: Valor definido pela interface do usuário.
* **Descrição**: Representa o código de cliente.

### cookieDomain

* **Tipo**: String
* **Valor** padrão: Se possível, defina para o domínio de nível superior.
* **Descrição**: Representa o domínio usado ao salvar cookies.

### crossDomain

* **Tipo**: String
* **Valor** padrão: Valor definido pela interface do usuário.
* **Descrição**: Indica se o rastreamento entre domínios está ativado ou não. Os valores permitidos são: desativado, ativado ou somente x.

### cspScriptNonce

* **Tipo**: Consulte a Política  [de segurança de conteúdo ](#content-security) abaixo.
* **Valor** padrão: Consulte a Política  [de segurança de conteúdo ](#content-security) abaixo.
* **Descrição**: Consulte a Política  [de segurança de conteúdo ](#content-security) abaixo.

### cspStyleNonce

* **Tipo**: Consulte a Política  [de segurança de conteúdo ](#content-security) abaixo.
* **Valor** padrão: Consulte a Política  [de segurança de conteúdo ](#content-security) abaixo.
* **Descrição**: Consulte a Política  [de segurança de conteúdo ](#content-security) abaixo.

### dataProviders

* **Tipo**: Consulte  [os ](#data-providers) provedores de dados abaixo.
* **Valor** padrão: Consulte  [os ](#data-providers) provedores de dados abaixo.
* **Descrição**: Consulte  [os ](#data-providers) provedores de dados abaixo.

### decisioningMethod {#on-device-decisioning}

* **Tipo**: String
* **Valor** padrão: lado do servidor
* **Outros valores**: no dispositivo, híbrido
* **Descrição**: Consulte Métodos de decisão abaixo.

   **Métodos de decisão**

   Com a decisão no dispositivo, o Target introduz uma nova configuração chamada [!UICONTROL Método de decisão] que determina como a at.js fornece suas experiências. O `decisioningMethod` tem três valores: somente do lado do servidor, somente no dispositivo e híbrido. Quando `decisioningMethod` é definido em `targetGlobalSettings()`, ele age como o método de decisão padrão para todas as [!DNL Target] decisões.

   **[!UICONTROL Somente]** no lado do servidor:

   [!UICONTROL O lado do servidor ] é somente o método de decisão padrão definido imediatamente quando o at.js 2.5+ é implementado e implantado em suas propriedades da Web.

   Usar [!UICONTROL somente do lado do servidor] como configuração padrão significa que todas as decisões são tomadas na rede de borda [!DNL Target], que envolve uma chamada de servidor de bloqueio. Essa abordagem pode introduzir latência incremental, mas também oferece benefícios significativos, como fornecer a você a capacidade de aplicar os recursos de aprendizado de máquina do Target que incluem as atividades de [Recommendations](/help/c-recommendations/recommendations.md), [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) e [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md).

   Além disso, aprimorar suas experiências personalizadas usando o perfil de usuário do Target, que é persistente em sessões e canais, pode fornecer resultados avançados para sua empresa.

   Por fim, [!UICONTROL somente no lado do servidor] permite usar a Adobe Experience Cloud e refinar públicos-alvo que podem ser direcionados por meio de segmentos do Audience Manager e Adobe Analytics.

   **[!UICONTROL Somente]** no dispositivo:

   [!UICONTROL O On-Device ] é apenas o método de decisão que deve ser definido no at.js 2.5+, quando a tomada de decisão no dispositivo deve ser usada somente em suas páginas da Web.

   O On-device decisioning pode fornecer suas experiências e atividades de personalização a uma velocidade extremamente rápida, pois as decisões são tomadas a partir de um artefato de regras em cache que contém todas as suas atividades qualificadas para decisões no dispositivo.

   Para saber mais sobre quais atividades se qualificam para decisões no dispositivo, consulte a seção recursos compatíveis .

   Esse método de decisão deve ser usado somente se o desempenho for altamente crítico em todas as páginas que exigem decisões de [!DNL Target]. Além disso, lembre-se de que, quando esse método de decisão for selecionado, suas atividades [!DNL Target] que não se qualificam para a tomada de decisão no dispositivo não serão entregues ou executadas. A biblioteca at.js 2.5+ está configurada para procurar somente o artefato de regras em cache para tomar decisões.

   **Híbrido**:

    O Hybridis é o método de decisão que deve ser definido no at.js 2.5+ quando a decisão no dispositivo e as atividades que exigem uma chamada de rede para a rede do Adobe Target Edge devem ser executadas.

   Ao gerenciar atividades de decisão no dispositivo e atividades no lado do servidor, pode ser um pouco complicado e entediante ao pensar em como implantar e provisionar [!DNL Target] em suas páginas. Com híbrido como o método de decisão, [!DNL Target] sabe quando deve fazer uma chamada de servidor para a rede do Adobe Target Edge para atividades que exigem execução no lado do servidor e também quando executar apenas decisões no dispositivo.

   O artefato de regras JSON inclui metadados para informar à at.js se uma mbox tem uma atividade do lado do servidor em execução ou uma atividade de decisão no dispositivo. Esse método de decisão garante que as atividades que você pretende entregar rapidamente sejam realizadas por meio de decisões no dispositivo e para atividades que exigem personalização mais poderosa orientada por ML, essas atividades são realizadas por meio da rede Adobe Target Edge.

### defaultContentHiddenStyle

* **Tipo**: String
* **Valor** padrão: visibility: oculto
* **Descrição**: Usado apenas para mboxes de encapsulamento que usam DIV com nome de classe &quot;mboxDefault&quot; e são executadas via  `mboxCreate()`,  `mboxUpdate()` ou  `mboxDefine()` para ocultar conteúdo padrão.

### defaultContentVisibleStyle

* **Tipo**: String
* **Valor** padrão: visibility: visível
* **Descrição**: Usado apenas para mboxes de encapsulamento que usam DIV com nome de classe &quot;mboxDefault&quot; e são executadas via  `mboxCreate()`,  `mboxUpdate()` ou  `mboxDefine()` para revelar uma oferta aplicada, caso exista, ou conteúdo padrão.

### deviceIdLifetime

* **Tipo**: Número
* **Valor** padrão: 63244800000 ms = 2 anos
* **Descrição**: A quantidade de tempo  `deviceId` é mantida nos cookies.

>[!NOTE]
>
>A configuração deviceIdLifetime pode ser substituída na at.js versão 2.3.1 ou posterior.

### ativado

* **Tipo**: Booleano
* **Valor** padrão: true
* **Descrição**: Quando habilitada, uma  [!DNL Target] solicitação para recuperar experiências e a manipulação de DOM para renderizar as experiências é executada automaticamente. Além disso, as chamadas [!DNL Target] podem ser executadas manualmente por `getOffer(s)` / `applyOffer(s)`.

   Quando desativadas, as solicitações [!DNL Target] não são executadas automática ou manualmente.

### globalMboxAutoCreate

* **Tipo**: Número
* **Valor** padrão: Valor definido pela interface do usuário.
* **Descrição**: Indica se a solicitação global de mbox deve ser acionada ou não.

### imsOrgId

* **Tipo**: String
* **Valor** padrão: true
* **Descrição**: Representa a ID da ORG IMS.

### optinEnabled

* **Tipo**: Booleano
* **Valor** padrão: false
* **Descrição**:  [!DNL Target] O oferece suporte à funcionalidade de opt-in por meio do  [!DNL Adobe Experience Platform] para ajudar a apoiar a estratégia de gerenciamento de consentimento. A funcionalidade de opt-in permite que os clientes controlem como e quando a tag do [!DNL Target] é acionada. Além disso, há uma opção por meio do [!DNL Adobe Experience Platform] para pré-aprovar a tag do [!DNL Target]. Para ativar a capacidade de usar o Opt-in na biblioteca at.js [!DNL Target], adicione a configuração `optinEnabled=true` . Em [!DNL Adobe Experience Platform] você deve selecionar &quot;ativar&quot; na lista suspensa [!UICONTROL GDPR Opt-In] na exibição de instalação da extensão. Consulte a [documentação do Adobe Experience Platform](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) para obter mais detalhes. Para obter mais informações sobre essa configuração, pois está relacionada às regulamentações de privacidade e proteção de dados, incluindo o Regulamento Geral sobre a Proteção de Dados (GDPR) da União Europeia e a Lei de Privacidade do Consumidor da Califórnia (CCPA), consulte [Privacidade e regulamentos sobre proteção de dados](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

### optoutEnabled

* **Tipo**: Booleano
* **Valor** padrão: false
* **Descrição**: Indica se o Target deve chamar a  `isOptedOut()` função da API de visitante. Isso é parte da ativação do gráfico de dispositivos.

### overrideMboxEdgeServer

* **Tipo**: Booleano
* **Valor** padrão: true (true que começa com a at.js versão 1.6.2)
* **Descrição**: Indica se devemos usar  `<clientCode>.tt.omtrdc.net` domínio ou  `mboxedge<clusterNumber>.tt.omtrdc.net` domínio.

   Se este valor for true, o domínio `mboxedge<clusterNumber>.tt.omtrdc.net` será salvo em um cookie. No momento, não está funcionando com [CNAME](/help/c-implementing-target/c-considerations-before-you-implement-target/implement-cname-support-in-target.md) ao usar versões da at.js anteriores à at.js 1.8.2 e à at.js 2.3.1. Se isso for um problema para você, considere [atualizar a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md) para uma versão mais recente e compatível.

### overrideMboxEdgeServerTimeout

* **Tipo**: Número
* **Valor** padrão: 1860000 => 31 minutos
* **Descrição**: Indica a vida útil do cookie que contém o  `mboxedge<clusterNumber>.tt.omtrdc.net` valor .

### pageLoadEnabled

* **Tipo**: Booleano
* **Valor** padrão: true
* **Descrição**: Quando ativado, recupere automaticamente as experiências que devem ser retornadas ao carregar a página.

### secureOnly

* **Tipo**: Booleano
* **Valor** padrão: false
* **Descrição**: Indica se a at.js deve usar somente HTTPS ou pode alternar entre HTTP e HTTPS com base no protocolo da página.

### selectorsPollingTimeout

* **Tipo**: Número
* **Valor** padrão: 5000 ms = 5 s
* **Descrição**: Na at.js 0.9.6,  [!DNL Target] introduziu essa nova configuração que pode ser anulada via  `targetGlobalSettings`.

   A configuração `selectorsPollingTimeout` representa quanto tempo o cliente está disposto a esperar até que todos os elementos identificados por seletores sejam exibidos na página.

   Atividades criadas pelo Visual Experience Composer (VEC) têm ofertas que contêm seletores.

### serverDomain

* **Tipo**: String
* **Valor** padrão: Valor definido pela interface do usuário.
* **Descrição**: Representa o servidor do Target Edge.

### serverState

* **Tipo**: Consulte  [Personalização híbrida ](#server-state) abaixo.
* **Valor** padrão: Consulte  [Personalização híbrida ](#server-state) abaixo.
* **Descrição**: Consulte  [Personalização híbrida ](#server-state) abaixo.

### timeout

* **Tipo**: Número
* **Valor** padrão: Valor definido pela interface do usuário.
* **Descrição**: Representa o tempo limite da solicitação de  [!DNL Target] borda.

### viewsEnabled

* **Tipo**: Booleano
* **Valor** padrão: true
* **Descrição**: Quando ativado, recupera automaticamente as exibições que devem ser retornadas no carregamento da página. As exibições são compatíveis com o at.js 2.somente *x.*

### visitorApiTimeout

* **Tipo**: Número
* **Valor** padrão: 2000 ms = 2 s
* **Descrição**: Representa o tempo limite  [!UICONTROL da ] solicitação da API de visitante.

## Uso {#section_9AD6FA3690364F7480C872CB55567FB0}

Essa função pode ser definida antes que at.js seja carregada ou em **[!UICONTROL Administration]** > **[!UICONTROL Implementation]** > **[!UICONTROL Editar configurações da at.js]** > **[!UICONTROL Configurações do código]** > **[!UICONTROL Cabeçalho da biblioteca]**.

O campo Cabeçalho da biblioteca permite que você entre no JavaScript do formulário gratuito. O código de personalização deve ser semelhante ao seguinte exemplo:

```javascript
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
| [Uso de provedores de dados do Adobe Target](https://helpx.adobe.com/br/target/kt/using/dataProviders-atjs-feature-video-use.html) | Os provedores de dados são uma função que permite passar dados de terceiros facilmente para o Target. Um terceiro pode ser um serviço de clima, um DMP ou até mesmo o seu próprio serviço Web. É possível então usar esses dados para criar públicos-alvo, conteúdo de direcionamento e enriquecer o perfil do visitante. |
| [Implementação de provedores de dados no Adobe Target](https://helpx.adobe.com/br/target/kt/using/dataProviders-atjs-technical-video-implement.html) | Detalhes de implementação e exemplos de como usar o recurso de provedores de dados do Adobe Target para recuperar dados de provedores de dados de terceiros e passá-los na solicitação do Target. |

A configuração `window.targetGlobalSettings.dataProviders` é uma matriz de provedores de dados.

Cada provedor de dados tem a seguinte estrutura:

| Chave | Tipo | Descrição |
|--- |--- |--- |
| name | String | Nome do provedor. |
| version | String | Versão do provedor. Essa tecla será usada para evolução do provedor. |
| timeout | Número | Representa o tempo limite do provedor se essa for uma solicitação de rede.  Essa tecla é opcional. |
| provider | Função | A função que contém a lógica de obtenção de dados do provedor.<br>A função tem um único parâmetro obrigatório: `callback`. O parâmetro retorno de chamada é uma função que só deve ser invocada quando os dados forem obtidos com êxito ou houver um erro.<br>O retorno de chamada espera dois parâmetros:<ul><li>error: Indica que ocorreu um erro. Se tudo estiver OK, este parâmetro deve ser definido como nulo.</li><li>parâmetros: Um objeto JSON, representando os parâmetros que serão enviados em uma solicitação do Target.</li></ul> |

O exemplo a seguir mostra onde o provedor de dados está usando a execução sincrônica:

```javascript
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

```javascript
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

```javascript
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

## Política de segurança de conteúdo {#content-security}

O at.js 2.3.0+ suporta a configuração de nonces da Política de segurança de conteúdo em tags SCRIPT e STYLE anexadas ao DOM da página ao aplicar ofertas do Target entregues.

As ações SCRIPT e STYLE devem ser definidas em `targetGlobalSettings.cspScriptNonce` e `targetGlobalSettings.cspStyleNonce` de forma correspondente, antes do carregamento de at.js 2.3.0+. Veja um exemplo abaixo:

```javascript
...
<head>
 <script nonce="<script_nonce_value>">
window.targetGlobalSettings = {
  cspScriptNonce: "<csp_script_nonce_value>",
  cspStyleNonce: "<csp_style_nonce_value>"
};
 </script>
 <script nonce="<script_nonce_value>" src="at.js"></script>
...
</head>
...
```

Depois que as configurações `cspScriptNonce` e `cspStyleNonce` são especificadas, o at.js 2.3.0+ as define como atributos nonce em todas as tags SCRIPT e STYLE anexadas ao DOM ao aplicar ofertas do Target.

## Personalização híbrida {#server-state}

`serverState` é uma configuração disponível no at.js v2.2+ que pode ser usada para otimizar o desempenho da página quando uma integração híbrida do Target é implementada. A integração híbrida significa que você está usando a at.js v2.2+ no lado do cliente e a API de entrega ou um SDK do Target no lado do servidor para fornecer experiências. O `serverState` fornece ao at.js v2.2+ a capacidade de aplicar experiências diretamente de conteúdo buscado no lado do servidor e retornado ao cliente como parte da página que está sendo veiculada.

### Pré-requisitos

Você deve ter uma integração híbrida de [!DNL Target].

* **Lado** do servidor: Você deve usar a nova  [API ](https://developers.adobetarget.com/api/delivery-api/) de entrega ou os  [SDKs do Target](https://developers.adobetarget.com/api/delivery-api/#section/SDKs).
* **Lado** do cliente: Você deve usar a  [at.js versão 2.2 ou posterior](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

### Amostras de código

Para entender melhor como isso funciona, consulte os exemplos de código abaixo que você teria em seu servidor. O código assume que você está usando o [SDK Node.js do Target](https://github.com/adobe/target-nodejs-sdk).

```javascript
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

Um exemplo de JSON de objeto `serverState` para visualização de busca prévia é exibido da seguinte maneira:

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

Depois que a página é carregada no navegador, a at.js aplica todas as [!DNL Target] ofertas de `serverState` imediatamente, sem acionar chamadas de rede contra a borda [!DNL Target]. Além disso, a at.js pré-oculta apenas os elementos DOM para os quais as [!DNL Target] ofertas estão disponíveis no conteúdo buscado no lado do servidor, afetando positivamente o desempenho do carregamento da página e a experiência do usuário final.

### Observações importantes

Considere o seguinte ao usar `serverState`:

* No momento, a at.js v2.2 oferece suporte somente para experiências via serverState para:

   * Atividades criadas pelo VEC que são executadas no carregamento da página.
   * Visualizações pré-buscadas.

      No caso de SPA usando [!DNL Target] Exibições e `triggerView()` na API at.js, a at.js v2.2 armazena em cache o conteúdo de todas as Exibições buscadas previamente no lado do servidor e as aplica assim que cada Exibição é acionada por meio de `triggerView()`, novamente sem acionar chamadas adicionais de busca de conteúdo para o Target.

   * **Observação**: Atualmente, as mboxes recuperadas no lado do servidor não são compatíveis com o  `serverState`.

* Ao aplicar `serverState `ofertas, at.js considera as configurações `pageLoadEnabled` e `viewsEnabled`, por exemplo, as ofertas de Carregamento de página não serão aplicadas se a configuração `pageLoadEnabled` for falsa.

   Para ativar essas configurações, ative o botão em **[!UICONTROL Administration] > [!UICONTROL Implementation] > [!UICONTROL Edit] > [!UICONTROL Page Load Enabled]**.

   ![Configurações ativadas para carregamento de página](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/page-load-enabled-setting.png)

* Se estiver usando `serverState` e `<script>` tags no conteúdo retornado, verifique se o seu conteúdo HTML usa `<\/script>` em vez de `</script>`. Se você usar `</script>`, o navegador interpretará `</script>` como o fim em um SCRIPT em linha e poderá quebrar a página HTML.

### Recursos adicionais

Para saber mais sobre como o `serverState` funciona, confira os seguintes recursos:

* [Código de exemplo](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/advanced-atjs-integration-serverstate).
* [Aplicativo de página única (SPA) com aplicativo de amostra  `serverState`](https://github.com/Adobe-Marketing-Cloud/target-node-client-samples/tree/master/react-shopping-cart-demo).
