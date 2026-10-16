---
keywords: visual experience composer;vec;wysiwyg
description: Saiba mais sobre as noções básicas de uso do Visual Experience Composer (VEC) no Adobe Target. O VEC é um editor do WYSIWYG que permite criar experiências personalizadas com facilidade.
title: Como usar o Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: 51650f2a-1f24-40c7-8692-77f55656b4f6
TQID: 'https://experienceleague.adobe.com/X4nfYuOtD3TVusnVIIEZhXwUdCZ-dMvbZeJlrkmI9Hs'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 140a7287246905d47bf02a84348627017a619386
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 0%
---
# [!UICONTROL Visual Experience Composer] (VEC)

O [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] é um editor do WYSIWYG para criar e testar experiências personalizadas diretamente em sites e páginas da Web móveis sem editar o código.

Crie experiências e ofertas para atividades do [!DNL Target] arrastando e soltando elementos, trocando conteúdo e alterando layouts de página. O compositor também fornece opções para editar o HTML e o JavaScript.

## Requisitos do navegador {#browser-requirements}

Há suporte para [!DNL Safari] para a interface [!DNL Adobe Target]. Você pode criar atividades baseadas em formulário no [!DNL Safari] e usar todas as funcionalidades, exceto o VEC e o [!UICONTROL Enhanced Experience Composer] (EEC). Se você abrir o Visual Experience Composer no [!DNL Safari], uma sobreposição solicitará que você alterne para [!DNL Google Chrome] para editar experiências.

Navegadores como o [!DNL Firefox] podem impedir que páginas com conteúdo misto, como uma página não segura em um site seguro, sejam exibidas no VEC. Se uma página não for exibida, clique no ícone ao lado do URL na barra de endereços do navegador e clique em **[!UICONTROL Desabilitar proteção nesta página]**. Esse problema não afeta como as páginas são exibidas para os visitantes do site.

## Abra o VEC {#open-the-vec}

Para definir a página que abre por padrão no VEC, insira uma URL padrão do [!UICONTROL Visual Experience Composer] na guia [!DNL Target] **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]**.

Se você não definir um URL padrão, o VEC será aberto com uma página em branco onde você pode especificar um URL.

![Destaque do VEC](/help/main/c-experiences/c-visual-experience-composer/assets/vec-highlight-refresh.png)

## Editar experiências {#edit-experiences}

### Exibir e nomear experiências {#view-and-name-experiences}

Use as guias no painel [!UICONTROL Experiências] para exibir como a página é exibida para públicos diferentes ou com experiências diferentes. Dê um nome descritivo a cada experiência para facilitar a identificação na lista.

Por exemplo, ao testar a posição do link Início na barra de navegação, nomeie a experiência em que aparece primeiro como &quot;Link inicial primeiro&quot;.

![Renomear uma experiência no painel Experiências](/help/main/c-experiences/c-visual-experience-composer/assets/rename_exp.png)

### Selecionar e modificar elementos {#select-and-modify-elements}

Mova o cursor sobre a página para realçar elementos individuais com uma caixa sensível ao contexto.

Clique em um elemento destacado para exibir as opções de edição desse tipo de elemento. Por exemplo, selecione uma imagem e clique em **[!UICONTROL Alterar origem da Imagem]** para substituí-la ou selecione um botão para alterar sua cor de texto.

![Opções de edição para um elemento selecionado](/help/main/c-experiences/c-visual-experience-composer/assets/properties-exp.png)

Não é possível editar o conteúdo dentro de um iframe incorporado na página. Para editar esse conteúdo, verifique se o documento do iframe está habilitado para [!DNL Target] e, em seguida, carregue o URL do iframe diretamente no VEC.

As alterações na estrutura da página fora do VEC podem afetar os locais usados por uma atividade. Se esses locais forem alterados, [!DNL Target] talvez não consiga encontrar os elementos modificados, o que pode causar problemas ao editar experiências.

### Navegação e design {#browse-and-design}

Clique em **[!UICONTROL Navegar]** para navegar para uma página acessível a partir da página atual, como uma página de remessa ou carrinho de compras, e testar as alterações nela.

![Modo de navegação no VEC](/help/main/c-experiences/c-visual-experience-composer/assets/browse_exp.png)

No modo Navegar, você também pode acessar elementos que aparecem ao passar o mouse, como menus flyout e minicarrinhos. Ao chegar na página ou elemento que deseja editar, clique em **[!UICONTROL Design]** para editar a experiência.

Se um estado de passar o mouse depender do JavaScript, certifique-se de que a opção **[!UICONTROL Desabilitar JavaScript]** não esteja selecionada. O JavaScript deve ser habilitado para editar elementos que dependem dele.

Para obter detalhes sobre as opções de edição disponíveis, consulte [Opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

## Gerenciar carregamento de página {#manage-page-loading}

Algumas opções de edição permanecem disponíveis enquanto uma página é carregada ou após uma falha de carregamento. Você também pode cancelar o carregamento da página para acessar essas opções sem esperar.

### Editar uma página enquanto ela está carregando ou após uma falha de carregamento {#loading}

Você pode fazer algumas alterações antes que uma página termine de ser carregada no VEC ou após uma falha no carregamento, por exemplo, porque o código personalizado não funciona mais.

Use as opções de edição disponíveis para:

* Fazer alterações simples, como adicionar código personalizado ou renomear uma experiência
* Copiar o código personalizado existente de uma página que não está mais acessível
* Faça edições simples em uma página que não pode ser carregada no VEC

O painel [!UICONTROL Experiências], o painel [!UICONTROL Componentes] e as opções [!UICONTROL Configurar] permanecem acessíveis enquanto a página é carregada ou após uma falha no carregamento.

### Cancelar carregamento de uma página no VEC {#cancel-loading}

Cancele o carregamento de página no VEC para editar a atividade sem esperar que a página termine de carregar.

Cancelar o carregamento da página é útil quando é necessário:

* Faça pequenas edições nas modificações existentes
* Excluir uma ou mais modificações existentes
* Inserir ou editar código personalizado
* Corrigir um URL de página inserido incorretamente
* Ative ou desative o JavaScript antes de carregar a página no VEC
* Adicionar regras de teste de modelo aos critérios de [!UICONTROL Entrega de página]
* Substitua o botão global [!UICONTROL Enhanced Experience Composer] (EEC) ao carregar uma página pelo EEC ou no modo somente iframe

Depois de cancelar o carregamento da página, você pode alternar entre experiências na atividade sem esperar que a página seja carregada. Clique em **[!UICONTROL Recarregar]** para exibir a página no VEC novamente.

>[!IMPORTANT]
>
>Se você editar o código personalizado ou fizer outras modificações após cancelar o carregamento da página, execute o teste de controle de qualidade (QA) para verificar se as alterações foram entregues conforme esperado.

Para interromper o carregamento da página, clique em **[!UICONTROL Cancelar o Carregamento]** enquanto a página estiver carregando. A página permanece descarregada para essa atividade durante a sessão de edição atual, a menos que você a recarregue.

Clique em **[!UICONTROL Recarregar]** para retomar o gerenciamento de experiências na atividade atual ou adicionar novas modificações.
