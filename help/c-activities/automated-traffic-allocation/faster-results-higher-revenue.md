---
keywords: alocação de tráfego automatizada;definição de metas;autoalocação;alocação automática
description: A atividade de Autoalocação no Adobe Target identifica um vencedor entre duas ou mais experiências e aloca automaticamente mais tráfego para o vencedor para aumentar as conversões enquanto o teste continua em execução e aprende.
title: A autoalocação pode fornecer resultados de teste mais rápidos e receita mais alta do que um teste manual
feature: Auto-Allocate
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 0%

---


# A Autoalocação pode fornecer resultados de teste mais rápidos e maior receita do que um teste manual

Com uma atividade A/B manual, você pode estar perdendo conversões porque não é possível entregar a experiência vencedora para toda a sua audiência até que a atividade seja concluída. Sua distribuição de tráfego permanece fixa mesmo depois que você reconhece que algumas experiências estão superando outras, e a atividade deve executar todo o curso antes que você possa agir em um vencedor.

## Autoalocação de tráfego

Se você quiser que uma opção sirva a experiência vencedora com mais frequência e mais cedo na atividade, ao mesmo tempo que remove ou reduz a configuração e o custo de cálculo da coleta de tamanhos de amostra, níveis de confiança e outros conceitos estatísticos, [!UICONTROL Autoalocar] é sua melhor opção.

## Como a Autoalocação funciona?

[!UICONTROL A autoalocação ] usa o princípio do multi-armed bandit. Se o termo não é familiar, um bandido com um único braço é um termo coloquial para uma slot machine (pense: Las Vegas). Visualize a alocação automática do tráfego como tendo várias máquinas de slot, neste caso, variações de teste e, primeiramente, puxando todas as alças igualmente. Com o tempo, uma ou mais máquinas, ou variações de teste, podem pagar mais do que outras. Quando isso acontece, um jogador naturalmente start puxando os punhos dos que ganham com mais frequência. Em termos de alocação de tráfego, [!DNL Adobe Target] servirá a mais visitantes a experiência ou experiências que estão ganhando mais.

Considere a ilustração a seguir de uma atividade A/B de duas semanas. Com [!UICONTROL Autoalocar], quando uma experiência vencedora emerge, [!UICONTROL o Público alvo] direciona mais tráfego para o vencedor no início do teste.

![Autoalocar ilustração](/help/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Como a Autoalocação me dá resultados mais rápidos?

O lado positivo é bastante claro: mais visitantes veem as variações que têm melhor desempenho. E à medida que uma única variação segue em frente, ainda mais visitantes são desviados para essa experiência vencedora, enquanto o teste ainda estava em execução. Isso é especialmente útil se a atividade A/B que está sendo executada estiver ocorrendo durante um momento comercial como feriado, lançamento de produtos ou evento de notícias do mundo.

## Como a Autoalocação poderia me dar uma receita maior?

[!UICONTROL A ] alocação automática localiza o vencedor mais rapidamente do que uma divisão A/B manual e também permite que você explore o vencedor imediatamente capturando a receita ascendente que seria perdida em uma abordagem tradicional ou manual. Como a [!UICONTROL Autoalocação] direciona mais tráfego para a experiência com a maior taxa de conversão, ela pode aumentar sua receita enquanto a atividade é executada e aprende.

No exemplo a seguir, [!UICONTROL Autoalocação] ganhou mais receita durante o teste, empurrando mais tráfego (40%) para a Experiência D, que tinha a maior taxa de conversão.

![A autoalocação fornece uma ilustração de receita mais alta](/help/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Em que casos devo me ater à alocação manual de tráfego?

Quando você precisa classificar como cada experiência é realizada em relação às outras, um teste A/B manual é mais aplicável. [!UICONTROL A ] alocação automática localiza e explora os melhores desempenhos, mas não garante a diferenciação entre as experiências de menor desempenho. Você deve usar a alocação de tráfego manual para obter controle total de quanto do tráfego do visitante vê cada variante de teste e para personalizar os limites estatísticos relevantes para a sua empresa.

## Começar

Pronto para iniciar sua primeira atividade [!UICONTROL Autoalocar]? [Saiba como aqui](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).

