---
keywords: AB;A/B;AB...n;compare experiences;Targeting;compare content;auto-target;auto-allocate
description: Uma atividade manual de teste A/B compara duas ou mais versões do conteúdo do site para ver qual versão melhora melhor suas conversões durante um período de teste pré-especificado.
title: Visão geral do teste A/B
feature: ab
uuid: 154559cf-58bb-425d-bb2e-4eaf34c89451
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '754'
ht-degree: 38%

---


# Visão geral do teste A/B

A manual [!UICONTROL A/B Test] activity compares two or more versions of your website content to see which version best improves your conversions during a pre-specified test period.

>[!NOTE]
>
>Além da atividade de teste [!UICONTROL A/B Manual (Padrão) (discutida nesta seção),] fornece dois tipos adicionais de atividades de teste [!DNL Target]  A/B: [!UICONTROL Alocar] automaticamente e Público alvo [!UICONTROL automático].
>
>Consulte [Tipos de atividades](#types) de teste A/B abaixo para obter mais informações.

A manual [!UICONTROL A/B Test] activity (sometimes referred to as an A/B...N test) compares two or more versions of your Web site content to see which best lifts your conversions, sales, or other metrics you identify. Use um teste A/B para comparar mudanças na sua página contra o design padrão da página para determinar qual experiência apresenta os melhores resultados.

Os testes A/B manuais são especialmente úteis quando você tem uma hipótese clara de maneiras de melhorar o desempenho da página com base em métricas de sucesso ou delivery de conteúdo alternativo.

Os testes A/B manuais são adequados para grandes mudanças que podem envolver novos layouts ou tratamentos drasticamente diferentes dos elementos. If your test design does not easily break down into individual page elements, you should run an A/B test before a [multivariate test](/help/c-activities/c-multivariate-testing/multivariate-testing.md).

Ao configurar seu teste A/B, você pode determinar a porcentagem de visitantes que veem cada experiência. Por exemplo, você pode dividir o tráfego igualmente entre o controle e a segunda experiência ou pode testar uma experiência nova, mais arriscada, exibindo-a para apenas 5% do seu público-alvo.

>[!NOTE]
>
>Para obter informações detalhadas sobre como determinar o tamanho ideal da amostra para um teste A/B, consulte [Planejar o teste A/B](/help/c-activities/t-test-ab/sample-size-determination.md).

Quando o número de experiências diferentes é maior que cinco e passa por dois ou mais locais, é uma boa ideia considerar um [teste MVT](/help/c-activities/c-multivariate-testing/multivariate-testing.md) antes de realizar seus testes A/B. O teste multivariado mostra quais áreas da página têm maior probabilidade de melhorar a conversão. Estes são os locais que um profissional de marketing deve se concentrar. Por exemplo, o teste MVT pode mostrar que a chamada para a ação é o local mais importante para atender suas metas. Depois de determinar quais locais e conteúdos são mais úteis para ajudá-lo a atingir suas metas, você poderá executar um teste A/B para refinar ainda mais os resultados, como testar duas imagens específicas entre si ou para comparar o texto ou as cores de uma chamada à ação. Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

## Tipos de atividades de teste A/B {#types}

Além da atividade de teste [!UICONTROL A/B manual (discutida nesta seção),] [!DNL Target] são fornecidos dois tipos adicionais de atividades de teste A/B: [!UICONTROL Alocar] automaticamente e Público alvo [!UICONTROL automático].

| Tipo de atividade | Descrição |
| --- | --- |
| [!UICONTROL Teste A/B manual] | Compara duas ou mais experiências para ver qual melhora mais conversões durante um período de teste pré-especificado. <br>Esta seção descreve como configurar uma atividade de teste [!UICONTROL A/B manual, mas as etapas para os outros tipos de atividades de teste]  A/B são semelhantes. |
| [!UICONTROL Alocação automática] | Identifica um vencedor entre duas ou mais experiências e redireciona tráfego para o vencedor, aumentando conversões enquanto o teste continua a ser executado e aprendendo. <br>Para saber mais sobre os benefícios de usar uma atividade de Autoalocação, consulte [Autoalocação](/help/c-activities/t-test-ab/sample-size-determination.md#auto-allocate) em *Quanto tempo você deve executar um Teste* A/B e uma visão geral [de](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)Autoalocação. |
| ![Etiqueta](/help/assets/premium.png) Premium [!UICONTROL Público alvo automático] | Usa aprendizagem de máquina avançada para personalizar conteúdo identificando várias experiências de alta performance definidas por profissionais de marketing e depois apresentando a experiência mais personalizada para visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfil similares. <br>Para obter mais informações, consulte Público alvo [automático](/help/c-activities/auto-target/auto-target-to-optimize.md). |

Para obter mais informações sobre qual dessas atividades de teste [!UICONTROL A/B é a mais adequada para você, consulte o PDF] interativo do Guia do [](/help/c-activities/target-activities-guide.md)Adobe Target Atividade.

As etapas para criar os três tipos de atividades de teste  A/B são semelhantes. Para criar uma atividade de [!UICONTROL Autoalocação] ou de Público alvo  Automático, start [criando uma atividade](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)de Teste A/B, mas ao acessar a página [!UICONTROL Direcionamento] , escolha o método de alocação de tráfego desejado, como mostrado abaixo:

* [!UICONTROL Autoalocar para a melhor experiência]
* [!UICONTROL Público alvo automático para experiência personalizada]

![Configurações do Método de Alocação de Tráfego](/help/c-activities/t-test-ab/t-test-create-ab/assets/traffic-allocation-method.png)

## Vídeo de treinamento: Etiqueta de ![Visão Geral de Tipos de atividades (9:03)](/help/assets/overview.png)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium].

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)
