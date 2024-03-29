---
keywords: Direcionamento;visual experience composer;vec;solucionar problemas do visual experience composer;solução de problemas;tls;tls 1.2
description: Saiba como solucionar problemas que às vezes ocorrem no Adobe [!DNL Target] Visual Experience Composer (VEC) do sob determinadas condições.
title: Como solucionar problemas relacionados ao Visual Experience Composer?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 67%

---

# Solução de problemas relacionados ao Visual Experience Composer

Problemas de exibição às vezes ocorrem no [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) em determinadas condições.

## Quando abro meu site no Visual Experience Composer, a variável [!DNL Target] As bibliotecas do não carregam. (Somente VEC)  {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

O Target adiciona dois parâmetros (`mboxEdit=1` e `mboxDisable=1`) ao abrir o site no Visual Experience Composer.

Se o site (principalmente, Aplicativos de página única) corta nossos parâmetros ou os remove ao navegar de uma página a outra (sem um recarregamento de página), a funcionalidade do Target é interrompida e as bibliotecas do Target não são carregadas. 
Para evitar esse problema, assegure-se de não cortar ou remover esses dois parâmetros.

## Minha página não abre no EEC ou carrega lentamente. As atividades ou experiências são carregadas de forma lenta no VEC. (Somente VEC)  {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Vários problemas podem afetar o desempenho da página nos compositores de experiência do Target. Alguns erros comuns incluem:

* Você não tem uma mbox na página.
* Seu site usa o bloqueio de proxy, que não permite que a página seja aberta em nenhum compositor de experiência.
* Seu site não pode ser aberto em um iFrame.

Se ocorrerem problemas no Enhanced Experience Composer, tente desativá-lo e usar o Visual Experience Composer.

Para desativar o Enhanced Experience Composer, acesse **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]** e desative o **[!UICONTROL Ativar o Enhanced Experience Composer]** opção.

Alguns usuários veem a seguinte mensagem de erro no console:

![Mensagem de erro do console](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Se nem o Visual Experience Composer nem o Enhanced Experience Composer funcionarem, use uma extensão de navegador como Requestly (Chrome ou Firefox) ou Modify Response Headers (Firefox), que podem substituir as opções de cabeçalho X-Frames para o site e permitir que sejam carregadas nos iFrames, habilitando o VEC. Se não conseguir usar as extensões do navegador, use o compositor de formulário.

>[!NOTE]
>
>Além das seguintes informações, você pode usar a extensão de navegador [Adobe Target VEC Helper](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para Google Chrome.


>[!NOTE]
>
>Estes plugins devem ser usados somente no contexto da edição VEC.
>
>Para a extensão Requestly, sempre que houver a necessidade de remover cabeçalhos, você deve fazer o seguinte:
>
>* Adicione regras de URL ao URL que você deseja abrir no VEC, para que os cabeçalhos sejam removidos apenas para esses URLs.
>
>* Habilite a regra quando estiver editando no VEC e desabilite a regra quando não estiver usando o VEC.
>
>Para a extensão Modify Response Header (Firefox), já que você não pode adicionar uma regra de URL, deve fazer o seguinte:
>
>* Habilite a regra quando estiver editando no VEC e desabilite a regra quando não estiver usando o VEC.


**Para usar a extensão Requestly no Chrome ou no Firefox:**

1. Desative o Enhanced Experienced Composer.
1. Instale a extensão de navegador Requestly no Chrome ou no Firefox.
1. Abra a extensão e configure-a usando o seguinte:
1. Selecione **[!UICONTROL Modificar cabeçalhos]**.
1. Digite o seguinte:

   * Nome da regra
   * Regras de modificação

      * Alterne **[!UICONTROL Adicionar]** para **[!UICONTROL Remover]**.
      * Alterne **[!UICONTROL Solicitação]** para **[!UICONTROL Resposta]**.
      * Digite &quot;X-Frame-Options&quot; como o nome do cabeçalho.
      * Repita as etapas anteriores e digite &quot;x-frame-options&quot; como nome do cabeçalho.

         >[!NOTE]
         >
         >Os cabeçalhos manipulados pelo Requestly diferenciam maiúsculas de minúsculas.

      * Altere **[!UICONTROL Igual a]** para **[!UICONTROL Contém]** como a condição para o URL de origem e insira o URL da atividade que você está tentando carregar no VEC.

      ![imagem chrome_extension](assets/chrome_extension.png)


1. Clique em **[!UICONTROL Salvar]**.

   ![imagem requestly](assets/requestly.png)

   Agora, você deve conseguir carregar a página rapidamente com o Visual Experience Composer.

**Para usar a extensão Modify Response Headers no Firefox:**

1. Instale a extensão Modify Response Headers no Firefox e reinicie o navegador.
1. Nas extensões do Firefox, selecione a extensão Modify Response Headers.
1. Clique em **[!UICONTROL Preferências]**.
1. Selecione **[!UICONTROL Filtro]** no menu suspenso Ação.
1. No campo Nome do cabeçalho, digite: **[!UICONTROL X-Frame-Options]**.
1. Repita as etapas 4 e 5 para adicionar um filtro com **[!UICONTROL x-frame-options]**.
1. Clique em **[!UICONTROL Adicionar]**.
1. Clique em **[!UICONTROL Iniciar]**.

![imagem firefox_extension](assets/firefox_extension.png)

Depois de configurar uma extensão, abra o Target. Suas páginas devem ser carregadas no Visual Experience Composer, mesmo que o Enhanced Experience Composer esteja desativado.

## Minha página não é exibida no VEC (somente VEC)  {#does-not-load}

* Não há suporte para o navegador.
* O navegador está bloqueando uma página não segura em um site seguro.

   Clique no ícone à esquerda do URL na barra de endereço do navegador e clique em **[!UICONTROL Desativar proteção nesta página]**
* Você inseriu um URL inválido.
* Você não inseriu um URL padrão na sua página de configuração de conta.

   Certifique-se de que essa configuração esteja ativada, baixe e atualize o at.js no site.

* Se você tentar usar o [novo [!UICONTROL Auxiliar de edição visual] extensão](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) e volte para a guia [extensão antiga](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) e [!DNL Target] falha ao carregar seu site, apagar todos os dados do navegador e desativar a nova extensão.

* Se o site falhar ao carregar no VEC ou se comportar inesperadamente, uma possível correção é aceitar cookies em seu site no navegador antes de tentar carregar o site no [!DNL Target].

## O VEC aparece interrompido quando uso o modo de navegação. (Somente VEC)  {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

Ao usar o modo de navegação, se você acessar um URL que não tenha [!DNL Target] bibliotecas implementadas ([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}) ou contém um cabeçalho frame-buster, o VEC parece quebrado. Devido a preocupações com a segurança do navegador, [!DNL Target] O não pode acessar corretamente o URL para o qual você navegou ou o URL do VEC não é atualizado de forma consistente se a página for carregada.

Esse problema ocorre porque o VEC carrega a página da Web em uma `<iframe>`. Os mecanismos de segurança atuais dos navegadores impedem que [!DNL Target] Impedir a interface de acessar os elementos do quadro fornecido devido à política de mesma origem. Os navegadores bloqueiam scripts que tentam acessar um quadro com uma origem diferente e que inclui informações como `location.href`.

Você deve usar o novo [Extensão Auxiliar de edição visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) (recomendado) ou o [extensão antiga](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para injetar o [!DNL Target] nas páginas para navegá-las de maneira ideal.
