---
keywords: custom events;at.js;request failed;request succeeded;content rendering failed;content rendering succeeded;library loaded;request start;content rendering start;content rendering no offers;content rendering rediret
description: Informações sobre os eventos personalizados da biblioteca at.js de JavaScript do Adobe Target.
title: Informações sobre os eventos personalizados da biblioteca at.js de JavaScript do Adobe Target.
feature: null
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '585'
ht-degree: 96%

---


# Eventos personalizados da at.js

Informações sobre `at.js custom events`, que informam quando uma solicitação ou oferta de mbox falha ou é bem-sucedida.

Historicamente, a mbox.js não permitiu que outro código JavaScript executado na página saiba o que acontece nos bastidores. Com o avanço da at.js, tivemos uma oportunidade única de corrigir este problema.

De acordo com nossos clientes, há vários cenários dos quais eles gostariam de ser notificados, incluindo:

* Uma falha em uma solicitação da mbox devido ao tempo limite, código do status incorreto, erro de análise do JSON, etc.
* Uma solicitação da mbox foi bem-sucedida.
* Falha na renderização da oferta devido à ausência do elemento da mbox de encapsulamento, não foi possível encontrar o seletor, etc.
* Renderização de oferta bem-sucedida. As alterações de DOM foram aplicadas.

Os eventos predefinidos têm uma estrutura que permite que você extraia os dados necessários conforme o tipo de evento.

Para certificar-se de que os eventos possam ser usados em diferentes cenários, os eventos personalizados têm um objeto de carga que é atribuído à propriedade detalhada do objeto do evento (que é transmitido ao manipulador). Para evitar, também, transmitir sequências de caracteres como nomes de evento, os eventos são expostos como constantes usando o espaço de nome `adobe.target.event`.

## Estrutura {#section_0E5C9A13DE234A5DAECBCBF9F23F94FE}

| Chave | Tipo | Descrição |
|--- |--- |--- |
| type | String | Há vários cenários em que você gostaria de receber notificações para ajudar com o rastreamento, depuração e personalização da interação com a at.js.<br>Cada evento personalizado listado abaixo tem dois formatos: um &quot;constante&quot; e um &quot;valor em sequência&quot;.<ul><li>**Constantes**: Prefixado com `adobe.target.event.`, apresentado em todas as maiúsculas e contém caracteres sublinhados. Para se inscrever em eventos personalizados *após* o carregamento da at.js, mas *antes* de receber a resposta da mbox, use o constante.</li><li>**Valores da string**: Minúsculas e contêm hifens. Para se inscrever em eventos personalizados *antes* do carregamento da at.js, use os valores em sequência.</li></ul>**Solicitação com Falha **<br>Constant:`adobe.target.event.REQUEST_FAILED`<br>String value:`at-request-failed`<br>Description: An mbox request failed due to timeout, wrong status code, JSON parse error, etc.<br>**Solicitação bem-sucedida**<br>Constante:`adobe.target.event.REQUEST_SUCCEEDED`<br>Valor da string:`at-request-succeeded`<br>Descrição: Uma solicitação de mbox foi bem-sucedida.<br>**Renderização de conteúdo com falha **<br>Constante:`adobe.target.event.CONTENT_RENDERING_FAILED`<br>Valor da string:`at-content-rendering-failed`<br>Descrição: A renderização da oferta falhou devido ao vínculo do elemento da mbox ausente, o seletor não pode ser encontrado, etc.<br>**Renderização de conteúdo bem-sucedida**<br>Constante:`adobe.target.event.CONTENT_RENDERING_SUCCEEDED`<br>Valor da string:`at-content-rendering-succeeded`<br>Descrição: A renderização da oferta foi bem-sucedida. As alterações de DOM foram aplicadas.<br>**Biblioteca carregada **<br>Constante:`adobe.target.event.LIBRARY_LOADED`<br>Valor da string:`at-library-loaded`<br>Descrição: Esse evento é ideal para rastrear quando o at.js foi totalmente carregado. Você pode usar este evento para personalizar a execução da mbox global. Você também pode usar este evento para desativar a mbox global e depois ouvir este evento disparar a mbox global posteriormente.<br>**Início da solicitação**<br>Constante:`adobe.target.event.REQUEST_START`<br>Valor da string:`at-request-start`<br>Descrição: Esse evento é disparado antes da execução de uma solicitação HTTP. Você pode usar este evento para avaliações de desempenho usando a API do Resource Timing.<br>**Início da renderização de conteúdo **<br>Constante:`adobe.target.event.CONTENT_RENDERING_START`<br>Valor da string:`at-content-rendering-start`<br>Descrição: Esse evento é disparado antes de a pesquisa do seletor ser iniciada e o conteúdo ser renderizado na página. Você pode usar este evento para monitorar o progresso da renderização de conteúdo.<br>**Renderização de conteúdo Não há ofertas**<br>Constante:`adobe.target.event.CONTENT_RENDERING_NO_OFFERS`<br>Valor da string:`at-content-rendering-no-offers`<br>Descrição: Esse evento é disparado quando não há ofertas retornadas.<br>**Renderização de conteúdo Redirecionamento **<br>Constante:`adobe.target.event.CONTENT_RENDERING_REDIRECT`<br>Valor da string:`at-content-rendering-redirect`<br>Descrição: Esse evento é disparado quando uma oferta é redirecionada e o Target redirecionará para um URL diferente. |
| mbox | String | nome da mbox |
| message | String | Contém descrição para leitura humana, como o que aconteceu, mensagem de erro, etc. |
| rastreamento | Objeto | Contém o `sessionId` e `deviceId`. Em alguns casos, o `deviceId` pode estar ausente, porque o [!DNL Target] não foi capaz de recuperá-lo do servidor do Edge. |

## Uso {#section_0500FF09D3A04450B5DC8F85C6F793E0}

```
document.addEventListener(adobe.target.event.REQUEST_SUCCEEDED, function(event) { 
  console.log('Event', event); 
});
```

## Vídeo de treinamento: Tokens de resposta e os Eventos personalizados da at.js {#section_ED304A7137DC42A4BDCD6D57C989F1FA} ![Crachá do tutorial](/help/assets/tutorial.png)

Assista ao vídeo a seguir para saber como usar Tokens de resposta e Eventos personalizados de at.js para compartilhar informações de perfil do Target com sistemas de terceiros.

>[!VIDEO](https://video.tv.adobe.com/v/23253/)