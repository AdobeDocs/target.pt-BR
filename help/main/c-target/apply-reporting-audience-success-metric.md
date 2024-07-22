---
keywords: Direcionamento, público-alvo, geração de relatórios, métrica de sucesso
description: Saiba como escolher uma métrica de sucesso no  [!DNL Adobe Target]  que qualifique o usuário para o público-alvo do relatório.
title: Posso aplicar um relatório de público-alvo a uma métrica de sucesso?
feature: Success Metrics
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: bcbb6dec9d6add07c109b07bf125c1356ad2a8b9
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 36%

---

# Aplicar um relatório de público-alvo a uma métrica de sucesso

Escolha uma métrica de sucesso que qualifique o usuário para o público-alvo de relatórios em [!DNL Adobe Target].

Para todas as atividades, a lista suspensa [!UICONTROL Applied At] permite aplicar um público-alvo a uma métrica de sucesso para que você possa exibir os números dos relatórios depois que a métrica for atingida e para ações subsequentes.

![imagem de métrica_de_sucesso](assets/success_metric.png)

Por exemplo, suponha que você tenha criado uma atividade para todos os visitantes que entram na sua página inicial e acessem a página de conversão, mas também queira obter mais detalhes dos visitantes que adicionaram mais de US$ 50 ao carrinho antes de converter.

A lista suspensa [!UICONTROL Applied At] possivelmente fornece três categorias:

* Quaisquer visitantes da atividade
* Somente visitantes que atingem uma determinada etapa na atividade
* Somente visitantes que alcançam a conversão

Ou, para expressar isso de outra maneira, você pode especificar que um visitante deve ter alcançado uma mbox na página de entrada da atividade, uma mbox que define algum ponto no meio da atividade ou a mbox de conversão no final da atividade.

>[!NOTE]
>
>[Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) estão disponíveis apenas se você as configurar para sua atividade. Se você não tiver definido as métricas de sucesso, verá apenas duas opções da lista suspensa: [!UICONTROL Campaign Entry] e [!UICONTROL Conversion].


## Considerações

Considere as seguintes informações ao aplicar um público-alvo de relatórios a uma métrica de sucesso:

* Somente as métricas de sucesso, começando pela aplicada ao público-alvo, mostrarão dados de relatórios segmentados pelo público-alvo
* As métricas de sucesso que precedem aquelas às quais o público-alvo é aplicado não serão segmentadas pelo público-alvo e mostrarão todos os dados do visitante
* As métricas são consideradas com base em sua ordem na definição da atividade, com [!UICONTROL Primary Goal] sendo a última.

## Exibir segmentação em relatórios

Para exibir a segmentação nos relatórios, selecione o público-alvo desejado na lista suspensa [!UICONTROL Audience] no relatório de atividade.

![imagem de report_audience_dropdown](assets/reporting_audience_dropdown.png)

## Exemplo

Considere uma atividade que tenha Métrica de sucesso1, Métrica de sucesso2, Métrica de sucesso3 e o Objetivo principal.

Suponha que você tenha o relatório Audience1 definido como &quot;Entrada&quot; e o relatório Audience2 definido como Métrica de sucesso2. Os públicos-alvo filtrarão os dados de relatório da seguinte maneira:

|  | Visitantes | Métrica de sucesso1 | Métrica de sucesso2 | Métrica de sucesso3 | Meta primária |
| --- | --- | --- | --- | --- | --- |
| Público1 | Aplicado | Aplicado | Aplicado | Aplicado | Aplicado |
| Público2 | Não aplicado | Não aplicado | Aplicado | Aplicado | Aplicado |
