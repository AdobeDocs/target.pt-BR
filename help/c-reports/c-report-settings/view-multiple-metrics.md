---
keywords: Target;reports;report settings;multiple metrics;metrics;shown metrics;hidden metrics
description: Selecione várias métricas para visualização em um relatório usando o Adobe Target.
title: Visualização de várias métricas em um relatório usando o Adobe Target
feature: report settings
uuid: f3ea7313-0f98-4b58-88aa-e2438c06e739
translation-type: tm+mt
source-git-commit: 1433de7270f400ec21c4f506cdc6dee8bcaa550f
workflow-type: tm+mt
source-wordcount: '419'
ht-degree: 61%

---


# Exibir várias métricas em um relatório{#view-multiple-metrics-in-a-report}

É possível selecionar várias métricas para visualização em um [!DNL Adobe Target] relatório.

Esteja ciente das seguintes informações ao trabalhar com várias métricas nos relatórios:

* The ability to view multiple metrics is available for [A/B Test](/help/c-activities/t-test-ab/test-ab.md), [Auto-Allocate](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Auto-Target](/help/c-activities/auto-target-to-optimize.md), and [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md) (XT) activities only.
* You cannot add more than 20 metrics to a report for an activity that uses [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). You can add as many metrics as you have in your activity to reports for activities that do *not* use A4T.
* Se você tiver selecionado várias métricas, não será possível usar a opção [](/help/c-reports/downloading-data-in-csv-file.md)Baixar para baixar os relatórios em CSV. Você deve selecionar uma única métrica apenas para ativar a opção [!UICONTROL Baixar].
* You cannot view multiple metrics for activities created before the July 2015 [!DNL Target] release (July 30, 2015).

**Para selecionar várias métricas para exibir no relatório:**

1. Para exibir um relatório, clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista e na guia **[!UICONTROL Relatórios.]**
1. Clique na lista suspensa **[!UICONTROL Métrica de relatório]** para exibir as listas [!UICONTROL Métricas exibidas] e [!UICONTROL Métricas ocultas].

   ![](assets/multiple_metrics.png)

   Você pode usar a caixa [!UICONTROL Pesquisar] para encontrar rapidamente as métricas disponíveis para adicionar à lista de [!UICONTROL Métricas exibidas].

   Observe que você pode selecionar várias métricas dos dois modos [!UICONTROL Exibição de tabela] e [!UICONTROL Exibição de gráfico] do relatório.

1. Passe o mouse sobre as métricas desejadas na lista [!UICONTROL Métricas ocultas], em seguida, clique em **[!UICONTROL Selecionar]** para movê-las para a lista [!UICONTROL Métricas exibidas].

   Ou

   Arraste e solte as métricas desejadas da lista [!UICONTROL Métricas ocultas] para a lista [!UICONTROL Métricas exibidas].

   Deve existir ao menos uma métrica na lista [!UICONTROL Métricas exibidas].

   Você pode reorganizar as métricas arrastando-as e soltando-as na ordem desejada na lista [!UICONTROL Métricas exibidas]. The selected order will be reflected in the [!UICONTROL Table View] and [!UICONTROL Graph View]. Para remover uma métrica da lista [!UICONTROL Métricas exibidas], passe o ponteiro do mouse sobre a métrica e clique no ícone **X**.

1. Clique em **[!UICONTROL Salvar]** ao concluir.
1. (Conditional) While viewing the report in the [!UICONTROL Table View], hover your mouse pointer on any metric&#39;s column header to display a blue arrow. Clique na seta para expandir a tabela e exibir o [!UICONTROL Aumento] e a [!UICONTROL Confiança] para essa métrica.

   ![](assets/multiple_metrics_table.png)

   Você pode expandir apenas uma métrica/coluna por vez. Clique na seta novamente para recolher as colunas.

1. (Condicional) Ao exibir o relatório na Visualização de gráfico, você pode selecionar métricas individuais para exibir na lista suspensa:

   ![](assets/multiple_metrics_graph.png)

