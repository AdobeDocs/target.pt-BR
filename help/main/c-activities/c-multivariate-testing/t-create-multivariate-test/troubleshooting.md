---
keywords: Testes multivariados, solução de problemas, solução de problemas, mvt
description: Explore os possíveis desafios que você pode enfrentar ao usar as atividades de Teste multivariado (MVT) no Adobe Target, juntamente com as soluções sugeridas.
title: Como soluciono problemas de testes multivariados?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '176'
ht-degree: 42%

---

# Solução de problemas de testes multivariados

Este tópico contém sugestões para solucionar alguns problemas que podem ocorrer ao criar um [!UICONTROL Multivariado] Teste (MVT) em [!DNL Adobe Target].

* Ao editar uma atividade, se você tiver usado [!DNL Analytics]métricas baseadas em , e o conjunto de relatórios não é carregado (exibições de ponteiro), alterne as métricas para [!DNL Target] e alternar novamente para [!DNL Analytics]métrica baseada em . Agora, o conjunto de relatórios deve ser carregado.
* Se você fizer alterações em um teste que já esteja em execução, poderá redefinir o teste e seus dados.

   [!DNL Target] permite editar uma atividade ao vivo. Uma atividade que está em andamento pode redefinir o teste, assim, os relatórios podem não reconhecer algumas das alterações.

   É seguro fazer pequenas mudanças, como editar ofertas existentes de texto ou html.

   As ações específicas que redefinem nomes e relatórios de experiência:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de uma localização existente
