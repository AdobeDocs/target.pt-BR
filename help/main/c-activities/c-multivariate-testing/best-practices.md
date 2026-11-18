---
keywords: mvt, teste multivariado, práticas recomendadas para o teste multivariado, práticas recomendadas para mvt, combinações mvt, relatórios mvt
description: Saiba como melhorar o desempenho, evitar problemas e corrigir problemas conhecidos que podem ocorrer ao criar e executar atividades de [!UICONTROL Teste Multivariado] no [!DNL Adobe Target].
title: Quais são as práticas recomendadas para uma atividade de [!UICONTROL Teste multivariado]?
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
TQID: 'https://experienceleague.adobe.com/nQEf5GZ8-zVZakygPtMAYWk-xoJPdcycFbzCNKTqJ-k'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: b934e7cf-c07f-5a64-924b-3c9da8413e3d
    internal-label: Multivariate Tests
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 0ae6991a6a86854bd64a632070a1fcbe544cc606
workflow-type: tm+mt
source-wordcount: '868'
ht-degree: 30%
---
# [!UICONTROL Práticas recomendadas para o teste multivariado] {#mvt-best-practices}

>[!BEGINSHADEBOX]

**Nesta página:** Aprenda a planejar, criar, analisar e acompanhar uma atividade de **[!UICONTROL Teste multivariado]** para obter resultados confiáveis.

>[!ENDSHADEBOX]

As dicas a seguir ajudam a melhorar o desempenho, evitar problemas e corrigir problemas conhecidos que podem ocorrer ao criar e executar atividades de **[!UICONTROL Teste Multivariado]** (MVT) no [!DNL Adobe Target].

## Planejar {#plan}

* **Use pelo menos três elementos no teste.**

  Se houver menos elementos, execute uma série de testes A/B. Para obter mais informações, consulte [Quando usar o Teste multivariado vs. A/B](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#when-to-use-mvt).

* **Esteja ciente da quantidade de tráfego que você normalmente recebe, incluindo o número de impressões e conversões.**

  O MVT requer tráfego suficiente para gerar resultados úteis, e essas informações ajudam a reduzir a probabilidade de projetar um teste com requisitos que excedem o tráfego do site.

* **Conheça os locais na sua página que provavelmente produzirão resultados significativos.**

  Um banner ou uma imagem herói provavelmente gerará mais conversões do que uma alteração no rodapé. A inclusão de localizações menos influentes no seu teste somente aumenta a quantidade de tráfego e o tempo necessários para testar as localizações de maior destaque na página.

* **Manter os elementos independentes uns dos outros.**

  Por exemplo, não teste o layout e o conteúdo no mesmo teste.

* **Examine o código HTML das páginas que deseja testar.**

  Verifique se os elementos do HTML no site não têm IDs DOM duplicadas. IDs duplicadas podem resultar na entrega do mesmo conteúdo a mais de um local.

* **Prepare antecipadamente suas variações de página.**

  Conheça as diferenças de conteúdo de cada oferta e crie imagens, texto, e ofertas de HTML que você espera usar no teste MVT.

* **Planejar mais tempo para QA.**

  O número de experiências aumenta, portanto, o controle de qualidade leva mais tempo.

## Criar {#create}

* **Não inclua mais combinações do que o necessário para o teste.**

  Cada combinação testada aumenta significativamente a quantidade de tráfego e de tempo necessária para atingir resultados aceitáveis. Por exemplo, se houver três localizações com três ofertas cada, haverá 27 combinações possíveis (3x3x3). Três localizações, com duas delas contendo três ofertas possíveis e uma com duas ofertas, oferecem 18 opções (3x3x2). Os números aumentam de modo substancial a cada localização e oferta adicional.

* **Nomear locais e ofertas.**

  Você pode renomear cada localização e oferta no teste para algo mais útil. A quantidade de ofertas em cada localização aparece no título da localização. Nomes úteis ajudam a identificar as ofertas ao examinar os relatórios.

* **Aproveite os recursos de visualização para evitar combinações indesejáveis de conteúdo.**

  Examine todas as experiências geradas pelo seu teste antes de acioná-lo. Verifique se não há combinações com declarações contraditórias (por exemplo, 20% de desconto e $19 de desconto na mesma experiência) ou designs incompatíveis, como um fundo e uma fonte da mesma cor.

* **Use o [Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md#traffic-estimator) para verificar se o teste foi criado para a quantidade de tráfego que sua página recebe.**

  Certifique-se de que o **[!UICONTROL Avaliador de tráfego]** dê à configuração de teste a luz verde para que você possa obter os resultados desejados.

* **Tornar as alternativas de cada elemento significativamente diferentes entre si.**

  Embora não seja obrigatório, é uma boa prática que cada elemento tenha o mesmo número de alternativas.

## Analisar {#analyze}

* **Use o [Relatório de contribuição de localização](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md)** para monitorar o desempenho de cada localização e oferta.

* **No [Relatório de desempenho da experiência](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), baseie suas decisões nos dados mostrados com o uso dos filtros [!UICONTROL Melhores 5] e [!UICONTROL Piores 5].**

  O filtro **[!UICONTROL Todos]** dificulta a extração das informações desejadas e nem todas as experiências podem ser exibidas no gráfico. Use o filtro **[!UICONTROL Tudo]** se quiser ver uma experiência específica que não seja uma das cinco melhores ou piores.

## Acompanhar {#follow-up}

* Embora [!DNL Target] permita a edição de uma atividade ao vivo, **a edição de uma atividade que esteja em andamento pode redefinir o teste.** Os relatórios podem não reconhecer algumas das alterações. É seguro fazer alterações nas ofertas do HTML somente na biblioteca de ofertas.

  As ações específicas que redefinem nomes de experiência e relatórios incluem:

  * Incluir uma nova localização
  * Excluir uma localização
  * Incluir novas ofertas ou excluir ofertas de um local existente
  * Editar ofertas de rich text
  * Editar ofertas de cor do fundo

* **Se o conjunto de relatórios não carregar quando você editar uma atividade que use métricas baseadas em [!DNL Analytics] (um ponteiro é exibido),** alterne as métricas para [!DNL Target] métricas e alterne novamente para as métricas baseadas em [!DNL Analytics]. Agora, o conjunto de relatórios deve ser carregado.

* **Siga um teste MVT com um ou mais testes A/B** para determinar o melhor conteúdo possível para os resultados desejados. Depois que determinar quais localizações e conteúdo são mais úteis para ajudar a atingir suas metas, você poderá executar um teste A/B para refinar mais os resultados. Por exemplo, quando você souber quais locais são mais importantes, teste duas imagens específicas entre si ou compare o texto ou as cores de uma call to action.
