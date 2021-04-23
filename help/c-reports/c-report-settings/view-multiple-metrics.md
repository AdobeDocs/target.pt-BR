---
keywords: Target, relatórios, configurações de relatório, várias métricas, métricas, métricas mostradas, métricas ocultas
description: Saiba como selecionar várias métricas para exibir em um relatório usando o Adobe Target.
title: Como visualizar várias métricas em um relatório?
feature: Relatórios
exl-id: 8d8aedd8-4583-4131-8ae0-df14e071940a
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '434'
ht-degree: 59%

---

# Exibir várias métricas em um relatório

Você pode selecionar várias métricas para exibir em um relatório [!DNL Adobe Target].

Esteja ciente das seguintes informações ao trabalhar com várias métricas nos relatórios:

* A capacidade de exibir várias métricas está disponível somente para atividades de [Teste A/B](/help/c-activities/t-test-ab/test-ab.md), [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) e [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md) (XT).
* Não é possível adicionar mais de 20 métricas a um relatório para uma atividade que usa o [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Você pode adicionar quantas métricas tiver em sua atividade aos relatórios de atividades que *not* usam o A4T.
* Se você tiver selecionado várias métricas, não será possível usar a opção [](/help/c-reports/downloading-data-in-csv-file.md)Baixar para baixar os relatórios em CSV. Você deve selecionar uma única métrica apenas para ativar a opção [!UICONTROL Baixar].
* Não é possível exibir várias métricas de atividades criadas antes da versão de julho de 2015 [!DNL Target] (30 de julho de 2015).

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

   Você pode reorganizar as métricas arrastando-as e soltando-as na ordem desejada na lista [!UICONTROL Métricas exibidas]. A ordem selecionada será refletida na [!UICONTROL Exibição de tabela] e [!UICONTROL Exibição de gráfico]. Para remover uma métrica da lista [!UICONTROL Métricas exibidas], passe o ponteiro do mouse sobre a métrica e clique no ícone **X**.

1. Clique em **[!UICONTROL Salvar]** ao concluir.
1. (Condicional) Ao visualizar o relatório na [!UICONTROL Exibição de tabela], passe o ponteiro do mouse sobre o cabeçalho da coluna de qualquer métrica para exibir uma seta azul. Clique na seta para expandir a tabela e exibir o [!UICONTROL Aumento] e a [!UICONTROL Confiança] para essa métrica.

   ![](assets/multiple_metrics_table.png)

   Você pode expandir apenas uma métrica/coluna por vez. Clique na seta novamente para recolher as colunas.

1. (Condicional) Ao visualizar o relatório na Visualização de gráfico, você pode selecionar métricas individuais para exibir na lista suspensa:

   ![](assets/multiple_metrics_graph.png)
