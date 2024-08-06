---
keywords: direcionamento;colisões;conflitos
description: Evite colisões de entrega de conteúdo na mesma página ao configurar as atividades corretamente no Adobe Target.
title: Como Posso Evitar Colisões De Atividades?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: 5c963e97dae11326396a5c1c5e32d19f4d463c74
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 50%

---

# Conflitos de atividades

A guia [!UICONTROL Collisions] na página [!UICONTROL Activity Overview] do [!DNL Adobe Target] lista as colisões de atividades no site.

Um conflito de atividade ocorre quando várias atividades são configuradas para fornecer conteúdo para a mesma página. Se ocorrer um conflito de atividades, você pode não conseguir visualizar o conteúdo esperado na página.

A guia [!UICONTROL Collisions] está disponível na página de visão geral da atividade e pode informá-lo se a atividade contiver possíveis colisões.

Para acessar a guia [!UICONTROL Collisions], clique em **[!UICONTROL Activities]** > clique na atividade desejada da lista > em seguida, clique em **[!UICONTROL Collisions]** no painel esquerdo.

São listadas todas as atividades do mesmo URL, independentemente do direcionamento de público-alvo de cada atividade. Abra esta guia para obter uma lista de atividades que podem colidir. Se a colisão alterar a experiência esperada, edite a atividade.

A lista [!UICONTROL Collisions] ajuda a:

* Identificar se um teste já está em execução em uma página antes de configurar uma nova atividade
* Solucionar problemas de atividade se o conteúdo esperado não aparecer

A lista [!UICONTROL Collisions] mostra cada cenário [!DNL Target] em que a mbox é usada e que usa a mesma URL. Para cada possível colisão, a lista mostra o URL da atividade, o nome da mbox em que a colisão pode ocorrer e quaisquer atividades que correspondam a esses dois critérios. Se houver várias mboxes, elas serão listadas.

A lista mostra o status e a prioridade de cada colisão potencial, junto com outras informações. Você pode usar o status e a prioridade para ajudar a determinar a probabilidade de uma colisão ocorrer. Considere duas atividades que podem colidir. Se uma atividade não estiver ativa no momento, não poderá ocorrer uma colisão. Uma colisão só é possível se a atividade inativa se tornar ativa. Se a colisão potencial for entre duas atividades ativas com a mesma prioridade e o mesmo público-alvo, ocorre uma colisão. Você pode alterar a prioridade ou o status para evitar a colisão.

Se os públicos-alvo forem diferentes, ainda haverá uma colisão potencial, pois pode ser que um determinado visitante pertença a vários públicos-alvo.
