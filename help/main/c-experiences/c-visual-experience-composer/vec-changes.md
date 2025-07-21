---
keywords: visual experience composer;vec;wysiwyg
description: Entenda as alterações introduzidas no Visual Experience Composer (VEC) na versão 25.2.1 do Adobe Target (17 de fevereiro de 2025).
title: Quais alterações são introduzidas no novo Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: c8cbf4998c304910a63e31acc3ec93a04ac652ae
workflow-type: tm+mt
source-wordcount: '876'
ht-degree: 0%

---

# [!UICONTROL Visual Experience Composer] alterado

A versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões anteriores e atualizadas do VEC.

>[!IMPORTANT]
>
>O [!UICONTROL Visual Editing Composer] atualizado exige a [!DNL Adobe Experience Cloud] [[!UICONTROL Visual Editing Helper] extensão](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) disponível no [!DNL Chrome Web Store].

O VEC é exibido ao criar ou editar uma atividade existente.

![Visual Experience Composer (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Principais alterações no VEC

As seções a seguir explicam as principais alterações no VEC atualizado em comparação à versão anterior.

### Painel [!UICONTROL Experiences]

Como na versão anterior, o painel [!UICONTROL Experiences] permanece no lado esquerdo do VEC. O painel [!UICONTROL Experiences] não pode ser recolhido.

![Painel de experiências](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Você pode criar, renomear ou remover experiências usando o painel [!UICONTROL Experiences]. Clique no ícone **[!UICONTROL Add]** ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) para adicionar uma nova experiência. Clique no ícone [!UICONTROL More Actions] ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) para duplicar, excluir ou redirecionar uma experiência.

### Painel [!UICONTROL Components] (novo)

Você pode adicionar vários componentes à sua página da Web e editá-los conforme necessário usando o novo painel [!UICONTROL Components].

![Painel de componentes](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Para adicionar um novo componente, arraste o componente do painel [!UICONTROL Components] que você deseja inserir sobre um elemento de página existente na tela [!UICONTROL Design]. Em seguida, escolha inserir o componente antes de depois do elemento selecionado.

>[!NOTE]
>
>Se você vir o painel [!UICONTROL Modifications] nessa área em vez do painel [!UICONTROL Components], clique no ícone **[!UICONTROL Show Components]** ( ![ícone Mostrar componentes](/help/main/assets/icons/Add.svg) ). O ícone [!UICONTROL Show Components] ( ![Mostrar ícone Componentes](/help/main/assets/icons/Add.svg) ) e o ícone [!UICONTROL Show Modifications] ( ![Mostrar painel Modificações](/help/main/assets/icons/History.svg) ) atuam como alternadores para mostrar as opções apropriadas.
>
>Para recolher o painel [!UICONTROL Components] e ampliar a tela [!UICONTROL Design], enquanto o painel [!UICONTROL Components] estiver aberto, clique no ícone ( ![Mostrar componentes](/help/main/assets/icons/Add.svg) ).

### Painel [!UICONTROL Modifications]

Para abrir o painel [!UICONTROL Modifications], clique no ícone [!UICONTROL Show Modifications] ( ![Mostrar painel de Modificações](/help/main/assets/icons/History.svg) ) no painel [!UICONTROL Components]. O painel [!UICONTROL Modifications] alterou a posição do lado direito para o lado esquerdo da tela de edição.

![Painel de modificações](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

>[!NOTE]
>
>O ícone [!UICONTROL Show Components] ( ![Mostrar ícone Componentes](/help/main/assets/icons/Add.svg) ) e o ícone [!UICONTROL Show Modifications] ( ![Mostrar painel Modificações](/help/main/assets/icons/History.svg) ) atuam como alternadores para mostrar as opções apropriadas.
>
>Para recolher o painel [!UICONTROL Modifications] e ampliar a tela [!UICONTROL Design], enquanto o painel [!UICONTROL Modifications] estiver aberto, clique no ícone [!UICONTROL Show Modifications] ( ![Mostrar painel de Modificações](/help/main/assets/icons/History.svg) ).

O painel [!UICONTROL Modifications] mostra todas as alterações feitas em sua página no VEC e permite que você faça alterações adicionais (como Seletor de CSS, Mbox e Código personalizado).

Clique no ícone [!UICONTROL More Options] ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) para adicionar uma modificação, excluir todas as modificações ou excluir todas as modificações inválidas. Clique em [!UICONTROL Select] para executar operações em massa: [!UICONTROL Apply to All Pages] ou [!UICONTROL Delete].

Para exibir o painel [!UICONTROL Modifications] novamente, clique no ícone [!UICONTROL Hide Modifications] ( ![Mostrar painel de Modificações](/help/main/assets/icons/History.svg) ) no painel [!UICONTROL Modifications].

### Painel [!UICONTROL Properties] (novo)

O painel [!UICONTROL Properties] permite alterar as propriedades dos elementos selecionados na página, sejam eles elementos do HTML ou objetos específicos do [!DNL Target], como recomendações ou ofertas.

![Painel de propriedades](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Clique nos ícones na parte superior do painel para editar o código HTML ou excluir, duplicar ou ocultar elementos. As alterações aparecem no painel [!UICONTROL Modifications].

![Ícones de propriedade](/help/main/c-experiences/c-visual-experience-composer/assets/options-icons.png)

O painel [!UICONTROL Properties] pode ser recolhido no painel direito. Clique no ícone [!UICONTROL Show/Hide Properties] ( ![Ícone Propriedades](/help/main/assets/icons/Propertie.svg) ) à direita do painel para recolher ou exibir o painel [!UICONTROL Properties].

### Configurações/configurações de atividade

Clique no ícone [!UICONTROL Configure] ( ![Ícone Configurar](/help/main/assets/icons/Setting.svg) ) exibido na parte superior da tela de design para exibir o menu de propriedades da atividade.

![Opções de configurações da atividade](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

As diferentes opções permitem atribuir propriedades, editar regras de entrega de página, especificar preferências do site, adicionar outras páginas e ativar ou desativar atividades de várias páginas ou de vários públicos-alvo. Atribuir [!UICONTROL Properties] é um recurso [[!DNL Target Premium]](/help/main/c-intro/intro.md#premium).

A posição e a funcionalidade são semelhantes à interface anterior do VEC.

### Modos [!UICONTROL Design]/[!UICONTROL Browse]

Use os botões [!UICONTROL Design]/[!UICONTROL Browse] exibidos na parte superior do painel [!UICONTROL Properties] para alternar entre o modo de design e de navegação.

![Alternância de design e navegação](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Use o modo [!UICONTROL Browse] para navegar em seu site e escolher o modo de exibição ou a página que deseja atualizar. Volte para o modo [!UICONTROL Design] para adicionar ou editar suas alterações.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Você pode desfazer as alterações feitas ao clicar no ícone [!UICONTROL Undo] ( ![ícone Desfazer](/help/main/assets/icons/Undo.svg) ).

![Ícone Desfazer no VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Para refazer uma ação, expanda o grupo de botões Desfazer/[!UICONTROL Redo] e escolha [!UICONTROL Redo].

### Tela [!UICONTROL Design]

A tela [!UICONTROL Design] permite selecionar janelas de visualização, inclusive ajustar à tela, [!UICONTROL Desktop], [!UICONTROL Tablet], [!UICONTROL Mobile Landscape] e [!UICONTROL Mobile Portrait].

![Opções de viewport](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

O VEC atualizado também permite aumentar ou diminuir o zoom clicando no ícone apropriado ( ![ícone de Aumentar o Zoom](/help/main/assets/icons/ZoomIn.svg) ou ![ícone de Diminuir o Zoom](/help/main/assets/icons/ZoomOut.svg) ).

## Ilustração visual mostrando as alterações na interface do usuário

A ilustração a seguir mostra as alterações da interface do usuário de alto nível feitas no VEC atualizado. A parte superior da ilustração mostra a interface atualizada do VEC e a parte inferior mostra a interface anterior. As setas mostram para onde vários elementos foram movidos.

(Clique na imagem para expandi-la até a largura total do navegador.)

![Comparação de VEC-novo para a interface anterior](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png){width="600" zoomable="yes"}

## Mais informações sobre a interface atualizada

* Notas de versão do [[!DNL Target Standard/Premium] 25.2.1 (17 de fevereiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para [!UICONTROL Activities], [!UICONTROL Recommendations] e o [!UICONTROL Visual Experience Composer] (VEC).

* Notas de versão do [[!DNL Target Standard/Premium] 25.1.1 (9 de janeiro de 2025)](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-1): fornece um resumo das principais alterações na interface do usuário do [!DNL Target] para o [!UICONTROL Offers Library].

* [Compreender a [!DNL Target] Interface](/help/main/c-intro/understand-the-target-ui.md): fornece uma breve visão geral para ajudá-lo a se familiarizar com o [!DNL Target] e fornece links para informações mais detalhadas e instruções passo a passo.

* [[!UICONTROL Visual Experience Composer] alterações](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md): a versão [!DNL Adobe Target Standard/Premium] 25.2.1 (17 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões herdadas e atualizadas do VEC.

* [[!UICONTROL Visual Experience Composer] opções](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md): este artigo explica a interface do usuário do VEC atualizada e suas opções.

* [[!DNL Target] Perguntas frequentes sobre atualização da interface do usuário](/help/main/c-intro/updated-ui-faq.md): estas perguntas frequentes abordam perguntas comuns sobre a nova interface do usuário do [!DNL Target] e do [!UICONTROL Visual Experience Composer] (VEC), incluindo alterações na navegação, locais de recursos e substituição da versão temporária da interface do usuário. Seja você um profissional de marketing, desenvolvedor ou administrador, essas Perguntas frequentes ajudarão a fazer a transição descomplicada e a aproveitar ao máximo a interface atualizada.