---
keywords: versões do at.js; versões do at.js; aplicativo de página única; spa; entre domínios; entre domínios
description: Saiba como atualizar do Adobe [!DNL Target] at.js 1.x para at.js 2.x. Examine diagramas de fluxo do sistema, saiba mais sobre funções novas e obsoletas e muito mais.
title: Como faço para atualizar da at.js versão 1.x para a versão 2.x?
feature: at.js
role: Developer
exl-id: f5ec6bf1-f38c-4681-a6c1-b862272ee55d
source-git-commit: cf65cfb6641ce837717658e6fd5d0013e65f7875
workflow-type: tm+mt
source-wordcount: '2758'
ht-degree: 91%

---

# Atualização do at.js 1.*x* para o at.js 2.*x*

A versão mais recente da at.js no [!DNL Adobe Target] fornece conjuntos de recursos avançados para sua empresa personalizar tecnologias de próxima geração no lado do cliente. Essa nova versão tem como foco a atualização da at.js para ter interações harmoniosas com aplicativos de página única (SPAs).

Estes são alguns benefícios do uso do at.js 2.*x* que não estão disponíveis nas versões anteriores:

* A capacidade de armazenar em cache todas as ofertas no carregamento da página para reduzir várias chamadas do servidor a uma única chamada de servidor.
* Melhore bastante as experiências dos usuários finais em seu site, uma vez que as ofertas são exibidas imediatamente por meio do cache, sem o atraso imposto pelas chamadas tradicionais do servidor.
* Uma linha de código simples e uma configuração de desenvolvedor única para permitir que seus profissionais de marketing criem e executem atividades A/B e XT por meio do VEC em seus SPAs.

## at.js 2.*x*  Diagramas do sistema

Os diagramas a seguir ajudam a entender o fluxo de trabalho do at.js 2.*x* com Exibições e como isso melhora a integração de SPA. Para obter uma melhor introdução dos conceitos usados no at.js 2.*x*, consulte [Implementação de aplicativos de página única](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![Fluxo do Target com o at.js 2.*x*](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

| Chama | Detalhes |
| --- | --- |
| 1 | A chamada retorna o [!DNL Experience Cloud ID] caso o usuário seja autenticado; outra chamada sincroniza a ID do cliente. |
| 2 | A biblioteca at.js é carregada de modo síncrono e oculta o corpo do documento.<br>O at.js também pode ser carregado de forma assíncrona com uma opção que oculta previamente o trecho implementado na página. |
| 3 | Uma solicitação de carregamento de página é feita, incluindo todos os parâmetros configurados (MCID, SDID e ID do cliente). |
| 4 | Os scripts de perfil executam e, em seguida, fazem o feed na Loja do perfil. A Loja solicita que os públicos-alvos qualificados da Biblioteca de público-alvos (por exemplo, públicos alvos compartilhados do Adobe Analytics, Gerenciamento de público-alvo etc.).<br>Os atributos do cliente são enviados à Loja de perfis em um processo em lote. |
| 5 | Com base nos parâmetros de solicitação de URL e dados de perfil, [!DNL Target] decide quais atividades e experiências retornarão ao visitante para a página atual e para as exibições futuras. |
| 6 | O conteúdo direcionado é enviado de volta para a página, incluindo, opcionalmente, valores de perfil para personalização adicional.<br>O conteúdo direcionado na página atual é revelado o mais rápido possível sem cintilação do conteúdo padrão.<br>Conteúdo direcionado para exibições que são mostradas como resultado das ações do usuário em um SPA, que é armazenado em cache no navegador para que possa ser aplicado instantaneamente, sem uma chamada de servidor adicional, quando as exibições forem acionadas `triggerView()`. |
| 7 | Os dados do Analytics são enviados ao servidores de Coleção de dados. |
| 8 | Os dados direcionados correspondem aos dados do Analytics por meio da SDID e são processados no armazenamento de relatórios do Analytics.<br>Em seguida, os dados do Analytics podem ser visualizados no Analytics e no Target pelos relatórios do Analytics for Target (A4T). |

Agora, onde quer `triggerView()` que seja implementada em seu SPA, as Exibições e as ações são recuperadas do cache e mostradas ao usuário, sem uma chamada de servidor. `triggerView()` também faz uma solicitação de notificações ao [!DNL Target] backend para aumentar e registrar contagens de impressão.

![Fluxo do Target com o at.js 2.*x* triggerView](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Chama | Detalhes |
| --- | --- |
| 1 | `triggerView()` é chamado no SPA para renderizar a Exibição e aplicar ações para modificar elementos visuais. |
| 2 | O conteúdo direcionado para a exibição é lido do cache. |
| 1 | O conteúdo direcionado é revelado o mais rápido possível sem oscilação do conteúdo padrão. |
| 4 | A solicitação de notificação é enviada para a [!DNL Target] Loja de perfil para contar o visitante nas métricas de atividade e incremento. |
| 5 | Os dados do Analytics são enviados aos Servidores de coleta de dados. |
| 6 | Os dados do Target são correspondidos aos dados do Analytics pela SDID, e processados no armazenamento de relatório do Analytics. Em seguida, os dados do Analytics podem ser visualizados no Analytics e no Target pelos relatórios do A4T. |

## Implantar o at.js 2.*x*  {#deploy-atjs-200}

1. Implantar o at.js 2.** tags xvia na  [[!DNL Adobe Experience Platform]](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) extensão.

   >[!NOTE]
   >
   > A implantação da at.js usando tags em [!DNL Adobe Experience Platform] é o método preferido.

   Ou

   Baixe manualmente o at.js 2.*x* usando a interface do usuário do Target e implante-a usando o método [da sua escolha](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/how-to-deployatjs.md).

## Funções obsoletas da at.js

Há várias funções que foram descontinuadas no at.js 2.*x*.

>[!IMPORTANT]
>
>Se essas funções obsoletas ainda forem usadas no site quando o at.js 2.*x* for implantado, serão exibidos avisos no console. A abordagem recomendada durante a atualização é testar a implantação do at.js 2.*x* em um ambiente de preparo, analisar cada um dos avisos registrados no console e substituir as funções obsoletas por novas funções introduzidas no at.js 2.*x*.

Você pode encontrar as funções obsoletas e a contraparte abaixo. Para obter uma lista completa das funções, consulte [funções da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>at.js 2.*x*  O não oculta automaticamente os elementos `mboxDefault` marcados. Os clientes devem, portanto, acomodar a lógica de pré-ocultação manualmente no site ou por meio de um gerenciador de tags.

### mboxCreate(mbox,params)

**Descrição**:

Executa uma solicitação e aplica a oferta ao DIV mais próximo com o nome de classe `mboxDefault`.

**Exemplo**:

```
<div class="mboxDefault">
  default content to replace by offer
</div>
<script>
  mboxCreate('mboxName','param1=value1','param2=value2');
</script>
```

**at.js 2.*x* equivalente**

Uma alternativa para `mboxCreate(mbox, params)` é `getOffer()` e `applyOffer()`.

**Exemplo**:

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  var el = document.currentScript.previousElementSibling;
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2"
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: el,
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      el.style.visibility = "visible";
    }
  });
</script> 
```

### mboxDefine() e mboxUpdate()

**Descrição**:

Cria um mapeamento interno entre um elemento e um nome de mbox, mas não executa a solicitação. Usada em conjunto com `mboxUpdate()`, que executa a solicitação e aplica a oferta ao elemento identificado pelo nodeId em `mboxDefine()`. Também pose ser usada para atualizar uma mbox iniciada por `mboxCreate`.

**Exemplo**:

```
<div id="someId" class="mboxDefault"></div>
<script>
 mboxDefine('someId','mboxName','param1=value1','param2=value2');
 mboxUpdate('mboxName','param3=value3','param4=value4');
</script>
```

**at.js 2.*x* equivalente**:

Uma alternativa para `mboxDefine()` e `mboxUpdate` é `getOffer()` e `applyOffer()`, com a opção do seletor usada em `applyOffer()`. Essa abordagem permite mapear a oferta para um elemento usando qualquer seletor de CSS, não apenas um com uma ID.

**Exemplo**:

```
<div id="someId" class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  adobe.target.getOffer({
    mbox: "mboxName",
    params: {
      param1: "value1",
      param2: "value2",
      param3: "value3",
      param4: "value4" 
    },
    success: function(offer) {
      adobe.target.applyOffer({
        mbox: "mboxName",
        selector: "#someId",
        offer: offer
      });
    },
    error: function(error) {
      console.error(error);
      var el = document.getElementById("someId");
      el.style.visibility = "visible";
    }
  });
</script>
```

### adobe.target.registerExtension()

**Descrição**:

Fornece uma forma padrão de registrar uma extensão específica.

Isso não é mais suportado e não deve ser usado.

## Resumo das funções obsoletas, novas e suportadas at.js em 2.*x* 

| Método | Suportado? | Novo? | Obsoleto?<br>(O conteúdo padrão será exibido) |
| --- | --- | --- | --- |
| `getOffer()` | Sim |  |  |
| `getOffers()` |  | Sim |  |
| `applyOffer()` | Sim |  |  |
| `applyOffers()` |  | Sim |  |
| `triggerView()` |  | Sim |  |
| `trackEvent()` | Sim |  |  |
| `mboxCreate()` |  |  | Sim |
| `mboxDefine()`<br>`mboxUpdate()` |  |  | Sim |
| `targetGlobalSettings()` | Sim |  |  |
| `Data Providers` | Sim |  |  |
| `targetPageParams()` | Sim |  |  |
| `targetPageParamsAll()` | Sim |  |  |
| `registerExtension()` |  |  | Sim |
| `At.js Custom Events` | Sim |  |  |

## Limitações e chamadas de retorno

Esteja ciente das seguintes limitações e chamadas de retorno:

### Rastreamento de conversão

Os clientes que usam `mboxCreate()` para rastreamento de conversão devem usar `trackEvent()` ou `getOffer()`.

### Entrega de oferta

Os clientes que não substituírem `mboxCreate()` por `getOffer()` ou `applyOffer()` correm o risco de não ter ofertas entregues.

### O at.js 2.*x* pode ser usado em algumas páginas enquanto o at.js 1.** xis em outras páginas?

Sim, o perfil do visitante é preservado nas páginas usando diferentes versões e bibliotecas. O formato de cookie é o mesmo.

### Nova API usada no at.js 2.*x*

at.js 2.*x*  A usa uma nova API, chamada de API de entrega. Para depurar se o at.js está chamando o servidor [!DNL Target] de borda corretamente, você pode filtrar a guia Rede das Ferramentas do desenvolvedor do seu navegador para “entrega”, “`tt.omtrdc.net`”, ou seu código de cliente. Você também notará que [!DNL Target] envia uma carga JSON em vez de pares de valores-chave.

### A mbox global do Target não é mais usada

Em at.js 2.Na *x*, “`target-global-mbox`” não estará mais visível nas chamadas de rede. Em vez disso, substituímos a sintaxe &quot;`target-global-mbox`&quot; por &quot;`execute > pageLoad`&quot; na carga JSON enviada aos [!DNL Target] servidores, como observado a seguir:

```
{
  "id": {
    // ...
  },
  "context": {
    "channel": "web",
    // ...
  },
  "execute": {
    "pageLoad": {}
  }
}
```

Basicamente, o conceito global de mbox foi apresentado para [!DNL Target] informar se recupera ofertas e conteúdo no carregamento de página. Dessa forma, deixamos isso mais explícito na versão mais recente.

### O nome da mbox global no at.js não importa mais?

Os clientes podem especificar um nome de mbox global por meio do [!UICONTROL Target > Administração > Implementação > Editar configurações da at.js]. Essa configuração é usada pelos servidores de borda [!DNL Target] para traduzir execute > pageLoad para o nome da mbox global que aparece na interface do [!DNL Target]. Isso permite que os clientes continuem a usar APIs do lado do servidor, o compositor baseado em formulário, scripts de perfil e criar públicos-alvo usando o nome global da mbox. Recomendamos que você também verifique se o mesmo nome global da mbox está configurado na página [!UICONTROL Administration > Visual Experience Composer], caso ainda tenha páginas usando a at.js 1.*x*, conforme mostrado nas ilustrações a seguir.

![Modificar caixa de diálogo da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

e

![Mbox global personalizada](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

### A configuração de mbox global de criação automática precisa ser ativada para o at.js 2.*x*?

Na maioria dos casos, sim. Essa configuração informa à at.js 2.*x* para disparar uma solicitação nos servidores de borda do [!DNL Target] ao carregar a página. Como a mbox global é traduzida para executar o > pageLoad e se você quiser acionar uma solicitação no carregamento da página, essa configuração deve estar ativada.

### As atividades existentes do VEC continuarão a funcionar, mesmo que o nome da mbox global do Target não seja especificado no at.js 2.*x*?

Sim, porque executar > carga é tratado no [!DNL Target] backend como `target-global-mbox`.

### Se minhas atividades baseadas em formulário forem direcionadas para o `target-global-mbox`, essas atividades continuarão funcionando?

Sim, porque executar > carga é tratado nos servidores [!DNL Target] de borda como `target-global-mbox`.

### Configurações compatíveis e não compatíveis no at.js 2.*x*

| Configuração | Suportado? |
| --- | --- |
| Domínio X | Não |
| Criar automaticamente mbox global | Sim |
| Nome da mbox global | Sim |

### Suporte de rastreamento entre domínios no at.js 2.x {#cross-domain}

O rastreamento entre domínios possibilita unir visitantes em diferentes domínios. Como um novo cookie deve ser criado para cada domínio, é difícil rastrear os visitantes quando eles navegam de um domínio para outro. Para realizar o rastreamento entre domínios, o [!DNL Target] usa um cookie de terceiros para rastrear visitantes entre domínios. Isso permite criar uma atividade do Target que abrange o `siteA.com` e o `siteB.com`, e os visitantes permanecem na mesma experiência quando navegam entre domínios únicos. Essa funcionalidade se associa ao comportamento de cookies de terceiros e próprios do Target.

>[!NOTE]
>
>O rastreamento entre domínios não é compatível imediatamente com o at.js 2.*x*. O rastreamento entre domínios é compatível com o at.js 2.*x* por meio da biblioteca da Experience Cloud ID (ECID) v4.3.0+.

No Target, o cookie de terceiros é armazenado no `<CLIENTCODE>.tt.omtrdc.net`. O cookie próprio é armazenado no `clientdomain.com`. A primeira solicitação retorna cabeçalhos de resposta HTTP que tentam instalar cookies de terceiros chamados `mboxSession` e `mboxPC`, enquanto uma solicitação de redirecionamento é enviada de volta com um parâmetro extra (`mboxXDomainCheck=true`). Se o navegador aceitar cookies de terceiros, a solicitação de redirecionamento vai inclui-los, e a experiência será retornada. Esse fluxo de trabalho é possível porque usamos o método HTTP GET.

No entanto, no at.js 2.*x*, o HTTP GET não é mais usado e, em vez disso, usamos o HTTP POST. Agora o HTTP POST é usado por meio do at.js 2.*x* para enviar cargas JSON para os servidores do Target Edge. Isso significa que a solicitação de redirecionamento para verificar se um navegador suporta cookies de terceiros agora está rompida. Isso ocorre porque as solicitações HTTP GET são transações idempotentes, enquanto HTTP POST é não idempotente e não deve ser repetido arbitrariamente. Por isso, o rastreamento entre domínios no at.js 2.*x* não é mais compatível imediatamente. Somente o at.js 1.*x* tem suporte pronto para uso para rastreamento entre domínios.

Se quiser usar o rastreamento entre domínios, instale a biblioteca da ECID v4.3.0+](https://experienceleague.adobe.com/docs/id-service/using/release-notes/release-notes.html?lang=pt-BR) juntamente com o at.js 2.[*x*. A biblioteca da ECID existe para gerenciar IDs persistentes usadas para identificar um visitante, mesmo entre domínios.

>[!NOTE]
>
>Depois de instalar a biblioteca da ECID v4.3.0+ e o at.js 2.*x*, você poderá criar atividades que abrangem domínios exclusivos e rastrear usuários. É importante observar que essa funcionalidade funciona somente após a sessão expirar.

### Criar automaticamente mbox global é compatível

Essa configuração informa à at.js 2.*x* para disparar uma solicitação nos servidores de borda do [!DNL Target] no carregamento da página. Como a mbox global é traduzida para executar > carga, e isso é interpretado pelos servidores [!DNL Target] de borda, os clientes devem ativar esse recurso se quiserem acionar uma solicitação no carregamento da página.

### O nome da mbox global é compatível

Os clientes podem especificar um nome de mbox global por meio do [!UICONTROL Target > Administração > Implementação > Editar]. Essa configuração é usada pelos [!DNL Target] servidores de borda para traduzir executar > carga para o nome da mbox global inserido. Isso permite que os clientes continuem a usar APIs do lado do servidor, o compositor baseado em formulário, scripts de perfil e criar públicos-alvo que direcionem a mbox global.

### Os eventos personalizados da at.js abaixo são aplicáveis a `triggerView()` ou são somente para `applyOffer()` ou `applyOffers()`?

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

Sim, os eventos personalizados da at.js `triggerView()` também se aplicam.

### Ele informa quando eu chamo `triggerView()` com &amp;lbrace;`“page” : “true”`&amp;rbrace;, enviará uma notificação para o [!DNL Target] backend e aumentará a impressão. Também faz com que os scripts de perfil sejam executados?

Quando uma chamada de pré-busca é feita no [!DNL Target] backend, os scripts de perfil são executados. Consequentemente, os dados de perfil afetados serão criptografados e enviados para o lado do cliente. Após invocar `triggerView()` com `{"page": "true"}`, uma notificação é enviada juntamente com os dados de perfil criptografados. Isso ocorre quando o [!DNL Target] backend descriptografa os dados do perfil e armazena nos bancos de dados.

### Precisamos adicionar um código que oculta previamente antes da chamada `triggerView()` a fim de gerenciar a cintilação?

Não, não é necessário adicionar código de pré-ocultação antes de chamar `triggerView()`. at.js 2.*x*  A gerencia a lógica de pré-ocultação e cintilação antes da exibição e aplicação da exibição.

### Qual at.js 1.** xparameters para criar públicos-alvo não são compatíveis com o at.js 2.*x*? {#audience-parameters}

Os seguintes parâmetros da at.js 1.x são *NOT* compatíveis com a criação de público-alvo ao usar a at.js 2.*x*:

* browserHeight
* browserWidth
* browserTimeOffset
* screenHeight
* screenWidth
* screenOrientation
* colorDepth
* devicePixelRatio

## compatibilidade com o at.js

As tabelas a seguir explicam o at.js. 2.*x* compatibilidade com diferentes tipos de atividades, integrações, recursos e funções da at.js.

### Tipos de atividade {#types}

| Tipo | Suportado? |
| --- | --- |
| Teste A/B | Sim |
| Alocação automática | Sim |
| Direcionamento automático | Sim |
| Direcionamento de experiência | Sim |
| Teste multivariado | Sim |
| Personalização automatizada | Sim |
| Recommendations | Sim |

>[!NOTE]
>
>As atividades de Direcionamento automático são compatíveis por meio do at.js 2.*x* e do VEC quando todas as modificações são aplicadas ao `Page Load Event`. Quando as modificações são adicionadas a exibições específicas, somente as atividades de Teste A/B, Alocação automática e Direcionamento de experiência (XT) são suportadas.

### Integrações {#integrations}

| Tipo | Suportado? |
| --- | --- |
| Analytics for Target (A4T) | Sim |
| Públicos-alvo | Sim |
| Atributos do cliente | Sim |
| Fragmentos de experiência do AEM | Sim |
| [!DNL Adobe Experience Platform] extensão | [Sim](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) |
| Depurador | Sim |
| Auditor | As regras ainda não foram atualizadas para o at.js 2.*x* |
| Opt-In | Não. O Opt-in dá suporte ao [GDPR](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) na [at.js versão 2.1.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md). |
| Personalização aprimorada do AEM fornecida pelo Adobe Target | Não |

### Recursos

| Recurso | Suportado? |
| --- | --- |
| Domínio X | Não |
| Propriedades/espaços de trabalho | Sim |
| Links de Controle de qualidade | Sim |
| Experience Composer baseado em formulário | Sim |
| Visual Experience Composer (VEC) | Sim |
| Código personalizado | Sim |
| Tokens de resposta | [Sim](#response-tokens) |
| Rastreamento de cliques | Sim |
| Disponibilização de várias atividades | Sim |
| targetGlobalSettings | Sim (mas não domínio x) |
| Métodos da at.js | Há suporte para tudo, exceto para <br>`mboxCreate()`<br>`mboxUpdate()`<br>`mboxDefine()`<br> que exibirá o conteúdo padrão. |

### Parâmetros da string de consulta

| Parâmetro | Suportado? |
| --- | --- |
| `?mboxDisable` | Sim |
| `?mboxDisable` | Sim |
| `?mboxTrace` | Sim |
| `?mboxSession` | Não |
| `?mboxOverride.browserIp` | Sim |

## Tokens de resposta {#response-tokens}

at.js 2.*x*, como a at.js 1.*x*, usa o evento personalizado `at-request-succeeded` para acionar tokens de resposta. Para obter exemplos de código usando o evento personalizado do `at-request-succeeded`, consulte [Tokens de resposta](/help/administrating-target/response-tokens.md).

## at.js 1.*x*  para o mapeamento de carga do at.js 2.*x* {#payload-mapping}

Esta seção descreve os mapeamentos entre a at.js 1.*x* e at.js 2.*x*.

Antes de analisar o mapeamento de parâmetros, os endpoints usados por essas versões de biblioteca foram alterados:

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at.js 2.*x*  - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

Outra diferença significativa é que:

* at.js 1.*x* - O código do cliente faz parte do caminho
* at.js 2.*x*  - O código do cliente é enviado como um parâmetro de sequência de consulta, como:
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

As seções a seguir listam todos os parâmetros da at.js 1.** xparameter, sua descrição e o 2 correspondente.** Carga xJSON (se aplicável):

### at_property

(at.js 1.*x* parâmetro)

Usado para [Permissões de usuário do Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md).

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### mboxHost

(at.js 1.*x* parâmetro)

O domínio da página em que a biblioteca do Target é executada.

at.js 2.*x*  Carga JSON:

```
{
  "context": {
    "browser": {
       "host": "test.com"
    }
  }
}
```

### webGLRenderer

(at.js 1.*x* parâmetro)

Os recursos de renderização da Web GL do navegador. Isso é usado pelo nosso mecanismo de detecção de dispositivo para determinar se o dispositivo do visitante é um desktop, iPhone, dispositivo Android, etc.

at.js 2.*x*  Carga JSON:

```
{
  "context": {
    "browser": {
       "webGLRenderer": "AMD Radeon Pro 560X OpenGL Engine"
    }
  }
}
```

### mboxURL

(at.js 1.*x* parâmetro)

O URL da página.

at.js 2.*x*  Carga JSON:

```
{
  "context": {
    "address": {
       "url": "http://test.com"
    }
  }
}
```

### mboxReferrer

(at.js 1.*x* parâmetro)

O referenciador de página.

at.js 2.*x*  Carga JSON:

```
{
  "context": {
    "address": {
       "referringUrl": "http://google.com"
    }
  }
}
```

### mbox (o nome) igual à mbox global

(at.js 1.*x* parâmetro)

A API de entrega não tem mais um conceito de mbox global. Na carga JSON, você deve usar `execute > pageLoad`.

at.js 2.*x*  Carga JSON:

```
{
  "execute": {
    "pageLoad": {
       "parameters": ....
       "profileParameters": ...
       .....
    }
  }
}
```

### mbox (o nome) *não* é igual à mbox global

(at.js 1.*x* parâmetro)

Para usar um nome de mbox, passe-o para `execute > mboxes`. Uma mbox exige um índice e um nome.

at.js 2.*x*  Carga JSON:

```
{
  "execute": {
    "mboxes": [{
       "index": 0,
       "name": "some-mbox",
       "parameters": ....
       "profileParameters": ...
       .....
    }]
  }
}
```

### mboxId

(at.js 1.*x* parâmetro)

Não está mais em uso.

### mboxCount

(at.js 1.*x* parâmetro)

Não está mais em uso.

### mboxRid

(at.js 1.*x* parâmetro)

A ID de solicitação usada por sistemas de downstream para ajudar na depuração.

at.js 2.*x*  Carga JSON:

```
{
  "requestId": "2412234442342"
  ....
}
```

### mboxTime

(at.js 1.*x* parâmetro)

Não está mais em uso.

### mboxSession

(at.js 1.*x* parâmetro)

A ID da sessão é enviada como parâmetro de sequência de consulta (`sessionId`) para o endpoint da API de entrega.

### mboxPC

(at.js 1.*x* parâmetro)

A ID de TNT é passada para `id > tntId`.

at.js 2.*x*  Carga JSON:

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1.*x* parâmetro)

A ID de visitante da Experience Cloud é passada para `id > marketingCloudVisitorId`.

at.js 2.*x*  Carga JSON:

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### `vst.aaaa.id` e `vst.aaaa.authState`

(at.js 1.*x* parâmetros)

As IDs do cliente devem ser passadas para `id > customerIds`.

at.js 2.*x*  Carga JSON:

```
{
  "id": {
    "customerIds": [{
       "id": "1232131",
       "integrationCode": "aaaa",
       "authenticatedState": "....."
     }]
  }
  ....
}
```

### mbox3rdPartyId

(at.js 1.*x* parâmetro)

A ID de terceiros do cliente usada para vincular IDs do Target diferentes.

at.js 2.*x*  Carga JSON:

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### mboxMCSDID

(at.js 1.*x* parâmetro)

SDID, também conhecida como ID de dados complementares. Deve ser passado para `experienceCloud > analytics > supplementalDataId`.

at.js 2.*x*  Carga JSON:

```
{
  "experienceCloud": {
    "analytics": {
      "supplementalDataId": "1212321132123131"
    }
  }
  ....
}
```

### vst.trk

(at.js 1.*x* parâmetro)

Servidor de rastreamento do Analytics. Deve ser passado para `experienceCloud > analytics > trackingServer`.

at.js 2.*x*  Carga JSON:

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServer": "analytics.test.com"
    }
  }
  ....
}
```

### vst.trks

(at.js 1.*x* parâmetro)

Servidor de rastreamento do Analytics seguro. Deve ser passado para `experienceCloud > analytics > trackingServerSecure`.

at.js 2.*x*  Carga JSON:

```
{
  "experienceCloud": {
    "analytics": {
      "trackingServerSecure": "secure-analytics.test.com"
    }
  }
  ....
}
```

### mboxMCGLH

(at.js 1.*x* parâmetro)

Dica de localização do Audience Manager. Deve ser passado para `experienceCloud > audienceManager > locationHint`.

at.js 2.*x*  Carga JSON:

```
{
  "experienceCloud": {
    "audienceManager": {
      "locationHint": 9
    }
  }
  ....
}
```

### mboxAAMB

(at.js 1.*x* parâmetro)

Blob do Audience Manager. Deve ser passado para `experienceCloud > audienceManager > blob`.

at.js 2.*x*  Carga JSON:

```
{
  "experienceCloud": {
    "audienceManager": {
      "blob": "2142342343242342"
    }
  }
  ....
}
```

### mboxVersion

(at.js 1.*x* parâmetro)

A versão é enviada como um parâmetro de sequência de consulta por meio do parâmetro da versão.

## Vídeo de treinamento: at.js 2.** Selo de  ![visão geral do diagrama xarchitecture](/help/assets/overview.png)

at.js 2.*x*  A aprimora o suporte do Adobe Target para SPAs e integra-se com outras soluções da Experience Cloud. Este vídeo explica como tudo se une.

>[!VIDEO](https://video.tv.adobe.com/v/26250)

Consulte [Como entender o at.js 2.** ](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) xworkspara obter mais informações.
