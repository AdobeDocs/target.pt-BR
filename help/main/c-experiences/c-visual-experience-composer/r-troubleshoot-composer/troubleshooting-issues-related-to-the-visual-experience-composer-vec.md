---
keywords: Direcionamento;visual experience composer;vec;solucionar problemas do visual experience composer;solução de problemas;tls;tls 1.2
description: Saiba como solucionar problemas no [!UICONTROL Visual Experience Composer] (VEC).
title: Como solucionar problemas relacionados ao [!UICONTROL Visual Experience Composer]?
feature: Visual Experience Composer (VEC)
exl-id: ca251025-25e8-4e56-9b59-81310fc763c1
source-git-commit: 7c0d0154b81fbd3f89a82b31cd18541a7f0ea1a7
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 24%

---

# Solução de problemas relacionados ao [!UICONTROL Visual Experience Composer]

Problemas de exibição às vezes ocorrem no [!DNL Adobe Target] [!UICONTROL Visual Experience Composer] (VEC) em determinadas condições.

## Quando eu abrir meu site na [!UICONTROL Visual Experience Composer], o [!DNL Target] As bibliotecas do não carregam. (Somente VEC)  {#section_8A7D3F4AD2CC4C3B823EE9432B97E06F}

[!DNL Target] adiciona dois parâmetros (`mboxEdit=1` e `mboxDisable=1`) ao abrir o site na [!UICONTROL Visual Experience Composer].

Se o site (principalmente, Aplicativos de página única) corta parâmetros ou os remove ao navegar de uma página a outra (sem um recarregamento de página), o [!DNL Target] A funcionalidade do falha e o [!DNL Target] As bibliotecas do não carregam.

Para evitar esse problema, assegure-se de não cortar ou remover esses dois parâmetros.

## Minha página não abre no EEC ou carrega lentamente. As atividades ou experiências são carregadas de forma lenta no VEC. (Somente VEC)  {#section_71E7601BE9894E3DA3A7FBBB72B6B0C1}

Vários problemas podem afetar o desempenho da página no [!UICONTROL Target] compositores de experiência. Alguns erros comuns incluem:

* Você não tem uma mbox na página.
* Seu site usa o bloqueio de proxy, que não permite que a página seja aberta em nenhum compositor de experiência.
* Seu site não pode ser aberto em um iFrame.

Se ocorrerem problemas no [!UICONTROL Enhanced Experience Composer], tente desativar o [!UICONTROL Enhanced Experience Composer] e use o [!UICONTROL Visual Experience Composer] em vez disso.

Para desativar o [!UICONTROL Enhanced Experience Composer], vá para **[!UICONTROL Administration]** > **[!UICONTROL Visual Experience Composer]** e desative o **[!UICONTROL Enable Enhanced Experience Composer]** opção.

Alguns usuários veem a seguinte mensagem de erro no console:

![Mensagem de erro do console](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/console_error_message.jpg)

Se nenhuma das duas opções [!UICONTROL Visual Experience Composer] nem a [!UICONTROL Enhanced Experience Composer] funciona, use uma extensão de navegador como [!DNL Requestly] ([!DNL Chrome] ou [!DNL Firefox]) ou Modificar cabeçalhos de resposta (Firefox) que podem substituir as opções de cabeçalho X-Frames para o site e permitir que sejam carregados em iFrames, habilitando o VEC. Se não conseguir usar as extensões do navegador, use o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

>[!NOTE]
>
>Além das seguintes informações, você pode usar a variável [[!DNL Adobe Target] [!UICONTROL Visual Editing Helper] extensão](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) para [!DNL Google Chrome].


>[!NOTE]
>
>Estes plugins devem ser usados somente no contexto da edição VEC.
>
>Para o [!DNL Requestly] extensão, sempre que houver necessidade de remover cabeçalhos, siga um destes procedimentos:
>
>* Adicione regras de URL ao URL que você deseja abrir no VEC, para que os cabeçalhos sejam removidos apenas para esses URLs.
>
>* Habilite a regra quando estiver editando no VEC e desabilite a regra quando não estiver usando o VEC.
>
>Para o [!UICONTROL Modify Response Header] extensão ([!DNL Firefox]), como não é possível adicionar uma regra de URL, faça o seguinte:
>
>* Habilite a regra quando estiver editando no VEC e desabilite a regra quando não estiver usando o VEC.

**Para usar o [!DNL Requestly] extensão ativada [!DNL Chrome] ou [!DNL Firefox]:**

1. Desative o [!UICONTROL Enhanced Experienced Composer].
1. Instale o [!DNL Requestly] extensão do navegador ativada [!DNL Chrome] ou [!DNL Firefox].
1. Abra a extensão e configure-a usando o seguinte:
1. Selecionar **[!UICONTROL Modify headers]**.
1. Digite o seguinte:

   * Nome da regra
   * Regras de modificação

      * Alternar **[!UICONTROL Add]** para **[!UICONTROL Remove]**.
      * Alternar **[!UICONTROL Request]** para **[!UICONTROL Response]**.
      * Digite &quot;X-Frame-Options&quot; como o nome do cabeçalho.
      * Repita as etapas anteriores e digite &quot;x-frame-options&quot; como nome do cabeçalho.

        >[!NOTE]
        >
        >Cabeçalhos manipulados via [!DNL Requestly] fazem distinção entre maiúsculas e minúsculas.

      * Alterar **[!UICONTROL Equals]** para **[!UICONTROL Contains]** como condição para o URL de origem e insira o URL da atividade que você está tentando carregar no VEC.

     ![imagem chrome_extension](assets/chrome_extension.png)

1. Clique em **[!UICONTROL Save]**.

   ![imagem requestly](assets/requestly.png)

   Agora é possível carregar a página rapidamente com o [!UICONTROL Visual Experience Composer].

**Para usar o [!DNL Modify Response Headers] extensão ativada [!UICONTROL Firefox]:**

1. Instale o [!UICONTROL Modify Response Headers] em [!DNL Firefox] e reinicie o navegador.
1. Do seu [!DNL Firefox] extensões, selecione a extensão Modificar Cabeçalhos de Resposta.
1. Clique em **[!UICONTROL Preferences]**.
1. Selecionar **[!UICONTROL Filter]** do [!UICONTROL Action] lista suspensa.
1. No [!UICONTROL Header Name] insira: **[!UICONTROL X-Frame-Options]**.
1. Repita as etapas 4 e 5 para adicionar um filtro com **[!UICONTROL x-frame-options]**.
1. Clique em **[!UICONTROL Add]**.
1. Clique em **[!UICONTROL Start]**.

![Extensão do Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox_extension.png)

Depois de configurar uma extensão, abra [!DNL Target]. Suas páginas agora devem ser carregadas no [!UICONTROL Visual Experience Composer], mesmo que o [!UICONTROL Enhanced Experience Composer] está desativado.

## Minha página não é exibida no VEC (somente VEC)  {#does-not-load}

* A melhor compatibilidade com o VEC é garantida pela versão mais recente da extensão: [[!DNL Adobe Experience Cloud] [!UICONTROL Visual Editing Helper extension]](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md).

  Para verificar se você está usando a versão mais recente, acesse [!UICONTROL Extensions] > [!UICONTROL Manage Extensions] e clique em [!UICONTROL Details].

* A variável [!UICONTROL Visual Experience Composer] O requer a criação de bibliotecas para realizar modificações na página da web. Essas bibliotecas são incorporadas à biblioteca at.js do e baixadas pela extensão do [!DNL Adobe] sempre que o VEC for usado.

  A extensão baixa a biblioteca at.js independentemente de at.js ou [!DNL Adobe Experience Platform Web SDK] já estão incluídos na página.

  Verifique se não há alterações inválidas adicionadas aos cabeçalhos do at.js configurados no [!UICONTROL Administration] > [!UICONTROL Implementation] seção.

* Certifique-se de que a página da Web não esteja bloqueando solicitações obrigatórias para carregamento quando incorporada a um iFrame. Isso inclui o uso de diretivas CSP frame-ancestors ou o código JS personalizado incorporado no site do cliente, tags meta HTML ou o cabeçalho x-frame-options.

* Certifique-se de que o JavaScript da página da Web não interfira nas bibliotecas de criação. Não use ou inclua arquivos usando os seguintes nomes reservados:

   * `target-vec-helper.js`
   * `target-vec.js`
   * `target.js`
   * `admin.css`
   * `sizzle.js`
   * `mixContentCheck.html`

     Além disso, a substituição acidental de variáveis ou eventos definidos nesses arquivos pode levar a problemas com o VEC.

* O navegador está bloqueando uma página não segura em um site seguro.

  Clique no ícone à esquerda do URL na barra de endereços do navegador e clique em **[!UICONTROL Disable protection on this page]**

* Você inseriu um URL inválido.
* Se o site falhar ao carregar no VEC ou se comportar inesperadamente, uma possível correção é aceitar cookies em seu site no navegador antes de tentar carregar o site no [!DNL Target].

## O VEC aparece interrompido quando uso o modo de navegação. (Somente VEC)  {#section_FA2A18E8FD6A4274B2E395DBAA2FB407}

Ao usar o modo de navegação, se você acessar um URL que não tenha [!DNL Target] bibliotecas implementadas ([at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=pt-BR){target=_blank} or [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}) ou contém um cabeçalho frame-buster, o VEC parece quebrado. Devido a preocupações com a segurança do navegador, [!DNL Target] O não pode acessar corretamente o URL para o qual você navegou ou o URL do VEC não é atualizado de forma consistente se a página for carregada.

Esse problema ocorre porque o VEC carrega a página da Web em uma `<iframe>`. Os mecanismos de segurança atuais dos navegadores impedem que [!DNL Target] Impedir a interface de acessar os elementos do quadro fornecido devido à política de mesma origem. Os navegadores bloqueiam scripts que tentam acessar um quadro com uma origem diferente e que inclui informações como `location.href`.

Você deve usar o novo [Extensão Auxiliar de edição visual](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/visual-editing-helper-extension.md) (recomendado) ou o [extensão antiga](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/vec-helper-browser-extension.md) para injetar o [!DNL Target] nas páginas para navegá-las de maneira ideal.

## Problemas causados por conflitos CSS no [!UICONTROL Visual Experience Composer]

Verifique se há algum arquivo CSS que possa afetar a visibilidade ao carregar a página da Web no editor. Por exemplo, usando o `overflow: hidden` no corpo da página pode levar a problemas de rolagem ou acionar eventos de clique que podem interferir no menu de criação.
