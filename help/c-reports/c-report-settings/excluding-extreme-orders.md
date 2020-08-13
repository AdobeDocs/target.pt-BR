---
keywords: Target;reports;report settings;extreme orders;extreme values
description: Você pode excluir valores extremos de afetar relatórios no Adobe Target para que alguns pedidos incomuns não afetem os resultados da atividade. Um exemplo de um pedido incomum pode ser um técnico comprando uniformes para um time inteiro em vez de compradores individuais comprando uniformes individuais.
title: Excluir valores extremos em relatórios do Adobe Target
feature: report settings
uuid: bb151b54-09ef-40b5-bc04-95c61b761f5a
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '342'
ht-degree: 88%

---


# Excluir valores extremos{#exclude-extreme-values}

Você pode excluir valores extremos em relatórios afetados para que alguns pedidos incomuns não afetem os resultados de suas atividades. Um exemplo de um pedido incomum pode ser um técnico comprando uniformes para um time inteiro em vez de compradores individuais comprando uniformes individuais.

>[!NOTE]
>
>O sinalizador [!UICONTROL Excluir valores extremos] é aplicado apenas para atividades com métricas do tipo receita e envolvimento.

Os valores extremos são automaticamente sinalizados com um indicador com base nas regras a seguir. Você pode alternar entre ver e excluir os valores extremos dos seus relatórios. Uma atividade terá seus valores extremos excluídos após a atividade ter sido executada por uma hora ou 15 pedidos, o que ocorrer primeiro.

Um valor é considerado extremo se ele tiver +/- 3 desvios-padrão do valor médio de pedido usando dados do último mês (até o ponto no tempo em que o cálculo foi feito).

Por exemplo, o filtro de valor extremo geralmente é útil ao usar a RPV. A RPV combina a taxa de conversão e o valor médio de pedido, e costuma exibir a volatilidade dessas métricas. Caso use a RPV e veja que os pedidos não estão sendo distribuídos normalmente, é provável que os resultados apareçam normais se você aplicar o filtro de pedido extremo.

Quando um valor é marcado como extremo, seu valor de pedido é substituído com o valor médio de pedido da experiência pelo último mês, excluindo extremos. O pedido também é marcado como extremo no relatório de detalhes do pedido e no download CSV dos resultados diários.

**Para excluir os valores extremos dos seus relatórios:**

1. Abra uma atividade que inclua métricas do tipo receita ou envolvimento e clique na guia **[!UICONTROL Relatórios.]**
1. Clique no ícone de engrenagem.

   ![Configurações do relatório](/help/c-reports/c-report-settings/assets/report-settings-gear-icon.png)

   A caixa de diálogo de opções de Configurações [!UICONTROL de] relatório é exibida.

   ![Resultado da etapa](assets/exclude_extreme_values.png)

1. Alterne a opção **[!UICONTROL Excluir valores extremos]** para ligada ou desligada, como desejar.
1. Clique em **[!UICONTROL Salvar]**.
