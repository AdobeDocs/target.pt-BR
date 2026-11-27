---
keywords: Direcionamento de experiência;teste de página de destino
description: Um seletor de elementos é uma expressão CSS que pode identificar um ou mais elementos. Saiba como usar seletores de elementos no Visual Experience Composer (VEC) do Adobe [!DNL Target].
title: Posso usar seletores de elementos no Visual Experience Composer (VEC)?
feature: Visual Experience Composer (VEC)
exl-id: f4ddb30a-f599-4fe5-861c-2deeeb9a70dd
TQID: 'https://experienceleague.adobe.com/sqvUyLFddt7HPHH62jwpOZmwTIMSg-hyLIUr8w-x7vg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 4%
---
# Seletores de elementos usados no [!UICONTROL Visual Experience Composer] {#vec-selectors}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como os seletores de elementos funcionam no [!UICONTROL Visual Experience Composer] (VEC), como escolher quais seletores serão usados e como o [!DNL Target] gera um seletor para um elemento.

>[!ENDSHADEBOX]

Um seletor de elementos é uma expressão CSS que pode identificar um ou mais elementos. Informações básicas sobre os seletores de CSS estão disponíveis no documento [Seletores](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) no *[!DNL Mozilla Developer Network]* (MDN).

Se as classes de elemento ou IDs de elemento devem ser usadas é definido nas preferências da conta. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Visual Experience Composer]** e escolha os seletores de CSS preferidos:

* **[!UICONTROL Usar IDs de elemento]**: desabilite se a mesma ID for usada para vários elementos ou se as IDs de elemento puderem mudar no carregamento da página.
* **[!UICONTROL Usar classes de elemento]**: desabilite se as classes de elemento em uma página puderem mudar.
* **[!UICONTROL Usar seletores preferenciais]**: permitir o uso de seletores exclusivos no VEC para identificar as principais áreas do site.

>[!NOTE]
>
>As classes de elemento estão disponíveis como seletores em **[!UICONTROL atividades de Teste A/B]**, **[!UICONTROL Automated Personalization]** e **[!UICONTROL Teste multivariado]**.

Para obter informações sobre quando usar seletores de CSS e quando usar IDs exclusivas, consulte [Práticas recomendadas e limitações do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#vec-best-practices).

## Como [!DNL Target] gera um seletor para um elemento {#generate-selector}

[!DNL Target] usa um algoritmo simples para criar um seletor. A lógica de geração é a seguinte:

1. Se um elemento tiver uma ID, por exemplo `id="container"`, o seletor do elemento é `#container`.

   Por exemplo:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- Selector is computed for this element -->
       <ul class="navigation">
         <li class="item active"> Home </li>
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

1. Se um elemento contiver um atributo de classe, [!DNL Target] tentará usar a primeira classe de qualquer classe presente no elemento.

   [!DNL Target] tenta analisar o elemento pai até encontrar o elemento `<HTML>` ou um elemento com uma ID. Sempre que um elemento contém uma ID e o seletor é calculado em seu filho descendente, a ID desse elemento contribui para o seletor.

   Por exemplo:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li class="item active"> Home </li> <!-- Selector is computed for this element -->
         <li class="item"> Men </li>
         <li class="item"> Women </li>
         <li class="item"> Kids </li>
       </ul>
     </div>
   </div>
   ```

   Neste exemplo, o seletor é `#container` > `ul.navigation:eq(0)` > `li.item:eq(0)` (&quot; > &quot; indica o filho imediato).

   `eq` fornece o índice do elemento que tem &quot;tagName=UL&quot; e a primeira classe `navigation`. Portanto, `index` é 0. Consulte o artigo [Seletores](https://developer.mozilla.org/en-US/docs/Web/Guide/CSS/Getting_started/Selectors) no site MDN para obter mais informações.

1. Se um elemento não contiver uma classe, [!DNL Target] usará `tagName` para o elemento e navegará pelo elemento pai até que o elemento `<HTML>` ou um elemento com uma ID seja encontrado.

   Por exemplo:

   ```html
   <div class="wrapper">
     <div id="container"> <!-- id is present here. It contributes to selector -->
       <ul class="navigation">
         <li> Home </li>
         <li> Men </li>
         <li class="active"> Women </li>
         <li> Kids </li><!-- Selector is computed for this element -->
       </ul>
     </div>
   </div>
   ```

   O seletor é `#container` > `ul.navigation:eq(0)` > `li:nth-of-type(4)`.

Neste processo:

* Qualquer seletor de CSS pode ser usado, desde que identifique exclusivamente um elemento no DOM.
* A abordagem acima é aquela usada por [!DNL Target]. [!DNL Target] não exige essa abordagem. Qualquer seletor pode ser adicionado, desde que ele identifique exclusivamente o elemento.
* Qualquer atributo pode ser usado no seletor. Este artigo usa apenas um nome de classe como exemplo.
