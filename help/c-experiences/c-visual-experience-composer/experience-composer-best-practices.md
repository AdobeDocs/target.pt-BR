---
keywords: visual experience composer; práticas recomendadas do visual experience composer; limitações do visual experience composer; avisos do visual experience composer; práticas recomendadas do vec; vec
description: Seguir as práticas recomendadas pode ajudar as suas experiências a funcionarem como esperado. Há também outras dicas e limitações que você deve ter em mente ao usar o Visual Experience Composer (VEC) no Adobe Target.
title: Práticas recomendadas e limitações do Visual Experience Composer
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '2472'
ht-degree: 95%

---


# Práticas recomendadas e limitações do Visual Experience Composer

Seguir as práticas recomendadas pode ajudar as suas experiências a funcionarem como esperado. Há também outras dicas e limitações que você deve ter em mente ao usar o Visual Experience Composer (VEC) em [!DNL Adobe Target].

Ao seguir essas práticas recomendadas, você tem menos probabilidade de encontrar problemas inesperados com as experiências que projeta.

## Práticas recomendadas {#section_86CF28C99CFF40329E4CBAFE4DD78BB4}

**Para a mbox. js versão 57 e posterior, e para o at.js, insira a referência de mbox.js ou at.js na parte superior da seção `<head>` da sua página.**

Se você também usa o serviço de API do visitante, coloque o script de API do visitante acima da mbox.js ou at.js.

**Para versões da mbox.js antes da 57, coloque o código da mbox.js o mais baixo possível na seção `<head>` da sua página.**

Coloque o mbox.js no final da seção `<head>`, sem declarações adicionais depois. Caso contrário, qualquer tag ou tag de link será movida para a seção `<body>`.

**Você pode ativar/desativar o Enhanced Experience Composer no nível da conta (ativada para todas as atividades criadas na conta) ou no nível da atividade individual.**

Para ativar o Enhanced Experience Composer no nível da conta, clique em [!UICONTROL Administração > Visual Experience Composer] e alterne a opção para a posição Ligado.

Para ativar o Enhanced Experience Composer no nível da atividade enquanto cria uma atividade no Visual Experience Composer, clique em [!UICONTROL Configurar > URL] e, em seguida, alterne o comutador para a posição Ligado.

**Você pode lista de permissões determinados endereços IP se o Visual Experience Composer aprimorado não for carregado em páginas seguras do site.**

Problemas ao carregar o Visual Experience Composer aprimorado podem ser resolvidos ao incluir na lista de permissões os seguintes endereços IP. Esses endereços IP são para o servidor do Adobe usado para o proxy do Enhanced Experience Composer. Eles são necessários somente para a atividade de edição. Os visitantes do site não precisam desses endereços IP incluir na lista de permissões.

Estados Unidos: 52.55.99.45, 54.80.158.92, and 54.204.197.253

Europa, Oriente Médio e África (EMEA): 52.51.238.221, 52.210.199.44 e 54.72.56.50

Pacífico Asiático (APAC): 52.193.67.35, 54.199.198.109 e 54.199.241.57

**Use IDs exclusivas para elementos de nível superior e outros elementos que podem ser bons candidatos a teste/direcionamento.**

Qualquer item imediatamente dentro do elemento body deve ter uma ID exclusiva. Se novos elementos forem inseridos no corpo de texto e o código for movido, pelo menos os elementos pai serão mais fáceis de reconhecer.

O Adobe Target não requer IDs, mas o uso de IDs aumenta a confiabilidade das experiências criadas com o Experience Composer. O Target usa seletores de CSS para modificar seu conteúdo quando a experiência é entregue. Quando você edita uma experiência, o Visual Experience Composer ancora o seletor para o ancestral mais próximo com um atributo de ID não nulo para o elemento HTML sendo modificado. Portanto, não é aconselhável usar nenhum mecanismo, incluindo bibliotecas de JavaScript, que defina ou modifique atributos de ID HTML. Embora essas IDs possam estar disponíveis para o Target Experience Composer para a criação de atividade, se o JavaScript modificar IDs, a ID que foi usada quando a experiência foi criada talvez não esteja disponível quando a experiência for executada. Se não houver uma ID disponível, o seletor ancorado para a ID falhará.

**Nomeie as classes CSS para identificá-las facilmente.**

Ao editar classes CSS no Visual Experience Composer, será útil tornar as classes facilmente identificáveis usando nomes de classe descritivos. Isso o ajuda a assegurar que você edite as classes CSS certas e suas páginas tenham a aparência esperada.

Não use a propriedade de CSS `!important` CSS ao ocultar ou remover elementos.

Se a propriedade CSS 1!important1 CSS está presente, as alterações feitas por target.js durante a entrega serão substituídas pelas regras CSS do site.

**Evite usar tabelas HTML para layouts de página.**

O Target Standard e o Premium usam JavaScript para formatar uma página. É difícil modificar layouts baseados em tabelas com o JavaScript. Além disso, os layouts baseados em tabela podem não ser exibidos da mesma maneira em todos os navegadores. Para obter os melhores resultados, use CSS para criar layouts de página.

**Reduza o uso de iFrames.**

É uma boa prática reduzir o uso de iFrames, para simplificar o gerenciamento de páginas e teste. O Visual Experience Composer pode aplicar algumas ações em um iFrame, mas algumas delas, como redimensionar, não funcionam corretamente. É difícil gerenciar e redimensionar páginas que usam vários iFrames. Em virtude disso, testar páginas com muitos iFrames pode causar problemas.

**Tente organizar todas as modificações de DOM dinâmicas assim que possível depois que o DOM estiver pronto.**

Se as suas modificações não forem aplicadas antes da aplicação de target.js, a entrega de conteúdo poderá ser interrompida. Isso acontecerá somente quando houver uma alteração de DOM na hierarquia de um elemento direcionado.

**Use somente texto simples ou uma tag de imagem nos seus elementos de ancoragem.**

`<a>Anchor Text</a>`

OU

`<a href=""> <img src=""> </img> </a>`

**Evite elementos de nível de bloco dentro de um elemento em linha.**

Os elementos de nível de bloco não devem ser usados dentro de elementos em linha como âncora, span etc. Isso faz com que os elementos em linha percam sua altura e largura, de modo que a ferramenta de sobreposição no Visual Experience Composer talvez não funcione como esperado.

**Não use a base da tag no seu site para resolver URLs e links.**

O Visual Experience Composer manipula o site em segundo plano, usando um servidor proxy que atualizou os links. Se você adicionar uma base de tag, os URLs utilizados pelo servidor proxy serão resolvidos novamente pelo navegador e aparecerão quebrados.

**O uso de EDIT HTML para manipular a estrutura DOM pode quebrar os seletores.**

Por exemplo, se você realizou duas ações:

* Adicionou uma classe ao Elemento 1
* Editou o HTML do Elemento 1

Cada alteração cria um novo elemento no Visual Experience Composer. Como a segunda ação modifica o Elemento 1, se você o excluir, a segunda ação não terá mais nada para modificar, e a alteração não funcionará mais.

Em outras palavras, se você adicionar um elemento com texto e, em seguida, editar esse elemento em uma ação separada com um texto diferente, o editor de códigos mostrará ambas as ações como elementos separados. Ao editar o elemento, você criou um novo elemento que modifica o elemento original que você criou, contendo o texto editado. Se você então excluir o elemento original, o texto editado não poderá encontrar o elemento que foi editado e não será exibido. O segundo elemento permanece na lista de elementos, mas não afeta a página porque o elemento que ele modifica não existe mais.

Consulte [Seletores de elementos usados no Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/vec-selectors.md#concept_4EB7663E255F439B8D24079D23479337).

**Use as tags `<b>` e `<i>` ao estilizar elementos de texto com o editor de rich text.**

* Para texto em negrito, use `<b>` em vez de `<strong>`.
* Para texto em itálico, use `<i>` em vez de `<em>`.

As tags `<strong>` e `<em>` podem causar resultados inesperados.

**Tenha cuidado ao remover campos de formulário.**

Certos campos de formulário poderão ser obrigatórios para envio. A remoção desses campos de formulário poderá afetar os envios.

**Não inclua `mboxCreate` em scripts.**

Como `mboxCreate` usa `document.write`, não é recomendado incluir `mboxCreate` em scripts. Em vez disso, use `mboxDefine` e `mboxUpdate` para o mesmo propósito.

**Não atualize um snippet de html usando Target Standard, se ele necessitar de um código JavaScript para a inicialização.**

Quando uma ação (Edit HTML) é realizada nos componentes da página (como Controles deslizantes, Carrosséis etc.), a entrega pode parecer quebrada. O Visual Experience Composer executa a ação após o componente da página tiver sido instanciado pelo JavaScript.

Entretanto, quando o conteúdo da página for entregue aos visitantes, a ação é aplicada antes de instanciar o componente. Devido a isso, a funcionalidade desse componente pode ou não ser quebrada no momento da entrega. A funcionalidade depende da natureza do script usado nesta página, para definir o componente.

Se você testar para entrega e ela funcionar da primeira vez, não há garantias de que ela continuará funcionando. Pode (ou não) ser uma condição de corrida.

* Se houver uma condição de corrida, a entrega funcionará de modo intermitente.
* Se não houver uma condição de corrida, ela sempre funcionará.

Teste a sua página várias vezes, para ter certeza de que a entrega funciona conforme esperado.

**Não use uma base da tag no seu site para resolver URLs e links.**

Quando você usa o Enhanced Experience Composer, o site é manipulado em segundo plano por um servidor proxy que atualizou todos os URLs do link para que funcionem no proxy. Se você adicionar uma base da tag, todos esses URLs são resolvidos pelo navegador, então aparecem quebrados.

**O texto importante no site que pode ser usado para direcionamento deve ser mantido no código HTML dentro de um elemento.**

Por exemplo, você não pode direcionar o texto do Carrinho de compras no VEC, se o código for parecido com este:

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

Neste exemplos, todo o elemento da âncora é selecionado no VEC, prejudicando outros elementos, se o direcionamento for realizado.

**Não use `top` ou `self` variáveis no código JavaScript.**

Quando o Enhanced Experience Composer está ativado, o valor das variáveis superior e própria é atualizado para desativar o iframe busting. Use um cabeçalho de X-frame-options para adicionar a edição do iframe, em vez dos códigos JavaScript personalizados.

**Sempre teste o seu site se os parâmetros são adicionados durante o carregamento da página.**

Por exemplo, para abrir www.abc.com, os parâmetros de URL a seguir são usados:

`www.abc.com?mboxEdit=1&mboxDisable=1`

Esses parâmetros ativam a edição em um iframe.

Certifique-se de que o seu site carregue conforme esperado, após adicionar parâmetros como esses.

**Certifique-se de que a sua página abra conforme esperado em um iframe.**

Desative as técnicas de edição de iframe no seu site e verifique se ele abre conforme esperado dentro de um iframe em uma página de teste. Por exemplo:

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

## Avisos {#section_A0436B7B85BA467FA9DE13A9A40E6A6E}

Considere os avisos a seguir ao usar o Visual Experience Composer para projetar sua atividade.

**O recurso Move não tem suporte para o índice z.**

Como não há nenhuma funcionalidade de índice z, o elemento movido não pode ser movido para cima de outro elemento. Consulte [Limitações](/help/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) para obter mais detalhes.

**A reorganização dos elementos afeta o rastreamento de cliques.**

Se um elemento marcado para rastreamento de cliques for reorganizado, os caminhos dos elementos reorganizados são alterados. Assim, o elemento no local em que o elemento original estava antes de ser reorganizado é aquele cujos cliques são acompanhados.

Isso ocorre porque o código para entregar o conteúdo da atividade e o código para rastrear os cliques está incluído em um pedaço de código entregue à página. Se você navegar para uma página diferente e configurar o acompanhamento por clique, então o código de conteúdo da atividade e o código de rastreamento de cliques são fornecidos para essa página. Se a página de acompanhamento de clique tem uma estrutura de página similar à página de execução de teste, então o conteúdo de teste pode aparecer também na página de acompanhamento de clique.

**A inserção de um elemento pode não funcionar em uma mbox `<div>`.**

Se uma mbox contiver uma oferta, inserir um elemento pode aparecer como insertBefore e não insertAfter, se a mbox estiver implementada incorretamente.

**Ao editar um elemento principal e secundário, edite o principal primeiro.**

Se você trocar uma ação da imagem em um elemento e depois editar o texto ou HTML no seu elemento principal, poderá ocorrer problemas. O melhor fluxo de trabalho é editar o elemento principal antes de trocar a imagem no elemento secundário.

**Não é possível selecionar o elemento de página que inclui uma mbox como um elemento filho.**

Por exemplo, se a sua página contiver:

```html
<div> 
  <div class="mboxDefault" > 
  </div>
  <script>mboxCreate('myMbox'); 
</div>`
```

O div externo não deve ser selecionado em uma experiência porque a mbox codificada na página ainda faz uma chamada para Target e recebe uma resposta. Essa resposta interfere na resposta pretendida para o elemento de página maior.

**Os IPs proxy podem ser bloqueados no ambiente dos clientes.**

Se você estiver usando o Enhanced Experienced Composer em um site sem transmissão ao vivo, como um ambiente de preparo, poderá observar erros de tempo limite e acesso negado, se o seu site bloquear RIPs.

**Ao adicionar várias páginas, o painel de experiência e da página são abertos ao mesmo tempo. Isso eventualmente diminui com a largura do Visual Experience Composer para exibir o site para otimizações. Como resultado, os sites refluídos podem começar a aparecer no espaço reduzido de modo diferente do esperado.**

A solução é recolher o painel de experiência e o painel da página, clicando nos ícones &quot;chevron&quot; esquerdos da página superior.

## Limitações {#section_F33C2EA27F2E417AA036BC199DD6C721}

**Recurso Mover**

Um elemento não pode ser movido para fora de um contêiner seguido por uma propriedade CSS.

**Somente ofertas de troca estão disponíveis em mboxes.**

Ações como Editar classe e Reorganizar não são permitidas dentro de uma mbox. O conteúdo da mbox é servido por mbox.js.

**Você não deve reorganizar e mover o mesmo elemento.**

Se um elemento tiver sido movido para outro local e você selecionar o contêiner pai e tentar reorganizar os elementos filho, o elemento movido não será afetado e permanecerá onde está. A reorganização talvez não apareça da maneira desejada.

**A ação de troca de imagem não funciona em uma Imagem no carrossel.**

Se, por exemplo, a sua página tiver um carrossel com seis imagens e você quiser trocar uma imagem pela segunda imagem do carrossel, a ação Trocar imagem não vai funcionar.

A solução é selecionar um contêiner principal e usar a ação Editar HTML para editar o HTML do carrossel, com o objetivo de atualizar a fonte de imagem da imagem desejada.

**As imagens não podem ser redimensionadas em uma mbox.**

Se você trocar uma imagem em um elemento de mbox, tente redimensionar essa imagem de acordo com o tamanho do elemento da mbox, o redimensionamento não será permitido.

**Depois que trocar uma imagem, você não poderá selecionar a ação Editar.**

Depois que trocar a imagem, você não poderá editar o URL do Scene7.

**Não é possível editar elementos HTML com a fonte externa.**

Por exemplo: vídeo, tags de áudio, incorporado, iFrames, quadros.

**O rastreamento de cliques não funciona para elementos de ancoragem que contenham qualquer coisa diferente de texto simples ou tags de imagem.**

Por exemplo, o rastreamento de cliques não funcionará se o elemento contiver JavaScript.

**As páginas devem aceitar os parâmetros de URL para que o Visual Experience Composer funcione.**

Alguns sites removem qualquer parâmetros de URL para as páginas. Entretanto, o Visual Experience Composer precisa desses parâmetros.

**Ao usar um script como parte do html, qualquer variável e função acessada da parte externa deve ser declarada no espaço de nome da janela.**

O script é executado dentro do escopo do target.js após a página carregar. Portanto, qualquer variável ou função que seja declarada localmente não está acessível da parte externa do bloco do script.

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

**Inserir uma imagem na Biblioteca de conteúdo (Scene7) e editar o HTML quebra o url da imagem.**

Adicione um elemento da âncora dentro do div &#39;customHeaderMessage&#39; com algum texto de teste:

```html
<a href="#"> 
<span> Dummy text </span>
</a>
```

Selecione esse div usando a ação Inserir elemento para inserir uma imagem como um irmão desse div de texto de teste.

Após a inserção da imagem, ele tem a seguinte aparência:

```html
<a href="#">  
<span> Dummy text </span> 
<img src=""> This is inserted Image. </img> 
</a>
```

Remova a extensão de texto de teste.

**A ação customCode no Visual Experience Composer não funciona com o Internet Explorer 8.**

Devido às limitações do IE8 ao manipular o conteúdo do script, a target.js não oferece suporte a isso no IE8. Como solução, se a página contiver jQuery e estiver exposta ao objeto window globalmente, a target.js pode usar para fornecer a ação customCode. Certifique-se de que window.jQuery e window.jQuery.fn.prepend estejam definidas.

**O rastreamento de cliques é compatível somente na página em que as experiências são criadas ou na página redirecionada.**

Embora o modo Navegar esteja disponível no VEC de rastreamento de cliques, ele não pode ser usado para adicionar o acompanhamento a uma página.
