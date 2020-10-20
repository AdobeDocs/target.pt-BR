---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Insira manualmente um ou mais valores estáticos para filtrar usando regras de inclusão no Adobe Target Recommendations.
title: Filtrar por valores estáticos nas regras de inclusão no Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: 60b71c426b61bb16a23976da9a03926f8e73cf6c
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 49%

---


# ![Filtro estático PREMIUM](/help/assets/premium.png)

Insira manualmente um ou mais valores estáticos para filtrar usando as regras de inclusão no [!DNL Adobe Target][!DNL Recommendations].

Por exemplo, recomendamos apenas o conteúdo com uma classificação MPA (Motion Picture Association) de &quot;G&quot; ou &quot;PG&quot;.

>[!NOTE]
>
>Se você estiver familiarizado com a configuração das regras de inclusão antes do Target versão 17.6.1 (junho de 2017), perceberá que algumas opções e operadores foram alterados. Somente os operadores aplicáveis à opção selecionada são exibidos e alguns operadores foram renomeados (&quot;matches&quot; agora é &quot;equals&quot;) para ficarem mais consistentes e intuitivos. Todas as regras de exclusão existentes criadas antes desta versão foram migradas automaticamente para a nova estrutura. Nenhuma reestruturação é necessária da sua parte.

## Conteúdo recomendado com classificação G ou PG

Para criar uma regra de inclusão com valores estáticos para recomendar conteúdo com uma classificação MPA somente &quot;G&quot; ou &quot;PG&quot; (excluir conteúdo &quot;R&quot; e &quot;NC17&quot;), você pode criar duas regras de filtragem: &quot;A classificação de filme é igual a g-rating&quot; e &quot;a classificação de filme igual a pg-rating&quot;, conforme mostrado abaixo.

![exemplo de classificação de filme](/help/c-recommendations/c-algorithms/assets/movies.png)

Você pode criar a quantidade de regras de inclusão necessária. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.