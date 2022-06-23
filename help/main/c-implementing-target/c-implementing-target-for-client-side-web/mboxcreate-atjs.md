---
keywords: mboxCreate; mboxcreate; criar mbox; at.js; funções; função
description: Use a função mboxCreate() para o Adobe [!DNL Target] biblioteca JavaScript da at.js para aplicar ofertas ao DIV mais próximo com o nome de classe mboxDefault. (at.js 1.x)
title: Como uso a função mboxCreate()?
feature: at.js
role: Developer
exl-id: 821ad97a-345a-4e56-9be6-ab1c7d3a651d
source-git-commit: a0a20b99a76ba0346f00e3841a345e916ffde8ea
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 73%

---

# mboxCreate(mbox,params) - at.js 1.x

Executa uma solicitação e aplica a oferta ao DIV mais próximo com o nome de classe mboxDefault.

>[!NOTE]
>
>Essa função está disponível para a at.js versão 1.somente *x*. Essa função foi descontinuada pelo lançamento da at.js 2.x. Ela retorna o conteúdo padrão se for usada com a 2.x.

Essa função é incorporada no [!DNL at.js] principalmente para facilitar a transição de [!DNL mbox.js] (agora obsoleto) para [!DNL at.js]. Uma alternativa mais nova para `mboxCreate()` é `adobe.target.getOffer()`/ `adobe.target.applyOffer()` ou a diretiva Angular.

## Exemplo

```javascript
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## Notas

`mboxCreate()` agora usa o terminal &quot;json&quot; ao invés de &quot;standard&quot; e dispara de maneira assíncrona. Por esse motivo:

* [Depuração](https://developer.adobe.com/target/implement/client-side/target-debugging-atjs/target-debugging-atjs/){target=_blank} é um pouco diferente.
* Evite oferecer código que exija chamadas bloqueio sincrônicas.

   Por exemplo, ofertas que definem variáveis de JavaScript que são usadas para código do site ou outras mboxes posteriores na página.

* Certifique-se de ter uma `<div class="mboxDefault"></div>` antes de invocar `mboxCreate()`, pois [!DNL at.js] não adicionará um para você.

* Funções vazias no topo da página `mboxCreate()` não são recomendadas como mbox global.

   A mbox global criada automaticamente em [!DNL at.js] é uma opção melhor, pois dispara do `<head>` e pode retornar conteúdo antecipadamente.
