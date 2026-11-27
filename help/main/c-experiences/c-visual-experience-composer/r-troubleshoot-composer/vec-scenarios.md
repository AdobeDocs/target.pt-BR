---
keywords: Recomendações
description: Explore cenários comuns que mostram como as alterações feitas em sua página no Visual Experience Composer (VEC) afetam a capacidade da Adobe Target de exibir uma experiência.
title: Quais São Alguns Cenários Comuns De Modificação De Página?
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
TQID: 'https://experienceleague.adobe.com/BI2SnUU5ilCf0auld15q1rpCrnLoPEwbe1fZO6G1quc'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '626'
ht-degree: 4%
---
# Cenários de modificação da página {#vec-scenarios}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como as alterações feitas em uma página fora do [!DNL Target] afetam a capacidade do [!DNL Target] de exibir uma experiência por meio de sete cenários com exemplos.

>[!ENDSHADEBOX]

O seletor [!DNL Target] determina onde uma experiência é exibida. Quando uma página é modificada fora do [!DNL Target], as alterações podem afetar a capacidade do [!DNL Target] de encontrar esse local e exibir a experiência.

O seletor sempre funciona com uma classe exclusiva, que não é equivalente a uma ID. Quando nenhuma classe é atribuída ao elemento, o seletor conta os irmãos anteriores que têm o mesmo nome de tag.

>[!NOTE]
>
>Os cenários usam itens de lista como exemplos, mas os conceitos se aplicam a qualquer elemento.

A tabela a seguir resume os cenários. Em todos os cenários, o seletor é `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`.

| Cenário | Ação aplicada | Motivo |
|---|---|---|
| Inserir um elemento com um nome de classe diferente antes do elemento selecionado | Sim | `li.women-section:eq(0)` não foi afetado |
| Inserir um elemento com o mesmo nome de classe do elemento selecionado | Não | Um novo elemento ocupa a primeira posição, o que quebra o seletor |
| Inserir um elemento após o elemento selecionado | Sim | O novo elemento é adicionado na mesma posição em relação ao elemento principal |
| Remover o elemento imediatamente anterior ao elemento selecionado | Sim | A classe do item selecionado não é alterada |
| Remova o elemento imediatamente após o elemento selecionado | Sim | A classe do item selecionado não é alterada |
| Remover o elemento selecionado | Sim | O elemento foi removido com sucesso |
| Renomear a classe do elemento selecionado | Não | `class` não encontrado |

## Inserir um elemento com um nome de classe diferente antes do elemento selecionado

Um novo elemento é inserido como um irmão do elemento no seletor [!DNL Target]. Se a primeira classe no elemento foi adicionada pelo JavaScript, o delivery falhará e a ação não será aplicada.

**Elemento inserido:**

```html
<li class="kids-section">Kids</li>
```

**Elemento selecionado:**

`<li class="women-section">Women</li>`

**Seletor:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** o seletor funciona conforme esperado, pois `li.women-section:eq(0)` não foi afetado.

**Antes:**

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul>
</div>
```

**Depois de:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

## Inserir um elemento com o mesmo nome de classe do elemento selecionado

Uma lista é inserida enquanto um item de uma lista é selecionado.

**Elemento inserido:**

```html
<ul class="nav">
   <li class="item"> Sale </li>
   <li class="item"> Offers </li>
</ul>
```

**Elemento selecionado:**

`<li class="women-section">Women</li>`

**Seletor:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** o seletor não funciona. `ul.nav:eq(0)` agora aponta para um elemento adicionado dinamicamente, que não está disponível, portanto, a ação não é aplicada. Adicionar um item de lista semelhante com a mesma classe, de modo dinâmico ou manual, após a criação da atividade, coloca um novo elemento na primeira posição, o que quebra o seletor.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul>
</div>
```

**Depois (tentativa):**

```html
<div id="wrap">
     <ul class="nav">
        <li class="item"> Sale</li>
        <li> class="item"> Offers</li>
     </ul>
     <ul class="nav">
       <li class="men-section"> Men</li>
       <li class="women-section">Women</li>
    </ul>
</div>
```

## Inserir um elemento após o elemento selecionado

Uma lista é inserida após o item de lista selecionado.

**Elemento inserido:**

```html
<ul class="nav">
   <li class="men-section"> Men Clothes</li>
   <li class="women-section"> Women Clothes</li>
</ul>
```

**Elemento selecionado:**

`<li class="women-section">Women Shoes</li>`

**Seletor:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** Inserir uma lista após a lista que termina com o item selecionado funciona conforme esperado. O novo elemento é adicionado na mesma posição do elemento selecionado em relação ao elemento principal.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>       <li class="women-section">Women Shoes</li>
    </ul>
</div>
```

**Depois de:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men Shoes </li>
        <li class="women-section">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## Remover o elemento imediatamente anterior ao elemento selecionado

O item de lista antes da exclusão do elemento selecionado.

**Elemento removido:**

```html
<li class="men-section"> Men </li>
```

**Elemento selecionado:**

`<li class="women-section">Women</li>`

**Seletor:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** o elemento foi removido com êxito, pois a classe do item selecionado não foi alterada.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Depois de:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Remova o elemento imediatamente após o elemento selecionado

O item de lista após a exclusão do elemento selecionado.

**Elemento removido:**

```html
<li class="kids-section">Kids</li>
```

**Elemento selecionado:**

`<li class="women-section">Women</li>`

**Seletor:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** o elemento foi removido com êxito, pois a classe do item selecionado não é alterada e o elemento removido tem uma classe exclusiva em sua subárvore pai.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Kids</li>
    </ul>
</div>
```

**Depois de:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Remover o elemento selecionado

O item de lista selecionado é excluído.

**Elemento removido:**

```html
<li class="women-section">Women</li>
```

**Elemento selecionado:**

`<li class="women-section">Women</li>`

**Seletor:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** o elemento foi removido com êxito.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Depois de:**

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## Renomear a classe do elemento selecionado

A classe do item de lista selecionado é alterada.

**Elemento alterado:**

```html
<li class="women-section">Women</li>
```

**Elemento selecionado:**

`<li class="women-section">Women</li>`

**Seletor:** `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:** Não é possível renomear a classe porque `class` não foi encontrado.

**Antes:**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

**Depois (tentativa):**

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div> 
```
