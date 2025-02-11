---
keywords: visual experience composer;vec;wysiwyg
description: Entenda as alterações introduzidas no Visual Experience Composer (VEC) na versão 25.2.1 do Adobe Target (11 de fevereiro de 2025).
title: Quais alterações são introduzidas no novo Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 4c7a5657-93d9-4355-9d2b-c992b36bcb50
source-git-commit: 75f44b7ea4c3aff0e33cc2ee54bc39a705deaf2a
workflow-type: tm+mt
source-wordcount: '617'
ht-degree: 1%

---

# [!UICONTROL Visual Experience Composer] alterado

A versão [!DNL Adobe Target Standard/Premium] 25.2.1 (11 de fevereiro de 2015) introduz um [!UICONTROL Visual Experience Composer] (VEC) atualizado. Este artigo explica as diferenças entre as versões anteriores e atualizadas do VEC.

O VEC é exibido ao criar ou editar uma atividade existente.

![Visual Experience Composer (VEC)](/help/main/c-experiences/c-visual-experience-composer/assets/new-vec.png)

## Grandes alterações

As seções a seguir explicam as principais alterações no VEC atualizado em comparação à versão anterior.

### Painel [!UICONTROL Experiences]

Como na versão anterior, o painel [!UICONTROL Experiences] permanece no lado esquerdo do VEC. O painel [!UICONTROL Experiences] não pode ser recolhido.

![Painel de experiências](/help/main/c-experiences/c-visual-experience-composer/assets/experiences-panel.png)

Você pode criar, renomear ou remover experiências usando o painel [!UICONTROL Experiences]. Clique no ícone **[!UICONTROL Add]** ( ![Ícone Adicionar](/help/main/assets/icons/Add.svg) ) para adicionar uma nova experiência. Clique no ícone [!UICONTROL More Actions] ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) para duplicar, excluir ou redirecionar uma experiência.

### Painel [!UICONTROL Components] (novo)

Você pode adicionar vários componentes à sua página da Web e editá-los conforme necessário, usando o novo painel [!UICONTROL Components].

![Painel Componentes](/help/main/c-experiences/c-visual-experience-composer/assets/components-panel.png)

Para adicionar um novo componente, arraste o componente que deseja inserir sobre um elemento de página existente na tela de edição. Em seguida, escolha inserir o componente antes de depois do elemento selecionado.

Em comparação com a versão anterior do VEC, não é possível substituir um elemento selecionado por um componente.

### Painel [!UICONTROL Modifications]

Para abrir o painel [!UICONTROL Modifications], clique no ícone [!UICONTROL Show Modifications] ( ![Mostrar painel de Modificações](/help/main/assets/icons/History.svg) ) no painel [!UICONTROL Components]. O painel [!UICONTROL Modifications] alterou a posição do lado direito para o lado esquerdo da tela de edição.

![Painel de modificações](/help/main/c-experiences/c-visual-experience-composer/assets/modifications-panel.png)

O painel [!UICONTROL Modifications] mostra todas as alterações feitas em sua página no [!UICONTROL Visual Experience Composer] (VEC) e permite que você faça alterações adicionais (como Seletor de CSS, Mbox e Código personalizado).

Clique no ícone [!UICONTROL More Options] ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmall.svg) ) para adicionar uma modificação, excluir todas as modificações ou excluir todas as modificações inválidas. Clique em [!UICONTROL Select] para executar operações em massa: [!UICONTROL Apply to All Pages] ou [!UICONTROL Delete].

### Painel [!UICONTROL Properties] (novo)

O novo painel [!UICONTROL Properties] permite alterar as propriedades dos elementos selecionados na página, sejam esses elementos elementos de HTML ou objetos específicos de [!DNL Target], como recomendações ou ofertas.

![Painel Propriedades](/help/main/c-experiences/c-visual-experience-composer/assets/properties-panel.png)

Clique nos ícones na parte superior do painel para editar o código HTML ou excluir, duplicar ou ocultar elementos. As alterações aparecem no painel [!UICONTROL Modifications].

O painel [!UICONTROL Properties] pode ser recolhido no painel direito. Clique no ícone [!UICONTROL Show/Hide Properties] ( ![Ícone Propriedades](/help/main/assets/icons/Propertie.svg) ) à direita do painel para recolher ou exibir o painel [!UICONTROL Properties].

### Configurações/configurações de atividade

Clique no ícone [!UICONTROL Configure] ( ![Ícone Configurar](/help/main/assets/icons/Setting.svg) ) exibido na parte superior da tela de design para exibir o menu de propriedades da atividade.

![Opções de configurações da atividade](/help/main/c-experiences/c-visual-experience-composer/assets/configure-options.png)

As diferentes opções permitem habilitar ou desabilitar atividades de várias páginas ou vários públicos-alvo, atribuir propriedades (recurso [[!DNL Target Premium]](/help/main/c-intro/intro.md#premium)) ou editar regras de entrega de página.

A posição e a funcionalidade são semelhantes à interface anterior do VEC.

### Modos [!UICONTROL Design]/[!UICONTROL Browse]

Use os botões [!UICONTROL Design]/[!UICONTROL Browse] exibidos na parte superior da tela de design para alternar entre o modo de design e o modo de navegação.

![Alternância de design e navegação](/help/main/c-experiences/c-visual-experience-composer/assets/design-browse-mode.png)

Use o modo [!UICONTROL Browse] para navegar em seu site e escolher o modo de exibição ou a página que deseja atualizar. Volte para o modo [!UICONTROL Design] para adicionar ou editar suas alterações.

### [!UICONTROL Undo]/[!UICONTROL Redo]

Você pode desfazer as alterações feitas ao clicar no ícone [!UICONTROL Undo] ( ![ícone Desfazer](/help/main/assets/icons/Undo.svg) ).

![Ícone Desfazer no VEC](/help/main/c-experiences/c-visual-experience-composer/assets/undo.png)

Para refazer uma ação, expanda o grupo de botões Desfazer/[!UICONTROL Redo] e escolha [!UICONTROL Redo].

### Tela [!UICONTROL Design]

A tela [!UICONTROL Design] permite selecionar janelas de visualização, inclusive ajustar à tela, [!UICONTROL Desktop], [!UICONTROL Tablet], [!UICONTROL Mobile Landscape] e [!UICONTROL Mobile Portrait]. Por padrão, a tela se ajusta à página junto com os visores definidos na seção [Administração](/help/main/administrating-target/visual-experience-composer-set-up.md).

![Opções de viewport](/help/main/c-experiences/c-visual-experience-composer/assets/viewports.png)

O VEC atualizado também permite aumentar ou diminuir o zoom clicando no ícone apropriado ( ![ícone de Aumentar o Zoom](/help/main/assets/icons/ZoomIn.svg) ou ![ícone de Diminuir o Zoom](/help/main/assets/icons/ZoomOut.svg) ).

## Ilustração visual mostrando as alterações na interface do usuário

A ilustração a seguir mostra as alterações da interface do usuário de alto nível feitas no VEC atualizado. A parte superior da ilustração mostra a interface atualizada do VEC e a parte inferior mostra a interface anterior. As setas mostram para onde vários elementos foram movidos.

![Comparação de VEC-novo para a interface anterior](/help/main/c-experiences/c-visual-experience-composer/assets/vec-comparison.png)