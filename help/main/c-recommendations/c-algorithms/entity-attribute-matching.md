---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;dinâmico;correspondência de atributos de entidade
description: Saiba como filtrar dinamicamente no  [!DNL Target Recommendations]  comparando um pool de itens em potencial a um item específico com o qual o usuário interagiu.
title: Como filtrar por Correspondência de atributos de entidade em atividades do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
source-git-commit: 02ffe8da6cdf96039218656b9690fa719a77910c
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Correspondência de atributos de entidade

Filtre dinamicamente em [!DNL Adobe Target Recommendations] comparando um pool de possíveis itens de recomendações a um item específico com o qual o usuário interagiu.

>[!NOTE]
>
>O [processo para criar e usar regras de inclusão](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md) para critérios e promoções é semelhante, assim como os casos de uso e exemplos.

Por exemplo, recomende somente itens que correspondam à marca do item atual, como no exemplo a seguir:

Se a mbox em uma página de aterrissagem de marca retornar `entity.brand=brandA`, somente os produtos da marca A serão retornados e exibidos nessa página. Da mesma forma, na Landing page da Marca B, somente os produtos da Marca B são devolvidos. Com esse tipo de regra de inclusão dinâmica, o usuário precisa especificar apenas uma regra de recomendação que retorne resultados de marca relevantes em todas as páginas de marca, em vez de especificar uma coleção ou um filtro estático para corresponder a cada nome de marca.

Observe que você deve fornecer o `entity.brand` na mbox nessas páginas de aterrissagem para que esse processo funcione.

## Exemplos de Correspondência de atributos de entidade

[!UICONTROL Entity Attribute Matching] permite que você recomende somente os itens correspondentes, por exemplo:

* Um atributo do item que o usuário está visualizando no momento
* O item exibido mais recentemente pelo usuário
* O item que o usuário comprou mais recentemente
* O item que o usuário visualizou com mais frequência
* Um item armazenado em um atributo personalizado no perfil do visitante

### Recomendando itens com base na marca

Depois que as regras de atributo de entidade forem criadas, elas filtrarão todas as recomendações com atributos que não correspondem ao valor de entidade transmitido na página.

O exemplo a seguir mostra recomendações que correspondem à marca de produto mostrada na página:

Quando você visita uma página que apresenta um produto da Marca A, a página define o valor do parâmetro `entity.brand` como &quot;MarcaA&quot;.

![Exemplo de chamada do Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

Nas recomendações da página, você verá somente os produtos da Marca A.

![Recomendações para a marca A](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Se, em seguida, você visualizar uma página de produto da Marca B, o valor `entity.brand` será redefinido para &quot;MarcaB&quot; e você verá produtos da Marca B recomendados nas páginas de produto da Marca B.

![Recomendações sobre a Marca B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Venda adicional para um produto mais caro

Suponha que você seja um retailer de vestuário e queira incentivar os usuários a considerar itens mais caros e, portanto, mais lucrativos. Você pode usar os operadores &quot;equals&quot; e &quot;is between&quot; para promover itens mais caros que sejam da mesma categoria e da mesma marca. Por exemplo, uma retailer de sapatos pode promover tênis de corrida mais caros em um esforço para fazer uma venda adicional de um visitante que procura tênis de corrida, como na seguinte amostra:

![Venda adicional](/help/main/c-recommendations/c-algorithms/assets/upsell-new.png)

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

### Promoção de produtos de rótulo privado

É possível misturar filtros dinâmicos e estáticos para promover produtos de rótulo privado. Por exemplo, uma empresa de suprimentos de escritório pode promover cartuchos de toner da marca da empresa para impulsionar uma venda mais lucrativa para um visitante que procura toner — e promover canetas da marca da empresa para impulsionar uma venda mais lucrativa para um visitante que procura canetas, como no exemplo a seguir:

![Marca da Casa](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)
)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
