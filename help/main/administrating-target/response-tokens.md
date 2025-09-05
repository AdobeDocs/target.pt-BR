---
keywords: tokens de resposta;tokens;plugins;plug-ins;at.js;response;platform web sdk;google analytics
description: Saiba como usar tokens de resposta no [!DNL Adobe Target]  para obter informações específicas de saída para depuração e integração com ferramentas de terceiros.
title: O que são Tokens de resposta e como usá-los?
feature: Administration & Configuration
role: Admin
exl-id: d0c1e914-3172-466d-9721-fe0690abd30b
source-git-commit: a1617f64f0633a87ea4c1f8e5104a1d177df04e2
workflow-type: tm+mt
source-wordcount: '1622'
ht-degree: 24%

---

# Tokens de resposta

Os tokens de resposta permitem enviar automaticamente informações específicas do [!DNL Adobe Target] para a página da Web da sua marca. Essas informações podem incluir detalhes sobre atividade, oferta, experiência, perfil do usuário, informações geográficas e muito mais. Esses detalhes fornecem dados de resposta adicionais para compartilhar com ferramentas internas ou de terceiros ou usar para depuração.

Os tokens de resposta permitem escolher quais variáveis (em pares de valores chave) usar e depois habilitar eles para serem enviados como parte de uma resposta [!DNL Target]. Você habilita uma variável usando o switch e a variável é enviada com [!DNL Target] respostas, que podem ser validadas em chamadas de rede. Os tokens de resposta também funcionam no modo [!UICONTROL Preview].

Uma diferença importante entre plug-ins e tokens de resposta é que os plug-ins fornecem o JavaScript à página que é executada na entrega. Os tokens de resposta, no entanto, fornecem um objeto que pode ser lido e utilizado com o uso de ouvintes de eventos. A abordagem do token de resposta é mais segura e permite um desenvolvimento e manutenção mais fáceis de integrações de terceiros.

{{permissions-update}}

>[!NOTE]
>
>Os tokens de resposta estão disponíveis com a at.js versão 1.1 ou posterior.

| SDK do Target | Ações sugeridas |
|--- |--- |
| [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank} | Verifique se você está usando o Platform Web SDK versão 2.6.0 ou posterior. Para obter informações sobre como baixar a versão mais recente do Platform Web SDK, consulte [Instalar o SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR){target=_blank} na *visão geral do Platform Web SDK* guia. Para obter informações sobre a nova funcionalidade em cada versão do Platform Web SDK, consulte as [notas de versão](https://experienceleague.adobe.com/docs/experience-platform/edge/release-notes.html?lang=pt-BR) na *visão geral do Platform Web SDK*. |
| [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html?lang=pt-BR){target=_blank} | Certifique-se de que você esteja usando a at.js versão 1.1 ou posterior. Para obter informações sobre como baixar a versão mais recente do at.js, consulte [Baixar o at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=pt-BR){target=_blank}. Para obter informações sobre a nova funcionalidade em cada versão do at.js, consulte [Detalhes da versão do at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank}.<br>Os clientes que usam a at.js são incentivados a usarem os tokens de resposta e a evitarem os plugins. Alguns plug-ins do que dependem de métodos internos existentes na mbox.js (descontinuada), mas não na at.js, são entregues, mas apresentam falha. |

## Uso de tokens de resposta {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Verifique se você está usando o Platform Web SDK versão 2.6.0 (ou posterior) ou a at.js versão 1.1 (ou posterior).

   Para obter mais informações:

   * **Platform Web SDK**: consulte [Instalar o SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR) no guia de *visão geral do Platform Web SDK*.
   * **at.js**: consulte [Baixar at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-without-a-tag-manager.html?lang=pt-BR){target=_blank}.

1. Em [!DNL Target], clique em **[!UICONTROL Administration]** > **[!UICONTROL Response Tokens]**.

1. Ative os tokens de resposta desejados, como `activity.id` e `offer.id`.

   Os seguintes parâmetros estão disponíveis por padrão:

   | Tipo | Parâmetro | Notas |
   |--- |--- |--- |
   | Perfis integrados | `profile.activeActivities` | Retorna uma matriz do `activityIds` para o qual os visitantes estão qualificados. Ele é incrementado à medida que os usuários são qualificados. Por exemplo, em uma página com duas solicitações [!DNL Target] que fornecem duas atividades diferentes, a segunda solicitação inclui ambas as atividades. |
   |  | `profile.isFirstSession` | Retorna &quot;true&quot; ou &quot;false.&quot; |
   |  | `profile.isNewSession` | Retorna &quot;true&quot; ou &quot;false.&quot; |
   |  | `profile.daysSinceLastVisit` | Retorna o número de dias, desde a última visita do visitante. |
   |  | `profile.tntId` | Retorna tntID do visitante |
   |  | `profile.marketingCloudVisitorId` | Retorna a ID do visitante da Experience Cloud. |
   |  | `profile.thirdPartyId` | Retorna a ID de terceiros do visitante. |
   |  | `profile.categoryAffinity` | Retorna a categoria favorita do visitante. |
   |  | `profile.categoryAffinities` | Retorna uma matriz das 5 categorias principais do visitante como sequências de caracteres. |
   | Atividade | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`offer.name`<br>`offer.id` | Detalhes da atividade atual.<br> Observe que os valores dos parâmetros de oferta são avaliados no nível de experiência. |
   | Geografia | `geo.country`<br>`geo.countryCode`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | Consulte [Geo](/help/main/c-target/c-audiences/c-target-rules/geo.md) para obter mais informações sobre como usar o direcionamento geográfico nas atividades. |
   | Método de Alocação de Tráfego <br>(Aplica-se somente a atividades [!UICONTROL Auto-Target] e [!UICONTROL Automated Personalization].) | `experience.trafficAllocationId` | Retorna 0 se um visitante recebeu uma experiência por estar no tráfego de &quot;controle&quot; e 1 se um visitante recebeu uma experiência pela distribuição de tráfego &quot;direcionada&quot;. |
   |  | `experience.trafficAllocationType` | Retornar &quot;controle&quot; ou &quot;direcionado&quot;. |

   Os atributos do perfil do usuário e dos Atributos do cliente também são exibidos na lista.

   >[!NOTE]
   >
   >Os parâmetros com caracteres especiais não são exibidos na lista. Somente caracteres alfanuméricos e sublinhados são suportados.

1. (Condicional) Para usar um parâmetro de perfil como token de resposta, mas o parâmetro não foi transmitido por uma solicitação [!DNL Target] e, portanto, não foi carregado na interface do usuário [!DNL Target], você pode usar o botão [!UICONTROL Add Response Token] para adicionar o perfil à interface do usuário.

   Clique em **[!UICONTROL Add Response Token]**, forneça o nome do token e clique em **[!UICONTROL Activate]**.

1. Crie uma atividade.

## Ouvir respostas e ler tokens de resposta

O processo usado para ouvir respostas do [!DNL Target] e ler tokens de resposta difere dependendo se você tem uma implementação do [!DNL Platform Web SDK] ou do at.js.

### ![Selo do Adobe Experience Platform Web SDK](/help/main/assets/platform.png) [!DNL Platform Web SDK] usando a classe de objeto Handle {#platform-web-sdk}

Use a classe de objeto Handle, que tem um objeto de metadados e um objeto de dados para escutar respostas [!DNL Target] e ler os tokens de resposta.

O exemplo de resposta a seguir adiciona um manipulador de eventos personalizado [!DNL Platform Web SDK] diretamente à página do HTML (a tabela explica os objetos usados no código):

| Objeto | Informações |
| --- | --- |
| Tipo - Personalization.decision | Se a decisão foi tomada pelo [!DNL Target] ou pelo provedor do Offer Decisioning. |
| Provedor de decisão - TGT | TGT-[!DNL Target]. [!DNL Target] fornece os valores e metadados do token de resposta à página. |
| Meta | Metadados passados para a página. |
| Dados | Valores dos metadados passados para a página. |

```html
<html>

<head>
 ...
 <script src="alloy.js"></script>
 <script>
  {
   "requestId": "4d0a7cfd-952c-408c-b3b8-438edc38250a",
   "handle": [{
    "type": "personalization:decisions",
    "payload": [{
     "id": "....",
     "scope": "__view__",
     "scopeDetails": {
      "decisionProvider": "TGT",
      "activity": {
       "id": "..."
      },
      "experience": {
       "id": "...."
      }
     },
     "items": [{
      "id": "123",
      "schema": "https://ns.adobe.com/personalization/dom-action",
      "meta": {
       "activity.id": "...",
       "activity.name": "...",
       "profile.foo": "...",
       "profile.bar": "..."
      },
      "data": {
       "id": "123",
       "type": "setHtml",
       "selector": "#foo",
       "prehidingSelector": "#foo",
       "content": "<div>Hello world</div>"
      }
     }]
    }]
   }]
  }
  });
 </script>
</head>

<body>
 ...
</body>

</html>
```

### ![selo da at.js](/help/main/assets/atjs.png) da at.js usando eventos personalizados

Use os [eventos personalizados da at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/atjs-custom-events.html?lang=pt-BR){target=_blank} para ouvir a resposta do [!DNL Target] e ler os tokens de resposta.

O código de amostra a seguir adiciona um manipulador de evento personalizado da [!DNL at.js] diretamente na página HTML:

```html
<html> 
  <head> 
    .... 
    <script src="at.js"></script> 
    <script> 
      document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
        console.log("Request succeeded", e.detail); 
      }); 
    </script> 
  <head> 
  <body> 
  ... 
  </body> 
</html>
```

## Perguntas frequentes sobre token de resposta {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**Qual função é necessária para ativar ou desativar os tokens de resposta?**

Os tokens de resposta só podem ser ativados ou desativados por usuários com a função [!DNL Target] [!UICONTROL Administrator].

**O que acontece se eu estiver executando o [!DNL Platform Web SDK] 2.6.0 (ou anterior)?**

Você não tem acesso aos tokens de resposta.

**O que acontece se eu estiver executando a at.js 1.0 (ou anterior)?**

Você vê os tokens de resposta, mas a at.js não pode usá-los.

**É possível ter [!DNL Target Classic] plug-ins e tokens de resposta ativos ao mesmo tempo?**

Os plug-ins e os tokens de resposta estão disponíveis em paralelo; no entanto, os plug-ins serão descontinuados no futuro.

**Os tokens de resposta são entregues por todas as [!DNL Target] respostas ou somente por [!DNL Target] respostas que fornecem uma atividade?**

Os tokens de resposta são entregues somente por meio de [!DNL Target] respostas que fornecem uma atividade.

**Meu plug-in [!DNL Target Classic] incluiu o JavaScript. Como replico a funcionalidade dele usando os tokens de resposta?**

Ao migrar para tokens de resposta, esse tipo de JavaScript deve ser mantido em sua base de código ou solução de gerenciamento de tags. Você pode acionar esse código usando [!DNL Platform Web SDK] ou [!DNL at.js] eventos personalizados e enviar os tokens de resposta às suas funções do JavaScript.

**Por que meu parâmetro de perfil/Atributos do cliente não é exibido na lista de tokens de resposta?**

O [!DNL Target] normalmente atualiza parâmetros a cada 15 minutos. Essa atualização depende da ação do usuário e os dados são atualizados somente quando você exibe a página de tokens de resposta. Se os seus parâmetros não forem exibidos na lista de tokens de resposta, [!DNL Target] ainda não atualizou os dados.

Além disso, se o parâmetro contiver qualquer coisa exceto caracteres não alfanuméricos ou qualquer símbolo diferente de sublinhado, o parâmetro não aparecerá na lista. Atualmente, somente caracteres alfanuméricos e sublinhados são aceitos.

**O token de resposta ainda fornecerá conteúdo se usar um script de perfil excluído ou um parâmetro de perfil?**

Os tokens de resposta extraem as informações dos perfis de usuário e, em seguida, as entregam. Se você excluir um script ou parâmetro de perfil, isso n~so significa que as informações foram removidas dos perfis de usuário. Os perfis de usuário ainda têm dados correspondentes ao script de perfil. O token de resposta continua a fornecer o conteúdo. Para usuários que não têm essas informações salvas em seus perfis ou para novos visitantes, esse token não é entregue porque os dados não estão presentes em seus perfis.

[!DNL Target] não desliga o token automaticamente. Se você excluir o script de perfil e não desejar mais que ele seja entregue, você deve desligar o token sozinho.

**Renomeei meu script de perfil, mas por que o token está usando o script ainda ativo com o nome herdado?**

Conforme mencionado acima os tokens de resposta trabalham nas informações de perfil salvas pelos usuários. Embora você tenha renomeado o script de perfil, os usuários que visitaram o site têm o valor do script de perfil antigo salvo nos perfis. O token continua a coletar o valor antigo que já está salvo nos perfis do usuário. Se você não deseja entregar o conteúdo no novo nom, deve desligar o token anterior e ligar o novo token.

**Se meus atributos foram alterados, quando eles serão removidos da lista?**

O [!DNL Target] executa uma atualização de atributos em intervalos regulares. Qualquer atributo que não esteja ativado é removido durante a próxima atualização. No entanto, se você tiver um atributo que foi ativado e removido, esse script não será removido da lista de atributos até que você o desative. Como exemplo, você removeu um script de perfil que era usado como um token. [!DNL Target] remove da lista apenas os atributos desativados quando eles são excluídos ou renomeados.

## Enviar dados para o Google Analytics

As seções a seguir descrevem como enviar dados do [!DNL Target] para o Google Analytics 4. Os dados enviados por tokens de resposta também podem ser enviados para outras integrações de terceiros.

### ![Selo da AEP](/help/main/assets/platform.png) Envio de dados para a Google Analytics via Platform Web SDK

O Google Analytics pode enviar dados por meio da Platform Web SDK versão 2.6.0 (ou posterior) adicionando o seguinte código na página do HTML.

>[!NOTE]
>
>Verifique se o par de valores da chave do token de resposta está sob o objeto `alloy("sendEvent"`.

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
<script type="text/javascript">
    alloy("sendEvent", {
 
 
    })
    .then(({ renderedPropositions, nonRenderedPropositions }) => {
        // concatenate all the propositions
        const propositions = [...renderedPropositions, ...nonRenderedPropositions];
        // extractResponseTokens() extract the meta from item -> meta
        const tokens = extractResponseTokens(propositions);
        const activityNames = [];
        const experienceNames = [];
        const uniqueTokens = distinct(tokens);
    
    
        uniqueTokens.forEach(token => {
            activityNames.push(token["activity.name"]);
            experienceNames.push(token["experience.name"]);
        });
 
        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });
</script>
```

### ![selo da at.js](/help/main/assets/atjs.png) Envio de dados para a Google Analytics via at.js {#section_04AA830826D94D4EBEC741B7C4F86156}

O Google Analytics pode enviar dados via at.js ao adicionar o seguinte código na página HTML:

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>

<script type="text/javascript">
    document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) {
        var tokens = e.detail.responseTokens;

        if (isEmpty(tokens)) {
            return;
        }

        var activityNames = [];
        var experienceNames = [];
        var uniqueTokens = distinct(tokens);

        uniqueTokens.forEach(function(token) {
            activityNames.push(token["activity.name"]);
            experienceNames.push(token["experience.name"]);
        });

        gtag('config', 'TAG_ID');
        gtag('event', 'action_name', {'eventCategory': 'target',
            'eventAction': experienceNames, 'eventLabel': activityNames
        });
    });

    function isEmpty(val) {
        return (val === undefined || val == null || val.length <= 0) ? true : false;
    }

    function key(obj) {
        return Object.keys(obj)
        .map(function(k) { return k + "" + obj[k]; })
        .join("");
    }

    function distinct(arr) {
        var result = arr.reduce(function(acc, e) {
            acc[key(e)] = e;
            return acc;
        }, {});

        return Object.keys(result)
        .map(function(k) { return result[k]; });
    }
</script>
```

## Depuração

As seções a seguir fornecem informações sobre a depuração de tokens de resposta:

### ![selo da at.js](/help/main/assets/atjs.png) Google Analytics e depuração

O código a seguir permite depurar usando o Google Analytics:

```javascript
<script async src="https://www.googletagmanager.com/gtag/js?id=TAG_ID"></script>
  
<script type="text/javascript">
    document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) {
      var tokens = e.detail.responseTokens;
  
      if (isEmpty(tokens)) {
        return;
      }
  
      var activityNames = [];
      var experienceNames = [];
      var uniqueTokens = distinct(tokens);
  
      uniqueTokens.forEach(function(token) {
        activityNames.push(token["activity.name"]);
        experienceNames.push(token["experience.name"]);
      });
  
      gtag('config', 'TAG_ID');
      gtag('event', 'action_name', {'eventCategory': 'target',
          'eventAction': experienceNames, 'eventLabel': activityNames
      });
    });
  
    function isEmpty(val) {
      return (val === undefined || val == null || val.length <= 0) ? true : false;
    }
  
    function key(obj) {
       return Object.keys(obj)
      .map(function(k) { return k + "" + obj[k]; })
      .join("");
    }
  
    function distinct(arr) {
      var result = arr.reduce(function(acc, e) {
        acc[key(e)] = e;
        return acc;
      }, {});
  
      return Object.keys(result)
      .map(function(k) { return result[k]; });
    }
</script>
```

### Depuração usando o equivalente do plug-in ttMeta

O equivalente do plugin ttMeta para fins de depuração pode ser criado ao adicionar o seguinte código à página HTML:

```javascript
<script type="text/javascript" > 
  document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function (e) { 
    window.ttMETA= typeof(window.ttMETA)!="undefined" ? window.ttMETA : []; 
 
    var tokens=e.detail.responseTokens; 
 
    if (isEmpty(tokens)) { 
      return; 
    } 
     
    var uniqueTokens = distinct(tokens); 
 
    uniqueTokens.forEach(function(token) { 
      window.ttMETA.push({ 
        'CampaignName': token["activity.name"], 
        'CampaignId' : token["activity.id"], 
        'RecipeName': token["experience.name"], 
        'RecipeId': token["experience.id"], 
        'OfferId': token["offer.id"], 
        'OfferName': token["offer.name"], 
        'MboxName': e.detail.mbox}); 
      console.log(ttMETA); 
    }); 
  }); 
 
  function isEmpty(val){ 
    return (val === undefined || val == null || val.length <= 0) ? true : false; 
  } 
 
  function key(obj) { 
     return Object.keys(obj) 
    .map(function(k) { return k + "" + obj[k]; }) 
    .join(""); 
  } 
 
  function distinct(arr) { 
    var result = arr.reduce(function(acc, e) { 
      acc[key(e)] = e; 
      return acc; 
    }, {}); 
   
    return Object.keys(result) 
    .map(function(k) { return result[k]; }); 
  } 
</script>
```

## Vídeo de treinamento do ![at.js](/help/main/assets/atjs.png): Tokens de resposta e Eventos personalizados do at.js {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

O vídeo a seguir explica como usar tokens de resposta e eventos personalizados de at.js para compartilhar informações de perfil do [!DNL Target] com sistemas de terceiros.

>[!NOTE]
>
>A interface do usuário de menu do [!DNL Target] [!UICONTROL Administration] (antigo [!UICONTROL Setup]) foi reprojetada para fornecer melhor desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário no produto. As informações do vídeo a seguir estão corretas; no entanto, as opções estão em locais um pouco diferentes.
>
>O vídeo menciona `option.name` e `option.id`, que foram substituídos por `offer.name` e `offer.id`, respectivamente.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
