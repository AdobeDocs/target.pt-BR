---
keywords: regras de inclusão, critérios de inclusão, recomendações, promoção, promoções, filtragem dinâmica, estático, filtro estático
description: Saiba como inserir manualmente um ou mais valores estáticos para filtrar usando regras de inclusão no Adobe [!DNL Target] Recommendations.
title: Como Filtrar Por Valores Estáticos Em Atividades Do Recommendations?
feature: Recommendations
exl-id: 217e19bf-521f-4913-9b41-099c9af8b393
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 46%

---

# ![](/help/assets/premium.png) PREMIUMStatic Filter

Insira manualmente um ou mais valores estáticos para filtrar usando regras de inclusão em [!DNL Adobe Target] [!DNL Recommendations].

Por exemplo, recomende somente o conteúdo com uma classificação MPA (Motion Picture Association) de &quot;G&quot; ou &quot;PG&quot;.

Você pode criar a quantidade de regras de inclusão necessária. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.

>[!NOTE]
>
>Se você estiver familiarizado com a configuração das regras de inclusão antes do Target versão 17.6.1 (junho de 2017), perceberá que algumas opções e operadores foram alterados. Somente os operadores aplicáveis à opção selecionada são exibidos e alguns operadores foram renomeados (&quot;matches&quot; agora é &quot;equals&quot;) para ficarem mais consistentes e intuitivos. Todas as regras de exclusão existentes criadas antes desta versão foram migradas automaticamente para a nova estrutura. Nenhuma reestruturação é necessária da sua parte.

## Conteúdo recomendado com classificação G ou PG

Para criar uma regra de inclusão com valores estáticos para recomendar conteúdo com uma classificação MPA de &quot;G&quot; ou &quot;PG&quot; somente (excluir conteúdo &quot;R&quot; e &quot;NC17&quot;), você pode criar as seguintes regras de filtragem &quot;classificação de filme igual a g-rating&quot; e &quot;classificação de filme igual a pg-rating&quot;, conforme mostrado abaixo.

![exemplo de classificação de filme](/help/c-recommendations/c-algorithms/assets/movies.png)
