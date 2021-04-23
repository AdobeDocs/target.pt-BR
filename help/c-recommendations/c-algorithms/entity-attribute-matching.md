---
keywords: regras de inclusão, critérios de inclusão, recomendações, promoção, promoções, filtragem dinâmica, dinâmica, correspondência de atributos de entidade
description: Saiba como filtrar dinamicamente no Adobe [!DNL Target] Recommendations, comparando um conjunto de itens em potencial a um item específico com o qual o usuário interagiu.
title: Como faço para filtrar por Correspondência de Atributos de Entidade nas Atividades do Recommendations?
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '524'
ht-degree: 0%

---

# ![](/help/assets/premium.png) PREMIUMECorrespondência de atributos de entidade

Filtre dinamicamente em [!DNL Adobe Target] [!DNL Recommendations] comparando um conjunto de possíveis itens de recomendações a um item específico com o qual o usuário interagiu.

>[!NOTE]
>
>O processo [para criar e usar regras de inclusão](/help/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para critérios e promoções é semelhante, assim como os casos de uso e exemplos.

Por exemplo, recomende somente itens que correspondam à marca do item atual, como no exemplo a seguir:

Se a mbox em uma Página de aterrissagem da marca retornar `entity.brand=brandA`, somente os produtos da Marca A serão retornados e exibidos nessa página. Da mesma forma, na Página de aterrissagem da marca da Marca B, somente os produtos da Marca B são retornados. Com esse tipo de regra de inclusão dinâmica, o usuário precisa especificar apenas uma regra de recomendação que retorna os resultados relevantes da marca em todas as páginas da marca, em vez de especificar uma coleção ou um filtro estático para corresponder a cada nome de marca.

Observe que você deve entregar o `entity.brand` na mbox nessas landing pages para que isso funcione.

## Exemplos de Correspondência de atributos de entidade

[!UICONTROL A ] Correspondência de atributos de entidade permite recomendar apenas os itens que correspondem, por exemplo:

* Um atributo do item que o usuário está visualizando no momento
* O item que o usuário visualizou mais recentemente
* O item que o usuário comprou mais recentemente
* O item que o usuário visualizou com mais frequência
* Um item armazenado em um atributo personalizado no perfil do visitante

### Itens recomendados com base na marca

Depois que as regras do atributo da entidade forem criadas, elas filtrarão todas as recomendações com atributos que não correspondem ao valor da entidade transmitido na página.

O exemplo a seguir mostra recomendações correspondentes à marca de produto mostradas na página:

Quando você visita uma página que possui um produto da Marca A, a página define o valor do parâmetro `entity.brand` como &quot;BrandA&quot;.

![Exemplo de chamada do Target](/help/c-recommendations/c-algorithms/assets/example-target-call.png)

Nas recomendações da página, você verá somente os produtos da Marca A.

![Recomendações da marca A](/help/c-recommendations/c-algorithms/assets/brandA.png)

Se você exibir uma página de produto da Marca B, o valor `entity.brand` será redefinido para &quot;MarcaB&quot; e você verá os produtos da Marca B recomendados nas páginas de produto da Marca B.

![Recomendações da Marca B](/help/c-recommendations/c-algorithms/assets/brandB.png)

### Atualizar para um produto mais caro

Suponha que você seja um varejista de vestuário e queira incentivar os usuários a considerar os itens com preços mais altos e, portanto, mais rentáveis. Você pode usar os operadores &quot;equals&quot; e &quot;is between&quot; para promover itens mais caros que sejam da mesma categoria e da mesma marca. Por exemplo, um varejista de sapatos pode promover sapatos de corrida mais caros em um esforço de fazer uma venda agregada de um visitante que visualiza sapatos de corrida, como na seguinte amostra:

![Aumento](/help/c-recommendations/c-algorithms/assets/upsell.png)

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

### Promoção de produtos de marca privada

Você pode misturar filtros dinâmicos e estáticos para promover produtos de rótulo privado. Por exemplo, uma empresa de fornecimento de escritórios pode promover cartuchos de toner da marca própria da empresa para impulsionar uma venda mais lucrativa para um visitante que olha para toner — e promover canetas da marca de casa da empresa para impulsionar uma venda mais lucrativa para um visitante que visualiza canetas, como na amostra a seguir:

![House Brand](/help/c-recommendations/c-algorithms/assets/housebrand.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
