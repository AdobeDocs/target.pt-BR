---
keywords: mbox.js changes;mbox.js versions
description: Esta página mostra as alterações em cada versão da mbox.js.
title: Detalhes da versão da mbox.js
feature: null
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '2320'
ht-degree: 98%

---


# Detalhes da versão da mbox.js{#mbox-js-version-details}

Esta página mostra as alterações em cada versão da mbox.js.

>[!NOTE]
>
>Recomendamos que todos os usuários mbox.js atualizem para a versão 57 ou posterior. Alguns usuários tiveram problemas de limite de tempo quando `target.js` não pôde ser carregada. A versão 57 corrigiu esse problema. No entanto, se você estiver usando o serviço[!DNL Experience Cloud Visitor ID], a versão 58 ou posterior será necessária.

A maneira como o Target responde a chamadas de sua página dependerá da versão da biblioteca do Target em uso, se a implementação da ID de visitante estiver presente e se a ID de visitante existir. Para obter informações, consulte  [Respostas de chamada do Target pela Versão da biblioteca](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/call-responses-library-version.md#concept_A95A4758A1E7405D947E9B4BCB5D62F0).

>[!NOTE]
>
>A biblioteca mbox.js não está mais sendo desenvolvida. Todos os clientes devem migrar da mbox.js para a at.js. Para obter mais informações, consulte [Migrar para at.js do mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

## mbox.js versão 63 {#section_ED8EFCF653A845ED8927F759578C4A33}

**Versão do Target:** 17.7.1

A [!DNL mbox.js] versão 63 já está disponível. Para obter mais informações, consulte [Baixar a mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/target-download-config-mbox.md).

Os seguintes aprimoramentos e correções estão incluídos na [!DNL mbox.js] versão 63:

* Corrige um problema na geração da SDID ao usar `mboxDefine()` e `mboxUpdate()`. Isso afeta apenas os clientes que possuem a API do visitante na página.

## mbox.js versão 62 {#section_723A9119FE204183847D3B0929A99B41}

* Correção de problemas de cintilação nas atividades de redirecionamento quando visualizadas no navegador Google Chrome.
* Adição da configuração `secureOnly`, que indica se a mbox.js deve usar somente HTTPS ou pode alternar entre HTTP e HTTPS com base no protocolo da página. Esta é uma configuração avançada cujo padrão é Falso.

## mbox.js versão 61 {#section_F3B59C5578B64883AE013B9342151193}

**Versão do Target:** 16.7.2

**Data de lançamento:** 28 de julho de 2016

A mbox.js versão 61 contém os seguintes aprimoramentos:

* O algoritmo de geração de ID da mboxSession na API de datas JavaScript agora gera uma cadeia de caracteres aleatória em vez de usar um carimbo de data e hora mais uma cadeia de caracteres aleatória.
* Os detalhes a seguir se aplicam somente se você tiver a API de visitante na página:

   * A versão [!DNL mbox.js] 61 não substitui a propriedade API `loadTimeout` do visitante. Os clientes podem usar `visitorApiTimeout` + `visitorApiPageDisplayTimeout` para controlar a integração da API do visitante.
   * Adição de uma configuração `optoutEnabled` para oferecer suporte à futura funcionalidade de não participação da Adobe Experience Cloud. O valor padrão é false. Se essa propriedade estiver ativada, todas as solicitações são executadas de forma assíncrona em relação ao endpoint[!DNL /ajax], da mesma forma como na versão 60.
   * A ocultação do corpo está desativada por padrão. O Target usa a ocultação do corpo somente quando a criação automática de mbox global está ativada e a ocultação do corpo está ativada.
   * Se não houver cookies de ID de visitante da Experience Cloud, todas as solicitações serão executadas de forma assíncrona em relação ao [!DNL /ajax] no carregamento da primeira página. No segundo carregamento da página, o Target usa o fluxo normal porque os valores de ID de visitante já estão presentes.
   * Se você usar o Adobe Analytics como a fonte de relatórios da sua atividade, não será necessário especificar um servidor de rastreamento durante a criação da atividade usando a mbox.js versão 61 (ou posterior) ou a at.js versão 0.9.1 (ou posterior). A biblioteca mbox.js ou at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].

## mbox.js versão 60 {#section_3BDAB885FA13444A8D35940A4BFF5825}

**Versão do Target:** 16.4.1

**Data de lançamento:** 21 de abril de 2016

Por padrão, o conteúdo da página não está oculto. A versão 60 oculta o conteúdo da página somente quando a opção de &quot;criação automática de mbox global&quot; está ativada. Ela usa a propriedade CSS `opacity:0` para ocultação de página em vez de `display:none`. Isso garante a entrega adequada para sites responsivos e se alinha à [!DNL at.js].

É possível ativar o ocultamento do corpo usando duas configurações:

* `bodyHidingEnabled` O valor padrão é false, que significa que o HTML BODY não está oculto.

* bodyHiddenStyle

   O valor padrão é `body{opacity:0}`. Esse valor pode ser alterado para algo diferente, como `body{display:none}`.

Essas configurações podem ser substituídas, incluindo algo como:

```
<script> 
window.targetGlobalSettings = { 
 bodyHidingEnabled: true, 
 bodyHiddenStyle: "body{opacity:0}", 
 visitorApiPageDisplayTimeout: 2000 
}; 
</script>
```

A técnica de ocultação de página usa tags de estilo para adicionar e remover estilos. Isso garante que os estilos do site permaneçam inalterados após a execução do código de ocultação da página.

**Usuários de DTM:** observe que isso impedirá que você use a opção de importação Automática, pois não há como salvar a configuração acima na interface do Target. Você terá que usar as instruções acima e depois colar o conteúdo na caixa de código da opção de hospedagem personalizada.

Além disso, na versão 60, se o arquivo [!DNL visitorAPI.js] estiver presente para o serviço de ID de visitante da Experience Cloud, todas as mboxes serão solicitadas por meio de um terminal AJAX. Isso é necessário porque os métodos de API do visitante são assíncronos. Um benefício dessa abordagem é que a hora de início da renderização é consideravelmente reduzida, porque as solicitações de mbox não bloqueiam a renderização. Contudo, isso significa também que todo o conteúdo de ofertas do [!DNL Target] é executado de forma assíncrona; por isso, todo o código de ofertas deve ser escrito do modo apropriado. As ofertas que contêm `document.write` e outros códigos que partem do pressuposto de que a execução ocorrerá no carregamento da página inicial não serão executadas conforme esperado.

* Chamadas assíncronas V60

   Ao usar a v60 com o serviço de identificação de visitante, todas as chamadas de mbox serão feitas de forma assíncrona. Esta é uma alteração na forma como as mboxes sempre funcionaram, portanto, tenha cuidado ao atualizar para esta versão. Revise a seção [Considerações assíncronas](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-limitations.md#section_B586360A3DD34E2995AE25A18E3FB953) da documentação da [!DNL at.js] (a [!DNL at.js] também usa chamadas assíncronas) para compreender alguns riscos.
* Novos cenários de visitantes podem sofrer cintilação

   Ao usar a v58 até v60 com o serviço de identificação de visitante, as chamadas de mbox aguardarão a definição da identificação do visitante antes de acionar (ou até atingir um tempo limite). Isso acontece no primeiro carregamento da página por um novo visitante.

## mbox.js versão 59 {#section_FF0E70C4C17E402D8374DE428C5D996E}

**Versão do Target:** 16.2.1

**Data de lançamento:** 17 de fevereiro de 2016

O mbox.js versão 59 contém os seguintes aprimoramentos:

* A desativação da mbox foi reduzida para 30 minutos
* Um problema relacionado à ocultação/exibição de páginas foi corrigido

   Em vez de usar `display:none` para ocultar a página como na versão 58, `opacity:0` é usado. Isso soluciona problemas em sites com design responsivo gerados com o método anterior de ocultação da página.

## mbox.js versão 58 {#section_5070B0D1C87F4937BB97727923DD36C7}

**Versão do Target:** 15.7.1

**Data de lançamento:** 30 de julho de 2015

Essa versão da mbox.js é necessária se você usa o Target como origem de relatórios do Target e é altamente recomendada para perfis e públicos.

A versão 58 da mbox.js garante que o serviço de ID do visitante da Experience Cloud retorne um ID de visitante antes da realização de chamadas do Target. Isso garante que os dados do público-alvo compartilhados por meio do serviço central de perfis e públicos sejam disponibilizados para a primeira chamada do Target na sessão do visitante. Para evitar a cintilação do conteúdo padrão antes que o conteúdo do teste retorne, o Target oculta o `<BODY>` valor até que o serviço de ID de visitante retorne. `display:none` é usado para ocultar a página.

Essa atualização também corrige um problema ao usar o Analytics como origem de relatórios para o Target que fazia com que um número exagerado de visitantes fosse informado no Analytics no caso de visitas que só incluíam uma página.

A mbox.js define valores de tempo limite para o caso de não haver retorno do serviço de ID de visitante. O tempo limite padrão para o serviço de ID do visitante é de 500 ms (0,5 segundo). Um tempo limite adicional define o limite máximo por quanto tempo a tag `<BODY>` ficará oculta. O padrão é 500 ms (0,5 segundo). O tempo limite pode ser alterado com a inserção do código a seguir antes da referência a mbox.js em cada página:

```
<script> 
window.targetGlobalSettings = { 
 visitorApiTimeout: 500, 
 visitorApiPageDisplayTimeout: 500 
}; 
</script> 
```

A mbox.js versão 58 e posterior executa conteúdo não-JavaScript para a mbox global imediatamente após a tag HTML `BODY` estar presente. O conteúdo JavaScript nas tags `<script>` da mbox global é executado depois que o evento `DOMContentLoaded` é acionado. Esta ordem de entrega de conteúdo garante que o conteúdo JavaScript da mbox global seja entregue e renderizado corretamente.

## mbox.js versão 57 {#section_6BA1CDBF75B14A94B59E8624ACF583D4}

**Versão do Target:** 15.4.1

**Data de lançamento:** 21 de abril de 2015

As seguintes alterações foram feitas nesta versão:

* A resposta de mbox global criada automaticamente para o Target Standard não usa mais document. write() ou cria um `<div>` elemento.

   This removes the requirement for the mbox.js file to be the last item in the `<head>` of the page. Recomenda-se um QA apurado ao se atualizar para esta nova versão.

   Essa alteração pode levar a mudanças no comportamento ao se entregar alguns tipos de ofertas. Veja algumas condições específicas que deverão ser levadas em consideração:

   * O conteúdo HTML retornado como parte de uma &quot;oferta de plug-in&quot; não é renderizada corretamente, mas o JavaScript nas ofertas é executado conforme esperado.
   * As ofertas JavaScript que retornam à mbox global podem ter o código JavaScript incorporado na tag `<script>` ou referenciado por um atributo `src`.

      Para isso, adicione o atributo `async` à chamada do script da seguinte maneira:

      `<script src='external-url' async='true'></script>`

      Observe que o atributo `async` tem suporte limitado no Internet Explorer (veja os detalhes aqui: [https://developer.mozilla.org/pt/docs/Web/HTML/Element/script#Browser_compatibility](https://developer.mozilla.org/en/docs/Web/HTML/Element/script#Browser_compatibility)); por isso, exclua os visitantes que usam versões mais antigas do IE dos testes que incluem esses scripts de terceiros.

* Houve correção dos problemas relatados na versão 56 devido a alterações na seção de JavaScript extra da mbox.js. Todos os códigos na seção de JavaScript extra já estão disponíveis novamente no escopo global.

A funcionalidade a seguir não tem suporte na mbox.js versão 57:

* Uma mbox global com criação automática gerada no Target Standard não funciona com tipos de ofertas hospedadas do Target Classic. Os tipos de ofertas hospedadas incluem &quot;oferta em seu site&quot; e &quot;oferta fora do Test&amp;Target&quot;.

   Isso significa que, no Target Classic, você não deve selecionar a mbox global criada automaticamente do Target Standard quando uma dessas ofertas é obrigatória.
* Somente plug-ins JavaScript contam com suporte.

   Se uma oferta de plug-in combinar código JavaScript e HTML, o código JavaScript será executado, mas o conteúdo HTML não será mostrado.

A mbox.js versão 57 também inclui correções importantes:

* Correção de um problema que fazia com que o plug-in do SiteCatalyst não funcionasse na mbox.js v56.
* Correção de um problema que gerava erros no JavaScript extra devido a alterações no escopo.
* Reversão de alterações no construtor de mboxFactory.

## mbox.js versão 56 {#section_C4F4A53584B741FF9FD907D81CB7E164}

**Versão do Target:** 15.1.2

**Data de lançamento:** 17 de fevereiro de 2015

>[!NOTE]
>
>Alguns usuários tiveram problemas de limite de tempo quando `target.js` não pôde ser carregada. A versão 57 corrigiu esse problema. No entanto, se você estiver usando o serviço[!DNL Experience Cloud Visitor ID], a versão 58 ou posterior será necessária.

As seguintes alterações foram feitas nesta versão:

* Alterações do Recommendations Premium para suportar o envio parâmetros para a mbox global
* Inclui 5 segundos de espera para a chamada de carregamento do target.js. Nos raros casos em que o arquivo não é carregado, a página será renderizada e nenhuma atividade do Target Standard será exibida.
* O &quot;JavaScript extra&quot; foi movido para ser executado antes da mbox global

   Todas as definições no v56+ têm nomes espaçados. Se houver funções declaradas em &quot;extra JavaScript&quot;, elas deverão ter o prefixo `window`.

   Por exemplo:

   `function foo {`

   `}`

   Torna-se:

   `window.foo = function() {`

   `}`

   As variáveis que devem estar acessíveis globalmente também devem receber o prefixo `window`.

* Adição de um cookie chamado &quot;em-disabled&quot;, que o mbox.js fornece ao usuário se o carregamento de target.js falha durante a entrega. Este cookie evita que as ofertas criadas com o Visual Experience Composer sejam renderizadas no site. Os usuários com esse cookie não verão o conteúdo de teste nem serão contados nos relatórios de atividades. O restante do conteúdo de ofertas (de campanhas no Target Classic, por exemplo) continuará a ser carregado. O cookie tem duração de 30 minutos a partir do momento da falha no carregamento.

## mbox versão 55

**Versão do Target:** 15.1

**Data de lançamento:** 19 de janeiro de 2015

Modifica a versão 53 com correções do IE.

## mbox versão 54

**Versão do Target:** 14.9.2

**Data de lançamento:** 30 de setembro de 2014

Altera a implementação da mbox global para AJAX de document.write. Isso remove o requisito do arquivo mbox.js ser o último item da página `<head>`. Esta versão está disponível somente via API. Os clientes podem baixá-la e usar esse arquivo mbox.js. Alguns sites apresentam cintilação de conteúdo com essa implementação, portanto, valide a integração no site.

## mbox versão 53

**Versão do Target:** 14.9.1

**Data de lançamento:** 14 de setembro de 2014

Um problema foi corrigido: os parâmetros de página do Target não são acionados corretamente no Internet Explorer.

## mbox versão 52

**Versão do Target:** 14.8

**Data de lançamento:** 14 de agosto de 2014

Agora, a função mboxParameter funciona no Target Standard e Premium.

Um problema que impedia o Analytics de funcionar no IE 9 &amp; 11 foi corrigido. Essa alteração afeta apenas os usuários do Analytics.

Agora você pode [passar parâmetros](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md) como uma matriz, como um objeto JSON ou como uma lista delimitada por vírgulas (que tinham suporte antes) para target-global-mbox usando a função targetPageParams().

M2PcId foi renomeado e tudo relacionado à VisitorId.

Permita a limpeza de defaultDiv de uma mbox registrada.

## mbox versão 51

**Versão do Target:** 14.6

**Data de lançamento:** 25 de junho de 2014

Foi corrigido um defeito que fazia com que um cookie incorreto fosse configurado em sites com dois caracteres em seus domínios de nível superior.

Foi corrigido um erro secundário em mbox.js que fazia com que valores de hashtag fossem retornados.

## mbox versão 50

A sincronização entre o Target Standard e o Target Classic foi aprimorada.

## mbox versão 49

O suporte do Explorer 10 para mboxes aninhadas foi aprimorado.

## mbox versão 48

Adição de suporte para o Adobe Analytics, como fonte de relatórios para o Target.

## mbox versão 47

mbox.js agora oferece suporte para o uso de um nome da mbox global personalizada para o Target Standard.

## mbox versão 46

Adição de suporte completo para o serviço de ID de visitante da Experience Cloud para a implementação de linha única de código do Target Standard. Isso permite a integração do Adobe Analytics no lado do servidor e o perfil compartilhado da Experience Cloud.

Corrigido um problema com a entrega de conteúdo no modo de documento do IE10.

## mbox versão 45

Adição de suporte completo para o serviço de ID de visitante da Experience Cloud. Isso permite a integração do Adobe Analytics no lado do servidor e o perfil compartilhado da Experience Cloud.

## mbox versão 44

Adição de novo parâmetro no URL por mboxVizTarget:

mboxDOMLoaded

## mbox versão 43

Adição de suporte ao Target Standard.

## mbox versão 42

Adição de suporte inicial ao serviço de ID de visitante compartilhado da Experience Cloud.

## mbox versão 41

* Mesmo com a configuração somente x, desativar o cookie próprio para melhorar o tempo de carregamento e evitar atualizações contínuas da página

   Um cookie de tempo limite será definido se a chamada para o Target não for retornada a tempo. Esse método é mais rápido do que usar apenas o cookie de terceiros. Somente com o cookie de terceiros, a página é atualizada o tempo todo durante a espera por uma boa resposta dos servidores do Target.

* Correção da limitação de tráfego para que ocorra somente quando a mbox.js estiver ativada

   Esse problema ocorrerá se um cliente tiver uma limitação de tráfego em seu arquivo mbox.js, fazendo com que a configuração de limite não funcione. Isso resultou na atualização da página durante a espera por uma boa resposta dos servidores do Target.

* Correção do plug-in do SiteCatalyst para sempre usar o Ajax fetcher

   Antes dessa alteração, havia algumas situações para os usuários do plug-in Test&amp;Target para SiteCatalyst em que, dependendo de quando o plug-in fosse carregado, um document.write que limparia a página poderia ser acionado.

## mbox versão 38

Adição de suporte ao SiteCatalyst baseado em páginas para integração do Test&amp;Target (deve ser ativado)

## mbox versão 37

Codificação de chaves de URL

## mbox versão 36

Alteração da mbox para usar tt.omtrdc.net

## mbox versão 35

* Agora, a depuração da mbox é sempre remota
* Adição do parâmetro mboxTime. Esse parâmetro é o tempo visto pelo usuário, em ms desde a época, GMT. Isso só é calculado uma vez.

## mbox versão 34

* Sempre tente obter o padrão mais recente div em vez de consultar uma versão em cache.

   Isso corrige o problema em que um conteúdo padrão em cache div não estava no DOM devido a um mboxUpdate, que fornecia o conteúdo para o padrão div.

* mbox.getDefaultDiv tem um novo parâmetro booleano opcional. Se true, retorna o padrão atual div. Se false, retorna o último padrão em cache div.
* Atualização do mbox.loaded para oferecer suporte ao carregamento do Ajax
* Agora, o parâmetro mboxURL é codificado usando encodeURIComponent em vez de escape
* Teste se encodeURIComponent é suportado pelo navegador e exiba o conteúdo padrão caso não seja. Também houve a remoção das seguintes opções de configuração do mbox.js:
   * encode\_mbox\_parameters
   * mbox\_signal\_support
