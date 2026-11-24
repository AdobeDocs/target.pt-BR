---
keywords: recomendação, backup, fazer o back up
description: Saiba como usar recomendações de backup no Adobe [!DNL Target Recommendations].
title: Usar uma recomendação de backup
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 070aa8ef-5691-4106-b5cf-45eb9f6f334c
TQID: 'https://experienceleague.adobe.com/TziWJoAuEdCqa7uMTpX0O0InnlnjtbPXP-0wzQ-FCM0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: e8a9b6be04169ea3024673babb62085667fe8990
workflow-type: tm+mt
source-wordcount: '497'
ht-degree: 18%
---
# Usar uma recomendação de backup {#backup-recommendations}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como as recomendações de backup preenchem os slots restantes de um design em [!DNL Adobe Target Recommendations].

>[!ENDSHADEBOX]

Quando uma recomendação não tem itens recomendados suficientes para preencher o design, o recurso de recomendação de backup em [!DNL Adobe Target] exibe os resultados do algoritmo de backup em vez do conteúdo padrão. Sem uma recomendação de backup, o sistema exibe o conteúdo padrão para o usuário.

>[!NOTE]
>
>Para obter mais informações, incluindo uma matriz que explica os resultados do uso das opções **[!UICONTROL Renderização de Design Parcial]** e **[!UICONTROL Mostrar Conteúdo de Backup]** juntas ou separadamente, consulte a [seção Conteúdo de Backup dos critérios de Criação](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content).

O recurso de recomendação de backup sempre usa os itens mais visualizados no site para preencher os slots restantes depois que os dados do algoritmo são usados. Por exemplo, um design é configurado para mostrar cinco itens recomendados, mas o algoritmo tem dados suficientes para preencher apenas dois dos cinco slots. O recurso de recomendação de backup preenche os outros três slots com itens exibidos na parte superior.

As recomendações de backup são escolhidas de maneira aleatória dentre os 500 produtos mais exibidos em todo o site. O período para recomendações de backup é de uma semana.

Os 500 resultados mais visualizados são ordenados sequencialmente e depois divididos em buckets de 20. Os buckets são fornecidos em ordem, mas os resultados dentro de cada bucket são aleatórios e retornados à página, para que os usuários que atualizam a página recebam resultados novos e aleatórios. Se o conjunto de resultados da união da coleção e das regras de filtragem for menor que 20, os itens serão aleatoriamente selecionados da coleção.

Esse processo de agrupamento em buckets significa que as recomendações de backup são exibidas na seguinte ordem:

1. Os 20 itens mais visualizados, aleatoriamente.
1. Os próximos 20 itens mais visualizados, aleatoriamente.
1. Os próximos 20 itens mais visualizados, aleatórios e assim por diante.

Sem a classificação, o 499º item mais visualizado poderia ser mostrado, seguido pelo 200º item mais visualizado, seguido pelo 380º item mais visualizado e assim por diante. A definição de períodos garante que os itens mais visualizados sejam recomendados primeiro.

Se os itens forem agrupados em coleções, as recomendações de backup geradas para cada critério também usarão a coleção, para que sejam incluídos na recomendação de backup apenas os itens na coleção. Qualquer item que for excluído pela regra de exclusão global não serve como uma recomendação de backup. As duplicatas são removidas dos lotes de recomendações.

As recomendações de backup são ativadas por padrão e preenchem os slots extras em um design com uma seleção aleatória dos itens mais populares no site.

O uso de recomendações de backup geralmente faz parte da discussão com a equipe de implementação durante a configuração inicial. Para alterar a configuração de recomendação de backup após a implementação, entre em contato com o gerente da conta.

Quando a **[!UICONTROL Renderização de Design Parcial]** (consulte [Conteúdo de Backup](/help/main/c-recommendations/c-algorithms/create-new-algorithm.md#content)) não está habilitada e o design não pode ser preenchido, as recomendações de backup (quando habilitadas) ou o conteúdo padrão são exibidos.
