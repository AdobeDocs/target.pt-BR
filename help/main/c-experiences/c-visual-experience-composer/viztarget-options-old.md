---
keywords: opções do visual experience composer;opções do visual experience composer;opções de experiência;editar texto;editar html;editar texto/html;editar cor de fundo;cor de fundo;inserir elemento;editar link;link;link do visual experience composer;editar classe css;classe css;trocar oferta;troca de oferta;trocar imagem;troca de imagem;remover item;item remover;ocultar item;ocultação de item;reorganizar;mover elemento;elemento mover;redimensionar elemento;elemento redimensionar;elemento;expandir seleção;navegar até este link;navegar no link;navegar;link;navegar;desfazer;refazer/refazer;eventos personalizados;componentes da web;decisão de oferta;offer decisioning
description: Explore as opções disponíveis no  [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).
title: Como faço para usar as Opções do [!UICONTROL Visual Experience Composer] (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: be9996c4dce0a3135a39fcbf0608b57b6e742ac3
workflow-type: tm+mt
source-wordcount: '2667'
ht-degree: 55%

---

# Opções do Visual Experience Composer

Ao clicar em um elemento de página no [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC), um menu mostrará as opções disponíveis para esse tipo de elemento. Além disso, um caminho DOM é exibido na parte inferior da página, possibilitando uma navegação fácil pela estrutura da página.

As várias ações do [!UICONTROL Visual Experience Composer] (VEC) são agrupadas nas opções de menu apropriadas para tornar seu trabalho mais rápido e eficiente:

![Menu de opções de VEC](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/vec-options.png)

>[!NOTE]
>
>As opções disponíveis dependem do tipo de atividade que você está criando ou editando.

## [!UICONTROL Edit]

As opções disponíveis são as seguintes:

### [!UICONTROL Text/HTML] {#edit-text-html}

Altere o código HTML do elemento, como o texto para uma área de texto, botão ou link.

Além do código HTML, você pode editar e injetar JavaScript personalizado.

Várias opções de formatação de rich text estão disponíveis durante a edição de texto e HTML para atividades de [!UICONTROL A/B] e [!UICONTROL Experience Targeting]. Você pode escolher uma fonte, selecionar um estilo de fonte, alterar o alinhamento do texto e outras opções de formatação de texto padrão. Ao modificar o HTML, você pode alternar entre a exibição de código e a exibição de rich-editing do HTML.

As seguintes tags de HTML 5 podem ser aninhadas:

| Adicionar tag | Tags aninhadas permitidas |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

### [!UICONTROL Background Color]

Use o seletor de cores para selecionar ou configurar uma cor do fundo. Você pode selecionar uma amostra de cor e ajustá-la com valores de RGB ou códigos de cor hexadecimal. O x vermelho no seletor de cores torna o fundo transparente.

**Observação:** essa opção não está disponível para um elemento no qual uma imagem do fundo está definida.

### [!UICONTROL Styles] {#styles}

Use o painel [!UICONTROL Styles] para exibir ou editar o valor dos estilos existentes para o elemento selecionado. Também é possível adicionar novos estilos.

Para acessar o painel [!UICONTROL Styles], clique em um elemento de página no VEC e em **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

O painel [!UICONTROL Styles] é exibido no lado direito do VEC. O painel contém uma lista de estilos que permite editar ou adicionar ao elemento selecionado. Um Editor de CSS em tempo real permite exibir alterações e adicionar estilos se você estiver familiarizado com o uso de Folhas de estilo em cascata (CSS) ou se receber um código do desenvolvedor.

![Painel de estilos](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

Ao aplicar estilos diferentes, sempre é possível reverter as alterações clicando no ícone [!UICONTROL Revert], exibido no canto superior direito do painel [!UICONTROL Styles], depois de alterar qualquer seção. Clicar no ícone [!UICONTROL Revert] reverte todas as alterações no painel da seção atual.

Expanda cada seção para editar ou adicionar estilos, conforme explicado abaixo. Para salvar as alterações, clique no ícone [!UICONTROL Back] na parte superior do painel para retornar à exibição principal do painel e clique em **[!UICONTROL Save]**.

Pontos azuis no painel principal e ao lado de cada opção nos vários painéis da seção indicam que você alterou os estilos correspondentes. Este indicador visual facilita a análise das alterações antes de clicar em [!UICONTROL Save].

>[!NOTE]
>
>Ações rápidas para alterações de layout, cor de fundo, redimensionamento e mover também estão disponíveis como ações separadas no menu do VEC. Essas opções podem ser usadas como ações separadas ou você pode usar o menu Estilos, conforme explicado aqui.

* **[!UICONTROL Background]**

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

* **[!UICONTROL Typography]**

  Altere a tipografia de um elemento. Edições de tipografia são rápidas e fáceis.

  Embora o editor de rich text (Editar Texto/HTML) esteja disponível para ajuste, as ações rápidas para alterar todo o elemento estão disponíveis por meio dessa opção. Se você quiser aplicar alterações de tipografia apenas a uma parte do texto (e não ao texto completo), use o [editor de rich text](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md).

  É possível editar os seguintes estilos de tipografia:

   * [!UICONTROL Font size]
   * [!UICONTROL Font weight]
   * [!UICONTROL Font style]
   * [!UICONTROL Color] (especifique o código de cor ou use o seletor de cores)
   * [!UICONTROL Word spacing]
   * [!UICONTROL Line height]
   * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Altere a margem do elemento selecionado. Você pode alterar as margens esquerda, direita, inferior e superior.

  Clique no ícone suspenso de cada margem para escolher entre as seguintes opções:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (arraste o controle deslizante para definir a margem ou especifique o número de pixels para cada margem)

  A margem suporta valores positivos e negativos.

  O Target também é compatível com outras unidades de tamanho, como rem, pc, em. Para obter mais informações sobre essas unidades, consulte [Dicas e truques de CSS e Folhas de Estilo da Web](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Altere o preenchimento do elemento selecionado. Você pode alterar o preenchimento esquerdo, direito, inferior e superior.

  Arraste o controle deslizante para definir o preenchimento ou especificar o número de pixels para o preenchimento.

  O preenchimento suporta escalas de largura a partir de 0.

  O Target também oferece suporte a [outras unidades de tamanho](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em.

* **[!UICONTROL Border]**

  Clique nos ícones de borda na parte superior do painel para alterar a borda do elemento selecionado.

  É possível editar os seguintes estilos para cada borda (superior, direita, inferior e esquerda):

   * [!UICONTROL Border style] (nenhum, oculto, pontilhado, tracejado, sólido ou duplo)
   * [!UICONTROL Border color] (especifique o código de cor ou use o seletor de cores)
   * [!UICONTROL Border width] (arraste o controle deslizante para selecionar uma largura de borda ou especifique a largura em pixels)

  A borda suporta escalas de largura a partir de 0.

  O Target também oferece suporte a [outras unidades de tamanho](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em.

* **[!UICONTROL Position]**

  Mova o elemento selecionado da posição atual. Você pode alterar a posição superior, inferior, esquerda, direita e [índice Z](https://www.w3schools.com/cssref/pr_pos_z-index.asp) do elemento.

  Clique na lista suspensa [!UICONTROL Static] para escolher entre as seguintes opções de posição:

   * [!UICONTROL Static]
   * [!UICONTROL Relative]
   * [!UICONTROL Absolute]
   * [!UICONTROL Sticky]
   * [!UICONTROL Fixed]

  Clique no ícone suspenso de cada posição para escolher entre as seguintes opções:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (arraste o controle deslizante para posicionar o elemento ou especifique o número de pixels que deseja mover o elemento)

  A posição suporta valores positivos e negativos.

  O Target também oferece suporte a [outras unidades de tamanho](https://www.w3.org/Style/Examples/007/units.en.html), como rem, pc, em.

* **[!UICONTROL Size]**

  Altere a largura e a altura do elemento selecionado.

  Clique no ícone suspenso ao lado de [!UICONTROL Width] e [!UICONTROL Height] para escolher entre as seguintes opções:

   * [!UICONTROL Auto]
   * [!UICONTROL Value] (arraste o controle deslizante para dimensionar o elemento ou especifique o número de pixels para cada dimensão)

* **[!UICONTROL Filter]**

  Arraste o controle deslizante para cada opção de filtro ou especifique a porcentagem desejada:

   * [!UICONTROL Sepia]
   * [!UICONTROL Contrast]
   * [!UICONTROL Brightness]
   * [!UICONTROL GrayScale]
   * [!UICONTROL Blur]
   * [!UICONTROL Opacity]
   * [!UICONTROL Invert]
*[!UICONTROL &#x200B; Hue-rotate]
   * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  O Editor de CSS em tempo real permite exibir alterações e adicionar estilos se você estiver familiarizado com o uso de Folhas de estilo em cascata (CSS) ou se receber um código do desenvolvedor.

  O Editor de CSS exibe todas as alterações feitas no painel Estilos. Conforme mostrado na ilustração abaixo, o tamanho da fonte, a borda superior e o tamanho da imagem foram alterados:

  ![Editor de CSS com alterações](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Observe os pontos azuis ao lado das opções [!UICONTROL Typography], [!UICONTROL Border] e [!UICONTROL Size] na ilustração anterior. Esses pontos indicam que você alterou essas seções. Se você abrir esses painéis de seção, os pontos azuis serão exibidos ao lado das opções específicas alteradas.

  Você pode digitar seu próprio código se o estilo desejado não estiver disponível, por padrão, no [!UICONTROL Styles].

  O Editor de CSS mostra somente os detalhes da sessão atual. Se você salvar as alterações e reabrir o editor, os detalhes sobre a alteração anterior não serão exibidos no editor, mesmo se o elemento for selecionado novamente.

  >[!IMPORTANT]
  >
  >Você pode aplicar uma imagem de fundo usando o Editor de CSS, mas isso pode causar cintilação. Teste as alterações antes da implantação.

### [!UICONTROL CSS Class]

Especifique a classe CSS usada para o elemento. Se mais de um elemento for selecionado, separe várias classes CSS com um espaço.

Disponível para atividades de [!UICONTROL A/B], [!UICONTROL Automated Personalization] e [!UICONTROL Multivariate Test].

### [!UICONTROL Link]

Alterar o URL no link.

Use Editar link para atualizar o seletor para apontar para o mesmo elemento de imagem. No entanto, a vinculação com um elemento de imagem diferente não é compatível. Para vincular a um elemento de imagem diferente, exclua a ação original do editor de código e use o [!UICONTROL Visual Experience Composer] para aplicar a ação no outro elemento de imagem.

## [!UICONTROL Insert Before]

As opções disponíveis são as seguintes:

### [!UICONTROL Offer Decision]

Adicione uma [oferta criada em [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} para apresentar a melhor oferta e experiência aos seus clientes usando o offer decisioning.

**Observação:** esta opção está disponível somente durante a edição ou criação das atividades [manuais [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) ou [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT). Essa opção não está disponível para outros tipos de atividade.

Para obter mais informações, consulte [Usar decisões de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML] e [!UICONTROL Text]

Inclua qualquer tipo de elemento em sua página, além de modificar o conteúdo existente. Inclua texto, código, listas, entre outros, para criar experiências completamente diferentes para testar.

Selecione um elemento da página, clique em [!UICONTROL Insert Before] e escolha se você quer inserir uma imagem, HTML ou texto. O elemento inserido aparece antes do elemento selecionado.

O comportamento do elemento inserido depende da estrutura da página, do CSS e de outras opções de configuração de página. É necessário um HTML válido para fazer página aparecer corretamente. Sempre teste sua página após inserir um item para garantir que ele apareça conforme esperado.

[!UICONTROL Recommendations] dá suporte a [!UICONTROL Insert Before] o conteúdo das marcas DIV, SECTION e ARTICLE.

**Observação:** para Inserir uma imagem, o [!DNL Adobe Scene7 Publishing System] deve estar habilitado para que você tenha acesso à biblioteca de imagens.

### Recomendação

Inclua recomendações nas atividades de teste A/B (incluindo as atividades Autoalocação e Direcionamento automático) e Direcionamento de experiência (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insira fragmentos de experiência criados em [!DNL Adobe Experience Manager] (AEM) nas atividades [!DNL Target] para auxiliar na otimização ou na personalização. Para obter mais informações, consulte [Fragmentos de experiência do AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

As opções disponíveis são as seguintes:

### [!UICONTROL Offer Decision]

Adicione uma [oferta criada em [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} para apresentar a melhor oferta e experiência aos seus clientes usando o offer decisioning.

**Observação:** esta opção está disponível somente durante a edição ou criação das atividades [manuais [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) ou [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT). Essa opção não está disponível para outros tipos de atividade.

Para obter mais informações, consulte [Usar decisões de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML] e [!UICONTROL Text]

Inclua qualquer tipo de elemento em sua página, além de modificar o conteúdo existente. Inclua texto, código, listas, entre outros, para criar experiências completamente diferentes para testar.

Selecione um elemento da página, clique em [!UICONTROL Insert After] e escolha se você quer inserir uma imagem, HTML ou texto. O elemento inserido aparece após o elemento selecionado.

O comportamento do elemento inserido depende da estrutura da página, do CSS e de outras opções de configuração de página. É necessário um HTML válido para fazer página aparecer corretamente. Sempre teste sua página após inserir um item para garantir que ele apareça conforme esperado.

[!UICONTROL Recommendations] dá suporte a [!UICONTROL Insert After] o conteúdo das marcas DIV, SECTION e ARTICLE.

**Observação:** para Inserir uma imagem, o [!DNL Adobe Scene7 Publishing System] deve estar habilitado para que você tenha acesso à biblioteca de imagens.

### Recomendação

Inclua recomendações nas atividades de teste A/B (incluindo as atividades Autoalocação e Direcionamento automático) e Direcionamento de experiência (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insira fragmentos de experiência criados em [!DNL Adobe Experience Manager] (AEM) nas atividades [!DNL Target] para auxiliar na otimização ou na personalização. Para obter mais informações, consulte [Fragmentos de experiência do AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

As opções disponíveis são as seguintes:

### [!UICONTROL Offer Decision]

Adicione uma [oferta criada em [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} para apresentar a melhor oferta e experiência aos seus clientes usando o offer decisioning.

**Observação:** esta opção está disponível somente durante a edição ou criação das atividades [manuais [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) ou [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT). Essa opção não está disponível para outros tipos de atividade.

Para obter mais informações, consulte [Usar decisões de oferta](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Selecione uma imagem diferente da Biblioteca de conteúdo. As imagens disponíveis para troca incluem aquelas carregadas na pasta de ativos da Experience Cloud ou na Biblioteca de conteúdo do Target.

Durante a criação da atividade inicial, o URL exibido não é o URL usado para a entrega. Após a sincronização da atividade, esse URL é atualizado para um URL de produto do Scene7.

Por exemplo, o URL inicial pode se parecer com o seguinte exemplo:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

Após a sincronização da atividade, o URL de entrega pode ser parecido com o seguinte exemplo:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

O Recommendations suporta a opção &quot;Substituir por&quot; nas tags DIV, SECTION e ARTICLE.

**Observação:** a troca de imagens exige uma conta do sistema de publicação do Adobe Scene7.

### [!UICONTROL HTML Offer]

Selecione uma oferta diferente de [!UICONTROL Content Library].

**Observação:** ofertas de HTML são armazenadas em servidores do [!DNL Target].

Uma oferta de HTML pode ter até 256 KB.

### Recomendação

Inclua recomendações nas atividades de teste A/B (incluindo as atividades Autoalocação e Direcionamento automático) e Direcionamento de experiência (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insira fragmentos de experiência criados em [!DNL Adobe Experience Manager] (AEM) nas atividades [!DNL Target] para auxiliar na otimização ou na personalização. Para obter mais informações, consulte [Fragmentos de experiência do AEM](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

As opções disponíveis são as seguintes:

### [!UICONTROL Rearrange]

Arraste o elemento para outro local no mesmo elemento pai ou DIV. Outros elementos trocam de local para abrir espaço para o elemento reorganizado.

**Observação**: o rastreamento de cliques não funciona em itens reorganizados.

Atualmente, determinadas ações do VEC, como [!UICONTROL Rearrange] e [!UICONTROL Move], presumem que os elementos irmãos dos elementos pais de origem e destino estão completamente carregados. Se o carregamento lento ocorrer nos elementos DOM principais (origem ou destino), essas ações do VEC podem causar comportamento inconsistente. Estamos trabalhando em uma abordagem mais confiável para fazer com que as ações do VEC funcionem em elementos DOM carregados lentamente. Como solução temporária, você pode usar [!UICONTROL Custom Code] nesses cenários para renderizar suas experiências.

### [!UICONTROL Resize]

Redimensionar um elemento na página. Quando você seleciona [!UICONTROL Resize], aparece uma alça no canto inferior direito do elemento que permite arrastar esse canto para redimensionar. Segure a tecla Shift para manter a mesma proporção.

**Observação:** elementos em linha não podem ser redimensionados.

### [!UICONTROL Move] {#move}

Mover elementos na página. Diferentemente da opção [!UICONTROL Rearrange], [!UICONTROL Move] não desloca outros elementos para abrir espaço para o elemento que está sendo movido. Use as teclas de seta para ajustar o movimento. (Aprimoramento planejado: suporte para garantir que os elementos movidos não estejam ocultos atrás de outros elementos.)

Em determinadas situações, como quando uma restrição CSS requer que um elemento permaneça dentro do elemento pai, você não pode mover o elemento para fora dele. Um elemento não pode ser movido para fora de um container que tenha a seguinte propriedade CSS: `overflow: hidden`.

Consulte [!UICONTROL Rearrange] acima para obter mais informações sobre comportamento inconsistente com as ações [!UICONTROL Move] e [!UICONTROL Rearrange] devido ao carregamento lento de elementos DOM.

### [!UICONTROL Hide]

Ocultar o elemento. O espaço em branco permanece, mas o conteúdo é removido.

### [!UICONTROL Remove]

Remova o elemento. O espaço em branco atrás da imagem é removido e o espaço onde o elemento estava é recolhido.

**Observação:** os itens de uma mbox &quot;clássica&quot; (uma mbox criada em uma campanha do Target Classic) não podem ser removidos usando esta opção.

## [!UICONTROL Expand Section]

Selecione o elemento pai, além do elemento selecionado originalmente. Ao selecionar qualquer elemento pai, todos os filhos desse elemento serão selecionados automaticamente. Você pode expandir a seleção várias vezes.

## [!UICONTROL Navigate to Link]

Abra o destino do link.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Desfaça as alterações feitas em suas atividades durante uma sessão de alteração. Você também pode refazer alterações que foram desfeitas anteriormente.

## Considerações {#considerations}

* Se uma oferta inclui conteúdo HTML, consulte &quot;Como o at.js renderiza ofertas com conteúdo HTML&quot; em [Como o at.js funciona](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} para obter mais informações.

## Suporte a elemento personalizado {#custom}

O VEC oferece suporte a [Componentes da Web](https://developer.mozilla.org/pt-BR/docs/Web/Web_Components) para permitir que você crie e teste experiências e ofertas personalizadas em elementos personalizados e em elementos dentro de elementos personalizados. Essa funcionalidade está disponível no VEC para todos os tipos de atividade [!DNL Target].

>[!NOTE]
>
>O VEC dá suporte a elementos personalizados na [at.js versão](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank} 2.7.0 (ou posterior){target=_blank}. Certifique-se de que seu site tenha a versão necessária implantada. Se você estiver usando a [extensão auxiliar do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), ela também deverá ter a versão necessária do at.js implantada. As opções de VEC descritas acima não estão visíveis e disponíveis para uso com versões não compatíveis da at.js.
>
>No momento, o suporte do VEC para elementos personalizados não é compatível com o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}.

A maioria das ações do VEC é compatível com eventos personalizados e dentro de eventos personalizados, com as seguintes exceções:

As seguintes ações não estão disponíveis em elementos personalizados:

* [!UICONTROL Edit]
   * [!UICONTROL Text/HTML]
   * [!UICONTROL Link]
   * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

A seguinte ação não está disponível dentro de elementos personalizados:

* [!UICONTROL Layout]
   * [!UICONTROL Rearrange]

## Navegar pelos elementos usando o caminho DOM {#dom-path}

Ao clicar em um elemento na página, o menu de opções de VEC é exibido. Além disso, ao clicar em um elemento, o caminho DOM correspondente é exibido na parte inferior da página.

![Caminho DOM](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path.png)

Você pode usar o caminho DOM para ver rapidamente as informações sobre o elemento selecionado (tipo, ID e classe) e mover para cima ou para baixo o caminho DOM para selecionar o elemento desejado.

Quando você passa o mouse sobre o caminho DOM, uma caixa azul destaca o elemento correspondente no VEC. Quando você clica no elemento, uma caixa laranja destaca o elemento e o menu de opções do VEC é exibido, conforme explicado acima.

É possível navegar com facilidade em qualquer elemento pai, irmão ou filho do VEC usando o caminho DOM.

O recurso de caminho DOM também está disponível ao configurar o [rastreamento de cliques](/help/main/c-activities/r-success-metrics/click-tracking.md).
