---
keywords: AB;A/B;AB...n;comparar experiências;direcionamento;comparar conteúdo;direcionamento automático;alocação automática
description: Explore as atividades do Teste A/B em [!DNL Target] - [!UICONTROL Manual], [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].
title: Descubra as atividades de teste A/B disponíveis em [!DNL Target].
feature: A/B Tests
exl-id: e8ff8994-a0a9-4fc7-8fcb-e3a1b7697604
TQID: 'https://experienceleague.adobe.com/wcflYDj0VB7dJODNO6XjFHB0PPIhN4aUrBJxbKPoNdg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ab2570eb-4844-49aa-8334-e91a345525e5
    internal-label: A/B Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: d887712962ad4e3cecd6b3b86ee33a4bcb99f2a8
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 19%
---
# Visão geral do teste A/B {#test-ab}

>[!BEGINSHADEBOX]

**Nesta página:** saiba o que é um teste A/B manual, quando usá-lo em vez de um teste multivariado e como ele se relaciona aos tipos de atividades de Alocação automática e Direcionamento automático.

>[!ENDSHADEBOX]

Uma atividade manual de **[!UICONTROL Teste A/B]** (às vezes chamada de teste A/B...N) compara duas ou mais versões do conteúdo do seu site para ver qual versão é a que melhor eleva suas conversões, vendas ou outras métricas identificadas. Use um teste A/B para comparar mudanças na sua página contra o design padrão da página para determinar qual experiência apresenta os melhores resultados.

## Quando usar um teste A/B manual {#when-to-use}

Use um teste A/B manual quando:

* Você tem uma hipótese clara de maneiras de melhorar o desempenho da sua página, com base em métricas de sucesso ou entrega de conteúdo alternativo.
* Você deseja testar grandes alterações, como novos layouts ou tratamentos drasticamente diferentes dos elementos. Se o design do seu teste não se decompor facilmente em elementos de página individuais, você deve executar um teste A/B antes de executar um [teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md).
* Você deseja decidir a porcentagem de visitantes que visualizarão cada experiência. Por exemplo, você pode dividir o tráfego uniformemente entre o controle e uma segunda experiência, ou testar uma nova experiência mais arriscada mostrando-a para apenas 5% do público-alvo.

Para obter informações detalhadas sobre como determinar o tamanho ideal da amostra para um teste A/B, consulte [Planejar o teste A/B](/help/main/c-activities/t-test-ab/sample-size-determination.md).

### Combinar um teste multivariado e testes A/B

Quando o número de experiências diferentes exceder cinco e abranger dois ou mais locais, é uma boa ideia considerar um [teste MVT](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) antes de executar seus testes A/B:

1. **Execute um teste multivariado** para ver quais áreas da página têm maior probabilidade de melhorar a conversão. Essas áreas são os locais nos quais um profissional de marketing deve se concentrar. Por exemplo, o teste MVT pode mostrar que a chamada para a ação é o local mais importante para atender suas metas.

1. **Execute um ou mais testes A/B** nesses locais para refinar ainda mais os resultados. Por exemplo, testar duas imagens específicas umas contra as outras ou comparar o texto ou as cores de uma call to action.

Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

## Tipos de atividades de teste A/B {#types}

Além da atividade manual **[!UICONTROL Teste A/B]**, [!DNL Target] fornece dois tipos adicionais de atividades de **[!UICONTROL Teste A/B]**: **[!UICONTROL Alocação automática]** e **[!UICONTROL Direcionamento automático]**.

| Tipo de atividade | Descrição |
| --- | --- |
| **[!UICONTROL Teste A/B manual]** | Compara duas ou mais experiências para ver qual melhora mais as conversões durante um período de teste pré-especificado.<P>Esta seção descreve como configurar uma atividade manual de **[!UICONTROL Teste A/B]**, mas as etapas para os outros tipos de atividades de **[!UICONTROL Teste A/B]** são semelhantes. |
| **[!UICONTROL Alocação automática]** | Identifica um vencedor entre duas ou mais experiências e redireciona tráfego para o vencedor, aumentando conversões enquanto o teste continua a ser executado e aprendendo.<P>Para saber mais sobre os benefícios de usar uma atividade de **[!UICONTROL Alocação automática]**, consulte [Alocação automática](/help/main/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) em *Por quanto tempo você deve executar um Teste A/B* e [Visão geral da Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| ![Selo Premium](/help/main/assets/premium.png) **[!UICONTROL Direcionamento automático]** | Usa aprendizagem de máquina avançada para personalizar conteúdo e gerar conversões identificando várias experiências de alto desempenho definidas pelo profissional de marketing. A experiência mais personalizada é então apresentada aos visitantes com base no perfil individual do cliente e no comportamento de visitantes semelhantes anteriores.<P>Para obter mais informações, consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md). |

Para obter mais informações sobre qual dessas **[!UICONTROL atividades de Teste A/B]** é a escolha certa para você, consulte o [Guia de Atividades do Adobe Target PDF](/help/main/c-activities/target-activities-guide.md).

>[!NOTE]
>
>Você pode incluir recomendações nas atividades de **[!UICONTROL Teste A/B]**, **[!UICONTROL Alocação automática]** e **[!UICONTROL Direcionamento automático]** (e **[!UICONTROL Direcionamento de experiência]** (XT)). Para obter mais informações, consulte [Recomendações como oferta](/help/main/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/main/c-intro/intro.md#premium).
