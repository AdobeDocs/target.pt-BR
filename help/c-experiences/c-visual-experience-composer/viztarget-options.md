---
keywords: visual experience composer options;experience composer options;experience options;edit text;edit html;edit text/html;edit background color;background color;insert element;edit link;link;visual experience composer link;edit css class;css class;swap offer;offer swap;swap image;image swap;remove item;item remove;hide item;item hide;rearrange;move element;element move;resize element;element resize;element;expand selection;navigate to this link;navigate link;link navigate;navigate;link;undo;redo;undo/redo
description: Ao clicar em um elemento de página no Visual Experience Composer (VEC) do Adobe Target, um menu mostrará as opções disponíveis para esse tipo de elemento.
title: Opções do Visual Experience Composer (VEC) do Adobe Target
feature: vec
topic: Standard
uuid: efd672ae-c684-455f-8ec1-0efcfe1e9534
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '2404'
ht-degree: 95%

---


# Opções do Visual Experience Composer{#visual-experience-composer-options}

Ao clicar em um elemento de página no Visual Experience Composer (VEC), um menu mostrará as opções disponíveis para esse tipo de elemento. Além disso, um caminho DOM é exibido na parte inferior da página, possibilitando uma navegação fácil pela estrutura da página.

## Opções de VEC

As várias ações do Visual Experience Composer (VEC) são agrupadas nas opções de menu apropriadas para tornar sua tarefa mais rápida e eficiente:

![Menu de opções de VEC](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>As opções disponíveis dependem do tipo de atividade que você está editando.

### Editar

As opções disponíveis são as seguintes:

#### Texto/HTML {#edit-text-html}

Altere o código HTML do elemento, como o texto para uma área de texto, botão ou link.

Além do código HTML, você pode editar e injetar JavaScript personalizado.

Várias opções de formatação de rich text estão disponíveis durante a edição de texto e HTML para atividades de teste [!UICONTROL A/B] e [!UICONTROL Direcionamento de experiência]. Você pode escolher uma fonte, selecionar um estilo de fonte, alterar o alinhamento do texto e outras opções de formatação de texto padrão. Ao modificar o HTML, você pode alternar entre a exibição de código e a exibição de rich-editing do HTML.

As seguintes tags de HTML 5 podem ser aninhadas:

| Adicionar tag | Tags aninhadas permitidas |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

#### Cor do plano de fundo

Use o seletor de cores para selecionar ou configurar uma cor do fundo. Você pode selecionar uma amostra de cor e ajustá-la com valores de RGB ou códigos de cor hexadecimal. O x vermelho no seletor de cores torna o fundo transparente.

**Observação:** essa opção não está disponível para um elemento no qual uma imagem do fundo está definida.

#### Estilos  {#styles}

Use o painel [!UICONTROL Estilos] para exibir ou editar o valor dos estilos existentes para o elemento selecionado. Também é possível adicionar novos estilos.

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

O painel [!UICONTROL Estilos] é exibido no lado direito do VEC. O painel contém uma lista de estilos que permite editar ou adicionar ao elemento selecionado. Um Editor de CSS em tempo real permite exibir alterações e adicionar estilos se você estiver familiarizado com o uso de Folhas de estilo em cascata (CSS) ou se receber um código do desenvolvedor.

![Painel de estilos](/help/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

Ao aplicar estilos diferentes, sempre é possível reverter as alterações clicando no ícone [!UICONTROL Reverter], exibido no canto superior direito do painel [!UICONTROL Estilos], depois de fazer uma alteração em qualquer seção. Observe que clicar no ícone [!UICONTROL Reverter] reverte todas as alterações no painel da seção atual.

Expanda cada seção para editar ou adicionar estilos, conforme explicado abaixo. Para salvar as alterações, clique no ícone Voltar na parte superior do painel para retornar à tela principal do painel e clique em **[!UICONTROL Salvar]**.

Observe que os pontos azuis no painel principal e ao lado de cada opção nos vários painéis da seção indicam que você fez alterações nos estilos correspondentes. Isso facilita a análise das alterações antes de clicar em [!UICONTROL Salvar].

>[!NOTE]
>
>Ações rápidas para alterações de layout, cor de fundo, redimensionamento e mover também estão disponíveis como ações separadas no menu do VEC. Essas opções podem ser utilizadas como ações separadas ou você pode usar o menu Estilos, conforme explicado aqui.

* **Segundo plano**

   Altere a cor e a imagem do fundo.

   * Cor (especifique o código de cor ou use o seletor de cores)
   * Imagem (selecione uma imagem do seletor de imagens)
   * Fonte da imagem (especifique um URL externo)
   * Anexo
      * Clique na lista suspensa superior para selecionar rolagem, fixo ou local
      * Clique na lista suspensa inferior para selecionar repetir, repetir-x, repetir-y, sem repetição, espaçar ou arredondar
   * Clipe
      * Clique na lista suspensa superior para selecionar a caixa de borda, a caixa de preenchimento, a caixa de conteúdo ou o texto
      * Clique na lista suspensa inferior para selecionar o áudio automático ou o áudio

* **Tipografia**

   Altere a tipografia de um elemento. Edições de tipografia são rápidas e fáceis.

   Embora o editor de rich text (Editar Texto/HTML) esteja disponível para ajuste, as ações rápidas para fazer alterações ao elemento inteiro estão disponíveis por meio dessa opção. Se você quiser aplicar alterações de tipografia apenas a uma parte do texto (e não ao texto completo), use o [editor de rich text](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).

   É possível editar os seguintes estilos de tipografia:

   * Tamanho da fonte
   * Espessura da fonte
   * Estilo da fonte
   * Cor (especifique o código de cor ou use o seletor de cores)
   * Espaçamento entre palavras
   * Altura da linha
   * Alinhamento de texto

* **Margem**

   Altere a margem do elemento selecionado. Você pode alterar as margens esquerda, direita, inferior e superior.

   Clique no ícone suspenso de cada margem para escolher entre as seguintes opções:

   * Automático
   * Valor (arraste o controle deslizante para definir a margem ou especifique o número de pixels para cada margem)

   A margem suporta valores positivos e negativos.

   O Target também é compatível com outras unidades de tamanho, como rem, pc, em, etc. For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **Preenchimento**

   Altere o preenchimento do elemento selecionado. Você pode alterar o preenchimento esquerdo, direito, inferior e superior.

   Arraste o controle deslizante para definir o preenchimento ou especificar o número de pixels para o preenchimento.

   O preenchimento suporta escalas de largura a partir de 0.

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **Borda**

   Clique nos ícones de borda na parte superior do painel para alterar a borda do elemento selecionado.

   É possível editar os seguintes estilos para cada borda (superior, direita, inferior e esquerda):

   * Estilo da borda (nenhum, oculta, pontilhada, tracejada, sólida ou dupla)
   * Cor da borda (especifique o código de cor ou use o seletor de cores)
   * Largura da borda (arraste o controle deslizante para selecionar uma largura de borda ou especifique a largura em pixels)

   A borda suporta escalas de largura a partir de 0.

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **Position**

   Mova o elemento selecionado da posição atual. You can change the element&#39;s top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

   Clique na lista suspensa [!UICONTROL Estático] para escolher entre as seguintes opções de posição:

   * Estático
   * Relativo
   * Absoluto
   * Aderente
   * Fixo

   Clique no ícone suspenso de cada posição para escolher entre as seguintes opções:

   * Automático
   * Valor (arraste o controle deslizante para posicionar o elemento ou especifique o número de pixels que deseja mover o elemento)

   A posição suporta valores positivos e negativos.

   Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em, etc.

* **Tamanho**

   Altere a largura e a altura do elemento selecionado.

   Clique no ícone suspenso próximo à [!UICONTROL Largura] e [!UICONTROL Altura] para escolher entre as seguintes opções:

   * Automático
   * Valor (arraste o controle deslizante para dimensionar o elemento ou especifique o número de pixels para cada dimensão)

* **Filtro**

   Arraste o controle deslizante para cada opção de filtro ou especifique a porcentagem desejada:

   * Sépia
   * Contraste
   * Brilho
   * Escala de cinza
   * Desfoque
   * Opacidade
   * Inverter
   * Rotação de matiz
   * Saturar

* **Editor de CSS**

   O Editor de CSS em tempo real permite exibir alterações e adicionar estilos se você estiver familiarizado com o uso de Folhas de estilo em cascata (CSS) ou se receber um código do desenvolvedor.

   O Editor de CSS exibe todas as alterações feitas no painel Estilos. Conforme mostrado na ilustração abaixo, o tamanho da fonte, a borda superior e o tamanho da imagem foram alterados:

   ![Editor de CSS com alterações](/help/c-experiences/c-visual-experience-composer/assets/css-changes.png)

   Observe os pontos azuis ao lado das opções de [!UICONTROL Tipografia], [!UICONTROL Borda] e [!UICONTROL Tamanho] na ilustração anterior. Esses pontos indicam que você fez alterações nessas seções. Se você abrir esses painéis de seção, os pontos azuis serão exibidos ao lado das opções específicas alteradas.

   Você pode digitar seu próprio código se o estilo desejado não estiver disponível, por padrão, no painel [!UICONTROL Estilos].

   Observe que o Editor de CSS mostra somente os detalhes da sessão atual. Se você salvar as alterações e reabrir o editor, os detalhes sobre a alteração anterior não serão exibidos no editor, mesmo se o elemento for selecionado novamente.

   >[!IImportante]
   >
   >Você pode aplicar uma imagem de fundo usando o Editor de CSS, mas isso pode causar cintilação. Teste as alterações antes da implantação.

#### Classe CSS

Especifique a classe CSS usada para o elemento. Se mais de um elemento for selecionado, separe várias classes CSS com um espaço.

Disponível para atividades de [!UICONTROL A/B], [!UICONTROL personalização automatizada] e [!UICONTROL teste multivariado].

#### Link

Alterar o URL no link.

Use Editar link para atualizar o seletor para apontar para o mesmo elemento de imagem. No entanto, a vinculação com um elemento de imagem diferente não é compatível. Para vincular a um elemento de imagem diferente, exclua a ação original do editor de códigos e use o [!UICONTROL Visual Experience Composer] para aplicar a ação ao outro elemento de imagem.

### Inserir antes

As opções disponíveis são as seguintes:

#### Imagem, HTML e texto

Inclua qualquer tipo de elemento em sua página, além de modificar o conteúdo existente. Inclua texto, código, listas, entre outros, para criar experiências completamente diferentes para testar.

Selecione um elemento da página, clique em [!UICONTROL Inserir antes] e escolha se você quer inserir uma imagem, HTML ou texto. O elemento inserido aparece antes do elemento selecionado.

O comportamento do elemento inserido depende da estrutura da página, do CSS e de outras opções de configuração de página. É necessário um HTML válido para fazer página aparecer corretamente. Sempre teste sua página após inserir um item para garantir que ele apareça conforme esperado.

[!UICONTROL O Recommendations] oferece suporte para [!UICONTROL Inserir antes] do conteúdo das tags DIV, SECTION e ARTICLE.

**Observação:** para Inserir uma imagem, o [!DNL Adobe Scene7 Publishing System] deve estar habilitado para que você tenha acesso à biblioteca de imagens.

#### Recomendação

Inclua recomendações nas atividades de teste A/B (incluindo as atividades Autoalocação e Direcionamento automático) e Direcionamento de experiência (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragmento de experiência

Insira fragmentos de experiência criados em [!DNL Adobe Experience Manager] (AEM) nas atividades [!DNL Target] para auxiliar na otimização ou na personalização. Para obter mais informações, consulte [Fragmentos de experiência do AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Inserir depois de

As opções disponíveis são as seguintes:

#### Imagem, HTML e texto

Inclua qualquer tipo de elemento em sua página, além de modificar o conteúdo existente. Inclua texto, código, listas, entre outros, para criar experiências completamente diferentes para testar.

Selecione um elemento da página, clique em [!UICONTROL Inserir depois de] e escolha se você quer inserir uma imagem, HTML ou texto. O elemento inserido aparece após o elemento selecionado.

O comportamento do elemento inserido depende da estrutura da página, do CSS e de outras opções de configuração de página. É necessário um HTML válido para fazer página aparecer corretamente. Sempre teste sua página após inserir um item para garantir que ele apareça conforme esperado.

[!UICONTROL O Recommendations] oferece suporte para [!UICONTROL Inserir antes] do conteúdo das tags DIV, SECTION e ARTICLE.

**Observação:** para Inserir uma imagem, o [!DNL Adobe Scene7 Publishing System] deve estar habilitado para que você tenha acesso à biblioteca de imagens.

#### Recomendação

Inclua recomendações nas atividades de teste A/B (incluindo as atividades Autoalocação e Direcionamento automático) e Direcionamento de experiência (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragmento de experiência

Insira fragmentos de experiência criados em [!DNL Adobe Experience Manager] (AEM) nas atividades [!DNL Target] para auxiliar na otimização ou na personalização. Para obter mais informações, consulte [Fragmentos de experiência do AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Substituir com

As opções disponíveis são as seguintes:

#### Imagem

Selecione uma imagem diferente da Biblioteca de conteúdo. As imagens disponíveis para troca incluem aquelas carregadas na pasta de ativos da Experience Cloud ou na Biblioteca de conteúdo do Target.

Durante a criação da atividade inicial, o URL exibido não é o URL usado para a entrega. Após a sincronização da atividade, esse URL é atualizado para um URL de produto do Scene7.

Por exemplo, o URL inicial pode se parecer com o seguinte exemplo:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Após a sincronização da atividade, o URL de entrega pode ser parecido com o seguinte exemplo:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

O Recommendations suporta a opção &quot;Substituir por&quot; nas tags DIV, SECTION e ARTICLE.

**Observação:** a troca de imagens exige uma conta do sistema de publicação do Adobe Scene7.

#### Oferta HTML

Selecione uma oferta diferente da [!UICONTROL Biblioteca de conteúdo].

**Observação:** ofertas de HTML são armazenadas em servidores do [!DNL Target].

Uma oferta de HTML pode ter até 256 KB.

#### Recomendação

Inclua recomendações nas atividades de teste A/B (incluindo as atividades Autoalocação e Direcionamento automático) e Direcionamento de experiência (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md).

#### Fragmento de experiência

Insira fragmentos de experiência criados em [!DNL Adobe Experience Manager] (AEM) nas atividades [!DNL Target] para auxiliar na otimização ou na personalização. Para obter mais informações, consulte [Fragmentos de experiência do AEM](/help/c-experiences/c-manage-content/aem-experience-fragments.md).

### Layout

As opções disponíveis são as seguintes:

#### Reorganizar

Arraste o elemento para outro local no mesmo elemento pai ou DIV. Outros elementos trocam de local para abrir espaço para o elemento reorganizado.

**Observação:** clicar no rastreamento de cliques não funciona em itens reorganizados.

#### Redimensionar

Redimensionar um elemento na página. Ao selecionar [!UICONTROL Redimensionar], uma alça, que permite arrastar o canto para dimensionar, aparece no canto inferior direito do elemento. Segure a tecla Shift para manter a mesma proporção.

**Observação:** elementos em linha não podem ser redimensionados.

#### Mover  {#move}

Mover elementos na página. Diferentemente da opção [!UICONTROL Reorganizar], [!UICONTROL Mover] não altera a posição de outros elementos para abrir espaço para o elemento que está sendo movido. Use as teclas de seta para ajustar o movimento. (Aprimoramento planejado: suporte para garantir que os elementos movidos não estejam ocultos atrás de outros elementos.)

Em alguns casos, como quando uma restrição CSS requer que um elemento permaneça dentro do elemento pai, você não pode mover o elemento para fora dele. Um elemento não pode ser movido para fora de um container que tenha a seguinte propriedade CSS: `overflow: hidden`.

#### Ocultar

Ocultar o elemento. O espaço em branco permanece, mas o conteúdo é removido.

#### Remover

Remova o elemento. O espaço em branco atrás da imagem é removido e o espaço onde o elemento estava é recolhido.

**Observação:** os itens de uma mbox &quot;clássica&quot; (uma mbox criada em uma campanha do Target Classic) não podem ser removidos usando esta opção.

### Expandir seção

Selecione o elemento pai, além do elemento selecionado originalmente. Ao selecionar qualquer elemento pai, todos os filhos desse elemento serão selecionados automaticamente. Você pode expandir a seleção várias vezes.

### Navegar para o link

Abra o destino do link.

### Desfazer/Refazer

Desfaça as alterações feitas em suas atividades durante uma sessão de alteração. Você também pode refazer alterações que foram desfeitas anteriormente.

## Considerações {#considerations}

* Se uma oferta inclui conteúdo HTML, consulte “Como o at.js renderiza ofertas com conteúdo HTML” em [Como o at.js funciona](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md#render), para obter mais informações.

## Navegar pelos elementos usando o caminho DOM {#dom-path}

Ao clicar em um elemento na página, o menu de opções de VEC é exibido. Além disso, ao clicar em um elemento, o caminho DOM correspondente é exibido na parte inferior da página.

![Caminho DOM](/help/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Você pode usar o caminho DOM para ver rapidamente as informações sobre o elemento selecionado (tipo, ID e classe) e mover para cima ou para baixo o caminho DOM para selecionar o elemento desejado.

Quando você passa o mouse sobre o caminho DOM, uma caixa azul destaca o elemento correspondente no VEC. Quando você clica no elemento, uma caixa laranja destaca o elemento e o menu de opções do VEC é exibido, conforme explicado acima.

É possível navegar com facilidade em qualquer elemento pai, irmão ou filho do VEC usando o caminho DOM.

O recurso de caminho DOM também está disponível ao configurar o [rastreamento de cliques](/help/c-activities/r-success-metrics/click-tracking.md).