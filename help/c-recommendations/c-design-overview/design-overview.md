---
description: Informações gerais sobre designs que definem como as recomendações são exibidas em uma página.
keywords: design de recomendações, modelo, criar design, entrega, saída
seo-description: Informações gerais sobre designs que definem como as recomendações são exibidas em uma página.
seo-title: Visão geral do design
solution: Target
title: Visão geral do design
topic: Premium
uuid: 82cc6a19-bfde-47b3-92b9-b862be70dd87
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Visão geral do design{#design-overview}

Informações gerais sobre designs que definem como as recomendações são exibidas em uma página.

O Target pode fornecer a aparência completa de suas recomendações, conforme mostrado na ilustração a seguir. O design pode incluir HTML, JavaScript e CSS.

![](assets/velocity_example.png)

O Target também pode enviar suas recomendações como objetos JSON que podem ser usados em mensagens de email, dispositivos IoT (Internet das Coisas), console ou casos de uso de voz (Amazon Alexa ou Google Home).

## Exemplo de JSON {#section_75BFB2537CFF4FBD9B560F59EB32C8DD}

O exemplo a seguir mostra como as respostas JSON podem ser retornadas ao configurar uma atividade por meio do editor baseado em formulário.

1. Crie um design na Biblioteca de projetos ou no fluxo de trabalho baseado em formulário. Se você tentar fazer isso dentro do fluxo de trabalho do Visual Experience Composer (VEC), poderá criar nada além de um design de HTML, que está envolvido com uma `<div>` para fins de rastreamento de cliques.
1. Verifique se a opção &quot;HTML Design&quot; está desativada:

   ![](assets/html_design_toggle.png)

1. O código a seguir é um exemplo abaixo do que você pode colar em seu design:

   ```
       #* 
       * "Return a simple list of recommended entity ids"   
       *#
   
       {   
         "notes":{   
         "purpose": "Return a simple list of recommended entity ids",   
         "use-case": "Use this approach if you prefer to do a real-time lookup of entity attribute details (such as inventory, price, rating) from another system (such as a CMS, PIM or ecommerce platform)",   
         "version": "01"   
         },   
         "recommendedItems": {   
           "key": "$key.id",   
           "slot-01": "$entity1.id",   
           "slot-02": "$entity2.id",   
           "slot-03": "$entity3.id",   
           "slot-04": "$entity4.id",   
           "slot-05": "$entity5.id",   
           "slot-06": "$entity6.id",   
           "slot-07": "$entity7.id",   
           "slot-08": "$entity8.id",   
           "slot-09": "$entity9.id",   
           "slot-10": "$entity10.id"   
         }   
       }  
   ```

1. Configurar uma atividade do Recommendations baseada em formulário que use esse design.

   1. Navegue até a página Atividades.
   1. Clique em **[!UICONTROL Criar atividade]**.
   1. Selecionar **[!UICONTROL Recommendations]**.
   1. Em **[!UICONTROL Escolher Experience Composer]**, selecione **[!UICONTROL Formulário]**.

   1. Em localização, digite o texto: &quot;Sample_Recs_Response&quot;
   1. Em **[!UICONTROL Conteúdo padrão]**, clique na seta para baixo e depois clique em **[!UICONTROL Adicionara recomendação]**.
   1. Selecione um tipo de página. Isso determina a filtragem inicial da próxima tela.
   1. Selecione um cartão de Critérios e depois clique em **[!UICONTROL Próximo]**.
   1. Selecione o design que você criou na etapa anterior e clique em **[!UICONTROL Salvar]**.
   1. Complete o processo de configuração.
   1. Clique na seta à direita próximo a **[!UICONTROL Inativo]** e depois selecione **[!UICONTROL Ativar]**.

1. Depois que sua atividade estiver configurada e ativada, você pode configurar uma solicitação de amostra para recuperar a resposta limpa do JSON.

   A partir do momento que você salvar sua atividade, o Target precisará criar um modelo para suportar a configuração de critérios selecionada. Dependendo de vários fatores, isso pode levar algum tempo. Os resultados aparecem quando o modelo tiver sido criado.

   Por exemplo:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   onde

| Parâmetro | Valor |
|--- |--- |
| `[YOUR_CLIENT_CODE]` | Código do Target do Target (disponível em ../target/products.html # recssetações &gt; Token de API do Recommendations &gt; Código do cliente. |
| `[YOUR_MBOX_NAME]` | O nome que você selecionou na seção &quot;locais&quot; do Recommendations baseado em formulário, neste caso YOUR_CLIENT_CODE. |
| `[ENTITY_ID`] | O `entity.id` de um item em seu catálogo. |
| `[AT_PROPERTY_TOKEN]` | (Opcional) Adicionar se você selecionou uma Propriedade (parte das Permissões da empresa) durante a configuração de sua atividade. |

Depois que seu algoritmo for executado e você obter os resultados, sua resposta deve ser:

![](assets/json_recommendation.png){width=&quot;575px&quot;}

## Dicas e truques adicionais sobre objetos JSON {#section_C305673C68944749969DB239E3221DC2}

Você também pode simplesmente enviar de volta uma lista simples de itens delimitados por vírgula, configurando um design com a seguinte sintaxe:

```
entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

Como alternativa, você pode enviar informações adicionais na resposta. O seguinte arquivo de código é um exemplo mais complexo que retorna muito mais do que as IDs de entidade com seus slots associados (ordem). Este exemplo de Design também retorna detalhes da atividade, detalhes do Perfil do Target (conforme aplicável) e outros `entity.attributes` associados aos itens retornados.

```
    {   
     "adobeRecommendations": {   
      "notes": {   
       "purpose": "Return a list of entity ids with their associated entity.attributes",   
       "use-case": "Use this approach to avoid looking up attribute details after receiving a response from Target",   
       "version": "01"   
      },   
      "recommendedItems": {   
       "slot-01": "$entity1.id",   
       "slot-02": "$entity2.id",   
       "slot-03": "$entity3.id",   
       "slot-04": "$entity4.id",   
       "slot-05": "$entity5.id",   
       "slot-06": "$entity6.id",   
       "slot-07": "$entity7.id",   
       "slot-08": "$entity8.id",   
       "slot-09": "$entity9.id",   
       "slot-10": "$entity10.id"   
      },   
      "activityDetails": {   
       "mbox.name": "email-mbox",   
       "campaign.name": "\${campaign.name}",   
       "campaign.id": "\${campaign.id}",   
       "campaign.recipe.name": "\${campaign.recipe.name}",   
       "campaign.recipe.id": "\${campaign.recipe.id}",   
       "offer.name": "\${offer.name}",   
       "offer.id": "\${offer.id}",   
       "criteria.title": "$criteria.title",   
       "algorithm.name": "$algorithm.name",   
       "algorithm.dayCount": "$algorithm.dayCount"   
      },   
      "visitorProfile": {   
       "profile.favorite-category": "\${profile.favorite-category}",   
       "profile.test": "\${profile.test}",   
       "user.endpoint.lastPurchasedEntity": "\${user.endpoint.lastPurchasedEntity}",   
       "user.endpoint.lastViewedEntity": "\${user.endpoint.lastViewedEntity}",   
       "user.endpoint.mostViewedEntity": "\${user.endpoint.mostViewedEntity}",   
       "user.endpoint.categoryAffinity": "\${user.endpoint.categoryAffinity}",   
       "profile.geolocation.city": "\${profile.geolocation.city}",   
       "profile.geolocation.dma": "\${profile.geolocation.dma}",   
       "profile.geolocation.state": "\${profile.geolocation.state}",   
       "profile.geolocation.country": "\${profile.geolocation.country}",   
       "profile.sessionCount": "\${profile.sessionCount}",   
       "profile.averageDaysBetweenVisits": "\${profile.averageDaysBetweenVisits}",   
       "profile.browserTime": "\${profile.browserTime}",   
       "user.activeActivities": "\${user.activeActivities}",   
       "user.pcId": "\${user.pcId}",   
       "user.isFirstSession": "\${user.isFirstSession}",   
       "user.isNewSession": "\${user.isNewSession}",   
       "user.header": "\${user.header}",   
       "user.parameter": "\${user.parameter}"   
      },   
      "recKey": {   
       "recKeyDetails": {   
        "id": "$key.id",   
        "name": "$key.name",   
        "category": "$key.category",   
        "pageUrl": "$key.pageUrl",   
        "thumbnailUrl": "$key.thumbnailUrl"   
       }   
      },   
      "recDetailedResults": {   
       "recEntity1Details": {   
        "id": "$entity1.id",   
        "name": "$entity1.name",   
        "category": "$entity1.category",   
        "pageUrl": "$entity1.pageUrl",   
        "thumbnailUrl": "$entity1.thumbnailUrl"   
       },   
       "recEntity2Details": {   
        "id": "$entity2.id",   
        "name": "$entity2.name",   
        "category": "$entity2.category",   
        "pageUrl": "$entity2.pageUrl",   
        "thumbnailUrl": "$entity2.thumbnailUrl"   
       },   
       "recEntity3Details": {   
        "id": "$entity3.id",   
        "name": "$entity3.name",   
        "category": "$entity3.category",   
        "pageUrl": "$entity3.pageUrl",   
        "thumbnailUrl": "$entity3.thumbnailUrl"   
       },   
       "recEntity4Details": {   
        "id": "$entity4.id",   
        "name": "$entity4.name",   
        "category": "$entity4.category",   
        "pageUrl": "$entity4.pageUrl",   
        "thumbnailUrl": "$entity4.thumbnailUrl"   
       },   
       "recEntity5Details": {   
        "id": "$entity5.id",   
        "name": "$entity5.name",   
        "category": "$entity5.category",   
        "pageUrl": "$entity5.pageUrl",   
        "thumbnailUrl": "$entity5.thumbnailUrl"   
       },   
       "recEntity6Details": {   
        "id": "$entity6.id",   
        "name": "$entity6.name",   
        "category": "$entity6.category",   
        "pageUrl": "$entity6.pageUrl",   
        "thumbnailUrl": "$entity6.thumbnailUrl"   
       },   
       "recEntity7Details": {   
        "id": "$entity7.id",   
        "name": "$entity7.name",   
        "category": "$entity7.category",   
        "pageUrl": "$entity7.pageUrl",   
        "thumbnailUrl": "$entity7.thumbnailUrl"   
       },   
       "recEntity8Details": {   
        "id": "$entity8.id",   
        "name": "$entity8.name",   
        "category": "$entity8.category",   
        "pageUrl": "$entity8.pageUrl",   
        "thumbnailUrl": "$entity8.thumbnailUrl"   
       },   
       "recEntity9Details": {   
        "id": "$entity9.id",   
        "name": "$entity9.name",   
        "category": "$entity9.category",   
        "pageUrl": "$entity9.pageUrl",   
        "thumbnailUrl": "$entity9.thumbnailUrl"   
       },   
       "recEntity10Details": {   
        "id": "$entity10.id",   
        "name": "$entity10.name",   
        "category": "$entity10.category",   
        "pageUrl": "$entity10.pageUrl",   
        "thumbnailUrl": "$entity10.thumbnailUrl"   
       }   
      }   
     }   
    }  
```

