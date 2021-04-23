---
keywords: spa vec;react;angular;react.js;spa visual experience composer;opções de spa do experience composer;single page apps;single-page-app;spa;opções do mobile experience;exibição do target
description: Saiba como usar o VEC SPA no Adobe [!DNL Target] para criar testes e personalizar conteúdo no SPA de maneira autônoma, sem dependências contínuas de desenvolvimento.
title: Como uso o Visual Experience Composer (VEC de SPA de aplicativo de página única)?
feature: Visual Experience Composer (VEC)
exl-id: fd3dcfaa-e5c6-45a1-8229-9c206562e5b0
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '3700'
ht-degree: 91%

---

# Aplicativo de página única (SPA) no Visual Experience Composer

Em [!DNL Adobe Target], o [!UICONTROL Visual Experience Composer] (VEC) fornece aos profissionais de marketing um recurso próprio para criar atividades e personalizar experiências que podem ser fornecidas dinamicamente em aplicativos de vários páginas tradicionais por meio da mbox global do Adobe Target. No entanto, isso depende da recuperação de ofertas em chamadas de carregamento de página ou servidor subsequentes, o que introduz a latência, como mostrado no diagrama abaixo. Essa abordagem não funciona bem com SPAs (aplicativos de página única), pois elimina a experiência do usuário e o desempenho do aplicativo.

![Ciclo de vida tradicional e ciclo de vida de SPA](/help/c-experiences/assets/trad-vs-spa.png)

Com a versão mais recente, agora apresentamos o VEC para SPAs. O VEC para SPAs permite que os comerciantes criem testes e personalizem conteúdo em SPAs de forma autônoma, sem dependências de desenvolvimento contínuas. O VEC pode ser usado para criar atividades de [teste A/B](/help/c-activities/t-test-ab/test-ab.md) e [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md) (XT) em estruturas populares, como o React e o Angular.

## Adobe [!DNL Target] Exibições e aplicativos de página única

O VEC do Adobe Target para SPAs utiliza um novo conceito chamado Exibições: um grupo lógico de elementos visuais que, juntos, constituem uma experiência de SPA. Por isso, uma SPA pode ser considerada como uma transição entre exibições, em vez das URLs, com base nas interações do usuário. Uma Exibição geralmente pode representar um site inteiro ou elementos visuais agrupados dentro de um site.

Para explicar mais sobre o que são Exibições, vamos navegar neste site de comércio eletrônico online hipotético implementado no React e explorar alguns exemplos de Exibições. Clique nos links abaixo para abrir este site em uma nova aba do navegador.

**Link:  [Site inicial](https://target.enablementadobe.com/react/demo/#/)**

![site inicial](/help/c-experiences/assets/home.png)

Quando navegamos para o site inicial, é possível visualizar imediatamente uma imagem principal que promove uma venda de Páscoa e os produtos mais recentes à venda no site. Nesse caso, uma Exibição pode ser definida como todo o site inicial. Isso é útil para observar como expandiremos mais isso na seção Implementação de exibições do Adobe Target abaixo.

**Link:  [Site do produto](https://target.enablementadobe.com/react/demo/#/products)**

![site do produto](/help/c-experiences/assets/product-site.png)

Conforme o interesse nos produtos aumenta, decidimos clicar no link Produtos. Assim como o site inicial, a totalidade do site de produtos pode ser definida como uma Exibição. É possível nomear os &quot;produtos&quot; dessa exibição como o nome do caminho em `https://target.enablementadobe.com/react/demo/#/products`.

![site do produto 2](/help/c-experiences/assets/product-site-2.png)

No início desta seção, definimos Exibições como o site inteiro ou até mesmo um grupo de elementos visuais no site. Como mostrado acima, os quatro produtos mostrados no site também podem ser agrupados e considerados como uma Exibição. Se queremos nomear esta Exibição, podemos chamá-la de &quot;produtos&quot;.

![site do produto 3](/help/c-experiences/assets/product-site-3.png)

Decidimos clicar no botão Carregar mais para explorar mais produtos no site. Nesse caso, o URL do site não é alterado. Entretanto, uma Exibição aqui pode representar apenas a segunda linha de produtos mostrados acima. O nome da exibição pode ser chamado de &quot;PRODUCTS-PAGE-2&quot;.

**Link:  [Check-out](https://target.enablementadobe.com/react/demo/#/checkout)**

![página de checkout](/help/c-experiences/assets/checkout.png)

Como curtimos alguns produtos mostrados no site, decidimos comprar alguns deles. Agora, no site de checkout, recebemos algumas opções para escolher a entrega normal ou a expressa. Como uma exibição pode ser qualquer grupo de elementos visuais em um site, podemos nomear essa opção como &quot;Exibir preferências de entrega&quot;.

Além disso, o conceito de Exibições pode ser estendido muito além disso. Se os profissionais de marketing quiserem personalizar o conteúdo no site, dependendo da preferência de entrega selecionada, é possível criar uma exibição para cada preferência de entrega. Nesse caso, quando selecionamos Entrega normal, a Exibição pode se chamar &quot;Entrega normal&quot;. Se a opção Entrega expressa estiver selecionada, a Exibição pode ser chamada de &quot;Entrega expressa&quot;.

Agora, os profissionais de marketing podem executar um teste A/B para ver se a alteração da cor de azul para vermelho quando a opção Entrega expressa está selecionada pode aumentar as conversões em vez de manter a cor do botão azul para ambas as opções de entrega.

## Implementação de exibições Adobe [!DNL Target]

Agora que cobrimos o que são Exibições do Adobe Target, podemos aproveitar este conceito no Target para que os profissionais de marketing executem testes de A/B e XT em SPAs por meio do VEC. Isso exigirá uma configuração de desenvolvedor única. Vamos analisar as etapas de configuração.

1. Instalar a at.js 2.x.

   Primeiro, é necessário instalar a at.js 2.x. Essa versão da at.js foi desenvolvida para SPAs. As versões anteriores do at.js e mbox.js não são compatíveis com as Exibições do Adobe Target e o VEC for SPA.

   ![Caixa de diálogo Detalhes da implementação](/help/c-experiences/assets/imp-200.png)

   Baixe a at.js 2.x pela interface do usuário do Adobe Target localizada em [!UICONTROL Administration > Implementation]. A at.js 2.x também pode ser implantada por meio do [Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md). No entanto, as extensões do Adobe Target não estão atualizadas e não são compatíveis.

1. Implemente a função mais recente da at.js 2.x: [triggerView()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md) em seus sites.

   Após definir as Exibições de SPA, onde deseja executar um teste A/B ou XT, implemente a função da at.js 2.x `triggerView()` com as Exibições passadas como parâmetro. Isso permite que os profissionais de marketing usem o VEC para projetar e executar os testes A/B e XT para essas Exibições definidas. Se a função `triggerView()` não estiver definida para essas Exibições, o VEC não detectará as Exibições e, portanto, os profissionais de marketing não poderão usar o VEC para projetar e executar testes A/B.

   **`adobe.target.triggerView(viewName, options)`**

   | Parâmetro | Tipo | Obrigatório? | Validação | Descrição |
   | --- | --- | --- | --- | --- |
   | viewName | String | Sim | 1. Sem espaços à direita.<br>2. Não pode estar em branco.<br>3. O nome da exibição deve ser exclusivo para todas as páginas.<br>4. **Aviso**: O nome da Exibição não deve iniciar ou terminar com &#39;`/`&#39;. Isso ocorre porque o cliente normalmente extrai o nome da Exibição do caminho do URL. Para nós, &quot;home&quot; e &quot;`/home`&quot; são diferentes.<br>5. **Aviso**: A mesma exibição não deve ser acionada consecutivamente várias vezes com a opção `{page: true}`. | Transmita qualquer nome como um tipo de sequência de caracteres que você deseja representar sua exibição. Esse nome Exibição é mostrado no painel [!UICONTROL Modificações] do VEC para que os profissionais de marketing criem ações e executem suas atividades A/B e XT. |
   | opções | Objeto | Não |  |  |
   | opções > página | Booleano | Não |  | **TRUE**: O valor padrão da página é true. Quando `page=true`, as notificações serão enviadas aos servidores Edge para aumentar a contagem de impressões.<br>**FALSE**: quando `page=false`, as notificações não serão enviadas para aumentar a contagem de impressões. Isso deve ser usado quando você deseja apenas renderizar novamente um componente em uma página com uma oferta. |

   Agora vamos analisar alguns exemplos de casos de uso de como invocar a função `triggerView()` no React para nosso SPA hipotético de comércio eletrônico:

   **Link:  [Site inicial](https://target.enablementadobe.com/react/demo/#/)**

   ![home-react-1](/help/c-experiences/assets/react1.png)

   Como profissionais de marketing, se queremos executar testes A/B em todo o site inicial, talvez seja ideal nomear a exibição &quot;inicial&quot; que pode ser extraída do URL:

   ```javascript
   function targetView() {
     var viewName = window.location.hash; // or use window.location.pathName if router works on path and not hash
   
     viewName = viewName || 'home'; // view name cannot be empty
   
     // Sanitize viewName to get rid of any trailing symbols derived from URL
     if (viewName.startsWith('#') || viewName.startsWith('/')) {
       viewName = viewName.substr(1);
     }
   
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   // react router v4
   const history = syncHistoryWithStore(createBrowserHistory(), store);
   history.listen(targetView);
   
   // react router v3
   <Router history={hashHistory} onUpdate={targetView} >
   ```

   **Link:  [Site de produtos](https://target.enablementadobe.com/react/demo/#/products)**

   Agora, vejamos um exemplo que é um pouco mais complicado. Considere que desejamos personalizar a segunda linha dos produtos alterando a cor do rótulo de preço para vermelho depois que um usuário clica no botão Carregar mais.

   ![produtos do react](/help/c-experiences/assets/react4.png)

   ```javascript
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   class Products extends Component {
     render() {
       return (
         <button type="button" onClick={this.handleLoadMoreClicked}>Load more</button>
       );
     }
   
     handleLoadMoreClicked() {
       var page = this.state.page + 1; // assuming page number is derived from component’s state
       this.setState({page: page});
       targetView('PRODUCTS-PAGE-' + page);
     }
   }
   ```

   **Link:  [Check-out](https://target.enablementadobe.com/react/demo/#/checkout)**

   ![checkout do react](/help/c-experiences/assets/react6.png)

   Se os profissionais de marketing quiserem personalizar o conteúdo no site, dependendo da preferência de entrega selecionada, é possível criar uma exibição para cada preferência de entrega. Nesse caso, quando selecionamos Entrega normal, a Exibição pode se chamar &quot;Entrega normal&quot;. Se a opção Entrega expressa estiver selecionada, a Exibição pode ser chamada de &quot;Entrega expressa&quot;.

   Agora, os profissionais de marketing podem executar um teste A/B para ver se a alteração da cor de azul para vermelho quando a opção Entrega expressa está selecionada pode aumentar as conversões em vez de manter a cor do botão azul para ambas as opções de entrega.

   ```javascript
   function targetView(viewName) {
     // Validate if the Target Libraries are available on your website
     if (typeof adobe != 'undefined' && adobe.target && typeof adobe.target.triggerView === 'function') {
       adobe.target.triggerView(viewName);
     }
   }
   
   class Checkout extends Component {
     render() {
       return (
         <div onChange={this.onDeliveryPreferenceChanged}>
           <label>
             <input type="radio" id="normal" name="deliveryPreference" value={"Normal Delivery"} defaultChecked={true}/>
             <span> Normal Delivery (7-10 business days)</span>
           </label>
   
           <label>
             <input type="radio" id="express" name="deliveryPreference" value={"Express Delivery"}/>
             <span> Express Delivery* (2-3 business days)</span>
           </label>
         </div>
       );
     }
     onDeliveryPreferenceChanged(evt) {
       var selectedPreferenceValue = evt.target.value;
       targetView(selectedPreferenceValue);
     }
   }
   ```

1. Inicie atividades A/B ou XT por meio do VEC.

   Quando `adobe.target.triggerView()` é implementado em sua SPA com nomes de exibição passados como parâmetros, o VEC poderá detectar essas exibições e permitir que os usuários criem ações e modificações para suas atividades de A/B ou XT.

   >[!NOTE]
   >
   >O VEC for SPAs é realmente o mesmo VEC que você usa em páginas da Web regulares, mas alguns recursos adicionais estão disponíveis ao abrir um aplicativo de página única com a implementação de `triggerView()`.

Há duas melhorias importantes no painel [Modificações](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) e Ações para o VEC que permitem seu funcione adequado com SPAs.

**Painel de modificações**

Como mostrado abaixo, o painel [!UICONTROL Modificações] captura as ações criadas para uma exibição específica. Observe que todas as ações para uma Exibição são agrupadas nessa Exibição.

**Ações**

Clique em uma ação para destacar o elemento no site onde esta ação será aplicada. Cada ação do VEC criada em uma Exibição tem os seguintes ícones, como mostrado abaixo: Informações, Editar, Clonar, Mover e Excluir.

![Modificações](/help/c-experiences/assets/modifications.png)

A seguinte tabela descreve cada ação:

| Página | Descrição |
| --- | --- |
| Informações | Exibe os detalhes da ação. |
| Editar | Permite editar as propriedades da ação diretamente. |
| Clonar | Clona a ação a uma ou mais Exibições que existem no painel [!UICONTROL Modificações] ou a uma ou mais Exibições que você buscou e nas quais navegou no VEC. A ação não precisa existir necessariamente no painel [!UICONTROL Modificações] .<br>**Observação**: após a realização de uma operação de Clonar, é necessário navegar para a Exibição no VEC via [!UICONTROL Procurar] para verificar se a ação clonada foi uma operação válida. Se a ação não puder ser aplicada à Exibição, você verá um erro. |
| Mover | Move a ação para um Evento de carregamento de página ou qualquer outra Exibição que já existe no painel de modificações.<br>[!UICONTROL Evento de carregamento de página] - qualquer ação correspondente ao evento de carregamento de página é aplicada no carregamento inicial da página no aplicativo da Web.<br>**Observação**: após a realização de uma operação de Mover, é necessário navegar para a Exibição no VEC via Procurar para ver se a movimentação foi uma operação válida. Se a ação não puder ser aplicada à Exibição, você verá um erro |
| Excluir | Exclui a ação. |

>[!NOTE]
>
>É possível executar muitas ações antes que a página seja carregada no VEC ou até mesmo se a página não carregar completamente. Ações que não podem ser editadas antes que o site seja carregado estão desabilitadas na interface.

**Exemplo 1**

Vamos consultar o exemplo acima em que criamos uma exibição de Página inicial. Nosso objetivo é criar duas dobras para esta exibição:

1. Altere os botões Adicionar ao carrinho e Curtir para uma cor azul mais clara. Isso deve estar em um &quot;Carregamento de página&quot; porque estamos alterando componentes do cabeçalho.
1. Altere o rótulo &quot;Produtos mais recentes de 2019&quot; para &quot;Produtos de teste simples para 2019&quot; com a cor do texto alterada para violeta.

Para executar essas metas, no VEC, clique em [!UICONTROL Compor] e aplique essas alterações na visualização inicial.

![Exemplo 1](/help/c-experiences/assets/example1.png)

**Exemplo 2**

Vamos analisar o exemplo acima em que criamos uma visualização PRODUCTS-PAGE-2. Nosso objetivo é alterar o rótulo &quot;Preço&quot; para &quot;Preço de venda&quot; com a cor do rótulo em vermelho.

1. Clique em [!UICONTROL Procurar] e, em seguida, clique no link [!UICONTROL Produtos] no cabeçalho.
1. Clique em [!UICONTROL Carregar mais] uma vez para ir até a segunda linha de produtos.
1. Clique em [!UICONTROL Compor].
1. Aplique ações a fim de alterar o rótulo do texto para &quot;Preço de venda&quot; e a cor como vermelho.

![Exemplo 2](/help/c-experiences/assets/example2.png)

**Exemplo 3**

Por fim, como mencionado anteriormente, as Exibições podem ser definidas em nível granular. As exibições podem ser um estado ou até mesmo uma opção de um botão de opção. Anteriormente criamos Exibições como CHECKOUT-EXPRESS e CHECKOUT-NORMAL. Nosso objetivo é alterar a cor do botão para a exibição CHECKOUT-EXPRESS.

1. Clique em [!UICONTROL Procurar].
1. Adicione alguns produtos ao carrinho.
1. Clique no ícone do carrinho no canto superior direito.
1. Clique em Checkout do pedido.
1. Clique no botão de opção Entrega expressa.
1. Clique em [!UICONTROL Compor].
1. Altere o botão &quot;Pagar&quot; para ler o botão &quot;Concluir o pedido&quot; e altere a cor para vermelho.

![Exemplo 3](/help/c-experiences/assets/example3.png)

>[!NOTE]
>
>A exibição CHECKOUT-EXPRESS não será mostrada no painel de modificação até você clicar no botão de opção Entrega expressa. Isso ocorre porque a função `triggerView()` acionada quando o botão de opção Entrega expressa é selecionado e isso ocorre somente quando o VEC sabe que há uma Exibição para mostrar no painel de modificação.

## Análise detalhada de at.js e SPAs

**Como posso recuperar as exibições dos dados de público-alvo mais recentes com ações após o carregamento da página inicial em meu SPA?**

O fluxo de trabalho típico da at.js 2.x é quando seu site é carregado; todas as suas exibições e ações são armazenadas em cache para que as ações subsequentes do usuário no seu site não acionem chamadas do servidor para recuperar ofertas. Se quiser recuperar exibições dependendo dos dados de perfil mais atualizados que possam ter sido atualizados, dependendo das ações subsequentes do usuário, você pode chamar `getOffers()` e `applyOffers()` com os dados de usuário do público-alvo ou de perfil mais recentes passados.

Por exemplo, considere que você tem uma SPA que usa a at.js 2.x. e é uma empresa de telecomunicações que deseja alcançar os seguintes objetivos:

* Para um usuário desconectado ou anônimo, mostre a promoção da empresa mais recente, como mostrar uma oferta principal de &quot;Primeiro mês gratuito&quot; em `http://www.telecom.com/home`.
* Para um usuário conectado, mostre uma oferta promocional de atualização para usuários cujos contratos estão surgindo, como &quot;Você está qualificado para receber um telefone gratuito!&quot; em `http://www.telecom.com/loggedIn/home`.

Agora seus desenvolvedores nomeiam e fazem chamadas para `triggerView()` da seguinte maneira:

* Para `http://www.telecom.com/home` o nome da exibição, é &quot;Página inicial desconectada&quot;
   * `triggerView(“Logged Out Home”)` é chamado.
* Para `http://www.telecom.com/loggedIn/home`, o nome de exibição é &quot;Logon conectado&quot;
   * `triggerView(“Logged In Home”)` é chamado na alteração da rota.

Seus profissionais de marketing executam as seguintes atividades A/B por meio do VEC:

* Compare a atividade com a oferta &quot;Primeiro mês gratuito&quot; para os públicos-alvo com o parâmetro &quot;`loggedIn= false`&quot; que serão exibidos em `http://www.telecom.com/home`, onde o nome da exibição está Desconectado do início.
* Atividade A/B com a oferta &quot;Você está qualificado para receber um telefone gratuito!&quot; de público-alvo com o parâmetro &quot;`loggedIn=true`&quot; a ser exibido em `http://www.telecom.com/loggedIn/home`, onde o nome da exibição é Oferta de exemplo conectada.

Agora, considere este fluxo de usuário:

1. Um usuário anônimo desconectado chega à sua página.
1. Como a at.js 2.x está em uso, você passa o parâmetro &quot;`loggedIn = false`&quot; no carregamento da página para recuperar todas as exibições presentes em atividades ativas, qualificadas quando o público-alvo tiver o parâmetro &quot;`loggedIn = false`&quot;.
1. A at.js 2.x recupera a exibição de Logout da página inicial e a ação para mostrar a oferta &quot;Primeiro mês gratuito&quot;, armazenando-as no cache.
1. Quando `triggerView(“Logged Out Home”)` é invocado, a oferta &quot;Primeiro mês gratuito&quot; é recuperada do cache e a oferta é exibida sem uma chamada de servidor.
1. Agora o usuário clica em &quot;Logon&quot; e fornece suas credenciais.
1. Como seu site é um SPA, você não faz um carregamento de página completo e, em vez disso, direciona seu usuário para `http://www.telecom.com/loggedIn/home`.

Agora, este é o problema. O usuário entra e encontramos `triggerView(“Logged In Home”)`, pois colocamos esse código na alteração da rota. Isso instrui que a at.js 2.x recupere a exibição e as ações do cache, mas a única exibição existente no cache é o Logout da página inicial.

Assim, como podemos recuperar a Exibição conectada e mostrar &quot;Você está qualificado para receber um telefone gratuito!&quot; offer? Como todas as ações subsequentes do site serão de uma perspectiva logada no usuário, como você pode garantir que todas as ações subsequentes resultam em ofertas personalizadas para usuários conectados?

Você pode usar as novas funções `getOffers()` e `applyOffers()` compatíveis com a at.js 2.x:

```javascript
adobe.target.getOffers({
  request: {
  prefetch: {
    "views": [
      {
        "parameters": {
          "loggedIn": true
        },
      }
    ]
  },
});
```

Envie a resposta `getOffers()` de `applyOffers()`. Agora todas as exibições e ações associadas a &quot;loggedIn = true&quot; atualizam o cache do at.js.

Ou seja, a at.js 2.x suporta uma maneira de recuperar exibições, ações e ofertas com os dados do público-alvo mais atualizados sob demanda.

**A at.js 2.x oferece suporte ao A4T para Aplicativos de página única?**

Sim, a at.js 2.x suporta o A4T para SPA por meio da função `triggerView()`, pois você implementou o Adobe Analytics e o Serviço de ID de visitante da Experience Cloud. Consulte o diagrama abaixo com descrições passo a passo.

![Fluxo do Target](/help/c-experiences/assets/atjs-spa-flow.png)

| Etapa | Descrição |
| --- | --- |
| 1 | `triggerView()` é chamado na SPA para renderizar uma visualização e aplicar ações a fim de modificar elementos visuais associados à visualização. |
| 2 | O conteúdo direcionado para a exibição é lido do cache. |
| 3 | O conteúdo direcionado é revelado o mais rápido possível sem oscilação do conteúdo padrão. |
| 4 | A solicitação de notificação é enviada para a Loja do perfil do Target para contar o visitante nas métricas de atividade e incremento. |
| 5 | Os dados do Analytics são enviados aos Servidores de coleta de dados. |
| 6 | Os dados do Target são correspondidos aos dados do Analytics pela SDID, e processados no armazenamento de relatório do Analytics. Em seguida, os dados do Analytics podem ser visualizados no Analytics e no Target pelos relatórios do A4T. |

>[!NOTE]
>Se não quiser enviar notificações ao Adobe Analytics para a contagem de impressões sempre que uma exibição for acionada, passe `{page: false}` para a função `triggerView()`, permitindo que a contagem de impressões não seja aumentada quando uma exibição é acionada várias vezes para um componente renderizado constantemente. Por exemplo:
>
>`adobe.target.triggerView(“PRODUCTS-PAGE-2”, {page:false})`

## Atividades com suporte

| Tipo de atividade | Suportado? |
| --- | --- |
| [Teste A/B](/help/c-activities/t-test-ab/test-ab.md) | Sim |
| [Recommendations como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md)<br>nas atividades de teste A/B e Direcionamento de experiência (XT) | Sim |
| [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Sim |
| [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md) | Sim |
| [Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | Não |
| [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) | Não |
| [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) | Não |
| [Recommendations](/help/c-recommendations/recommendations.md) | Não |

**Se a at.js 2.x for instalada e implementada `triggerView()` em nossos sites, como é possível executar atividades A/B de Direcionamento automático, já que a SPA do VEC não é compatível com o Direcionamento automático?**

Se você quiser usar atividades A/B de Direcionamento automático, mova todas as suas ações para serem executadas no Evento de carregamento de página no VEC. Passe o mouse sobre cada ação e clique no botão [!UICONTROL Mover para o evento de carregamento de página]. Depois de fazer isso, na próxima etapa você pode selecionar o Direcionamento automático para o método de alocação de tráfego.

## Integrações compatíveis

| Integração | Suportado? |
| --- | --- |
| [Analytics for Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md) | Sim |
| [Públicos-alvo da Experience Cloud](/help/c-integrating-target-with-mac/mmp.md) | Sim |
| [Atributos do cliente](/help/c-target/c-visitor-profile/working-with-customer-attributes.md) | Sim |
| [Fragmentos de experiência do AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md) | Sim |

## Recursos compatíveis   {#supported-features}

| Recurso | Suportado? |
| --- | --- |
| [Áreas de trabalho e propriedades](/help/administrating-target/c-user-management/property-channel/property-channel.md) | Sim |
| [Links de Controle de qualidade](/help/c-activities/c-activity-qa/activity-qa.md) | Sim |
| [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md) | Não |
| [Código personalizado](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md) | Sim |
| [Opções de VEC](/help/c-experiences/c-visual-experience-composer/viztarget-options.md) | Todos |
| [Rastreamento de cliques](/help/c-activities/r-success-metrics/click-tracking.md) | Sim |
| [Disponibilização de várias atividades](/help/c-experiences/c-visual-experience-composer/multipage-activity.md) | Sim |

## Configurações de entrega de página para o SPA VEC {#page-delivery-settings}

As configurações de [!UICONTROL Entrega de página] permitem definir regras para determinar quando uma atividade do Target deve ser qualificada e executada para um público-alvo.

Para acessar as opções de [!UICONTROL Entrega de página] no fluxo de trabalho de criação de atividade guiado de três partes do VEC, na etapa **[!UICONTROL Experiências]** , clique em **[!UICONTROL Configurar]** (ícone de engrenagem) > **[!UICONTROL Entrega de página]**.

![Caixa de diálogo de opções de Entrega de página](/help/c-experiences/assets/page-delivery.png)

Por exemplo, conforme definido pelas configurações de [!UICONTROL Entrega de página] mostradas acima, uma atividade do Target é qualificada e executada quando um visitante acessa diretamente `https://www.adobe.com`*ou* quando um visitante acessa qualquer URL que contém `https://www.adobe.com/products`. Isso funciona perfeitamente para aplicativos de várias páginas em que cada interação com a página chama um recarregamento de página, para o qual a at.js recupera as atividades qualificadas para o URL ao qual o usuário navega.

No entanto, como os SPAs funcionam de maneira diferente, as configurações de [!UICONTROL Entrega de página] devem ser definidas de modo a permitir que todas as ações sejam aplicadas às Exibições, conforme definido na atividade de SPA VEC.

### Exemplo de caso de uso

Considere este exemplo de caso de uso:

![Painel de Modificações de SPA VEC](/help/c-experiences/assets/page-delivery-example.png)

As seguintes alterações foram feitas:

* Alteração da cor de fundo na exibição Início, localizada no URL: [/#/](https://target.enablementadobe.com/react/demo/#/)https://target.enablementadobe.com/react/demo/#/.
* Alteração da cor do botão na exibição Produtos, localizada no URL: [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).

Com o exemplo acima em mente, o que aconteceria quando definíssemos as configurações de [!UICONTROL Entrega de página] para incluir apenas: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/) em um SPA com at.js 2.*x*?

![Caixa de diálogo Entrega de página](/help/c-experiences/assets/spa-page-delivery.png)

A ilustração a seguir mostra o Fluxo do Target - Solicitação de carregamento de página na at.js 2.*x*:

![Fluxo do Target - Solicitação de carregamento de página da at.js 2.0](/help/c-experiences/assets/page-load-request.png)

**Jornada do usuário nº 1**

* Um usuário navega diretamente para [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* at.js 2.*x*  O faz uma consulta ao Edge para ver se alguma atividade precisa ser executada para o URL: [https://target.enablementadobe.com/react/demo/#/](https://target.enablementadobe.com/react/demo/#/).
* Na etapa 6, o Target Edge retorna as ações para as exibições Início e Produtos para que sejam armazenadas em cache no navegador.

**Resultado**: o usuário vê a cor de fundo verde na exibição Início. Quando o usuário navega para [](https://target.enablementadobe.com/react/demo/#/products)https://target.enablementadobe.com/react/demo/#/products, a cor de fundo azul do botão é vista porque a ação foi armazenada no cache do navegador na exibição Produtos.

Observação: A navegação do usuário para [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products) não acionou um carregamento de página.

**Jornada do usuário nº 2**

* Um usuário navega diretamente para [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* at.js 2.*x*  O faz uma consulta ao Edge para ver se alguma atividade precisa ser executada para o URL: [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* Não há atividades qualificadas para [https://target.enablementadobe.com/react/demo/#/products](https://target.enablementadobe.com/react/demo/#/products).
* Como não há atividades qualificadas, não há ações e Exibições para armazenar em cache para a at.js 2.*x* acionar.

**Resultado**: mesmo que você tenha definido `triggerView()` para a exibição Produtos e executado uma ação na exibição Produtos por meio do SPA VEC, você não verá a ação esperada, pois não criou uma regra que incluísse [](https://target.enablementadobe.com/react/demo/#/products)https://target.enablementadobe.com/react/demo/#/products nas configurações de Entrega de página.

### Prática recomendada

Você pode ver que o gerenciamento da jornada do usuário pode ser bastante difícil, pois os usuários podem acessar qualquer URL do seu SPA e navegar para qualquer outra página. Portanto, é melhor especificar uma regra de Entrega de página que inclua um URL base para englobar todo o SPA. Dessa forma, não é necessário pensar em todas as diferentes jornadas e caminhos que um usuário pode tomar para chegar a uma página na qual você deseja exibir um teste A/B ou uma atividade de direcionamento de experiência (XT).

Por exemplo, para resolver o problema acima, é possível especificar o URL base nas configurações de Entrega de página da seguinte maneira:

![Caixa de diálogo Entrega de página](/help/c-experiences/assets/conclusion.png)

Isso garante que, sempre que um visitante acessar o SPA e navegar até a exibição Início ou Página, ele veja as ações aplicadas.

Agora, sempre que você adicionar uma ação a uma Exibição no SPA VEC, mostraremos a seguinte mensagem pop-up para lembrá-lo de pensar nas regras de [!UICONTROL Entrega de página].

![Mensagem das configurações de Entrega de página](/help/c-experiences/assets/pop-up-message.png)

Esta mensagem é exibida quando você adiciona a primeira ação a uma Exibição para cada atividade nova criada. Esta mensagem ajuda a garantir que todos na organização saibam aplicar essas regras de [!UICONTROL Entrega de página] corretamente.

## Vídeo de treinamento: uso do VEC para SPAs no Adobe Target

>[!VIDEO](https://video.tv.adobe.com/v/26249)

Consulte [Usar o Visual Experience Composer para aplicativo de página única (VEC SPA) no Adobe Target](https://helpx.adobe.com/target/kt/using/visual-experience-composer-for-single-page-applications-feature-video-use.html) para obter mais informações.
