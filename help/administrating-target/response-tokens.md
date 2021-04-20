---
keywords: tokens de resposta; tokens; plugins; plug-ins; at.js; resposta
description: Saiba como usar tokens de resposta em informações específicas de saída do Adobe Target para usar na depuração e integração com sistemas de terceiros (como o Clicktale).
title: O que são tokens de resposta e como usá-los?
feature: Administration & Configuration
role: Administrator
translation-type: tm+mt
source-git-commit: 86102ed5b49d102660ed38fe0a71612cefcd2caf
workflow-type: tm+mt
source-wordcount: '1575'
ht-degree: 76%

---


# Tokens de resposta{#response-tokens}

Os tokens de resposta permitem gerar automaticamente informações específicas para [!DNL Target] (detalhes da atividade, informações de perfil do usuário, informações geográficas e assim por diante) para usar na depuração ou na integração com sistemas de terceiros (como o Clicktale).

Os tokens de resposta permitem que você escolha quais variáveis serão aproveitadas e, em seguida, permitem que sejam enviadas como parte de uma resposta do Target. Para fazer isso, basta habilitar uma variável usando o switch e a variável será enviada com respostas do Target, que podem ser validadas em chamadas de rede. Os tokens de resposta funcionam no modo [!UICONTROL Preview] também.

Uma diferença importante entre os plugins e os tokens de resposta é que os plugins entregam o JavaScript para a página de execução, após a entrega, por sua vez, os tokens de resposta entregam um objeto que pode ser lido e utilizado pelos ouvintes do evento. Para obter mais informações, consulte [eventos personalizados de at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) e os exemplos mais adiante neste artigo. A abordagem dos tokens de resposta é mais segura e permite um desenvolvimento e manutenção mais fáceis de integrações de terceiros.

>[!NOTE]
>
>Os tokens de resposta estão disponíveis com a at.js 1.1 ou posterior.

| Biblioteca do Target em uso | Ações sugeridas |
|--- |--- |
| at.js | Certifique-se de que você esteja usando a at.js versão 1.1 ou posterior. Para obter informações sobre como baixar a versão mais recente do at.js, consulte [Baixar o at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md). Para obter informações sobre a nova funcionalidade em cada versão do at.js, consulte [Detalhes da versão do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).<br>Os clientes que usam a at.js são incentivados a usarem os tokens de resposta e a evitarem os plugins. Alguns plugins que dependem de métodos internos existentes na mbox.js, mas não na at.js, serão entregues, mas apresentarão falha. Para obter mais informações, consulte [Limitações do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md). |
| mbox.js | Os plug-ins continuam a ser suportados e entregues no uso da mbox.js.<br>No entanto, os clientes que usam mbox.js e plugins são incentivados a mudar para at.js e tokens de resposta. Para obter informações sobre as vantagens do uso de at.js em mbox. js, consulte [Perguntas frequentes do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md). Para obter informações sobre a migração, consulte [Migrar para at.js do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md).<br>Após a desativação do Target Classic (novembro de 2017), você pode entrar em contato com o Atendimento ao cliente para editar ou desativar os plugins existentes. Você deveria ter auditado os plugins antes da desativação do Target Classic e desativado os plugins indesejados.<br>Você não pode criar novos plugins no Target Standard/Premium. Em vez disso, use os tokens de resposta.<br>Os plug-ins antigos do SiteCatalyst devem ser desativados e substituídos pelo [Adobe Analytics como a fonte de relatórios do Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). O plugin ttMeta deve ser desativado e substituído pelo [depurador da Adobe Experience Cloud](https://chrome.google.com/webstore/detail/adobe-experience-cloud-de/ocdmogmohccmeicdhlhhgepeaijenapj). |

## Utilização de tokens de resposta {#section_A9E141DDCBA84308926E68D05FD2AC62}

1. Certifique-se de que você esteja usando a [!DNL at.js] versão 1.1 ou posterior.

   Para obter mais informações, consulte [Baixar a at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_1E1F958F9CCC4E35AD97581EFAF659E2).

1. Em [!DNL Target], clique em **[!UICONTROL Administração]** > **[!UICONTROL Tokens de Resposta]**.

   ![](assets/response_tokens-new.png)

1. Ative os tokens de resposta desejados, como `activity.id`, `option.id` e assim por diante.

   Os seguintes parâmetros estão disponíveis por padrão:

   | Tipo | Parâmetro | Notas |
   |--- |--- |--- |
   | Perfis incorporados | `profile.activeActivities` | Retorna uma matriz do `activityIds` para o qual os visitantes estão qualificados. Ele é incrementado à medida que os usuários são qualificados. Por exemplo, em uma página com duas solicitações [!DNL Target] que fornecem duas atividades diferentes, a segunda solicitação inclui ambas as atividades. |
   |  | `profile.isFirstSession` | Retorna &quot;true&quot; ou &quot;false.&quot; |
   |  | `profile.isNewSession` | Retorna &quot;true&quot; ou &quot;false.&quot; |
   |  | `profile.daysSinceLastVisit` | Retorna o número de dias, desde a última visita do visitante. |
   |  | `profile.tntId` | Retorna tntID do visitante |
   |  | `profile.marketingCloudVisitorId` | Retorna a ID do visitante da Experience Cloud. |
   |  | `profile.thirdPartyId` | Retorna a ID de terceiros do visitante. |
   |  | `profile.categoryAffinity` | Retorna a categoria favorita do visitante. |
   |  | `profile.categoryAffinities` | Retorna uma matriz das 5 categorias principais do visitante como sequências de caracteres. |
   | Atividade | `activity.name`<br>`activity.id`<br>`experience.name`<br>`experience.id`<br>`option.name`<br>`option.id` | Detalhes da atividade atual. Observe que &quot;option&quot; equivale a &quot;offer.&quot; |
   | Geografia | `geo.country`<br>`geo.state`<br>`geo.city`<br>`geo.zip`<br>`geo.dma`<br>`geo.domainName`<br>`geo.ispName`<br>`geo.connectionSpeed`<br>`geo.mobileCarrier` | Consulte [Geo](/help/c-target/c-audiences/c-target-rules/geo.md) para obter mais informações sobre como usar o direcionamento geográfico nas atividades. |
   | Método de alocação de tráfego<br>(Aplica-se somente às atividades [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization]). | `experience.trafficAllocationId` | Retorna 0 se um visitante recebeu uma experiência de estar em tráfego de &quot;controle&quot; e 1 se um visitante recebeu uma experiência da distribuição de tráfego de &quot;direcionado&quot;. |
   |  | `experience.trafficAllocationType` | Retorne &quot;controle&quot; ou &quot;direcionado&quot;. |

   Os atributos do perfil do usuário e dos Atributos do cliente também são exibidos na lista.

   >[!NOTE]
   >
   >Os parâmetros com caracteres especiais não são exibidos na lista. Somente caracteres alfanuméricos e sublinhados são suportados.

1. (Condicional) Se você quiser usar um parâmetro de perfil como um token de resposta, mas o parâmetro não tiver sido passado por uma solicitação [!DNL Target] e, portanto, não tiver sido carregado na interface do usuário do Target, poderá usar o botão [!UICONTROL Adicionar token de resposta] para adicionar o perfil à interface do usuário.

   Clique em **[!UICONTROL Adicionar Token de Resposta]**, forneça o nome do token e clique em **[!UICONTROL Ativar]**.

   ![](assets/response_token_create.png)

1. Crie uma atividade.

Use [Eventos personalizados da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) para ouvir a resposta da e ler os tokens de resposta.[!DNL Target]

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

As instruções a seguir mostram como adicionar um manipulador de evento da [!DNL at.js] usando o Gerenciador dinâmico de tags de Adobe (DTM):

1. Faça logon no DTM.
1. Navegue até a propriedade apropriada.
1. Abra a ferramenta Target.

   Como o DTM originalmente não suporta at.js, você precisará usar o editor de código.

1. No editor de código, anexe o seguinte código à [!DNL at.js]:

   ```json
   document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
     console.log("Request succeeded", e.detail); 
   });
   ```

Você pode adicionar o seguinte trecho ao rodapé da biblioteca da [páginas de configuração do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812) se quiser que tudo seja um único arquivo.

```json
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(e) { 
  console.log("Request succeeded", e.detail); 
});
```

## Perguntas frequentes de tokens de resposta {#section_3DD5F32C668246289CDF9B4CDE1F536D}

**Qual função é necessária para ativar ou desativar os tokens de resposta?**

Resposta podem ser ativados ou desativados apenas por usuários com a função de administrador do Target.

**O que acontecerá se eu estiver executando at.js 1.0 ou anterior?**

Você verá os tokens de resposta, mas a at.js não poderá usá-los.

**O que acontece se eu estiver usando a at.js 1.1 (ou posterior) em algumas páginas, mas a mbox.js em outras páginas?**

Os tokens de resposta serão entregues às respostas do [!DNL at.js] Target, mas não às respostas [!DNL mbox.js].

**Posso fazer com que ambos plugins e tokens de resposta do Target Classic fiquem ativos ao mesmo tempo?**

Os plugins e os tokens de resposta serão disponibilizados em paralelo; no entanto, os plugins serão desativados no futuro.

**Os tokens de resposta são entregues por meio de todas as  [!DNL Target] respostas ou somente por meio de  [!DNL Target] respostas que entregam uma atividade do ?**

Os tokens de resposta são entregues somente por meio de respostas [!DNL Target] que entregam uma atividade.

**Meu plugin do Target Classic está incluído no JavaScript. Como replico a funcionalidade dele usando os tokens de resposta?**

Ao migrar para os tokens de resposta, esse tipo de JavaScript precisará ser mantido na sua base de código ou na solução de gerenciamento de tags. Você pode acionar esse código usando os eventos personalizados da [!DNL at.js] e enviar os tokens de resposta às suas funções do JavaScript.

**Por que meu parâmetro de perfil/Atributos do cliente não é exibido na lista de tokens de resposta?**

O Target normalmente atualiza os parâmetros a cada 15 minutos. Essa atualização depende da ação dos usuários, sendo que os dados são atualizados somente quando você visualiza a página dos tokens de resposta. Se os seus parâmetros não forem exibidos na lista de token de resposta, isso ainda poderá acontecer, porque o Target ainda não atualizou os dados.

Além disso, se o seu parâmetro contém caracteres que não sejam alfanuméricos ou qualquer símbolo que não seja sublinhados, o parâmetro não aparecerá na lista. Atualmente, somente caracteres alfanuméricos e sublinhados são aceitos.

**Se eu criar um token de resposta usando um script de perfil ou um parâmetro de perfil e, em seguida, excluir o script de perfil ou parâmetro, o token de resposta ainda entregará o conteúdo?**

Os tokens de resposta extraem as informações dos perfis de usuário e, em seguida, as entregam. Se você excluir um script ou parâmetro de perfil, isso n~so significa que as informações foram removidas dos perfis de usuário. Os perfis de usuário ainda terão os dados correspondentes para o script de perfil. O token de resposta continuará a entregar o conteúdo. Para usuários que não têm as informações salvas nos perfis, ou para novos visitantes, esse token não será entregue porque os dados não estão presentes nos perfis.

O Target não desligará o token automaticamente. Se você excluir o script de perfil e não desejar mais que ele seja entregue, você deve desligar o token sozinho.

**Renomeei meu script de perfil, mas por que o token está usando o script ainda ativo com o nome herdado?**

Conforme mencionado acima os tokens de resposta trabalham nas informações de perfil salvas pelos usuários. Mesmo se você tiver renomeou seu script de perfil, os usuários que visitaram seu site têm o valor antigo de script do perfil salvos nos perfis e o token continuará a escolher o valor antigo que já está salvo nos perfis do usuário. Se você não deseja entregar o conteúdo no novo nom, deve desligar o token anterior e ligar o novo token.

**Se meus atributos foram alterados, quando eles serão removidos da lista?**

O Target realiza uma atualização de atributos em intervalos regulares. Qualquer atributo que não esteja ligado será demovido durante a próxima atualização. Entretanto, se você tem um atributo que foi ligado e tiver sido removido (por exemplo, você removeu um script de perfil que foi usado como um token), esse script não será removido da lista de atributos, até ele ter sido desligado. O Target remove somente os atributos desligados na lista, quando são excluídos ou renomeados.

## Envio de dados para o Google Analytics via at.js   {#section_04AA830826D94D4EBEC741B7C4F86156}

O Google Analytics pode enviar dados via at.js ao adicionar o seguinte código na página HTML:

```javascript
<script type="text/javascript"> 
  (function(i, s, o, g, r, a, m) { 
    i['GoogleAnalyticsObject'] = r; 
    i[r] = i[r] || function() { 
      (i[r].q = i[r].q || []).push(arguments) 
    }, i[r].l = 1 * new Date(); 
    a = s.createElement(o), 
      m = s.getElementsByTagName(o)[0]; 
    a.async = 1; 
    a.src = g; 
    m.parentNode.insertBefore(a, m) 
  })(window, document, 'script', 'https://www.google-analytics.com/analytics.js', 'ga'); 
  ga('create', 'Google Client Id', 'auto'); 
</script> 
 
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
 
    ga('send', 'event', { 
      eventCategory: "target", 
      eventAction: experienceNames, 
      eventLabel: activityNames 
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

## Depuração (similar ao plugin ttMeta)   {#section_DB3392B6E80749C1BFB520732EDF3BCE}

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
        'OfferId': token["option.id"], 
        'OfferName': token["option.name"], 
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

## Vídeo de treinamento: tokens de resposta e eventos personalizados do at.js ![Selo tutorial](/help/assets/tutorial.png) {#section_3AA0A6C8DBD94A528337A2525E3E05D5}

Assista ao vídeo a seguir para saber como usar tokens de resposta e eventos personalizados de at.js para compartilhar informações de perfil do Target com sistemas de terceiros.

>[!NOTE]
>
>A interface do usuário do menu [!DNL Target] [!UICONTROL Administration] (anteriormente [!UICONTROL Setup]) foi reprojetada para fornecer melhor desempenho, reduzir o tempo de manutenção necessário ao lançar novos recursos e melhorar a experiência do usuário no produto. As informações do vídeo a seguir são geralmente corretas; no entanto, as opções podem estar em locais um pouco diferentes. Os vídeos atualizados serão publicados em breve.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)
