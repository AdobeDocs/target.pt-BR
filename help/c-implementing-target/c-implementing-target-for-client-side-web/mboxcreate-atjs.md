---
keywords: mboxCreate; mboxcreate; criar mbox; at.js; funções; função
description: Informações sobre a função mboxCreate(mbox,params) da biblioteca at.js de JavaScript do Adobe Target.
title: Informações sobre a função mboxCreate(mbox,params) da biblioteca at.js de JavaScript do Adobe Target.
subtopic: Introdução
topic: Padrão
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

---


# mboxCreate(mbox,params) - at.js 1.x {#reference_E68805FE86C64792B2066DB17B253D74}

Executa uma solicitação e aplica a oferta ao DIV mais próximo com o nome de classe mboxDefault.

>[!NOTE]
>
>Essa função está disponível para a at.js versão 1.somente *x*. Essa função foi descontinuada pelo lançamento da at.js 2.x. Ela retorna o conteúdo padrão se for usada com a 2.x.

A função está incorporada na [!DNL at.js], principalmente para facilitar a transição de [!DNL mbox.js] para [!DNL at.js]. Uma alternativa mais nova para `mboxCreate()` é `adobe.target.getOffer()`/ `adobe.target.applyOffer()` ou a diretiva Angular.

## Exemplo

```
<div class="mboxDefault"> 
  default content to replace by offer 
</div> 
<script> 
  mboxCreate('mboxName','param1=value1','param2=value2'); 
</script>
```

## Notas

`mboxCreate()` agora usa o terminal "json" ao invés de "standard" e dispara de maneira assíncrona. Por esse motivo:

* [Depuração](../../c-implementing-target/c-implementing-target-for-client-side-web/c-target-debugging-atjs/target-debugging-atjs.md#concept_CAE591DA8C404C22917584ECD4F7494F) é diferente.
* Evite oferecer código que exija chamadas bloqueio sincrônicas.

   Por exemplo, ofertas que definem variáveis de JavaScript que são usadas para código do site ou outras mboxes posteriores na página.

* Certifique-se de ter uma `<div class="mboxDefault"></div>` antes de invocar `mboxCreate()`, pois [!DNL at.js] não adicionará um para você.

* Funções vazias no topo da página `mboxCreate()` não são recomendadas como mbox global.

   A mbox global criada automaticamente em [!DNL at.js] é uma opção melhor, pois dispara do `<head>` e pode retornar conteúdo antecipadamente.