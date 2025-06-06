---
keywords: visual experience composer; práticas recomendadas do visual experience composer; limitações do visual experience composer; avisos do visual experience composer; práticas recomendadas do vec; vec
description: Conheça as práticas recomendadas para que suas experiências funcionem conforme o esperado ao usar o [!UICONTROL Visual Experience Composer] (VEC).
title: Quais são as práticas recomendadas e as limitações do [!UICONTROL Visual Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
source-git-commit: 8c62a0e976ce075d07e1f80018c7ad7fac240eea
workflow-type: tm+mt
source-wordcount: '2435'
ht-degree: 37%

---

# Práticas recomendadas e limitações do [!UICONTROL Visual Experience Composer]

Para garantir que suas experiências funcionem conforme o esperado, siga as práticas recomendadas ao usar o [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC). Esteja ciente das principais dicas e limitações para maximizar o desempenho e evitar problemas comuns.

## Práticas recomendadas {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

Estas são as práticas recomendadas ao usar o VEC:

### Coloque a referência à at.js na parte superior da seção `<head>` da página.

+++Ver detalhes
Se você também usa o [!UICONTROL Visitor API Service], coloque o script de API do visitante acima da at.js.

+++

### Você pode habilitar o [!UICONTROL Enhanced Experience Composer] no nível da conta (habilitado para todas as atividades criadas na conta) ou no nível da atividade individual.

+++Ver detalhes
Para habilitar o [!UICONTROL Enhanced Experience Composer] no nível da conta, clique em [!UICONTROL [!UICONTROL Administration] > [!UICONTROL Visual Experience Composer]] e alterne a opção [!UICONTROL Enable Enhanced Experience Composer] para a posição Ligado.

Para habilitar [!UICONTROL Enhanced Experience Composer] no nível de atividade ao criar uma atividade no [!UICONTROL Visual Experience Composer], clique em [!UICONTROL Configure > [!UICONTROL Page Delivery]] e alterne o switch [!UICONTROL Enable Enhanced Experience Composer] para a posição Ligado.

+++

### Incluir na lista de permissões Você pode modificar determinados endereços IP se o [!UICONTROL Enhanced Experience Composer] não carregar em páginas seguras no seu site.

+++Ver detalhes
Problemas ao carregar o [!UICONTROL Enhanced Experience Composer] podem ser resolvidos através do incluir na lista de permissões dos seguintes endereços IP. Esses endereços IP são para [!DNL Adobe] servidores usados para o proxy [!UICONTROL Enhanced Experience Composer]. Eles são necessários somente para a atividade de edição. Incluir na lista de permissões Os visitantes do seu site não precisam desses endereços IP resolvidos.

Para obter mais informações, consulte [O EEC não carregará uma URL de controle de qualidade interna que não esteja acessível no IP público](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md) em *Solução de problemas relacionados ao Enhanced Experience Composer*.

+++

### Use IDs únicas para elementos de nível superior e outros elementos que podem ser bons candidatos a teste/direcionamento.

+++Detalhes
Qualquer coisa imediatamente dentro do elemento do corpo deve ter uma ID exclusiva. Se novos elementos forem inseridos no corpo de texto e o código for movido, pelo menos os elementos pai serão mais fáceis de reconhecer.

[!DNL Target] não requer IDs, mas usar IDs aumenta a confiabilidade das experiências criadas com o compositor de experiências. [!DNL Target] usa seletores de CSS para modificar seu conteúdo quando a experiência é entregue. Quando você edita uma experiência, o [!UICONTROL Visual Experience Composer] ancora o seletor ao ancestral mais próximo com um atributo de ID não nulo ao elemento HTML que está sendo modificado. Portanto, não é aconselhável usar nenhum mecanismo, incluindo bibliotecas de JavaScript, que defina ou modifique atributos de ID HTML. Embora essas IDs possam estar disponíveis para o compositor de experiência do [!DNL Target] para criação de atividades, se o JavaScript modificar IDs, a ID usada quando a experiência foi criada pode não estar disponível quando a experiência foi executada. Se não houver uma ID disponível, o seletor ancorado para a ID falhará.

+++

### Nomeie as classes CSS para identificá-las facilmente.

+++Detalhes
Ao editar classes CSS no [!DNL Visual Experience Composer], é útil facilitar a identificação das classes usando nomes de classe descritivos. Isso o ajuda a assegurar que você edite as classes CSS certas e suas páginas tenham a aparência esperada.

Não use a propriedade de CSS `!important` CSS ao ocultar ou remover elementos.

Se a propriedade CSS `!important` estiver presente, as alterações feitas por `target.js` durante a entrega serão substituídas pelas regras CSS do site.

+++

### Evite usar tabelas HTML para layouts de página.

+++Detalhes
[!DNL Target] usa JavaScript para formatar uma página. É difícil modificar layouts baseados em tabelas com o JavaScript. Além disso, os layouts baseados em tabela podem não ser exibidos da mesma maneira em todos os navegadores. Para obter os melhores resultados, use CSS para criar layouts de página.

+++

### Reduza o uso de iFrames.

+++Detalhes
É uma boa prática minimizar o uso de iFrames para simplificar o gerenciamento de páginas e testes. O Visual Experience Composer pode aplicar algumas ações em um iFrame, mas algumas ações, como redimensionamento, não funcionam corretamente. É difícil gerenciar e redimensionar páginas que usam vários iFrames. Em virtude disso, testar páginas com muitos iFrames pode causar problemas.

+++

### Tente organizar todas as modificações de DOM dinâmicas assim que possível depois que o DOM estiver pronto.

+++Detalhes
Se as modificações não forem aplicadas antes do aplicativo de experiência por `target.js`, a entrega do conteúdo poderá ser interrompida. Isso acontecerá somente quando houver uma alteração de DOM na hierarquia de um elemento direcionado.

+++

### Use somente texto simples ou uma tag de imagem nos seus elementos de ancoragem.

+++Detalhes
`<a>Anchor Text</a>`

OU

`<a href=""> <img src=""> </img> </a>`

+++

### Evite elementos de nível de bloco dentro de um elemento em linha.

+++Detalhes
Os elementos de nível de bloco não devem ser usados dentro de elementos em linha, como âncora, extensão e assim por diante. Isso faz com que os elementos em linha percam sua altura e largura, de modo que a ferramenta de sobreposição no [!UICONTROL Visual Experience Composer] pode não funcionar conforme esperado.

+++

### Não use a base da tag no seu site para resolver URLs e links.

+++Detalhes
O VEC manipula o site nos bastidores, usando um servidor proxy que atualiza os links. Se você adicionar uma base de tag, os URLs utilizados pelo servidor proxy serão resolvidos novamente pelo navegador e aparecerão quebrados.

+++

### O uso de EDIT HTML para manipular a estrutura DOM pode quebrar os seletores.

+++Detalhes
Por exemplo, se você executou duas ações:

* Adicionou uma classe ao Elemento 1
* Editou o HTML do Elemento 1

Cada alteração cria um novo elemento no VEC. Como a segunda ação modifica o Elemento 1, se você o excluir, a segunda ação não terá mais nada para modificar, e a alteração não funcionará mais.

Em outras palavras, se você adicionar um elemento com texto e, em seguida, editar esse elemento em uma ação separada com um texto diferente, o editor de códigos mostrará ambas as ações como elementos separados. Ao editar o elemento, você criou um novo elemento que modifica o elemento original que você criou, contendo o texto editado. Se você então excluir o elemento original, o texto editado não poderá encontrar o elemento que foi editado e não será exibido. O segundo elemento permanece na lista de elementos, mas não afeta a página porque o elemento que ele modifica não existe mais.

Consulte [Seletores de elementos usados em [!UICONTROL Visual Experience Composer]](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337).

+++

### Use as marcas `<b>` e `<i>` ao estilizar elementos de texto com o editor de rich text.

+++Detalhes
* Para texto em negrito, use `<b>` em vez de `<strong>`.
* Para texto em itálico, use `<i>` em vez de `<em>`.

As tags `<strong>` e `<em>` podem causar resultados inesperados.

+++

### Tenha cuidado ao remover campos de formulário.

+++Detalhes
Determinados campos de formulário podem ser obrigatórios para envio. A remoção desses campos de formulário poderá afetar os envios.

+++

### Não inclua `mboxCreate` em scripts.

+++Detalhes
Como `mboxCreate` usa `document.write`, não é recomendável incluir `mboxCreate` em scripts. Em vez disso, use `mboxDefine` e `mboxUpdate` para o mesmo propósito.

+++

### Não atualize um trecho HTML usando [!DNL Target] se ele exigir um código JavaScript para a inicialização.


+++Detalhes
Quando uma ação (Editar HTML) é executada em componentes da página (como controles deslizantes, carrosséis e assim por diante), a entrega pode parecer interrompida. O VEC executa a ação depois que o componente de página é instanciado pelo JavaScript.

Entretanto, quando o conteúdo da página for entregue aos visitantes, a ação é aplicada antes de instanciar o componente. Devido a isso, a funcionalidade desse componente pode ou não ser quebrada no momento da entrega. A funcionalidade depende da natureza do script usado nesta página, para definir o componente.

Se você testar para entrega e ela funcionar da primeira vez, não há garantias de que ela continuará funcionando. Pode (ou não) ser uma condição de corrida.

* Se houver uma condição de corrida, a entrega funciona intermitentemente.
* Se não houver condição de corrida, a entrega sempre funcionará.

Teste a sua página várias vezes, para ter certeza de que a entrega funciona conforme esperado.

+++

### Não use uma base da tag no seu site para resolver URLs e links.

+++Detalhes
Quando você usa o [!UICONTROL Enhanced Experience Composer], o site é manipulado em segundo plano por um servidor proxy que atualiza todas as URLs de links para que funcionem no proxy. Se você adicionar uma tag base, todos esses URLs serão resolvidos pelo navegador para que pareçam corrompidos.

+++

### O texto importante no site que pode ser usado para direcionamento deve ser mantido no código HTML dentro de um elemento.

+++Detalhes
Por exemplo, você não pode direcionar o texto do carrinho de compras no VEC se o código for como o seguinte:

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart"> 
   <img alt="Shopping Cart"src="/images/ico-cart.gif"></img> 
   Shopping Cart: 
   <span id="HeaderCartQtyTotal">
      0 
  </span> 
  Items 
  <span id="HeaderCartPriceTotal"></span> 
</a>
```

Neste exemplo, todo o elemento de ancoragem é selecionado no VEC, o que afeta negativamente outros elementos se o direcionamento for executado.

+++

### Não use `top` ou `self` variáveis no código JavaScript.

+++Detalhes
Quando a [!UICONTROL Enhanced Experience Composer] está habilitada, o valor das variáveis superior e própria é atualizado para desabilitar a edição do iframe. Use um cabeçalho de X-frame-options para adicionar a edição do iframe, em vez dos códigos JavaScript personalizados.

+++

### Sempre teste o seu site se os parâmetros são adicionados durante o carregamento da página.

+++Detalhes
Por exemplo, para abrir `www.abc.com`, os seguintes parâmetros de URL são usados:

`www.abc.com?mboxEdit=1&mboxDisable=1`

Esses parâmetros ativam a edição em um iframe.

Certifique-se de que o seu site carregue conforme esperado, após adicionar parâmetros como esses.

+++

### Certifique-se de que a sua página abra conforme esperado em um iframe.

+++Detalhes
Desative as técnicas de interrupção de iframe no seu site e verifique se o site abre como esperado em um iframe em uma página de testes. Por exemplo:

```html
<!DOCTYPE 
<html> 
<html> 
<head> 
  <meta charset="utf-8"> 
  <meta name="viewport" content="width=device-width"> 
  <title>JS Bin</title> 
</head> 
<body> 
  <iframe src="https://www.homedepot.com"</iframe> 
</body> 
</html>
```

+++

## Avisos {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Considere os avisos a seguir ao usar o [!UICONTROL Visual Experience Composer] para criar sua atividade.

### O recurso [!UICONTROL Move] não dá suporte ao índice z.

+++Detalhes
Como não há nenhuma funcionalidade de índice z, o elemento movido não pode ser movido para cima de outro elemento. Consulte [Limitações](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) para obter mais detalhes.

+++

### A reorganização dos elementos afeta o rastreamento de cliques.

+++Detalhes
Se um elemento marcado para rastreamento de cliques for reorganizado, os caminhos dos elementos reorganizados serão alterados. Assim, o elemento no local em que o elemento original estava antes de ser reorganizado é aquele cujos cliques são acompanhados.

Isso ocorre porque o código para entregar o conteúdo da atividade e o código para rastrear os cliques está incluído em um pedaço de código entregue à página. Se você navegar para uma página diferente e configurar o acompanhamento por clique, então o código de conteúdo da atividade e o código de rastreamento de cliques são fornecidos para essa página. Se a página de acompanhamento de clique tem uma estrutura de página similar à página de execução de teste, então o conteúdo de teste pode aparecer também na página de acompanhamento de clique.

+++

### A inserção de um elemento pode não funcionar em um `<div>` que seja uma mbox.

+++Detalhes
Se uma mbox contiver uma oferta, inserir um elemento pode aparecer como `insertBefore` e não `insertAfter`, se a mbox for implementada incorretamente.

+++

### Ao editar um elemento principal e secundário, edite o principal primeiro.

+++Detalhes
Se você trocar uma ação de imagem em um elemento e editar o texto ou o HTML no elemento pai, poderão ocorrer problemas de entrega. O melhor fluxo de trabalho é editar o elemento principal antes de trocar a imagem no elemento secundário.

+++

### Não é possível selecionar o elemento de página que inclui uma mbox como um elemento filho.

+++Detalhes
Por exemplo, se a sua página contiver:

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

A div externa não deve ser selecionada em uma experiência porque a mbox codificada na página ainda faz uma chamada para [!DNL Target] e recebe uma resposta. Essa resposta interfere na resposta pretendida para o elemento de página maior.

+++

### Os IPs proxy podem ser bloqueados no ambiente dos clientes.

+++Detalhes
Se você estiver usando o [!UICONTROL Enhanced Experienced Composer] em um site sem transmissão ao vivo, como um ambiente de preparo, poderá ver erros de tempo limite e acesso negado se o site bloquear RIPs.

+++

## Limitações {#section_F33C2EA27F2E417AA036BC199DD6C721}

Considere as seguintes limitações ao trabalhar com o VEC:

### Manipulando compatibilidade do VEC com [!DNL Chrome] alterações de política de extensão. {#ext}

+++Detalhes
Devido às políticas atualizadas do Manifesto [V3 no Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}, as extensões não podem mais modificar o DOM original antes que ele seja analisado pelo navegador. Como resultado, determinados scripts de segurança, como implementações de edição de iframe, podem impedir que as páginas sejam carregadas no VEC.

Para garantir a compatibilidade, esses scripts devem ser desabilitados condicionalmente quando a página for carregada dentro do iframe [!DNL Target]. Esse processo pode ser feito com segurança verificando a presença do objeto `window.adobeVecExtension`, que é inserido por [!DNL Target] durante o carregamento do VEC.

Os trechos de código a seguir são exemplos de código de interrupção de iframe que podem fazer com que a página da Web não seja carregada no VEC:

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

Uma verificação simples pode ser usada para verificar quando uma página da Web é inserida dentro de [!DNL Target]. Um trecho de código deve ter esta aparência:

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

### Não é possível mover um elemento fora de um container seguido de uma propriedade CSS.

+++Detalhes
Um elemento não pode ser movido para fora de um contêiner seguido por uma propriedade CSS.

+++

### Você não pode selecionar o elemento [!UICONTROL Button] para reorganização.

+++Detalhes
[!UICONTROL Button] elementos não podem ser selecionados diretamente para reorganização. Para habilitar a reorganização, coloque botões dentro de um contêiner maior.

+++

### Somente ofertas de troca estão disponíveis em mboxes.

+++Detalhes
Ações como [!UICONTROL Edit Class] e [!UICONTROL Rearrange] não são permitidas dentro de uma mbox.

+++

### Você não deve reorganizar e mover o mesmo elemento.

+++Detalhes
Se um elemento tiver sido movido para outro local, e você selecionar o contêiner principal e tentar reorganizar os elementos secundários, o elemento movido não será afetado e permanecerá onde está. A reorganização talvez não apareça da maneira desejada.

+++

### A ação [!UICONTROL Change Image] não funciona em uma imagem no carrossel.

+++Detalhes
Se, por exemplo, sua página contiver um carrossel com seis imagens e você quiser trocar uma imagem pela segunda imagem do carrossel, a ação [!UICONTROL Change Image] não funcionará.

A solução alternativa é selecionar o contêiner pai e usar a ação [!UICONTROL Edit HTML] para editar a HTML do carrossel e atualizar a fonte de imagem da imagem desejada.

+++

### As imagens não podem ser redimensionadas em uma mbox.

+++Detalhes
Se você trocar uma imagem em um elemento de mbox, tente redimensionar essa imagem de acordo com o tamanho do elemento da mbox, o redimensionamento não será permitido.

+++

### Depois que trocar uma imagem, você não poderá selecionar a ação [!UICONTROL Edit].

+++Detalhes
Depois que trocar a imagem, você não poderá editar o URL do Scene7.

+++

### Os elementos do HTML com uma fonte externa não podem ser editados.

+++Detalhes
Por exemplo: Vídeo, tags de áudio, código incorporado, iFrames, quadros.

+++

### O rastreamento de cliques não funciona para elementos de ancoragem que contenham qualquer coisa diferente de texto simples ou tags de imagem.

+++Detalhes
Por exemplo, o rastreamento de cliques não funcionará se o elemento contiver JavaScript.

+++

### As páginas devem aceitar os parâmetros de URL para que o VEC funcione.

+++Detalhes
Alguns sites removem quaisquer parâmetros de URL de suas páginas. No entanto, o VEC exige esses parâmetros.

+++

### Ao usar um script como parte do HTML, qualquer variável e função acessada da parte externa deve ser declarada no namespace da janela.

+++Detalhes
O script é executado no escopo de `target.js` depois que a página é carregada. Portanto, qualquer variável ou função que seja declarada localmente não está acessível da parte externa do bloco do script.

*Incorreto:*

```html
<script> 
  var myVar = 123; 
  function myFunc() { 
    // 
  } 
</script>`
```

*Correto:*

```html
<script> 
  window.myVar = 123; 
  window.myFunc = function() { 
    // 
  }; 
</script>
```

+++

### Inserir uma imagem na biblioteca [!UICONTROL Content] (Scene7) e editar o HTML quebra a URL da imagem.

+++Detalhes
Adicione um elemento de âncora dentro da div &#39;customHeaderMessage&#39; com algum texto fictício:

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

Selecione esta div usando a ação [!UICONTROL Insert Element] para inserir uma imagem como irmã desta div de texto fictício.

Após a inserção da imagem, ele tem a seguinte aparência:

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Remova a extensão de texto de teste.

+++

### A ação `customCode` no VEC não funciona com [!DNL Internet Explorer] 8.

+++Detalhes
Devido às limitações do IE8 ao manipular o conteúdo do script, o `target.js` não oferece suporte a isso no IE8. Como solução, se a página contiver jQuery e estiver exposta ao objeto window globalmente, `target.js` pode usar para entregar a ação `customCode`. Verifique se `window.jQuery` e `window.jQuery.fn.prepend` estão definidos.

+++

### O rastreamento de cliques é compatível somente na página em que as experiências são criadas ou na página redirecionada.

+++Detalhes
Embora o modo [!UICONTROL Browse] esteja disponível para o rastreamento de cliques no VEC, o modo [!UICONTROL Browse] não pode ser usado para adicionar o rastreamento de cliques em uma página.

+++
