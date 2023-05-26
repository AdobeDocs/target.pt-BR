---
keywords: oferta remota; criar oferta remota
description: Saiba como criar ofertas JSON no Adobe [!DNL Target] para uso no Experience Composer baseado em formulário.
title: Como criar ofertas JSON?
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 32%

---

# Criar ofertas JSON

Criar ofertas JSON no [!UICONTROL Biblioteca de ofertas] in [!DNL Adobe Target] para uso na [!UICONTROL Experience Composer baseado em formulário].

As ofertas JSON podem ser usadas em atividades baseadas em formulários, permitindo casos de uso em que [!DNL Target] a decisão é necessária para enviar uma oferta no formato JSON para consumo na estrutura SPA ou em integrações do lado do servidor.

## Considerações JSON

Considere as informações a seguir ao trabalhar com ofertas JSON:

* No momento, as ofertas JSON estão disponíveis apenas para [!UICONTROL Teste A/B], Automated Personalization (AP) e [!UICONTROL Direcionamento de experiência] (XT) Atividades.
* As ofertas JSON podem ser usadas no [atividades baseadas em formulário](/help/main/c-experiences/form-experience-composer.md) somente.
* A oferta JSON pode ser recuperada diretamente ao usar o [APIs do lado do servidor e SDKs Node.js móveis, Java, .NET e Python](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/server-side-overview.html){target=_blank}.
* No navegador, as ofertas JSON podem ser recuperadas SOMENTE via at.js 1.2.3 (ou posterior) e usando [getOffer()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer.html){target=_blank} ao filtrar ações usando o `setJson` ação.
* As ofertas JSON são entregues como objetos JSON nativos, e não como cadeia de caracteres. Os consumidores desses objetos não precisam mais manipular objetos como cadeia de caracteres e convertê-los em objetos JSON.
* As ofertas JSON não são aplicadas automaticamente em oposição a outras ofertas (como ofertas de HTML) porque as ofertas JSON são ofertas não visuais. Os desenvolvedores devem escrever o código para obter explicitamente a oferta usando  [getOffer()](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/functions-overview/adobe-target-getoffer.html){target=_blank}.

## Criar uma oferta JSON {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Clique em **[!UICONTROL Ofertas]** > **[!UICONTROL Ofertas de código]**.

   ![Ofertas > guia Ofertas de código](/help/main/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta JSON]**.

   ![imagem offer-json](assets/offer-json.png)

1. Insira um nome de oferta.
1. Insira ou cole seu código JSON na caixa **[!UICONTROL Código]**.
1. Clique em **[!UICONTROL Salvar]**.

## Exemplo de JSON {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

As ofertas JSON são suportadas somente em atividades criadas usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Atualmente, a única maneira de poder usar ofertas JSON é por meio de chamadas diretas de API/SDK.

Exemplo:

```json
adobe.target.getOffer({ 
  mbox: "some-mbox", 
  success: function(actions) { 
    console.log('Success', actions); 
  }, 
  error: function(status, error) { 
    console.log('Error', status, error); 
  } 
});
```

As ações passadas para o retorno de chamada de sucesso são uma matriz de objetos. Supondo que tenhamos uma única oferta JSON, que tenha esse conteúdo:

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

Para extrair a oferta JSON, faça uma iteração por meio de ações e encontre a ação com o `setJson` e, em seguida, percorra a matriz de conteúdo.

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
      "excepteur", 
    ], 
    "friends": [ 
      { 
        "id": 0, 
        "name": "Carla Lyons" 
      }, 
      { 
        "id": 1, 
        "name": "Ollie Mooney" 
      }, 
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

Os atributos de perfil da Real-time CDP podem ser compartilhados com [!DNL Target] para uso na oferta HTML e ofertas JSON. (Observe que esse recurso está atualmente na versão beta.)

Para obter mais informações, consulte [Compartilhar atributos de perfil da Real-time CDP com a [!DNL Target]](/help/main/c-integrating-target-with-mac/integrating-with-rtcdp.md#rtcdp-profile-attributes).

## Filtrar ofertas por tipo de oferta JSON {#section_52533555BCE6420C8A95EB4EB8907BDE}

É possível filtrar a variável [!UICONTROL Ofertas] biblioteca pelo tipo de oferta JSON clicando no link **[!UICONTROL Tipo]** e, em seguida, selecionando a opção **[!UICONTROL JSON]** caixa de seleção

![imagem offer-json-filter](assets/offer-json-filter.png)
