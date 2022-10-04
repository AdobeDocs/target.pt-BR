---
keywords: oferta remota; criar oferta remota
description: Saiba como criar ofertas JSON no Adobe [!DNL Target] para uso no Experience Composer baseado em formulário. As ofertas JSON são úteis para estruturas SPA ou integrações do lado do servidor.
title: Como crio ofertas JSON?
feature: Experiences and Offers
exl-id: 793665a4-4cd6-458f-8225-ba23e503a115
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 38%

---

# Criar ofertas JSON

Crie ofertas JSON no [!UICONTROL Biblioteca de ofertas] em [!DNL Adobe Target] para uso no [!UICONTROL Experience Composer baseado em formulário].

As ofertas JSON podem ser usadas em atividades baseadas em formulário, permitindo casos de uso em que [!DNL Target]A decisão do é necessária para enviar uma oferta no formato JSON para consumo em SPA estrutura ou integrações do lado do servidor.

## Considerações sobre JSON

Considere as informações a seguir ao trabalhar com ofertas JSON:

* Ofertas JSON estão disponíveis no momento somente para [!UICONTROL Teste A/B] e [!UICONTROL Direcionamento de experiência] (XT).
* Ofertas JSON podem ser usadas em [atividades baseadas em formulário](/help/main/c-experiences/form-experience-composer.md) somente.
* A oferta JSON pode ser recuperada diretamente quando você está usando a API do lado do servidor, o SDK para dispositivos móveis ou o SDK do NodeJS.
* No navegador, as ofertas JSON podem ser recuperadas APENAS via at.js 1.2.3 (ou posterior) e usando  [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank} filtrando ações usando o `setJson` ação.
* As ofertas JSON são entregues como objetos JSON nativos, e não como cadeia de caracteres. Os consumidores desses objetos não precisam mais manipular objetos como cadeia de caracteres e convertê-los em objetos JSON.
* As ofertas JSON não são aplicadas automaticamente em oposição a outras ofertas (como ofertas de HTML) porque as ofertas JSON são ofertas não visuais. Os desenvolvedores devem escrever o código para obter explicitamente a oferta usando  [getOffer()](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank}.

## Criar uma oferta JSON {#section_BB9C72D59DEA4EFB97A906AE7569AD7A}

1. Clique em **[!UICONTROL Ofertas]** > **[!UICONTROL Ofertas de código]**.

   ![Ofertas > guia Ofertas de código](/help/main/c-experiences/c-manage-content/assets/code-offers-tab.png)

1. Clique em **[!UICONTROL Criar]** > **[!UICONTROL Oferta JSON]**.

   ![imagem offer-json](assets/offer-json.png)

1. Insira um nome de oferta.
1. Insira ou cole seu código JSON na caixa **[!UICONTROL Código]**.
1. Clique em **[!UICONTROL Salvar]**.

## Exemplo de JSON {#section_A54F7BB2B55D4B7ABCD5002E0C72D8C9}

As ofertas JSON são suportadas apenas em atividades criadas usando o [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md). Atualmente, a única maneira de possível de usar as ofertas JSON é por meio de chamadas diretas à API.

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

A matriz de ações terá essa estrutura:

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

Para extrair a oferta JSON, faça uma iteração por meio de ações e encontre a ação com a variável `setJson` e, em seguida, percorra a matriz de conteúdo.

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

## Exemplo de oferta JSON usando atributos de perfil da CDP em tempo real

Os atributos de perfil da CDP em tempo real podem ser compartilhados com o Target para uso na oferta do HTML e em ofertas JSON. (Observe que esse recurso está atualmente na versão beta.)

Caso de uso de exemplo: Como comerciante online, a Grace quer que o Perfil AEP/Unified compartilhe valores de atributo com o Target para fornecer personalização em tempo real. Ao usar Atributos de perfil da CDP em tempo real, o Grace pode exibir o valor do atributo AEP em uma oferta do Target usando a substituição de token. Por exemplo, ela pode personalizar de acordo com a cor favorita de um cliente usando `${aep.profile.favoriteColor}`ou seu nível de fidelidade e valor do ponto de fidelidade usando os tokens `${aep.loyalty.tier}` e `${aep.loyalty.points}`.

![offer-json-aep-shared-attribute image](assets/offer-json-aep-shared-attribute.png)

No exemplo mostrado acima, observe que a atribuição de valores padrão é opcional.

## Filtragem de ofertas pelo tipo de oferta JSON {#section_52533555BCE6420C8A95EB4EB8907BDE}

Você pode filtrar a variável [!UICONTROL Ofertas] biblioteca pelo tipo de oferta JSON clicando no botão **[!UICONTROL Tipo]** lista suspensa e, em seguida, selecionando a **[!UICONTROL JSON]** caixa de seleção.

![imagem do filtro de oferta-json](assets/offer-json-filter.png)
