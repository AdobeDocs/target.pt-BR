---
keywords: recomendações;atividade de recomendações;critérios;algoritmo;chave de recomendação;chave personalizada;vertical do setor;varejo;comércio eletrônico;geração de clientes potenciais;b2b;serviços financeiros;mídia;publicação
description: Saiba como usar os critérios no Adobe [!DNL Target] [!DNL Recommendations].
title: Como faço para usar os critérios no [!DNL Target] Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: a6e4c857-f991-4293-9d33-8d7c2ca5dade
TQID: 'https://experienceleague.adobe.com/Wo7I3piBQ7zwYF7kqRphDeWjcBCpyvIvTkwKK0t0f9U'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7c7de77-382f-4f48-8b36-61a170f06d3d
    internal-label: Integrations
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
    internal-label: Administration
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '743'
ht-degree: 5%
---
# Introdução ao [!UICONTROL Critério] {#get-started-criteria}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como os critérios funcionam em [!DNL Adobe Target Recommendations] e quais opções de chave de recomendação, vertical do setor e tipo de algoritmo estão disponíveis.

>[!ENDSHADEBOX]

**[!UICONTROL Critérios]** em [!DNL Adobe Target] [!DNL Recommendations] são regras que determinam quais produtos ou conteúdo recomendar com base em um conjunto predeterminado de comportamentos do visitante. Os critérios podem ser baseados em tendências populares, nos comportamentos atuais e passados de um visitante ou em produtos e conteúdo semelhantes. Vários critérios podem ser adicionados a uma atividade para testar vários tipos de recomendações entre si.

O vertical do setor e o tipo de algoritmo selecionados determinam as opções que estão disponíveis quando os critérios são criados.

## Vertical do setor {#section_936BCFCF234C49A2BEC1C38AAC2D71AF}

Quando os critérios são criados, um negócio vertical é selecionado com base nas metas da atividade do recommendations.

| Vertical do setor | Meta |
|--- |--- |
| **[!UICONTROL Varejo/Comércio eletrônico]** | Conversão resultando em compra |
| **[!UICONTROL Geração de lead/B2B/Serviços financeiros]** | Conversão sem compra |
| **[!UICONTROL Mídia/Publicação]** | Engajamento |

Outras opções de critério mudam com base no vertical do setor selecionado. O negócio vertical padrão pode ser definido na página **[!UICONTROL Administração]** > **[!UICONTROL Recomendações]** ou o negócio vertical pode ser especificado para cada critério.

## Tipo de algoritmo {#section_885B3BB1B43048A88A8926F6B76FC482}

O tipo de algoritmo selecionado determina os algoritmos disponíveis. A tabela a seguir explica os tipos de algoritmo e os algoritmos que os acompanham.

| Tipo de algoritmo | Quando usar | Algoritmos disponíveis |
| --- | --- | --- |
| **[!UICONTROL Baseado Em Carrinho]** | Faça recomendações com base no conteúdo do carrinho do usuário. | <ul><li>**[!UICONTROL Pessoas que os visualizaram, também visualizaram]**</li><li>**[!UICONTROL Pessoas Que Os Visualizaram, Também Compraram]**</li><li>**[!UICONTROL Pessoas que Compraram Estes, Também Compraram]**</li></ul>Para obter mais informações, consulte [Baseado em carrinho](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md#cart-based) em *Basear a recomendação em uma chave de recomendação*. |
| **[!UICONTROL Com Base Em Popularidade]** | Faça recomendações com base na popularidade geral de um item em todo o site ou na popularidade de itens dentro da categoria, marca, gênero e assim por diante favoritas ou mais visualizadas do usuário. | <ul><li>**[!UICONTROL Mais visualizados em todo o site]**</li><li>**[!UICONTROL Mais Visualizados por Categoria]**</li><li>**[!UICONTROL Mais Visualizados pelo Atributo de Item]**</li><li>**[!UICONTROL Mais visualizados por atributo de perfil]**</li><li>**[!UICONTROL Mais vendidos em todo o site]**</li><li>**[!UICONTROL Mais vendidos por categoria]**</li><li>**[!UICONTROL Mais vendidos por atributo de item]**</li><li>**[!UICONTROL Mais vendidos por atributo de perfil]**</li><li>**[!UICONTROL Métrica Top by Analytics]**</li></ul> |
| **[!UICONTROL Baseado em Item]** | Fazer recomendações com base em itens semelhantes a um item que o usuário está visualizando atualmente ou que visualizou recentemente. | <ul><li>**[!UICONTROL Pessoas Que Visualizaram Isto, Visualizaram Aquilo]**</li><li>**[!UICONTROL Pessoas que Visualizaram Isto, Compraram Aquilo]**</li><li>**[!UICONTROL Pessoas que Compraram Isto, Compraram Aquilo]**</li><li>**[!UICONTROL Itens com Atributos Semelhantes]**</li></ul> |
| **[!UICONTROL Baseado em Usuário]** | Faça recomendações com base no comportamento do usuário. | <ul><li>**[!UICONTROL Itens visualizados recentemente]**</li><li>**[!UICONTROL Recomendado para você]**</li></ul> |
| **[!UICONTROL Critérios personalizados]** | Fazer recomendações com base em um arquivo personalizado carregado. | <ul><li>Algoritmo personalizado</li></ul> |

Para obter mais informações sobre cada algoritmo, consulte [Basear a recomendação em uma chave de recomendação](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md).

## Usar uma chave de recomendação personalizada {#custom-key}

As recomendações também podem ser baseadas no valor de um atributo de perfil personalizado. Por exemplo, os filmes recomendados podem ser exibidos com base no filme que um usuário adicionou mais recentemente à fila.

1. Clique em **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]**.

1. Clique em **[!UICONTROL Criar Critério]** > **[!UICONTROL Criar Critério]**.

   ![Página de Critérios com o menu Criar critérios aberto, mostrando Criar critérios e Criar sequência de critérios](../assets/criteria_1.png)

1. Preencha as informações na [seção Informações Básicas](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#info).

1. Na seção [Algoritmo recomendado](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#rec-algo), selecione **[!UICONTROL Baseado em Item]** na lista **[!UICONTROL Tipo de Algoritmo]**.

1. Selecione **[!UICONTROL Pessoas que assistiram isto, assistiram aquilo]** na lista **[!UICONTROL Algoritmo]**.

1. Selecione o atributo de perfil personalizado na lista **[!UICONTROL Chave de recomendação]** (por exemplo, **[!UICONTROL Último programa adicionado à Lista de favoritos]**).

   >[!NOTE]
   >
   >Parâmetros de perfil personalizados podem ser passados para [!DNL Target] por meio de JavaScript, API ou integrações. Para obter mais informações sobre atributos de perfil personalizados, consulte [Perfis de visitantes](/help/main/c-target/c-visitor-profile/visitor-profile.md).

   ![Caixa de diálogo Criar Critérios mostrando a seção Algoritmo de Recomendações com as listas Tipo de Algoritmo, Algoritmo e Chave de Recomendação](../assets/criteria_2.png)

## Exibir informações de critérios {#section_7162DE58E4594FD688A4D7FDB829FD8B}

Os detalhes do critério mostram como um critério é configurado e quais atividades o usam.

1. Clique em **[!UICONTROL Recomendações]** > **[!UICONTROL Critérios]** para exibir a lista de critérios.

1. Clique nos critérios desejados na coluna **[!UICONTROL Nome]**.

1. Exiba informações gerais sobre os critérios selecionados nas seções **[!UICONTROL Atributos]** e Detalhes, incluindo seu **[!UICONTROL Nome]**, **[!UICONTROL Descrição]**, **[!UICONTROL Vertical do setor]**, **[!UICONTROL Tipos de Página]**, **[!UICONTROL Chave de Recomendação]**, **[!UICONTROL Lógica de Recomendação]**, **[!UICONTROL ID do Algoritmo]** e informações da Última Modificação (data e quem modificou o algoritmo).

1. Exiba a lista de atividades que fazem referência aos critérios selecionados na seção **[!UICONTROL Uso]**.

   >[!NOTE]
   >
   >O recurso **[!UICONTROL Uso do Algoritmo]** tem suporte no momento apenas para atividades [!DNL Recommendations]. Este recurso não tem suporte atualmente para atividades de **[!UICONTROL Teste A/B]**, **[!UICONTROL Alocação automática]**, **[!UICONTROL Direcionamento automático]** e **[!UICONTROL Direcionamento de experiência]** (XT) que incluem [recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

   ![Detalhes do critério com as seções Atributos e Detalhes e a seção Uso destacada](../assets/criteria_3.png)
