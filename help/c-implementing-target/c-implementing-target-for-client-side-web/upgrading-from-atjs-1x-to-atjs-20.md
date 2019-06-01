---
description: Atualização de at. js 1. x para at. js 2. x
keywords: versões da at.js; versões da at.js; aplicativo de página única; spa
seo-description: Informações detalhadas sobre como atualizar do Adobe Target at.js 1.x para o at.js versão 2.0.0
seo-title: 'Atualização do Adobe Target da at.js versão 1.x para a at.js versão 2.0.0 '
solution: Target
subtopic: Introdução
title: Atualização de at. js 1. x para at. js 2. x
uuid: 3586af55-db15-4e68-90a7-d552338ec5e8
translation-type: tm+mt
source-git-commit: 4315e6dbec175b22fb7b321719c2f3e2d6729009

---


# Atualização de at. js 1. x para at. js 2. x {#upgrading-from-atjs-1x-to-atjs-200}

A versão mais recente do at. js em [!DNL Adobe Target] fornecer conjuntos de recursos avançados que fazem com que seus negócios executem personalização em tecnologias de próxima geração e cliente. Essa nova versão tem como foco a atualização da at.js para ter interações harmoniosas com aplicativos de página única (SPAs).

Estes são alguns benefícios do uso de at. js 2. x que não estão disponíveis nas versões anteriores:

* A capacidade de armazenar em cache todas as ofertas no carregamento da página para reduzir várias chamadas do servidor a uma única chamada de servidor.
* Melhore bastante as experiências dos usuários finais em seu site, uma vez que as ofertas são exibidas imediatamente por meio do cache, sem o atraso imposto pelas chamadas tradicionais do servidor.
* Uma linha de código simples e uma configuração de desenvolvedor única para permitir que seus profissionais de marketing criem e executem atividades A/B e XT por meio do VEC em seus SPAs.

## Diagramas do sistema at. js 2. x

Os diagramas a seguir ajudam você a entender o fluxo de trabalho do at. js 2. x com Exibições e como isso aprimora a integração de SPA. Para obter uma melhor introdução dos conceitos usados em at. js 2. x, consulte [Implementação de aplicativos de página única](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/target-atjs-single-page-application.md).

![Fluxo do Target com at. js 2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/system-diagram-atjs-20.png)

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

![Fluxo de target at. js 2. x triggerview](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-triggerview.png)

| Chama | Detalhes |
| --- | --- |
| 1 | `triggerView()` é chamado no SPA para renderizar a Exibição e aplicar ações para modificar elementos visuais. |
| 2 | O conteúdo direcionado para a exibição é lido do cache. |
| 3 | O conteúdo direcionado é revelado o mais rápido possível sem oscilação do conteúdo padrão. |
| 4 | A solicitação de notificação é enviada para a [!DNL Target] Loja de perfil para contar o visitante nas métricas de atividade e incremento. |
| 5 | Os dados do Analytics são enviados aos Servidores de coleta de dados. |
| 6 | Os dados do Target são correspondidos aos dados do Analytics pela SDID, e processados no armazenamento de relatório do Analytics. Em seguida, os dados do Analytics podem ser visualizados no Analytics e no Target pelos relatórios do A4T. |

## Implantar at. js 2. x {#deploy-atjs-200}

1. Baixe o at. js 2. x usando a interface do usuário do Target.

   ![Caixa de diálogo Detalhes da implementação](/help/c-experiences/assets/imp-200.png)

   >[!NOTE]
   >
   >A instalação do at. js 2. x pela extensão [do Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) ainda não é suportada.

## Funções obsoletas da at.js

Há várias funções que foram substituídas em at. js 2. x.

>[!IMPORTANT]
>
>Se essas funções obsoletas ainda forem usadas no site quando at. js 2. x for implantado, você verá avisos do console. A abordagem recomendada durante a atualização é testar a implantação do at. js 2. x em um ambiente de preparo e garantir a passagem de cada um dos avisos que foram conectados no console e traduzir as funções obsoletas para novas funções introduzidas em at. js 2. x.

Você pode encontrar as funções obsoletas e a contraparte abaixo. Para obter uma lista completa das funções, consulte [funções da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>O at. js 2. x não oculta automaticamente os elementos `mboxDefault` marcados. Os clientes devem, portanto, acomodar a lógica de pré-ocultação manualmente no site ou por meio de um gerenciador de tags.

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

**equivalente em. js 2. x**

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

**at. js 2. x equivalente**:

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

## Resumo das funções obsoletas, novas e suportadas at.js em 2.0

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

**Rastreamento de conversão**

Os clientes que usam `mboxCreate()` para rastreamento de conversão devem usar `trackEvent()` ou `getOffer()`.

**Entrega de oferta**

Os clientes que não substituírem `mboxCreate()` por `getOffer()` ou `applyOffer()` correm o risco de não ter ofertas entregues.

**Pode ser usado em. js 2. x em algumas páginas durante o at. js 1.*x*ou mbox.js está em outras páginas?**

Sim, o perfil do visitante é preservado nas páginas usando diferentes versões e bibliotecas. O formato de cookie é o mesmo.

**O Adobe Experience Cloud Debugger não é totalmente suportado em at. js 2. x**

[!DNL Adobe Experience Cloud Debugger][!UICONROL Recursos da guia] Resumo e [!UICONTROL Desativar e Desativar logon] são suportados, mas as Solicitações de rede e mboxtrace não são compatíveis com o at. js 2. x.

Isso ocorre porque em at. js 2. x, uma carga JSON é enviada em vez de pares de valor chave. Para inspecionar solicitações [!DNL Target], filtre a guia [!UICONTROL Rede] das Ferramentas do desenvolvedor do seu navegador para &quot;entrega&quot;, &quot;`tt.omtrdc.net`&quot; ou seu código de cliente. Os dados de rastreamento ainda podem ser inspecionados usando o parâmetro da sequência de consulta e o token de autorização. Para obter mais informações, consulte [mboxTrace](/help/c-activities/c-troubleshooting-activities/content-trouble.md).

**Nova API usada em at. js 2. x**

O at. js 2. x usa uma nova API, que chamamos a API de entrega. Para depurar se o at.js está chamando o servidor [!DNL Target] de borda corretamente, você pode filtrar a guia Rede das Ferramentas do desenvolvedor do seu navegador para “entrega”, “`tt.omtrdc.net`”, ou seu código de cliente. Você também notará que [!DNL Target] envia uma carga JSON em vez de pares de valores-chave.

**A mbox global do Target não é mais usada**

No at. js 2. x, você não verá mais «`target-global-mbox`» visivelmente nas chamadas de rede. Em vez disso, substituímos a sintaxe &quot;`target-global-mbox`&quot; por &quot;`execute > pageLoad`&quot; na carga JSON enviada aos [!DNL Target] servidores, como observado a seguir:

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

**O nome da mbox global no at.js não importa mais?**

Os clientes podem especificar um nome de mbox global por meio do [!UICONTROL Target &gt; Configuração &gt; Implementação &gt; Editar configurações da at.js]. Essa configuração é usada pelos servidores de borda [!DNL Target] para traduzir execute &gt; pageLoad para o nome da mbox global que aparece na interface do [!DNL Target]. Isso permite que os clientes continuem a usar APIs do servidor, o compositor baseado em formulário, scripts de perfil e criar públicos-alvo usando o nome global da mbox. Recomendamos que você também verifique se o mesmo nome global da mbox está configurado na página [!UICONTROL Configuração &gt; Preferências], caso ainda tenha páginas que usam o at.js 1.*x* ou mbox.js, conforme mostrado nas ilustrações a seguir.

![Modificar caixa de diálogo da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/modify-atjs.png)

e

![Mbox global personalizada](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/custom-global-mbox.png)

**A configuração de mbox global de criação automática precisa ser ativada para at. js 2. x?**

Na maioria dos casos, sim. Esta configuração instrui o. js 2. x a disparar uma solicitação nos servidores [!DNL Target] de borda ao carregar a página. Como a mbox global é traduzida para executar o &gt; pageLoad e se você quiser acionar uma solicitação no carregamento da página, essa configuração deve estar ativada.

**As atividades existentes da VEC continuarão a funcionar, mesmo que o nome da mbox global alvo não seja especificado de at. js 2. x?**

Sim, porque executar &gt; carga é tratado no [!DNL Target] backend como `target-global-mbox`.

**Se minhas atividades baseadas em formulário forem direcionadas para o`target-global-mbox`, essas atividades continuarão funcionando?**

Sim, porque executar &gt; carga é tratado nos servidores [!DNL Target] de borda como `target-global-mbox`.

**Configurações com suporte e não suportadas em. js 2. x**

| Configuração | Suportado? |
| --- | --- |
| Domínio X | Não |
| Criar automaticamente mbox global | Sim |
| Nome da mbox global | Sim |

**O rastreamento entre domínios*não*é suportado**

O rastreamento entre domínios possibilita visualizar sessões em sites relacionados, mas com domínios diferentes, como uma única sessão. Você poderia criar uma [!DNL Target] atividade que expande `siteA.com` e `siteB.com` e o visitante permaneceria na mesma experiência ao cruzar os domínios. Essa funcionalidade se associa ao comportamento de cookies de terceiros e próprios do Target.

No [!DNL Target], o cookie de terceiros é armazenado em `[CLIENTCODE].tt.omtrdc.net` e o cookie próprio é armazenado em `clientdomain.com`. A primeira solicitação retorna cabeçalhos de resposta HTTP que tentam instalar cookies de terceiros chamados `mboxSession` e `mboxPC`, enquanto uma solicitação de redirecionamento é enviada de volta com um parâmetro extra (`mboxXDomainCheck=true`). Se o navegador aceitar cookies de terceiros, a solicitação de redirecionamento vai inclui-los, e a oferta será retornada. Esse fluxo de trabalho é possível porque usamos o método HTTP GET.

No entanto, no at. js 2. x, o HTTP GET não é mais usado e, em vez disso, usamos HTTP POST. HTTP POST agora é usado via at.js para enviar cargas JSON para servidores [!DNL Target] de borda. Isso significa que a solicitação de redirecionamento para verificar se um navegador suporta cookies de terceiros agora está rompida. Isso ocorre porque as solicitações HTTP GET são transações idempotentes, enquanto HTTP POST é não idempotente e não deve ser repetido arbitrariamente. Portanto, o rastreamento entre domínios no at. js 2. x não é mais suportado.

**Criar automaticamente mbox global é compatível**

Esta configuração instrui o. js 2. x a disparar uma solicitação nos servidores [!DNL Target] de borda na carga da página. Como a mbox global é traduzida para executar &gt; carga, e isso é interpretado pelos servidores [!DNL Target] de borda, os clientes devem ativar esse recurso se quiserem acionar uma solicitação no carregamento da página.

**O nome da mbox global é compatível**

Os clientes podem especificar um nome de mbox global por meio do [!UICONTROL Target &gt; Configuração &gt; Implementação &gt; Editar configurações da at.js]. Essa configuração é usada pelos [!DNL Target] servidores de borda para traduzir executar &gt; carga para o nome da mbox global inserido. Isso permite que os clientes continuem a usar APIs do servidor, o compositor baseado em formulário, scripts de perfil e criar públicos-alvo que direcionem a mbox global.

**Os eventos personalizados da at.js abaixo são aplicáveis a`triggerView()`ou são somente para`applyOffer()`ou`applyOffers()`?**

* `adobe.target.event.CONTENT_RENDERING_FAILED`
* `adobe.target.event.CONTENT_RENDERING_SUCCEEDED`
* `adobe.target.event.CONTENT_RENDERING_NO_OFFERS`
* `adobe.target.event.CONTENT_RENDERING_REDIRECT`

Sim, os eventos personalizados da at.js `triggerView()` também se aplicam.

**Ele informa quando eu chamo`triggerView()`com`{“page” : “true”}`, enviará uma notificação para o[!DNL Target]backend e aumentará a impressão. Também faz com que os scripts de perfil sejam executados?**

Quando uma chamada de pré-busca é feita no [!DNL Target] backend, os scripts de perfil são executados. Consequentemente, os dados de perfil afetados serão criptografados e enviados para o lado do cliente. Após invocar `triggerView()` com `{"page": "true"}`, uma notificação é enviada juntamente com os dados de perfil criptografados. Isso ocorre quando o [!DNL Target] backend descriptografa os dados do perfil e armazena nos bancos de dados.

**Precisamos adicionar um código que oculta previamente antes da chamada`triggerView()`a fim de gerenciar a cintilação?**

Não, não é necessário adicionar código de pré-ocultação antes de chamar `triggerView()`. O at. js 2. x gerencia a lógica pré-ocultante e piscante antes da exibição ser exibida e aplicada.

## compatibilidade com o at.js

As tabelas a seguir explicam o at.js. Compatibilidade 2.0.0 com tipos de atividades, integrações, recursos e funções da at.js diferentes.

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
>Atividades do Target automáticas são suportadas por meio do at. js 2. x e do VEC quando todas as modificações são aplicadas ao `Page Load Event`. Quando as modificações são adicionadas a exibições específicas, as atividades de Teste A/B, Autoalocação e Segmentação de experiência (XT) são suportadas apenas.

### Integrações {#integrations}

| Tipo | Suportado? |
| --- | --- |
| Analytics for Target (A4T) | Sim |
| Públicos-alvo | Sim |
| Atributos do cliente | Sim |
| Fragmentos de experiência do AEM | Sim |
| Extensão do Adobe Launch | Não no momento |
| Depurador | Sim |
| Auditor | As regras ainda não foram atualizadas para at. js 2. x |
| Gerenciador dinâmico de tags (DTM) | Sim |
| Opt-In | Não. O suporte de aceitação para [o RGPD](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) é suportado na [versão 2.1.0](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)do at. js. |
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
| `?mboxOverride.browserIp` | Não |

## Tokens de resposta {#response-tokens}

at.js 2.*x*, como at. js 1.*x*, usa os tokens de resposta de evento `at-request-succeeded` personalizado. Para exemplos de código usando o evento `at-request-succeeded` personalizado, consulte [Tokens de resposta](/help/administrating-target/response-tokens.md).

## parâmetros do at. js 1. x para o mapeamento de carga at. js 2. x {#payload-mapping}

Esta seção descreve os mapeamentos entre o at. js 1.*x* e at. js 2. x.

Antes de passar para o mapeamento de parâmetros, os pontos finais que essas versões de biblioteca usavam foram alterados:

* at.js 1.*x* - `http://<client code>.tt.omtrdc.net/m2/<client code>/mbox/json`
* at. js 2. x - `http://<client code>.tt.omtrdc.net/rest/v1/delivery`

Outra diferença significativa é que:

* at.js 1.*x* - O código do cliente faz parte do caminho
* O código at. js 2. x - do cliente é enviado como um parâmetro de sequência de consulta, como:
   `http://<client code>.tt.omtrdc.net/rest/v1/delivery?client=democlient`

As seções a seguir listam cada at. js 1.*parâmetro x* , sua descrição e a carga JSON 2.0.0 correspondente (se aplicável):

### at_ property

(at.js 1.** parâmetro x)

Usado para [Permissões do usuário do Enterprise](/help/administrating-target/c-user-management/property-channel/property-channel.md).

```
{
  ....
  "property": {
    "token": "1213213123122313121"
  }
  ....
}
```

### browserHeight

(at.js 1.** parâmetro x)

A altura da janela do navegador do visitante.

Carga JSON do at. js 2. x:

```
{
  "context": {
    "window": {
       "height": 200
    }
  }
}
```

### browserWidth

(at.js 1.** parâmetro x)

A largura da janela do navegador do visitante.

Carga JSON do at. js 2. x:

```
{
  "context": {
    "window": {
       "width": 200
    }
  }
}
```

### Browsertimeoffset

(at.js 1.** parâmetro x)

O deslocamento do fuso horário.

Carga JSON do at. js 2. x:

```
{
  "context": {
    "timeOffsetInMinutes": -480
  }
}
```

### Screenheight

(at.js 1.** parâmetro x)

A altura da tela do visitante.

Carga JSON do at. js 2. x:

```
{
  "context": {
    "screen": {
       "height": 200
    }
  }
}
```

### Screenwidth

(at.js 1.** parâmetro x)

A largura da tela do visitante.

Carga JSON do at. js 2. x:

```
{
  "context": {
    "screen": {
       "width": 200
    }
  }
}
```

### colorDepth

(at.js 1.** parâmetro x)

A intensidade de cor da tela do visitante.

Carga JSON do at. js 2. x:

```
{
  "context": {
    "screen": {
       "colorDepth": 24
    }
  }
}
```

### mboxHost

(at.js 1.** parâmetro x)

O domínio da página em que a biblioteca do Target é executada.

Carga JSON do at. js 2. x:

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

(at.js 1.** parâmetro x)

Os recursos de renderização do Web GL do navegador. Isso é usado pelo nosso mecanismo de detecção de dispositivo para determinar se o dispositivo do visitante é um desktop, iphone, dispositivo Android etc.

Carga JSON do at. js 2. x:

```
{
  "context": {
    "browser": {
       "webGLRenderer": "AMD Radeon Pro 560X OpenGL Engine"
    }
  }
}
```

### Mboxurl

(at.js 1.** parâmetro x)

O URL da página.

Carga JSON do at. js 2. x:

```
{
  "context": {
    "address": {
       "url": "http://test.com"
    }
  }
}
```

### Mboxreferrer

(at.js 1.** parâmetro x)

O referenciador de página.

Carga JSON do at. js 2. x:

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

(at.js 1.** parâmetro x)

A API de entrega não tem mais um conceito global de mbox. Na carga JSON, você deve usar `execute > pageLoad`.

Carga JSON do at. js 2. x:

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

(at.js 1.** parâmetro x)

Para usar um nome de mbox, passe-o `execute > mboxes`para. Uma mbox requer um índice e um nome.

Carga JSON do at. js 2. x:

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

### Mboxid

(at.js 1.** parâmetro x)

Não está mais em uso.

### Mboxcount

(at.js 1.** parâmetro x)

Não está mais em uso.

### Mboxrid

(at.js 1.** parâmetro x)

ID de solicitação usada por sistemas descendentes para ajudar na depuração.

Carga JSON do at. js 2. x:

```
{
  "requestId": "2412234442342"
  ....
}
```

### Mboxtime

(at.js 1.** parâmetro x)

Não está mais em uso.

### mboxSession

(at.js 1.** parâmetro x)

A ID da sessão é enviada como parâmetro de sequência de consulta (`sessionId`) para o ponto de extremidade da API de entrega.

### mboxPC

(at.js 1.** parâmetro x)

A ID TNT é passada `id > tntId`.

Carga JSON do at. js 2. x:

```
{
  "id": {
    "tntId": "ca5ddd7e33504c58b70d45d0368bcc70.21_3"
  }
  ....
}
```

### mboxMCGVID

(at.js 1.** parâmetro x)

A ID de visitante da Marketing Cloud é passada `id > marketingCloudVisitorId`.

Carga JSON do at. js 2. x:

```
{
  "id": {
    "marketingCloudVisitorId": "797110122341429343505"
  }
  ....
}
```

### vst. aaaa. id e vst. aaaa. authstate

(at.js 1.*x* parâmetros)

As IDs do cliente `id > customerIds`devem ser enviadas.

Carga JSON do at. js 2. x:

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

(at.js 1.** parâmetro x)

ID de terceiros do cliente usada para vincular IDs de Target diferentes.

Carga JSON do at. js 2. x:

```
{
  "id": {
    "thirdPartyId": "1232312323123"
  }
  ....
}
```

### Mboxmcsdid

(at.js 1.** parâmetro x)

SDID, também conhecido como ID de dados complementares. Deve ser passado `experienceCloud > analytics > supplementalDataId`.

Carga JSON do at. js 2. x:

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

### vst. trk

(at.js 1.** parâmetro x)

Servidor de rastreamento do Analytics. Deve ser passado `experienceCloud > analytics > trackingServer`.

Carga JSON do at. js 2. x:

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

### vst. trks

(at.js 1.** parâmetro x)

Servidor de rastreamento do Analytics seguro. Deve ser passado `experienceCloud > analytics > trackingServerSecure`.

Carga JSON do at. js 2. x:

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

(at.js 1.** parâmetro x)

Dica de localização do Audience Manager. Deve ser passado `experienceCloud > audienceManager > locationHint`.

Carga JSON do at. js 2. x:

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

(at.js 1.** parâmetro x)

blob do Audience Manager. Deve ser passado `experienceCloud > audienceManager > blob`.

Carga JSON do at. js 2. x:

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

### Mboxversion

(at.js 1.** parâmetro x)

A versão é enviada como um parâmetro de sequência de consulta por meio do parâmetro da versão.

## Vídeo de treinamento: diagrama de arquitetura at. js 2. x

O at. js 2. x melhora o suporte do Adobe Target para spas e integra-se com outras soluções da Experience Cloud. Este vídeo explica como tudo se une.

>[!VIDEO](https://video.tv.adobe.com/v/26250?captions=por_br)

Consulte [Entendendo como at. js 2. x funciona](https://helpx.adobe.com/target/kt/using/atjs20-diagram-technical-video-understand.html) para obter mais informações.