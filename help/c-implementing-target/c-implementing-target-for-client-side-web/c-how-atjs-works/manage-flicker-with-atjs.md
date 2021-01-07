---
keywords: flicker;at.js;implementation;asynchronously;asynchronous;synchronously;synchronous
description: Informações sobre como a biblioteca de JavaScript at.js do Adobe Target impede a cintilação durante o carregamento de página ou aplicativo.
title: Como o at.js do Adobe Target gerencia a cintilação
feature: at.js
translation-type: tm+mt
source-git-commit: 6bb75e3b818a71af323614d9150e50e3e9f611b7
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 80%

---


# Como a at.js gerencia a cintilação{#how-at-js-manages-flicker}

Informações sobre como a biblioteca de JavaScript at.js do Target impede a cintilação durante o carregamento de página ou aplicativo.

A cintilação ocorre quando o conteúdo padrão é exibido momentaneamente aos visitantes, antes de ele ser substituído pelo conteúdo da atividade. A cintilação é indesejável porque pode ser confusa para os visitantes.

## Usando uma mbox global criada automaticamente {#section_C502170D551C4F52AAFD8E82C41BB63A}

Se você ativar a configuração [Criar mbox global automaticamente](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/understanding-global-mbox.md#concept_76AC0EC995A048238F3220F53773DB13) ao configurar o at.js, o at.js gerenciará a cintilação alterando a configuração de opacidade, à medida que a página é carregada. Ao carregar o at.js, é alterada a configuração de opacidade do `<body>` elemento para &quot;0&quot;, tornando a página invisível inicialmente para os visitantes. Após receber uma resposta do Target, ou se for detectado um erro com a solicitação Target, a at.js redefine a opacidade para &quot;1&quot;. Isso garante que o visitante veja a página somente depois que o conteúdo de suas atividades for aplicado.

Se a configuração for ativada ao definir a at.js, a at.js definirá a opacidade do estilo HTML BODY para 0. Após receber uma resposta do Target, a at.js redefine a opacidade do HTML BODY para 1.

A opacidade definida para 0 mantém o conteúdo da página oculto para evitar cintilação, mas o navegador ainda renderiza a página e carrega todos os recursos necessários, como CSS, imagens, etc.

Se a opacidade 0 não funcionar na implementação, você também poderá gerenciar a cintilação personalizando `bodyHiddenStyle` e configurando-a `body {visibility:hidden !important}`. Você pode usar o corpo do valor `{opacity:0 !important}` ou `body {visibility:hidden !important}`, o que funcionar melhor para sua circunstância específica.

A ilustração a seguir mostra as chamadas Ocultar corpo e Mostrar corpo no at.js 1.*x* e at.js 2.x.

**at.js 2.x**

![Fluxo do Target: Solicitação de carregamento de página da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/assets/atjs-20-flow-page-load-request.png)

**at.js 1.*x*** 

![](assets/target-flow2.png)

Para obter mais informações sobre `bodyHiddenStyle` a substituição, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).

## Gerenciamento de cintilação ao carregar at.js de maneira assíncrona

Carregar a at.js de forma assíncrona é uma ótima maneira de evitar o bloqueio de renderização do navegador. No entanto, essa técnica pode levar à cintilação na página da Web.

Você pode evitar a cintilação usando um trecho oculto previamente, que ficará visível após a personalização dos elementos HTML relevantes pelo [!DNL Target].

O at.js pode ser carregado de forma assíncrona, seja diretamente incorporado na página ou por meio de um gerenciador de tags (Adobe Launch, Dynamic Tag Manager (DTM) etc.).

Se o at.js estiver incorporado na página, o snippet deverá ser adicionado antes de carregar o at.js. Se você carregar o at.js por meio de um gerenciador de tags, que também é carregado de forma assíncrona, é necessário adicionar o snippet antes de carregar o gerenciador de tags. Se o gerenciador de tags for carregado sincronicamente, o script poderá ser incluído no gerenciador de tags antes de at.js.

O trecho de código oculto previamente é como o seguinte:

```
;(function(win, doc, style, timeout) {
  var STYLE_ID = 'at-body-style';

  function getParent() {
    return doc.getElementsByTagName('head')[0];
  }

  function addStyle(parent, id, def) {
    if (!parent) {
      return;
    }

    var style = doc.createElement('style');
    style.id = id;
    style.innerHTML = def;
    parent.appendChild(style);
  }

  function removeStyle(parent, id) {
    if (!parent) {
      return;
    }

    var style = doc.getElementById(id);

    if (!style) {
      return;
    }

    parent.removeChild(style);
  }

  addStyle(getParent(), STYLE_ID, style);
  setTimeout(function() {
    removeStyle(getParent(), STYLE_ID);
  }, timeout);
}(window, document, "body {opacity: 0 !important}", 3000));
```

Por padrão, o trecho oculta previamente todo o HTML BODY. Em alguns casos, talvez você queira ocultar previamente apenas certos elementos de HTML e não a página inteira. Você pode conseguir isso personalizando o parâmetro de estilo. Ele pode ser substituído por algo que oculte previamente apenas regiões específicas da página.

Por exemplo, você tem duas regiões identificadas por IDs, container-1 e container-2, por isso o estilo poderá ser substituído pelo seguinte:

```
#container-1, #container-2 {opacity: 0 !important}
```

Em vez do padrão:

```
body {opacity: 0 !important}
```

## Gerenciar oscilação em at.js 2.x para triggerView()

Ao usar `triggerView()` para mostrar o conteúdo direcionado em seu SPA, o gerenciamento de cintilação é fornecido imediatamente. Isso significa que a lógica pré-ocultar não precisa ser adicionada manualmente. Em vez disso, a at.js 2.x pré-oculta o local em que sua exibição precisa ser mostrada antes de aplicar o conteúdo direcionado.

## Gerenciar oscilação com getOffer() e applyOffer()

Como `getOffer()` e `applyOffer()` são APIs de baixo nível, não há controle de cintilação incorporado. É possível passar um seletor ou elemento HTML como opção `applyOffer()`, nesse caso, `applyOffer()` adiciona o conteúdo da atividade a este elemento específico; no entanto, verifique se o elemento está pré-oculto corretamente antes de chamar `getOffer()` e `applyOffer()`.

```
document.documentElement.style.opacity = "0";
 
adobe.target.getOffer({
    mbox: 'target-global-mbox',
    success: function(offer) {
        adobe.target.applyOffer({
            mbox: 'target-global-mbox',
            offer: offer
        });
 
        document.documentElement.style.opacity = "1";
    },
    error: function() {
        document.documentElement.style.opacity = "1";        
    }
});
```

## Usar uma mbox regional com mboxCreate() em at.js 1.x (não suportado em at.js 2.x)

Se você usar uma implementação de mbox regional, poderá usar `mboxCreate()` com sua página provisionada semelhante ao seguinte código de exemplo:

```
<div class="mboxDefault">
Some default content
</div>
<script>
mboxCreate('some-mbox');
</script>
```

Se as suas páginas estiverem corretamente provisionadas, o at.js gerenciará a cintilação ao trocar apropriadamente a propriedade de &quot;visibilidade&quot; de CSS do elemento pela classe mboxDefault.