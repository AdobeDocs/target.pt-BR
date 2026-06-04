---
keywords: Testes multivariados;solucionar problemas;solução de problemas;mvt
description: Explore os possíveis desafios a serem enfrentados ao usar as atividades de [!UICONTROL Teste multivariado] (MVT) no [!DNL Adobe Target], juntamente com as soluções sugeridas.
title: Como solucionar problemas de um [!UICONTROL teste multivariado]?
feature: Multivariate Tests
exl-id: 93bb8446-06af-4466-9824-7099c1080059
TQID: https://experienceleague.adobe.com/O9lmC1PmICPCOxcMDYVcSdpRoM-bqwKR-79deFIG2mg
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 174
ht-degree: 21%

---

# Solução de problemas de [!UICONTROL atividades de Teste multivariado]

Este artigo contém sugestões para resolver alguns problemas que podem ocorrer ao criar um [!UICONTROL Teste Multivariado] (MVT) no [!DNL Adobe Target].

* Ao editar uma atividade, se você usou métricas baseadas em [!DNL Analytics] e o conjunto de relatórios não foi carregado (exibições do ponteiro), alterne as métricas para [!DNL Target] métricas e alterne novamente para a métrica baseada em [!DNL Analytics]. Agora, o conjunto de relatórios deve ser carregado.
* Se você fizer alterações em um teste que já está em execução, poderá redefinir o teste e seus dados.

  [!DNL Target] permite que você edite uma atividade ao vivo. A edição de uma atividade que está em andamento pode redefinir o teste, de modo que os relatórios podem não reconhecer algumas das alterações.

  É seguro fazer pequenas mudanças, como editar ofertas existentes de texto ou html.

  As ações específicas que redefinem nomes de experiência e relatórios incluem:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de uma localização existente
