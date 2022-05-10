---
keywords: mboxDefine; mboxdefine; definir mbox; mboxUpdate; mboxupdate; atualizar mbox; at.js; funções; função
description: Use as funções mboxDefine() e mboxUpdate() para o Adobe [!DNL Target] biblioteca JavaScript da at.js para definir ou atualizar uma mbox. (at.js 1.x)
title: Como uso as funções mboxDefine() e mboxUpdate()?
feature: at.js
role: Developer
exl-id: 48261be0-c4d0-4961-9712-ef7e0d2cb1c0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 75%

---

# mboxDefine() e mboxUpdate() - at.js 1.x

Defina e atualize uma mbox no Adobe Target.

>[!NOTE]
>
>Essas funções estão disponíveis para a at.js versão 1.somente *x*. Essas funções foram descontinuadas com o lançamento da at.js 2.x. Elas retornam o conteúdo padrão se forem usadas com a 2.x.

`mboxDefine()` e `mboxCreate()` estão vinculados a elementos HTML DIV onde a oferta deve ser exibida. Esses elementos HTML DIV devem ter a classe `mboxDefault`. Se os elementos HTML não tiverem essa classe anexada, você pode observar alguma cintilação perceptível.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Cria um mapeamento interno entre um nodeId e um nome de mbox, mas não executa a solicitação. Usado em conjunto com `mboxUpdate()`. Incorporada em [!DNL at.js] principalmente para facilitar a transição de [!DNL mbox.js] (agora obsoleto) para [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Executa a solicitação e aplica a oferta ao elemento identificado pelo `nodeId` em `mboxDefine()`. Também pose ser usada para atualizar uma mbox iniciada por `mboxCreate`. Incorporada em [!DNL at.js] principalmente para facilitar a transição de [!DNL mbox.js] (agora obsoleto) para [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` pode ser substituído por [adobe.target.getOffer()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) e [adobe.target.applyOffer()](/help/main/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) usando a opção do seletor.

## Exemplo {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```javascript
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```