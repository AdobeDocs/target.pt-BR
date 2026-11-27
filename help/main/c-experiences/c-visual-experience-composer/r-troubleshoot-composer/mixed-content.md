---
keywords: conteúdo misto;seguro;inseguro;chrome;solução de problemas;vec;visual experience composer;inseguro;http;https;firefox;internet explorer
description: Saiba como habilitar conteúdo misto em [!DNL Chrome], [!DNL Firefox] e [!DNL Edge].
title: Como habilitar conteúdo misto no meu navegador
feature: Visual Experience Composer (VEC)
exl-id: a2209af6-65e5-427e-b2cb-53b803728ef3
TQID: 'https://experienceleague.adobe.com/6Q1UvNmU-vSr9sp3pe2JN-wkjFUMWFxtPkgQegArrVw'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
    internal-label: Security
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 11%
---
# Habilitar conteúdo misto no navegador {#mixed-content}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como habilitar conteúdo misto no [!DNL Google Chrome], [!DNL Mozilla Firefox] e [!DNL Microsoft Edge], para que o **[!UICONTROL Visual Experience Composer]** (VEC) possa abrir sites HTTP e sites que tenham conteúdo misto.

>[!ENDSHADEBOX]

Uma página tem conteúdo misto quando é solicitada com segurança por HTTPS, mas carrega conteúdo HTTPS e HTTP. O conteúdo HTTPS é seguro, enquanto o conteúdo HTTP não é, portanto, os navegadores modernos podem bloquear essa página ou exibir uma mensagem de aviso.

Quando o **[!UICONTROL Visual Experience Composer]** (VEC) no [!DNL Adobe Target] tenta abrir uma página com conteúdo misto, uma mensagem de aviso é exibida com instruções para desabilitar o bloqueio no navegador. Desativar o bloqueio possibilita abrir um site HTTP ou um site que tenha conteúdo misto (HTTPS e HTTP).

![Página de criação de atividade com a mensagem de que os scripts do navegador devem ter permissão para carregar para criar atividades, ao lado de uma ilustração do prompt de recarregamento do navegador](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/mixed_content_warning.png)

Anteriormente, algumas ações na Etapa 1 do fluxo de trabalho guiado de três etapas permaneciam disponíveis quando um conteúdo misto não era permitido. [!DNL Target] agora bloqueia todas as ações na Etapa 1, portanto, o conteúdo misto deve ser habilitado antes que a criação da atividade possa continuar.

As configurações de segurança do navegador podem bloquear conteúdo não seguro (HTTP) que é carregado em uma página segura (HTTPS) ou quadro, como o VEC. A alternativa para alterar essas configurações é um site HTTPS. Se o site for executado em um domínio não seguro (HTTP), o VEC deverá ter permissão para carregar o conteúdo ativo misto.

>[!IMPORTANT]
>
>Permitir o conteúdo misto afeta somente o VEC e não o site ativo.

Para obter mais informações, consulte [Conteúdo misto](https://developer.mozilla.org/en-US/docs/Web/Security/Mixed_content) no site *Mozilla Developer Network* (MDN).

## Habilitar conteúdo misto em [!DNL Google Chrome]

O [!DNL Chrome] verifica se o conteúdo de uma página solicitada através de uma conexão segura foi transmitido em segurança. Consulte “[Gerenciamento de avisos sobre sites inseguros](https://support.google.com/chrome/answer/99020?hl=pt-BR)” na Ajuda do Google Chrome.

Para usar o VEC com a versão mais recente do [!DNL Chrome] (versão 79.0.3945.117 ou posterior), atualize as configurações do site da seguinte maneira. Os visitantes do site não precisam concluir essas etapas.

1. Clique no ícone de bloqueio (cuidado) e clique em **[!UICONTROL Configurações do site]**.

   ![Barra de endereços do Chrome com o menu de conexão aberto e as configurações do site realçadas](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/site-settings.png)

1. Em **[!UICONTROL Conteúdo não seguro]**, altere &quot;Bloquear (padrão)&quot; para &quot;Permitir&quot; na lista suspensa.

   ![Configurações do site do Chrome com o menu suspenso Conteúdo não seguro aberto e Permitir selecionado](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/insecure-content.png)

1. Recarregue a página do VEC.

## Habilitar conteúdo misto em [!DNL Mozilla Firefox]

Por padrão, o [!DNL Firefox] bloqueia páginas que misturam conteúdo seguro e inseguro, portanto, essa configuração deve ser alterada permanentemente para usar o [!DNL Target]. Os visitantes do site não precisam concluir essas etapas.

1. Em [!DNL Firefox], digite `about:config` na barra de endereços.
1. Confirme a mensagem de aviso que [!DNL Firefox] é exibida.

   ![Firefox Continue com a página de aviso de cuidado por aproximadamente:config com o botão Aceitar o Risco e Continuar](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox.png)

1. Na barra de pesquisa, digite `block_active`.

   ![Firefox sobre:config procure block_ative mostrando security.mixed_content.block_ative_content definido como true](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox3.png)

1. Clique duas vezes em `security.mixed_content.block_active_content`.

   O valor muda de &quot;Verdadeiro&quot; para &quot;Falso&quot;. Quando o valor mostra &quot;Falso&quot;, a alteração é concluída.

   ![Firefox aproximadamente:config mostrando security.mixed_content.block_ative_content definido como false](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/assets/firefox2.png)

1. Reinicie o computador depois de alterar essa configuração.

## Habilitar conteúdo misto em [!DNL Microsoft Edge]

O [!DNL Edge] verifica se o conteúdo de uma página solicitada através de uma conexão segura foi transmitido em segurança. Para usar o VEC com a versão mais recente do [!DNL Edge], atualize as configurações do site da seguinte maneira. Os visitantes do site não precisam concluir essas etapas.

1. Em [!DNL Edge], clique em **[!DNL Microsoft Edge]** na barra de menus, clique em **[!UICONTROL Configurações]** e em **Cookies e Permissões de Site**.
1. Role para **[!UICONTROL Conteúdo não seguro]** e clique nele.
1. Ao lado de **[!UICONTROL Permitir]**, clique em **[!UICONTROL Adicionar]**, insira o site no qual o conteúdo não seguro será permitido e clique em **[!UICONTROL Adicionar]**.
1. Recarregue a página do VEC.
