---
keywords: alocação automática de tráfego;direcionamento;alocação automática;alocação automática;automated traffic allocation;targeting;autoallocate
description: Saiba como uma atividade de [!UICONTROL Alocação automática] do [!DNL Adobe Target] identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor.
title: As atividades de [!UICONTROL Alocação automática] podem obter resultados mais rápidos e receitas mais altas?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
TQID: https://experienceleague.adobe.com/aSxZ0Zp3cm0x-fVBXHWW4OiXd3Riz-tuhBiw0f8m4lk
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 560
ht-degree: 0%

---

# [!UICONTROL Alocação automática] oferece resultados de teste mais rápidos e receita maior do que um teste manual

Com uma atividade A/B manual, você pode perder conversões, pois não pode entregar a experiência vencedora a todo o público-alvo até que a atividade seja concluída. Sua distribuição de tráfego permanece fixa mesmo depois de reconhecer que algumas experiências estão com desempenho melhor que outras, e a atividade deve executar todo o curso antes de poder agir em um vencedor.

## Alocação automática de tráfego

Se você quiser ter uma opção para distribuir a experiência vencedora com mais frequência e no início da atividade, enquanto remove ou reduz simultaneamente o custo de configuração e cálculo de escolher tamanhos de amostra, níveis de confiança e outros conceitos estatísticos, a [!UICONTROL Alocação automática] é a melhor opção.

## Como a [!UICONTROL Alocação automática] funciona?

[!UICONTROL Alocação automática] usa o princípio do bandit multi-armed. Se o termo não é familiar, um bandido de um braço é um termo coloquial para uma slot machine (pense: Las Vegas). Visualize a alocação automática de tráfego como se tivesse várias máquinas de fenda, neste caso, variações de teste e, a princípio, puxando todas as alças igualmente. Com o tempo, uma ou mais máquinas, ou variações de testes, podem pagar mais do que outras. Quando isso acontece, um apostador naturalmente começa a puxar as alças daqueles que ganham com mais frequência. Em termos de alocação de tráfego, [!DNL Target] serve mais visitantes da experiência ou experiências que estão ganhando mais.

Considere a ilustração a seguir de uma atividade A/B de duas semanas. Com a [!UICONTROL Alocação automática], à medida que uma experiência vencedora surge, o [!UICONTROL Target] desvia mais tráfego para esse vencedor no início do teste.

![Ilustração de alocação automática](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Como a [!UICONTROL Alocação automática] fornece resultados mais rápidos?

A vantagem é clara: mais visitantes veem as variações com melhor desempenho. E à medida que uma única variação se antecipa, ainda mais visitantes são desviados para aquela experiência vencedora, enquanto o teste ainda estava em execução. Esse método é especialmente útil se a atividade A/B que está sendo executada estiver acontecendo durante um momento comercial principal, como um feriado, lançamento de produto ou evento de notícias mundiais.

## Como a [!UICONTROL Alocação automática] pode fornecer receita mais alta?

A [!UICONTROL Alocação automática] encontra o vencedor mais rápido que uma divisão A/B manual e também permite explorar esse vencedor capturando imediatamente uma receita adicional que teria sido perdida em uma abordagem tradicional ou manual. Como a [!UICONTROL Alocação automática] direciona mais tráfego para a experiência com a maior taxa de conversão, ela pode aumentar sua receita enquanto a atividade é executada e aprendida.

No exemplo a seguir, a [!UICONTROL Alocação automática] obteve mais receita durante o teste ao enviar mais tráfego (40%) para a Experiência D, que tinha a maior taxa de conversão.

![A alocação automática fornece uma ilustração de receita mais alta](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Em que casos devo me manter com a alocação manual de tráfego?

Quando você precisa classificar a forma como cada experiência foi executada em relação às outras, um teste A/B manual é mais aplicável. A [!UICONTROL Alocação automática] encontra e explora os executores principais, mas não garante a diferenciação entre as experiências de desempenho inferior. Use a alocação manual de tráfego para obter controle completo de quanto do tráfego de visitantes vê cada variante de teste e para personalizar os limites estatísticos relevantes para sua empresa.

## Introdução

Pronto para iniciar sua primeira atividade de [!UICONTROL Alocação automática]? [Saiba mais aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
