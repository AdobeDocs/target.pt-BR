---
keywords: AB;A/B;AB...n;comparar experiências;direcionamento;comparar conteúdo;direcionamento automático;alocação automática
description: Explore as atividades do Teste A/B em  [!DNL Target] - [!UICONTROL Manual], [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target].
title: Descubra as Atividades de Teste A/B Disponíveis em  [!DNL Target].
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
source-git-commit: 974746e25724abf0e5edd3884331ec0975e5352e
workflow-type: tm+mt
source-wordcount: '670'
ht-degree: 21%

---

# Visão geral do teste A/B

Uma atividade manual [!UICONTROL A/B Test] (às vezes chamada de teste A/B...N) compara duas ou mais versões do conteúdo do site para ver qual versão é a que melhor eleva suas conversões, vendas ou outras métricas identificadas. Use um teste A/B para comparar mudanças na sua página contra o design padrão da página para determinar qual experiência apresenta os melhores resultados.

>[!TIP]
>
>Além da atividade [!UICONTROL Manual] (Padrão) [!UICONTROL A/B Test] (discutida neste artigo), [!DNL Target] fornece dois tipos adicionais de atividades [!UICONTROL A/B Test]: [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]. Consulte [Tipos de atividades de teste A/B](#types) abaixo para obter mais informações.

Os testes A/B manuais são úteis quando você tem uma hipótese clara de maneiras de melhorar o desempenho da sua página com base em métricas de sucesso ou entrega de conteúdo alternativo.

Os testes A/B manuais são adequados para grandes alterações que podem envolver novos layouts ou tratamentos drasticamente diferentes dos elementos. Se o design do seu teste não se decompor facilmente em elementos de página individuais, você deve executar um teste A/B antes de executar um [teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).

Ao configurar o teste A/B, é possível determinar a porcentagem de visitantes que visualizam cada experiência. Por exemplo, você pode dividir o tráfego uniformemente entre o controle e uma segunda experiência, ou testar uma nova experiência mais arriscada mostrando-a para apenas 5% do público-alvo.

>[!NOTE]
>
>Para obter informações detalhadas sobre como determinar o tamanho ideal da amostra para um teste A/B, consulte [Planejar o teste A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

Quando o número de experiências diferentes exceder cinco e abranger dois ou mais locais, é uma boa ideia considerar um [teste MVT](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) antes de executar seus testes A/B. O teste multivariado mostra quais áreas da página têm maior probabilidade de melhorar a conversão. Essas áreas são os locais nos quais um profissional de marketing deve se concentrar. Por exemplo, o teste MVT pode mostrar que a chamada para a ação é o local mais importante para atender suas metas. Depois de determinar quais locais e conteúdo são mais úteis para ajudá-lo a atingir suas metas, você pode executar um teste A/B para refinar ainda mais os resultados. Por exemplo, testar duas imagens específicas umas contra as outras ou comparar o texto ou as cores de um chamado à ação. Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

## Tipos de atividades de teste A/B {#types}

Além da atividade manual [!UICONTROL A/B Test], [!DNL Target] fornece dois tipos adicionais de atividades [!UICONTROL A/B Testing]: [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target].

| Tipo de atividade | Descrição |
| --- | --- |
| [!UICONTROL Manual A/B Test] | Compara duas ou mais experiências para ver qual melhora mais as conversões durante um período de teste pré-especificado. <P>Esta seção descreve como configurar uma atividade [!UICONTROL A/B Test] manual, mas as etapas para os outros tipos de atividades [!UICONTROL A/B Test] são semelhantes. |
| [!UICONTROL Auto-Allocate] | Identifica um vencedor entre duas ou mais experiências e redireciona tráfego para o vencedor, aumentando conversões enquanto o teste continua a ser executado e aprendendo.<P>Para saber mais sobre os benefícios de usar uma atividade [!UICONTROL Auto-Allocate], consulte [Alocação automática](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) em *Por quanto tempo você deve executar um Teste A/B* e [Visão geral da Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Selo Premium](/help/main/assets/premium.png) [!UICONTROL Auto-Target] | Usa aprendizagem de máquina avançada para personalizar conteúdo e gerar conversões identificando várias experiências de alto desempenho definidas pelo profissional de marketing. A experiência mais personalizada é então apresentada aos visitantes com base no perfil individual do cliente e no comportamento de visitantes semelhantes anteriores.<P>Para obter mais informações, consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Para obter mais informações sobre qual destas [!UICONTROL A/B Test] atividades é a escolha certa para você, consulte o [PDF do Guia de Atividades do Adobe Target](/help/main/c-activities/target-activities-guide.md).

As etapas para criar os três tipos de atividades do [!UICONTROL A/B Test] são semelhantes. Para criar uma atividade [!UICONTROL Auto-Allocate] ou [!UICONTROL Auto-Target]:

1. Comece com [criando uma atividade de Teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md).
1. Ao chegar na página [!UICONTROL Targeting], clique no controle [!UICONTROL Traffic Allocation] e escolha o método de alocação de tráfego desejado no painel direito, conforme mostrado abaixo:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experience]

   ![Configurações do Método de Alocação de Tráfego](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method-new.png)

## Incluir recomendações nas atividades A/B

Você pode incluir recomendações nas atividades [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] (e nas atividades [!UICONTROL Experience Targeting] (XT)). Para obter mais informações, consulte [Recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

Essa funcionalidade exige uma [licença do Target Premium](/help/main/c-intro/intro.md#premium).
