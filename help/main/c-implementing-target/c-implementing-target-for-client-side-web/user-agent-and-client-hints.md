---
keywords: at.js; agente do usuário do navegador; agente do usuário; dicas do cliente; agente do usuário
description: Saiba como [!DNL Adobe Target] O usa o agente do usuário e as Dicas do cliente para qualificar visitantes para segmentação e personalização.
title: Agente do usuário e dicas do cliente
feature: at.js
role: Developer
source-git-commit: 2527608fc781913024d5d6ffee49aff9eb6c2f42
workflow-type: tm+mt
source-wordcount: '1303'
ht-degree: 3%

---

# Agente do usuário e Dicas do cliente

[!DNL Adobe Target] O usa o agente do usuário para qualificar visitantes para segmentação e personalização.

Cada vez que um navegador da Web faz uma solicitação a um servidor, incluída no cabeçalho da solicitação, são informações sobre o navegador e o ambiente em que o navegador é executado. Desde os primeiros dias da Internet, esses dados foram agregados em uma única sequência chamada agente-usuário.

O texto a seguir é um exemplo de agente do usuário de um computador baseado no Mac OS X usando um navegador Safari:

```
Mozilla/5.0 (Linux; Android 12; SM-S908E) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.41 Mobile Safari/537.36 
```

Desse agente-usuário, o servidor que recebe a solicitação pode discernir as seguintes informações sobre o navegador e o sistema operacional:

| Informações | Detalhes |
| --- | --- |
| Nome do software | Chrome |
| Versão do software | 101 |
| Versão completa do software | 101.0.4951,41 |
| Nome do mecanismo de layout | AppleWebKit |
| Versão do mecanismo de layout | 537,36 |
| Sistema operacional | Android |
| Versão do sistema operacional | Android 12 (Snow Cone) |
| Dispositivo | SM-S908E (Samsung Galaxy S22 Ultra) |

Ao longo dos anos, a quantidade de informações de navegador e dispositivo incluída na sequência agente-usuário aumentou.

## Casos de uso do agente do usuário

Os agentes do usuário são usados há muito para fornecer às equipes de marketing e desenvolvedores informações importantes sobre como navegadores, sistemas operacionais. Os dispositivos e exibem o conteúdo do site, bem como a forma como os usuários interagem com os sites. Os agentes do usuário também são usados para bloquear spam e filtrar bots que rastreiam sites para uma variedade de fins adicionais.

Entretanto, nos últimos anos, alguns proprietários de sites e fornecedores de marketing usaram o agente-usuário junto com outras informações incluídas nos cabeçalhos de solicitação para criar impressões digitais que podem ser usadas como meio de identificar usuários sem conhecimento deles. Apesar do importante propósito que o agente do usuário serve para os proprietários do site, os desenvolvedores de navegador decidiram fazer alterações em como os agentes do usuário operam para limitar possíveis problemas de privacidade para os visitantes do site.

Dicas do cliente do agente-usuário é a solução desenvolvida pelos desenvolvedores do navegador. As Dicas do cliente ainda permitem que os sites coletem as informações necessárias do navegador, sistema operacional e dispositivo, além de fornecer maior proteção contra métodos de rastreamento ocultos, como impressão digital.

## Dicas do cliente

Dicas do cliente do agente-usuário fornecem aos proprietários do site a capacidade de acessar muitas das mesmas informações disponíveis no agente-usuário, mas de uma maneira mais preservada na privacidade. Quando navegadores modernos enviam um agente-usuário para um servidor da Web, todo o agente-usuário é enviado em cada solicitação, independentemente de ser necessário. Dicas do cliente, por outro lado, impõem um modelo em que o servidor deve solicitar ao navegador as informações adicionais que ele deseja saber sobre o cliente. Ao receber essa solicitação, o navegador pode aplicar suas próprias políticas ou configurações do usuário para determinar quais dados são retornados. Em vez de expor todo o agente de usuário por padrão em todas as solicitações, o acesso agora é gerenciado de forma explícita e auditável.

As Dicas do cliente do agente-usuário estão disponíveis no Chrome desde a versão 89. Versões recentes de navegadores baseados em Chromium, como Microsoft Edge, Opera, Brave, Chrome Android, Opera Android e Samsung Internet, também oferecem suporte à API de dicas do cliente.

As Dicas do cliente contidas nos cabeçalhos da primeira solicitação feita pelo navegador para um servidor da Web contêm a marca do navegador, a versão principal do navegador e um indicador de se o cliente é um dispositivo móvel. Cada parte dos dados tem seu próprio valor de cabeçalho, em vez de ser agrupada em uma única sequência agente-usuário, como mostrado na seguinte amostra:

```
Sec-CH-UA: "Chromium";v="101", "Google Chrome";v="101", " Not;A Brand";v="99" 
Sec-CH-UA-Mobile: ?0 
Sec-CH-UA-Platform: "macOS"
```

O exemplo a seguir é o agente do usuário para o mesmo navegador:

```
Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/101.0.4951.54 Safari/537.36 
```

Embora as informações sejam semelhantes, a primeira solicitação para o servidor contém Dicas do cliente que contêm apenas um subconjunto do que está disponível na sequência agente-usuário. Falta a solicitação da arquitetura do sistema operacional, versão completa do sistema operacional, nome do mecanismo de layout, versão do mecanismo de layout e versão completa do navegador. No entanto, em solicitações subsequentes, a API de dicas do cliente permite que os servidores da Web solicitem detalhes adicionais e de alta entropia sobre o dispositivo. Quando esses valores de alta entropia são solicitados, dependendo da política do navegador ou das configurações do usuário, a resposta do navegador pode incluir essas informações.

O exemplo a seguir é um objeto JSON retornado pela API de Dicas do Cliente quando valores de alta entropia são solicitados:

```
{ 

    "architecture":"x86", 
    "bitness":"64", 
    "brands":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100" 
        } 
    ], 
    "fullVersionList":[ 
        { 
            "brand":" Not A;Brand", 
            "version":"99.0.0.0" 
        }, 
        { 
            "brand":"Chromium", 
            "version":"100.0.4896.127" 
        }, 
        { 
            "brand":"Google Chrome", 
            "version":"100.0.4896.127" 
        } 
    ], 
    "mobile":false, 
    "model":"", 
    "platformVersion":"12.2.1" 
} 
```

Os valores de alta entropia incluem várias informações adicionais que não estão disponíveis nas informações padrão de Dicas do Cliente. A tabela a seguir contém detalhes de quais dados estão disponíveis na solicitação padrão em comparação às informações de Dicas do cliente do agente de usuário de alta entropia.

| Cabeçalho HTTP | JavaScript | Agente do usuário | Dica do cliente | Dica do cliente de alta entropia |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | marcas | Sim | Sim | Não |
| Sec-CH-UA-Platform | plataforma | Sim | Sim | Não |
| Sec-CH-UA-Mobile | mobile | Sim | Sim | Não |
| Sec-CH-UA-Platform-Version | platformVersion | Sim | Não | Sim |
| Sec-CH-UA-Arch | arquitetura | Sim | Não | Sim |
| Sec-CH-UA-Model | model | Sim | Não | Sim |
| Sec-CH-UA-Bitness | Beleza | Sim | Não | Sim |
| Sec-CH-UA-Full-Version-List | fullVersionList | Sim | Não | Sim |

## Migração para dicas de clientes

Atualmente, os navegadores baseados em Chromium continuam a enviar o agente-usuário juntamente com Dicas do cliente nos cabeçalhos de solicitações feitas aos servidores da Web. No entanto, a partir de abril de 2022 e até fevereiro de 2023, a quantidade de dados contidos na sequência agente-usuário será reduzida. Outros navegadores, como Safari e Firefox, continuarão a utilizar a sequência de agente do usuário; no entanto, também eles irão reduzir o volume de informação nele contido.

## [!DNL Target] casos de uso que exigem dicas de cliente

Os seguintes casos de uso no Target exigem dicas para o cliente:

### Atributos do público-alvo

Se você usar [!DNL Target] públicos-alvo e usar qualquer um dos atributos de público-alvo a seguir, [!DNL Target] O requer Dicas do cliente para executar a segmentação correta:

* Navegador
* Sistema operacional
* Móvel

### Scripts de perfil

Se você usar scripts de perfil e fizer referência ao `user.browser` (que se refere ao agente-usuário), talvez seja necessário atualizar o script de perfil para também verificar uma ou mais Dicas do cliente. Você pode acessar qualquer uma das Dicas do cliente usando a função `user.clientHint('sec-ch-ua-xxxxx')`. O nome do cabeçalho da Dica do Cliente deve estar em todas as minúsculas.

O exemplo a seguir mostra como detectar corretamente um sistema operacional Windows em um script de perfil:

```
"return (((user.browser != null) && (user.browser.indexOf(\"Windows\") > -1)) || " + 
      "((user.clientHint('sec-ch-ua-platform') != null) && 
(user.clientHint('sec-ch-ua-platform') === 'Windows')));" 
```

As seções a seguir mostram os cabeçalhos de Dicas do cliente e a semântica de uso do script de perfil correspondente.

#### Sec-CH-UA

Entropia: Baixa documentação: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA){target=_blank} Atributo de público-alvo: Uso do script do Perfil do navegador: `user.clientHint('sec-ch-ua')`

#### Sec-CH-UA-Arch

Entropia: Alta documentação: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Arch){target=_blank} Atributo de público-alvo: Uso do script de perfil: `user.clientHint('sec-ch-ua-arch')`

#### Sec-CH-UA-Bitness

Entropia: Alta documentação: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Bitness){target=_blank} Atributo de público-alvo: Uso do script de perfil: `user.clientHint('sec-ch-ua-bitness')`

#### Sec-CH-UA-Full-Version-List

Entropia: Alta documentação: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Full-Version-List){target=_blank} Atributo de público-alvo: Uso do script do Perfil do navegador: `user.clientHint('sec-ch-ua-full-version-list')`

#### Sec-CH-UA-Mobile

Entropia: Baixa documentação: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Mobile){target=_blank} Atributo de público-alvo: Uso do script do perfil móvel: `user.clientHint('sec-ch-ua-mobile')`

#### Sec-CH-UA-Model

Entropia: Alta documentação: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Model){target=_blank} Atributo de público-alvo: Uso do script do perfil móvel: `user.clientHint('sec-ch-ua-model')`

#### Sec-CH-UA-Platform

Entropia: Baixa documentação: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform){target=_blank} Atributo de público-alvo: Uso do script de perfil do sistema operacional: `user.clientHint('sec-ch-ua-platform')`

#### Sec-CH-UA-Platform-Version

Entropia: Alta documentação: [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Sec-CH-UA-Platform-Version){target=_blank} Atributo de público-alvo: Uso do script de perfil: `user.clientHint('sec-ch-ua-platform-version')`

## Como passar as dicas do cliente para [!DNL Adobe Target]

As seções a seguir contêm mais informações sobre como enviar as Dicas do cliente, dependendo do [!DNL Target] implementação.

### at.js versão 2.9.0 (ou posterior)

A partir da at.js 2.9.0, as Dicas do cliente do agente do usuário serão coletadas automaticamente do navegador e enviadas para [!DNL Target] when `getOffer/getOffers()` é chamado. Por padrão, a at.js coleta apenas dicas de cliente de &quot;baixa criptografia&quot;. Se estiver executando a segmentação de público-alvo ou usando scripts de perfil com base em dados categorizados como &quot;Alta criptografia&quot; nas seções anteriores, será necessário configurar a at.js para coletar &quot;Alta criptografia&quot; de dicas do cliente do navegador por meio de `targetGlobalSettings`.

`window.targetGlobalSettings = { allowHighEntropyClientHints: true };`

### SDKs do lado do servidor

Para obter mais informações sobre como passar dicas do cliente por SDKs do lado do servidor, consulte [Dicas do cliente](https://adobetarget-sdks.gitbook.io/docs/core-principles/audience-targeting#client-hints){target=_blank} na *SDKs do Adobe Target* documentação.












