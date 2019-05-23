---
description: 'Informações sobre as funções mboxdefine () e mboxupdate () para at. js. '
keywords: adobe.target.notificação; elemento; seletor; notificação; extensão
seo-description: Informações sobre as funções mboxdefine () e mboxupdate () para a biblioteca do Adobe Target no javascript.
seo-title: Informações sobre as funções mboxdefine () e mboxupdate () para a biblioteca do Adobe Target no javascript.
solution: Target
subtopic: Introdução
title: mboxDefine() e mboxUpdate() - at.js 1.x
topic: Padrão
translation-type: tm+mt
source-git-commit: 126f62d8966beb8157f54f87cf68b092fe976c51

---


# mboxDefine() e mboxUpdate() - at.js 1.x

Defina e atualize uma mbox no Adobe Target.

>[!NOTE]
>
>Essas funções estão disponíveis para a at.js versão 1.somente *x*. Essas funções foram substituídas pelo lançamento do at. js 2. x. Essas funções retornam o conteúdo padrão se forem usadas com o at. js 2. x.

`mboxDefine()` e `mboxCreate()` estão vinculados a elementos HTML DIV onde a oferta deve ser exibida. Esses elementos HTML DIV devem ter a classe `mboxDefault`. Se os elementos HTML não tiverem essa classe anexada, você pode observar alguma cintilação perceptível.

## mboxDefine {#section_134BAAE8EE9D49D8BAFEA5E7EAB93BA7}

Cria um mapeamento interno entre um nodeId e um nome de mbox, mas não executa a solicitação. Usado em conjunto com `mboxUpdate()`. Incorporada na [!DNL at.js], principalmente para facilitar a transição de [!DNL mbox.js] para [!DNL at.js].

## mboxUpdate {#section_D20B3E551884452A996305C12D5959D5}

Executa a solicitação e aplica a oferta ao elemento identificado pelo `nodeId` em `mboxDefine()`. Também pose ser usada para atualizar uma mbox iniciada por `mboxCreate`. Incorporada na [!DNL at.js], principalmente para facilitar a transição de [!DNL mbox.js] para [!DNL at.js]. `mboxDefine()`/ `mboxUpdate()` poderia ser substituído [por adobe. target. getoffer ()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) e [adobe. target. applyoffer ()](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) usando a opção seletor.

## Exemplo {#section_9C1E75D9E4BA4DC7879D2B69877EB01A}

```
<div id="someId" class="mboxDefault"></div> 
<script> 
 mboxDefine('someId','mboxName','param1=value1','param2=value2'); 
 mboxUpdate('mboxName','param3=value3','param4=value4'); 
</script>
```
