---
keywords: Recommendations
description: Explore cenários comuns que mostram como as alterações feitas em sua página no Visual Experience Composer (VEC) afetam a capacidade da Adobe Target de exibir uma experiência.
title: Quais São Alguns Cenários Comuns De Modificação De Página?
feature: Visual Experience Composer (VEC)
exl-id: 7a05fbf9-3427-436e-a54f-4f1dd16d885a
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '532'
ht-degree: 90%

---

# Cenários de modificação da página

Os cenários neste tópico mostram como as alterações feitas em sua página afetam a capacidade da Adobe Target de exibir uma experiência.

O seletor do Target determina onde exibir uma experiência. Se uma página for modificada fora do Target, as alterações poderão afetar a capacidade de o Target exibir a experiência.

Durante o uso do seletor, a classe única não é equivalente à ID. O seletor sempre funciona com uma classe única. Se nenhuma classe for atribuída ao elemento, o seletor calculará o número de irmãos anteriores que têm o mesmo nome de tag.

>[!NOTE]
>
>Embora esses cenários usem itens de lista como exemplos, os conceitos se aplicam a qualquer elemento.

## Cenário: insira um elemento com um nome de classe diferente antes do elemento selecionado {#section_298F661F72384F6AB957D5885A99D822}

Neste exemplo, um novo elemento foi inserido como um irmão do elemento no seletor do Target.

Há uma possibilidade de a primeira classe presente no elemento poder ser adicionada pelo JavaScript. Nesse caso, a entrega falha e a ação não é aplicada.

**Elemento inserido:**

```html
<li class="kids-section">Kids</li>
```

**Selecionado:**

`<li class="women-section">Women</li>`

Seletor: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

O seletor funciona como esperado, pois `li.women-section:eq(0)` não é afetado.

Antes:

```html
<div id="wrap">
     <ul class="nav">
        <li class="men-section"> Men</li> <li class="women-section">Women</li>
     </ul> 
</div>
```

Depois:

```html
<div id="wrap">
    <ul class="nav">
        <li class="kids-section">Kids</li>
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

## Cenário: insira um elemento com o mesmo nome de classe do elemento selecionado {#section_0969B88C2F154E648D9969C8C85EF55A}

Neste cenário, é feita uma tentativa de inserir uma lista quando um item em uma lista é selecionado.

**Elemento inserido:**

```html
<ul class="nav"> 
   <li class="item"> Sale </li> 
   <li> class="item"> Offers </li> 
</ul>
```

**Selecionado**

`<li class="women-section">Women</li>`

Seletor: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

O seletor não funciona, pois `ul.nav:eq(0)` fornece um elemento adicionado dinamicamente. O elemento não estará disponível e a ação não será aplicada. Quando um item de lista semelhante com a mesma classe é adicionado de modo dinâmico ou manual após a criação de uma atividade, um novo elemento é criado na primeira posição. Isso interrompe o seletor.

Antes:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section"> Men</li>       <li class="women-section">Women</li>
    </ul> 
</div>
```

Depois (tentativa):

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

## Cenário: insira um elemento depois do elemento selecionado {#section_15B07B84BEE94ED39D85BBBE0733E170}

Neste cenário, um item de lista é inserido após o elemento selecionado.

**Elemento inserido:**

```html
<ul class="nav"> 
   <li class="men-section"> Men Clothes</li> 
   <li class="women-section"> Women Clothes</li> 
</ul>
```

**Selecionado:**

`<li class="women-section">Women Shoes</li>`

Seletor: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

Nesse caso, insira uma lista depois do fim da lista com o item de lista selecionado funcionando conforme esperado. O novo elemento é adicionado à mesma posição do elemento selecionado em relação ao elemento pai.

Antes:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>       <li class="women">Women Shoes</li>
    </ul>
</div>
```

Depois:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men">Men Shoes </li>
        <li class="women">Women Shoes</li>
    </ul>
      <ul class="nav">
        <li class="men-section">Men Clothes</li>
        <li class="women-section"> Women Clothes</li>
    </ul>
</div>
```

## Cenário: remova o elemento imediatamente antes do outro elemento {#section_F193674F04F84AA593EAA1137C880EBA}

Neste cenário, o item de lista antes do elemento selecionado é excluído.

**Elemento removido:**

```html
<li class="men-section"> Men </li>
```

**Selecionado:**

`<li class="women-section">Women</li>`

Seletor: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

O elemento foi removido com êxito porque a classe do item selecionado não foi alterada.

Antes:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

Depois:

```html
<div id="wrap">
    <ul class="nav">
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Cenário: remova o elemento logo após o outro elemento {#section_F83B51BE54924FB58679D512DAF1EBB2}

Neste cenário, o item de lista depois do elemento selecionado é excluído.

**Elemento removido:**

```html
<li class="kids-section">Kids</li>
```

**Selecionado:**

`<li class="women-section">Women</li>`

Seletor: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

O elemento foi removido com êxito porque a classe do item selecionado não foi alterada. O elemento removido inclui uma classe única dentro de sua sub-árvore pai.

Antes:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
        <li class="kids-section">Women</li>
    </ul>
</div>
```

Depois:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

## Cenário: remova o elemento selecionado {#section_1989CF1E2C344CC5963084ED83C18F9C}

Neste cenário, o item de lista selecionado é excluído.

**Elemento removido:**

```html
<li class="women-shoes">Women</li>
```

**Selecionado:**

`<li class="women-shoes">Women</li>`

Seletor: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

O elemento foi removido com êxito.

Antes:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```

Depois

```html
<div id="wrap">
    <ul class="nav">
       <li class="men-section">Men</li>
    </ul>
</div>
```

## Cenário: renomeie a classe do elemento selecionado  {#section_79D244C588BA452DB8E433D82B7F63EA}

Neste cenário, a classe do item de lista selecionado foi alterada.

**Elemento alterado:**

```html
<li class="women-section">Women</li>
```

**Selecionado:**

`<li class="women-section">Women</li>`

Seletor: `#wrap > ul.nav:eq(0) > li.women-section:eq(0)`

**Resultado:**

Não é possível renomear a classe do elemento porque `class` não foi encontrado.

Antes:

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-section">Women</li>
    </ul>
</div>
```

Depois (tentativa):

```html
<div id="wrap">
    <ul class="nav">
        <li class="men-section">Men</li>
        <li class="women-shoes">Women</li>
    </ul>
</div>
```
