---
title: Regras complexas de público
description: Saiba como trabalhar com conjuntos de regras de público-alvo grandes ou complexos em Sinalizadores, incluindo limites de valor em massa e como dividir regras em várias condições.
hide: true
exl-id: 37e037b6-45eb-4261-b580-30d94d8e55da
source-git-commit: eeba7af62ab101e687852ce993a001832ce4a83b
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 2%

---

# Regras complexas de público {#complex-rules}

## Uso de lógica aninhada para regras complexas {#nested-logic}

A lógica aninhada permite combinar várias condições de público-alvo com controle AND/OR preciso. Para ativá-lo:

1. Adicione as condições de público-alvo necessárias.
2. Habilite a **Lógica aninhada** na seção de regras de público-alvo.
3. Cada condição recebe um número. Insira uma expressão lógica que faça referência a esses números, por exemplo:
   * `1 and (2 or 3)`
   * `(1 and 2) or 3`
   * `(1 and 2) or (3 and 4)`

## Consulte também {#see-also}

* [Público-alvo em sinalizadores e grupos de recursos](audience-in-feature-flags-and-feature-groups.md)

<!-- -->
