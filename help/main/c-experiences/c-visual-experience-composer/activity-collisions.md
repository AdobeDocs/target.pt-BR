---
keywords: direcionamento;colisões;conflitos
description: Evite colisões de entrega de conteúdo na mesma página ao configurar as atividades corretamente no Adobe Target.
title: Como Posso Evitar Colisões De Atividades?
feature: Visual Experience Composer (VEC)
exl-id: 1af90dd1-69c9-41ec-8785-095dcc557b32
TQID: 'https://experienceleague.adobe.com/R6cwp4KnoYPO9Wxr47HswtBX6jKPJ0i-UGdtA1ZHawU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f7501c88-b36a-590b-9cc4-dea607bda94b
    internal-label: Visual Experience Composer (VEC)
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '354'
ht-degree: 18%
---
# Conflitos de atividades {#activity-collisions}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como usar a guia **[!UICONTROL Conflitos]** para localizar atividades que possam fornecer conteúdo à mesma página.

>[!ENDSHADEBOX]

Um conflito de atividade ocorre quando várias atividades são configuradas para fornecer conteúdo para a mesma página. Se ocorrer uma colisão de atividade, o conteúdo esperado pode não aparecer na página.

A guia **[!UICONTROL Conflitos]** na página **[!UICONTROL Visão Geral da Atividade]** em [!DNL Adobe Target] lista as colisões de atividades no site e mostra se uma atividade contém possíveis colisões. A lista **[!UICONTROL Conflitos]** ajuda a:

* Identifique se um teste já está em execução em uma página antes de uma nova atividade ser configurada
* Solucionar problemas de atividade se o conteúdo esperado não aparecer

## Acesse a guia Conflitos {#access-collisions}

Clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista e acesse o menu **[!UICONTROL Conflitos]**.

![Ícone Configurar](assets/collisions_1.png)

São listadas todas as atividades do mesmo URL, independentemente do direcionamento de público-alvo de cada atividade. A guia lista as atividades que podem estar em conflito. Se a colisão alterar a experiência esperada, edite a atividade.

## Leia a lista de colisões {#collisions-list}

A lista **[!UICONTROL Conflitos]** mostra cada cenário [!DNL Target] em que a mbox é usada e que usa a mesma URL. Para cada possível colisão, a lista mostra o URL da atividade, o nome da mbox em que a colisão pode ocorrer e quaisquer atividades que correspondam a esses dois critérios. Se houver várias mboxes, elas serão listadas.

A lista também mostra o status e a prioridade de cada possível colisão, juntamente com outras informações. O status e a prioridade ajudam a determinar a probabilidade de ocorrer uma colisão. Para duas atividades que podem colidir:

* Se uma atividade não estiver ativa no momento, não poderá ocorrer uma colisão. Uma colisão só é possível se a atividade inativa se tornar ativa.
* Se a colisão potencial for entre duas atividades ativas com a mesma prioridade e o mesmo público-alvo, ocorre uma colisão. A prioridade ou o status podem ser alterados para evitar a colisão.
* Se os públicos forem diferentes, ainda haverá uma possível colisão, pois um visitante específico pode pertencer a vários públicos.
