---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: Saiba como criar atividades de Alocação automática e Direcionamento automático no Adobe [!DNL Target] que usam o Analytics como fonte de relatórios (A4T).
title: O A4T suporta atividades de alocação automática e direcionamento automático?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1243'
ht-degree: 2%

---

# Suporte do A4T para atividades de Alocação automática e Direcionamento automático

O [!DNL Adobe Target]-para-[!DNL Adobe Analytics] integração, conhecida como [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades.

A integração A4T permite:

* Use [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)Recurso multi-armed bandit da para direcionar o tráfego para experiências vencedoras.
* Use [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)O algoritmo de aprendizado de máquina do conjunto da para escolher a melhor experiência para cada visitante. O Direcionamento automático escolhe a melhor experiência com base nos perfis, comportamentos e contexto dos usuários ao usar um [!DNL Adobe Analytics] métrica de meta e [!DNL Adobe Analytics]recursos avançados de análise e emissão de relatórios.

Certifique-se de que [A4T implementado para uso com atividades de Teste A/B e Direcionamento de experiência](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Se estiver usando `analyticsLogging = client_side`, você também deve passar o `sessionId` para [!DNL Analytics]. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) no *SDKs do Adobe Target* guia.

Para começar:

1. Ao criar uma atividade de Teste A/B, no **[!UICONTROL Direcionamento]** selecione uma das opções a seguir como **[!UICONTROL Método de alocação de tráfego]**:

   * [!UICONTROL Alocação automática para a melhor experiência]
   * [!UICONTROL Direcionamento automático para experiências personalizadas]

   ![Opções de métodos de alocação de tráfego: Manual, Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obter mais informações e instruções passo a passo, consulte [Criar uma atividade de alocação automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e [Criar uma atividade de Direcionamento automático](/help/main/c-activities/auto-target/create-auto-target.md).

1. Selecionar **[!UICONTROL Adobe Analytics]** para seu **[!UICONTROL Fonte de geração de relatórios]** no **[!UICONTROL Metas e configurações]** e selecione o conjunto de relatórios correspondente à meta de otimização desejada.

   ![Seção Fonte de geração de relatórios na página Metas e configurações](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Escolha uma métrica de meta primária.

   * Para usar [!DNL Adobe Target] para especificar a meta de otimização, escolha **[!UICONTROL Conversão]** .
   * Choose **[!UICONTROL Usar uma métrica do Analytics]** e, em seguida, selecione uma métrica de [!DNL Analytics] para uso como meta de otimização. Você pode usar um [!DNL Analytics] métrica de conversão ou uma [!DNL Analytics] evento personalizado.

   Consulte [Métricas de meta compatíveis](#supported) abaixo para obter mais informações.

1. Salve e ative a atividade.

   [!UICONTROL Alocação automática] O usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para a experiência que maximiza sua métrica de meta.

   Ou

   [!UICONTROL Direcionamento automático] O usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para uma melhor experiência personalizada.

1. Use o **[!UICONTROL Relatórios]** para exibir os relatórios da atividade, à sua escolha [!DNL Adobe Analytics] métricas. Clique em **[!UICONTROL Exibir no Analytics]** para aprofundar e segmentar seus dados de relatórios.

## Métricas de meta compatíveis {#supported}

[!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] permite escolher qualquer um dos seguintes tipos de métricas como sua métrica de meta principal para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] exige que você escolha uma métrica baseada em um evento binário. Um evento binário ocorre ou não. Os eventos binômicos incluem um clique, uma conversão, um pedido e assim por diante. Esse tipo de evento também é às vezes chamado de Bernoulli, binário ou discreto.

[!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] não suporta otimização para métricas contínuas. As métricas contínuas incluem receita, número de produtos solicitados, duração da sessão, número de exibições de página na sessão e assim por diante. Esses tipos de métricas não compatíveis também são, às vezes, chamadas de métricas não binômicas ou não Bernoulli.

Os seguintes tipos de métricas não são suportados como métricas de meta primária:

* [!DNL Adobe Target] métricas de envolvimento e receita
* [!DNL Adobe Analytics] métricas de envolvimento e receita

   É possível selecionar uma [!DNL Analytics] envolvimento ou métrica de receita como sua métrica de meta principal porque [!DNL Target] O não pode identificar e excluir todas as métricas de envolvimento e receita do [!DNL Analytics]. Selecione somente métricas de conversão binomial ou eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

## Limitações e observações

Algumas limitações e observações se aplicam a [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades. Outras limitações e observações se aplicam a um tipo de atividade ou ao outro.

### Alocação automática e Direcionamento automático {#both}

* Ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], você sempre deve visualizar os relatórios em [!DNL Analytics].
* A origem de relatório não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou, inversamente, após uma atividade ter sido ativada.
* Embora as métricas calculadas não sejam suportadas como métricas de meta primária, geralmente é possível alcançar o resultado pretendido selecionando, em vez disso, um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;preenchimentos de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;preenchimentos de formulário&quot; como a métrica de meta principal. [!DNL Target] normaliza automaticamente as métricas de conversão com base em cada visita para contabilizar a distribuição desigual do tráfego, de modo que não é necessário usar uma métrica calculada para executar a normalização.
* Ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático] você sempre deve exibir os relatórios em [!DNL Analytics].
* A origem de relatório não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade é ativada.
* Embora as métricas calculadas não sejam suportadas como métricas de meta primária, geralmente é possível alcançar o resultado pretendido selecionando, em vez disso, um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;preenchimentos de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;preenchimentos de formulário&quot; como a métrica de meta principal. [!DNL Target] normaliza automaticamente as métricas de conversão com base no visitante para [!UICONTROL Alocação automática] assim, não é necessário usar uma métrica calculada para executar a normalização.

### Alocação automática {#aa}

* **Frequência de treinamento**: [!UICONTROL Alocação automática] Os modelos continuam treinando a cada hora, como de costume.
* **Modelos de atribuição**: [!DNL Target] usa a variável [!DNL Adobe Analytics] modelo de atribuição padrão para[!UICONTROL  Alocação automática] atividades que usam o A4T.
* **Confiança**: A fórmula de confiança usada por [!UICONTROL Alocação automática] As atividades do são diferentes da fórmula exibida por padrão no [!DNL Adobe Analytics] [!UICONTROL A4T] painel. [Conforme descrito aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Alocação automática] O usa intervalos de confiança mais conservadores do que o regular [!UICONTROL Teste A/B] atividades. Esses níveis conservadores de confiança compensam avaliações repetidas (picos) nos dados. Como resultado, o relatório padrão em [!DNL Adobe Analytics] mostra intervalos de confiança mais estreitos em comparação aos usados pelo [!UICONTROL Alocação automática] algoritmo. No entanto, você pode determinar qual experiência é favorecida pelos algoritmos com base na qual a experiência tem mais visitantes únicos sendo enviados para ela.
* **Status do vencedor**: Atualmente, o [Semblemas &quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) não estão disponíveis no [!UICONTROL A4T] no painel [!DNL Analysis Workspace]. Esses selos também não estarão disponíveis se o mesmo relatório for visualizado em [!DNL Target]. Um símbolo de &quot;estrela&quot; vencedora exibido em um [!DNL Target] relatório para um [!UICONTROL Alocação automática] atividade usando A4T deve ser ignorada. Esse selo reflete cálculos de confiança regulares, e não aqueles usados pelo [!UICONTROL Alocação automática].

### Direcionamento automático {#at}

* [!UICONTROL Direcionamento automático] Os modelos continuam a treinar a cada 24 horas, como de costume. No entanto, os dados do evento de conversão são provenientes de [!DNL Analytics] é atrasada em 6 a 24 horas adicionais. Esse atraso significa a distribuição do tráfego por [!DNL Target] rastreia os eventos mais recentes registrados em [!DNL Analytics]. Esse atraso tem o maior efeito nas primeiras 48 horas após uma atividade ser ativada inicialmente. O desempenho da atividade refletirá mais detalhadamente [!DNL Analytics] o comportamento de conversão após cinco dias passou. Considere usar [!UICONTROL Alocação automática] em vez de [!UICONTROL Direcionamento automático] para atividades de curta duração em que a maior parte do tráfego ocorra nos primeiros cinco dias da vida da atividade.
* Ao usar [!DNL Analytics] como a fonte de dados de um [!UICONTROL Direcionamento automático] , as sessões terminam após seis horas decorrido. Conversões que ocorrem após seis horas não são contadas.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Guia de ferramentas do Analytics*.

## Tutorial: Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático {#tutorial}

Embora os recursos de análise avançada estejam disponíveis em [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algumas modificações no padrão [!UICONTROL Analytics para Target] são necessários para interpretar corretamente as atividades de Direcionamento automático. Essas modificações são necessárias devido às diferenças entre as atividades de experimentação (manual A/B e [!UICONTROL Alocação automática]) e atividades de personalização ([!UICONTROL Direcionamento automático]).

Este tutorial o orienta pelas modificações recomendadas para analisar [!UICONTROL Direcionamento automático] atividades em [!UICONTROL Workspace].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) em *Adobe Target Tutorials*.
