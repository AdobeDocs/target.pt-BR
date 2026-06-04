---
keywords: recomendações;atividade de recomendações;critérios;algoritmo;chave de recomendação;chave personalizada;vertical do setor;varejo;comércio eletrônico;geração de clientes potenciais;b2b;serviços financeiros;mídia;publicação
description: Saiba como usar os critérios no Adobe [!DNL Target] [!DNL Recommendations].
title: Como faço para usar os critérios no  [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
TQID: https://experienceleague.adobe.com/Wo7I3piBQ7zwYF7kqRphDeWjcBCpyvIvTkwKK0t0f9U
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 657
ht-degree: 7%

---

# [!UICONTROL Critérios]

[!UICONTROL Critérios] em [!DNL Adobe Target] [!DNL Recommendations] são regras que determinam quais produtos ou conteúdo recomendar com base em um conjunto predeterminado de comportamentos do visitante. Os critérios podem ser baseados em tendências populares, nos comportamentos atuais e passados de um visitante ou em produtos e conteúdo semelhantes. Você pode comparar vários tipos de recomendação por meio da adição de vários critérios.

As seções a seguir explicam mais sobre as chaves de critérios e a lógica de recomendação que você pode usar para cada chave. Clique nos links para obter informações mais detalhadas.

## Vertical do setor {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Ao criar um critério, você seleciona um negócio vertical com base nas metas de sua atividade de recomendações.

| Vertical do setor | Meta |
|--- |--- |
| [!UICONTROL Varejo/Comércio eletrônico] | Conversão resultando em compra |
| [!UICONTROL Geração de lead/B2B/Serviços financeiros] | Conversão sem compra |
| [!UICONTROL Mídia/Publicação] | Engajamento |

Outras opções de critério mudam de acordo com o negócio vertical que você selecionar. Você pode definir seu negócio vertical padrão na página **[!UICONTROL Administração] > [!UICONTROL Recomendações]** ou pode especificar o setor vertical para cada critério.

## Tipo de algoritmo {#section_885B3BB1B43048A88A8926F6B76FC482}

O tipo de algoritmo selecionado determina os algoritmos disponíveis.

A tabela a seguir explica os vários tipos de algoritmos e os algoritmos que os acompanham.

| Tipo de algoritmo | Quando usar | Algoritmos disponíveis |
| --- | --- | --- |
| [!UICONTROL Baseado Em Carrinho] | Faça recomendações com base no conteúdo do carrinho do usuário. | <ul><li>[!UICONTROL Pessoas que os visualizaram, também visualizaram]</li><li>[!UICONTROL Pessoas Que Os Visualizaram, Também Compraram]</li><li>[!UICONTROL Pessoas que Compraram Estes, Também Compraram]</li></ul>Para obter mais informações, consulte [Baseado em carrinho](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) em *Basear a recomendação em uma chave de recomendação*. |
| [!UICONTROL Com Base Em Popularidade] | Faça recomendações com base na popularidade geral de um item em todo o site ou na popularidade de itens na categoria, marca, gênero e assim por diante favoritas ou mais visualizadas de um usuário. | <ul><li>[!UICONTROL Mais visualizados em todo o site]</li><li>[!UICONTROL Mais Visualizados por Categoria]</li><li>[!UICONTROL Mais Visualizados pelo Atributo de Item]</li><li>[!UICONTROL Mais vendidos em todo o site]</li><li>[!UICONTROL Mais vendidos por categoria]</li><li>[!UICONTROL Mais vendidos por atributo de item]</li><li>[!UICONTROL Métrica Top by Analytics]</li></ul> |
| [!UICONTROL Baseado em Item] | Fazer recomendações com base na localização de itens semelhantes a um item que o usuário está visualizando atualmente ou que visualizou recentemente. | <ul><li>[!UICONTROL Pessoas Que Visualizaram Isto, Visualizaram Aquilo]</li><li>[!UICONTROL Pessoas que Visualizaram Isto, Compraram Aquilo]</li><li>[!UICONTROL Pessoas que Compraram Isto, Compraram Aquilo]</li><li>[!UICONTROL Itens com Atributos Semelhantes]</li></ul> |
| [!UICONTROL Baseado em Usuário] | Faça recomendações com base no comportamento do usuário. | <ul><li>[!UICONTROL Itens visualizados recentemente]</li><li>[!UICONTROL Recomendado para você]</li></ul> |
| [!UICONTROL Critérios personalizados] | Fazer recomendações com base em um arquivo personalizado que você carregou. | <ul><li>Algoritmo personalizado</li></ul> |

Para obter mais informações sobre cada algoritmo, consulte [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Uso de uma chave de recomendação personalizada {#custom-key}

Você também pode basear as recomendações no valor de um atributo de perfil personalizado.

>[!NOTE]
>
>Parâmetros de perfil personalizados podem ser passados para [!DNL Target] por meio de JavaScript, API ou integrações. Para obter mais informações sobre atributos de perfil personalizados, consulte [Perfis de visitantes](/help/main/c-target/c-visitor-profile/visitor-profile.md).

Por exemplo, suponha que você deseja exibir filmes recomendados com base no filme adicionado recentemente por um usuário à fila.

1. Clique em **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar Critério]** > **[!UICONTROL Criar Critério]**.

1. Preencha as informações na [seção Informações Básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Na seção [Algoritmo recomendado](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo), selecione **[!UICONTROL Baseado em Item]** na lista **[!UICONTROL Tipo de Algoritmo]**.

1. Selecione **[!UICONTROL Pessoas que assistiram isto, assistiram aquilo]** na lista **[!UICONTROL Algoritmo]**.

1. Selecione o atributo de perfil personalizado na lista **[!UICONTROL Chave de recomendação]** (por exemplo, [!UICONTROL Último programa adicionado à Lista de favoritos]).

## Exibição de informações de critérios {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Você pode exibir os detalhes dos critérios clicando nos critérios desejados na coluna [!UICONTROL Nome].

As seções **[!UICONTROL Atributos]** e Detalhes permitem exibir informações gerais sobre os critérios selecionados, incluindo seu [!UICONTROL Nome], [!UICONTROL Descrição], [!UICONTROL Vertical do setor], [!UICONTROL Tipos de página], [!UICONTROL Chave de recomendação], [!UICONTROL Lógica de recomendação], [!UICONTROL ID do algoritmo] e informações da Última Modificação (data e quem modificou o algoritmo).

A seção **[!UICONTROL Uso]** permite exibir uma lista de atividades que fazem referência aos critérios selecionados.

>[!NOTE]
>
>O recurso [!UICONTROL Uso do Algoritmo] tem suporte no momento apenas para atividades [!DNL Recommendations]. Este recurso não tem suporte atualmente para atividades de [!UICONTROL Teste A/B], [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Direcionamento de experiência] (XT) que incluem [recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).
