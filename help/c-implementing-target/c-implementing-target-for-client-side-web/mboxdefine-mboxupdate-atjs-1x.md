---
keywords: mboxDefine;mboxdefine;mbox define;mboxUpdate;mboxupdate;mbox update;at.js;functions;function
description: Informações sobre as funções mboxDefine() e mboxUpdate() da biblioteca at.js de JavaScript do Adobe Target.
title: Informações sobre as funções mboxDefine() e mboxUpdate() da biblioteca at.js de JavaScript do Adobe Target.
feature: null
subtopic: Getting Started
topic: Standard
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '184'
ht-degree: 100%

---


# mboxDefine() e mboxUpdate() - at.js 1.x

Defina e atualize uma mbox no Adobe Target.

>[!NOTE]
>
>Essas funções estão disponíveis para a at.js versão 1.somente *x*. Essas funções foram descontinuadas com o lançamento da at.js 2.x. Elas retornam o conteúdo padrão se forem usadas com a 2.x.

`mboxDefine()` e `mboxCreate()` estão vinculados a elementos HTML DIV onde a oferta deve ser exibida. Esses elementos HTML DIV devem ter a classe `mboxDefault`. Se os elementos HTML não tiverem essa classe anexada, você pode observar alguma cintilação perceptível.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Cria um mapeamento interno entre um nodeId e um nome de mbox, mas não executa a solicitação. Usado em conjunto com `mboxUpdate()`. Incorporada na [!DNL at.js], principalmente para facilitar a transição de [!DNL mbox.js] para [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Executa a solicitação e aplica a oferta ao elemento identificado pelo `nodeId` em `mboxDefine()`. Também pose ser usada para atualizar uma mbox iniciada por `mboxCreate`. Incorporada na [!DNL at.js], principalmente para facilitar a transição de [!DNL mbox.js] para [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` pode ser substituído por [adobe.target.getOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) e [adobe.target.applyOffer()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) usando a opção do seletor.

## Exemplo {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
