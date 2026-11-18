---
keywords: teste multivariado;mvt;fatorial completo;mvt ou a/b;multivariado a/b;avaliador de tráfego;quando usar mvt;considerações de mvt;multivariado;fatorial parcial;fatorial parcial;fatorial completo
description: Saiba como usar um [!UICONTROL Teste Multivariado] (MVT) no [!DNL Adobe Target] para comparar combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho.
title: O que é um [!UICONTROL teste multivariado]?
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
TQID: 'https://experienceleague.adobe.com/JKmjIHJuRxAXlhvUOrrmLMVLnJFhA3T4xkahgH-ozHE'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '1382'
ht-degree: 25%
---
# Introdução ao [!UICONTROL Teste multivariado] {#get-started-mvt}

>[!BEGINSHADEBOX]

**Nesta página:** saiba como funciona um **[!UICONTROL Teste multivariado]**, quais termos [!DNL Target] usa, quando usá-lo em vez de um teste A/B e como o teste fatorial parcial reduz os requisitos de tráfego.

>[!ENDSHADEBOX]

Uma atividade de **[!UICONTROL Teste Multivariado]** (MVT) em [!DNL Adobe Target] compara combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico. Também ajuda a identificar qual elemento afeta mais o sucesso da atividade. O teste multivariado ajuda você a descobrir a influência relativa que elementos específicos têm na conversão, em comparação a outros elementos na página, e pode ajudar você a refinar uma combinação de elementos que se mostraram eficazes.

Um **[!UICONTROL Teste multivariado]** oferece duas vantagens em comparação a um teste A/B:

* Ele mostra quais elementos na página têm maior influência na conversão, o que também é conhecido como &quot;efeito principal&quot;. Essas informações são úteis, por exemplo, para ajudá-lo a determinar onde colocar o conteúdo que você deseja que receba mais atenção.
* Ela ajuda a encontrar efeitos compostos entre dois ou mais elementos em uma página, que também é conhecida como &quot;efeito de interação&quot;. Por exemplo, um determinado anúncio pode produzir mais conversas quando combinado com um certo banner ou imagem principal.

[!DNL Target]O usa testes multivariados fatoriais completos para ajudar você a otimizar seu conteúdo. Um teste multivariado fatorial completo examina todas as combinações possíveis de conteúdo com igual probabilidade. Por exemplo, se houver dois elementos de página com três ofertas cada, haverá nove combinações possíveis (3x3). Três elementos, com dois deles contendo três ofertas possíveis e um com duas ofertas, oferecem 18 opções (3x3x2).

Em [!DNL Target], cada combinação é uma experiência. O **[!UICONTROL Teste multivariado]** compara cada experiência para que você possa saber quais combinações são as mais bem-sucedidas. Ao mesmo tempo, o [!DNL Target] coleta e analisa dados para entender como cada local e as ofertas influenciam a métrica de sucesso.

![Combinações de teste multivariado](assets/multivariate.png)

Devido ao número de combinações que podem ser geradas, um **[!UICONTROL Teste multivariado]** requer mais tempo e tráfego do que um teste A/B. A página deve receber tráfego suficiente para produzir resultados significativos estatisticamente para cada experiência. Para obter resultados úteis, entenda a quantidade de tráfego que sua página recebe e teste o número ideal de combinações para a quantidade certa de tempo.

O [Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator) pode ajudar você a projetar um teste que funcione com seu tráfego. Antes de usá-lo, você deve ter boas estatísticas mostrando o número de impressões e conversões que seu site normalmente recebe e considerar seus níveis de tráfego por dia. Quanto mais experiências uma atividade tiver, mais tráfego ela deverá incluir ou mais demorada deverá ser executada. Se a quantidade de tráfego não estiver alta, teste algumas combinações. Caso contrário, a quantidade de tempo necessária para produzir resultados de teste significativos pode ser muito longa para ser útil.

## Terminologia do MVT {#mvt-terminology}

Vários termos são usados de maneiras diferentes em todo o setor. A tabela a seguir define os termos que [!DNL Target] usa quando você configura um teste multivariado.

| Termo | Definição |
|--- |--- |
| Combinação | As variações de conteúdo criadas quando você testa várias opções de conteúdo em diversos locais. Por exemplo, se você estiver testando três locais, cada um com três opções de conteúdo, há 27 combinações possíveis (3x3x3). Um visitante do site vê uma combinação, também chamada de experiência. |
| Conteúdo | O texto ou a imagem que compõe uma variação de teste em uma localização. Em um teste multivariado, várias opções de conteúdo em vários locais são comparadas. Na metodologia MVT, o conteúdo é, às vezes, chamado de *nível*. |
| Elemento | Um elemento DOM que contém variações de conteúdo a serem testadas no teste MVT. Consulte também *Localização*. |
| Localização | Uma área de conteúdo específico em uma página, normalmente, contido por um elemento DOM. Na metodologia MVT, uma localização é, às vezes, chamado de *fator*. Um teste multivariado fatorial completo compara todas as combinações possíveis de ofertas nas localizações. |

## Quando usar [!UICONTROL Teste multivariado] vs. A/B {#when-to-use-mvt}

A tabela a seguir mostra quando usar um **[!UICONTROL Teste multivariado]**, um teste A/B ou ambos juntos para otimizar sua página.

| Situação | O que fazer | Detalhes |
|--- |--- |--- |
| Você tem menos de três elementos para testar. | Execute uma série de testes A/B. | Use um teste MVT quando você tiver pelo menos três elementos para testar. |
| Você deseja otimizar o layout e o conteúdo da página. | Use um teste A/B para otimizar o layout da página, seguido de um teste MVT para determinar o melhor conteúdo em cada elemento na página. | Um teste A/B pode fornecer feedback importante no layout, e os testes MVT são ótimos para testar o conteúdo dentro dos elementos no design da sua página. A execução de um teste A/B no layout antes de testar várias opções de conteúdo ajuda a determinar o melhor layout e o conteúdo mais impactante. |
| O número de experiências diferentes excede cinco e abrange dois ou mais elementos. | Use um teste MVT para determinar qual elemento é o mais importante e acompanhe com um teste A/B mais focado nesse elemento. | O teste MVT mostra quais áreas da página têm maior probabilidade de melhorar a conversão. Esses são os elementos em que um profissional de marketing deve se concentrar. Por exemplo, o teste de MVT pode mostrar que a chamada à ação é o elemento mais importante para atingir suas metas. Você pode executar um teste A/B para refinar ainda mais os resultados, por exemplo, testando duas imagens específicas entre si ou comparando o texto ou as cores de uma call to action. Ao seguir um teste MVT com um ou mais testes A/B, é possível determinar o melhor conteúdo possível para os resultados desejados. |

Para mais considerações, como quantos elementos incluir e como planejar o teste, consulte [Práticas recomendadas para o teste multivariado](/help/main/c-activities/c-multivariate-testing/best-practices.md).

## Teste fatorial parcial {#partial-factorial}

[!DNL Target]O oferece teste multivariado fatorial completo como uma opção de atividade incorporada. Em estatísticas, o &quot;Projeto de experimentos&quot; oferece muitas abordagens, ou projetos, para determinar quais fatores influenciam os resultados. Uma abordagem como essa é o [Método Taguchi](https://en.wikipedia.org/wiki/Taguchi_methods) para testes fatoriais parciais. O Método Taguchi permite que os profissionais de marketing criem um conjunto de suposições que reduzem o número de permutas de experiências que devem ser testadas, o que, por sua vez, diminui os requisitos de tráfego para um teste multivariado. Você pode aplicar esta abordagem em [!DNL Target] usando esta [planilha offline](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx).

Se sua equipe usar outras abordagens de Design de experimentos, você poderá usar a planilha como uma implementação de referência para designs de experimento personalizados.

À medida que você usa a planilha de cálculo, considere as seguintes dicas:

* Escolha os elementos que deseja alterar e o número de versões de cada elemento (3x2, 4x3 e assim por diante).
* Mantenha a numeração consistente. Por exemplo, se o botão for o Elemento 1 e as opções forem Azul, Verde e Amarelo, o botão azul é 1-1, o botão verde é 1-2 e o botão amarelo é 1-3.
* A planilha offline fornece o número apropriado de experiências necessárias (quatro para um 3x2, nove para 4x3 e assim por diante).
* Crie as experiências no fluxo de trabalho A/B com o [Visual Experience Composer (VEC)](/help/main/c-experiences/experiences.md). Você pode usar o código personalizado, editar o HTML, o WYSIWYG ou qualquer combinação.
* Após o término da atividade (com base na calculadora de tamanho de amostra), execute os resultados na planilha para obter os outros detalhes.

## Vídeos de treinamento {#training-videos}

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos nesta página.

### Tipos de atividades (9:03) ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo de visão geral explica os tipos de atividades disponíveis em [!DNL Target]. O teste multivariado é discutido a partir de 04:20. Neste vídeo, você aprenderá a:

* Descreva os tipos de atividades incluídas em [!DNL Adobe Target].
* Selecione o tipo de atividade apropriado para atingir suas metas.
* Descreva o fluxo de trabalho guiado de três etapas que se aplica a todos os tipos de atividade.

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Criando Testes Multivariados (9:25) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo explica como entender, planejar e criar um teste multivariado usando o fluxo de trabalho guiado de três etapas do [!DNL Target]. Neste vídeo, você aprenderá a:

* Definir e projetar um teste multivariado.
* Criar um teste multivariado.

>[!VIDEO](https://video.tv.adobe.com/v/17395)
