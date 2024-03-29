---
keywords: direcionamento;colisões;conflitos
description: Conflitos ocorrem quando várias atividades são configuradas para entregar conteúdo na mesma página. Saiba como evitar colisões ao usar o Adobe Target.
title: Como Posso Evitar Colisões De Atividades?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
source-git-commit: b34701113ebdc9f539e5a3d7163aa3dd85368af3
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 66%

---

# Conflitos de atividades

A variável [!UICONTROL Colisões] na guia [!UICONTROL Visão geral da atividade] página em [!DNL Adobe Target] lista as atividades em conflito no seu site.

Um conflito de atividade ocorre quando várias atividades são configuradas para fornecer conteúdo para a mesma página. Se ocorrer um conflito de atividades, você pode não conseguir ver o conteúdo esperado na página.

A variável [!UICONTROL Colisões] está disponível na página de visão geral da atividade e pode informá-lo se a atividade contiver possíveis colisões. São listadas todas as atividades do mesmo URL, independentemente do direcionamento de público-alvo de cada atividade. Abra esta guia para obter uma lista de atividades que podem colidir. Clique em uma atividade na lista para exibir a página de visão geral da atividade. Se a colisão alterar a experiência esperada, edite a atividade.

A variável [!UICONTROL Colisões] ajuda a:

* Identificar se um teste já está em execução em uma página antes de configurar uma nova atividade
* Solucionar problemas de atividade se o conteúdo esperado não aparecer

A variável [!UICONTROL Colisões] a lista mostra a cada [!DNL Target] cenário em que a mbox é usada e que usa o mesmo URL. Para cada possível colisão, a lista mostra o URL da atividade, o nome da mbox em que a colisão pode ocorrer e quaisquer atividades que correspondam a esses dois critérios. Se houver várias mboxes, elas serão listadas.

A lista mostra o status e a prioridade de cada colisão potencial, junto com outras informações. Você pode usar o status e a prioridade para ajudar a determinar a probabilidade de uma colisão ocorrer. Por exemplo, se houver uma colisão potencial entre duas atividades e uma estiver inativa, não haverá colisão real, a menos que a atividade inativa seja ativada. Se a colisão potencial for entre duas atividades ao vivo com a mesma prioridade e o mesmo público-alvo, uma colisão ocorrerá. Você pode alterar a prioridade ou o status para evitar a colisão.

Se os públicos-alvo forem diferentes, ainda haverá uma colisão potencial, pois pode ser que um determinado visitante pertença a vários públicos-alvo.
