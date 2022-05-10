---
keywords: conteúdo misto; seguro; inseguro; chrome; solução de problemas; vec; visual experience composer; não seguro; http; https; firefox; internet explorer
description: Alguns navegadores bloqueiam a exibição de uma página se o conteúdo seguro estiver misturado com conteúdo inseguro. Saiba como ativar conteúdo misto no Chrome, Firefox e Edge.
title: Como ativar conteúdo misto no meu navegador?
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 26%

---

# Ativar conteúdo misto no navegador

O conteúdo misto ocorre se a solicitação inicial estiver segura por HTTPS, mas por HTTPS *e* O conteúdo HTTP é carregado para exibir a página da Web. O conteúdo HTTPS é seguro. O conteúdo HTTP é inseguro.

Navegadores modernos podem bloquear a exibição de uma página ou exibir mensagens de aviso se o conteúdo seguro estiver misturado com conteúdo inseguro.

Uma mensagem de aviso será exibida se a variável [!UICONTROL Visual Experience Composer] (VEC) em [!DNL Target] O tenta abrir uma página com conteúdo misto. Esta mensagem informa como desativar o bloqueio no navegador. Desativar o bloqueio permite abrir um site HTTP ou um site que tenha chamadas mistas (HTTPS e HTTP).

![Aviso de conteúdo misto](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Antes, quando um conteúdo misto não era permitido, você ainda poderia realizar algumas ações na Etapa 1 do fluxo de trabalho guiado de três etapas, ao criar atividades. [!DNL Target]O agora bloqueia as ações na Etapa 1. Quando esta mensagem é exibida, você deve ativar o conteúdo misto antes de continuar criando a atividade.

As configurações de segurança do seu navegador pode bloquear o conteúdo misto ou não seguro (HTTP) carregado em uma página segura (HTTPS) ou quadro (como VEC). Se não quiser desativar as configurações de segurança do navegador, você deve ter um site HTTPS.

Se o site estiver sendo executado em um domínio inseguro (HTTP), você deverá permitir que o VEC carregue conteúdo ativo misto.

>[!NOTE]
>
>Permitir o conteúdo misto afeta somente o VEC e não o site ativo.

Para obter mais informações, consulte [Conteúdo misto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) no site *Mozilla Developer Network* (MDN).

## Ativar conteúdo misto no Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Se você estiver visitando um site por meio de uma conexão segura, o Chrome verificará se o conteúdo na página da Web foi transmitido com segurança.

Consulte &quot;[Esta página tem conteúdo inseguro](https://support.google.com/chrome/answer/1342714?hl=en)&quot; na Ajuda do Google Chrome.

Se estiver usando o VEC com a versão mais recente do Chrome (versão 79.0.3945.117 ou posterior), você deve atualizar as configurações do site. Os visitantes do seu site não precisam concluir essas etapas.

1. Clique no ícone de bloqueio (cuidado) e clique em **[!UICONTROL Configurações do site]**.

   ![Configurações do site](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Rolar para **[!UICONTROL Conteúdo inseguro]**, em seguida, use a lista suspensa para alterar &quot;Bloqueio (padrão)&quot; para &quot;Permitir&quot;.

   ![Conteúdo inseguro](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Recarregue a página do VEC.

## Ativar conteúdo misto no Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

Por padrão, o Firefox bloqueia páginas que misturem conteúdo seguro e inseguro. É recomendável alterar essa definição permanentemente para usar o [!DNL Target]. Os visitantes do seu site não precisam concluir essas etapas.

1. No Firefox, digite `about:config` na barra de endereços.
1. Confirme a mensagem de aviso exibida pelo Firefox.

   ![Aviso do Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Na barra de pesquisa, digite `block_active`.

   ![Configuração de bloco_ativo do Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Clique duas vezes em ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   O valor altera de &quot;Verdadeiro&quot; para &quot;Falso&quot;. Quando o valor mostrar &quot;Falso&quot;, você terá concluído. 

   ![Segurança do Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

Reinicie o computador depois de alterar esta configuração.

## Ativar conteúdo misto no Microsoft Edge

Se você estiver visitando um site por meio de uma conexão segura, o Edge verificará se o conteúdo na página da Web foi transmitido com segurança.

Se você estiver usando o VEC com a versão mais recente do Edge, deverá atualizar as configurações do site. Os visitantes do seu site não precisam concluir essas etapas.

1. Clique no ícone de bloqueio (cuidado) e clique em **[!UICONTROL Permissões do site]**.

   ![Permissões do site no Microsoft Edge](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Rolar para **[!UICONTROL Conteúdo inseguro]**, em seguida, use a lista suspensa para alterar &quot;Bloquear (padrão)&quot; para &quot;Permitir&quot;.

   ![Conteúdo inseguro](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Recarregue a página do VEC.