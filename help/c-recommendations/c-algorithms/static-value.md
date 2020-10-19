---
keywords: inclusion rules;inclusion criteria;recommendations;promotion;promotions;dynamic filtering;static;static filter
description: Insira manualmente um ou mais valores estáticos para filtrar usando regras de inclusão no Adobe Target Recommendations.
title: Filtrar por valores estáticos nas regras de inclusão no Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: c814215476ef6e40f4f175fe3f9dbb2c26b966eb
workflow-type: tm+mt
source-wordcount: '160'
ht-degree: 73%

---


# ![Filtro estático PREMIUM](/help/assets/premium.png)

Insira manualmente um ou mais valores estáticos para filtrar usando as regras de inclusão no [!DNL Adobe Target][!DNL Recommendations].

Por exemplo, apenas recomende um conteúdo com uma classificação MPAA de &quot;G&quot; ou &quot;PG&quot;.

>[!NOTE]
>
>Se você estiver familiarizado com a configuração das regras de inclusão antes do Target versão 17.6.1 (junho de 2017), perceberá que algumas opções e operadores foram alterados. Somente os operadores aplicáveis à opção selecionada são exibidos e alguns operadores foram renomeados (&quot;matches&quot; agora é &quot;equals&quot;) para ficarem mais consistentes e intuitivos. Todas as regras de exclusão existentes criadas antes desta versão foram migradas automaticamente para a nova estrutura. Nenhuma reestruturação é necessária da sua parte.

Você pode criar a quantidade de regras de inclusão necessária. As regras de inclusão são unidas por um operador E. Todas as regras devem ser cumpridas para incluir um item em uma recomendação.