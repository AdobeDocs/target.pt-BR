---
keywords: Multivariate Tests;troubleshoot;troubleshooting;mvt
description: Este tópico contém sugestões para resolver alguns problemas que podem ocorrer ao projetar um teste MVT no Adobe Target.
title: Solução de problemas de testes multivariados
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: 4adade56529fb95e4400e06d04d3c6c69e120edc
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 45%

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

