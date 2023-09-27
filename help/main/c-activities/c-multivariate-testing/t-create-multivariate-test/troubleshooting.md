---
keywords: Testes multivariados;solucionar problemas;solução de problemas;mvt
description: Explore os possíveis desafios que você pode enfrentar ao usar o [!UICONTROL Teste multivariado] (MVT) atividades no [!DNL Adobe Target], juntamente com as soluções sugeridas.
title: Como solucionar problemas de uma [!UICONTROL Teste multivariado]?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 21%

---

# Solução de problemas [!UICONTROL Teste multivariado] atividades

Este artigo contém sugestões para resolver alguns problemas que podem ocorrer ao criar uma [!UICONTROL Teste multivariado] (MVT) em [!DNL Adobe Target].

* Ao editar uma atividade, se você usou [!DNL Analytics]métricas baseadas em e o conjunto de relatórios não for carregado (exibições com controle giratório), alterne as métricas para [!DNL Target] métricas e alterne novamente para [!DNL Analytics]métrica baseada em. Agora, o conjunto de relatórios deve ser carregado.
* Se você fizer alterações em um teste que já está em execução, poderá redefinir o teste e seus dados.

  [!DNL Target] permite editar uma atividade ativa. A edição de uma atividade que está em andamento pode redefinir o teste, de modo que os relatórios podem não reconhecer algumas das alterações.

  É seguro fazer pequenas mudanças, como editar ofertas existentes de texto ou html.

  As ações específicas que redefinem nomes de experiência e relatórios incluem:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de uma localização existente
