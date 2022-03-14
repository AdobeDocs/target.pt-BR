---
keywords: alocação automática de tráfego, direcionamento, alocação automática, alocação automática
description: Saiba como uma atividade de Alocação automática no Adobe [!DNL Target] identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor.
title: As atividades de alocação automática podem obter resultados mais rápidos e receita mais alta?
feature: Auto-Allocate
exl-id: 104ad88f-044b-4c2f-bdaf-f023fd1787a5
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 2%

---

# A Alocação automática pode fornecer resultados de teste mais rápidos e receita maior do que um teste manual

Com uma atividade A/B manual, você pode estar perdendo conversões porque não pode entregar a experiência vencedora para todo o seu público-alvo até que a atividade seja concluída. Sua distribuição de tráfego permanece fixa mesmo depois que você reconhece que algumas experiências estão superando outras e que a atividade deve executar todo seu curso antes que você possa agir em um vencedor.

## Atribuição automática de tráfego

Se você quiser oferecer uma opção para oferecer a experiência vencedora com mais frequência e anteriormente na atividade, removendo ou reduzindo simultaneamente a configuração e o custo de cálculo da escolha de tamanhos de amostra, níveis de confiança e outros conceitos estatísticos, [!UICONTROL Alocação automática] é sua melhor opção.

## Como a alocação automática funciona?

[!UICONTROL Alocação automática] usa o princípio do multi-armed bandit. Se o termo não é familiar, um bandit com um único braço é um termo coloquial para uma máquina de slot (pense: Las Vegas). Visualize a alocação automática do tráfego como tendo várias máquinas de slot, neste caso, variações de teste e, inicialmente, obtendo todas as alças igualmente. Com o tempo, uma ou mais máquinas, ou variações em testes, podem pagar mais do que outras. Quando isso acontece, um jogador começaria naturalmente a puxar os punhos dos que ganham com mais frequência. Em termos de alocação de tráfego, [!DNL Adobe Target] fornecerá a mais visitantes a experiência ou experiências que estão ganhando mais.

Considere a ilustração a seguir de uma atividade A/B de duas semanas. Com [!UICONTROL Alocação automática], à medida que surge uma experiência vencedora, [!UICONTROL Target] desviar mais do tráfego para o vencedor no início do teste.

![Ilustração de alocação automática](/help/main/c-activities/automated-traffic-allocation/assets/Auto-Allocate-test.png)

## Como a alocação automática me dá resultados mais rápidos?

O lado de cima é bem claro: mais visitantes visualizam as variações que têm melhor desempenho. E à medida que uma única variação avança, ainda mais visitantes são desviados para aquela experiência vencedora, enquanto o teste ainda estava em execução. Isso é especialmente útil se a atividade A/B que está sendo executada estiver acontecendo durante um momento comercial principal, como um feriado, lançamento de produto ou evento de notícias do mundo.

## Como a alocação automática pode me dar maior receita?

[!UICONTROL Alocação automática] O encontra o vencedor mais rapidamente do que uma divisão A/B manual e também permite que você explore o vencedor imediatamente capturando a receita ascendente que teria sido perdida em uma abordagem tradicional ou manual. Porque [!UICONTROL Alocação automática] O direciona mais tráfego para a experiência com a maior taxa de conversão, ele pode aumentar sua receita enquanto a atividade é executada e aprende.

No exemplo a seguir, [!UICONTROL Alocação automática] ganhou mais receita durante o teste, enviando mais tráfego (40%) para a Experiência D, que teve a taxa de conversão mais alta.

![A alocação automática fornece ilustração de receita mais alta](/help/main/c-activities/automated-traffic-allocation/assets/five-experiences.png)

## Em quais casos devo me ater à alocação manual de tráfego?

Quando você precisa classificar o desempenho de cada experiência em relação às outras, um teste A/B manual é mais aplicável. [!UICONTROL Alocação automática] O encontra e explora os melhores desempenhos, mas não garante a diferenciação entre as experiências de desempenho mais baixo. Você deve usar a alocação de tráfego manual para obter controle total sobre quanto do tráfego de visitantes vê cada variante de teste e para personalizar os limites estatísticos relevantes para sua empresa.

## Começar

Pronto para iniciar o primeiro [!UICONTROL Alocação automática] atividade ? [Saiba como aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md).
