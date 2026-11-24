---
keywords: vários valores;atributos;recomendações;vários valores;vários valores
description: Saiba como trabalhar com um campo de vários valores em [!DNL Target Recommendations] usando operadores especiais de vários valores.
title: Trabalhar com atributos de vários valores
feature: Recommendations
exl-id: 82018a9a-0983-458c-9387-3602dab4409b
TQID: 'https://experienceleague.adobe.com/FrjVxvYfGh2o-qomXRbVh6WS6f65Mja41gBMhejEPlE'
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
source-wordcount: '502'
ht-degree: 2%
---
# Trabalhar com atributos de vários valores {#multi-value-attributes}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como enviar dados de vários valores para [!DNL Adobe Target Recommendations] e como usá-los nas regras de inclusão com os operadores de vários valores.

>[!ENDSHADEBOX]

Um campo de vários valores contém vários valores para o mesmo item ou visitante. Por exemplo:

* Filmes oferecidos aos usuários: um determinado filme tem vários atores.
* Ingressos vendidos para shows: um determinado usuário tem várias bandas favoritas.
* Vestuário vendido: uma camisa está disponível em vários tamanhos.

Para lidar com recomendações nesses cenários, dados de vários valores podem ser passados para [!DNL Target Recommendations] e usados com operadores especiais de vários valores.

## Enviar dados de vários valores {#send}

Para permitir que [!DNL Recommendations] identifique dados de vários valores, eles devem ser enviados como uma matriz JSON.

Para um parâmetro de vários valores no JavaScript (`targetPageParams`), consulte [Implementação de atributos de vários valores](/help/main/c-recommendations/c-products/custom-entity-attributes.md#section_80FEFE49E8AF415D99B739AA3CBA2A14) em *Atributos de entidade personalizados*.

Em um arquivo CSV, um atributo de entidade de vários valores é enviado como uma matriz JSON na célula do atributo, como na amostra a seguir.

+++ Arquivo CSV de amostra com um atributo de vários valores

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

+++

Quando um atributo de entidade, atributo de perfil ou parâmetro de mbox é fornecido como vários valores neste formato, o [!DNL Recommendations] infere automaticamente que o campo tem vários valores.

## Usar atributos de vários valores nas regras de inclusão {#multi-value-inclusion-rules}

Os seguintes operadores estão disponíveis para uso com atributos de entidade, perfil e mbox de vários valores:

* **[!UICONTROL está contido na lista]**
* **[!UICONTROL não consta na lista]**

>[!NOTE]
>
>No momento, o suporte para correspondência dinâmica a atributos de vários valores está disponível apenas em critérios que usam uma regra de correspondência de atributos de perfil ou de parâmetro (mbox) que compara um único valor à esquerda a um múltiplo valor à direita. Atualmente, os atributos de vários valores não são permitidos em promoções, na correspondência de atributos de entidade ou em listas no lado esquerdo das regras de inclusão.

### Exemplo: Excluir itens observados recentemente

Para evitar que qualquer filme nos últimos dez filmes assistidos do usuário seja recomendado, primeiro escreva um script de perfil chamado `user.lastWatchedMovies` que rastreie os últimos dez filmes visualizados como uma matriz JSON. Os itens podem ser excluídos com a seguinte regra de inclusão:

```
Profile Attribute Matching
id - is not contained in list - user.lastWatchedMovies
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

Para recomendar ingressos de shows somente quando a banda tocando for uma das bandas favoritas do usuário, dois itens são necessários: uma variável de perfil chamada `profile.favoriteBands`, que contém as bandas favoritas do usuário, e um atributo `entity.artistPerforming` no catálogo que contém o artista tocando no concerto. A seguinte regra de inclusão pode ser usada:

```
Profile Attribute Matching
artistPerforming - is contained in list - profile.favoriteBands
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

Critérios que usam regras de filtragem de vários valores podem ser criados por meio das APIs [!DNL Adobe Target], como todos os critérios. O exemplo de chamada de API a seguir cria um critério em que o atributo de entidade `id` está contido na lista de parâmetros de mbox `favorites`:

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

Essa chamada é emparelhada com o JavaScript na página que passa o conteúdo dos favoritos:

```
<!-- pass in the value of mbox parameter "favorites" as JSON array -->
<script type="text/javascript">
   mboxCreate('myMbox','entity.id=<key>','favorites=["a","b","c"]');
</script>
```
