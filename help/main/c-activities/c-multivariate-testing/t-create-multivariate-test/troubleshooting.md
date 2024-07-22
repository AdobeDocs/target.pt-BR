---
keywords: Testes multivariados;solucionar problemas;solução de problemas;mvt
description: Explore os possíveis desafios que você poderá enfrentar ao usar as atividades do [!UICONTROL Multivariate Test] (MVT) no  [!DNL Adobe Target], juntamente com as soluções sugeridas.
title: Como solucionar problemas de um [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 6c00224e814abb33cdf968a249bd36fb2e5ed2ed
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 22%

---

# Solução de problemas de [!UICONTROL Multivariate Test] atividades

Este artigo contém sugestões para resolver alguns problemas que podem ocorrer ao criar um [!UICONTROL Multivariate Test] (MVT) no [!DNL Adobe Target].

* Ao editar uma atividade, se você usou métricas baseadas em [!DNL Analytics] e o conjunto de relatórios não foi carregado (exibições do ponteiro), alterne as métricas para [!DNL Target] métricas e alterne novamente para a métrica baseada em [!DNL Analytics]. Agora, o conjunto de relatórios deve ser carregado.
* Se você fizer alterações em um teste que já está em execução, poderá redefinir o teste e seus dados.

  [!DNL Target] permite que você edite uma atividade ao vivo. A edição de uma atividade que está em andamento pode redefinir o teste, de modo que os relatórios podem não reconhecer algumas das alterações.

  É seguro fazer pequenas mudanças, como editar ofertas existentes de texto ou html.

  As ações específicas que redefinem nomes de experiência e relatórios incluem:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de uma localização existente
