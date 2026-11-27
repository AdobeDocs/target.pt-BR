---
keywords: visual experience composer; práticas recomendadas do visual experience composer; limitações do visual experience composer; avisos do visual experience composer; práticas recomendadas do vec; vec
description: Conheça as práticas recomendadas para que suas experiências funcionem conforme o esperado ao usar o [!UICONTROL Visual Experience Composer] (VEC).
title: Quais são as práticas recomendadas e as limitações do [!UICONTROL Visual Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: cf51bfec-d7fa-4ec1-a5dc-35edefefd3e4
TQID: 'https://experienceleague.adobe.com/upZDSyuS9VqUmYskNXrlYazhwRHmZGBpSR-cR-qliRs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
subfeature_v2:
  - id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
    internal-label: at.js
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '2420'
ht-degree: 8%
---
# Práticas recomendadas e limitações do [!UICONTROL Visual Experience Composer] {#vec-best-practices}

>[!BEGINSHADEBOX]

**Nesta página:** conheça as práticas recomendadas, os avisos e as limitações a serem observadas ao criar experiências no **[!UICONTROL Visual Experience Composer]** (VEC).

>[!ENDSHADEBOX]

Seguir essas práticas ajuda as experiências criadas no [!DNL Adobe Target] **[!UICONTROL Visual Experience Composer]** (VEC) a funcionar conforme o esperado. As limitações e advertências descrevem comportamentos que podem causar problemas comuns, portanto, conhecê-los ajuda a evitar problemas e a manter o desempenho.

## Práticas recomendadas {#best-practices}

As práticas a seguir se aplicam ao usar o VEC.

### Habilitar o [!UICONTROL Enhanced Experience Composer] {#enable-eec}

O **[!UICONTROL Enhanced Experience Composer]** pode ser ativado no nível da conta, o que o habilita para todas as atividades criadas na conta, ou no nível da atividade individual.

* **Nível da conta:** Clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]** e alterne a opção **[!UICONTROL Habilitar Enhanced Experience Composer]** para a posição Ligado.
* **Nível de atividade:** ao criar uma atividade no **[!UICONTROL Visual Experience Composer]**, clique em **[!UICONTROL Configurar]** > **[!UICONTROL Entrega de página]** e alterne o switch **[!UICONTROL Habilitar Enhanced Experience Composer]** para a posição Ligado.

### Configuração e carregamento de página

+++ Coloque a referência à at.js na parte superior da seção `<head>` da página.

Se o **[!UICONTROL Serviço de API do visitante]** também for usado, coloque o script de API do visitante acima da at.js.

+++

+++ Inclua na lista de permissões os endereços IP se o [!UICONTROL Enhanced Experience Composer] não carregar em páginas seguras do site.

O Incluir na lista de permissões dos endereços IP dos servidores [!DNL Adobe] usados para o proxy do **[!UICONTROL Enhanced Experience Composer]** resolve problemas de carregamento. Esses endereços IP são necessários somente para a edição de atividades. Os visitantes do site não precisam deles para acessar o site. Os endereços IP estão listados em [O EEC não carregará uma URL de controle de qualidade interna que não esteja acessível no IP público](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshooting-issues-related-to-the-enhanced-experience-composer-eec.md#eec-ip-addresses) em *Solucionando problemas relacionados ao Enhanced Experience Composer*.

+++

+++ Não use a base da tag no site para resolver URLs e links.

O VEC, incluindo o **[!UICONTROL Enhanced Experience Composer]**, manipula o site em segundo plano por meio de um servidor proxy que atualiza todas as URLs de link para que funcionem no proxy. Se uma tag base for adicionada, o navegador resolverá esses URLs novamente, para que pareçam corrompidos.

+++

+++ Não use as variáveis `top` ou `self` no código JavaScript.

Quando o **[!UICONTROL Enhanced Experience Composer]** está habilitado, os valores das variáveis `top` e `self` são atualizados para desabilitar a edição do iframe. Use um cabeçalho X-Frame-Options para adicionar a edição do iframe, em vez do código JavaScript personalizado.

+++

+++ Sempre teste o site se os parâmetros são adicionados quando a página é carregada.

Por exemplo, os seguintes parâmetros de URL são usados para abrir o `www.abc.com` para edição em um iframe:

`www.abc.com?mboxEdit=1&mboxDisable=1`

Certifique-se de que o site seja carregado conforme esperado depois de adicionar parâmetros como esses.

+++

+++ Certifique-se de que a página abra conforme esperado em um iframe.

Desative as técnicas de interrupção de iframe no site e verifique se o site abre como esperado em um iframe em uma página de teste. Por exemplo:

```html
<!DOCTYPE html>
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

### Marcação de página

+++ Use IDs exclusivas para elementos de nível superior e para quaisquer outros elementos que sejam bons candidatos a teste ou direcionamento.

Qualquer coisa imediatamente dentro do elemento do corpo deve ter uma ID exclusiva, para que pelo menos os elementos principais sejam fáceis de reconhecer quando novos elementos são inseridos no corpo e o código se move.

[!DNL Target] não requer IDs, mas as IDs aumentam a confiabilidade das experiências criadas com o compositor de experiências. [!DNL Target] usa seletores de CSS para modificar o conteúdo quando a experiência é entregue. Quando uma experiência é editada, o **[!UICONTROL Visual Experience Composer]** ancora o seletor ao ancestral mais próximo do elemento HTML modificado que tenha um atributo de ID não nulo. Portanto, não é aconselhável usar nenhum mecanismo, incluindo bibliotecas JavaScript, que defina ou modifique atributos da HTML ID. Essas IDs podem estar disponíveis para o compositor de experiência quando a atividade é criada, mas se o JavaScript as modificar, a ID usada na criação pode não estar disponível quando a experiência é executada. Se uma ID não estiver disponível, o seletor ancorado a essa ID falhará.

+++

+++ Use nomes de classe CSS descritivos.

Nomes de classe descritivos facilitam a identificação das classes quando as classes CSS são editadas no **[!UICONTROL Visual Experience Composer]**. Isso ajuda a garantir que as classes CSS certas sejam editadas e que as páginas sejam exibidas conforme esperado.

+++

+++ Não use a propriedade CSS `!important` ao ocultar ou remover elementos.

Se a propriedade CSS `!important` estiver presente, as regras CSS do site substituirão as alterações feitas por `target.js` durante a entrega.

+++

+++ Evite tabelas do HTML para layouts de página.

O [!DNL Target] usa o JavaScript para formatar uma página, e os layouts baseados em tabela são difíceis de modificar com o JavaScript. Os layouts baseados em tabela também podem não ser exibidos da mesma forma em todos os navegadores. Para obter os melhores resultados, use CSS para criar layouts de página.

+++

+++ Reduza o uso de iFrames.

A minimização de iFrames simplifica o gerenciamento de páginas e testes. O **[!UICONTROL Visual Experience Composer]** pode aplicar algumas ações em um iFrame, mas algumas ações, como redimensionamento, não funcionam corretamente. As páginas que usam vários iFrames são difíceis de gerenciar e redimensionar, portanto, testar páginas com iFrame excessivo pode criar problemas.

+++

+++ Use somente texto simples ou uma tag de imagem em elementos de ancoragem.

Um elemento âncora contém texto simples:

`<a>Anchor Text</a>`

ou uma tag de imagem:

`<a href=""> <img src=""> </img> </a>`

+++

+++ Evite elementos de nível de bloco dentro de um elemento em linha.

Os elementos de nível de bloco não devem ser usados dentro de elementos em linha, como elementos de ancoragem e extensão. Isso faz com que os elementos em linha percam sua altura e largura, de modo que a ferramenta de sobreposição no **[!UICONTROL Visual Experience Composer]** pode não funcionar conforme esperado.

+++

+++ Tenha cuidado ao remover campos de formulário.

Alguns campos de formulário podem ser obrigatórios para envio, portanto, sua remoção pode afetar os envios.

+++

+++ Mantenha um texto importante que possa ser usado para direcionamento no código HTML dentro de um elemento.

Por exemplo, o texto do Carrinho de compras não poderá ser direcionado no VEC se o código for como o seguinte:

```html
<a href="https://www.botanicchoice.com/shop.axd/Cart">
   <img alt="Shopping Cart" src="/images/ico-cart.gif"></img>
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

### Edição e entrega

+++ Organize todas as modificações de DOM dinâmicas assim que possível depois que o DOM estiver pronto.

Se as modificações não forem aplicadas antes de `target.js` aplicar a experiência, a entrega de conteúdo poderá ser interrompida. Isso acontecerá somente quando houver uma alteração de DOM na hierarquia de um elemento direcionado.

+++

+++ Usar Editar HTML para manipular a estrutura DOM pode quebrar os seletores.

Por exemplo, duas ações são executadas:

* Uma classe é adicionada ao Elemento 1.
* O HTML do Elemento 1 é editado.

Cada alteração cria um novo elemento no VEC. A segunda ação modifica o Elemento 1; portanto, se o Elemento 1 for excluído, a segunda ação não terá mais nada para modificar e a alteração não funcionará mais.

Da mesma forma, se um elemento for adicionado com texto e uma ação separada, então, editar esse elemento com um texto diferente, o editor de código mostrará ambas as ações como elementos separados. A edição cria um novo elemento que modifica o original e contém o texto editado. Se o elemento original for excluído, o texto editado não poderá encontrar o elemento a ser modificado e não será exibido. O segundo elemento permanece na lista de elementos, mas não tem efeito na página porque o elemento alterado não existe mais.

Consulte [Seletores de elementos usados no **[!UICONTROL Visual Experience Composer]**](/help/main/c-experiences/c-visual-experience-composer/vec-selectors.md#vec-selectors).

+++

+++ Use as marcas `<b>` e `<i>` ao estilizar elementos de texto com o editor de rich text.

* Para texto em negrito, use `<b>` em vez de `<strong>`.
* Para texto em itálico, use `<i>` em vez de `<em>`.

As marcas `<strong>` e `<em>` podem causar resultados inesperados.

+++

+++ Não inclua `mboxCreate` em scripts.

`mboxCreate` usa `document.write`, portanto, não é recomendado incluí-lo em scripts. Use `mboxDefine` e `mboxUpdate` para a mesma finalidade.

+++

+++ Não atualize um trecho HTML com [!DNL Target] se o trecho exigir código JavaScript para a inicialização.

Quando uma ação (Editar HTML) é executada em componentes da página, como controles deslizantes e carrosséis, a entrega pode parecer interrompida. O VEC executa a ação depois que o JavaScript instancia o componente de página. No entanto, quando o conteúdo da página é entregue aos visitantes, a ação é aplicada antes que o componente seja instanciado. Como resultado, a funcionalidade do componente pode ou não ser interrompida no delivery, dependendo do script que define o componente na página.

Um teste de delivery que funciona pela primeira vez não garante que o delivery continue a funcionar, pois uma condição de corrida pode existir:

* Se houver uma condição de corrida, a entrega funciona intermitentemente.
* Se não houver condição de corrida, a entrega sempre funcionará.

Teste a página várias vezes para garantir que o delivery funcione conforme esperado.

+++

## Avisos {#caveats}

Os avisos a seguir se aplicam ao usar o **[!UICONTROL Visual Experience Composer]** para criar uma atividade.

+++ O recurso [!UICONTROL Move] não oferece suporte ao índice z.

Sem a funcionalidade do índice z, um elemento movido não pode ser colocado sobre outro elemento. Consulte [Limitações](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721) para obter mais detalhes.

+++

+++ A reorganização dos elementos afeta o rastreamento de cliques.

Se um elemento marcado para rastreamento de cliques for reorganizado, os caminhos dos elementos reorganizados serão alterados. Como resultado, os cliques são rastreados no elemento no local em que o elemento original estava antes de ser reorganizado.

Isso ocorre porque o código que entrega o conteúdo da atividade e o código que rastreia os cliques são incluídos em uma parte do código entregue à página. Se uma página diferente for navegada para e o rastreamento de cliques for configurado lá, ambas as partes do código serão entregues a essa página. Se a página de rastreamento de cliques tiver uma estrutura de página semelhante à da página em que o teste é executado, o conteúdo do teste também poderá aparecer na página de rastreamento de cliques.

+++

+++ A inserção de um elemento pode não funcionar em um `<div>` que seja uma mbox.

Se uma mbox contiver uma oferta e ela for implementada incorretamente, um elemento inserido poderá aparecer como `insertBefore` e não como `insertAfter`.

+++

+++ Ao editar um elemento pai e um elemento filho, edite o pai primeiro.

Se uma ação de imagem for trocada em um elemento e o texto ou o HTML do elemento principal for editado, podem ocorrer problemas de entrega. O melhor fluxo de trabalho é editar o elemento principal antes de trocar a imagem no elemento secundário.

+++

+++ Não selecione um elemento de página que inclua uma mbox como um elemento secundário.

Por exemplo, se a página contiver o seguinte código:

```html
<div>
  <div class="mboxDefault" >
  </div>
  <script>mboxCreate('myMbox');
</script>
</div>
```

A div externa não deve ser selecionada em uma experiência, pois a mbox codificada na página ainda faz uma chamada para [!DNL Target] e recebe uma resposta. Essa resposta interfere na resposta pretendida para o elemento de página maior.

+++

+++ Endereços IP proxy podem ser bloqueados no ambiente do cliente.

Se o **[!UICONTROL Enhanced Experience Composer]** for usado em um site sem transmissão ao vivo, como um ambiente de preparo, erros de tempo limite e acesso negado poderão ocorrer se o site bloquear os endereços IP de proxy.

+++

## Limitações {#section_F33C2EA27F2E417AA036BC199DD6C721}

As limitações a seguir se aplicam ao trabalhar com o VEC.

### Requisitos da página

+++ Manipular compatibilidade do VEC com [!DNL Chrome] alterações na política de extensão.

Nas políticas atualizadas do Manifesto [V3 no Google Chrome](https://developer.chrome.com/docs/extensions/develop/migrate/what-is-mv3){target=_blank}, as extensões não podem mais modificar o DOM original antes que o navegador o analise. Como resultado, determinados scripts de segurança, como implementações de edição de iframe, podem bloquear o carregamento de páginas no VEC.

Para garantir a compatibilidade, desabilite condicionalmente esses scripts quando a página for carregada dentro do iframe [!DNL Target]. Isso pode ser feito com segurança verificando a presença do objeto `window.adobeVecExtension`, que [!DNL Target] injeta enquanto o VEC é carregado.

Os trechos de código a seguir são exemplos de código iframe-busting que podem impedir que uma página da Web seja carregada no VEC:

`window.top.location = window.self.location;`

`top.location.href = self.location.href;`

Uma verificação simples pode verificar quando uma página da Web é inserida dentro de [!DNL Target]. O trecho de código tem esta aparência:

```
if(!window.adobeVecExtension) {
    // additional security logic
}
```

+++

+++ As páginas devem aceitar os parâmetros de URL para que o VEC funcione.

Alguns sites removem quaisquer parâmetros de URL de suas páginas, mas o VEC exige esses parâmetros.

+++

+++ Quando um script for usado como parte do HTML, declare todas as variáveis e funções acessadas de fora no namespace da janela.

O script é executado no escopo de `target.js` depois que a página é carregada, portanto, qualquer variável ou função declarada localmente não pode ser acessada de fora do bloco de script.

*Incorreto:*

```html
<script>
  var myVar = 123;
  function myFunc() {
    //
  }
</script>
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

+++ A ação `customCode` no VEC não funciona com [!DNL Internet Explorer] 8.

O `target.js` não dá suporte a esta ação no IE8 devido a limitações do IE8 ao manipular conteúdo de script. Como solução, se a página contiver jQuery e jQuery estiver exposta globalmente no objeto da janela, `target.js` poderá fornecer a ação `customCode`. Verifique se `window.jQuery` e `window.jQuery.fn.prepend` estão definidos.

+++

### Reorganização e mboxes

**Um elemento não pode ser movido para fora de um contêiner seguido por uma propriedade CSS.**

+++ O elemento [!UICONTROL Button] não pode ser selecionado para reorganização.

Os elementos **[!UICONTROL Button]** não podem ser selecionados diretamente para reorganização. Para habilitar a reorganização, coloque os botões dentro de um contêiner maior.

+++

+++ Não reorganize e mova o mesmo elemento.

Se um elemento tiver sido movido para outro local e o contêiner pai for selecionado para reorganizar os elementos filho, o elemento movido não será afetado e permanecerá onde está. A reorganização talvez não apareça da maneira desejada.

+++

+++ Somente ofertas de troca estão disponíveis em mboxes.

Ações como **[!UICONTROL Editar classe]** e **[!UICONTROL Reorganizar]** não são permitidas dentro de uma mbox.

+++

### Imagens

+++ A ação [!UICONTROL Alterar imagem] não funciona em uma imagem no carrossel.

Por exemplo, se a página contiver um carrossel com seis imagens e uma imagem precisar ser trocada pela segunda imagem do carrossel, a ação **[!UICONTROL Alterar imagem]** não funcionará.

Como solução alternativa, selecione o contêiner pai e use a ação **[!UICONTROL Editar HTML]** para editar a HTML do carrossel e atualizar a fonte de imagem da imagem desejada.

+++

+++ As imagens não podem ser redimensionadas em uma mbox.

Se uma imagem for trocada em um elemento da mbox e redimensionada de acordo com o tamanho do elemento da mbox, o redimensionamento não será permitido.

+++

+++ Depois que uma imagem é trocada, a ação [!UICONTROL Editar] não pode ser selecionada.

Depois que a imagem é trocada, o URL do Scene7 não pode ser editado.

+++

+++ Inserir uma imagem na biblioteca de [!UICONTROL Conteúdo] (Scene7) e editar o HTML quebra a URL da imagem.

Adicione um elemento de âncora dentro da div `customHeaderMessage` com algum texto fictício:

```html
<a href="#">
<span> Dummy text </span>
</a>
```

Selecione esta div usando a ação **[!UICONTROL Inserir Elemento]** para inserir uma imagem como irmã do texto fictício.

Depois que a imagem é inserida, o código tem esta aparência:

```html
<a href="#">
<span> Dummy text </span>
<img src=""> This is inserted Image. </img>
</a>
```

Remova a extensão de texto de teste.

+++

### Rastreamento de cliques e conteúdo externo

+++ O rastreamento de cliques não funciona para elementos de ancoragem que contenham qualquer coisa diferente de texto simples ou tags de imagem.

Por exemplo, o rastreamento de cliques não funcionará se o elemento contiver JavaScript.

+++

+++ O rastreamento de cliques é compatível somente na página em que as experiências são criadas ou na página redirecionada.

Embora o modo **[!UICONTROL Procurar]** esteja disponível para rastreamento de cliques no VEC, o modo **[!UICONTROL Procurar]** não pode ser usado para adicionar o rastreamento de cliques em uma página.

+++

+++ Os elementos do HTML com uma fonte externa não podem ser editados.

Por exemplo: vídeo, tags de áudio, código incorporado, iFrames e quadros.

+++
