---
keywords: AB;A/B;AB...n;comparar experiências;direcionamento;comparar conteúdo;direcionamento automático;alocação automática
description: Saiba mais sobre os diferentes tipos de atividades de Teste A/B no Adobe [!DNL Target] - Manual, Alocação automática e Direcionamento automático. Escolha aquele que é certo para você.
title: Que tipo de atividades A/B estão disponíveis no Target?
feature: Testes A/B
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '769'
ht-degree: 38%

---

# Visão geral do teste A/B

Uma atividade manual [!UICONTROL Teste A/B] compara duas ou mais versões do conteúdo do site para ver qual versão melhora mais suas conversões durante um período de teste pré-especificado.

>[!NOTE]
>
>Além da atividade Manual (Padrão) [!UICONTROL Teste A/B] (discutida nesta seção), [!DNL Target] fornece dois tipos adicionais de atividades [!UICONTROL Teste A/B]: [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].
>
>Consulte [Tipos de atividades de Teste A/B](#types) abaixo para obter mais informações.

Uma atividade [!UICONTROL Teste A/B] manual (às vezes chamada de teste A/B...N) compara duas ou mais versões do conteúdo do seu site para ver qual eleva mais suas conversões, vendas ou outras métricas identificadas. Use um teste A/B para comparar mudanças na sua página contra o design padrão da página para determinar qual experiência apresenta os melhores resultados.

Testes A/B manuais são particularmente úteis quando você tem uma hipótese clara de maneiras de melhorar o desempenho da página com base em métricas de sucesso ou entrega de conteúdo alternativo.

Os testes A/B manuais são adequados para grandes alterações que podem envolver novos layouts ou tratamentos drasticamente diferentes dos elementos. Se o seu design de teste não for facilmente detalhado em elementos de página individuais, você deve executar um teste A/B antes de um [teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

Ao configurar seu teste A/B, você pode determinar a porcentagem de visitantes que visualizam cada experiência. Por exemplo, você pode dividir o tráfego igualmente entre o controle e a segunda experiência ou pode testar uma experiência nova, mais arriscada, exibindo-a para apenas 5% do seu público-alvo.

>[!NOTE]
>
>Para obter informações detalhadas sobre como determinar o tamanho ideal da amostra para um teste A/B, consulte [Planejar o teste A/B](/help/c-activities/t-test-ab/sample-size-determination.md).

Quando o número de experiências diferentes é maior que cinco e passa por dois ou mais locais, é uma boa ideia considerar um [teste MVT](/help/c-activities/c-multivariate-testing/multivariate-testing.md) antes de realizar seus testes A/B. O teste multivariado mostra quais áreas da página têm maior probabilidade de melhorar a conversão. Estes são os locais que um profissional de marketing deve se concentrar. Por exemplo, o teste MVT pode mostrar que a chamada para a ação é o local mais importante para atender suas metas. Depois de determinar quais locais e conteúdos são mais úteis para ajudá-lo a atingir suas metas, você pode executar um teste A/B para refinar ainda mais os resultados, por exemplo, para testar duas imagens específicas entre si ou para comparar o texto ou as cores de uma chamada para a ação. Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

## Tipos de atividades de Teste A/B {#types}

Além da atividade manual [!UICONTROL Teste A/B] (discutida nesta seção), [!DNL Target] fornece dois tipos adicionais de atividades de Teste A/B: [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].

| Tipo de atividade | Descrição |
| --- | --- |
| [!UICONTROL Teste A/B manual] | Compara duas ou mais experiências para ver qual melhora mais conversões durante um período de teste pré-especificado. <br>Esta seção descreve como configurar um teste  [!UICONTROL A/B manual, mas as etapas para os outros tipos de ] teste   A/B são semelhantes. |
| [!UICONTROL Alocação automática] | Identifica um vencedor entre duas ou mais experiências e redireciona tráfego para o vencedor, aumentando conversões enquanto o teste continua a ser executado e aprendendo. <br>Para saber mais sobre os benefícios de usar uma atividade de Alocação automática, consulte  [Alocação ](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) automática  *Por quanto tempo você deve executar um* teste A/B e uma visão geral da Alocação  [automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Selo Premium ](/help/assets/premium.png) [!UICONTROL Direcionamento automático] | Usa aprendizagem de máquina avançada para personalizar conteúdo identificando várias experiências de alta performance definidas por profissionais de marketing e depois apresentando a experiência mais personalizada para visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfil similares. <br>Para obter mais informações, consulte Direcionamento  [automático](/help/c-activities/auto-target/auto-target-to-optimize.md). |

Para obter mais informações sobre qual dessas atividades [!UICONTROL Teste A/B] é a escolha certa para você, consulte o [Guia de atividades do Adobe Target PDF](/help/c-activities/target-activities-guide.md) interativo.

As etapas para criar os três tipos de atividades [!UICONTROL Teste A/B] são semelhantes. Para criar uma atividade de [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], comece criando uma atividade de Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), mas quando chegar à página [!UICONTROL Direcionamento], escolha o método de alocação de tráfego desejado, conforme mostrado abaixo:[

* [!UICONTROL Alocar automaticamente para a melhor experiência]
* [!UICONTROL Direcionamento automático para experiência personalizada]

![Configurações do Método de Alocação de Tráfego](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Vídeo de treinamento: Tipos de atividade (9:03) ![Selo de visão geral](/help/assets/overview.png)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium].

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)
