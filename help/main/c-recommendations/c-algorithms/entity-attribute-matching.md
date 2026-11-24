---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;dinâmico;correspondência de atributos de entidade
description: Saiba como filtrar dinamicamente no [!DNL Target Recommendations] comparando um pool de itens em potencial a um item específico com o qual o usuário interagiu.
title: Correspondência de atributo de entidade
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: aadd3132-d590-4dc9-b01b-bedf41bc7441
TQID: 'https://experienceleague.adobe.com/2cBSfWXS96u7iumehPd7enxPjQcebkQCdSBSHWOUcJg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 5%
---
# Correspondência de atributo de entidade {#entity-attribute-matching}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como filtrar recomendações dinamicamente em [!DNL Adobe Target Recommendations] comparando um pool de possíveis itens recomendados a um item específico com o qual o visitante interagiu.

>[!ENDSHADEBOX]

**[!UICONTROL Correspondência de atributos de entidade]** recomenda apenas os itens que correspondem a um atributo de um item com o qual o visitante interagiu. O processo para criar e usar regras de inclusão para critérios e promoções é semelhante, assim como os casos de uso e exemplos. Para obter mais informações, consulte [Usar regras de inclusão estática e dinâmica](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Exemplos de correspondência do atributo de entidade

**[!UICONTROL Correspondência de Atributos de Entidade]** pode recomendar somente os itens correspondentes, por exemplo:

* Um atributo do item que o visitante está visualizando no momento
* O item que o visitante visualizou mais recentemente
* O item que o visitante comprou mais recentemente
* O item que o visitante visualizou com mais frequência
* Um item armazenado em um atributo personalizado no perfil do visitante

### Recomendando itens com base na marca

Depois que as regras de atributo de entidade são criadas, elas filtram todas as recomendações com atributos que não correspondem ao valor de entidade transmitido na página. O valor `entity.brand` deve ser entregue na mbox nas páginas para que esse processo funcione.

Com esse tipo de regra de inclusão dinâmica, apenas uma regra de recomendação deve ser especificada para retornar resultados de marca relevantes em todas as páginas de marca, em vez de uma coleção ou um filtro estático para cada nome de marca.

Por exemplo, quando uma página com um produto da Marca A é exibida, a página define o valor do parâmetro `entity.brand` como &quot;MarcaA&quot;. Em uma página de aterrissagem de marca, a mbox retorna `entity.brand=brandA`.

![Exemplo de chamada do Target](/help/main/c-recommendations/c-algorithms/assets/example-target-call.png)

As recomendações na página contêm apenas os produtos da Marca A.

![Recomendações para a marca A](/help/main/c-recommendations/c-algorithms/assets/brandA.png)

Quando a página de um produto da Marca B é exibida, o valor `entity.brand` é redefinido para &quot;MarcaB&quot; e somente os produtos da Marca B são recomendados. Da mesma forma, na Landing page da Marca B, somente os produtos da Marca B são devolvidos.

![Recomendações sobre a Marca B](/help/main/c-recommendations/c-algorithms/assets/brandB.png)

### Venda adicional para um produto mais caro

Para incentivar os visitantes a considerar itens mais caros e, portanto, mais lucrativos, os operadores &quot;equals&quot; e &quot;is between&quot; podem promover itens mais caros da mesma categoria e da mesma marca. Por exemplo, uma retailer de sapatos pode promover tênis de corrida mais caros para fazer uma venda adicional de um visitante que está olhando para tênis de corrida, como na seguinte amostra:

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

Filtros dinâmicos e estáticos podem ser misturados para promover produtos de rótulo privado. Por exemplo, uma empresa de suprimentos de escritório pode promover cartuchos de toner da marca da empresa para direcionar uma venda mais lucrativa para um visitante que está olhando para o toner, e canetas da marca da empresa para um visitante que está olhando para canetas, como no exemplo a seguir:

![Marca da Casa](/help/main/c-recommendations/c-algorithms/assets/housebrand-new.png)

```
Entity Attribute Matching
category - equals - current item's - category 
And
Static Filter
IsHouseBrand - equals - true
```
