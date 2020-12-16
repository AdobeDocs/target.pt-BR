---
keywords: recommendation;backup;back up
description: Se você usar o recurso de recomendação de backup no Adobe Target, qualquer recomendação que não tenha itens recomendados suficientes não exibirá o conteúdo padrão. Em vez disso, as recomendações exibem os resultados do algoritmo de backup.
title: Usar uma recomendação de backup no Adobe Target Recommendations
feature: criteria
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 83%

---


# ![PREMIUM](/help/assets/premium.png) Use uma recomendação de backup{#use-a-backup-recommendation}

Se você usar o recurso de recomendação de backup no Adobe Target, qualquer recomendação que não tenha itens recomendados suficientes não exibirá o conteúdo padrão. Em vez disso, as recomendações exibem os resultados do algoritmo de backup.

Se você não usar a recomendação de backup, se uma recomendação não tiver itens suficientes para preencher a tela, o sistema exibirá o conteúdo padrão para o usuário.

>[!NOTE]
>
>Informações adicionais estão incluídas na seção [Conteúdo do tópico Criar critérios](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content), incluindo uma matriz que explica os resultados que você observará ao usar as opções [!UICONTROL Renderização parcial de design] e [!UICONTROL Mostrar Recommendations] de backup juntas ou separadamente.

O recurso de recomendação de backup sempre usa os principais itens visualizados no site para preencher as vagas restantes após os dados do algoritmo serem usados. Por exemplo, seu modelo está configurado para mostrar cinco itens recomendados e você está usando o algoritmo de *Afinidades de compra*. No entanto, você só tem dados suficientes para preencher duas das cinco vagas, de modo que o recurso de recomendação de backup preenche as outras três vagas com os itens mais visualizados.

As recomendações de backup são escolhidas de maneira aleatória dentre os 500 produtos mais exibidos em todo o site. O período para recomendações de backup é de uma semana.

Os 500 resultados mais visualizados são ordenados sequencialmente e depois divididos em compartimentos de 20. Os compartimentos são exibidos em ordem, mas os resultados dentro de cada compartimento são randomizados e devolvidos à página. Se os usuários atualizarem a página, elas serão apresentadas com novos resultados aleatórios. Se o conjunto de resultados da união da coleção e das regras de filtragem for menor que 20, ele selecionará aleatoriamente a partir da coleção.

Esse processo de divisão de compartimentos significa que as recomendações de backup são exibidas na seguinte ordem:

1. Mostre os 20 itens mais visualizados, randomizados, em seguida
1. Mostre os próximos 20 itens mais visualizados, randomizados, em seguida
1. Mostre os próximos 20 itens mais visualizados, randomizados,
1. E, assim por diante.

Sem o intervalo de recomendações de backup, seria possível mostrar o 499º item mais visualizado, seguido pelo 200º item mais visualizado, seguido pelo 380º item mais visualizado, e assim por diante. O processo de divisão garante que os itens mais visualizados sejam recomendados primeiro.

>[!NOTE]
>
>Se você agrupar seus itens em catálogos, as recomendações de backup geradas para cada algoritmo em cada recomendação também usarão o catálogo, portanto, somente os itens no catálogo serão incluídos na recomendação de backup.

Qualquer item que for excluído pela regra de exclusão global não serve como uma recomendação de backup.

As recomendações de backup são ativadas por padrão e preenchem as vagas extras em um modelo com uma seleção aleatória dos itens mais populares no site.

As duplicatas são removidas dos lotes de recomendações.

O uso das recomendações de backup normalmente faz parte da discussão com a equipe de implementação durante a configuração inicial do programa. Se quiser mudar a configuração da recomendação de backup após a implementação, entre em contato com seu gerente de conta.

Para Habilitar a renderização de design parcial (consulte  [Configurações de conteúdo](/help/c-recommendations/c-algorithms/create-new-algorithm.md#content)) não estiverem ativadas e o modelo não for exibido, então a recomendação de backup ou o conteúdo padrão serão exibidos.
