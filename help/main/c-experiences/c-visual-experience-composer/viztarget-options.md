---
keywords: opções do visual experience composer;opções do visual experience composer;opções de experiência;editar texto;editar html;editar texto/html;editar cor de fundo;cor de fundo;inserir elemento;editar link;link;link do visual experience composer;editar classe css;classe css;trocar oferta;troca de oferta;trocar imagem;troca de imagem;remover item;item remover;ocultar item;ocultar item;reorganizar;mover elemento;elemento mover;redimensionar elemento;elemento redimensionar;elemento;expandir seleção;navegar até este link;navegar no link;navegar;link;navegar;desfazer;refazer/refazer;eventos personalizados;componentes da web;decisão de oferta;decisão de oferta
description: Explore as opções disponíveis no  [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC).
title: Como faço para usar as Opções do [!UICONTROL Visual Experience Composer] (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 50993d6c-5025-488a-8b33-9ed7c142de6e
source-git-commit: b1bde455f686c34e7a5184868ce63db0b74e2af7
workflow-type: tm+mt
source-wordcount: '1998'
ht-degree: 8%

---

# Opções do Visual Experience Composer

A versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica a interface do usuário atualizada e suas opções.

>[!TIP]
>
>Para saber como o VEC atualizado difere do VEC herdado, consulte [alterações do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md).

>[!IMPORTANT]
>
>O [!UICONTROL Visual Editing Composer] atualizado exige a [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper] extensão](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) disponível no [!DNL Chrome Web Store].

O VEC é exibido ao criar ou editar uma atividade existente.

![Visual Experience Composer (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## Visão geral da interface do VEC

As seções a seguir explicam as opções disponíveis no VEC atualizado para uma atividade [!UICONTROL A/B Test]. As opções variam, dependendo do tipo de atividade.

### Painel [!UICONTROL Experiences]

O painel [!UICONTROL Experiences] é exibido no painel esquerdo do VEC.

![Painel de experiências](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Você pode exibir, criar, renomear ou remover experiências usando o painel [!UICONTROL Experiences].

As seguintes opções estão disponíveis no painel [!UICONTROL Experiences]:

* **Exibir uma experiência**: para exibir uma experiência, clique na experiência desejada para exibi-la na tela [!UICONTROL Design].
* **Adicionar uma experiência**: clique no ícone **[!UICONTROL Add]** ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) para adicionar uma nova experiência. Configure a nova experiência conforme desejado.
* **Renomear uma experiência**: clique no ícone **[!UICONTROL Rename]** ( ![Ícone Renomear](/help/main/assets/icons/Rename.svg) ) para exibir a caixa de diálogo [!UICONTROL Rename Experience]. Especifique o novo nome e clique em **[!UICONTROL Save]**.
* **Duplique, exclua ou redirecione uma experiência**: clique no ícone **[!UICONTROL More Actions]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) e escolha **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]** ou **[!UICONTROL Redirect to URL]**.

### Configurações/configurações de atividade {#settings}

Clique no ícone [!UICONTROL Configure] ( ![Ícone Configurar](/help/main/assets/icons/Setting.svg) ) exibido na parte superior da tela [!UICONTROL Design] para exibir o menu de propriedades da atividade.

![Opções de configurações da atividade](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

As opções disponíveis são as seguintes:

* **[!UICONTROL Properties]**: Atribua propriedades à atividade ou remova propriedades da atividade. [!UICONTROL Properties] é um recurso ([[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)). Para obter mais informações, consulte [Permissões de usuário do Enterprise](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).
* **[!UICONTROL Page Delivery]**: Incluir a mesma experiência em páginas semelhantes do site. Use um modelo de página para fornecer estrutura às suas páginas, ou, se as páginas contiverem elementos semelhantes, para testar variações em elementos de página estruturadas de forma semelhante ou em todo o domínio. Para obter mais informações, consulte [Incluir a mesma experiência em páginas semelhantes](/help/main/c-experiences/c-visual-experience-composer/temtest.md).
* **[!UICONTROL Site Preferences]**: configure as preferências do site para especificar como o [!DNL Target] gera seletores de CSS. Para obter mais informações, consulte _Seletores de CSS_ em [Configurar o [!UICONTROL Visual Experience Composer]](/help/main/administrating-target/visual-experience-composer-set-up.md).
* **Adicionar mais páginas**: adicione mais páginas à atividade para criar uma atividade multipáginas que permita criar uma história em várias páginas, com um design específico para cada página. Para obter mais informações, consulte [Atividade multipáginas](/help/main/c-experiences/c-visual-experience-composer/multipage-activity.md).
* **Público-alvo**: use um único público para a atividade.
* **Vários públicos-alvo**: atribua vários públicos-alvo à atividade. Clique no ícone Adicionar públicos-alvo ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) e selecione um ou mais públicos-alvo da lista. Você também pode [combinar públicos-alvo](/help/main/c-target/combining-multiple-audiences.md) ou [criar um novo público-alvo](/help/main/c-target/c-audiences/create-audience.md) na caixa de diálogo [!UICONTROL Add Audiences].

### Modos [!UICONTROL Design]/[!UICONTROL Browse]

Use os botões [!UICONTROL Design]/[!UICONTROL Browse] exibidos na parte superior da tela de design para alternar entre o modo de design e o modo de navegação.

![Alternância de design e navegação](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Use o modo [!UICONTROL Browse] para navegar em seu site e escolher o modo de exibição ou a página que deseja atualizar. Volte para o modo [!UICONTROL Design] para adicionar ou editar suas alterações.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Você pode desfazer as alterações feitas ao clicar no ícone [!UICONTROL Undo] ( ![ícone Desfazer](/help/main/assets/icons/Undo.svg) ).

![Ícone Desfazer no VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Para refazer uma ação, expanda o grupo de botões Desfazer/[!UICONTROL Redo] e escolha [!UICONTROL Redo].

### Painel [!UICONTROL Components]

Você pode adicionar vários componentes à sua página da Web e editá-los conforme necessário usando o novo painel [!UICONTROL Components].

![Painel de componentes](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

>[!NOTE]
>
>Se você vir o painel [!UICONTROL Modifications] nessa área em vez do painel [!UICONTROL Components], clique no ícone **[!UICONTROL Show Components]** ( ![ícone Mostrar componentes](/help/main/assets/icons/Add.svg) ). O ícone [!UICONTROL Show Components] ( ![Mostrar ícone Componentes](/help/main/assets/icons/Add.svg) ) e o ícone [!UICONTROL Show Modifications] ( ![Mostrar painel Modificações](/help/main/assets/icons/History.svg) ) atuam como alternadores para mostrar as opções apropriadas.

Para adicionar um novo componente a uma experiência:

1. Clique no componente desejado que deseja adicionar para realçá-lo.

   Os componentes disponíveis são agrupados em contêineres lógicos:

   * [!UICONTROL Basic]
      * [!UICONTROL Divider]
      * [!UICONTROL HTML]
      * [!UICONTROL Image]
   * [!UICONTROL Text]
      * [!UICONTROL Heading]
      * [!UICONTROL Paragraph]
      * [!UICONTROL Link]
   * [!UICONTROL Dynamic]
      * [[!UICONTROL Recommendation]](/help/main/c-recommendations/recommendations-as-an-offer.md)
      * [[!UICONTROL Experience Fragment]](/help/main/c-integrating-target-with-mac/aem/experience-fragments-aem.md)
      * [[!UICONTROL HTML Offer]](/help/main/c-experiences/c-manage-content/manage-content.md)

1. Arraste o componente sobre um elemento de página existente na tela [!UICONTROL Design].
1. Escolha substituir o elemento selecionado ou inserir o componente antes ou depois do elemento selecionado.

### Painel [!UICONTROL Modifications]

Para abrir o painel [!UICONTROL Modifications], clique no ícone [!UICONTROL Show Modifications] ( ![Mostrar painel de Modificações](/help/main/assets/icons/History.svg) ) no painel [!UICONTROL Components].

![Painel de modificações](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>O ícone [!UICONTROL Show Components] ( ![Mostrar ícone Componentes](/help/main/assets/icons/Add.svg) ) e o ícone [!UICONTROL Show Modifications] ( ![Mostrar painel Modificações](/help/main/assets/icons/History.svg) ) atuam como alternadores para mostrar as opções apropriadas.

O painel [!UICONTROL Modifications] mostra todas as alterações feitas em sua página no [!UICONTROL Visual Experience Composer] (VEC) e permite que você faça alterações adicionais (como Seletor de CSS, Mbox e Código personalizado).

Clique no ícone **[!UICONTROL More Options]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) no cabeçalho do painel para adicionar uma modificação, excluir todas as modificações ou excluir todas as modificações inválidas. Clique em [!UICONTROL Select] para executar operações em massa: [!UICONTROL Apply to All Pages] ou [!UICONTROL Delete].

Clique no ícone **[!UICONTROL More Options]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) ao lado de cada modificação para exibir suas informações, excluir a modificação ou aplicar a modificação a mais exibições.

### Tela [!UICONTROL Design]

A tela [!UICONTROL Design] permite selecionar janelas de visualização, inclusive ajustar à tela, [!UICONTROL Desktop], [!UICONTROL Tablet], [!UICONTROL Mobile Landscape] e [!UICONTROL Mobile Portrait]. Por padrão, a tela se ajusta à página junto com os visores definidos na seção [Administração](/help/main/administrating-target/visual-experience-composer-set-up.md).

![Opções de viewport](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

Também é possível aumentar ou diminuir o zoom clicando no ícone apropriado ( ![ícone de Aumentar Zoom](/help/main/assets/icons/ZoomIn.svg) ou ![ícone de Diminuir Zoom](/help/main/assets/icons/ZoomOut.svg) ).

Ao clicar em um elemento de página na tela [!UICONTROL Design], um menu mostrará as opções disponíveis para esse tipo de elemento. Além disso, um caminho DOM é exibido na parte inferior da página, possibilitando uma navegação fácil pela estrutura da página.

As várias ações do [!UICONTROL Visual Experience Composer] (VEC) são agrupadas nas opções de menu apropriadas para tornar seu trabalho mais rápido e eficiente:

![Menu de opções de VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-options.png)

>[!NOTE]
>
>As opções disponíveis dependem do tipo de atividade e do elemento que você está criando ou editando. Para obter mais informações sobre como editar imagens e ofertas em uma atividade [!UICONTROL A/B Test], consulte [Editar elementos usando a [!UICONTROL Design] tela](#design) abaixo.

### Painel [!UICONTROL Properties]

O painel [!UICONTROL Properties] permite alterar as propriedades dos elementos selecionados na página, sejam eles elementos do HTML ou objetos específicos do [!DNL Target], como recomendações ou ofertas.

![Painel de propriedades](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Clique nos ícones na parte superior do painel para editar o código HTML ou excluir, duplicar ou ocultar elementos. As alterações aparecem no painel [!UICONTROL Modifications].

O painel [!UICONTROL Properties] pode ser recolhido no painel direito. Clique no ícone [!UICONTROL Show/Hide Properties] ( ![Ícone Propriedades](/help/main/assets/icons/Propertie.svg) ) à direita do painel para recolher ou exibir o painel [!UICONTROL Properties].

## Editar elementos usando a tela [!UICONTROL Design] {#design}

As seções a seguir mostram como editar imagens e texto na tela [!UICONTROL Design]. A tela Design, junto com os painéis Componentes, Modificações e Propriedades fornecem ferramentas poderosas para permitir que você crie experiências facilmente para suas atividades.

### Opções de imagem

Se você clicar em uma imagem em uma atividade [!UICONTROL A/B Test], o VEC será semelhante à seguinte ilustração:

![VEC com imagem selecionada](/help/main/c-experiences/c-visual-experience-composer/assets/vec-image.png)

Selecione componentes do quadro [!UICONTROL Components] no lado esquerdo para inserir os seguintes elementos:

* Básico (divisor, HTML, imagem).
* Texto (cabeçalho, parágrafo, link).
* Dinâmico ([Recomendação](/help/main/c-recommendations/recommendations-as-an-offer.md), [Fragmento de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), oferta do HTML).

O menu na parte superior da imagem permite fazer o seguinte:

* Inserir um link ( ![ícone Inserir link](/help/main/assets/icons/Link.svg) ).
* Altere a imagem ( ![Ícone Escolher imagem](/help/main/assets/icons/Images.svg) ).
* Adicionar personalização ( ![Ícone Adicionar Personalization](/help/main/assets/icons/PersonalizationField.svg) ).
* Excluir a imagem ( ![Ícone Excluir](/help/main/assets/icons/Delete.svg) ).

O painel [!UICONTROL Properties] no lado direito permite configurar ainda mais as propriedades da imagem.

Os ícones na parte superior do quadro permitem fazer o seguinte:

* Edite o HTML ( ![Ícone Inserir HTML](/help/main/assets/icons/Code.svg) ). Consulte [Editar HTML](#html) abaixo para obter mais informações.
* Duplique a imagem ( ![Ícone de duplicação](/help/main/assets/icons/Code.svg) ).
* Excluir a imagem ( ![Ícone Excluir](/help/main/assets/icons/Delete.svg) ).
* Ocultar a imagem ( ![Ícone Ocultar](/help/main/assets/icons/VisibilityOff.svg) ).

As opções no quadro direito permitem que você faça o seguinte:

* Edite a classe CSS.
* Configure as propriedades da imagem (fonte, título, texto alternativo).
* Edite o URL do link.
* Configure o tamanho da imagem (altura e largura). Clique em [!UICONTROL Show Advanced Options] para configurar o tamanho mínimo e máximo, a largura, a altura, o estouro e o ajuste do objeto da imagem.
* Configure a posição da imagem na página (absoluta, fixa, relativa, estática ou fixa).
* Configure o espaçamento do elemento, incluindo a margem e o preenchimento.
* Configure os efeitos do elemento (opacidade). Clique em [!UICONTROL Show Advanced Options] para configurar os valores de sépia, escala de cinza, contraste, brilho e desfoque da imagem. Também é possível inverter ou girar a imagem.
* Configure os estilos em linha da imagem.

### Opções de texto

Se você clicar em texto em uma atividade [!UICONTROL A/B Test], o VEC será semelhante à seguinte ilustração:

![VEC com texto selecionado](/help/main/c-experiences/c-visual-experience-composer/assets/vec-text.png)

Selecione componentes do quadro [!UICONTROL Components] no lado esquerdo para inserir os seguintes elementos:

* Básico (divisor, HTML, imagem).
* Texto (cabeçalho, parágrafo, link).
* Dinâmico ([Recomendação](/help/main/c-recommendations/recommendations-as-an-offer.md), [Fragmento de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md), oferta do HTML).

Clique no ícone [!UICONTROL Show Modifications] ( ![Ícone Mostrar modificações](/help/main/assets/icons/History.svg) ) para exibir as modificações na experiência.

O menu na parte superior do elemento de texto permite fazer o seguinte:

* Configurar as propriedades do texto (nível do cabeçalho, parágrafo, citação em bloco ou monoespaço)
* Selecione a cor do texto ( ![ícone Cor do Texto](/help/main/assets/icons/TextColor.svg) )
* Configure os atributos do texto (negrito, itálico, sublinhado ou tachado) ( ![Ícone Escolher atributos de texto](/help/main/assets/icons/Text.svg) ).
* Configure o alinhamento do texto (esquerda, centro, direita, justificado) ( ![Ícone de Alinhamento de Texto](/help/main/assets/icons/TextAlignCenter.svg) ).
* Inserir um link ( ![ícone Inserir link](/help/main/assets/icons/Link.svg) ).
* Substitua o conteúdo por uma oferta do HTML, [Fragmento de experiência](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md) ou [Recomendação](/help/main/c-recommendations/recommendations-as-an-offer.md).
* Edite o HTML ( ![Ícone Inserir HTML](/help/main/assets/icons/Code.svg) ).
* Adicionar personalização ( ![Ícone Adicionar Personalization](/help/main/assets/icons/PersonalizationField.svg) ).
* Excluir a imagem ( ![Ícone Excluir](/help/main/assets/icons/Delete.svg) ).

O painel [!UICONTROL Properties] no lado direito permite configurar ainda mais as propriedades do texto.

Os ícones na parte superior do quadro permitem fazer o seguinte:

* Edite o HTML ( ![Ícone Inserir HTML](/help/main/assets/icons/Code.svg) ). Consulte [Editar HTML](#html) abaixo para obter mais informações.
* Duplique o texto ( ![Ícone de duplicado](/help/main/assets/icons/Code.svg) ).
* Exclua o texto ( ![Ícone Excluir](/help/main/assets/icons/Delete.svg) ).
* Ocultar o texto ( ![Ícone Ocultar](/help/main/assets/icons/VisibilityOff.svg) ).

As opções no quadro direito permitem que você faça o seguinte:

* Edite a classe CSS.
* Configurar a cor de fundo e a imagem do texto.
* Configure a tipografia do texto (estilo do cabeçalho, tamanho da fonte, espessura da fonte, altura da linha, alinhamento, cor do texto, estilo do texto (negrito, itálico, sublinhado ou tachado)).
* Configure listas, incluindo com marcadores, numeradas ou A,B,C.
* Escolha a cor da borda.
* Configure o tamanho da caixa de texto (altura e largura). Clique em [!UICONTROL Show Advanced Options] para configurar o tamanho mínimo e máximo, a largura, a altura, o estouro e o ajuste do objeto da caixa de texto.
* Configure a posição da caixa de texto na página (absoluta, fixa, relativa, estática ou fixa) e defina o número de pixels entre a parte superior, direita, inferior e esquerda.
* Configure o espaçamento do elemento, incluindo a margem e o preenchimento.
* Configure os efeitos do elemento (opacidade). Clique em [!UICONTROL Show Advanced Options] para configurar os valores de sépia, escala de cinza, contraste, brilho e desfoque da imagem. Também é possível inverter ou girar o texto.
* Configure os estilos em linha.

## Editar HTML

Além do código HTML, você pode editar e injetar JavaScript personalizado.

Várias opções de formatação de rich text estão disponíveis durante a edição de texto e HTML para atividades de [!UICONTROL A/B] e [!UICONTROL Experience Targeting]. Você pode escolher uma fonte, selecionar um estilo de fonte, alterar o alinhamento do texto e outras opções de formatação de texto padrão. Ao modificar o HTML, você pode alternar entre a visualização de código e a visualização de edição avançada do HTML.

As seguintes tags de HTML 5 podem ser aninhadas:

| Adicionar tag | Tags aninhadas permitidas |
| --- | --- |
| `<a>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>` |
| `<ins>` | `<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>` |
| `<del>` | `<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>` |
| `<label>` | `<p>` |

## Navegar pelos elementos usando o caminho DOM {#dom-path}

Ao clicar em um elemento na página, o menu de opções de VEC é exibido. Além disso, ao clicar em um elemento, o caminho DOM correspondente é exibido na parte inferior da página.

![Caminho DOM](/help/main/c-experiences/c-visual-experience-composer/assets/dom-path-refresh.png)

Se você não vir o caminho DOM, clique no ícone [!UICONTROL Show DOM] ( ![Mostrar ícone DOM](/help/main/assets/icons/LayersBringToFront.svg) ).

Você pode usar o caminho DOM para ver rapidamente as informações sobre o elemento selecionado (tipo, ID e classe) e mover para cima ou para baixo o caminho DOM para selecionar o elemento desejado.

<!--When you hover over the DOM path, a blue box highlights the corresponding element in the VEC. When you click the element, an orange box highlights the element and the VEC options menu displays, as explained above.-->

É possível navegar com facilidade em qualquer elemento pai, irmão ou filho do VEC usando o caminho DOM.

O recurso de caminho DOM também está disponível ao configurar o [rastreamento de cliques](/help/main/c-activities/r-success-metrics/click-tracking.md).

## Mais informações sobre a interface atualizada

* Notas de versão do [[!DNL Target Standard/Premium] 25.2.1 (17 de fevereiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] e o [!UICONTROL Visual Experience Composer] (VEC).

* Notas de versão do [[!DNL Target Standard/Premium] 25.1.1 (9 de janeiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para o [!UICONTROL Offers Library].

* [Compreender a [!DNL Target] Interface](/help/main/c-intro/understand-the-target-ui.md): fornece uma breve visão geral para ajudá-lo a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.

* [[!UICONTROL Visual Experience Composer] alterações](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): a versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões herdadas e atualizadas do VEC.

* [[!UICONTROL Visual Experience Composer] opções](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): este artigo explica a interface do usuário do VEC atualizada e suas opções.

* [[!DNL Target] Perguntas frequentes sobre atualização da interface do usuário](/help/main/c-intro/updated-ui-faq.md): estas perguntas frequentes abordam perguntas comuns sobre a nova interface do usuário do [!DNL Target] e do [!UICONTROL Visual Experience Composer] (VEC), incluindo alterações na navegação, locais de recursos e substituição da versão temporária da interface do usuário. Seja você um profissional de marketing, desenvolvedor ou administrador, essas Perguntas frequentes ajudarão a fazer a transição descomplicada e a aproveitar ao máximo a interface atualizada.

<!--## [!UICONTROL Edit]

The following options are available:

### [!UICONTROL Text/HTML] {#edit-text-html}

Change the HTML code for the element, such as the text for a text area, button, or link.

In addition to HTML code, you can edit and inject custom JavaScript.

Several rich text formatting options are available when editing text and HTML for [!UICONTROL A/B] and [!UICONTROL Experience Targeting] activities. You can choose a font, select a font style, change text alignment, and other standard text formatting options. When modifying HTML, you can toggle between the code view and rich-editing view of the HTML.

The following HTML5 tags can be nested:

|Tag|Allowed Nested Tags|
| --- | --- |
|`<a>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`, `<div>`, `<figure>`, `<figcaption>`|
|`<ins>`|`<h1-h6>`, `<p>`, `<ul>`, `<ol>`, `<menu>`|
|`<del>`|`<ul>`, `<ol>`, `<menu>`, `<h1-h6>`, `<p>`|
|`<label>`|`<p>`|

### [!UICONTROL Background Color]

Use the color picker to select or configure a background color. You can select a color swatch, and adjust it using RGB values or color hex codes. The red x in the color picker makes the background transparent.

**Note:** This option is not available for an element where a background image is set. 

### [!UICONTROL Styles] {#styles}

Use the [!UICONTROL Styles] panel to view or edit the value of existing styles for the selected element. You can also add additional styling.

To access the [!UICONTROL Styles] panel, click a page element from within the VEC, then click **[!UICONTROL Edit]** > **[!UICONTROL Styles]**.

The [!UICONTROL Styles] panel displays on the right side of the VEC. The panel contains a list of styles that lets you edit or add to the selected element. A real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

![Styles panel](/help/main/c-experiences/c-visual-experience-composer/assets/styles-panel-new.png)

As you apply different styles, you can always revert your changes by clicking the [!UICONTROL Revert] icon that displays at the top-right corner of the [!UICONTROL Styles] panel after you change any section. Clicking the [!UICONTROL Revert] icon reverts all changes on the current section's panel.

Expand each section to edit or add styles, as explained below. To save your changes, click the [!UICONTROL Back] icon at the top of the panel to return to the panel's main display, then click **[!UICONTROL Save]**. 

Blue dots on the main panel and next to each option on the various section panels indicate that you have changed the corresponding styles. This visual indicator makes it easy for you to review your changes before clicking [!UICONTROL Save].

>[!NOTE]
>
>Quick actions for layout changes, background color, resizing, and move are also available as separate actions in the VEC menu. These options can be used as separate actions or you can use the Styles menu, as explained here.

* **[!UICONTROL Background]**

  Change the background color and image.

  * Color (specify the color code or use the color picker)
  * Image (select an image from the image picker)
  * Image source (specify an external URL)
  * Attachment
    * Click the top drop-down list to select scroll, fixed, or local
    * Click the bottom drop-down list to select repeat, repeat-x, repeat-y, no-repeat, space, or round
  * Clip
    * Click the top drop-down list to select border-box, padding-box, content-box, or text
    * Click the bottom drop-down list to select auto audio or audio

* **[!UICONTROL Typography]**

  Change the typography of an element. Typography edits are quick and easy. 

  Although the rich text editor (Edit Text/HTML) is available for fine tuning, quick actions to change the entire element is available via this option. If you want to apply typography changes to only a part of the text (not to the full text), use the [rich text editor](/help/main/c-experiences/c-visual-experience-composer/c-vec-code-editor/vec-code-editor.md). 

  You can edit the following typography styles:

  * [!UICONTROL Font size]
  * [!UICONTROL Font weight]
  * [!UICONTROL Font style]
  * [!UICONTROL Color] (specify the color code or use the color picker)
  * [!UICONTROL Word spacing]
  * [!UICONTROL Line height]
  * [!UICONTROL Text alignment]

* **[!UICONTROL Margin]**

  Change the margin for the selected element. You can change the left, right, bottom, and top margins.

  Click the drop-down icon for each margin to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to set the margin or specify the number of pixels for each margin)

  Margin supports positive and negative values.

  Target also supports other size units, such as rem, pc, em. For more information about these units, see [Web Style Sheets CSS Tips and Tricks](https://www.w3.org/Style/Examples/007/units.en.html).

* **[!UICONTROL Padding]**

  Change the padding for the selected element. You can change the left, right, bottom, and top padding.

  Drag the slider to set the padding or specify the number of pixels for padding.

  Padding supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Border]**

  Click the border icons at the top of the panel to change the selected element's border.

  You can edit the following styles for each border (top, right, bottom, and left):

  * [!UICONTROL Border style] (none, hidden, dotted, dashed, solid, or double)
  * [!UICONTROL Border color] (specify the color code or use the color picker)
  * [!UICONTROL Border width] (drag the slider to select a border width or specify the width in pixels)

  Border supports width scales from 0 onwards.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Position]**

  Move the selected element from its current position. You can change the element's top, bottom, left, right, and [Z-index](https://www.w3schools.com/cssref/pr_pos_z-index.asp) position.

  Click the [!UICONTROL Static] drop-down list to choose from the following position options:

  * [!UICONTROL Static]
  * [!UICONTROL Relative]
  * [!UICONTROL Absolute]
  * [!UICONTROL Sticky]
  * [!UICONTROL Fixed]

  Click the drop-down icon for each position to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to position the element or specify the number of pixels you want to move the element)

  Position supports positive and negative values.

  Target also supports [other size units](https://www.w3.org/Style/Examples/007/units.en.html), such as rem, pc, em.

* **[!UICONTROL Size]**

  Change the selected element's width and height.

  Click the drop-down icon next to [!UICONTROL Width] and [!UICONTROL Height] to choose from the following options:

  * [!UICONTROL Auto] 
  * [!UICONTROL Value] (drag the slider to size the element or specify the number of pixels for each dimension)

* **[!UICONTROL Filter]**

  Drag the slider for each filter option or specify the desired percentage:

  * [!UICONTROL Sepia]
  * [!UICONTROL Contrast]
  * [!UICONTROL Brightness]
  * [!UICONTROL GrayScale]
  * [!UICONTROL Blur]
  * [!UICONTROL Opacity]
  * [!UICONTROL Invert]
  *[!UICONTROL  Hue-rotate]
  * [!UICONTROL Saturate]

* **[!UICONTROL CSS Editor]**

  The real-time CSS Editor lets you view changes and add styles if you are comfortable using Cascading Style Sheets (CSS) or if you receive code from your developer.

  The CSS Editor displays any changes that you make in the Styles panel. As shown in the illustration below, the font size, top border, and image size have been changed:

  ![CSS editor with changes](/help/main/c-experiences/c-visual-experience-composer/assets/css-changes.png)

  Notice the blue dots next to the [!UICONTROL Typography], [!UICONTROL Border], and [!UICONTROL Size] options in the preceding illustration. These dots indicate that you have changed these sections. If you open these section panels, blue dots display next to the specific options that you changed.

  You can type your own code if your desired style is not available by default in the [!UICONTROL Styles].

  The CSS Editor shows details for the current session only. If you save changes and then reopen the editor, details about your previous change do not display in the editor, even if you select the same element again.

  >[!IMPORTANT]
  >
  >You can apply a background image using the CSS Editor, but it might cause flicker. Test your changes before deployment.

### [!UICONTROL CSS Class]

Specify the predefined CSS class used for the element. If more than one element is selected, separate multiple CSS classes with a space.

Available for [!UICONTROL A/B], [!UICONTROL Automated Personalization], and [!UICONTROL Multivariate Test] activities.

### [!UICONTROL Link]

Change the URL in the link.

Use Edit Link to update the selector to point to the same image element. However, linking to a different image element is not supported. To link to a different image element, delete the original action from the code editor and use the [!UICONTROL Visual Experience Composer] to apply the action on the other image element.

## [!UICONTROL Insert Before]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert Before] and choose whether you want to insert an image, HTML, or text. The inserted element appears before the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert Before] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Insert After]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image], [!UICONTROL HTML], and [!UICONTROL Text]

Add any kind of element to your page in addition to modifying existing content. Add text, code, lists, and more to create entirely different experiences to test.

Select an element on the page, then click [!UICONTROL Insert After] and choose whether you want to insert an image, HTML, or text. The inserted element appears after the selected element.

The behavior of the inserted element depends on the structure of your page, your CSS, and other page configuration options. Valid HTML is required to make your page appear correctly. Always test your page after inserting an item to make sure it appears as expected.

[!UICONTROL Recommendations] supports [!UICONTROL Insert After] the contents of DIV, SECTION, and ARTICLE tags.

**Note:** Inserting an image requires that [!DNL Adobe Scene7 Publishing System] is enabled so you have access to the image library.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Replace Content]

The following options are available:

### [!UICONTROL Offer Decision]

Add an [offer created in [!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/offer-decisioniong/get-started/starting-offer-decisioning.html){target=_blank} to present the best offer and experience to your customers using offer decisioning.

**Note:** This option is available when editing or creating [manual [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md#types) or [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) (XT) activities only. This option is not available for other activity types.

For more information, see [Use offer decisions](/help/main/c-integrating-target-with-mac/ajo/offer-decision.md).

### [!UICONTROL Image]

Select a different image from the Content Library. The images available for swapping include the images uploaded to the Experience Cloud assets folder or uploaded in the Content Library in Target.

During initial activity creation, the URL displayed is not the URL used for delivery. Upon activity synching, that URL is updated to a production Scene7 URL.

For example, the initial URL might look like the following example:

`https://test.marketing.adobe.com/content/dam/mac/scholasticinc/Aug_MBM.jpeg?ch_ck=1470774943867`

After activity syncing, the delivery URL might look like the following example:

`http://s7d2.scene7.com/is/image/TargetTest/Aug_MBM?tm=1470768352933&fit=constrain&hei=173&wid=300`

Recommendations supports Replace With in DIV, SECTION, and ARTICLE tags.

**Note:** Swapping images requires an Adobe Scene7 Publishing System Account.

### [!UICONTROL HTML Offer]

Select a different offer from the [!UICONTROL Content Library].

**Note:** HTML Offers are stored on [!DNL Target] servers.

An HTML offer can be up to 256 KB.

### Recommendation

Include recommendations inside A/B Test (including Auto-Allocate and Auto-Target) and Experience Targeting (XT) activities. For more information, see [Recommendations as an offer](/help/main/c-recommendations/recommendations-as-an-offer.md).

### [!UICONTROL Experience Fragment]

Insert experience fragments created in [!DNL Adobe Experience Manager] (AEM) in [!DNL Target] activities to aid optimization or personalization. For more information, see [AEM Experience Fragments](/help/main/c-experiences/c-manage-content/aem-experience-fragments.md).

## [!UICONTROL Layout]

The following options are available:

### [!UICONTROL Rearrange]

Drag the element to another location inside the same parent element or DIV. Other elements shift location to make space for the rearranged element.

**Note**: Click-tracking does not work on rearranged items.

Currently, certain VEC actions, such as [!UICONTROL Rearrange] and [!UICONTROL Move], assume that the sibling elements of the source and destination parent elements are completely loaded. If lazy loading occurs under the parent DOM elements (source or destination), these VEC actions can cause inconsistent behavior. We are working on a more reliable approach to make VEC actions work in lazy-loaded DOM elements. As a temporary workaround, you can use [!UICONTROL Custom Code] in these scenarios to render your experiences.

### [!UICONTROL Resize]

Resize an element on your page. When you select [!UICONTROL Resize], a handle appears in the bottom-right corner of the element that lets you drag that corner to resize. Hold the Shift key to retain the same aspect ratio.

**Note:** Inline elements cannot be resized.

### [!UICONTROL Move] {#move}

Move elements on your page. Unlike the [!UICONTROL Rearrange] option, [!UICONTROL Move] does not shift other elements to make room for the element being moved. Use the arrow keys to fine tune the move. (Planned enhancement: support to ensure moved elements are not hidden behind other elements.)

In certain situations, such as when a CSS restriction requires an element to remain inside its parent element, you cannot move the element outside its parent. An element cannot be moved outside of a container that has following CSS property: `overflow: hidden`.

See [!UICONTROL Rearrange] above for more information about inconsistent behavior with the [!UICONTROL Move] and [!UICONTROL Rearrange] actions due to lazy loading of DOM elements.

### [!UICONTROL Hide]

Hide the element. The white space remains, but the content is removed.

### [!UICONTROL Remove]

Remove the element. The white space behind the image is removed and the space where the element was is collapsed.

**Note:** Items within a "classic" mbox (an mbox created within a Target Classic campaign) cannot be removed using this option.

## [!UICONTROL Expand Section]

Select the parent element in addition to the originally selected element. When you select any parent element, all children of that element are automatically selected. You can expand the selection multiple times.

## [!UICONTROL Navigate to Link]

Open the destination of the link.

## [!UICONTROL Undo]/[!UICONTROL Redo]

Undo changes you make to your activities during an editing session. You can also redo changes that have been previously undone.

## Considerations {#considerations}

* If an offer contains HTML content, see "How at.js renders offers with HTML content" in [How at.js works](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/at-js/how-atjs-works.html){target=_blank} for more information.

## Custom element support {#custom}

The VEC supports [Web Components](https://developer.mozilla.org/en-US/docs/Web/Web_Components) to let you create and test personalized experiences and offers on custom elements and on elements inside custom elements. This functionality is available in the VEC for all [!DNL Target] activity types.

>[!NOTE]
>
>VEC support for custom elements is supported in [at.js version](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank} 2.7.0 (or later){target=_blank}. Ensure that your website has the required version deployed. If you are using the [Visual Experience Composer helper extension](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md), it must also have the required version of at.js deployed. The VEC options described above are not visible and available for use with non-supported versions of at.js.
>
>VEC support for custom elements is currently not supported with the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}.

Most VEC actions are supported on custom events and inside custom events, with the following exceptions: 

The following actions are not available on custom elements:

* [!UICONTROL Edit]
  * [!UICONTROL Text/HTML]
  * [!UICONTROL Link]
  * [!UICONTROL Edit Source]

* [!UICONTROL Replace Content]

The following action is not available inside custom elements:

* [!UICONTROL Layout]
  * [!UICONTROL Rearrange]-->
