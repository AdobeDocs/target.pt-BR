---
keywords: configurações avançadas de mbox.js; cliente; domínio do servidor; xdomain; nível de compactação; suporte a id de sessão do cliente; secureOnly; suporte a id do pc do cliente; passar página; url de referência; nível de tráfego; duração do tráfego; corpo da função mboxParameters(); corpo da função mboxSupported(); corpo da função mboxCookieDomain(); JavaScript extra; plug-in do SiteCatalyst; obter mbox.js como JavaScript com extração automática; cintilação; ocultação de corpo; ocultar corpo
description: Saiba mais sobre a implementação legada da mbox.js do Adobe Target. Migre para o Adobe Experience Platform Web SDK (AEP Web SDK) ou para a versão mais recente do at.js.
title: Como configuro a biblioteca mbox.js do Público alvo?
feature: at.js
role: Developer
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '472'
ht-degree: 70%

---


# Configurar mbox.js

Informações para ajudar a definir várias configurações na página Configurações da mbox.js.

>[!IMPORTANT]
>
>**Fim da vida útil** do mbox.js: Em 31 de março de 2021, não  [!DNL Adobe Target] será mais compatível com a biblioteca mbox.js. Após 31 de março de 2021, todas as chamadas feitas a partir do mbox.js falharão e afetarão suas páginas que possuem [!DNL Target] atividades sendo executadas com o conteúdo padrão.
>
>Recomendamos que todos os clientes migrem para a versão mais recente da nova [!DNL Adobe Experience Platform Web SDK] ou da biblioteca JavaScript at.js antes dessa data para evitar possíveis problemas com seus sites. Para obter mais informações, consulte [Visão geral: implemente o Público alvo para Web do lado do cliente](/help/c-implementing-target/c-implementing-target-for-client-side-web/implement-target-for-client-side-web.md).

As configurações padrão da biblioteca da função [!DNL mbox.js] atendem aos objetivos da maioria dos clientes do [!DNL Target].

Se necessário, entre em contato com seu representante de contas para modificar as configurações do arquivo [!DNL mbox.js].

As seguintes configurações estão disponíveis:

## Cliente

Código de cliente da sua conta.

Ao exibir [!UICONTROL Administração > Implementação], o Cliente na parte superior é o código do cliente para sua conta.

## Tempo limite

A solicitação do Target atinge o tempo limite.

Ao exibir [!UICONTROL Administração > Implementação], a configuração Tempo limite (segundos) é o tempo limite da solicitação de Público alvo. Por padrão, esse valor é definido como 15 segundos, mas é recomendável configurá-lo para um valor entre 2 segundos e 5 segundos.

## XDomain

Determina se o navegador define cookies em seu domínio (cookies próprios), no domínio do Target ou em ambos.

A alteração dessa configuração afeta a mbox.js e a at.js.

## Nível de compactação

Determina o nível de compactação do arquivo da biblioteca mbox.js. Aumentar o nível de compactação reduz o tempo de carregamento da página.

## Corpo da função mboxParameters()

Retorna parâmetros adicionais que serão transmitidos para cada chamada de mbox.

Por exemplo:

return &quot;test=123&quot;;

## Corpo da função mboxSupported()

Retorna false para excluir usuários específicos.

Por exemplo:

return !navigator.userAgent.indexOf(&#39;Safari&#39;) != -1;

Os navegadores a seguir podem ser aceitos ou excluídos:

* IE 5.0 ou superior (Windows)
* Netscape 5.0 ou superior (Mac, Windows, Linux)
* Safari 1.2.4 ou superior (Mac)
* Mozilla Firefox 1.0 ou superior (Mac, Windows, Linux)

## Corpo da função mboxCookieDomain()

Retorna uma cadeia de caracteres descrevendo o domínio para definir cookies primários.

Por exemplo:

return &quot;YOUR-DOMAIN&quot;;

## JavaScript extra

Inclui qualquer JavaScript adicional que desejar executar em cada página.

## Plug-in do SiteCatalyst

Ativa o plug-in do Target para o Analytics.

Quando ativado, o plug-in do Analytics gera um código de plugin na mbox.js. Isso envia informações de tag do Analytics para os servidores do Target como uma solicitação de mbox em toda página marcada com Analytics.

O plug-in do Analytics ainda deve ser referenciado na página.

## secureOnly

Indica se a mbox.js deve usar somente HTTPS ou pode alternar entre HTTP e HTTPS com base no protocolo da página. Esta é uma configuração avançada cujo padrão é Falso.