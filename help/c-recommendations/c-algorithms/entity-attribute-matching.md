---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;dynamic;entity attribute matching
description: Filtre dinamicamente no Adobe Target Recommendations comparando um pool de itens de recomendações potenciais a um item específico com o qual o usuário interagiu.
title: Filtrar por correspondência de atributo de entidade nas regras de inclusão dinâmica no Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 0%

---


# ![Correspondência de Atributo de Entidade PREMIUM](/help/assets/premium.png)

Filter dynamically in [!DNL Adobe Target] [!DNL Recommendations] by comparing a pool of potential recommendations items to a specific item that the user has interacted with.

>[!NOTE]
>
>The [process for creating and using inclusion rules](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) for criteria and promotions is similar, as are the use cases and examples.

Por exemplo, recomende somente itens que correspondam à marca do item atual, como no exemplo a seguir:

Se a mbox em uma Landing page de marca retornar `entity.brand=Nike`, somente os produtos Nike serão retornados e exibidos nessa página. Da mesma forma, na Landing page da Marca para o Adidas, apenas os produtos Adidas são devolvidos. Com esse tipo de regra de inclusão dinâmica, o usuário precisa especificar apenas uma regra de recomendação que retorna os resultados relevantes da marca em todas as páginas da marca, em vez de especificar uma coleção ou um filtro estático para corresponder a cada nome da marca.

Observe que você deve fornecer o conteúdo da mbox `entity.brand` nessas landings page para que isso funcione.

## Exemplos de Correspondência de Atributo de Entidade

[!UICONTROL A Correspondência] de Atributos de Entidade permite recomendar somente os itens que correspondem, por exemplo:

* Um atributo do item que o usuário está visualizando no momento
* O item que o usuário visualizou mais recentemente
* O item que o usuário comprou mais recentemente
* O item que o usuário visualizou com mais frequência
* Um item armazenado em um atributo personalizado no perfil do visitante

### Itens recomendados com base na marca

Depois que as regras de atributo da entidade forem criadas, elas filtrarão todas as recomendações com atributos que não correspondem ao valor da entidade passado na página.

O exemplo a seguir mostra recomendações que correspondem à marca do produto mostrada na página:

Quando você visita uma página que apresenta um produto Nike, a página define o valor do `entity.brand` parâmetro como &quot;Nike&quot;.

![Exemplo de chamada de Público alvo](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

Nas recomendações da página, você verá somente os produtos Nike.

![Recomendações Nike](/help/c-recommendations/c-algorithms/assets/nike.png)

Se você visualização uma página de produto Adidas, o `entity.brand` valor será redefinido para &quot;Adidas&quot; e você verá os produtos Adidas recomendados nas páginas de produto Adidas.

![Recomendações do Adidas](/help/c-recommendations/c-algorithms/assets/adidas.png)

### Venda a um produto mais caro

Suponha que você seja um varejista de roupas e queira incentivar os usuários a considerar itens com preços mais altos e, portanto, mais lucrativos. Você pode usar os operadores &quot;igual&quot; e &quot;é entre&quot; para promover itens mais caros que sejam da mesma categoria e da mesma marca. Por exemplo, um varejista de sapatos pode promover tênis de corrida mais caros em um esforço para vender um visitante olhando tênis de corrida, como na seguinte amostra de código:

```
Entity Attribute Matching
category - equals - current item's - category 
And 
Entity Attribute Matching
brand - equals - current item's - brand 
And 
Entity Attribute Matching
value - is between - 100% and 1000% of - current item's - value
```

### Promoção de produtos de etiquetas privadas

Você pode combinar filtros dinâmicos e estáticos para promover produtos de etiquetas privadas. Por exemplo, uma empresa de suprimento de escritório pode promover cartuchos de toner da marca da empresa para promover uma venda mais lucrativa para um visitante que olha para o toner — e promover canetas da marca da empresa para levar a uma venda mais lucrativa para um visitante que olha para as canetas, como na seguinte amostra de código:

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
