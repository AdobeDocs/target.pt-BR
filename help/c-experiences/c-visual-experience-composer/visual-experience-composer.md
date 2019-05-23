---
description: Informações sobre o uso do Visual Experience Composer (VEC).
seo-description: Informações sobre o uso do Visual Experience Composer (VEC) no Adobe Target.
seo-title: Visual Experience Composer (VEC) do Adobe Target
title: Visual Experience Composer (VEC)
uuid: f1e6f67e-1d7e-4806-8389-2ce165b534b4
translation-type: tm+mt
source-git-commit: f59e96cd5afcae9d27d730aecead9eb360f04026

---


# Visual Experience Composer (VEC){#visual-experience-composer-vec}

Informações sobre o uso do Visual Experience Composer (VEC).

O VEC é um dos principais recursos do [!DNL Adobe Target]. O VEC é um editor que permite aos comerciantes e designers criar e alterar conteúdo usando uma interface visual. Muitas escolhas de design podem ser feitas sem necessitar de edição direta do código. A edição de HTML e JavaScript também é possível usando as opções de edição disponíveis no compositor.

No Target, na guia **[!UICONTROL Configuração]** &gt; **[!UICONTROL Preferências]**, você pode inserir o URL do Visual Experience Composer.

![Configurações padrão de URL de VEC](/help/c-experiences/c-visual-experience-composer/assets/pref-default-url-new.png)

Esse URL determina onde você começa quando abre o VEC. Se não inserir um padrão, você começará com uma página em branco quando abrir o editor e especificar um URL nesse momento.

>[!NOTE]
>
>Determinados navegadores, como o Firefox, podem bloquear a exibição de uma página no VEC se a página contiver conteúdo misto (por exemplo, uma página não segura em um site seguro). Se a página não for exibida, clique no ícone ao lado do URL na barra de endereço do navegador e clique **[!UICONTROL em Desativar proteção nesta página]**. Esse problema não afeta a exibição das suas páginas para os visitantes do site.

O conteúdo dentro de um iframe na página não pode ser modificado no VEC. Para editar o conteúdo em um iframe, certifique-se de que o documento iframe esteja habilitado para o Target e carregue esse URL do iframe no VEC.

Você pode usar os menus suspensos na parte superior da página para ver como sua página aparecerá para públicos-alvo diferentes ou com experiências diferentes. Você pode fornecer um nome para cada experiência na segunda lista suspensa. Por exemplo, se você estiver testando o local do link Início na sua barra de navegação, poderá nomear uma experiência em que esse link aparecerá primeiro como algo como &quot;link Início&quot; para facilitar a identificação das experiências na lista.

>[!NOTE]
>
>As alterações na estrutura de uma página que afetam os locais usados em uma atividade criada nessa página podem causar problemas com a edição de experiência. Se um local foi alterado fora do VEC, o Target pode não ser capaz de encontrar o local onde o conteúdo foi alterado.

Ao mover seu mouse pela página, uma caixa sensível ao contexto segue o cursor, destacando os elementos na página.

![Destaque VEC](/help/c-experiences/c-visual-experience-composer/assets/vec-highlight-new.png)

Clique no ícone **[!UICONTROL Sobreposições]** para alterar a forma como o destaque é exibido. Por exemplo, você pode optar por destacar apenas imagens, links, mboxes regionais, modificações ou javascript. É possível alterar a cor do destaque. Você também pode especificar a cor de um destaque e o tipo de preenchimento usado para destacar tipos de elementos diferentes.

![Alterar configurações de sobreposição](/help/c-experiences/c-visual-experience-composer/assets/change-overlay.png)

Clique em um elemento realçado para um menu de opções disponíveis para esse tipo de elemento. Por exemplo, você pode clicar em uma imagem e selecionar **[!UICONTROL Editar &gt; Texto/HTML]** para alterar o texto, ou clicar em um botão e alterar a cor do plano de fundo. Você pode usar os botões na parte esquerda superior da página para ligar e desligar as sobreposições.

Você também pode clicar em **[!UICONTROL Navegar]**, depois navegar para uma página que esteja disponível a partir da página primária, como uma página de remessa ou carrinho de compras, e testar as alterações nessa página. Você também pode acessar elementos de página que estão disponíveis quando passa o mouse, como menus flyout e minicarrinhos. Quando você terminar de navegar na página, clique em **[!UICONTROL Compor]** para editar a experiência. Por exemplo, talvez você queira alterar o design do menu suspenso de um carrinho de compras ou de um carrossel de imagens.

>[!NOTE]
>
>Se um estado de passar o mouse depender do JavaScript, verifique se a opção **[!UICONTROL Desativar JavaScript]** não está selecionada. O JavaScript deve ser ativado para editar elementos de JavaScript.

Para obter informações sobre as opções disponíveis no VEC, consulte [Opções do Visual Experience Composer](../../c-experiences/c-visual-experience-composer/viztarget-options.md#reference_3BD1BEEAFA584A749ED2D08F14732E81).

Você pode realizar algumas modificações em uma página enquanto a página está carregando (ou depois que a página não é carregada) ou pode cancelar o carregamento da página no VEC. Para obter mais informações, consulte:

* [Editar uma página enquanto a página está carregando ou depois que a página não carregar](#loading)
* [Cancelar carregamento de uma página no VEC](#cancel-loading)

## Editar uma página enquanto a página está carregando ou depois que a página não carregar {#loading}

É possível executar muitas ações antes que a página seja carregada no VEC ou até mesmo se a página não carregar completamente (por exemplo, o código personalizado não é mais operacional).

Alguns motivos pelos quais você pode querer acessar ou fazer edições em uma página enquanto está carregando no VEC ou depois de falhar no carregamento:

* Você deseja fazer uma modificação simples em uma página, como adicionar código personalizado ou alterar o nome de uma experiência
* Você deseja copiar o código personalizado existente de uma página que não está mais acessível
* Você sabe que uma página não carregará no VEC, mas deseja fazer edições simples

Enquanto a página é carregada (ou após a falha ao carregar), o [!UICONTROL painel Experiências] , [!UICONTROL o] painel Modificações e as configurações na parte superior da experiência (Overlays, Modificações, Configurar e assim por diante) ficam acessíveis.

A ilustração a seguir mostra que você pode inserir um código personalizado ou executar outras ações enquanto a página ainda está carregando:

![Carregamento de página](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/loading-page.png)

## Cancelar carregamento de uma página no VEC {#cancel-loading}

Você pode cancelar o carregamento de uma página no VEC para desbloquear a edição da atividade sem aguardar a carga da página. Esse recurso economiza tempo e ajuda você a efetuar edições simples ou inserir um código personalizado com mais eficiência sem esperar que a página seja carregada no VEC.

Alguns motivos pelos quais você pode cancelar o carregamento de página no VEC incluem:

* Você deseja fazer pequenas edições em modificações existentes
* Você deseja excluir uma ou mais modificações existentes
* Você deseja inserir ou editar código personalizado
* Você inseriu erroneamente o URL incorreto da página
* Você deseja ativar ou desativar o javascript antes de carregar a página no VEC
* Você deseja adicionar mais regras de teste de modelo aos critérios de Entrega de página
* Você deseja substituir o comando global Enhanced Experience Composer (EEC) ao carregar uma página pela EEC ou somente iframe pode depender de uma página na página

Depois de cancelar o carregamento de página no VEC, você pode alternar entre experiências na atividade sem esperar que a página seja carregada. Para visualizar a página no VEC novamente, clique no botão **[!UICONTOL Recarregar]** .

>[!IMPORTANT]
>
>Observe que quando o código personalizado ou qualquer modificação é feita, ao optar por cancelar o carregamento no VEC, você deve garantir que sua codificação ou alterações sejam feitas corretamente. Certifique-se de executar o QA correto para garantir que seu código personalizado e outras modificações sejam entregues conforme esperado.

Para cancelar o carregamento de uma página no VEC, clique no botão **[!UICONTROL Cancelar carregamento]** enquanto a página estiver carregando. A página não será carregada no VEC para essa atividade durante a sessão de edição atual.

![Cancelar o carregamento do botão](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/cancel-loading.png)

Para continuar o gerenciamento de experiências na atividade atual ou para adicionar novas modificações, clique no **[!UICONTROL botão Recarregar]** .

![Botão Recarregar](/help/c-experiences/c-visual-experience-composer/c-vec-code-editor/assets/reload-in-vec.png)

>[!NOTE]
>
>Há um problema conhecido atual com este recurso que será corrigido na próxima versão. Para obter mais informações, consulte &quot;Cancelar carregamento de uma página no VEC&quot; nos problemas [conhecidos e na página de problemas](/help/r-release-notes/known-issues-resolved-issues.md#cancel) resolvidos.

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Visual Experience Composer (7:17)

Este vídeo fornece informações sobre o uso das opções do Visual Experience Composer.

* Alterar o conteúdo de uma página
* Alterar o layout de uma página

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Visual Experience Composer (1 de 2) (7:17)

* Alterar o conteúdo de uma página
* Alterar o layout de uma página

>[!VIDEO](https://video.tv.adobe.com/v/17399)

### Visual Experience Composer (2 de 2) (7:29)

* Renomear e duplicar uma experiência
* Criar uma experiência de redirecionamento
* Direcionar uma atividade para um único URL ou um grupo de URLs
* Criar uma atividade multipáginas
* Visualizar e criar a experiência para sites responsivos
* Use sobreposições para destacar tipos de elementos

>[!VIDEO](https://video.tv.adobe.com/v/17401)

### No expediente: Visual Experience Composer

Este vídeo é uma gravação do &quot;[No expediente](../../cmp-resources-and-contact-information.md#concept_58EA30379D3B48C4848BA2A8C464A5B7)&quot;, uma iniciativa da equipe de Atendimento ao cliente da Adobe.

* Como funciona o VEC
* Como evitar problemas comuns com o VEC
* Práticas de correção que podem ser usadas com o VEC

>[!VIDEO](https://video.tv.adobe.com/v/20784/)