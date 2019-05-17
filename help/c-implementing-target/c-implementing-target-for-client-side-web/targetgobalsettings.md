---
description: 'Informações sobre a função targetglobalsettings () para at. js. '
keywords: adobe.target.notificação; elemento; seletor; notificação; extensão
seo-description: Informações sobre a função targetglobalsettings () da biblioteca do Adobe Target no javascript.
seo-title: Informações sobre a função targetglobalsettings () da biblioteca do Adobe Target no javascript.
solution: Target
subtopic: Introdução
title: targetGlobalSettings()
topic: Padrão
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# targetGlobalSettings()

Você pode substituir as configurações na biblioteca at.js usando `targetGlobalSettings()`, em vez de definir as configurações na [!DNL Target] interface do usuário Standard/Premium ou usar REST APIs.

Há casos de uso, especialmente quando at.js for entregue via [!DNL Dynamic Tag Management] (DTM) quando você desejar anular algumas das configurações.

## Configurações {#section_42C759AE9B524A43B8659018677224B8}

É possível anular pelas seguintes configurações:

| Configurações | Tipo | Valor padrão | Descrição |
|--- |--- |--- |--- |
| clientCode | String | Valor definido via IU | Representa o código de cliente |
| serverDomain | String | Valor definido via IU | Representa o servidor do Target Edge |
| cookieDomain | String | Se possível, defina para o domínio de nível superior | Representa o domínio usado ao salvar cookies |
| crossDomain | String | Valor definido via IU | Indica se o monitoramento de domínio cruzado está ativado ou não.<br>Os valores permitidos são:<ul><li>desativado</li><li>ativado</li><li>somente x</li></ul> |
| timeout | Número | Valor definido via IU | Representa o tempo limite da solicitação do Target Edge |
| globalMboxAutoCreate | Booleano | Valor definido via IU | Indica se a solicitação global de mbox deve ser disparada ou não |
| visitorApiTimeout | Número | 2000 ms = 2 s | Representa o tempo limite da solicitação da API de visitante |
| ativado | Booleano | true | Indica se at.js está ativada como biblioteca, ou seja, se ela deve executar algo ou não. Sendo o principal caso de uso dessa configuração a não autorização de uso de cookies ou outras decisões personalizadas que desativariam a funcionalidade at.js |
| defaultContentHiddenStyle | String | visibility: hidden | Usado apenas para mboxes de encapsulamento que usam DIV com nome de classe &quot;mboxDefault&quot; e são executadas via `mboxCreate()`, `mboxUpdate()` ou `mboxDefine()` para ocultar conteúdo padrão |
| defaultContentVisibleStyle | String | visibility: visible | Usado apenas para mboxes de encapsulamento que usam DIV com nome de classe &quot;mboxDefault&quot; e são executadas via `mboxCreate()`, `mboxUpdate()` ou `mboxDefine()` para revelar uma oferta aplicada, caso exista, ou conteúdo padrão |
| bodyHiddenStyle | String | body { opacity: 0 } | Usado apenas quando `globalMboxAutocreate === true` para minimizar a chance de cintilação.<br>Para obter mais informações, consulte [Como o at.js gerencia a cintilação](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/manage-flicker-with-atjs.md). |
| bodyHidingEnabled | Booleano | true | Usado para controlar a cintilação quando `target-global-mbox` é usada para entregar ofertas criadas no Visual Experience Composer, também conhecido como ofertas visuais |
| imsOrgId | String | ID da ORG IMS | Representa a ID da ORG IMS |
| secureOnly | Booleano | false | Indica se a at.js deve usar somente HTTPS ou pode alternar entre HTTP e HTTPS com base no protocolo da página. |
| overrideMboxEdgeServer | Booleano | true (true que começa com a at.js versão 1.6.2) | Indica se devemos usar o domínio `<clientCode>.tt.omtrdc.net` ou o domínio `mboxedge<clusterNumber>.tt.omtrdc.net`.<br>Se este valor for true, o domínio `mboxedge<clusterNumber>.tt.omtrdc.net` será salvo em um cookie |
| overrideMboxEdgeServerTimeout | Número | 1860000 =&gt; 31 minutos | Indica a vida útil do cookie que contém o valor `mboxedge<clusterNumber>.tt.omtrdc.net`. |
| optoutEnabled | Booleano | false | Indica se o Target deve chamar a função `isOptedOut()` da API de visitante. Isso é parte da ativação do gráfico de dispositivos. |
| selectorsPollingTimeout | Número | 5000 ms = 5 s | Na at.js 0.9.6, o Target apresentou essa nova configuração que pode ser anulada via `targetGlobalSettings`.<br>`selectorsPollingTimeout` representa quanto tempo o cliente está disposto a esperar até que todos os elementos identificados por seletores sejam exibidos na página.<br>Atividades criadas pelo Visual Experience Composer (VEC) têm ofertas que contêm seletores. |
| dataProviders | Consulte &quot;Provedores de dados&quot; abaixo. | Consulte &quot;Provedores de dados&quot; abaixo. | Consulte &quot;Provedores de dados&quot; abaixo. |

## Uso {#section_9AD6FA3690364F7480C872CB55567FB0}

Esta função pode ser definida antes que at.js seja carregada ou em **[!UICONTROL Configurar]** &gt; **[!UICONTROL Implementação]** &gt; **[!UICONTROL Editar configurações da at.js]** &gt; **[!UICONTROL Configurações do código]** &gt; **[!UICONTROL Cabeçalho da biblioteca]**.

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
| timeout | Número | Representa o tempo limite do provedor se essa for uma solicitação de rede. Essa tecla é opcional. |
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
