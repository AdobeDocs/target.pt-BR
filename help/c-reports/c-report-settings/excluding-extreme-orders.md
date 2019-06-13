---
description: Você pode excluir valores extremos em relatórios afetados para que alguns pedidos incomuns não afetem os resultados de suas atividades. Um exemplo de um pedido incomum pode ser um técnico comprando uniformes para um time inteiro em vez de compradores individuais comprando uniformes individuais.
keywords: Target, relatórios, configurações de relatório, pedidos extremos, valores extremos
seo-description: Você pode excluir valores extremos em relatórios afetados para que alguns pedidos incomuns não afetem os resultados de suas atividades. Um exemplo de um pedido incomum pode ser um técnico comprando uniformes para um time inteiro em vez de compradores individuais comprando uniformes individuais.
seo-title: Excluir valores extremos
solution: Target
title: Excluir valores extremos
topic: Premium
uuid: bb151b54-09ef-40b5-bc04-95c61b761f5a
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

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
1. Clique no ícone de engrenagem para exibir as opções de [!UICONTROL Configurações do relatório.]

   ![Resultado da etapa](assets/exclude_extreme_values.png)

1. Alterne a opção **[!UICONTROL Excluir valores extremos]** para ligada ou desligada, como desejar.
1. Clique em **[!UICONTROL Salvar configurações]**.
