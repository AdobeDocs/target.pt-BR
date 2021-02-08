---
keywords: Testes multivariados;solução de problemas;troubleshooting;mvt
description: Explore os possíveis desafios que você pode enfrentar ao usar atividades de teste multivariado (MVT) no Adobe Target, juntamente com as soluções sugeridas.
title: Como soluciono problemas de testes multivariados?
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---


# Solução de problemas de testes multivariados

Este tópico contém sugestões para resolver alguns problemas que podem ocorrer ao projetar um teste [!UICONTROL Multivariado] (MVT) em [!DNL Adobe Target].

* Ao editar uma atividade, se você usou [!DNL Analytics] métricas baseadas no conjunto de relatórios e o conjunto de relatórios não for carregado (exibições de ponteiro), mude as métricas para [!DNL Target] métricas e, em seguida, alterne novamente para métricas baseadas em [!DNL Analytics]. Agora, o conjunto de relatórios deve ser carregado.
* Se você fizer alterações em um teste que já está em execução, poderá redefinir o teste e seus dados.

   [!DNL Target] permite que você edite uma atividade ao vivo. Uma atividade que está em andamento pode redefinir o teste, assim, os relatórios podem não reconhecer algumas das alterações.

   É seguro fazer pequenas mudanças, como editar ofertas existentes de texto ou html.

   As ações específicas que redefinem nomes e relatórios de experiência:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de uma localização existente

