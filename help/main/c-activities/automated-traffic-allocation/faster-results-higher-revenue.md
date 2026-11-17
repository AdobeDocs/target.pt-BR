---
keywords: alocação automática de tráfego;direcionamento;alocação automática;alocação automática;automated traffic allocation;targeting;autoallocate
description: Saiba como uma atividade de [!UICONTROL Alocação automática] em [!DNL Adobe Target] identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor.
title: As atividades de [!UICONTROL Alocação automática] podem obter resultados mais rápidos e receitas mais altas?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
TQID: 'https://experienceleague.adobe.com/aSxZ0Zp3cm0x-fVBXHWW4OiXd3Riz-tuhBiw0f8m4lk'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f2d0aafb-18af-41a0-a32e-2788eafacc2b
    internal-label: Auto-allocate
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 0%
---
# Como a [!UICONTROL Alocação automática] supera o desempenho de um teste manual {#faster-results-higher-revenue}

>[!BEGINSHADEBOX]

**Nesta página:** saiba por que uma atividade de **[!UICONTROL Alocação automática]** pode fornecer resultados mais rápidos e receita maior do que um teste A/B manual, como ela funciona e quando a alocação manual de tráfego continua sendo a melhor opção.

>[!ENDSHADEBOX]

Com uma atividade A/B manual, você pode perder conversões porque não pode fornecer a experiência vencedora a todo o público-alvo até que a atividade seja concluída. Sua distribuição de tráfego permanece fixa mesmo depois de reconhecer que algumas experiências estão com desempenho melhor que outras, e a atividade deve executar todo o curso antes de poder agir em um vencedor.

## Alocação automática de tráfego {#auto-allocating-traffic}

A **[!UICONTROL Alocação automática]** é a melhor opção se você deseja distribuir a experiência vencedora com mais frequência e anteriormente na atividade, além de remover ou reduzir o custo de configuração e cálculo de escolher tamanhos de amostra, níveis de confiança e outros conceitos estatísticos.

## Como a [!UICONTROL Alocação automática] funciona? {#how-it-works}

**[!UICONTROL Alocação automática]** usa o princípio do bandit multi-armed. Um bandido de um braço é um termo coloquial para uma máquina de fenda. Pense na alocação automática de tráfego como um conjunto de máquinas de fenda, neste caso, variações de teste, cujos manipuladores são puxados igualmente no início. Com o tempo, uma ou mais máquinas, ou variações de testes, podem pagar mais do que outras. Quando essa situação acontece, o jogador naturalmente passa a puxar os punhos das máquinas que vencem com mais frequência. Em termos de alocação de tráfego, [!DNL Target] serve mais visitantes da experiência ou experiências que estão ganhando mais.

A ilustração a seguir mostra uma atividade A/B de duas semanas. Com a **[!UICONTROL Alocação automática]**, à medida que uma experiência vencedora surge, [!DNL Target] desvia mais tráfego para esse vencedor no início do teste.

![Ilustração de alocação automática](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Como a [!UICONTROL Alocação automática] fornece resultados mais rápidos? {#faster-results}

Mais visitantes veem as variações com melhor desempenho. À medida que uma única variação avança, ainda mais visitantes são desviados para essa experiência vencedora enquanto o teste ainda está em execução. Esse método é especialmente útil se a atividade A/B for executada durante um momento comercial principal, como um feriado, um lançamento de produto ou um evento de notícias mundial.

## Como a [!UICONTROL Alocação automática] pode fornecer receita mais alta? {#higher-revenue}

A **[!UICONTROL Alocação automática]** encontra o vencedor mais rápido que uma divisão A/B manual e permite que você explore esse vencedor imediatamente, capturando receita adicional que teria sido perdida em uma abordagem tradicional ou manual. A **[!UICONTROL Alocação automática]** direciona mais tráfego para a experiência com a maior taxa de conversão, para que possa aumentar sua receita enquanto a atividade é executada e aprendida.

No exemplo a seguir, a **[!UICONTROL Alocação automática]** obteve mais receita durante o teste ao enviar mais tráfego (40%) para a Experiência D, que tinha a maior taxa de conversão.

![A alocação automática fornece uma ilustração de receita mais alta](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Em que casos devo me manter com a alocação manual de tráfego? {#manual-allocation}

Um teste A/B manual é a opção mais aplicável quando você deve classificar como cada experiência foi executada em relação às outras. A **[!UICONTROL Alocação automática]** encontra e explora os melhores desempenhos, mas não garante a diferenciação entre as experiências de baixo desempenho. Use a alocação manual de tráfego para obter controle completo de quanto do tráfego de visitantes vê cada variante de teste e para personalizar os limites estatísticos relevantes para sua empresa.

## Introdução {#get-started}

Pronto para iniciar sua primeira atividade de **[!UICONTROL Alocação automática]**? Consulte [Criar uma atividade de alocação automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e a [visão geral da alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
