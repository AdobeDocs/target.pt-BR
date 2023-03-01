---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: Saiba como criar atividades de Alocação automática e Direcionamento automático no Adobe [!DNL Target] que usam o Analytics como fonte de relatórios (A4T).
title: O A4T suporta atividades de alocação automática e direcionamento automático?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: 7c15a0795e94b6c6317cb5b4018899be71f03a40
workflow-type: tm+mt
source-wordcount: '1246'
ht-degree: 2%

---

# Suporte do A4T para atividades de Alocação automática e Direcionamento automático

A variável [!DNL Adobe Target]-para-[!DNL Adobe Analytics] integração, conhecida como [Analytics for Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) O (A4T) suporta [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades.

A integração A4T permite:

* Uso [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)O recurso de bandit de vários braços do para direcionar tráfego para experiências vencedoras.
* Uso [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)O reúne o algoritmo de aprendizado de máquina do para escolher uma melhor experiência para cada visitante. O Direcionamento automático escolhe a melhor experiência com base nos perfis, comportamentos e contexto dos usuários ao usar um [!DNL Adobe Analytics] métrica de meta e [!DNL Adobe Analytics]recursos avançados de relatórios e análises.

Verifique se você tem [A4T implementado para uso com atividades de Teste A/B e Direcionamento de experiência](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Se você estiver usando `analyticsLogging = client_side`, você também deve passar o `sessionId` valor para [!DNL Analytics]. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://experienceleague.corp.adobe.com/docs/target-dev/developer/server-side/integration/a4t-reporting.html){target=_blank} no *SDKs do Adobe Target* guia.

Para começar:

1. Ao criar uma atividade de Teste A/B, no **[!UICONTROL Direcionamento]** selecione uma das seguintes opções como a variável **[!UICONTROL Método de alocação de tráfego]**:

   * [!UICONTROL Alocar automaticamente para a melhor experiência]
   * [!UICONTROL Direcionamento automático para experiências personalizadas]

   ![Opções de Métodos de alocação de tráfego: Manual, Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obter mais informações e instruções passo a passo, consulte [Criar uma atividade de alocação automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e [Criar uma atividade de direcionamento automático](/help/main/c-activities/auto-target/create-auto-target.md).

1. Selecionar **[!UICONTROL Adobe Analytics]** para seu **[!UICONTROL Fonte dos relatórios]** no **[!UICONTROL Metas e configurações]** e selecione o conjunto de relatórios correspondente à meta de otimização desejada.

   ![Seção de origem de relatório na página Metas e configurações](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Escolha uma métrica de Meta primária.

   * Para usar [!DNL Adobe Target] para especificar a meta de otimização, escolha **[!UICONTROL Conversão]** .
   * Escolher **[!UICONTROL Usar uma métrica do Analytics]** e selecione uma métrica em [!DNL Analytics] para uso como meta de otimização. Você pode usar um pacote pronto para uso [!DNL Analytics] métrica de conversão ou um [!DNL Analytics] evento personalizado.

   Consulte [Métricas de meta compatíveis](#supported) abaixo para obter mais informações.

1. Salve e ative a atividade.

   [!UICONTROL Alocação automática] O usa a métrica selecionada para otimizar a atividade, impulsionando os visitantes para a experiência que maximiza a métrica de meta.

   Ou

   [!UICONTROL Direcionamento automático] O usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para uma melhor experiência personalizada.

1. Use o **[!UICONTROL Relatórios]** para exibir os relatórios de atividades de acordo com a sua escolha de [!DNL Adobe Analytics] métricas. Clique em **[!UICONTROL Exibir no Analytics]** para detalhar e segmentar ainda mais seus dados de relatórios.

## Métricas de meta compatíveis {#supported}

[!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] O permite escolher qualquer um dos seguintes tipos de métrica como sua métrica de meta principal para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] exige que você escolha uma métrica baseada em um evento binomial. Um evento binomial acontece ou não. Os eventos binomiais incluem um clique, uma conversão, uma ordem e assim por diante. Esses tipos de eventos também são por vezes referidos como Bernoulli, binários ou discretos.

[!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] não suporta otimização para métricas contínuas. As métricas contínuas incluem receita, número de produtos solicitados, duração da sessão, número de exibições de página na sessão e assim por diante. Esses tipos de métricas não suportados às vezes também são chamados de métricas não binomiais ou não Bernoulli.

Os seguintes tipos de métricas não são compatíveis como métricas de meta principal:

* [!DNL Adobe Target] métricas de envolvimento e receita
* [!DNL Adobe Analytics] métricas de envolvimento e receita

   É possível selecionar um [!DNL Analytics] métrica de envolvimento ou receita como sua métrica de meta principal porque [!DNL Target] não é possível identificar e excluir todas as métricas de envolvimento e receita do [!DNL Analytics]. Selecione somente métricas de conversão binomial ou eventos personalizados em [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculada

## Limitações e observações

Algumas limitações e observações se aplicam a [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades. Outras limitações e observações se aplicam a um tipo de atividade ou a outro.

### Alocação automática e Direcionamento automático {#both}

* Ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], você sempre deve exibir relatórios no [!DNL Analytics].
* A fonte de relatórios não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade for ativada.
* Embora as métricas calculadas não sejam compatíveis como métricas de meta principal, geralmente é possível alcançar o resultado desejado selecionando um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;conclusões de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;conclusões de formulário&quot; como a métrica de meta principal. [!DNL Target] normaliza automaticamente as métricas de conversão por visita para levar em conta a distribuição desigual do tráfego, de modo que não é necessário usar uma métrica calculada para executar a normalização.
* Ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático] atividades, você sempre deve exibir relatórios no [!DNL Analytics].
* A fonte de relatórios não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade for ativada.
* Embora as métricas calculadas não sejam compatíveis como métricas de meta principal, geralmente é possível alcançar o resultado desejado selecionando um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;conclusões de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;conclusões de formulário&quot; como a métrica de meta principal. [!DNL Target] normaliza automaticamente as métricas de conversão com base no visitante para [!UICONTROL Alocação automática] atividades, portanto, não é necessário usar uma métrica calculada para executar a normalização.

### Alocação automática {#aa}

* **Frequência de treinamento**: [!UICONTROL Alocação automática] Os modelos continuam a treinar a cada hora, como de costume.
* **Modelos de atribuição**: [!DNL Target] usa o [!DNL Adobe Analytics] modelo de atribuição padrão para[!UICONTROL  Alocação automática] atividades que usam o A4T.
* **Confiança**: A fórmula de confiança usada por [!UICONTROL Alocação automática] é diferente da fórmula mostrada por padrão no campo [!DNL Adobe Analytics] [!UICONTROL A4T] painel. [Conforme descrito aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Alocação automática] usa intervalos de confiança mais conservadores do que os regulares [!UICONTROL Teste A/B] atividades. Esses níveis de confiança conservadores compensam avaliações repetidas (picos) nos dados. Como resultado, o relatório padrão em [!DNL Adobe Analytics] mostra intervalos de confiança mais estreitos em comparação com os utilizados [!UICONTROL Alocação automática] algoritmo. No entanto, você pode determinar qual experiência é favorecida pelos algoritmos com base na experiência que tem mais visitantes únicos sendo enviados para ela.
* **Status do vencedor**: Atualmente, a variável [Medalhas &quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) não estão disponíveis no [!UICONTROL A4T] painel no [!DNL Analysis Workspace]. Esses emblemas também não estarão disponíveis se o mesmo relatório for visualizado em [!DNL Target]. Um emblema de &quot;estrela&quot; vencedor mostrado em um [!DNL Target] relatório para um [!UICONTROL Alocação automática] A atividade usando A4T deve ser ignorada. Esse selo reflete cálculos de confiança regulares, e não aqueles usados por [!UICONTROL Alocação automática].

### Direcionamento automático {#at}

* [!UICONTROL Direcionamento automático] Os modelos continuam a treinar a cada 24 horas, como de costume. No entanto, os dados do evento de conversão provenientes de [!DNL Analytics] é adiado por mais seis a 24 horas. Este atraso significa a distribuição do tráfego por [!DNL Target] rastreia os eventos mais recentes registrados em [!DNL Analytics]. Esse atraso tem o maior efeito nas primeiras 48 horas após uma atividade ser ativada inicialmente. O desempenho da atividade refletirá mais [!DNL Analytics] comportamento de conversão após cinco dias. Considere usar [!UICONTROL Alocação automática] em vez de [!UICONTROL Direcionamento automático] para atividades de curta duração em que a maior parte do tráfego ocorre nos primeiros cinco dias da vida da atividade.
* Ao usar [!DNL Analytics] como fonte de dados para uma [!UICONTROL Direcionamento automático] atividade, as sessões terminam após o decurso de seis horas. As conversões que ocorrem após seis horas não são contadas.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Guia de ferramentas do Analytics*.

## Tutorial: como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático {#tutorial}

Embora os recursos avançados de análise estejam disponíveis no [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algumas modificações no padrão [!UICONTROL Analytics for Target] para interpretar corretamente as atividades de Direcionamento automático. Essas modificações são necessárias devido a diferenças entre as atividades de experimentação (atividades A/B manuais e [!UICONTROL Alocação automática]) e atividades de personalização ([!UICONTROL Direcionamento automático]).

Este tutorial o orienta pelas modificações recomendadas para análise [!UICONTROL Direcionamento automático] atividades no [!UICONTROL Workspace].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) in *Adobe Target Tutorials*.
