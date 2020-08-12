---
keywords: global mbox;implement mbox.js;implement at.js
description: Informações sobre a mbox global, um nome usado para fazer referência à chamada única de servidor feita na parte superior de cada página da Web na implementação do Adobe Target.
title: Entender a mbox global
feature: null
subtopic: Getting Started
topic: Standard
uuid: d8f48c94-6487-437b-828f-f9be7da58f48
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 73%

---


# Entender a mbox global{#understand-the-global-mbox}

Informações sobre a mbox global, um nome usado para fazer referência à chamada única de servidor feita na parte superior de cada página da Web na implementação do Adobe Target.

Por padrão, a mbox global é chamada de [!DNL target-global-mbox]. Ela pode ser renomeada para a sua conta, se necessário.

Existem várias diferenças entre uma mbox comum (mbox não global) e a mbox global, incluindo:

| Mbox comum | Mbox global |
|--- |--- |
| Uma mbox comum geralmente envolve conteúdo com uma tag `<DIV>`. | A mbox global está &quot;vazia&quot; e não envolve nenhum conteúdo. |
| O conteúdo de apenas uma atividade pode ser entregue em uma mbox comum. | O conteúdo de várias atividades pode ser entregue em uma resposta a uma mbox global. |

Se várias atividades forem fornecidas por meio da mbox global ou por várias mboxes regulares, [!DNL Target] [determine a prioridade](../../../../c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) pela qual a atividade (ou atividades) é entregue para uma página da Web.

Os dados adicionais da página podem ser enviados para o [!DNL Target] junto com a mbox global usando a função `targetPageParams`. Isso é semelhante à funcionalidade do parâmetro da mbox. Para obter mais informações, consulte [Passar parâmetros para uma mbox global](../../../../c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).
