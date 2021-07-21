---
keywords: Direcionamento, público-alvo, geração de relatórios, métrica de sucesso
description: Saiba como escolher uma métrica de sucesso em [!DNL Adobe Target] que qualifique o usuário para o público-alvo do relatório.
title: Posso aplicar um relatório de público-alvo a uma métrica de sucesso?
feature: Métricas de sucesso
exl-id: 6b2f6669-6178-4da4-850d-8b1ce796a50d
source-git-commit: 20a5201b5c05b1f083252ac73b3b4bbc91e97aaa
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 54%

---

# Aplicar um relatório de público-alvo a uma métrica de sucesso

Escolha uma métrica de sucesso que qualifique o usuário para o público-alvo do relatório em [!DNL Adobe Target].

Para todas as atividades, a lista suspensa [!UICONTROL Aplicado em] permite que você aplique um público-alvo a uma métrica de sucesso para exibir números de relatórios depois que a métrica tiver sido alcançada e para ações subsequentes.

![](assets/success_metric.png)

Por exemplo, suponha que você tenha criado uma atividade para todos os visitantes que entram na sua página inicial e acessem a página de conversão, mas também queira obter mais detalhes dos visitantes que adicionaram mais de US$ 50 ao carrinho antes de converter.

A lista suspensa [!UICONTROL Aplicado em] fornece, potencialmente, três categorias: qualquer visitante da atividade, somente visitantes que atingem uma determinada etapa da atividade ou somente visitantes que alcançam a conversão. Ou, para expressar isso de outra maneira, você pode especificar que um visitante deve ter alcançado uma mbox na página de entrada da atividade, uma mbox que define algum ponto no meio da atividade ou a mbox de conversão no final da atividade.

[Métricas de sucesso](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) estão disponíveis apenas se você as configurar para sua atividade. Caso não tenha definido as métricas de sucesso, você verá apenas duas opções na lista suspensa: [!UICONTROL Entrada da Campanha] e [!UICONTROL Conversão].

Considere as seguintes informações ao aplicar um público-alvo de relatórios a uma métrica de sucesso:

* Para ações antes da ação com a métrica de sucesso aplicada, [!DNL Target] não aplica um público-alvo segmentado.
* Para ações após a métrica de sucesso aplicada, [!DNL Target] aplica um público segmentado.

Para exibir a segmentação nos relatórios, selecione o público-alvo desejado na lista suspensa [!UICONTROL Audience] no relatório da atividade.

![](assets/reporting_audience_dropdown.png)
