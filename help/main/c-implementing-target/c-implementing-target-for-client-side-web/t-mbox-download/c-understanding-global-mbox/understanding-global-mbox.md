---
keywords: mbox global;; implementar a at.js
description: Saiba mais sobre a mbox global no Adobe Target, um nome usado para referir-se a uma única chamada de servidor feita na parte superior de cada página da Web em seu [!DNL Target] implementação.
title: O que é uma mbox global?
feature: at.js
role: Developer
exl-id: 84d15feb-f5df-4879-ae35-a7f455c1b20f
source-git-commit: b1e8ea2370fc15f4bfcd960ab2960cafe2db92b8
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 79%

---

# Entender a mbox global

Informações sobre a mbox global, um nome usado para referir-se a uma chamada de servidor única feita na parte superior de cada página da Web na sua implementação do [!DNL Adobe Target].

Por padrão, a mbox global é chamada de `target-global-mbox`. Ela pode ser renomeada para a sua conta, se necessário.

Existem várias diferenças entre uma mbox comum (mbox não global) e a mbox global, incluindo:

| Mbox comum | Mbox global |
|--- |--- |
| Uma mbox comum geralmente envolve conteúdo com uma tag `<DIV>`. | A mbox global está &quot;vazia&quot; e não envolve nenhum conteúdo. |
| O conteúdo de apenas uma atividade pode ser entregue em uma mbox comum. | O conteúdo de várias atividades pode ser entregue em uma resposta a uma mbox global. |

Se várias atividades forem fornecidas por meio da mbox global ou por várias mboxes regulares, [!DNL Target] [determine a prioridade](/help/main/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) pela qual a atividade (ou atividades) é entregue para uma página da Web.

Os dados adicionais da página podem ser enviados para o [!DNL Target] junto com a mbox global usando a função `targetPageParams`. Isso é semelhante à funcionalidade do parâmetro da mbox. Para obter mais informações, consulte [Passar parâmetros para uma mbox global](https://developer.adobe.com/target/implement/client-side/atjs/global-mbox/pass-parameters-to-global-mbox/).
