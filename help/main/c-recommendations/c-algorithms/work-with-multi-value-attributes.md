---
keywords: vários valores;atributos;recomendações;vários valores;vários valores
description: Saiba como trabalhar com um campo de vários valores no Adobe [!DNL Target] Recommendations usando operadores especiais de vários valores, por exemplo, ao recomendar filmes com vários atores.
title: Posso usar atributos de vários valores no Recommendations?
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 9%

---

# Trabalhar com atributos de vários valores

Às vezes, você pode querer trabalhar com um campo de vários valores. Considere os exemplos a seguir:

* Você oferece filmes aos usuários. Determinado filme tem vários atores.
* Você vende ingressos para shows. Um determinado usuário tem várias bandas favoritas.
* Você vende roupas. Uma camisa está disponível em vários tamanhos.

Para lidar com recomendações nesses cenários, você pode passar dados de vários valores para [!DNL Target Recommendations] e usar operadores especiais de vários valores.

Para permitir que [!DNL Recommendations] identifique dados de vários valores, eles devem ser enviados como uma matriz JSON, como nas amostras de código abaixo.

## Passar um parâmetro de vários valores no JavaScript

```
function targetPageParams() { 
  return { 
    'entity.id':                   '123', 
    'entity.categoryId':            '["A", "A:B", "A:B:C", "A:B:C:D"]',        
    'entity.MultiValueAttribute':   '["X", "Y", "Z"]', 
    'entity.event.detailsOnly':     'true', 
    'excludedIds":                  '[123, 3232, 2323, 4344]', 
    'orderId":                      '123456', 
    'orderTotal":                   '195.32', 
    'productPurchaseId":            '[001,002,003]' 
  }; 
}
```

Para obter mais informações, consulte [Implementação de atributos de vários valores](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) em *Atributos de entidade personalizados*.

## Passar um atributo de entidade de vários valores em um arquivo CSV

```
## RECSRecommendations Upload File,,,,,,,,,,,,,,,,,,,
## RECS''## RECS'' indicates a Recommendations pre-process header. Please do not remove these lines.,,,,,,,,,,,,,,,,,,,
## RECS,,,,,,,,,,,,,,,,,,,
## RECSUse this file to upload product display information to Recommendations. Each product has its own row. Each line must contain 19 values and if not all are filled a space should be left.,,,,,,,,,,,,,,,,,,,
## RECSThe last 100 columns (entity.custom1 - entity.custom100) are custom. The name 'customN' can be replaced with a custom name such as 'onSale' or 'brand'.,,,,,,,,,,,,,,,,,,,
## RECSIf the products already exist in Recommendations then changes uploaded here will override the data in Recommendations. Any new attributes entered here will be added to the product''s entry in Recommendations.,,,,,,,,,,,,,,,,,,,
## RECSentity.id ,entity.name,entity. categoryId ,entity. message ,entity.thumbnailUrl ,entity.value ,entity.pageUrl ,entity.inventory ,entity.margin ,entity.custom1 ,entity.custom2 ,entity.custom3 ,entity.custom4,entity.custom5,entity.custom6,entity.custom7,entity.custom8,entity.custom9,entity.custom10,
1,Sample Product 1,category1,Save 10%,http://sample.store/products/images/product1_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=1,1000,48,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
2,Sample Product 2,category1,Save 10%,http://sample.store/products/images/product2_th.jpg,369,http://sample.store/products/product_detail.jsp?productId=2,1000,52,a,"[ ""v1"", ""v2"" ]",, , , , , , , ,
3,Sample Product 3,category1,Save 10%,http://sample.store/products/images/product3_th.jpg,479,http://sample.store/products/product_detail.jsp?productId=3,1000,78,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
4,Sample Product 4,category1,Save 10%,http://sample.store/products/images/product4_th.jpg,409,http://sample.store/products/product_detail.jsp?productId=4,1000,66,a,"[ ""v1"", ""v2"" ]",,,,,,,,,
5,Sample Product 5,category1,Save 10%,http://sample.store/products/images/product5_th.jpg,325,http://sample.store/products/product_detail.jsp?productId=5,1000,45,a,"[ ""v1"", ""v2"" ]",,,,,,,,, 
```

Quando um atributo de entidade, atributo de perfil ou parâmetro de mbox é fornecido como vários valores de acordo com o formato acima, o [!DNL Recommendations] infere automaticamente que o campo tem vários valores.

Os seguintes operadores estão disponíveis para uso com atributos de entidade, perfil e mbox de vários valores:

* [!UICONTROL is contained in list]
* [!UICONTROL is not contained in list]

## Trabalhar com atributos de vários valores em regras de inclusão

>[!NOTE]
>
>No momento, o suporte para correspondência dinâmica a atributos de vários valores está disponível apenas em critérios do ao usar uma regra de correspondência de atributo de perfil ou de correspondência de atributo de parâmetro (mbox) ao comparar um único valor do lado esquerdo com um multivalor do lado direito. Atualmente, os atributos de vários valores não são permitidos em promoções, na correspondência de atributos de entidade ou em listas no lado esquerdo das regras de inclusão.

### Exemplo: Excluir itens observados recentemente

Suponha que você queira impedir que qualquer filme que esteja nos últimos dez filmes assistidos do usuário seja recomendado. Primeiro, escreva um script de perfil chamado `user.lastWatchedMovies` para rastrear os últimos dez filmes visualizados como uma matriz JSON. Em seguida, é possível excluir os itens usando a seguinte regra de inclusão:

```
`Profile Attribute Matching`
`id - is not contained in list - user.lastWatchedMovies`
```

Representação da API JSON da regra de inclusão:

```
{
    "attribute": "id",
    "operation": "isNotContainedInList",
    "source": {
        "name": "user.lastWatchedMovies",
        "type": "PROFILE"
    }
} 
```

### Exemplo: itens recomendados dos favoritos do usuário

Suponha que você queira recomendar ingressos somente para shows se a banda tocando for uma das bandas favoritas do usuário. Primeiro, verifique se você tem uma variável de perfil chamada `profile.favoriteBands` que contém as bandas favoritas do usuário. Em seguida, verifique se o catálogo inclui um atributo `entity.artistPerforming` que inclui o artista que atua no concerto. Em seguida, é possível usar a seguinte regra de inclusão:

```
`Profile Attribute Matching`
`artistPerforming - is contained in list - profile.favoriteBands`
```

Representação da API JSON da regra de inclusão:

```
{
    "attribute": "artistPerforming",
    "operation": "isContainedInList",
    "source": {
        "name": "profile.favoriteBands",
        "type": "PROFILE"
    }
}
```

### Exemplo: criação de critérios pela API recomendando itens dos favoritos de um usuário

Critérios usando regras de filtragem de vários valores, como todos os critérios, podem ser criados por meio de APIs Adobe I/O. Um exemplo de chamada de API para criar um critério em que o atributo de entidade `id` está contido na lista de parâmetros de mbox `favorites` é fornecido aqui:

```
curl -X POST \
  https://<serverhost>/api/recs/<client>/criteria/item \
  -H 'Accept: application/vnd.adobe.target.v1+json' \
  -H 'Accept-Encoding: gzip, deflate' \
  -H 'Cache-Control: no-cache' \
  -H 'Connection: keep-alive' \
  -H 'Content-Type: application/json' \
  -H 'User-Agent: <from API client>' \
  -H 'X-Target-user-email: <email address>' \
  -H 'cache-control: no-cache' \
  -d '{
    "name": "viewed criteria",
    "criteriaTitle": "test title",
    "type": "VIEWED_CF",
    "key": "CURRENT",
    "daysCount": "TWO_WEEKS",
    "aggregation": "NONE",
    "backupDisabled": false,
    "partialDesignAllowed": true,
    "configuration": {
        "inclusionRules": [
            {
                "attribute": "id",
                "operation": "isContainedInList",
                "source": {
                    "name": "mbox.favorites",
                    "type": "MBOX"
                }
            }
        ]
    }
}'
```

Isso seria emparelhado com o JavaScript na página para transmitir o conteúdo dos favoritos:

```
<!-- pass in the value of mbox parameter “favorites” as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
