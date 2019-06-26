---
description: Dicas para ajudá-lo a melhorar o desempenho, evitar problemas e corrigir problemas conhecidos que podem ocorrer ao criar e executar atividades de teste multivariado no Adobe Target.
keywords: mvt, teste multivariado, práticas recomendadas para o teste multivariado, práticas recomendadas para mvt, combinações mvt, relatórios mvt
seo-description: Dicas para ajudá-lo a melhorar o desempenho, evitar problemas e corrigir problemas conhecidos que podem ocorrer ao criar e executar atividades de teste multivariado no Adobe Target.
seo-title: Práticas recomendadas de teste multivariado usando o Adobe Target
solution: Target
title: Práticas recomendadas para testes multivariados
topic: Padrão
uuid: 4468a2eb-3fc1-4bc5-85ac-90cc02db4fbb
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Práticas recomendadas para testes multivariados{#multivariate-test-best-practices}

Tips to help you improve performance, avoid issues, and correct known issues that might occur when creating and running Multivariate Test (MVT) activities in [!DNL Adobe Target].

## Planejar {#section_4D4A1F6226F042379BF48DB753608579}

* Conheça os locais na sua página que provavelmente produzirão resultados significativos.

   Por exemplo, um banner ou uma imagem principal provavelmente resultará em mais conversões do que uma alteração no rodapé. A inclusão de localizações menos influentes no seu teste somente aumenta a quantidade de tráfego e o tempo necessários para testar as localizações de maior destaque na página.
* Prepare suas variações de página com antecedência.

   Conheça as diferenças de conteúdo de cada oferta e crie imagens, texto, e ofertas de HTML que você espera usar no teste MVT.

## Criar {#section_C59C722CA82E48ABA58A4A7FA758F193}

* Não inclua mais combinações do que o necessário para o teste.

   Cada combinação testada aumenta significativamente a quantidade de tráfego e de tempo necessária para atingir resultados aceitáveis. Por exemplo, se você tem três localizações com três ofertas cada, há 27 combinações possíveis (3 x 3 x 3). Três localizações, em que dois locais contêm três ofertas possíveis e um local tem duas ofertas, oferecem 18 opções (3 x 3 x 2). Os números aumentam de modo substancial a cada localização e oferta adicional.

* Cite localizações e ofertas.

   Você pode renomear cada localização e oferta no teste para algo mais útil. A quantidade de ofertas em cada localização aparece no título da localização. Nomes úteis ajudarão a identificar suas ofertas ao examinar relatórios.

* Aproveite os recursos de visualização para evitar combinações indesejadas de conteúdo.

   Examine todas as experiências geradas pelo seu teste antes de acioná-lo. Verifique se não há combinações com reivindicações contraditórias (por exemplo, 20% de desconto e US$ 19 de desconto na mesma experiência) ou designs incompatíveis, como fundo e fonte da mesma cor.

* Use the [Traffic Estimator](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) to make sure that your test is designed for the amount of traffic your page receives.

   Verifique se o Avaliador de tráfego aceita a configuração do teste para que você possa obter os resultados que deseja.
* Recomendamos que as alternativas de cada elemento sejam diferentes entre si.

## Analisar {#section_9A2118CF1039451681C13D9AE79A58AB}

* Make frequent use of the [Location Contribution report](/help/c-reports/location-contribution-report.md) to monitor the performance of each location and each offer.
* In the [Experience Performance report](/help/c-reports/experience-performance-report.md), base your decisions on the data shown using the Best 5 and Worst 5 filters.

   [!UICONTROL O] filtro Todos dificulta a extração das informações desejadas, e nem todas as experiências podem ser exibidas no gráfico. Use the [!UICONTROL All] filter if you want to look at a specific experience that is not in the best or worst five.

## Acompanhar {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Although [!DNL Target] allows you to edit a live activity, be aware that editing an activity that is in progress could reset the test. Sendo assim, os relatórios podem não reconhecer algumas das alterações. É seguro fazer alterações em ofertas HTML somente na biblioteca de ofertas.

   As ações específicas que redefinem nomes de experiência e relatórios são:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de um local existente
   * Editar ofertas de rich text
   * Editar ofertas de cor do fundo

* Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

   Depois que determinar quais localizações e conteúdo são mais úteis para ajudar a atingir suas metas, você poderá executar um teste A/B para refinar mais os resultados. Por exemplo, quando você souber quais localizações são mais importantes, teste duas imagens específicas entre si ou compare o texto ou as cores de uma chamada à ação.

