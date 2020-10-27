---
keywords: A4T;Adobe Analytics;Analytics-based activity;Analytics report suite;report suite;Analytics Target integration;configure report suite
description: Várias etapas são necessárias para a implementação do Adobe Analytics como a fonte de geração de relatórios para o Target (A4T).
title: Implementação do Analytics for Target
feature: a4t implementation
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: b6d4cc35e32f118ff46fcd3b235c8b5deae35d05
workflow-type: tm+mt
source-wordcount: '904'
ht-degree: 49%

---


# Implementação do Analytics for Target{#analytics-for-target-implementation}

Several steps are required when implementing [!DNL Adobe Analytics] as the reporting source for [!DNL Target] (A4T).

## Implementation steps {#section_73961BAD5BB4430A95E073DE5C026277}

As seções a seguir descrevem as etapas necessárias para implantar essa integração no site.

## Etapa 1: Solicitar provisionamento para o Analytics e Públicos alvos

After you implement [!DNL Analytics] as the reporting source for [!DNL Target], you must be provisioned for [!DNL Analytics] and [!DNL Target]. [Use este formulário para solicitar o aprovisionamento](http://www.adobe.com/go/audiences).

## Etapa 2: Configurar permissões do usuário

User account requirements must be met before you can create an [!DNL Analytics]-based activity in [!DNL Target]. See [User permission requirements](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Etapa 3: Implementar o serviço de ID de visitante da Experience Cloud

O serviço de ID do visitante permite identificar os usuários através das soluções da [!DNL Adobe Experience Cloud]. Você deve implementar ou migrar para a versão exigida da ID de visitante da Experience Cloud. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

See [Implement the Experience Cloud ID Service for Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html) in the *Experience Cloud Visitor ID Service* documentation.

## Etapa 4: Atualizar o AppMeasurement para JavaScript ou s_code

Você deve implementar ou migrar para a versão exigida da appMeasurement.js. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para novas implementações, consulte Visão geral [da implementação do](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) JavaScript no Guia *de implementação do* Analytics.

Para obter uma migração, consulte [Migração para o AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) no Guia *de implementação do* Analytics.

## Etapa 5: Baixe e atualize o at.js

Você deve implementar ou migrar para a versão necessária do at.js usando sua conta de produção. Não são necessárias modificações no código.

Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Etapa 6: Host at.js

Se você implantou anteriormente o at.js, é possível substituir o arquivo existente pela versão atualizada. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Caso contrário, este arquivo pode ser hospedado com o serviço de ID de visitante e os arquivos do AppMeasurement para JavaScript. Esses arquivos devem ser hospedados em um servidor da Web que seja acessível a todas as páginas no seu site. Você precisa do caminho até esses arquivos na próxima etapa.

## Step 7: Reference at.js on all site pages {#step7}

Inclua o at.js abaixo de VisitorAPI.js adicionando a seguinte linha de código na tag em cada página:

Para at.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

É essencial que VisitorAPI.js seja carregado antes do at.js. Se você estiver atualizando um arquivo at.js ou mbox.js existente, verifique a ordem de carregamento.

The way the out-of-the-box settings are configured for [!DNL Target] and [!DNL Analytics] integration from an implementation perspective is to use the SDID that is passed from the page to stitch the [!DNL Target] and [!DNL Analytics] request together on the backend automatically for you.

However, if you want more control on how and when to send analytics data related to [!DNL Target] to [!DNL Analytics] for reporting purposes, and you do not want to opt-in to the default settings of having [!DNL Target] and [!DNL Analytics] automatically stitch the analytics data via the SDID, then you can set **analyticsLogging = client_side** via **window.targetGlobalSettings**. Observação: qualquer versão inferior a 2.1 não dá suporte a essa abordagem.

Por exemplo:

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Essa configuração tem um efeito global, o que significa que **analyticsLogging: &quot;client_side&quot;** será enviado para todas as chamadas feitas pela at.js nas solicitações do e uma carga de análise será retornada para cada solicitação. [!DNL Target] Quando configurado, o formato da carga retornada é semelhante ao seguinte:

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

A carga pode ser encaminhada ao Analytics por meio da API [de inserção de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)dados. Observe que, para as atividades [!UICONTROL Autoalocação] e Público alvo  Automático, você também precisará encaminhar sessionId. Para obter mais informações, consulte [Adobe Analytics for Público alvo (A4T)](https://developers.adobetarget.com/api/delivery-api/#section/Integration-with-Experience-Cloud/Adobe-Analytics-for-Target-(A4T)) no Guia da API do Delivery *Adobe Target*

Se uma configuração global não for desejada e uma abordagem mais sob demanda for preferível, você poderá usar a função [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) para fazer isso, passando em **analyticsLogging: &quot;client_side&quot;**. The analytics payload will be returned for only this call and the [!DNL Target] backend will not forward the payload to [!DNL Analytics]. By pursuing this approach, every at.js [!DNL Target] request will not return the payload by default, but instead only when desired and specified.

Por exemplo:

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

Essa chamada chama uma resposta da qual você pode extrair a carga de análise.

A resposta é semelhante à seguinte:

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

A carga pode ser encaminhada para [!DNL Analytics] a API [de inserção de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)dados.

## Etapa 8: Validar a implementação {#step8}

Carregue suas páginas depois de atualizar as bibliotecas JavaScript para confirmar que os valores dos parâmetros `mboxMCSDID`[!DNL Target] nas chamadas do são compatíveis com o valor do parâmetro `sdid`[!DNL Analytics] na chamada de exibição de página do 

Isso é especialmente importante para confirmar em Aplicativos de página única (SPAs), onde a ordem das chamadas nem sempre é previsível.

**Observação:** a compatibilidade desses valores é necessária para que o A4T funcione corretamente.

## Etapa 9: (Opcional) Remover o código de integração anterior

Recomendamos remover a integração anterior para simplificar sua implementação e eliminar a necessidade de classificar as discrepâncias entre os sistemas. Você pode remover qualquer código implantado por um SC anterior à integração T&amp;T, incluindo `mboxLoadSCPlugin`.

## Etapa 10: Ativar as opções de uso do Analytics como a fonte de relatórios do Target

In [!DNL Target], click **[!UICONTROL Administation > Visual Experience Composer]** and choose either **[!UICONTROL Select per activity]** or **[!UICONTROL Adobe Analytics]** to enable the options.

* **[!UICONTROL Selecionar por atividade permite escolher entre o e o para criar cada atividade.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL O Adobe configura o Analytics como fonte de relatórios para todas as atividades que você criar.]**[!DNL Analytics]

