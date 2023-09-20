---
keywords: alocação automática de tráfego;direcionamento;alocação automática;alocação automática;automated traffic allocation;targeting;autoallocate
description: Saiba como [!UICONTROL Alocação automática] atividade no [!DNL Adobe Target] O identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor.
title: Pode [!UICONTROL Alocação automática] Atividades obtêm resultados mais rápidos e receita maior?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: e9976135c46f6658030b07fce384364f0c9ff0ed
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# [!UICONTROL Alocação automática] oferece resultados de testes mais rápidos e receita maior do que um teste manual

Com uma atividade A/B manual, você pode perder conversões, pois não pode entregar a experiência vencedora a todo o público-alvo até que a atividade seja concluída. Sua distribuição de tráfego permanece fixa mesmo depois de reconhecer que algumas experiências estão com desempenho melhor que outras, e a atividade deve executar todo o curso antes de poder agir em um vencedor.

## Alocação automática de tráfego

Se você quiser ter uma opção para distribuir a experiência vencedora com mais frequência e no início da atividade, removendo ou reduzindo simultaneamente o custo de configuração e cálculo de escolher tamanhos de amostra, níveis de confiança e outros conceitos estatísticos, [!UICONTROL Alocação automática] O é a melhor opção.

## Como o [!UICONTROL Alocação automática] trabalhar?

[!UICONTROL Alocação automática] usa o princípio do multi-armed bandit. Se o termo não é familiar, um bandido de um braço é um termo coloquial para uma slot machine (pense: Las Vegas). Visualize a alocação automática de tráfego como se tivesse várias máquinas de fenda, neste caso, variações de teste e, a princípio, puxando todas as alças igualmente. Com o tempo, uma ou mais máquinas, ou variações de testes, podem pagar mais do que outras. Quando isso acontece, um apostador naturalmente começa a puxar as alças daqueles que ganham com mais frequência. Em termos de alocação de tráfego, [!DNL Target] O atende mais visitantes à experiência ou às experiências que estão ganhando mais.

Considere a ilustração a seguir de uma atividade A/B de duas semanas. Com [!UICONTROL Alocação automática], à medida que uma experiência vencedora emerge, [!UICONTROL Target] O desvia mais tráfego para o vencedor no início do teste.

![Ilustração de alocação automática](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Como o [!UICONTROL Alocação automática] fornecer resultados mais rápidos?

A vantagem é clara: mais visitantes veem as variações com melhor desempenho. E à medida que uma única variação se antecipa, ainda mais visitantes são desviados para aquela experiência vencedora, enquanto o teste ainda estava em execução. Esse método é especialmente útil se a atividade A/B que está sendo executada estiver acontecendo durante um momento comercial principal, como um feriado, lançamento de produto ou evento de notícias mundiais.

## Como pode [!UICONTROL Alocação automática] fornecer maior receita?

[!UICONTROL Alocação automática] O encontra o vencedor mais rapidamente do que uma divisão A/B manual e também permite explorá-lo imediatamente, capturando receita adicional que teria sido perdida em uma abordagem tradicional ou manual. Porque [!UICONTROL Alocação automática] O direciona mais tráfego para a experiência com a taxa de conversão mais alta; portanto, pode aumentar sua receita enquanto a atividade é executada e aprendida.

No exemplo a seguir, [!UICONTROL Alocação automática] A obteve mais receita durante o teste enviando mais tráfego (40%) para a Experiência D, que tinha a taxa de conversão mais alta.

![A alocação automática fornece uma ilustração de receita mais alta](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Em que casos devo me manter com a alocação manual de tráfego?

Quando você precisa classificar a forma como cada experiência foi executada em relação às outras, um teste A/B manual é mais aplicável. [!UICONTROL Alocação automática] O encontra e explora os melhores desempenhos, mas não garante a diferenciação entre as experiências de menor desempenho. Use a alocação manual de tráfego para obter controle completo de quanto do tráfego de visitantes vê cada variante de teste e para personalizar os limites estatísticos relevantes para sua empresa.

## Introdução

Pronto para iniciar o primeiro [!UICONTROL Alocação automática] atividade? [Saiba mais aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
