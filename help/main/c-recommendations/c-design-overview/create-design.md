---
keywords: design de recomendações, criar design, copiar design
description: Saiba como criar um design do [!DNL Target Recommendations] usando um design padrão ou criando um design personalizado para melhor se ajustar ao layout de uma página.
title: Criar um design
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 0f10ee9d-7210-4e02-9342-e4f85cf46e8c
TQID: 'https://experienceleague.adobe.com/GLWcKaQGl6TmL9i7LYUiYepg6SkAjBtL-78-zlaWCTk'
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
source-git-commit: d5030abcda38bbc6d33b88ce3bb5d64f69e4e492
workflow-type: tm+mt
source-wordcount: '912'
ht-degree: 11%
---
# Criar um design {#create-design}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como criar, editar, copiar e excluir designs no [!DNL Adobe Target Recommendations] e como retornar recomendações como JSON.

>[!ENDSHADEBOX]

Um design define como as recomendações são exibidas em uma página. Um design pode ser baseado em um design padrão ou criado como um design personalizado. A tela **[!UICONTROL Recomendações]** > **[!UICONTROL Designs]** exibe os cartões de design padrão e os designs criados na conta.

* Um design padrão não pode ser editado ou excluído.
* Um design personalizado pode ser editado, copiado ou excluído.
* Para criar um design com base em um design padrão, primeiro copie o design e, em seguida, edite a cópia.

Um design pode ser criado durante o processo de criação da atividade no **[!UICONTROL Visual Experience Composer]** (VEC) ou na biblioteca de design fora da criação da atividade. As etapas a seguir pressupõem que o design seja criado a partir da biblioteca, mas as etapas são semelhantes.

## Criar um design a partir da biblioteca {#steps}

1. Clique em **[!UICONTROL Recomendações]** > **[!UICONTROL Designs]** para exibir a biblioteca **[!UICONTROL Designs]**.

1. Inicie o design de uma das seguintes maneiras:

   * Para basear o design em um design padrão ou em um design existente, clique no ícone Mais Ações ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) desse design e clique em **[!UICONTROL Copiar]**. A caixa de diálogo **[!UICONTROL Criar Design]** é exibida. A cópia editada torna-se um novo design personalizado.
   * Para criar um design personalizado do zero, clique em **[!UICONTROL Criar Design]**.

     ![Designs de biblioteca com o botão Criar design realçado](../assets/design_1.png)

1. Digite um **[!UICONTROL Nome]** e selecione uma imagem de visualização opcional a ser exibida no cartão de design.

   Quando um design padrão é usado, o nome do design seguido de &quot;Cópia&quot; aparece no campo **[!UICONTROL Nome do Conteúdo]**. O nome pode ser editado.

1. (Condicional) Edite o design **[!UICONTROL Code]**, conforme desejado.

   Os designs de recomendação usam o idioma de design da Velocity de fonte aberta. Para obter informações sobre o Velocity, consulte [https://velocity.apache.org](https://velocity.apache.org) e [Personalizar um design usando o Velocity](/help/main/c-recommendations/c-design-overview/customizing-a-template.md).

   Um design pode ser HTML ou não-HTML. Por padrão, os designs do HTML são envolvidos com uma tag `<div>` para permitir o rastreamento de cliques em um ambiente da Web. Designs não-HTML são para ambientes que não sejam da Web onde click-tracking não é possível. Deslize o botão **[!UICONTROL HTML Design]** para a posição &quot;desligado&quot; para usar código que não seja HTML.

   >[!NOTE]
   >
   >A quantidade máxima de entidades que podem ser referenciadas em um design, seja em código rígido ou em loops, é de 99.

1. Clique em **[!UICONTROL Criar]**.

1. Clique no ícone Mais Ações ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) do design para editar, copiar ou excluir e clique na opção apropriada: **[!UICONTROL Editar]**, **[!UICONTROL Copiar]** ou **[!UICONTROL Excluir]**.

   ![Designa a biblioteca com o menu Mais Ações aberto, mostrando Editar, Copiar e Excluir](../assets/design_2.png)

Designs estão disponíveis em toda a conta. O uso entre contas deve ser considerado antes que um design seja excluído. Os designs excluídos não podem ser recuperados.

## Exemplo de JSON {#json-example}

O exemplo a seguir mostra como as respostas JSON podem ser retornadas quando uma atividade é configurada com o [editor baseado em formulário](/help/main/c-experiences/form-experience-composer.md).

1. Crie um design dentro da **[!UICONTROL Biblioteca de design]** ou dentro do fluxo de trabalho baseado em formulário. Um design criado no fluxo de trabalho do **[!UICONTROL Visual Experience Composer]** (VEC) só pode ser um design de HTML, que é colocado em um `<div>` para fins de rastreamento de cliques.

1. Verifique se a opção **[!UICONTROL HTML Design]** está desativada:

   ![Alternância do HTML Design na posição desligado](/help/main/c-recommendations/c-design-overview/assets/html_design_toggle.png)

1. Cole o código como o exemplo a seguir no design:

   +++ Código de design de exemplo que retorna uma lista de IDs de entidade

   ```javascript
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

   +++

1. Configure uma atividade [!DNL Recommendations] baseada em formulário que use este design.

   +++ Saiba como configurar uma atividade [!DNL Recommendations] baseada em formulário 

   1. Navegue até a página **[!UICONTROL Atividades]**.
   1. Clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Recomendações]**.
   1. Em **[!UICONTROL Escolher Experience Composer]**, selecione **[!UICONTROL Formulário]** e clique em **[!UICONTROL Avançar]**.
   1. Em localização, digite o texto &quot;Sample_Recs_Response&quot;.
   1. Em **[!UICONTROL Conteúdo padrão]**, clique na seta para baixo e depois clique em **[!UICONTROL Adicionara recomendação]**.
   1. Selecione um tipo de página. Isso determina a filtragem inicial da próxima tela.
   1. Selecione um cartão de Critérios e depois clique em **[!UICONTROL Próximo]**.
   1. Selecione o design criado na etapa anterior e clique em **[!UICONTROL Avançar]**.
   1. Complete o processo de configuração.
   1. Clique na seta à direita próximo a **[!UICONTROL Inativo]** e depois selecione **[!UICONTROL Ativar]**.

   +++

1. Depois que a atividade for configurada e ativada, uma solicitação de amostra pode ser configurada para obter a resposta JSON limpa.

   A partir do momento em que a atividade é salva, [!DNL Target] precisa criar um modelo para suportar a configuração dos critérios selecionados. Dependendo de vários fatores, esse processo pode levar algum tempo. Os resultados aparecem depois que o modelo é criado.

   Por exemplo:

   ```
   https://[YOUR_CLIENT_CODE].tt.omtrdc.net/m2/YOUR_CLIENT_CODE/ubox/raw?mbox=[YOUR_MBOX_NAME]&mboxContentType=text/html&mboxXDomain=disabled&entity.id=[ENTITY_ID]&mboxHost=rawbox_sample&at_property=[AT_PROPERTY_TOKEN]&mboxNoRedirect=true&mboxPC=1234-4321&mboxSession=9876-7000
   ```

   onde

   | Parâmetro | Valor |
   |--- |--- |
   | `[YOUR_CLIENT_CODE]` | O código de cliente [!DNL Target] (disponível em /help/target/products.html#recsSettings > Token de API do Recommendations > Código de cliente). |
   | `[YOUR_MBOX_NAME]` | O nome selecionado na seção &quot;locais&quot; da atividade do Recommendations baseada em formulário, neste caso Sample_Recs_Response. |
   | `[ENTITY_ID]` | O `entity.id` de um item no catálogo. |
   | `[AT_PROPERTY_TOKEN]` | (Opcional) Adicionado quando uma Propriedade (parte das Permissões empresariais) era selecionada durante a configuração da atividade. |

Depois que o algoritmo for executado e os resultados estiverem disponíveis, a resposta será semelhante ao seguinte:

![Resposta JSON com os itens recomendados](/help/main/c-recommendations/c-design-overview/assets/json_recommendation.png){width="575px"}

## Dicas adicionais de objetos JSON {#json-tips}

Uma lista de itens delimitada por vírgulas simples também pode ser enviada de volta configurando um design com a seguinte sintaxe:

```
$entity1.id, $entity2.id, $entity3.id, $entity4.id, $entity5.id, 
```

Informações adicionais também podem ser enviadas na resposta. O código a seguir é um exemplo mais complexo que retorna muito mais do que as IDs de entidade com seus slots associados (ordem). Este exemplo de design também retorna detalhes da atividade, detalhes do **[!UICONTROL Perfil de Destino]** (conforme aplicável) e outros `entity.attributes` associados aos itens retornados.

+++ Exemplo de código de design que retorna detalhes de atividade, perfil e entidade

```javascript
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

+++

