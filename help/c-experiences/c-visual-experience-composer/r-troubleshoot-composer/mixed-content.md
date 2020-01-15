---
keywords: mixed content;secure;insecure;chrome;troubleshooting;vec;visual experience composer;unsecure
description: Alguns navegadores bloqueiam a exibição de uma página se o conteúdo seguro estiver misturado com conteúdo inseguro.
title: Habilitar conteúdo misto em seu navegador
topic: Advanced,Standard,Classic
uuid: 6944ce97-ff73-4b61-b006-35862ff83ef1
translation-type: tm+mt
source-git-commit: 862966508fefaa935c7a5e64bc223e90cee80755

---


# Enabling mixed content in your browser{#enabling-mixed-content-in-your-browser}

Alguns navegadores bloqueiam a exibição de uma página se o conteúdo seguro estiver misturado com conteúdo inseguro.

Se o Visual Experience Composer (VEC) tentar abrir uma página com conteúdo (seguro e não seguro), uma mensagem é exibida mostrando como desativar o bloqueio no seu navegador, para que você possa abrir um site HTTP ou um site com chamadas mistas (HTTPS e HTTP).

![](assets/mixed_content_warning.gif)

Antes, quando um conteúdo misto não era permitido, você ainda poderia realizar algumas ações na Etapa 1 do fluxo de trabalho guiado de três etapas, ao criar atividades. O Target agora bloqueia as ações na Etapa 1. Quando essa mensagem é exibida, você deve ativar o conteúdo misto, antes de continuar.

As configurações de segurança do seu navegador pode bloquear o conteúdo misto ou não seguro (HTTP) carregado em uma página segura (HTTPS) ou quadro (como VEC). Se você não quiser desativar as configurações de segurança do seu navegador, é necessário ter um site HTTPS.

Se o seu site estiver executando em um domínio inseguro (HTTP), precisa permitir que o VEC carregue o conteúdo ativo misto.

>[!NOTE]
>
>Permitir o conteúdo misto afeta somente o VEC e não o site ativo.

Para obter mais informações, consulte [Conteúdo misto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) no site *Mozilla Developer Network* (MDN).

## Enabling mixed content in Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Se você está acessando um site através de uma conexão segura, o Google Chrome irá verificar se o conteúdo da página da Web foi transmitida em segurança.

<!-- 

target/t_mixed_content_chrome.xml

 -->

Consulte [Esta página possui conteúdo não seguro](https://support.google.com/chrome/answer/1342714?hl=en) na Ajuda do Chrome.

### Vídeo de treinamento: Habilitar VEC no Chrome (janeiro de 2020)

Se você estiver usando o VEC com a versão mais recente do Chrome (versão 79.0.3945.117 ou posterior), é necessário atualizar as configurações do site. Os visitantes do site não precisarão concluir essas etapas.

>[!VIDEO](https://www.youtube.com/watch?v=6zGCi5Y8eVo&feature=youtu.be)

O vídeo acima descreve as etapas necessárias:

1. Clique no ícone de bloqueio ou cuidado e clique em Configurações do site.

   ![Configurações do site](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Role até Conteúdo inseguro e use a lista suspensa para alterar Bloquear (padrão) para Permitir.

   ![Conteúdo inseguro](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Recarregue a página VEC.

## Enabling mixed content in Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

Por padrão, o Firefox bloqueia páginas que misturem conteúdo seguro e inseguro. É recomendável alterar essa definição permanentemente para usar o [!DNL Target].

<!-- 

target/t_mixed_content_firefox.xml

 -->

1. No Firefox, digite `about:config` na barra de endereços.
1. Confirme a mensagem de aviso exibida pelo Firefox.
1. Na barra de pesquisa, digite `block_active`.
1. Clique duas vezes em ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   O valor altera de &quot;Verdadeiro&quot; para &quot;Falso&quot;. Quando o valor mostrar &quot;Falso&quot;, você terá concluído. Recomenda-se reiniciar o computador após alterar essas definições.

## Enabling mixed content in Internet Explorer {#task_59E7D13C04DF486C92CD78D0C63DDDE8}

Por padrão, o Internet Explorer bloqueia páginas que misturem conteúdo seguro e inseguro. É recomendável alterar essa definição permanentemente para usar o Target Standard.

<!-- 

target/t_mixed_content_ie.xml

 -->

1. No Internet Explorer, clique no ícone de configurações > **[!UICONTROL Opções da Internet]**.
1. Abra a guia [!UICONTROL Segurança.]
1. Selecione **[!UICONTROL Internet]**e clique em**[!UICONTROL  Nível personalizado]**.
1. Selecione **[!UICONTROL Diversos]**.
1. Em [!UICONTROL Miscelânea]**[!UICONTROL , ative Exibir conteúdo misto]**.
1. Clique em **[!UICONTROL OK]**>**[!UICONTROL  Sim]** > **[!UICONTROL Aplicar]**.

Recomenda-se reiniciar o computador após alterar essas definições.

