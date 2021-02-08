---
keywords: definição de metas;colisões;conflitos
description: As colisões ocorrem quando várias atividades são configuradas para fornecer conteúdo para a mesma página. Saiba como evitar colisões ao usar o Adobe Target.
title: Como Evitar Colisões De Atividades?
feature: Visual Experience Composer (VEC)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 79%

---


# Conflitos de atividades

A guia [!UICONTROL Colisões] na página [!UICONTROL Visão geral da Atividade] em [!DNL Adobe Target] colisões de atividades do lista no seu site.

Um conflito de atividade ocorre quando várias atividades são configuradas para fornecer conteúdo para a mesma página. Se ocorrer um conflito de atividades, você pode não conseguir ver o conteúdo esperado na página.

Se a sua atividade contiver possíveis conflitos, a guia [!UICONTROL Conflitos] estará disponível na página de visão geral da atividade. São listadas todas as atividades do mesmo URL, independentemente do direcionamento de público-alvo de cada atividade. Abra esta guia para obter uma lista de atividades que podem colidir. Clique em uma atividade na lista para exibir a página de visão geral da atividade. Se a colisão alterar a experiência esperada, edite a atividade.

A lista [!UICONTROL Colisões] ajuda a:

* Identificar se um teste já está em execução em uma página antes de configurar uma nova atividade
* Solucionar problemas de atividade se o conteúdo esperado não aparecer

A lista [!UICONTROL Colisões] mostra cada [!DNL Target] cenário em que a mbox é usada e que usa o mesmo URL. Para cada colisão potencial, a lista mostra o URL da atividade, o nome da mbox onde a colisão pode ocorrer e as atividades que correspondem a esses critérios. Se houver várias mboxes, elas serão listadas.

A lista mostra o status e a prioridade de cada colisão potencial, junto com outras informações. Você pode usar o status e a prioridade para ajudar a determinar a probabilidade de uma colisão ocorrer. Por exemplo, se houver uma colisão potencial entre duas atividades e uma estiver inativa, não haverá colisão real, a menos que a atividade inativa seja ativada. Se a colisão potencial for entre duas atividades ao vivo com a mesma prioridade e o mesmo público-alvo, uma colisão ocorrerá. Você pode alterar a prioridade ou o status para evitar a colisão.

Se os públicos-alvo forem diferentes, ainda haverá uma colisão potencial, pois pode ser que um determinado visitante pertença a vários públicos-alvo.
