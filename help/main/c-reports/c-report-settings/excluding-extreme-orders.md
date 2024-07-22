---
keywords: Target, relatórios, configurações de relatório, pedidos extremos, valores extremos
description: Saiba como excluir valores extremos de relatórios que afetam o Adobe [!DNL Target]  para que algumas ordens incomuns não afetem os resultados da atividade.
title: Como excluir valores extremos em relatórios?
feature: Reports
exl-id: fd2d0c18-62c0-41e0-800c-b2ae123f0e74
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 65%

---

# Excluir valores extremos

Você pode excluir valores extremos para que não afetem os relatórios em [!DNL Adobe Target], de modo que algumas ordens incomuns não afetem os resultados da atividade. Um exemplo de um pedido incomum pode ser um técnico comprando uniformes para um time inteiro em vez de compradores individuais comprando uniformes individuais.

>[!NOTE]
>
>O sinalizador [!UICONTROL Exclude Extreme Values] se aplica somente a atividades com os tipos de métrica [!UICONTROL Revenue] e [!UICONTROL Engagement].

Os valores extremos são automaticamente sinalizados com um indicador com base nas regras a seguir. Você pode alternar entre ver e excluir os valores extremos dos seus relatórios. Uma atividade terá seus valores extremos excluídos após a atividade ter sido executada por uma hora ou 15 pedidos, o que ocorrer primeiro.

Um valor é considerado extremo se ele tiver +/- 3 desvios-padrão do valor médio de pedido usando dados do último mês (até o ponto no tempo em que o cálculo foi feito).

Por exemplo, o filtro de valor extremo geralmente é útil ao usar a RPV. A RPV combina a taxa de conversão e o valor médio de pedido, e costuma exibir a volatilidade dessas métricas. Caso use a RPV e veja que os pedidos não estão sendo distribuídos normalmente, é provável que os resultados apareçam normais se você aplicar o filtro de pedido extremo.

Quando um valor é marcado como extremo, seu valor de pedido é substituído com o valor médio de pedido da experiência pelo último mês, excluindo extremos. A ordem também é marcada como extrema no relatório [!UICONTROL Order Details] e no download do CSV para resultados diários.

**Para excluir os valores extremos dos seus relatórios:**

1. Abra uma atividade que inclua métricas do tipo receita ou envolvimento e clique na guia **[!UICONTROL Reports]**.
1. Clique no ícone de engrenagem para exibir a caixa de diálogo **[!UICONTROL Settings]**.

   ![Resultado da etapa](assets/exclude_extreme_values.png)

1. Deslize o botão **[!UICONTROL Exclude Extreme Values]** para a posição &quot;ligado&quot; ou &quot;desligado&quot;, conforme desejado.
1. Clique em **[!UICONTROL Save]**.
