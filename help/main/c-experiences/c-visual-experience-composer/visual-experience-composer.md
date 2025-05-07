---
keywords: visual experience composer;vec;wysiwyg
description: Saiba mais sobre as noções básicas de uso do Visual Experience Composer (VEC) no Adobe Target. O VEC é um editor do WYSIWYG que permite criar experiências personalizadas com facilidade.
title: Como usar o Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
source-git-commit: 3f5b198ad08d85caa9c859171e78b710083e44fb
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 43%

---

# [!UICONTROL Visual Experience Composer] (VEC)

O [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] é um editor do WYSIWYG que permite aos clientes criar e testar experiências personalizadas diretamente em seus sites ou páginas da Web móveis sem precisar editar o código.

>[!NOTE]
>
>A versão [!DNL Target Standard/Premium] 25.2.1 (17 de fevereiro de 2025) incluiu uma versão atualizada do VEC. Para obter informações sobre como o VEC atualizado difere da versão anterior, consulte [alterações do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/vec-changes.md). Para obter uma visão geral das várias opções no VEC atualizado, consulte [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

O VEC permite criar e testar facilmente experiências e ofertas personalizadas no contexto do site. Você pode criar experiências e ofertas para atividades do [!DNL Target] arrastando e soltando, alternando e modificando o layout e o conteúdo de uma página da Web (ou oferta) ou página da Web móvel.

O VEC é um dos principais recursos do [!DNL Target]. O VEC permite aos profissionais de marketing e designers criarem e alterarem o conteúdo usando uma interface visual. Muitas escolhas de design podem ser feitas sem necessitar de edição direta do código. A edição de HTML e JavaScript também é possível usando as opções de edição disponíveis no compositor.

Na guia [!DNL Target] **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]**, você pode inserir a URL padrão [!UICONTROL Visual Experience Composer].

Esse URL determina onde você começa quando abre o VEC. Se você não inserir um URL padrão, começará com uma página em branco quando abrir o editor e, em seguida, poderá especificar um URL.

![Destaque do VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

>[!NOTE]
>
>Certos navegadores, como o [!DNL Firefox], podem impedir a exibição de uma página no VEC se ela tiver conteúdo misto (por exemplo, uma página não segura em um site seguro). Se a sua página não for exibida, clique no ícone ao lado da URL na barra de endereços do navegador e clique em **[!UICONTROL Disable protection on this page]**. Esse problema não afeta a exibição das suas páginas para os visitantes do site.

O conteúdo dentro de um iframe na página não pode ser modificado no VEC. Para editar o conteúdo em um iframe, verifique se o documento do iframe está habilitado para [!DNL Target] e, em seguida, carregue esse URL de iframe no VEC.

Você pode usar as guias no painel [!UICONTROL Experiences] para exibir sua página da mesma forma que ela apareceria para públicos diferentes ou com experiências diferentes. Você pode fornecer um nome para cada experiência. Por exemplo, se você estiver testando o local do link Início na barra de navegação, poderá nomear uma experiência em que o link Início aparecerá primeiro. Por exemplo, &quot;Link da página inicial&quot; para facilitar a identificação das experiências na lista.

>[!NOTE]
>
>As alterações na estrutura de uma página que afetam os locais usados em uma atividade criada nessa página podem causar problemas com a edição de experiência. Se um local tiver sido alterado fora do VEC, [!DNL Target] talvez não consiga encontrar o local onde o conteúdo foi alterado.

Ao mover seu mouse pela página, uma caixa sensível ao contexto segue o cursor, destacando os elementos na página.

<!--Click the **[!UICONTROL Overlays]** icon to change the way the highlight displays. For example, you can choose to highlight only images, links, regional mboxes, modifications, or JavaScript. You can change the color of the highlight. You can also specify a highlight color and type of fill used to highlight different element types.

![Change Overlay settings](/help/main/c-experiences/c-visual-experience-composer/assets/change-overlay.png)-->

Clique em um elemento destacado para obter um menu de opções disponíveis para esse tipo de elemento. Por exemplo, você pode clicar em uma imagem e selecionar **[!UICONTROL Change Image]** para alterá-la para outra imagem. Ou clique em um botão e altere a cor do texto.

Você também pode clicar em **[!UICONTROL Browse]**, navegar para uma página que esteja disponível a partir da página principal, como uma página de remessa ou carrinho de compras, e testar as alterações nessa página. Você também pode acessar elementos de página que estão disponíveis quando passa o mouse, como menus flyout e minicarrinhos. Quando você terminar de navegar na página, clique em **[!UICONTROL Design]** para editar a experiência. Por exemplo, talvez você queira alterar o design do menu suspenso de um carrinho de compras ou de um carrossel de imagens.

>[!NOTE]
>
>Se um estado de passar o mouse depender do JavaScript, verifique se **[!UICONTROL Disable JavaScript]** não está selecionado. O JavaScript deve ser ativado para editar elementos de JavaScript.

Para obter informações sobre as opções disponíveis no VEC, consulte [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Você pode realizar algumas modificações em uma página enquanto ela está carregando (ou após uma falha no carregamento) ou pode cancelar o carregamento da página no VEC. Para obter mais informações, consulte:

* [Editar uma página enquanto ela está carregando ou após uma falha de carregamento](#loading)
* [Cancelar carregamento de uma página no VEC](#cancel-loading)

## Editar uma página enquanto ela está carregando ou após uma falha de carregamento {#loading}

É possível executar muitas ações antes que a página seja carregada no VEC ou até mesmo se a página não carregar completamente (por exemplo, o código personalizado não é mais operacional).

Alguns motivos pelos quais você pode querer acessar ou fazer edições em uma página enquanto ela está carregando no VEC ou após uma falha no carregamento:

* Você deseja fazer uma modificação simples em uma página, como adicionar um código personalizado ou alterar o nome de uma experiência
* Você deseja copiar o código personalizado existente de uma página que não está mais acessível
* Você sabe que uma página não carregará no VEC, mas quer fazer edições simples mesmo assim

Enquanto a página é carregada (ou após uma falha no carregamento), o painel [!UICONTROL Experiences], o painel [!UICONTROL Components] e as opções [!UICONTROL Configure] ficam acessíveis.

## Cancelar carregamento de uma página no VEC {#cancel-loading}

Você pode cancelar o carregamento de uma página no VEC para desbloquear a edição da atividade sem esperar o carregamento da página. Esse recurso economiza tempo e ajuda a fazer edições simples ou inserir um código personalizado com mais eficiência sem esperar que a página seja carregada no VEC.

Alguns motivos pelos quais você pode cancelar o carregamento de uma página no VEC incluem:

* Você deseja fazer pequenas edições em modificações existentes
* Você deseja excluir uma ou mais modificações existentes
* Você deseja inserir ou editar um código personalizado
* Você inseriu erroneamente o URL incorreto da página
* Você deseja ativar ou desativar o JavaScript antes de carregar a página no VEC
* Você deseja adicionar mais regras de teste de modelo aos critérios [!UICONTROL Page Delivery]
* Você deseja substituir o botão [!UICONTROL Enhanced Experience Composer] (EEC) global ao carregar uma página pelo EEC ou somente iframe

Se você cancelar o carregamento de página no VEC, poderá alternar entre experiências na atividade sem esperar que a página seja carregada. Para visualizar a página no VEC novamente, clique no botão **[!UICONTROL Reload]**.

>[!IMPORTANT]
>
>Ao optar por cancelar o carregamento no VEC, certifique-se de inserir um código personalizado ou realizar qualquer modificação corretamente. Execute o procedimento de controle de qualidade de maneira adequada para garantir que seu código personalizado e quaisquer modificações sejam entregues conforme esperado.

Para cancelar o carregamento de uma página no VEC, clique no botão **[!UICONTROL Cancel Loading]** enquanto a página estiver carregando. A página não será carregada no VEC para essa atividade durante a sessão de edição atual.

Para continuar o gerenciamento de experiências na atividade atual ou adicionar novas modificações, clique no botão **[!UICONTROL Reload]**.
