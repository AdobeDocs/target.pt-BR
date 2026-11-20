---
keywords: produto, coleções
description: Saiba mais sobre entidades no Adobe [!DNL Target] Recommendations. As entidades se referem aos itens que você deseja recomendar usando o [!DNL Target], como artigos, filmes ou produtos.
title: Como usar Entidades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: ffe23eea-b914-4c86-ad54-c63c1cc1c0d7
TQID: 'https://experienceleague.adobe.com/zfISb59XJ5qrD1-FA0syglPPswIL8cA0N0pBpY4tgIE'
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
source-git-commit: 5ed511322cc9f04c349471f8ad84a17526d4925f
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%
---
# Introdução a entidades {#get-started-entities}

>[!BEGINSHADEBOX]

**Nesta página:** saiba quais entidades estão em [!DNL Adobe Target Recommendations] e onde gerenciá-las.

>[!ENDSHADEBOX]

Entidades são os itens que [!DNL Recommendations] pode recomendar. Uma entidade pode ser um produto, um conteúdo (como um artigo, apresentação de slides, imagem, filme ou programa de TV), uma lista de empregos, um restaurante e assim por diante.

[!DNL Recommendations] exibe itens de suas coleções de acordo com os critérios que você configurou.

## Como as entidades atingem o Recommendations

As informações sobre suas entidades podem ser passadas para [!DNL Recommendations] de várias maneiras, incluindo:

* Com [atributos de entidade](/help/main/c-recommendations/c-products/entity-attributes.md) enviados de suas páginas, usando uma mbox ou `targetPageParams`.
* Com [feeds](/help/main/c-recommendations/c-products/feeds.md), que podem usar arquivos CSV, o formato de feed [!DNL Google Product Search] ou as classificações de produto [!DNL Adobe Analytics].
* Com a API de entrega.

Se [!DNL Target] coletar dados para um item de um feed e de uma mbox, os dados mais recentes serão usados.

As entidades e os valores de atributos de entidade carregados expiram após 61 dias. Envie cada item novamente pelo menos uma vez a cada 60 dias. Caso contrário, [!DNL Target] considera o item não mais relevante e o remove do catálogo.

## Gerenciar suas entidades

Use as seguintes páginas para trabalhar com suas entidades:

* [Atributos de entidade](/help/main/c-recommendations/c-products/entity-attributes.md) e [Atributos de entidade personalizados](/help/main/c-recommendations/c-products/custom-entity-attributes.md): defina as informações sobre o produto ou conteúdo que você passar para [!DNL Recommendations].
* [Feeds](/help/main/c-recommendations/c-products/feeds.md): obtenha informações de entidade ou conteúdo em suas recomendações.
* [Pesquisa no catálogo](/help/main/c-recommendations/c-products/catalog-search.md): localize os itens no catálogo.
* [Coleções](/help/main/c-recommendations/c-products/collections.md): configure suas coleções. Uma coleção é selecionada para cada experiência quando você cria uma atividade [!DNL Recommendations].
* [Exclusões](/help/main/c-recommendations/c-products/exclusions.md): impede que determinados itens sejam exibidos em suas recomendações. As exclusões se aplicam a todas as atividades na conta.
