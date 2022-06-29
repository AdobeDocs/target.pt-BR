---
keywords: conteúdo misto;seguro;inseguro;chrome;solução de problemas;vec;visual experience composer;não seguro;http;https;firefox;internet explorer
description: Saiba como ativar conteúdo misto no Chrome, Firefox e Edge. Você pode ativar conteúdo misto quando um navegador bloquear a exibição de uma página porque o conteúdo seguro é misturado com conteúdo inseguro.
title: Como ativar conteúdo misto no meu navegador
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
source-git-commit: 5e6bb16ad752b85e9a7dad088d15f5f6d3897ee9
workflow-type: tm+mt
source-wordcount: '593'
ht-degree: 93%

---

# Ativar conteúdo misto no navegador

O conteúdo misto ocorre se a solicitação inicial estiver segura por HTTPS, mas o conteúdo HTTPS *e* HTTP é carregado para exibir a página da Web. O conteúdo HTTPS é seguro. O conteúdo HTTP não é seguro.

Navegadores modernos podem bloquear a exibição de uma página ou exibir mensagens de aviso se o conteúdo seguro estiver misturado com conteúdo não seguro.

Uma mensagem de aviso será exibida se o [!UICONTROL Visual Experience Composer] (VEC) no [!DNL Adobe Target] tentar abrir uma página com conteúdo misto. Esta mensagem informa como desativar o bloqueio no navegador. Desativar o bloqueio permite abrir um site HTTP ou um site que tenha chamadas mistas (HTTPS e HTTP).

![Aviso de conteúdo misto](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Antes, quando um conteúdo misto não era permitido, você ainda poderia realizar algumas ações na Etapa 1 do fluxo de trabalho guiado de três etapas, ao criar atividades. O [!DNL Target] agora bloqueia as ações na Etapa 1. Quando essa mensagem é exibida, você deve ativar o conteúdo misto antes de criar a atividade.

As configurações de segurança do seu navegador pode bloquear o conteúdo misto ou não seguro (HTTP) carregado em uma página segura (HTTPS) ou quadro (como VEC). Se você não quiser desativar as configurações de segurança do seu navegador, é necessário ter um site HTTPS.

Se o seu site estiver executando em um domínio não seguro (HTTP), você precisa permitir que o VEC carregue o conteúdo ativo misto.

>[!NOTE]
>
>Permitir o conteúdo misto afeta somente o VEC e não o site ativo.

Para obter mais informações, consulte [Conteúdo misto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) no site *Mozilla Developer Network* (MDN).

## Habilitar conteúdo misto no Google Chrome {#task_FF297A08F66E47A588C14FD67C037B3A}

Se você está acessando um site através de uma conexão segura, o Chrome verifica se o conteúdo da página da Web foi transmitido em segurança.

Consulte “[Esta página tem conteúdo não seguro](https://support.google.com/chrome/answer/1342714?hl=pt)” na Ajuda do Google Chrome.

Se estiver usando o VEC com a versão mais recente do Chrome (versão 79.0.3945.117 ou posterior), você deve atualizar as configurações do site. Os visitantes do seu site não precisam concluir essas etapas.

1. Clique no ícone de bloqueio (cuidado) e clique em **[!UICONTROL Configurações do site]**.

   ![Configurações do site](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Role a tela até **[!UICONTROL Conteúdo não seguro]**, em seguida, use a lista suspensa para alterar “Bloquear (padrão)” para “Permitir”.

   ![Conteúdo não seguro](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Recarregue a página do VEC.

## Habilitar conteúdo misto no Mozilla Firefox {#task_5448763B8DC941FD80F84041AEF0A14D}

Por padrão, o Firefox bloqueia páginas que misturem conteúdo seguro e inseguro. É recomendável alterar essa definição permanentemente para usar o [!DNL Target]. Os visitantes do seu site não precisam concluir essas etapas.

1. No Firefox, digite `about:config` na barra de endereços.
1. Confirme a mensagem de aviso exibida pelo Firefox.

   ![Aviso do Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Na barra de pesquisa, digite `block_active`.

   ![Configuração de block_active do Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Clique duas vezes em ` **[!UICONTROL security.mixed_content.block_active_content]**`.

   O valor altera de &quot;Verdadeiro&quot; para &quot;Falso&quot;. Quando o valor mostrar &quot;Falso&quot;, você terá concluído. 

   ![Segurança do Firefox](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

Reinicie o computador depois de alterar esta configuração.

## Habilitar conteúdo misto no Microsoft Edge

Se você está acessando um site através de uma conexão segura, o Edge verifica se o conteúdo da página da Web foi transmitido em segurança.

Se você estiver usando o VEC com a versão mais recente do Edge, deverá atualizar as configurações do site.. Os visitantes do seu site não precisam concluir essas etapas.

1. Clique no ícone de bloqueio (cuidado) e clique em **[!UICONTROL Permissões do site]**.

   ![Permissões do site no Microsoft Edge](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge.png)

1. Role a tela até **[!UICONTROL Conteúdo não seguro]**, em seguida, use a lista suspensa para alterar “Bloquear (padrão)” para “Permitir”.

   ![Conteúdo não seguro](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/ms-edge-2.png)

1. Recarregue a página do VEC.
