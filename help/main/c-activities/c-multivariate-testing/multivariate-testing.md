---
keywords: teste multivariado;mvt;fatorial completo;mvt ou a/b;multivariado a/b;avaliador de tráfego;quando usar mvt;considerações de mvt;multivariado;fatorial parcial;fatorial parcial;fatorial completo
description: Saiba como usar um [!UICONTROL Multivariate Test] (MVT) no [!DNL Adobe Target] para comparar combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho.
title: O que é um [!UICONTROL Multivariate Test]?
feature: Multivariate Tests
exl-id: c8b60011-cb3a-4e28-b84f-06910687b14b
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '1438'
ht-degree: 46%

---

# Visão geral das [!UICONTROL Multivariate Test]

Uma atividade do [!UICONTROL Multivariate Test] (MVT) no [!DNL Adobe Target] compara combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico. Uma atividade [!UICONTROL Multivariate Test] também ajuda a identificar qual elemento afeta mais o sucesso da atividade.

O teste multivariado ajuda você a descobrir a influência relativa que elementos específicos têm na conversão, em comparação a outros elementos na página. Testes multivariados também podem ajudar você a refinar uma combinação de elementos que se mostraram eficazes.

Uma vantagem que um [!UICONTROL Multivariate Test] fornece em comparação a um teste A/B é a capacidade de mostrar quais elementos na sua página têm maior influência na conversão. Essa vantagem também é conhecida como &quot;efeito principal&quot;. Essas informações são úteis, por exemplo, para ajudá-lo a determinar onde colocar o conteúdo que você deseja que receba mais atenção.

[!UICONTROL Multivariate Test] atividades também ajudam a encontrar efeitos compostos entre dois ou mais elementos em uma página. Por exemplo, um determinado anúncio pode produzir mais conversas quando combinado com um certo banner ou imagem principal. Isso também é conhecido como &quot;efeito de interação&quot;.

[!DNL Target]O usa testes multivariados fatoriais completos para ajudar você a otimizar seu conteúdo. Um teste multivariado fatorial completo examina todas as combinações possíveis de conteúdo com igual probabilidade. Por exemplo, se houver dois elementos de página com três ofertas cada, haverá nove combinações possíveis (3x3). Três elementos, com dois deles contendo três ofertas possíveis e um com duas ofertas, oferecem 18 opções (3x3x2).

Em [!DNL Target], cada combinação é uma experiência. O [!UICONTROL Multivariate Test] compara cada experiência para que você possa saber quais combinações são as mais bem-sucedidas. Ao mesmo tempo, os dados são coletados e analisados para entender como cada local e as ofertas influenciam a métrica de sucesso.

![imagem multivariada](assets/multivariate.png)

Devido ao número de combinações que podem ser geradas, um [!UICONTROL Multivariate Test] requer mais tempo e tráfego do que um teste A/B. A página deve receber tráfego suficiente para produzir resultados significativos estatisticamente para cada experiência. Para obter resultados úteis, você deve entender a quantidade de tráfego que sua página recebe e testar o número ideal de combinações para a quantidade certa de tempo para obter os resultados necessários.

O [Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) do Target pode ajudar você a projetar um teste que funcione com seu tráfego. Antes de usar o Avaliador de tráfego, você deve ter boas estatísticas que demonstrem o número de impressões e conversas que o site recebe normalmente. Considere seus níveis diários de tráfego. Quanto mais experiências numa atividade, mais tráfego a atividade deve incluir ou mais sua atividade deve ser executada. Se a quantidade de tráfego não estiver alta, você deverá testar algumas combinações; caso contrário, a quantidade de tempo necessária para produzir resultados de teste significativos pode ser muito longa para ser útil.

## Terminologia do MVT {#section_DF475CA7F34B4CFDB7BE7363761D64AE}

Ao configurar um teste multivariado, é útil compreender a terminologia básica.

Há vários termos que são usados de maneiras diferentes no setor. Esta seção define os termos usados pelo [!DNL Target].

**Combinação:** as variações de conteúdo criadas quando você testa várias opções de conteúdo em diversos locais. Por exemplo, se você estiver testando três localizações, cada uma delas com três opções de conteúdo, então, haverá 27 combinações possíveis (3x3x3). Um visitante do site vê uma combinação, também chamada de experiência.

**Conteúdo:** o texto ou a imagem que compõe uma variação de teste em uma localização. Em um teste multivariado, várias opções de conteúdo em vários locais são comparadas. Na metodologia MVT, o conteúdo é, às vezes, chamado de *nível*.

**Elemento:** um elemento DOM que tem variações de conteúdo a serem testadas no teste MVT. Consulte também *Localização*.

**Localização:** uma área de conteúdo específico em uma página, normalmente, contido por um elemento DOM. Na metodologia MVT, uma localização é, às vezes, chamado de *fator*. Um teste multivariado fatorial completo compara todas as combinações possíveis de ofertas nas localizações.

## Quando usar [!UICONTROL Multivariate Test] vs. A/B {#section_3D2B966B6671406C861A1843EA41D28C}

Os testes multivariados podem ser usados junto com testes A/B para otimizar sua página. Estes são alguns exemplos de ocasiões em que talvez você queira usá-los juntos:

* Use um teste A/B para otimizar o layout da página, seguido de um teste MVT para determinar o melhor conteúdo em cada elemento na página.

  Um teste A/B pode gerar um feedback importante no layout, e os testes MVT são ótimos para testar o conteúdo dentro dos elementos no design da sua página. A execução de um teste A/B no layout antes de testar várias opções de conteúdo pode ajudar você a determinar o melhor layout e o conteúdo mais impactante.

* Use um teste MVT para determinar qual elemento é o mais importante e acompanhe com um teste A/B mais focado nesse elemento.

  Quando o número de experiências diferentes exceder cinco e abranger dois ou mais elementos, é uma boa ideia considerar um teste MVT antes de realizar seus testes A/B. O teste MVT mostra quais áreas da página têm maior probabilidade de melhorar a conversão. Esses são os elementos em que um profissional de marketing deve se concentrar. Por exemplo, o teste de MVT pode mostrar que a chamada à ação é o elemento mais importante para atingir suas metas. Depois de determinar quais elementos e conteúdo são mais úteis para ajudá-lo a atingir suas metas, você pode executar um teste A/B para refinar ainda mais os resultados. Por exemplo, você pode testar duas imagens específicas umas contra as outras ou comparar o texto ou as cores de uma call to action. Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

## Considerações {#section_979FE3F398654C1EA1C86E7DBC9A8DAD}

* Use um teste MVT quando você tiver pelo menos três elementos para testar. Se houver menos elementos, execute uma série de testes A/B.
* Selecione os elementos de página que você acha que têm maior impacto nos resultados.
* Não inclua elementos nem locais demais em um teste. Quanto maior o número, maior será a duração do teste.
* Planejar o teste com antecedência. Não edite um teste depois que ele entrar em funcionamento e os dados começarem a ser coletados e analisados.
* Os elementos devem ser independentes uns dos outros.

  Por exemplo, não teste o layout e o conteúdo no mesmo teste.

* Planeje mais tempo para o controle de qualidade devido ao aumento no número de experiências. Você também pode usar testes fatoriais parciais para diminuir a quantidade de tráfego necessária para um teste multivariado. Para obter mais informações, consulte Teste fatorial parcial abaixo:

## Teste fatorial parcial

[!DNL Target]O oferece teste multivariado fatorial completo como uma opção de atividade incorporada. Nas estatísticas,
O &quot;Projeto de experimentos&quot; oferece muitas abordagens, ou projetos, para determinar quais fatores influenciam os resultados. Uma abordagem como essa é o [Método Taguchi](https://en.wikipedia.org/wiki/Taguchi_methods) para testes fatoriais parciais. O Taguchi permite que os profissionais de marketing criem um conjunto de suposições que reduzem o número de permutas de experiências que devem ser testadas e, por sua vez, diminuam os requisitos de tráfego para um teste multivariado. Esta abordagem de funcionalidade e teste pode ser aplicada em [!DNL Target] usando esta [planilha offline](/help/main/assets/MVT-Taguchi-Partial-Factorial-Design-02102017.xlsx).

Se a sua equipe usa outras abordagens de Projeto de Experimentos, você pode usar essa planilha como implementação de referência para projetos experimentais personalizados.

À medida que você usa a planilha de cálculo, considere as seguintes dicas:

* Escolha os elementos que deseja alterar e o número de versões de cada elemento (3x2, 4x3 e assim por diante).
* Mantenha a numeração consistente. Por exemplo, se o botão for o Elemento 1 e as opções forem Azul, Verde e Amarelo, o botão azul é 1-1, o botão verde é 1-2 e o botão amarelo é 1-3.
* A planilha offline fornece o número apropriado de experiências necessárias (quatro para um 3x2, nove para 4x3 e assim por diante).
* Crie as experiências no fluxo de trabalho A/B com o [Visual Experience Composer (VEC)](/help/main/c-experiences/experiences.md). Você pode usar o código personalizado, editar o HTML, o WYSIWYG ou qualquer combinação.
* Após o término da atividade (com base na calculadora de tamanho de amostra), execute os resultados na planilha para obter os outros detalhes.

Para mais considerações e práticas recomendadas, consulte [Práticas recomendadas de teste multivariado](/help/main/c-activities/c-multivariate-testing/best-practices.md#reference_53635817FFB741EF8C4E56CC70688EDD).

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Tipos de atividades (9:03) ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo de visão geral explica os tipos de atividades disponíveis em [!DNL Target]. Teste multivariado discutido a partir de 4:20.

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/31290?captions=por_br)

### Criando Testes Multivariados (9:25) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo explica como entender, planejar e criar um teste multivariado usando o fluxo de trabalho orientado de três etapas do Target.

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/30985?captions=por_br)
