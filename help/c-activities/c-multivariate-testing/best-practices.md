---
keywords: mvt, teste multivariado, práticas recomendadas para o teste multivariado, práticas recomendadas para mvt, combinações mvt, relatórios mvt
description: Saiba como melhorar o desempenho, evitar problemas e corrigir problemas conhecidos que podem ocorrer ao criar e executar atividades de teste multivariado no Adobe Target.
title: Que práticas recomendadas para testes multivariados?
feature: Multivariate Tests
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '627'
ht-degree: 91%

---


# Práticas recomendadas para testes multivariados

Dicas para ajudá-lo a melhorar o desempenho, evitar problemas e corrigir problemas conhecidos que podem ocorrer ao criar e executar [!UICONTROL atividades de Teste Multivariado] (MVT) em [!DNL Adobe Target].

## Planejar   {#section_4D4A1F6226F042379BF48DB753608579}

* Conheça os locais na sua página que provavelmente produzirão resultados significativos.

   Um banner ou uma imagem herói, por exemplo, provavelmente gerará mais conversões do que uma mudança no rodapé. A inclusão de localizações menos influentes no seu teste somente aumenta a quantidade de tráfego e o tempo necessários para testar as localizações de maior destaque na página.
* Prepare suas variações de página com antecedência.

   Conheça as diferenças de conteúdo de cada oferta e crie imagens, texto, e ofertas de HTML que você espera usar no teste MVT.

## Criar {#section_C59C722CA82E48ABA58A4A7FA758F193}

* Não inclua mais combinações do que o necessário para o teste.

   Cada combinação testada aumenta significativamente a quantidade de tráfego e de tempo necessária para atingir resultados aceitáveis. Por exemplo, se houver três localizações com três ofertas cada, haverá 27 combinações possíveis (3x3x3). Três localizações, com duas delas contendo três ofertas possíveis e uma com duas ofertas, oferecem 18 opções (3x3x2). Os números aumentam de modo substancial a cada localização e oferta adicional.

* Cite localizações e ofertas.

   Você pode renomear cada localização e oferta no teste para algo mais útil. A quantidade de ofertas em cada localização aparece no título da localização. Nomes úteis ajudarão a identificar suas ofertas ao examinar relatórios.

* Aproveite os recursos de visualização para evitar combinações indesejadas de conteúdo.

   Examine todas as experiências geradas pelo seu teste antes de acioná-lo. Verifique se não há combinações com reivindicações contraditórias (por exemplo, 20% de desconto e US$ 19 de desconto na mesma experiência) ou designs incompatíveis, como fundo e fonte da mesma cor.

* Use o [Avaliador de tráfego](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/traffic-estimator.md) para garantir que o teste foi criado para a quantidade de tráfego que sua página recebe.

   Verifique se o Avaliador de tráfego aceita a configuração do teste para que você possa obter os resultados que deseja.
* Recomendamos que as alternativas de cada elemento sejam diferentes entre si.

## Analisar   {#section_9A2118CF1039451681C13D9AE79A58AB}

* Use o relatório de [Contribuição da localização](/help/c-reports/location-contribution-report.md) para monitorar o desempenho de cada localização e cada oferta.
* No relatório de [Desempenho da experiência](/help/c-reports/experience-performance-report.md), baseie suas decisões nos dados mostrados com o uso dos filtros 5 melhores e 5 piores.

   O filtro [!UICONTROL Todos] dificulta a extração das informações desejadas e nem todas as experiências podem ser exibidas no gráfico. Use o filtro [!UICONTROL Todas] se quiser ver uma experiência específica que não seja uma das cinco melhores ou piores.

## Acompanhar   {#section_1C44A767F6AB4441A3EAA8AC995F46B0}

* Embora o [!DNL Target] permita a edição de uma atividade ao vivo, tenha em mente que a edição de uma atividade que esteja em andamento pode redefinir o teste. Sendo assim, os relatórios podem não reconhecer algumas das alterações. É seguro fazer alterações em ofertas HTML somente na biblioteca de ofertas.

   As ações específicas que redefinem nomes de experiência e relatórios são:

   * Incluir uma nova localização
   * Excluir uma localização
   * Incluir novas ofertas ou excluir ofertas de um local existente
   * Editar ofertas de rich text
   * Editar ofertas de cor do fundo

* Ao seguir o teste MVT com um ou mais testes A/B, você pode determinar o melhor conteúdo possível para os resultados que deseja.

   Depois que determinar quais localizações e conteúdo são mais úteis para ajudar a atingir suas metas, você poderá executar um teste A/B para refinar mais os resultados. Por exemplo, quando você souber quais localizações são mais importantes, teste duas imagens específicas entre si ou compare o texto ou as cores de uma chamada à ação.

