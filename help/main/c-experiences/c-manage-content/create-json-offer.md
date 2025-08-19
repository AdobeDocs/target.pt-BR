---
keywords: oferta json;criar oferta json
description: Saiba como criar ofertas JSON para usar no [!UICONTROL Form-Based Experience Composer].
title: Como criar ofertas JSON?
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: e8201198dc6ac36e803153d5c6b345a30716204a
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 25%

---

# Criar ofertas JSON

Crie ofertas JSON no [!UICONTROL Offer Library] em [!DNL Adobe Target] para usar no [!UICONTROL Form-Based Experience Composer].

As ofertas JSON podem ser usadas em atividades baseadas em formulário para habilitar casos de uso em que a decisão do [!DNL Target] é necessária para enviar uma oferta no formato JSON para consumo na estrutura SPA ou em integrações no lado do servidor.

## Considerações JSON

Considere as informações a seguir ao trabalhar com ofertas JSON:

* As ofertas JSON estão disponíveis no momento apenas para atividades do [!UICONTROL A/B Test], [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Experience Targeting] (XT).
* As ofertas JSON podem ser usadas somente em [atividades baseadas em formulário](/help/main/c-experiences/form-experience-composer.md).
* As ofertas JSON podem ser recuperadas diretamente quando você estiver usando as [APIs do Server Side e os SDKs Node.js para dispositivos móveis, Java, .NET e Python](https://experienceleague.adobe.com/en/docs/target-dev/developer/server-side/server-side-overview){target=_blank}.
* No navegador, as ofertas JSON podem ser recuperadas apenas via at.js 1.2.3 (ou posterior) e usando [getOffer()](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank} ao filtrar ações usando a ação `setJson`.
* As ofertas JSON são entregues como objetos JSON nativos, e não como cadeia de caracteres. Os consumidores desses objetos não precisam mais manipular objetos como cadeia de caracteres e convertê-los em objetos JSON.
* As ofertas JSON não são aplicadas automaticamente em oposição a outras ofertas (como ofertas de HTML) porque as ofertas JSON são ofertas não visuais. Os desenvolvedores devem gravar o código para obter explicitamente a oferta usando [getOffer()](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer){target=_blank}.

## Criar uma oferta JSON {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Clique em **[!UICONTROL Offers]** > **[!UICONTROL Code Offers]**.
1. Clique em **[!UICONTROL Create Offer]** > **[!UICONTROL JSON Offer]**.
1. Insira um nome de oferta.
1. (Condicional) Se você tiver uma [[!DNL Target] conta Premium](/help/main/c-intro/intro.md#premium), escolha o [espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#workspace) desejado.
1. (Condicional) Escolha os atributos de perfil desejados.
1. Digite ou cole seu código JSON na caixa **[!UICONTROL Code]**.
1. Clique em **[!UICONTROL Create]**.

## Exemplo de JSON {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

Só há suporte para ofertas JSON em atividades criadas com o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Atualmente, a única maneira de poder usar ofertas JSON é por meio de chamadas diretas de API/SDK.

Exemplo:

![Caixa de diálogo Criar oferta JSON](/help/main/c-experiences/c-manage-content/assets/json-example.png)

As ações passadas para o retorno de chamada de sucesso são uma matriz de objetos. Supondo que você tenha uma única oferta JSON, que tenha este conteúdo:

```json
{ 
  "demo": {"a": 1, "b": 2} 
}
```

A matriz de ações tem esta estrutura:

```json
[ 
 { 
   action: "setJson", 
   content: [{ 
     "demo": {"a": 1, "b": 2} 
   }] 
 }  
]
```

Para extrair a oferta JSON, faça uma iteração por meio de ações e encontre a ação com a ação `setJson` e, em seguida, percorra a matriz de conteúdo.

## Caso de uso {#section_85B07907B51A43239C8E3498EF58B1E5}

Digamos que a seguinte oferta JSON seja entregue em sua página da Web:

```json
{ 
    "_id": "5a65d24d8fafc966921e9169", 
    "index": 0, 
    "guid": "7c006504-c6f7-468d-a46f-f72531ea454c", 
    "isActive": true, 
    "balance": "$2,075.06", 
    "picture": "https://placehold.it/32x32", 
    "tags": [ 
      "esse", 
      "commodo", 
      "excepteur"
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      } 
    ], 
    "greeting": "Hello, Stephenson Fernandez! You have 4 unread messages.", 
    "favoriteFruit": "strawberry" 
} 
  
```

O código a seguir mostra como acessar o atributo &quot;saudação&quot;:

```json
adobe.target.getOffer({   
  "mbox": "name_of_mbox", 
  "params": {}, 
  "success": function(offer) {           
        console.log(offer[0].content[0].greeting); 
  },   
  "error": function(status, error) {           
      console.log('Error', status, error); 
  } 
});
```

## Exemplo de oferta JSON usando atributos de perfil da Real-time CDP

Os Atributos de Perfil da Real-time CDP podem ser compartilhados com [!DNL Target] para uso em ofertas HTML e JSON.

Para obter mais informações, consulte [Compartilhar Atributos de Perfil da Real-time CDP com o [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes).

## Filtrar ofertas por tipo de oferta JSON {#section_52533555BCE6420C8A95EB4EB8907BDE}

Você pode filtrar a biblioteca [!UICONTROL Offers] pelo tipo de oferta JSON ao clicar no ícone **[!UICONTROL Show filters]** ( ![ícone Mostrar filtros](/help/main/assets/icons/Filter.svg) ) e marcar a caixa de seleção **[!UICONTROL JSON Offers]**.
