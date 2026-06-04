---
keywords: a4t;A4T;Analytics como origem de relatório do Target;analytics for target
description: Saiba como criar atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] no [!DNL Target] que usam o [!DNL Analytics] como fonte de relatórios (A4T).
title: O A4T suporta atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
TQID: https://experienceleague.adobe.com/VVbjMp7jYDyslZ8ubn8ntPufLK8nKGI9k3ZGh1DLWWs
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ceid: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2: id: df62f171-ac37-440f-8f0f-f41a72ebdd34
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eb30f47f-d87a-400f-8f78-63ce7979ff56id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1509
ht-degree: 6%

---

# Suporte do A4T para atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]

A integração [!DNL Adobe Target] para [!DNL Adobe Analytics], conhecida como [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), oferece suporte às atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].

A integração A4T permite:

* Use o recurso de bandit de vários braços do [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) para direcionar tráfego para experiências vencedoras.
* Use o algoritmo de aprendizado de máquina do conjunto de [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para escolher a melhor experiência para cada visitante. O [!UICONTROL Direcionamento automático] escolhe a melhor experiência com base no perfil, comportamento e contexto de cada usuário, tudo isso ao usar uma métrica de meta [!DNL Adobe Analytics] e os recursos avançados de relatório e análise do [!DNL Adobe Analytics].

Verifique se você implementou o [A4T para uso com atividades de Teste A/B e Direcionamento de experiência](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Se você usar `analyticsLogging = client_side`, também deverá passar o valor `sessionId` para [!DNL Analytics]. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} no *Guia do Desenvolvedor do Adobe Target*.

Para começar:

1. Ao [criar uma atividade de [!UICONTROL Teste A/B]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), na página **[!UICONTROL Direcionamento]**, clique no controle **[!UICONTROL Alocação de tráfego]** e escolha o método de alocação de tráfego desejado no painel direito.

   ![Configurações do Método de Alocação de Tráfego](/help/main/c-activities/assets/auto-target.png)

   Os seguintes métodos de alocação de tráfego estão disponíveis:

   * **[!UICONTROL Manual (Padrão)]**: especifique a porcentagem de participantes que deseja visualizar cada experiência. Você pode dividir os percentuais igualmente entre todas as experiências ou especificar percentuais maiores ou menores para cada experiência. O total de experiências deve ser igual a 100%.

   * **[!UICONTROL Alocar automaticamente na melhor experiência]**: a maioria dos participantes da atividade é direcionada automaticamente para experiências de maior desempenho. Alguns visitantes são alocados em todas experiências, para manter a exploração de experiências e reconhecer alterações em tendências de desempenho. Para obter mais informações, consulte [[!UICONTROL Visão geral da Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4).

   * **[!UICONTROL Direcionamento automático para experiências personalizadas]**: [!DNL Target] usa aprendizagem de máquina avançada para personalizar conteúdo e gerar conversões, identificando várias experiências definidas pelo profissional de marketing com desempenho elevado e apresentando a experiência mais personalizada para os visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfil similares. Para obter mais informações, consulte [visão geral do Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md).

   Para obter mais informações e instruções passo a passo, consulte [Criar uma atividade de Alocação automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e [Criar uma atividade de Direcionamento automático](/help/main/c-activities/auto-target/create-auto-target.md).

1. Selecione a **[!UICONTROL Adobe Analytics]** para sua **[!UICONTROL Source de relatórios]** na página **[!UICONTROL Metas e configurações]**, selecione a empresa e o conjunto de relatórios que correspondam à meta de otimização desejada.

   ![Seção de relatório do Source na página Metas e Configurações](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Especifique o servidor de rastreamento e a sandbox.

1. Escolha uma métrica [!UICONTROL Meta primária].

   * Para usar [!DNL Adobe Target] para especificar a meta de otimização, escolha **[!UICONTROL Conversão]**.
   * Escolha **[!UICONTROL Usar uma métrica do Analytics]** e selecione uma métrica de [!DNL Analytics] para usar como meta de otimização. Você pode usar uma métrica de conversão [!DNL Analytics] predefinida ou um evento personalizado [!DNL Analytics].

   Consulte [Métricas de meta compatíveis](#supported) abaixo para obter mais informações.

1. Salve e ative a atividade.

   A [!UICONTROL Alocação automática] usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para a experiência que maximiza sua métrica de meta.

   Ou

   O [!UICONTROL Direcionamento automático] usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para uma melhor experiência personalizada.

1. Use a guia **[!UICONTROL Relatórios]** para exibir os relatórios de atividade de acordo com as métricas [!DNL Adobe Analytics] escolhidas. Clique em **[!UICONTROL Exibir no Analytics]** para detalhar e segmentar ainda mais seus dados de relatórios.

## Métricas de meta compatíveis {#supported}

O [!UICONTROL A4T] para a [!UICONTROL Alocação automática] e o [!UICONTROL Direcionamento automático] permite escolher qualquer um dos seguintes tipos de métrica como sua métrica de meta principal para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

>[!NOTE]
>
>Depois de selecionar [!UICONTROL Usar uma métrica do Analytics], selecione [!UICONTROL Maximizar a taxa de conversão de visitante único] para exibir as [!DNL Adobe Analytics] métricas de conversão disponíveis, e [!UICONTROL Maximizar o valor da métrica por visitante] para explorar [!DNL Adobe Analytics] eventos personalizados.

[!DNL Target] permite escolher métricas baseadas em eventos binomiais ou métricas baseadas em eventos contínuos ao usar o [!UICONTROL A4T] para atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático].

* **Métricas baseadas em eventos binomiais**: um evento binomial ocorre ou não. Os eventos binomiais incluem um clique, uma conversão, uma ordem e assim por diante. Esses tipos de eventos também são por vezes referidos como Bernoulli, binários ou discretos.

* **Métricas baseadas em eventos contínuos**. As métricas contínuas incluem receita, número de produtos solicitados, duração da sessão, número de exibições de página na sessão e assim por diante. Esses tipos de eventos também são às vezes referidos como métricas não binomiais ou não-Bernoulli.

>[!IMPORTANT]
>
>A partir da versão [!DNL Adobe Target Standard/Premium] 22.15.1 (8 e 9 de março de 2023), o [!DNL Target] continuará a oferecer suporte a atividades existentes com as métricas que agora não são compatíveis (listadas nas tabelas a seguir). No entanto, após 9 de setembro de 2023, essas métricas não serão mais compatíveis com as atividades existentes e todas as atividades que usam métricas não compatíveis serão descontinuadas para forçar a migração de atividades existentes para o novo comportamento.

### Impacto nas atividades de [!UICONTROL Alocação automática]

| Nome da métrica | Não é mais compatível com: |
| --- | --- |
| [!UICONTROL averagepagedepth] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL averagetimespentonsite] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL bouncerate] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL rejeições] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL entradas] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL saídas] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL visualizações de página] | Maximizar valor de métrica |
| [!UICONTROL recarregamentos] | Maximizar valor de métrica |
| [!UICONTROL visitantes] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL visitas] | Maximizar valor de métrica |

### Impacto nas atividades de [!UICONTROL Direcionamento automático]

| Nome da métrica | Não é mais compatível com: |
| --- | --- |
| [!UICONTROL cartremovals] | Maximizar valor de métrica |
| [!UICONTROL visualizações de página] | Maximizar valor de métrica |
| [!UICONTROL visitantes] | Taxa de conversão, maximizar valor da métrica |
| [!UICONTROL visitas] | Maximizar valor de métrica |

## Limitações e observações

Algumas limitações e observações se aplicam às atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]. Outras limitações e observações se aplicam a um tipo de atividade ou a outro.

### Alocação automática e Direcionamento automático {#both}

* Ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], você sempre deve exibir relatórios em [!DNL Analytics].
* A fonte de relatórios não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade for ativada.
* Embora as métricas calculadas não sejam compatíveis como métricas de meta principal, geralmente é possível alcançar o resultado desejado selecionando um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;conclusões de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;conclusões de formulário&quot; como a métrica de meta principal. O [!DNL Target] normaliza automaticamente as métricas de conversão por visita para levar em conta a distribuição desigual do tráfego, portanto, não é necessário usar uma métrica calculada para executar a normalização.

### Alocação automática {#aa}

* **Frequência de Treinamento**: [!UICONTROL Alocação automática] modelos continuam a ser treinados a cada hora, como de costume.
* **Modelos de Atribuição**: [!DNL Target] usa o modelo de atribuição padrão [!DNL Adobe Analytics] para as atividades [!UICONTROL  de Alocação Automática] que usam o A4T.
* **Confiança**: a fórmula de confiança usada pelas atividades [!UICONTROL Alocação Automática] é diferente da fórmula mostrada por padrão no painel [!DNL Adobe Analytics] [!UICONTROL A4T]. [Conforme descrito aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), a [!UICONTROL Alocação automática] usa intervalos de confiança mais conservadores do que as atividades [!UICONTROL Teste A/B] comuns. Esses níveis de confiança conservadores compensam avaliações repetidas (picos) nos dados. Como resultado, o relatório padrão em [!DNL Adobe Analytics] mostra intervalos de confiança mais estreitos em comparação aos intervalos que estão sendo usados pelo algoritmo [!UICONTROL Alocação automática]. No entanto, você pode determinar qual experiência é favorecida pelos algoritmos com base na experiência que tem mais visitantes únicos sendo enviados para ela.
* **Status do vencedor**: atualmente, os emblemas [&quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) não estão disponíveis no painel [!UICONTROL A4T] em [!DNL Analysis Workspace]. Essas medalhas também não estarão disponíveis se o mesmo relatório for visualizado em [!DNL Target]. Um selo de &quot;estrela&quot; vencedor mostrado em um relatório [!DNL Target] para uma atividade [!UICONTROL Alocação automática] usando A4T deve ser ignorado. Esta medalha reflete cálculos de confiança regulares, e não os cálculos usados por [!UICONTROL Alocação automática].

### Direcionamento automático {#at}

* Os modelos de [!UICONTROL Direcionamento automático] continuam a ser treinados a cada 24 horas, como de costume. No entanto, os dados do evento de conversão provenientes de [!DNL Analytics] são atrasados em mais seis a 24 horas. Este atraso significa que a distribuição do tráfego por [!DNL Target] rastreia os eventos mais recentes registrados em [!DNL Analytics]. Esse atraso tem o maior efeito nas primeiras 48 horas após uma atividade ser ativada inicialmente. O desempenho da atividade espelha mais detalhadamente o comportamento de conversão [!DNL Analytics] após cinco dias.

  Considere usar a [!UICONTROL Alocação automática] em vez do [!UICONTROL Direcionamento automático] para atividades de curta duração nas quais a maioria do tráfego ocorre nos primeiros cinco dias da vida da atividade.

* Ao usar [!DNL Analytics] como fonte de dados para uma atividade de [!UICONTROL Direcionamento automático], as sessões terminarão após seis horas. As conversões que ocorrem após seis horas não são contadas.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Guia de Ferramentas do Analytics*.

## Tutoriais

Embora os recursos de análise avançada estejam disponíveis no [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algumas modificações no painel [!UICONTROL Analytics for Target] padrão são necessárias para interpretar corretamente as atividades de [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]. Essas modificações são necessárias devido a diferenças entre as atividades de experimentação (A/B manual e [!UICONTROL Alocação automática]) e as atividades de personalização ([!UICONTROL Direcionamento automático]).

### Configurando relatórios do A4T em [!DNL Analysis Workspace] para [!UICONTROL atividades de Alocação automática]

Este tutorial o guiará pelas modificações recomendadas para analisar as atividades de [!UICONTROL Alocação automática] em [!DNL Analysis Workspace].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Alocação automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-allocate-activities.html?lang=pt-BR){target=_blank} em *Tutoriais do Adobe Target*.

### Configurando relatórios do A4T em [!DNL Analysis Workspace] para atividades de [!UICONTROL Direcionamento automático]

Este tutorial o guiará pelas modificações recomendadas para analisar as atividades de [!UICONTROL Direcionamento automático] em [!DNL Analysis Workspace].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=pt-BR){target=_blank} em *Tutoriais do Adobe Target*.


