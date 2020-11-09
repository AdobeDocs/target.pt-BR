---
keywords: mixed content;secure;insecure;chrome;troubleshooting;vec;visual experience composer;unsecure;http;https;firefox;internet explorer
description: Alguns navegadores bloqueiam a exibição de uma página se o conteúdo seguro estiver misturado com conteúdo inseguro.
title: Habilitar conteúdo misto em seu navegador
feature: vec
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 35%

---


# Enabling mixed content in your browser{#enabling-mixed-content-in-your-browser}

O conteúdo misto ocorre se o conteúdo HTTPS (seguro) ** e HTTP (inseguro) for carregado para exibir a mesma página da Web e a solicitação inicial estiver protegida em HTTPS.

Os navegadores modernos podem bloquear a exibição de uma página ou exibir mensagens de aviso se o conteúdo protegido estiver misturado a conteúdo inseguro.

If the [!UICONTROL Visual Experience Composer] (VEC) in [!DNL Target] tries to open a page containing mixed content, a message displays showing how to disable blocking in your browser so you can open an HTTP site or a site that has mixed calls (HTTPS and HTTP).

![aviso de conteúdo misto](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Antes, quando um conteúdo misto não era permitido, você ainda poderia realizar algumas ações na Etapa 1 do fluxo de trabalho guiado de três etapas, ao criar atividades. [!DNL Target]O agora bloqueia as ações na Etapa 1. Quando essa mensagem for exibida, você deverá ativar o conteúdo misto antes de continuar a criar a atividade.

As configurações de segurança do seu navegador pode bloquear o conteúdo misto ou não seguro (HTTP) carregado em uma página segura (HTTPS) ou quadro (como VEC). Se você não quiser desativar as configurações de segurança do seu navegador, é necessário ter um site HTTPS.

Se o seu site estiver executando em um domínio inseguro (HTTP), precisa permitir que o VEC carregue o conteúdo ativo misto.

>[!NOTE]
>
>Permitir o conteúdo misto afeta somente o VEC e não o site ativo.

Para obter mais informações, consulte [Conteúdo misto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) no site *Mozilla Developer Network* (MDN).

## Enabling mixed content in Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Se você estiver visitando um site por uma conexão segura, o Chrome verificará se o conteúdo da página da Web foi transmitido com segurança.

Consulte [Esta página possui conteúdo não seguro](https://support.google.com/chrome/answer/1342714?hl=en) na Ajuda do Chrome.

Se você estiver usando o VEC com a versão mais recente do Chrome (versão 79.0.3945.117 ou posterior), é necessário atualizar as configurações do site. Os visitantes do site não precisam concluir essas etapas.

1. Clique no ícone de bloqueio ou cuidado e, em seguida, clique em Configurações **** do site.

   ![Configurações do site](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Role até Conteúdo **** inseguro e use a lista suspensa para alterar &quot;Bloquear (padrão)&quot; para &quot;Permitir&quot;.

   ![Conteúdo inseguro](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Recarregue a página VEC.

## Enabling mixed content in Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

Por padrão, o Firefox bloqueia páginas que misturem conteúdo seguro e inseguro. É recomendável alterar essa definição permanentemente para usar o [!DNL Target]. Os visitantes do site não precisam concluir essas etapas.

1. No Firefox, digite `about:config` na barra de endereços.
1. Confirme a mensagem de aviso exibida pelo Firefox.

   ![Aviso Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Na barra de pesquisa, digite `block_active`.

   ![Configuração ativa do bloco Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Clique duas vezes em ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   O valor altera de &quot;Verdadeiro&quot; para &quot;Falso&quot;. Quando o valor mostrar &quot;Falso&quot;, você terá concluído. 

   ![Segurança do Firefox](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

Recomendamos que você reinicie o computador após alterar essa configuração.

## Habilitar conteúdo misto no Microsoft Edge

Se você estiver visitando um site por uma conexão segura, o Edge verificará se o conteúdo da página da Web foi transmitido com segurança.

Se estiver usando o VEC com a versão mais recente do Edge, é necessário atualizar as configurações do site. Os visitantes do site não precisam concluir essas etapas.

1. Clique no ícone de bloqueio ou cuidado e, em seguida, clique em Permissões **** do site.

   ![Permissões do site no Microsoft Edge](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Role até Conteúdo **** inseguro e use a lista suspensa para alterar &quot;Bloquear (padrão)&quot; para &quot;Permitir&quot;.

   ![Conteúdo inseguro](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Recarregue a página VEC.