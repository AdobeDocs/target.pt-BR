---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: Uma atividade manual de teste A/B compara duas ou mais versões do conteúdo do site para ver qual versão melhora melhor suas conversões durante um período de teste pré-especificado.
title: Visão geral do teste A/B
feature: ab
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 38%

---


# Visão geral do teste A/B

Uma atividade manual [!UICONTROL Teste A/B] compara duas ou mais versões do conteúdo do site para ver qual versão melhora melhor suas conversões durante um período de teste pré-especificado.

>[!NOTE]
>
>Além da atividade Manual (Padrão) [!UICONTROL Teste A/B] (discutida nesta seção), [!DNL Target] fornece dois tipos adicionais de atividades [!UICONTROL Teste A/B]: [!UICONTROL Alocar automaticamente] e [!UICONTROL Público alvo automático].
>
>Consulte [Tipos de atividades de teste A/B](#types) abaixo para obter mais informações.

Uma atividade manual [!UICONTROL Teste A/B] (às vezes chamada de teste A/B...N) compara duas ou mais versões do conteúdo do site para ver qual favorece mais suas conversões, vendas ou outras métricas que você identifica. Use um teste A/B para comparar mudanças na sua página contra o design padrão da página para determinar qual experiência apresenta os melhores resultados.

Os testes A/B manuais são especialmente úteis quando você tem uma hipótese clara de maneiras de melhorar o desempenho da página com base em métricas de sucesso ou delivery de conteúdo alternativo.

Os testes A/B manuais são adequados para grandes mudanças que podem envolver novos layouts ou tratamentos drasticamente diferentes dos elementos. Se o seu projeto de teste não for facilmente detalhado em elementos de página individuais, você deve executar um teste A/B antes de um [teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

Ao configurar seu teste A/B, você pode determinar a porcentagem de visitantes que veem cada experiência. Por exemplo, você pode dividir o tráfego igualmente entre o controle e a segunda experiência ou pode testar uma experiência nova, mais arriscada, exibindo-a para apenas 5% do seu público-alvo.

>[!NOTE]
>
>Para obter informações detalhadas sobre como determinar o tamanho ideal da amostra para um teste A/B, consulte [Planejar o teste A/B](/help/c-activities/t-test-ab/sample-size-determination.md).

Quando o número de experiências diferentes é maior que cinco e passa por dois ou mais locais, é uma boa ideia considerar um [teste MVT](/help/c-activities/c-multivariate-testing/multivariate-testing.md) antes de realizar seus testes A/B. O teste multivariado mostra quais áreas da página têm maior probabilidade de melhorar a conversão. Estes são os locais que um profissional de marketing deve se concentrar. Por exemplo, o teste MVT pode mostrar que a chamada para a ação é o local mais importante para atender suas metas. Depois de determinar quais locais e conteúdos são mais úteis para ajudá-lo a atingir suas metas, você poderá executar um teste A/B para refinar ainda mais os resultados, como testar duas imagens específicas entre si ou para comparar o texto ou as cores de uma chamada à ação. Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

## Tipos de atividades de teste A/B {#types}

Além da atividade manual [!UICONTROL A/B Test] (discutida nesta seção), [!DNL Target] fornece dois tipos adicionais de atividades de teste A/B: [!UICONTROL Alocar automaticamente] e [!UICONTROL Público alvo automático].

| Tipo de atividade | Descrição |
| --- | --- |
| [!UICONTROL Teste A/B manual] | Compara duas ou mais experiências para ver qual melhora mais conversões durante um período de teste pré-especificado. <br>Esta seção descreve como configurar um  [!UICONTROL teste A/B manual, mas as etapas para os outros tipos de atividades de teste ]    A/B são semelhantes. |
| [!UICONTROL Alocação automática] | Identifica um vencedor entre duas ou mais experiências e redireciona tráfego para o vencedor, aumentando conversões enquanto o teste continua a ser executado e aprendendo. <br>Para saber mais sobre os benefícios de usar uma atividade de Autoalocação, consulte  [Autoalocação ](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) em  *Quanto tempo você deve executar um* teste A/B e uma visão geral [ de ](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)Autoalocação. |
| ![Público alvo ](/help/assets/premium.png) [!UICONTROL automáticoCrachá Premium] | Usa aprendizagem de máquina avançada para personalizar conteúdo identificando várias experiências de alta performance definidas por profissionais de marketing e depois apresentando a experiência mais personalizada para visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfil similares. <br>Para obter mais informações, consulte Público alvo  [automático](/help/c-activities/auto-target/auto-target-to-optimize.md). |

Para obter mais informações sobre qual dessas atividades [!UICONTROL A/B Test] é a certa para você, consulte o [Adobe Target Atividade Guide PDF](/help/c-activities/target-activities-guide.md) interativo.

As etapas para criar os três tipos de atividades [!UICONTROL A/B Test] são semelhantes. Para criar uma atividade [!UICONTROL Autoalocar] ou [!UICONTROL Público alvo automático], start por [criar uma atividade de teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), mas quando você acessar a página [!UICONTROL Direcionamento], escolha o método de alocação de tráfego desejado, como mostrado abaixo:

* [!UICONTROL Autoalocar para a melhor experiência]
* [!UICONTROL Público alvo automático para experiência personalizada]

![Configurações do Método de Alocação de Tráfego](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Vídeo de treinamento: Tipos de atividade (9:03) ![emblema de visão geral](/help/assets/overview.png)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium].

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)
