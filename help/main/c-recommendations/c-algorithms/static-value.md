---
keywords: regras de inclusão;critérios de inclusão;recomendações;promoção;promoções;filtragem dinâmica;estático;filtro estático
description: Saiba como inserir manualmente um ou mais valores estáticos para filtrar usando regras de inclusão no Adobe [!DNL Target] Recommendations.
title: Filtro estático
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
TQID: 'https://experienceleague.adobe.com/-HTJO4YFi0-isyA-5LbVUaEPu7YX1WFgPy-OexMSXFY'
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
source-wordcount: '184'
ht-degree: 2%
---
# Filtro estático {#static-filter}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como filtrar recomendações inserindo manualmente um ou mais valores estáticos nas regras de inclusão em [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

**[!UICONTROL Filtro Estático]** limita os itens em uma recomendação aos itens que correspondem a valores estáticos inseridos manualmente. É possível criar qualquer número de regras de inclusão. As regras de inclusão são unidas com um operador AND, portanto, todas as regras devem ser atendidas para que um item seja incluído em uma recomendação. Para obter informações gerais sobre regras de inclusão, consulte [Usar regras de inclusão dinâmicas e estáticas](/help/main/c-recommendations/c-algorithms/use-dynamic-and-static-inclusion-rules.md).

## Conteúdo recomendado classificado como G ou PG

Para recomendar apenas conteúdo com uma classificação de MPA (Motion Picture Association) de &quot;G&quot; ou &quot;PG&quot; (excluir conteúdo &quot;R&quot; e &quot;NC17&quot;), crie uma regra de filtragem com o operador &quot;movie-rating equals any of&quot; e insira os valores &quot;g-rating&quot; e &quot;pg-rating&quot;.
