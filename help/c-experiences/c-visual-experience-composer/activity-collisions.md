---
keywords: Targeting
description: A guia Conflitos na página Visão geral das atividades lista as atividades em conflito no seu site.
title: Conflitos de atividades
feature: vec
uuid: 0e53ef60-2f71-4b34-9383-1de5cf5d3ab5
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 100%

---


# Conflitos de atividades{#activity-collisions}

A guia Conflitos na página Visão geral das atividades lista as atividades em conflito no seu site.

Um conflito de atividade ocorre quando várias atividades são configuradas para fornecer conteúdo para a mesma página. Se ocorrer um conflito de atividades, você pode não conseguir ver o conteúdo esperado na página.

Se a sua atividade contiver possíveis conflitos, a guia [!UICONTROL Conflitos] estará disponível na página de visão geral da atividade. São listadas todas as atividades do mesmo URL, independentemente do direcionamento de público-alvo de cada atividade. Abra esta guia para obter uma lista de atividades que podem colidir. Clique em uma atividade na lista para exibir a página de visão geral da atividade. Se a colisão alterar a experiência esperada, edite a atividade.

A lista de Colisões o ajuda a:

* Identificar se um teste já está em execução em uma página antes de configurar uma nova atividade
* Solucionar problemas de atividade se o conteúdo esperado não aparecer

A lista de Colisões mostra cada cenário do Target Standard onde a mbox é usada e que utiliza o mesmo URL. Para cada colisão potencial, a lista mostra o URL da atividade, o nome da mbox onde a colisão pode ocorrer e as atividades que correspondem a esses critérios. Se houver várias mboxes, elas serão listadas.

A lista mostra o status e a prioridade de cada colisão potencial, junto com outras informações. Você pode usar o status e a prioridade para ajudar a determinar a probabilidade de uma colisão ocorrer. Por exemplo, se houver uma colisão potencial entre duas atividades e uma estiver inativa, não haverá colisão real, a menos que a atividade inativa seja ativada. Se a colisão potencial for entre duas atividades ao vivo com a mesma prioridade e o mesmo público-alvo, uma colisão ocorrerá. Você pode alterar a prioridade ou o status para evitar a colisão.

Se os públicos-alvo forem diferentes, ainda haverá uma colisão potencial, pois pode ser que um determinado visitante pertença a vários públicos-alvo.
