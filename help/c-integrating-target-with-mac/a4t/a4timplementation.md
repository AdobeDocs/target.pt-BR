---
description: Várias etapas são necessárias para a implementação do Adobe Analytics como a fonte de geração de relatórios para o Target (A4T).
keywords: A4T; Adobe Analytics; Atividade baseada no Analytics; Conjunto de relatórios do Analytics; conjunto de relatórios; Integração do Analytics Target; configurar conjunto de relatórios
seo-description: Várias etapas são necessárias para a implementação do Adobe Analytics como a fonte de geração de relatórios para o Target (A4T).
seo-title: Implementação do Analytics for Target
solution: Target
title: Implementação do Analytics for Target
topic: Premium
uuid: da6498c8-1549-4c36-ae42-38c731a28f08
translation-type: tm+mt
source-git-commit: 8dc94ca1ed48366e6b3ac7a75b03c214f1db71d9

---


# Implementação do Analytics for Target{#analytics-for-target-implementation}

Várias etapas são necessárias para a implementação do Adobe Analytics como a fonte de geração de relatórios para o Target (A4T).

## Etapas da implementação {#section_73961BAD5BB4430A95E073DE5C026277}

A tabela a seguir descreve as etapas necessárias para implantar essa integração no seu site.

## Etapa 1: Solicitar provisionamento para o Analytics e Target

Após implementar o Analytics como fonte de relatórios para o Target, você deve ser provisionado para Analytics e Target. [Use este formulário para solicitar o aprovisionamento](http://www.adobe.com/go/audiences).

## Etapa 2: Configurar permissões do usuário

As exigências da conta do usuário devem ser atendidas antes da criação de uma atividade no Adobe Target baseada no Adobe Analytics. Consulte [Exigências de permissão do usuário](/help/c-integrating-target-with-mac/a4t/account-reqs.md).

## Etapa 3: Implementar o serviço de ID de visitante da Experience Cloud

O serviço de ID do visitante permite identificar os usuários através das soluções da Experience Cloud. Você deve implementar ou migrar para a versão exigida da ID de visitante da Experience Cloud. Para obter mais informações, consulte "Requisitos de implementação" em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Consulte [Implementar o Serviço da Experience Cloud ID para Target](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/setup-target.html) na documentação Serviço da ID de visitante da Experience Cloud.

## Etapa 4: Atualizar o AppMeasurement para JavaScript ou s_code

Você deve implementar ou migrar para a versão exigida da appMeasurement.js. Para obter mais informações, consulte "Requisitos de implementação" em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Para novas implementações, consulte Visão geral [da implementação do](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) JavaScript no Guia *de implementação do* Analytics.

Para obter uma migração, consulte [Migração para o AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs-migrate.html) no Guia *de implementação do* Analytics.

## Etapa 5: Baixe e atualize o at.js ou mbox.js

Você deve implementar ou migrar para a versão exigida da at.js ou da mbox.js usando sua conta de produção. Não são necessárias modificações no código.

Para obter mais informações, consulte "Requisitos de implementação" em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

## Etapa 6: Hospedagem de at.js ou mbox.js

Se você implantou anteriormente o at.js ou o mbox.js, você pode substituir seu arquivo existente pela versão atualizada. Para obter mais informações, consulte "Requisitos de implementação" em [antes de implementar](/help/c-integrating-target-with-mac/a4t/before-implement.md).

Caso contrário, este arquivo pode ser hospedado com o serviço de ID de visitante e os arquivos do AppMeasurement para JavaScript. Esses arquivos devem ser hospedados em um servidor da Web que seja acessível a todas as páginas no seu site. Você precisa do caminho até esses arquivos na próxima etapa.

## Etapa 7: Referência a at.js ou mbox.js em todas as páginas do site {#step7}

Inclua at.js ou mbox.js abaixo de VisitorAPI.js adicionando a seguinte linha de código na tag de cada página:

Para at.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/at.js"></script>
```

Para mbox.js:

```
<script language="JavaScript" type="text/javascript"
src="http://INSERT-DOMAIN-AND-PATH-TO-CODE-HERE/mbox.js"></script>
```

É essencial que o VisitorAPI.js seja carregado antes da at.js ou da mbox.js. Se estiver atualizando um arquivo at.js ou mbox.js existente, verifique a ordem do carregamento.

As configurações padrão são definidas para a integração do Target e do Analytics, do ponto de vista da implementação, usando a SDID transmitida da página para unir a solicitação do Target e do Analytics ao back-end automaticamente para você.

No entanto, se você quiser ter mais controle sobre como e quando enviar dados de análise relacionados ao Target para o Analytics para fins de relatório, e não quiser aderir às configurações padrão que unem os dados de análise do Target e do Analytics automaticamente por meio da SDID, poderá definir **analyticsLogging = client_side** via **window.targetGlobalSettings**. Observação: qualquer versão inferior a 2.1 não dá suporte a essa abordagem.

Por exemplo:

```
window.targetGlobalSettings = {
  analyticsLogging: "client_side"
};
```

Essa configuração tem um efeito global, o que significa que **analyticsLogging: "client_side"** será enviado para todas as chamadas feitas pela at.js nas solicitações do Target e uma carga de análise será retornada para cada solicitação. Quando configurado, o formato da carga retornada é semelhante ao seguinte:

```
"analytics": {
   "payload": {
      "pe": "tnt",
      "tnta": "167169:0:0|0|100,167169:0:0|2|100,167169:0:0|1|100"
   }
}
```

A carga pode ser encaminhada ao Analytics por meio da API [de inserção de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)dados.

Se uma configuração global não for desejada e uma abordagem mais sob demanda for preferível, você poderá usar a função [getOffers()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md) para fazer isso, passando em **analyticsLogging: "client_side"**. A carga de análise será retornada somente para esta chamada e o back-end do Target não encaminhará a carga para o Analytics. Ao seguir essa abordagem, as solicitações da at.js do Target não retornarão a carga por padrão, somente quando isso for desejado e especificado.

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

A carga pode ser encaminhada ao Analytics por meio da API [de inserção de](https://helpx.adobe.com/analytics/kb/data-insertion-api-post-method-adobe-analytics.html)dados.

## Etapa 8: Validar a implementação {#step8}

Carregue suas páginas depois de atualizar as bibliotecas JavaScript para confirmar que os valores dos parâmetros mboxMCSDID nas chamadas do Target são compatíveis com o valor do parâmetro sdid na chamada de exibição de página do Analytics.

Isso é especialmente importante para confirmar em Aplicativos de página única (SPAs), onde a ordem das chamadas nem sempre é previsível.

**Observação:** a compatibilidade desses valores é necessária para que o A4T funcione corretamente.

## Etapa 9: (Opcional) Remover o código de integração anterior

Recomendamos remover a integração anterior para simplificar sua implementação e eliminar a necessidade de classificar as discrepâncias entre os sistemas. Você pode remover qualquer código implantado por um SC anterior à integração T&amp;T, incluindo `mboxLoadSCPlugin`.

## Etapa 10: Ativar as opções de uso do Analytics como a fonte de relatórios do Target

No Target, clique em [!UICONTROL Configurar &gt; Preferências] escolha [!UICONTROL Selecionar por atividade] ou [!UICONTROL Adobe Analytics] para habilitar as opções.

* Selecionar por atividade permite escolher entre o Target e o Analytics para criar cada atividade.
* O Adobe Analytics configura o Analytics como fonte de relatórios para todas as atividades que você criar.

