---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: Saiba como criar atividades de Alocação automática e Direcionamento automático no Adobe Target que usam o Analytics como fonte de relatórios (A4T).
title: O A4T suporta atividades de alocação automática e direcionamento automático?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4abf975095c5e29eea42d67119a426a3922d8d79
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 3%

---


# Suporte do A4T para atividades de Alocação automática e Direcionamento automático

A integração [!DNL Adobe Target]-to-[!DNL Adobe Analytics], conhecida como [Analytics for Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), suporta as atividades [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].

A integração A4T permite:

* Use o recurso multi-armed bandit de [alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para direcionar o tráfego para experiências vencedoras.
* Use o algoritmo de aprendizado de máquina do conjunto do [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) para escolher uma melhor experiência para cada visitante. O Direcionamento automático escolhe a melhor experiência com base nos perfis, comportamentos e contexto dos usuários ao usar uma métrica de meta [!DNL Adobe Analytics] e recursos de análise e relatórios avançados [!DNL Adobe Analytics].

Certifique-se de ter [implementado o A4T para uso com atividades de Teste A/B e Direcionamento de experiência](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Se você estiver usando `analyticsLogging = client_side`, também deverá passar o valor `sessionId` para [!DNL Analytics]. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) no guia *SDKs do Adobe Target* .

Para começar:

1. Ao criar uma atividade de Teste A/B, na página **[!UICONTROL Direcionamento]**, selecione uma das seguintes opções como **[!UICONTROL Método de alocação de tráfego]**:

   * [!UICONTROL Alocação automática para a melhor experiência]
   * [!UICONTROL Direcionamento automático para experiências personalizadas]

   ![Opções de métodos de alocação de tráfego: Manual, Alocação automática e Direcionamento automático](/help/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obter mais informações e instruções passo a passo, consulte [Criar uma atividade de Alocação automática](/help/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e [Criar uma atividade de Direcionamento automático](/help/c-activities/auto-target/create-auto-target.md).

1. Selecione **[!UICONTROL Adobe Analytics]** para sua **[!UICONTROL Fonte de relatórios]** na página **[!UICONTROL Metas e configurações]** e selecione o conjunto de relatórios correspondente à meta de otimização desejada.

   ![Seção Fonte de geração de relatórios na página Metas e configurações](/help/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Escolha uma métrica de meta primária.

   * Para usar [!DNL Adobe Target] para especificar a meta de otimização, escolha **[!UICONTROL Conversão]** .
   * Escolha **[!UICONTROL Use uma métrica do Analytics]** e selecione uma métrica de [!DNL Analytics] para usar como meta de otimização. Você pode usar uma métrica de conversão [!DNL Analytics] predefinida ou um evento [!DNL Analytics] personalizado.

   Consulte [Métricas de meta compatíveis](#supported) abaixo para obter mais informações.

1. Salve e ative a atividade.

   [!UICONTROL A ] alocação automática usa sua métrica selecionada para otimizar a atividade, direcionando os visitantes para a experiência que maximiza sua métrica de meta.

   Ou

   [!UICONTROL O Direcionamento ] automático usa sua métrica selecionada para otimizar a atividade, levando os visitantes a uma melhor experiência personalizada.

1. Use a guia **[!UICONTROL Reports]** para exibir os relatórios da atividade de acordo com a escolha das métricas [!DNL Adobe Analytics]. Clique em **[!UICONTROL Exibir no Analytics]** para aprofundar e segmentar seus dados de relatórios.

## Métricas de meta compatíveis {#supported}

[!UICONTROL A4] Para Alocação  [!UICONTROL automática e ] Direcionamento   automático, você pode escolher qualquer um dos seguintes tipos de métricas como a principal métrica de meta para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL O A4] para alocação  [!UICONTROL automática e ] direcionamento   automático exige que você escolha uma métrica baseada em um evento binário. Um evento binário ocorre ou não. Os eventos binômicos incluem um clique, uma conversão, um pedido e assim por diante. Esse tipo de evento também é às vezes chamado de Bernoulli, binário ou discreto.

[!UICONTROL O A4] para  [!UICONTROL alocação automática e direcionamento ] automático não suporta otimização para métricas contínuas.   As métricas contínuas incluem receita, número de produtos solicitados, duração da sessão, número de exibições de página na sessão e assim por diante. Esses tipos de métricas não compatíveis também são, às vezes, chamadas de métricas não binômicas ou não Bernoulli.

Os seguintes tipos de métricas não são suportados como métricas de meta primária:

* [!DNL Adobe Target] métricas de envolvimento e receita
* [!DNL Adobe Analytics] métricas de envolvimento e receita

   É possível selecionar um envolvimento [!DNL Analytics] ou métrica de receita como sua métrica de meta principal porque [!DNL Target] não pode identificar e excluir todas as métricas de envolvimento e receita de [!DNL Analytics]. Selecione somente métricas de conversão binomial ou eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

## Limitações e observações

Algumas limitações e observações se aplicam às atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]. Outras limitações e observações se aplicam a um tipo de atividade ou ao outro.

### Alocação automática e direcionamento automático

* A fonte de relatórios não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade é ativada.
* Embora as métricas calculadas não sejam suportadas como métricas de meta primária, geralmente é possível alcançar o resultado pretendido selecionando, em vez disso, um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;preenchimentos de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;preenchimentos de formulário&quot; como a métrica de meta principal. [!DNL Target] normaliza automaticamente as métricas de conversão com base em cada visita para contabilizar a distribuição desigual do tráfego, de modo que não é necessário usar uma métrica calculada para executar a normalização.
* [!DNL Target] O usa o modelo de atribuição &quot;Mesmo toque&quot; no recurso  [!UICONTROL Alocação ] automática: Analytics for Target (A4T).

### Alocação automática

* [!UICONTROL A ] alocação automática continua a treinar a cada duas horas, como de costume.

### Direcionamento automático

* [!UICONTROL Os modelos de ] Direcionamento automático continuam a ser treinados a cada 24 horas, como de costume. No entanto, os dados de evento de conversão provenientes de [!DNL Analytics] são atrasados em mais seis a 24 horas. Esse atraso significa que a distribuição do tráfego por [!DNL Target] rastreia os eventos mais recentes registrados em [!DNL Analytics]. Esse atraso tem o maior efeito nas primeiras 48 horas após uma atividade ser ativada inicialmente. O desempenho da atividade refletirá mais o comportamento de conversão [!DNL Analytics] após cinco dias. Considere usar [!UICONTROL Alocação automática] em vez de [!UICONTROL Direcionamento automático] para atividades de curta duração nas quais a maioria do tráfego ocorre nos primeiros cinco dias da vida da atividade.
* Ao usar [!DNL Analytics] como fonte de dados para uma atividade de [!UICONTROL Direcionamento automático], as sessões terminam após seis horas terem decorrido. Conversões que ocorrem após seis horas não são contadas.

Para obter mais informações, consulte [Attribution models and lookback windows](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Analytics Tools Guide*.
