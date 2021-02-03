---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: É possível usar o A4T com Público alvo automático e autoalocação de atividades?
title: Suporte A4T para autoalocação e Público alvo automático de Atividades
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '853'
ht-degree: 2%

---


# Suporte A4T para autoalocação e Público alvo automático de atividades

A integração [!DNL Adobe Target]-to-[!DNL Adobe Analytics], conhecida como [Analytics para Público alvo](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T) suporta [!UICONTROL Autoalocar] e [!UICONTROL Público alvo automático] atividades.

A integração A4T permite:

* Use o recurso de [Autoalocar](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) bandit multiarmed para direcionar o tráfego para experiências vencedoras.
* Use o algoritmo de aprendizado de máquina montado de [Público alvo automático](/help/c-activities/auto-target/auto-target-to-optimize.md) para escolher uma melhor experiência para cada visitante com base em seu perfil, comportamento e contexto, tudo isso usando uma métrica de [!DNL Adobe Analytics] objetivo e recursos ricos de relatórios e análise [!DNL Adobe Analytics].

Certifique-se de que [implementou A4T para uso com atividades de teste A/B e direcionamento de experiência](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Se você estiver usando `analyticsLogging = client_side`, também será necessário passar o valor `sessionId` para [!DNL Analytics]. Para obter mais informações, consulte [relatórios do Analytics for Público alvo (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) no guia *SDKs do Adobe Target*.

Para começar:

1. Ao criar uma atividade de teste A/B, na página **[!UICONTROL Definição de metas]**, selecione uma das seguintes opções como **[!UICONTROL Método de alocação de tráfego]**:

   * [!UICONTROL Autoalocar para a melhor experiência]
   * [!UICONTROL Público alvo automático para experiências personalizadas]

   ![Opções de métodos de alocação de tráfego: Manual, Autoalocação e Público alvo automático](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obter mais informações e instruções passo a passo, consulte [Criar uma atividade de Autoalocação](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e [Criar uma atividade de Público alvo Automático](/help/c-activities/auto-target/create-auto-target.md).

1. Selecione **[!UICONTROL Adobe Analytics]** para a sua **[!UICONTROL Origem do Relatórios]** na página **[!UICONTROL Metas e Definições]** e selecione o conjunto de relatórios correspondente à sua meta de otimização desejada.

   ![seção Origem do relatórios na página Metas e configurações](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Escolha uma métrica de Objetivo principal.

   * Escolha **[!UICONTROL Conversão]** para usar [!DNL Adobe Target] para especificar a meta de otimização.
   * Escolha **[!UICONTROL Use uma métrica do Analytics]** e selecione uma métrica de [!DNL Analytics] para usar como objetivo de otimização. Você pode usar uma métrica de conversão [!DNL Analytics] predefinida ou um evento personalizado [!DNL Analytics].

   Consulte [Métricas de objetivo suportadas](#supported) abaixo para obter mais informações.

1. Salve e ative sua atividade.

   [!UICONTROL A ] alocação automática usará sua métrica selecionada para otimizar a atividade, direcionando os visitantes para a experiência que maximiza sua métrica de objetivo.

   Ou

   [!UICONTROL O Auto-] Target usará sua métrica selecionada para otimizar a atividade, conduzindo visitantes a uma melhor experiência personalizada.

1. Use a guia **[!UICONTROL Relatórios]** para visualização do relatórios de sua atividade por sua escolha de [!DNL Adobe Analytics] métricas. Clique em **[!UICONTROL Visualização no Analytics]** para detalhar e segmentar ainda mais seus dados de relatórios.

## Métricas de meta suportadas {#supported}

[!UICONTROL A4] para  [!UICONTROL autoalocação ] e  [!UICONTROL autodirecionamento, você ] pode escolher qualquer um dos seguintes tipos de métricas como sua principal métrica de meta para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocate and  [!UICONTROL Auto-] Targetexige que você escolha uma métrica baseada em um evento binomial, ou seja, um evento que ocorra ou não, por exemplo, um clique, uma conversão, um pedido etc. Esses tipos de eventos às vezes também são chamados de eventos Bernoulli, binários ou discretos.

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Alocate and  [!UICONTROL Auto-] Targett não suporta otimização para métricas contínuas, como receita, número de produtos solicitados, duração da sessão, número de visualizações de página na sessão etc. Esses tipos de métricas não suportados às vezes também são chamadas de métricas não-binomiais ou não-Bernoulli.

Os seguintes tipos de métricas não são suportados como métricas de objetivo principal:

* [!DNL Adobe Target] métricas de envolvimento e receita
* [!DNL Adobe Analytics] métricas de envolvimento e receita

   Pode ser possível selecionar uma métrica de envolvimento ou de receita [!DNL Analytics] como sua métrica de objetivo principal porque [!DNL Target] não pode identificar e excluir todas as métricas de envolvimento e receita de [!DNL Analytics]. Tenha cuidado para selecionar somente métricas de conversão binomial ou eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

## Limitações e notas

Algumas limitações e observações se aplicam às atividades [!UICONTROL Autoalocar] e [!UICONTROL Público alvo automático]. Outras limitações e observações se aplicam a um tipo de atividade ou outro.

### Autoalocar e Público alvo automático

* A fonte do relatórios não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade é ativada.
* Embora as métricas calculadas não sejam suportadas como métricas de objetivo principal, geralmente é possível alcançar o resultado pretendido selecionando, em vez disso, um evento personalizado como a métrica de objetivo principal. Por exemplo, se você deseja otimizar para uma métrica como &quot;conclusões de formulário por visitante&quot;, selecione um evento personalizado que corresponda a &quot;conclusões de formulário&quot; como sua métrica de objetivo principal. [!DNL Target] normaliza automaticamente as métricas de conversão com base em cada visita para contabilizar uma distribuição de tráfego desigual, de modo que não é necessário usar uma métrica calculada para executar a normalização.
* [!DNL Target] usa o modelo de atribuição &quot;Mesmo toque&quot; no recurso  [!UICONTROL Autoalocação ] : Analytics for Público alvo (A4T).

### Alocação automática

* [!UICONTROL A autoalocação ] continua a treinar a cada duas horas, como de costume.

### Direcionamento automático

* [!UICONTROL Os modelos de ] direcionamento automático continuam treinando a cada 24 horas, como de costume. No entanto, os dados do evento de conversão provenientes de [!DNL Analytics] são atrasados em mais 6 a 24 horas. Esse atraso significa que a distribuição do tráfego por [!DNL Target] rastreará os eventos mais recentes registrados em [!DNL Analytics]. Isto tem o maior efeito nas primeiras 48 horas após uma atividade ser inicialmente ativada. O desempenho da atividade refletirá melhor o comportamento de conversão [!DNL Analytics] após cinco dias. Você deve considerar usar [!UICONTROL Autoalocar] em vez de [!UICONTROL Público alvo automático] para atividades de curta duração nas quais a maioria do tráfego ocorre nos primeiros cinco dias de vida da atividade.
* Ao usar [!DNL Analytics] como fonte de dados para uma atividade [!UICONTROL Público alvo automático], as sessões são consideradas como encerradas após seis horas. As conversões que ocorrerem após seis horas não serão contadas.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Guia de ferramentas do Analytics*.
