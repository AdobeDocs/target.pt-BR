---
keywords: Destino;relatórios;configurações de relatório;várias métricas;métricas;métricas mostradas;métricas ocultas;Target;reports;report settings;multiple metrics;metrics;displayed metrics;hidden metrics
description: Saiba como selecionar várias métricas para visualizar em um relatório usando o Adobe Target.
title: Como exibir várias métricas em um relatório?
feature: Reports
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
TQID: https://experienceleague.adobe.com/mXLlrS1wwfISfxWxq2c-sMDJP1vqxQjbqM-DsLJK9bY
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 439
ht-degree: 55%

---

# Exibir várias métricas em um relatório

Você pode selecionar várias métricas para exibir em um relatório [!DNL Adobe Target].

Esteja ciente das seguintes informações ao trabalhar com várias métricas nos relatórios:

* A capacidade de exibir várias métricas está disponível somente para atividades de [Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md), [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) e [Direcionamento de experiência](/help/main/c-activities/t-experience-target/experience-target.md) (XT).
* Você não pode adicionar mais de 20 métricas a um relatório para uma atividade que usa o [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Você pode adicionar quantas métricas tiver em sua atividade aos relatórios para atividades que *não* usam o A4T.
* Você não pode usar a [opção de Download](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md) para baixar relatórios em CSV se tiver selecionado várias métricas. Você deve selecionar uma única métrica apenas para ativar a opção [!UICONTROL Baixar].
* Não é possível exibir várias métricas para atividades criadas antes da versão [!DNL Target] de julho de 2015 (30 de julho de 2015).

**Para selecionar várias métricas para exibir no relatório:**

1. Para exibir um relatório, clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista e na guia **[!UICONTROL Relatórios]**.
1. Clique na lista suspensa **[!UICONTROL Métrica de relatório]** para exibir as listas [!UICONTROL Métricas exibidas] e [!UICONTROL Métricas ocultas].

   Você pode usar a caixa [!UICONTROL Pesquisar] para encontrar rapidamente as métricas disponíveis para adicionar à lista de [!UICONTROL Métricas exibidas].

   Observe que você pode selecionar várias métricas dos dois modos [!UICONTROL Exibição de tabela] e [!UICONTROL Exibição de gráfico] do relatório.

1. Passe o mouse sobre as métricas desejadas na lista [!UICONTROL Métricas ocultas], em seguida, clique em **[!UICONTROL Selecionar]** para movê-las para a lista [!UICONTROL Métricas exibidas].

   Ou

   Arraste e solte as métricas desejadas da lista [!UICONTROL Métricas ocultas] para a lista [!UICONTROL Métricas exibidas].

   Deve existir ao menos uma métrica na lista [!UICONTROL Métricas exibidas].

   Você pode reorganizar as métricas arrastando-as e soltando-as na ordem desejada na lista [!UICONTROL Métricas exibidas]. A ordem selecionada será refletida na [!UICONTROL Exibição de Tabela] e na [!UICONTROL Exibição de Gráfico]. Para remover uma métrica da lista [!UICONTROL Métricas exibidas], passe o ponteiro do mouse sobre a métrica e clique no ícone **X**.

1. Clique em **[!UICONTROL Salvar]** ao concluir.
1. (Condicional) Ao visualizar o relatório na [!UICONTROL Visualização de tabela], passe o mouse sobre o cabeçalho de coluna de qualquer métrica para exibir uma seta azul. Clique na seta para expandir a tabela e exibir o [!UICONTROL Aumento] e a [!UICONTROL Confiança] para essa métrica.

   Você pode expandir apenas uma métrica/coluna por vez. Clique na seta novamente para recolher as colunas.

1. (Condicional) Ao visualizar o relatório na [!UICONTROL Exibição em gráfico], você pode selecionar métricas individuais para exibir na lista suspensa.
