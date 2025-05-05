---
keywords: a4t;A4T;Analytics como origem de relatório do Target;analytics for target
description: Saiba como criar atividades de [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] no [!DNL Target] que usam [!DNL Analytics] como fonte de relatórios (A4T).
title: O A4T suporta [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] atividades?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 80e4741f5f501a48b15b718c6c0bf55a86c4d676
workflow-type: tm+mt
source-wordcount: '1146'
ht-degree: 1%

---

# Suporte do A4T para atividades de [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]

A integração [!DNL Adobe Target] para [!DNL Adobe Analytics], conhecida como [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), dá suporte a atividades [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target].

A integração A4T permite:

* Use o recurso de bandit de vários braços do [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para direcionar tráfego para experiências vencedoras.
* Use o algoritmo de aprendizado de máquina do conjunto de [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para escolher a melhor experiência para cada visitante. O [!UICONTROL Auto-Target] escolhe a melhor experiência com base no perfil, comportamento e contexto de cada usuário, tudo isso usando uma métrica de meta [!DNL Adobe Analytics] e os recursos avançados de relatório e análise do [!DNL Adobe Analytics].

Verifique se você implementou o [A4T para uso com atividades de Teste A/B e Direcionamento de experiência](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Se você usar `analyticsLogging = client_side`, também deverá passar o valor `sessionId` para [!DNL Analytics]. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} no *Guia do Desenvolvedor do Adobe Target*.

Para começar:

1. Ao [criar uma atividade [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), na página **[!UICONTROL Targeting]**, selecione uma das seguintes opções como **[!UICONTROL Traffic Allocation Method]**:

   * [!UICONTROL Auto-Allocate to best experience]
   * [!UICONTROL Auto-Target for personalized experiences]

   ![Opções de Métodos de Alocação de Tráfego: Manual, Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obter mais informações e instruções passo a passo, consulte [Criar uma atividade de Alocação automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e [Criar uma atividade de Direcionamento automático](/help/main/c-activities/auto-target/create-auto-target.md).

1. Selecione **[!UICONTROL Adobe Analytics]** para **[!UICONTROL Reporting Source]** na página **[!UICONTROL Goals & Settings]** e selecione o conjunto de relatórios correspondente à meta de otimização desejada.

   ![Seção de relatório do Source na página Metas e Configurações](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Escolha uma métrica [!UICONTROL Primary Goal].

   * Para usar [!DNL Adobe Target] para especificar a meta de otimização, escolha **[!UICONTROL Conversion]** .
   * Escolha **[!UICONTROL Use an Analytics metric]** e selecione uma métrica de [!DNL Analytics] para usar como meta de otimização. Você pode usar uma métrica de conversão [!DNL Analytics] predefinida ou um evento personalizado [!DNL Analytics].

   Consulte [Métricas de meta compatíveis](#supported) abaixo para obter mais informações.

1. Salve e ative a atividade.

   O [!UICONTROL Auto-Allocate] usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para a experiência que maximiza a métrica de meta.

   Ou

   O [!UICONTROL Auto-Target] usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para uma melhor experiência personalizada.

1. Use a guia **[!UICONTROL Reports]** para exibir os relatórios de atividade escolhendo [!DNL Adobe Analytics] métricas. Clique em **[!UICONTROL View in Analytics]** para detalhar e segmentar ainda mais seus dados de relatório.

## Métricas de meta compatíveis {#supported}

O [!UICONTROL A4T] para [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] permite que você escolha qualquer um dos seguintes tipos de métricas como sua métrica de meta principal para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

>[!NOTE]
>
>Depois de selecionar [!UICONTROL Use an Analytics Metric], selecione [!UICONTROL Maximize Unique Visitor Conversion Rate] para exibir as métricas de conversão [!DNL Adobe Analytics] disponíveis e [!UICONTROL Maximize Metric Value per Visitor] para explorar os eventos personalizados [!DNL Adobe Analytics].

[!DNL Target] permite que você escolha métricas baseadas em eventos binomiais ou métricas baseadas em eventos contínuos ao usar [!UICONTROL A4T] para atividades [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target].

* **Métricas baseadas em eventos binomiais**: um evento binomial ocorre ou não. Os eventos binomiais incluem um clique, uma conversão, uma ordem e assim por diante. Esses tipos de eventos também são por vezes referidos como Bernoulli, binários ou discretos.

* **Métricas baseadas em eventos contínuos**. As métricas contínuas incluem receita, número de produtos solicitados, duração da sessão, número de exibições de página na sessão e assim por diante. Esses tipos de eventos também são às vezes referidos como métricas não binomiais ou não-Bernoulli.

>[!IMPORTANT]
>
>A partir da versão [!DNL Adobe Target Standard/Premium] 22.15.1 (8 e 9 de março de 2023), o [!DNL Target] continuará a oferecer suporte a atividades existentes com as métricas que agora não são compatíveis (listadas nas tabelas a seguir). No entanto, após 9 de setembro de 2023, essas métricas não serão mais compatíveis com as atividades existentes e todas as atividades que usam métricas não compatíveis serão descontinuadas para forçar a migração de atividades existentes para o novo comportamento.

### Impacto em [!UICONTROL Auto-Allocate] atividades

| Nome da métrica | Não é mais compatível com: |
| --- | --- |
| [!UICONTROL averagepagedepth] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL averagetimespentonsite] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL bouncerate] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL bounces] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL entries] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL exits] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL pageviews] | Maximizar valor de métrica |
| [!UICONTROL reloads] | Maximizar valor de métrica |
| [!UICONTROL visitors] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL visits] | Maximizar valor de métrica |

### Impacto em [!UICONTROL Auto-Target] atividades

| Nome da métrica | Não é mais compatível com: |
| --- | --- |
| [!UICONTROL cartremovals] | Maximizar valor de métrica |
| [!UICONTROL pageviews] | Maximizar valor de métrica |
| [!UICONTROL visitors] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL visits] | Maximizar valor de métrica |

## Limitações e observações

Algumas limitações e observações se aplicam às atividades [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]. Outras limitações e observações se aplicam a um tipo de atividade ou a outro.

### Alocação automática e Direcionamento automático {#both}

* Ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!UICONTROL Auto-Allocate] ou [!UICONTROL Auto-Target], você sempre deve exibir relatórios em [!DNL Analytics].
* A fonte de relatórios não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade for ativada.
* Embora as métricas calculadas não sejam compatíveis como métricas de meta principal, geralmente é possível alcançar o resultado desejado selecionando um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;conclusões de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;conclusões de formulário&quot; como a métrica de meta principal. O [!DNL Target] normaliza automaticamente as métricas de conversão por visita para levar em conta a distribuição desigual do tráfego, portanto, não é necessário usar uma métrica calculada para executar a normalização.

### Alocação automática {#aa}

* **Frequência de Treinamento**: [!UICONTROL Auto-Allocate] modelos continuam treinando a cada hora, como de costume.
* **Modelos de Atribuição**: [!DNL Target] usa o modelo de atribuição padrão [!DNL Adobe Analytics] para [!UICONTROL &#x200B; Auto-Allocate] atividades que usam o A4T.
* **Confiança**: a fórmula de confiança usada por [!UICONTROL Auto-Allocate] atividades é diferente da fórmula mostrada por padrão no painel [!DNL Adobe Analytics] [!UICONTROL A4T]. [Conforme descrito aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Auto-Allocate] usa intervalos de confiança mais conservadores do que as atividades [!UICONTROL A/B Test] regulares. Esses níveis de confiança conservadores compensam avaliações repetidas (picos) nos dados. Como resultado, o relatório padrão em [!DNL Adobe Analytics] mostra intervalos de confiança mais estreitos em comparação aos intervalos sendo usados pelo algoritmo [!UICONTROL Auto-Allocate]. No entanto, você pode determinar qual experiência é favorecida pelos algoritmos com base na experiência que tem mais visitantes únicos sendo enviados para ela.
* **Status do vencedor**: atualmente, os emblemas [&quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) não estão disponíveis no painel [!UICONTROL A4T] em [!DNL Analysis Workspace]. Essas medalhas também não estarão disponíveis se o mesmo relatório for visualizado em [!DNL Target]. Um emblema de &quot;estrela&quot; vencedor mostrado em um relatório [!DNL Target] para uma atividade [!UICONTROL Auto-Allocate] usando A4T deve ser ignorado. Este selo reflete cálculos de confiança regulares, e não os cálculos usados por [!UICONTROL Auto-Allocate].

### Direcionamento automático {#at}

* [!UICONTROL Auto-Target] modelos continuam sendo treinados a cada 24 horas, como de costume. No entanto, os dados do evento de conversão provenientes de [!DNL Analytics] são atrasados em mais seis a 24 horas. Este atraso significa que a distribuição do tráfego por [!DNL Target] rastreia os eventos mais recentes registrados em [!DNL Analytics]. Esse atraso tem o maior efeito nas primeiras 48 horas após uma atividade ser ativada inicialmente. O desempenho da atividade espelha mais detalhadamente o comportamento de conversão [!DNL Analytics] após cinco dias.

  Considere usar [!UICONTROL Auto-Allocate] em vez de [!UICONTROL Auto-Target] para atividades de curta duração nas quais a maioria do tráfego ocorre nos primeiros cinco dias da vida da atividade.

* Ao usar [!DNL Analytics] como fonte de dados para uma atividade [!UICONTROL Auto-Target], as sessões terminam após seis horas. As conversões que ocorrem após seis horas não são contadas.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Guia de Ferramentas do Analytics*.

## Tutoriais

Embora os recursos de análise avançada estejam disponíveis no [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algumas modificações no painel [!UICONTROL Analytics for Target] padrão são necessárias para interpretar corretamente as atividades [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]. Essas modificações são necessárias devido a diferenças entre as atividades de experimentação (A/B manual e [!UICONTROL Auto-Allocate]) e as atividades de personalização ([!UICONTROL Auto-Target]).

### Configurando relatórios do A4T em [!DNL Analysis Workspace] para [!UICONTROL Auto-Allocate] atividades

Este tutorial guiará você pelas modificações recomendadas para analisar [!UICONTROL Auto-Allocate] atividades no [!DNL Analysis Workspace].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Alocação automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=pt-BR){target=_blank} em *Tutoriais do Adobe Target*.

### Configurando relatórios do A4T em [!DNL Analysis Workspace] para [!UICONTROL Auto-Target] atividades

Este tutorial guiará você pelas modificações recomendadas para analisar [!UICONTROL Auto-Target] atividades no [!DNL Analysis Workspace].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=pt-BR){target=_blank} em *Tutoriais do Adobe Target*.


