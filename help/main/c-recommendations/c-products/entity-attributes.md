---
keywords: entidade; atributos de entidade, transmitir informações para o Recommendations, dados comportamentais, contador de dados, definir URL relativo, exibir nível de inventário, definir preço, definir margem de lucro, atributos personalizados
description: Saiba como usar atributos de entidade para transmitir informações de produto ou conteúdo ao  [!DNL Target] Recommendations.
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
title: Como usar atributos de entidade?
feature: Recommendations
exl-id: 4ed5fad3-b8b6-4675-a741-9f85cf73fcf1
source-git-commit: b6697eee5925cb8fa3b2fa2e107af0c617d30f94
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 48%

---

# Atributos da entidade

Use atributos de entidade para passar informações sobre o produto ou conteúdo para [!DNL Adobe Target Recommendations].

As entidades referem-se a itens que você quer recomendar. As entidades podem incluir produtos, conteúdo (artigos, apresentação de slides, imagens, filmes e programas de televisão), listas de trabalho, restaurantes e assim por diante.

[!DNL Recommendations] envia `productId` ou `productPurchasedId` (referido como `entity.id` no código) que é usado nos algoritmos.

Considere o seguinte:

* `entity.id` deve corresponder ao `productPurchasedId` enviado à página de confirmação do pedido e ao `productId` usado em [!DNL Adobe Analytics] relatórios de produto.
* Os valores de atributos de entidade passados para [!DNL Recommendations] expiram após 61 dias. A Adobe recomenda que você passe o valor mais recente de cada atributo de entidade para [!DNL Recommendations] pelo menos uma vez por mês para cada item do catálogo.

A maioria dos parâmetros predefinidos aceita apenas um único valor, enquanto os novos valores substituem os valores antigos. O parâmetro `categoryId` pode aceitar uma lista delimitada por vírgulas de valores de cada categoria que contenha esse produto. Os novos valores de `categoryId` não substituem os valores existentes, mas em vez disso são anexados durante a atualização da entidade (limite de 250 caracteres).

Em geral, a mbox de informações de exibição é semelhante ao seguinte exemplo se você estiver usando a at.js 1.*x* com `mboxCreate`. Todos os atributos de parâmetro de entidade fazem distinção entre maiúsculas e minúsculas.

>[!NOTE]
>
>Se estiver usando a at.js 2.Não há mais suporte para *x*, `mboxCreate` (como usado no exemplo a seguir). Para transmitir informações de produto ou conteúdo para [!DNL Recommendations] usando a at.js 2.*x*, use [targetPageParams](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/targetpageparams.html?lang=pt-BR){target=_blank}. Para obter um exemplo, consulte [Planejar e implementar o Recommendations](https://experienceleague.adobe.com/docs/target-dev/developer/recommendations.html?lang=pt-BR){target=_blank}.

```javascript
<div class="mboxDefault"></div><script language="JavaScript1.2"> 
 
mboxCreate('productPage', 
 
'entity.id=67833', 
 
'entity.name=GIANTS VS ROCKIES 5/12', 
 
'entity.categoryId=BASEBALL, GIANTS, SF BAY AREA', 
 
'entity.pageUrl=/help/baseball/giants-tix/giantsvrockies5.12.2000-67833', 
 
'entity.venue=AT&T PARK', 
 
'entity.secondary=ROCKIES', 
 
'entity.thumbnailUrl=/help/baseball/giants-tix/giants-136px.gif', 
 
'entity.message=FAMILY SPECIAL', 
 
'entity.value=15.99', 
 
'entity.inventory=1' 
 
); 
 
</script>
```

>[!NOTE]
>
>URLs relativos são preferidos para `pageUrl` e `thumbnailUrl` no lugar de URLs absolutos, pois os dados de recomendação recebem dados de todos os ambientes do seu site. O uso dos URLs relativos evita que os links inseridos no código para um servidor de preparação ou desenvolvimento.

Se a mbox estiver em uma página de produto, é possível incluir a ID de produto e de categoria. O algoritmo selecionado determina o que será exibido. A ID de produto é usada para algoritmos de afinidade e a ID de categoria para algoritmos de categoria.

## Variáveis disponíveis

A lista a seguir descreve as variáveis disponíveis.

### entity.id

Somente valor único.

Este parâmetro obrigatório identifica o produto. Esta ID alfanumérica deve ser igual em todos os produtos utilizados da [!DNL Adobe Experience Cloud], incluindo o [!DNL Analytics], para que os produtos reconheçam o item e compartilhem dados sobre ele.

Os valores `entity.id` devem *não* conter espaços, barras, &quot;E&quot; comercial, pontos de interrogação, símbolos de porcentagem, vírgulas ou outros caracteres de pontuação que exigem codificação de URL quando passados em uma chamada REST API. Hifens e sublinhados são permitidos. Incluir pontuação inválida em um valor `entity.id` [!DNL Recommendations] provoca falha em algumas funcionalidades do.

Exemplo: `'entity.id=67833'`

### entity.name

Somente valor único.

O nome do produto é exibido no site quando o produto é recomendado.

Exemplo: `'entity.name=Giants& vs& Rockies& 5/12'`

### entity.categoryId

Suporta valores múltiplos (lista separada por vírgulas).

Categoria da página atual. A entity.categoryID pode incluir várias categorias, como uma subseção de cardigãs (por exemplo, `womens`, `womens:sweaters`, `womens:sweaters:cardigans`). Categorias múltiplas devem ser separadas por vírgulas.

O valor `categoryId` é limitado a 250 caracteres.

>[!NOTE]
>
>Para mostrar uma recomendação com base em uma categoria da página [!UICONTROL Category], apenas um `categoryId` pode ser transmitido para a mbox usada para exibir essa determinada recomendação. O valor de `categoryId` deve corresponder exatamente ao valor de `entity.categoryId` passado na página [!UICONTROL Product Detail].

Exemplos:

* Exemplo de página de detalhes do produto: `womens`, `womens:sweaters`, `womens:sweaters:cardigans`
* Exemplo de Sweaters de Página de Categoria: `womens:sweaters`
* Exemplo de Cardigans de Página de Categoria: `womens:sweaters:cardigans`

Para recomendações baseadas em categorias, uma vírgula separa o valor da categoria. Quaisquer valores separados por vírgulas se tornam categorias. Você também pode definir subcategorias usando um separador diferente, como dois pontos (:), para separá-las dos valores de categoria.

Por exemplo, no código a seguir, a categoria Feminino é dividida em várias subcategorias:

```javascript
mboxCreate('mboxName', 'entity.id=343942-32', 'entity.categoryId= Womens, Womens:Outerwear, Womens:Outerwear:Jackets, Womens:Outerwear:Jackets:Parka, Womens:Outerwear:Jackets:Caban', 'entity.thumbnailUrl=...', 'entity.message=...', );
```

Para a entrega da mbox, o maior nome de atributo é usado para a chave. Se houver um vínculo, o último atributo será usado. No exemplo acima, a chave da categoria é `Womens:Outerwear:Jackets:Caban`.

### entity.brand

Somente valor único.

Exibe o nome da marca de um item.

Exemplo: `'entity.brand=brandxyz'`

### entity.pageUrl

Somente valor único.

Define o URL relativo da página onde o item pode ser comprado.

Exemplo: `'entity.pageUrl=baseball/giants-tix/giantsvrockies5.12.2000-67833'`

### entity.thumbnailUrl

Somente valor único.

Define o URL relativo da imagem em miniatura que é exibida com o item.

Exemplo: `'entity.thumbnailUrl=baseball/giants-tix/giants-136px.gif'`

### entity.message

Somente valor único.

A mensagem sobre o produto que é exibido na recomendação, como &quot;à venda&quot; ou &quot;promoção&quot;. A mensagem normalmente é mais detalhada do que o nome do produto. Use entity.message para definir informações adicionais para exibir com o produto no modelo.

Exemplo: `'entity.message=Family&nbsp;special'`

### entity.inventory

Somente valor único. Exige um valor inteiro ou longo.

Exibe o nível de inventário do item.

Exemplo: `'entity.inventory=1'`

**Tratamento de Atributo de Inventário Vazio:** Para a entrega, se você tiver uma regra de inclusão, regra de coleção ou uma configuração de critérios com `entity.inventory` > 0 ou `entity.inventory` = 0 e o produto não tiver o inventário definido, o [!DNL Target] avaliará esse valor como TRUE e incluirá os produtos com inventário não definido. Como resultado, os produtos com inventário não definido são exibidos nos resultados da recomendação.

Da mesma forma, se você tiver uma regra de exclusão global com `entity.inventory` = 0 e `entity.inventory` não definido, o [!DNL Target] avalia essa regra como TRUE e exclui o produto.

**Problema conhecido:** a Pesquisa de Produto está inconsistente com a entrega para atributos de valor de estoque não definidos. Por exemplo, para uma regra com `entity.inventory` = 0 , a Pesquisa de produto não exibe produtos em que o valor de inventário não está definido.

### entity.value

Somente valor único.

Define o preço ou o valor do item.

Exemplo: `'entity.value=15.99'`

entity.value suporta apenas o formato decimal (por exemplo, 15.99). O formato de vírgula (15,99) não é compatível.

### entity.margin

Somente valor único.

A margem de lucro ou outro valor do item.

Exemplo: `'entity.margin=1.00'`

### entidade.*custom*

Suporta vários valores (matriz JSON).

Defina até 100 variáveis personalizadas que oferecem informações adicionais sobre o item. É possível especificar qualquer nome de atributo não utilizado para cada atributo personalizado. Por exemplo, você pode criar um atributo personalizado chamado `entity.genre` para definir um livro ou filme. Um vendedor de ingressos pode criar atributos para o local onde um evento será realizado para um artista secundário, como uma equipe visitante em um evento esportivo ou um show de abertura em um concerto.

Restrições:

* Não é possível usar nomes de atributos de entidade predefinidos para atributos de entidade personalizados.
* O atributo entity.environment é reservado pelo sistema e não pode ser usado para atributos de entidade personalizados. Tentativas de enviar entity.environment usando targetPageParams, feed ou API são ignoradas.

Exemplos:

`'entity.venue=AT&T&nbsp;Park'`

`'entity.secondary=Rockies'`

Os atributos de entidade personalizados suportam vários valores. Consulte [Atributos de entidade personalizados](/help/main/c-recommendations/c-products/custom-entity-attributes.md#limits) para obter limites de caracteres e valores.

Exemplo: `'entity.secondary=["band1",&nbsp;"band2"]'`

Os atributos de entidade personalizados com vários valores exigem matrizes JSON válidas. Para obter informações de sintaxe corretas, consulte [Atributos de Entidade Personalizados](/help/main/c-recommendations/c-products/custom-entity-attributes.md).

### entity.event.detailsOnly

Somente valor único.

Usado para impedir que uma chamada de mbox incremente contadores de dados comportamentais para um algoritmo.

Exemplo: `'entity.event.detailsOnly=true'`

Nos exemplos abaixo, a primeira chamada de mbox atualiza o catálogo e os dados comportamentais. A segunda chamada de mbox atualiza somente o catálogo.

```javascript
mboxCreate('myMbox', 'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 'entity.inventory = 4' )
mboxCreate('myMbox',  'profile.geo.city = new york', 'profile.geo.state = new york',  'entity.id = 123', 'entity.inventory = 4' 'entity.event.detailsOnly=true' )
```

>[!MORELIKETHIS]
>
>* [Atributos de entidade personalizados](/help/main/c-recommendations/c-products/custom-entity-attributes.md#concept_E5CF39BCAC8140309A73828706288322)
