---
keywords: A4T; Adobe Analytics; Atividade baseada no Analytics; Conjunto de relatórios do Analytics; Conjunto de relatórios; Integração do Analytics Target; configurar conjunto de relatórios; at.js; atjs; sdk da web da adobe experience platform; sdk da web da aep; sdk da web da plataforma
description: Siga as etapas necessárias para implementar as soluções Analytics para  [!DNL Target] (A4T) in your Adobe [!DNL Target] e Adobe Analytics.
title: Como implementar o Analytics para [!DNL Target] (A4T)?
feature: 'Analytics for Target (A4T) '
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ea5a451e71f390ddacc6ccea583112dd831184dc
workflow-type: tm+mt
source-wordcount: '1144'
ht-degree: 24%

---

# Analytics para implementação [!DNL Target]

Várias etapas são necessárias ao implementar [!DNL Adobe Analytics] como a fonte de relatórios para [!DNL Adobe Target] (A4T). O processo varia dependendo da implementação do A4T com o [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) ou com o at.js.

## ![Etapas ](/help/assets/platform.png) de implementação do SDK da Web da Adobe Experience Platform para uma implementação do SDK da Web da Adobe Experience Platform {#platform}

As seções a seguir descrevem as etapas necessárias para implantar essa integração no seu site se você estiver planejando usar o SDK da Web da plataforma:

### Etapa 1: Solicitar provisionamento para [!DNL Analytics] e [!DNL Target]

Antes de implementar o A4T, você deve ser provisionado para [!DNL Analytics] e [!DNL Target]. [Use este formulário para solicitar o aprovisionamento](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES).

### Etapa 2: Configurar permissões do usuário

Os requisitos da conta do usuário devem ser atendidos antes que você possa criar uma atividade baseada em [!DNL Analytics] em [!DNL Target]. Consulte [Requisitos de permissão do usuário](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

### Etapa 3: Criar uma configuração de Edge

Crie uma configuração de borda usando [!DNL Adobe Experience Platform Launch] usando a ferramenta de configuração de borda. Defina as configurações de [[!DNL Analytics] and [!DNL Target] borda](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/datastreams.html).

### Etapa 4: Instalar e configurar o SDK da Web da plataforma

Para começar a fornecer [!DNL Target] experiências e aplicar [!DNL Analytics] para fins de rastreamento e análise, [Instale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html) e [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html) o SDK da Web da plataforma nas páginas do site.

### Etapa 5: Ativar as opções para uso do A4T

Na interface [!DNL Target], clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]** e escolha **[!UICONTROL Selecionar por atividade]** ou **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL Selecionar por atividade permite escolher entre o e o para criar cada atividade.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL O Adobe configura o Analytics como fonte de relatórios para todas as atividades que você criar.]**[!DNL Analytics]

## ![Etapas de at.js ](/help/assets/atjs.png) badgeImplementation para uma implementação da at.js{#section_73961BAD5BB4430A95E073DE5C026277}

As seções a seguir descrevem as etapas necessárias para implantar essa integração no seu site se você planeja usar a at.js:

### Etapa 1: Solicitar provisionamento para o Analytics e Target

Após implementar [!DNL Analytics] como a fonte de relatórios para [!DNL Target], você deve ser provisionado para [!DNL Analytics] e [!DNL Target]. [Use este formulário para solicitar o aprovisionamento](http://www.adobe.com/go/audiences).

### Etapa 2: Configurar permissões do usuário

Os requisitos da conta do usuário devem ser atendidos antes que você possa criar uma atividade baseada em [!DNL Analytics] em [!DNL Target]. Consulte [Requisitos de permissão do usuário](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

### Etapa 3: Implementar o serviço de ID de visitante da Experience Cloud

O serviço de ID do visitante permite identificar os usuários através das soluções da [!DNL Adobe Experience Cloud]. Implemente ou migre para a versão exigida da ID de visitante do Experience Cloud. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementar o Serviço de ID do Experience Cloud para Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html) na documentação *Serviço de ID do visitante do Experience Cloud*.

### Etapa 4: Atualizar o AppMeasurement para JavaScript ou s_code

Implemente ou migre para a versão exigida do appMeasurement.js. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para novas implementações, consulte [Visão geral da implementação do JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html) no *Guia de Implementação do Analytics*.

Para migração, consulte [Migrating to AppMeasurement for JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html) no *Analytics Implementation Guide*.

### Etapa 5: Baixe e atualize a at.js

Implemente ou migre para a versão exigida da at.js usando sua conta de produção. Não são necessárias modificações no código.

Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

### Etapa 6: Host da at.js

Se você já implantou a at.js, é possível substituir o arquivo existente pela versão atualizada. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Caso contrário, este arquivo pode ser hospedado com o serviço de ID de visitante e os arquivos do AppMeasurement para JavaScript. Esses arquivos devem ser hospedados em um servidor da Web que seja acessível a todas as páginas no seu site. Você precisa do caminho até esses arquivos na próxima etapa.

### Etapa 7: Referencie a at.js em todas as páginas do site {#step7}

Inclua at.js abaixo de VisitorAPI.js adicionando a seguinte linha de código na tag de cada página:

Para at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

O VisitorAPI.js deve ser carregado antes da at.js. Se estiver atualizando um arquivo at.js ou mbox.js existente, verifique a ordem do carregamento.

A configuração padrão para a integração [!DNL Target] e [!DNL Analytics], de uma perspectiva de implementação, é usar a SDID transmitida da página para unir a solicitação [!DNL Target] e [!DNL Analytics] ao back-end automaticamente.

Você pode controlar como e quando enviar dados de análise relacionados a [!DNL Target] a [!DNL Analytics] para fins de relatório. Se não quiser aceitar as configurações padrão de ter [!DNL Target] e [!DNL Analytics] automaticamente unir os dados de análise pela SDID, defina **analyticsLogging = client_side** via **window.targetGlobalSettings**. Observação: qualquer versão inferior a 2.1 não dá suporte a essa abordagem.

Por exemplo:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Essa configuração tem um efeito global, o que significa que cada chamada feita por at.js tem **analyticsLogging: &quot;client_side&quot;** enviado nas solicitações [!DNL Target] e uma carga de análise é retornada para cada solicitação. Quando essa opção é configurada, o formato da carga retornada é semelhante ao seguinte:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

A carga pode ser encaminhada para o Analytics por meio da [Data Insertion API](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Para atividades de Alocação automática e Direcionamento automático, você também deve encaminhar a sessionId. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) no guia *SDKs do Adobe Target* .

Se uma configuração global não for desejada e uma abordagem mais sob demanda for preferível, use a função at.js [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) passando em **analyticsLogging: &quot;client_side&quot;**. A carga de análise é retornada somente para esta chamada e o [!DNL Target] backend não encaminha a carga para [!DNL Analytics]. Ao seguir essa abordagem, cada solicitação de at.js [!DNL Target] retorna a carga por padrão, mas somente quando desejado e especificado.

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

### Etapa 8: Validar a implementação {#step8}

Carregue suas páginas depois de atualizar as bibliotecas JavaScript para confirmar que os valores dos parâmetros `mboxMCSDID`[!DNL Target] nas chamadas do são compatíveis com o valor do parâmetro `sdid`[!DNL Analytics] na chamada de exibição de página do 

É especialmente importante confirmar que esses valores correspondem em Aplicativos de página única (SPA), onde a ordem das chamadas nem sempre é previsível.

>[!NOTE]
>
>A correspondência desses valores é necessária para que o A4T funcione corretamente.

### Etapa 9: (Opcional) Remover o código de integração anterior

O Adobe recomenda remover a integração anterior para simplificar sua implementação e eliminar a necessidade de classificar as discrepâncias entre os sistemas. Você pode remover qualquer código implantado por um SC anterior à integração T&amp;T, incluindo `mboxLoadSCPlugin`.

### Etapa 10: Ativar as opções de uso do Analytics como a fonte de relatórios do Target

Em [!DNL Target], clique em **[!UICONTROL Administração > Visual Experience Composer]** e escolha **[!UICONTROL Selecionar por atividade]** ou **[!UICONTROL Adobe Analytics]** para ativar as opções.

* **[!UICONTROL Selecionar por atividade permite escolher entre o e o para criar cada atividade.]**[!DNL Target][!DNL Analytics]
* **[!UICONTROL O Adobe configura o Analytics como fonte de relatórios para todas as atividades que você criar.]**[!DNL Analytics]


