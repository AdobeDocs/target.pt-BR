---
keywords: A4T;Adobe Analytics;Atividade baseada no Analytics;Conjunto de relatórios do Analytics;conjunto de relatórios;Integração do Analytics Target;configurar conjunto de relatórios;at.js;atjs;adobe experience platform web sdk;aep web sdk;platform web sdk
description: Siga as etapas necessárias para implementar o Analytics for [!DNL Target] (A4T) em suas soluções do Adobe [!DNL Target]  e da Adobe Analytics.
title: Como implementar o Analytics for [!DNL Target] (A4T)?
feature: Analytics for Target (A4T)
exl-id: b5269b9e-01ef-449a-bb03-3dcc2cd68af7
source-git-commit: ddfb06a17a24200b2aa4f01d370cc0e92ff5f180
workflow-type: tm+mt
source-wordcount: '1055'
ht-degree: 17%

---

# Implementação do Analytics para [!DNL Target]

Várias etapas são necessárias para implementar o [!DNL Adobe Analytics] como a fonte de relatórios do [!DNL Adobe Target] (A4T). O processo varia dependendo se você implementa o A4T com o [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=pt-BR) ou com a at.js.

## ![Selo do Adobe Experience Platform Web SDK](/help/main/assets/platform.png) Etapas de implementação para uma implementação do Adobe Experience Platform Web SDK {#platform}

As seções a seguir descrevem as etapas necessárias para implantar essa integração no site se você planeja usar o SDK da Web da plataforma:

### Etapa 1: solicitar provisionamento para [!DNL Analytics] e [!DNL Target]

Antes de implementar o A4T, você deve ser provisionado para [!DNL Analytics] e [!DNL Target]. [Use este formulário para solicitar o provisionamento](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y).

### Etapa 2: Configurar permissões do usuário

Os requisitos da conta de usuário devem ser atendidos antes que você possa criar uma atividade com base em [!DNL Analytics] em [!DNL Target]. Consulte [Requisitos de permissão do usuário](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Etapa 3: criar uma configuração do Edge

Crie uma configuração do Edge usando o [!DNL Adobe Experience Platform] com a ferramenta de configuração de borda. Configure o [Criar e configurar sequências de dados](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=pt-BR).

### Etapa 4: instalar e configurar o SDK da Web da plataforma

Para começar a fornecer experiências [!DNL Target] e aplicar o [!DNL Analytics] para fins de rastreamento e análise, [Instale](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/installing-the-sdk.html?lang=pt-BR) e [configure](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/configuring-the-sdk.html?lang=pt-BR) o SDK da Web da Platform nas páginas do site.

### Etapa 5: Ativar as opções de uso do A4T

Na interface do usuário do [!DNL Target], clique em **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** e escolha **[!UICONTROL Select per activity]** ou **[!UICONTROL Adobe Analytics]**.

* **[!UICONTROL Select per activity]** permite que você escolha entre [!DNL Target] e [!DNL Analytics] ao criar cada atividade.
* **[!UICONTROL Adobe Analytics]** define [!DNL Analytics] como a fonte de relatórios para todas as atividades que você criar.

## ![selo da at.js](/help/main/assets/atjs.png) Etapas de implementação para uma implementação da at.js{#section_73961BAD5BB4430A95E073DE5C026277}

As seções a seguir descrevem as etapas necessárias para implantar essa integração no site se você planeja usar a at.js:

### Etapa 1: solicitar provisionamento para o Analytics e o Target

Depois de implementar o [!DNL Analytics] como fonte de relatórios para [!DNL Target], você deve ser provisionado para [!DNL Analytics] e [!DNL Target]. [Use este formulário para solicitar o provisionamento](https://survey.adobe.com/jfe/form/SV_ekBHTLSoP5Zki2y){target=_blank}.

### Etapa 2: Configurar permissões do usuário

Os requisitos da conta de usuário devem ser atendidos antes que você possa criar uma atividade baseada em [!DNL Analytics] no [!DNL Target]. Consulte [Requisitos de permissão do usuário](/help/main/c-integrating-target-with-mac/a4t/account-reqs.md).

### Etapa 3: Implementar o serviço de ID de visitante da Experience Cloud

O serviço de ID de visitante permite identificar os usuários nas soluções do [!DNL Adobe Experience Cloud]. Implemente ou migre para a versão exigida da ID de visitante do Experience Cloud. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementar o Serviço de ID de Experience Cloud para o Target](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-target.html?lang=pt-BR) na documentação do *Serviço de ID de visitante de Experience Cloud*.

### Etapa 4: Atualizar o AppMeasurement para JavaScript ou s_code

Implemente ou migre para a versão exigida do appMeasurement.js. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Para novas implementações, consulte [visão geral da implementação do JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=pt-BR) no *Guia de Implementação do Analytics*.

Para migração, consulte [Migração para o AppMeasurement para o JavaScript](https://experienceleague.adobe.com/docs/analytics/implementation/js/migrate-from-hcode.html?lang=pt-BR) no *Guia de Implementação do Analytics*.

### Etapa 5: baixar e atualizar a at.js

Implemente ou migre para a versão exigida da at.js usando sua conta de produção. Não são necessárias modificações no código.

Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

### Etapa 6: Hospedagem de at.js

Se você implantou anteriormente a at.js, é possível substituir seu arquivo existente pela versão atualizada. Para obter mais informações, consulte &quot;Requisitos de implementação&quot; em [antes de implementar](/help/main/c-integrating-target-with-mac/a4t/before-implement.md).

Caso contrário, este arquivo pode ser hospedado com o serviço de ID de visitante e os arquivos do AppMeasurement para JavaScript. Esses arquivos devem ser hospedados em um servidor da Web que seja acessível a todas as páginas no seu site. Você precisa do caminho até esses arquivos na próxima etapa.

### Etapa 7: Referência a at.js em todas as páginas do site {#step7}

Inclua at.js abaixo de VisitorAPI.js adicionando a seguinte linha de código na tag de cada página:

Para at.js:

```javascript
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

O VisitorAPI.js deve ser carregado antes da at.js. Se estiver atualizando um arquivo at.js existente, verifique a ordem do carregamento.

A configuração padrão para a integração de [!DNL Target] e [!DNL Analytics], de uma perspectiva de implementação, é usar a SDID transmitida da página para unir a solicitação de [!DNL Target] e [!DNL Analytics] no back-end automaticamente.

Você pode controlar como e quando enviar dados de análise relacionados a [!DNL Target] para [!DNL Analytics] para fins de relatório. Se você não quiser aceitar as configurações padrão de ter o [!DNL Target] e o [!DNL Analytics] compilando automaticamente os dados de análise por meio da SDID, defina **analyticsLogging = client_side** via **window.targetGlobalSettings**. Observação: qualquer versão inferior a 2.1 não dá suporte a essa abordagem.

Por exemplo:

```javascript
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Essa configuração tem um efeito global, o que significa que cada chamada feita pela at.js tem **analyticsLogging: &quot;client_side&quot;** enviado nas solicitações [!DNL Target] e uma carga de análise é retornada para cada solicitação. Quando essa opção é configurada, o formato da carga retornada é semelhante ao seguinte:

```javascript
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

A carga pode ser encaminhada para o Analytics por meio da [API de inserção de dados](https://helpx.adobe.com/br/analytics/kb/data-insertion-api-post-method-adobe-analytics.html). Para atividades de Alocação automática e Direcionamento automático, você também deve encaminhar a sessionId. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html?lang=pt-BR){target=_blank} no *guia dos SDKs do Adobe Target*.

Se uma configuração global não for desejada e uma abordagem mais sob demanda for preferível, use a função da at.js [getOffers()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffers-atjs-2.html?lang=pt-BR){target=_blank} passando em **analyticsLogging: &quot;client_side&quot;**. A carga de análise é retornada somente para esta chamada e o back-end do [!DNL Target] não encaminha a carga para [!DNL Analytics]. Ao seguir essa abordagem, cada solicitação de at.js [!DNL Target] retorna a carga por padrão, mas somente quando desejado e especificado.

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

A carga pode ser encaminhada para [!DNL Analytics] por meio da [API de Inserção de Dados](https://helpx.adobe.com/br/analytics/kb/data-insertion-api-post-method-adobe-analytics.html).

### Etapa 8: Validar a implementação {#step8}

Carregue suas páginas depois de atualizar as bibliotecas JavaScript para confirmar que os valores de parâmetro `mboxMCSDID` nas chamadas do [!DNL Target] correspondem ao valor do parâmetro `sdid` na chamada de exibição de página [!DNL Analytics].

É especialmente importante confirmar se esses valores correspondem em Aplicativos de página única (SPA), nos quais a ordem das chamadas nem sempre é previsível.

>[!NOTE]
>
>A correspondência desses valores é necessária para que o A4T funcione corretamente.

### Etapa 9: (Opcional) Remover o código de integração anterior

A Adobe recomenda remover a integração anterior para simplificar sua implementação e eliminar a necessidade de classificar as discrepâncias entre os sistemas. Você pode remover qualquer código implantado por um SC anterior à integração T&amp;T, incluindo `mboxLoadSCPlugin`.

### Etapa 10: Ativar as opções de uso do Analytics como a fonte de relatórios do Target

Em [!DNL Target], clique em **[!UICONTROL Administration > Reporting]** e escolha **[!UICONTROL Select per activity]** ou **[!UICONTROL Adobe Analytics]** para habilitar as opções.

* **[!UICONTROL Select per activity]** permite que você escolha entre [!DNL Target] e [!DNL Analytics] ao criar cada atividade.
* **[!UICONTROL Adobe Analytics]** define [!DNL Analytics] como a fonte de relatórios para todas as atividades que você criar.


