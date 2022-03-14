---
keywords: implementação; biblioteca javascript; js; atjs; decisão no dispositivo; no device decisioning; at.js; no dispositivo; no dispositivo; solução de problemas; solução de problemas
description: Saiba como solucionar problemas no dispositivo com a biblioteca at.js.
title: Como soluciono problemas no dispositivo com a biblioteca at.js de JavaScript?
feature: at.js
role: Developer
exl-id: 76bb9393-1560-455b-9d95-91576faee1f2
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '256'
ht-degree: 1%

---

# Solução de problemas da decisão no dispositivo para at.js

Conclua as etapas a seguir para solucionar problemas de decisão no dispositivo em [!DNL Adobe Target] com a biblioteca at.js de JavaScript:

## Etapa 1: Ativar o log do console para at.js

Anexar o parâmetro do URL `mboxDebug=1` O permite que a at.js imprima mensagens no console do navegador.

Todas as mensagens contêm um prefixo &quot;AT:&quot; para obter uma visão geral conveniente. Para garantir que um artefato tenha sido carregado com êxito, o log do console deve conter mensagens semelhantes ao seguinte:

```
AT: LD.ArtifactProvider fetching artifact - https://assets.adobetarget.com/your-client-cide/production/v1/rules.json
AT: LD.ArtifactProvider artifact received - status=200
```

A ilustração a seguir mostra essas mensagens no log do console:

![Logon do console com mensagens de artefato](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/browser-console.png)

## Etapa 2: Verifique o download do artefato da regra na guia Rede do navegador

Abra a guia Rede do navegador.

Por exemplo, para abrir o DevTools no Google Chrome:

1. Pressione Control+Shift+J (Windows) ou Command+Option+J (Mac).
1. Navegue até a guia Rede.
1. Filtre suas chamadas por palavra-chave &quot;rules.json&quot; para garantir que somente o arquivo de regras de artefato seja exibido.

   Além disso, você pode filtrar por &quot;/delivery|rules.json/&quot; para exibir todas as [!DNL Target] chamadas e artifact rules.json.

   ![Guia Rede no Google Chrome](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/assets/rule-json.png)

## Etapa 3: Verificar o download do artefato da regra usando eventos personalizados da at.js

A biblioteca at.js despacha dois novos eventos personalizados para suportar decisões no dispositivo.

* `adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED`
* `adobe.target.event.ARTIFACT_DOWNLOAD_FAILED`

Você pode assinar para ouvir esses eventos personalizados em seu aplicativo para ação após o sucesso ou falha do download do arquivo de regras de artefato.

O exemplo a seguir mostra uma amostra de código ouvindo os eventos de sucesso e falha do download de artefatos:

```javascript
document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_SUCCEEDED, function(e) { 
  console.log("Artifact successfully downloaded", e.detail);
}, false);

document.addEventListener(adobe.target.event.ARTIFACT_DOWNLOAD_FAILED, function(e) { 
  console.log("Artifact failed to download", e.detail);
}, false);
```
