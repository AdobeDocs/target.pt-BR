---
keywords: mbox global;; implementar a at.js
description: Saiba mais sobre a mbox global no Adobe Target, um nome usado para fazer referência à chamada única de servidor feita na parte superior de cada página da Web na implementação  [!DNL Target] .
title: O que é uma mbox global?
feature: at.js
role: Developer
exl-id: 84d15feb-f5df-4879-ae35-a7f455c1b20f
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 82%

---

# Entender a mbox global

Informações sobre a mbox global, um nome usado para referir-se a uma chamada de servidor única feita na parte superior de cada página da Web na sua implementação do [!DNL Adobe Target].

Por padrão, a mbox global é chamada de `target-global-mbox`. Ela pode ser renomeada para a sua conta, se necessário.

Existem várias diferenças entre uma mbox comum (mbox não global) e a mbox global, incluindo:

| Mbox comum | Mbox global |
|--- |--- |
| Uma mbox comum geralmente envolve conteúdo com uma tag `<DIV>`. | A mbox global está &quot;vazia&quot; e não envolve nenhum conteúdo. |
| O conteúdo de apenas uma atividade pode ser entregue em uma mbox comum. | O conteúdo de várias atividades pode ser entregue em uma resposta a uma mbox global. |

Se várias atividades forem fornecidas por meio da mbox global ou por várias mboxes regulares, [!DNL Target] [determine a prioridade](/help/c-activities/priority.md#concept_1780C11FEA57440499F0047DD6900E0F) pela qual a atividade (ou atividades) é entregue para uma página da Web.

Os dados adicionais da página podem ser enviados para o [!DNL Target] junto com a mbox global usando a função `targetPageParams`. Isso é semelhante à funcionalidade do parâmetro da mbox. Para obter mais informações, consulte [Passar parâmetros para uma mbox global](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-understanding-global-mbox/pass-parameters-to-global-mbox.md#concept_33362A04146C4E3C8E7089B65F38B5E5).
