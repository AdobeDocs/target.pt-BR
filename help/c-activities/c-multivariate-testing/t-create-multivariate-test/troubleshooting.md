---
keywords: Mobile Web Experience Editor
description: Este tópico contém sugestões para resolver alguns problemas que podem ocorrer ao projetar um teste MVT no Adobe Target.
title: Solução de problemas de testes multivariados
feature: mvt
translation-type: tm+mt
source-git-commit: c2769c0fcf7a05c10405ec855468c829aca785c0
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 77%

---


# Solução de problemas de testes multivariados{#troubleshoot-multivariate-tests}

Este tópico contém sugestões para resolver alguns problemas que podem ocorrer ao projetar um teste MVT no Adobe Target.

* Ao editar uma atividade, se você usar métricas baseadas no Analytics e o conjunto de relatórios não for carregado (exibições de ponteiro), alterne as métricas para as do Target e alterne novamente para a métrica baseada no Analytics. Agora, o conjunto de relatórios deve ser carregado.
* Para fazer alterações em um teste que já esteja em execução, é possível redefinir o teste e seus dados.

   O Target permite editar uma atividade ao vivo. Uma atividade que está em andamento pode redefinir o teste, assim, os relatórios podem não reconhecer algumas das alterações.

   É seguro fazer pequenas mudanças, como editar ofertas existentes de texto ou html.

   As ações específicas que redefinem nomes e relatórios de experiência:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de uma localização existente

