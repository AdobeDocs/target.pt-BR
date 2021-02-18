---
keywords: A4T; Adobe Analytics; Atividade baseada no Analytics; Conjunto de relatórios do Analytics; conjunto de relatórios; Integração do Analytics Target; configurar conjunto de relatórios
description: Siga as etapas necessárias para implementar o Analytics for Público alvo (A4T) nas soluções Adobe Target e Adobe Analytics.
title: Como implementar o Analytics para o Público alvo (A4T)?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 260492867eb31c59637fc8dff2b8440b5d24c347
workflow-type: tm+mt
source-wordcount: '918'
ht-degree: 48%

---


# Implementação do Analytics for Target{#analytics-for-target-implementation}

Várias etapas são necessárias ao implementar [!DNL Adobe Analytics] como a fonte de relatórios para [!DNL Target] (A4T).

## Etapas de implementação {#section_73961BAD5BB4430A95E073DE5C026277}

As seções a seguir descrevem as etapas necessárias para implantar essa integração no site.

## Etapa 1: Solicitar provisionamento para o Analytics e Públicos alvos

Depois de implementar [!DNL Analytics] como a origem do relatórios para [!DNL Target], você deve ser provisionado para [!DNL Analytics] e [!DNL Target]. [Use este formulário para solicitar o aprovisionamento](http://www.adobe.com/go/audiences).

## Etapa 2: Configurar permissões do usuário

Os requisitos da conta de usuário devem ser atendidos antes que você possa criar uma atividade baseada em [!DNL Analytics] em [!DNL Target]. Consulte [Requisitos de permissão do usuário](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Etapa 3: Implementar o serviço de ID de visitante da Experience Cloud

O serviço de ID do visitante permite identificar os usuários através das soluções da [!DNL Adobe Experience Cloud]. Você deve implementar ou migrar para a versão exigida da ID de visitante da Experience Cloud. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementar o serviço de ID do Experience Cloud para Público alvo](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) na documentação *Serviço de ID do Visitante*.

## Etapa 4: Atualizar o AppMeasurement para JavaScript ou s_code

Você deve implementar ou migrar para a versão exigida da appMeasurement.js. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para novas implementações, consulte [Visão geral da implementação do JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) no *Guia de Implementação do Analytics*.

Para obter uma migração, consulte [Migração para o AppMeasurement para JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) no *Guia de implementação do Analytics*.

## Etapa 5: Baixe e atualize o at.js

Você deve implementar ou migrar para a versão necessária do at.js usando sua conta de produção. Não são necessárias modificações no código.

Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Etapa 6: Host at.js

Se você implantou anteriormente o at.js, é possível substituir o arquivo existente pela versão atualizada. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Caso contrário, este arquivo pode ser hospedado com o serviço de ID de visitante e os arquivos do AppMeasurement para JavaScript. Esses arquivos devem ser hospedados em um servidor da Web que seja acessível a todas as páginas no seu site. Você precisa do caminho até esses arquivos na próxima etapa.

## Etapa 7: Referência ao at.js em todas as páginas do site {#step7}

Inclua o at.js abaixo de VisitorAPI.js adicionando a seguinte linha de código na tag em cada página:

Para at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

É essencial que VisitorAPI.js seja carregado antes do at.js. Se você estiver atualizando um arquivo at.js ou mbox.js existente, verifique a ordem de carregamento.

A maneira como as configurações predefinidas são configuradas para a integração [!DNL Target] e [!DNL Analytics] a partir de uma perspectiva de implementação é usar o SDID transmitido da página para unir as solicitações [!DNL Target] e [!DNL Analytics] no backend automaticamente para você.

No entanto, se você quiser mais controle sobre como e quando enviar dados de análise relacionados a [!DNL Target] para [!DNL Analytics] para fins de relatórios, e não quiser aceitar as configurações padrão de ter [!DNL Target] e [!DNL Analytics] automaticamente costurar os dados de análise via SDID, você poderá definir **analyticsLogging = client_side** via **window.targetGlobalSettings**. Observação: qualquer versão inferior a 2.1 não dá suporte a essa abordagem.

Por exemplo:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Essa configuração tem um efeito global, o que significa que **analyticsLogging: &quot;client_side&quot;** será enviado para todas as chamadas feitas pela at.js nas solicitações do e uma carga de análise será retornada para cada solicitação. [!DNL Target] Quando configurado, o formato da carga retornada é semelhante ao seguinte:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

A carga pode ser encaminhada ao Analytics por meio da [API de inserção de dados](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Observe que, para as atividades [!UICONTROL Autoalocar] e [!UICONTROL Público alvo automático], você também precisará encaminhar sessionId. Para obter mais informações, consulte [relatórios do Analytics for Público alvo (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) no guia *SDKs do Adobe Target*.

Se uma configuração global não for desejada e uma abordagem mais sob demanda for preferível, você poderá usar a função [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) para fazer isso, passando em **analyticsLogging: &quot;client_side&quot;**. A carga do Analytics será retornada somente para esta chamada e o back-end [!DNL Target] não encaminhará a carga para [!DNL Analytics]. Ao seguir essa abordagem, cada solicitação at.js [!DNL Target] não retornará a carga por padrão, mas somente quando desejado e especificado.

Por exemplo:

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

Essa chamada chama uma resposta da qual você pode extrair a carga de análise.

A resposta é semelhante à seguinte:

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

A carga pode ser encaminhada para [!DNL Analytics] por meio da [API de inserção de dados](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

## Etapa 8: Validar a implementação {#step8}

Carregue suas páginas depois de atualizar as bibliotecas JavaScript para confirmar que os valores dos parâmetros `mboxMCSDID`[!DNL Target] nas chamadas do são compatíveis com o valor do parâmetro `sdid`[!DNL Analytics] na chamada de exibição de página do 

Isso é especialmente importante para confirmar em Aplicativos de página única (SPAs), onde a ordem das chamadas nem sempre é previsível.

**Observação:** a compatibilidade desses valores é necessária para que o A4T funcione corretamente.

## Etapa 9: (Opcional) Remover o código de integração anterior

Recomendamos remover a integração anterior para simplificar sua implementação e eliminar a necessidade de classificar as discrepâncias entre os sistemas. Você pode remover qualquer código implantado por um SC anterior à integração T&amp;T, incluindo `mboxLoadSCPlugin`.

## Etapa 10: Ativar as opções de uso do Analytics como a fonte de relatórios do Target

Em [!DNL Target], clique em **[!UICONTROL Administração > Visual Experience Composer]** e escolha **[!UICONTROL Selecionar por atividade]** ou **[!UICONTROL Adobe Analytics]** para ativar as opções.

* **[!UICONTROL Selecionar por atividade permite escolher entre o e o para criar cada atividade.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL O Adobe configura o Analytics como fonte de relatórios para todas as atividades que você criar.]**[!DNL Analytics]

