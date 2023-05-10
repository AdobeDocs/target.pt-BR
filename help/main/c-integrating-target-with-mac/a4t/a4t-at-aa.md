---
keywords: a4t; A4T; Analytics como fonte de relatórios para o Target; analytics para target
description: Saiba como criar [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades em [!DNL Target] que [!DNL Analytics] como fonte de geração de relatórios (A4T).
title: Suporte ao A4T [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] Atividades?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 39b4c0363cde97b07265403b680ad4ed899f5a64
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 7%

---

# Compatibilidade do A4T com atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]

O [!DNL Adobe Target]-para-[!DNL Adobe Analytics] integração, conhecida como [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades.

A integração A4T permite:

* Use o [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) recurso multi-armed bandit para direcionar o tráfego para experiências vencedoras.
* Use o [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) agrupe algoritmo de aprendizado de máquina para escolher a melhor experiência para cada visitante. [!UICONTROL Direcionamento automático] escolhe a melhor experiência com base no perfil, no comportamento e no contexto de cada usuário, ao usar um [!DNL Adobe Analytics] métrica de meta e os recursos avançados de relatórios e análise de [!DNL Adobe Analytics].

Certifique-se de que [A4T implementado para uso com atividades de Teste A/B e Direcionamento de experiência](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Se você usar `analyticsLogging = client_side`, você também deve passar o `sessionId` para [!DNL Analytics]. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} no *Guia do desenvolvedor do Adobe Target*.

Para começar:

1. Ao [criar um [!UICONTROL Teste A/B] atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), no **[!UICONTROL Direcionamento]** selecione uma das opções a seguir como **[!UICONTROL Método de alocação de tráfego]**:

   * [!UICONTROL Alocação automática para a melhor experiência]
   * [!UICONTROL Direcionamento automático para experiências personalizadas]

   ![Opções de métodos de alocação de tráfego: Manual, Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obter mais informações e instruções passo a passo, consulte [Criar uma atividade de alocação automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e [Criar uma atividade de Direcionamento automático](/help/main/c-activities/auto-target/create-auto-target.md).

1. Selecionar **[!UICONTROL Adobe Analytics]** para seu **[!UICONTROL Fonte de geração de relatórios]** no **[!UICONTROL Metas e configurações]** e selecione o conjunto de relatórios correspondente à meta de otimização desejada.

   ![Seção Fonte de geração de relatórios na página Metas e configurações](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Escolha um [!UICONTROL Meta principal] métrica.

   * Para usar [!DNL Adobe Target] para especificar a meta de otimização, escolha **[!UICONTROL Conversão]** .
   * Choose **[!UICONTROL Usar uma métrica do Analytics]** e, em seguida, selecione uma métrica de [!DNL Analytics] para uso como meta de otimização. Você pode usar um [!DNL Analytics] métrica de conversão ou uma [!DNL Analytics] evento personalizado.

   Consulte [Métricas de meta compatíveis](#supported) abaixo para obter mais informações.

1. Salve e ative a atividade.

   [!UICONTROL Alocação automática] O usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para a experiência que maximiza sua métrica de meta.

   Ou

   [!UICONTROL Direcionamento automático] O usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para uma melhor experiência personalizada.

1. Use o **[!UICONTROL Relatórios]** para exibir os relatórios da atividade, de acordo com a sua escolha [!DNL Adobe Analytics] métricas. Clique em **[!UICONTROL Exibir no Analytics]** para aprofundar e segmentar seus dados de relatórios.

## Métricas de meta compatíveis {#supported}

[!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] permite escolher qualquer um dos seguintes tipos de métricas como a métrica de meta principal para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

O [!DNL Target] permite escolher métricas baseadas em eventos binomiais ou em eventos contínuos ao usar o [!UICONTROL A4T] para as atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].

* **Métricas baseadas em eventos binômicos**: Um evento binário ocorre ou não. Os eventos binômicos incluem um clique, uma conversão, um pedido e assim por diante. Esse tipo de evento também é às vezes chamado de Bernoulli, binário ou discreto.

* **Métricas baseadas em eventos contínuos**. As métricas contínuas incluem receita, número de produtos solicitados, duração da sessão, número de exibições de página na sessão e assim por diante. Esses tipos de eventos também são, às vezes, chamados de métricas não binômicas ou não-Bernoulli.

>[!IMPORTANT]
>
>Em [!DNL Adobe Target Standard/Premium] Versão 22.15.1 (8 e 9 de março de 2023), [!DNL Target] O continua a suportar atividades existentes com as métricas que agora não são suportadas (listadas nas tabelas a seguir). No entanto, após 9 de setembro de 2023, essas métricas não serão mais suportadas nas atividades existentes e todas as atividades que usam métricas não suportadas serão descontinuadas para forçar a migração de atividades existentes a ter o novo comportamento.

### Impacto para [!UICONTROL Alocação automática] atividades

| Nome da métrica | Não há mais suporte no: |
| --- | --- |
| [!UICONTROL averagepagedepth] | Taxa de conversão, Maximizar valor da métrica |
| [!UICONTROL averagetimespentonsite] | Taxa de conversão, Maximizar valor da métrica |
| [!UICONTROL bouncerate] | Taxa de conversão, Maximizar valor da métrica |
| [!UICONTROL devoluções] | Taxa de conversão, Maximizar valor da métrica |
| [!UICONTROL entradas] | Taxa de conversão, Maximizar valor da métrica |
| [!UICONTROL saídas] | Taxa de conversão, Maximizar valor da métrica |
| [!UICONTROL pageviews] | Maximizar valor da métrica |
| [!UICONTROL recarregamentos] | Maximizar valor da métrica |
| [!UICONTROL visitantes] | Taxa de conversão, Maximizar valor da métrica |
| [!UICONTROL visitas] | Maximizar valor da métrica |

### Impacto para [!UICONTROL Direcionamento automático] atividades

| Nome da métrica | Não há mais suporte no: |
| --- | --- |
| [!UICONTROL remoções] | Maximizar valor da métrica |
| [!UICONTROL pageviews] | Maximizar valor da métrica |
| [!UICONTROL visitantes] | Taxa de conversão, Maximizar valor da métrica |
| [!UICONTROL visitas] | Maximizar valor da métrica |

## Limitações e observações

Algumas limitações e observações se aplicam a [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades. Outras limitações e observações se aplicam a um tipo de atividade ou ao outro.

### Alocação automática e Direcionamento automático {#both}

* Ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], você sempre deve visualizar os relatórios em [!DNL Analytics].
* A origem de relatório não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade é ativada.
* Embora as métricas calculadas não sejam suportadas como métricas de meta primária, geralmente é possível alcançar o resultado pretendido selecionando, em vez disso, um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;preenchimentos de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;preenchimentos de formulário&quot; como a métrica de meta principal. [!DNL Target] normaliza automaticamente as métricas de conversão com base em cada visita para contabilizar a distribuição desigual do tráfego, de modo que não é necessário usar uma métrica calculada para executar a normalização.

### Alocação automática {#aa}

* **Frequência de treinamento**: [!UICONTROL Alocação automática] Os modelos continuam treinando a cada hora, como de costume.
* **Modelos de atribuição**: [!DNL Target] usa a variável [!DNL Adobe Analytics] modelo de atribuição padrão para[!UICONTROL  Alocação automática] atividades que usam o A4T.
* **Confiança**: A fórmula de confiança usada por [!UICONTROL Alocação automática] As atividades do são diferentes da fórmula exibida por padrão no [!DNL Adobe Analytics] [!UICONTROL A4T] painel. [Conforme descrito aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Alocação automática] O usa intervalos de confiança mais conservadores do que o regular [!UICONTROL Teste A/B] atividades. Esses níveis conservadores de confiança compensam avaliações repetidas (picos) nos dados. Como resultado, o relatório padrão em [!DNL Adobe Analytics] mostra intervalos de confiança mais estreitos em comparação aos intervalos usados pelo [!UICONTROL Alocação automática] algoritmo. No entanto, você pode determinar qual experiência é favorecida pelos algoritmos com base na qual a experiência tem mais visitantes únicos sendo enviados para ela.
* **Status do vencedor**: Atualmente, o [Semblemas &quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) não estão disponíveis no [!UICONTROL A4T] no painel [!DNL Analysis Workspace]. Esses selos também não estarão disponíveis se o mesmo relatório for visualizado em [!DNL Target]. Um símbolo de &quot;estrela&quot; vencedora exibido em um [!DNL Target] relatório para um [!UICONTROL Alocação automática] atividade usando A4T deve ser ignorada. Esse selo reflete cálculos de confiança regulares, e não aqueles cálculos usados pelo [!UICONTROL Alocação automática].

### Direcionamento automático {#at}

* [!UICONTROL Direcionamento automático] Os modelos continuam a treinar a cada 24 horas, como de costume. No entanto, os dados do evento de conversão são provenientes de [!DNL Analytics] é atrasada em 6 a 24 horas adicionais. Esse atraso significa a distribuição do tráfego por [!DNL Target] rastreia os eventos mais recentes registrados em [!DNL Analytics]. Esse atraso tem o maior efeito nas primeiras 48 horas após uma atividade ser ativada inicialmente. O desempenho da atividade é mais espelhado [!DNL Analytics] o comportamento de conversão após cinco dias passou.

   Considere usar [!UICONTROL Alocação automática] em vez de [!UICONTROL Direcionamento automático] para atividades de curta duração em que a maior parte do tráfego ocorra nos primeiros cinco dias da vida da atividade.

* Ao usar [!DNL Analytics] como a fonte de dados de um [!UICONTROL Direcionamento automático] , as sessões terminam após seis horas decorrido. Conversões que ocorrem após seis horas não são contadas.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Guia de ferramentas do Analytics*.

## Tutoriais

Embora os recursos de análise avançada estejam disponíveis em [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algumas modificações no padrão [!UICONTROL Analytics para Target] são necessários para interpretar corretamente o painel [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades. Essas modificações são necessárias devido às diferenças entre as atividades de experimentação (manual A/B e [!UICONTROL Alocação automática]) e atividades de personalização ([!UICONTROL Direcionamento automático]).

### Configuração de relatórios do A4T no[!DNL Analysis Workspace]para as atividades de [!UICONTROL Alocação automática]

Este tutorial o orienta pelas modificações recomendadas para analisar [!UICONTROL Alocação automática] atividades em [!DNL Analysis Workspace].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Alocação automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=pt-BR){target=_blank} em *Adobe Target Tutorials*.

### Configuração de relatórios do A4T no [!DNL Analysis Workspace] para as atividades de [!UICONTROL Direcionamento automático]

Este tutorial o orienta pelas modificações recomendadas para analisar [!UICONTROL Direcionamento automático] atividades em [!DNL Analysis Workspace].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=pt-BR){target=_blank} em *Adobe Target Tutorials*.


