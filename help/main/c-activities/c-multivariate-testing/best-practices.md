---
keywords: mvt, teste multivariado, práticas recomendadas para o teste multivariado, práticas recomendadas para mvt, combinações mvt, relatórios mvt
description: Saiba como melhorar o desempenho, evitar problemas e corrigir problemas conhecidos que podem ocorrer ao criar e executar [!UICONTROL Teste multivariado] atividades no [!DNL Adobe Target].
title: Quais são as práticas recomendadas para um [!UICONTROL Teste multivariado] atividade?
feature: Multivariate Tests
exl-id: bcd15517-1b5f-4425-9404-1d7dd0689e28
source-git-commit: 0d73a062f70080057c3323f5150af067e3a2e27e
workflow-type: tm+mt
source-wordcount: '620'
ht-degree: 70%

---

# [!UICONTROL Práticas recomendadas para testes multivariados]

Dicas para ajudar você a melhorar o desempenho, evitar problemas e corrigir problemas conhecidos que podem ocorrer ao criar e executar atividades de [!UICONTROL Teste multivariado] (MVT) no [!DNL Adobe Target].

## Planejar  {#section_4D4A1F6226F042379BF48DB753608579}

* Conheça os locais na sua página que provavelmente produzirão resultados significativos.

  Um banner ou uma imagem herói, por exemplo, provavelmente gerará mais conversões do que uma mudança no rodapé. A inclusão de localizações menos influentes no seu teste somente aumenta a quantidade de tráfego e o tempo necessários para testar as localizações de maior destaque na página.
* Prepare suas variações de página com antecedência.

  Conheça as diferenças de conteúdo de cada oferta e crie imagens, texto, e ofertas de HTML que você espera usar no teste MVT.

## Criar {#section_C59C722CA82E48ABA58A4A7FA758F193}

* Não inclua mais combinações do que o necessário para o teste.

  Cada combinação testada aumenta significativamente a quantidade de tráfego e de tempo necessária para atingir resultados aceitáveis. Por exemplo, se houver três localizações com três ofertas cada, haverá 27 combinações possíveis (3x3x3). Três localizações, com duas delas contendo três ofertas possíveis e uma com duas ofertas, oferecem 18 opções (3x3x2). Os números aumentam de modo substancial a cada localização e oferta adicional.

* Cite localizações e ofertas.

  Você pode renomear cada localização e oferta no teste para algo mais útil. A quantidade de ofertas em cada localização aparece no título da localização. Nomes úteis ajudam a identificar as ofertas ao examinar os relatórios.

* Aproveite os recursos de visualização para evitar combinações indesejadas de conteúdo.

  Examine todas as experiências geradas pelo seu teste antes de acioná-lo. Verifique se não há combinações com declarações contraditórias (por exemplo, 20% de desconto e $19 de desconto na mesma experiência) ou designs incompatíveis, como plano de fundo e fonte da mesma cor.

* Use o [Avaliador de tráfego](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) para garantir que o teste foi criado para a quantidade de tráfego que sua página recebe.

  Certifique-se de que o Avaliador de tráfego dê à configuração de teste a luz verde para que você possa obter os resultados desejados.

* As alternativas de cada elemento devem ser significativamente diferentes entre si.

## Analisar  {#section_9A2118CF1039451681C13D9AE79A58AB}

* Use o [Relatório de contribuição de localização](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) para monitorar o desempenho de cada local e oferta.
* No relatório de [Desempenho da experiência](/help/main/c-reports/multivariate-test-reports/experience-performance-report.md), baseie suas decisões nos dados mostrados com o uso dos filtros 5 melhores e 5 piores.

  O filtro [!UICONTROL Todos] dificulta a extração das informações desejadas e nem todas as experiências podem ser exibidas no gráfico. Use o filtro [!UICONTROL Todas] se quiser ver uma experiência específica que não seja uma das cinco melhores ou piores.

## Acompanhar  {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Embora [!DNL Target] permite editar uma atividade ao vivo, editar uma atividade que esteja em andamento pode redefinir o teste. Os relatórios podem não reconhecer algumas das alterações. É seguro fazer alterações em ofertas HTML somente na biblioteca de ofertas.

  As ações específicas que redefinem nomes de experiência e relatórios incluem:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de um local existente
   * Editar ofertas de rich text
   * Editar ofertas de cor do fundo

* Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

  Depois que determinar quais localizações e conteúdo são mais úteis para ajudar a atingir suas metas, você poderá executar um teste A/B para refinar mais os resultados. Por exemplo, quando você souber quais locais são mais importantes, teste duas imagens específicas entre si ou compare o texto ou as cores de um chamado para ação.
