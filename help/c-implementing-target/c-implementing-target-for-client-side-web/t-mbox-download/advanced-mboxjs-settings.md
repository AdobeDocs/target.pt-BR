---
description: Informações para ajudar a definir várias configurações na página Configurações da mbox.js.
keywords: configurações avançadas de mbox.js; cliente; domínio do servidor; xdomain; nível de compactação; suporte a id de sessão do cliente; secureOnly; suporte a id do pc do cliente; passar página; url de referência; nível de tráfego; duração do tráfego; corpo da função mboxParameters(); corpo da função mboxSupported(); corpo da função mboxCookieDomain(); JavaScript extra; plug-in do SiteCatalyst; obter mbox.js como JavaScript com extração automática; cintilação; ocultação de corpo; ocultar corpo
seo-description: Informações para ajudar a definir várias configurações na página Configurações da mbox.js.
seo-title: Configurar mbox.js
solution: Target
title: Configurar mbox.js
uuid: e79c7af7-f8bd-4e2b-8e67-b04eddf0c65d
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Configurar mbox.js{#configure-mbox-js}

Informações para ajudar a definir várias configurações na página Configurações da mbox.js.

As configurações padrão da biblioteca da função [!DNL mbox.js] atendem aos objetivos da maioria dos clientes do [!DNL Target].

Se necessário, entre em contato com seu representante de contas para modificar as configurações do arquivo [!DNL mbox.js].

As seguintes configurações estão disponíveis:

## Cliente

Código de cliente da sua conta.

Ao visualizar [!UICONTROL Configurar &gt; Implementação &gt; Editar configurações da mbox.js], o Cliente na parte superior é o código de cliente da sua conta.

## Tempo limite

A solicitação do Target atinge o tempo limite.

Ao exibir [!UICONTROL Configuração &gt; Implementação &gt; Editar configurações da Mbox. js], o Tempo limite após o Nível de compactação é o tempo limite da solicitação do Target. Por padrão, esse valor é definido como 15 segundos, mas é recomendável configurá-lo para um valor entre 2 segundos e 5 segundos.

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