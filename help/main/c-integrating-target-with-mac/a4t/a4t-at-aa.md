---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: Saiba como criar atividades de Alocação automática e Direcionamento automático no Adobe [!DNL Target] que usam o Analytics como fonte de relatórios (A4T).
title: O A4T suporta atividades de alocação automática e direcionamento automático?
feature: Analytics for Target (A4T)
exl-id: 3302f26d-c445-4779-8435-be142d5cea8c
source-git-commit: e8fc28ef2497c1dfea523a769c9c817cbd74fea2
workflow-type: tm+mt
source-wordcount: '1695'
ht-degree: 3%

---

# Suporte do A4T para atividades de Alocação automática e Direcionamento automático

O [!DNL Adobe Target]-para-[!DNL Adobe Analytics] integração, conhecida como [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T) [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades.

A integração A4T permite:

* Use [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md)Recurso multi-armed bandit da para direcionar o tráfego para experiências vencedoras.
* Use [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)O algoritmo de aprendizado de máquina do conjunto da para escolher a melhor experiência para cada visitante. O Direcionamento automático escolhe a melhor experiência com base nos perfis, comportamentos e contexto dos usuários ao usar um [!DNL Adobe Analytics] métrica de meta e [!DNL Adobe Analytics]recursos avançados de análise e emissão de relatórios.

Certifique-se de que [A4T implementado para uso com atividades de Teste A/B e Direcionamento de experiência](/help/main/c-integrating-target-with-mac/a4t/a4timplementation.md). Se estiver usando `analyticsLogging = client_side`, você também deve passar o `sessionId` para [!DNL Analytics]. Para obter mais informações, consulte [Relatórios do Analytics for Target (A4T)](https://developer.adobe.com/target/implement/server-side/sdk-guides/integration-with-experience-cloud/a4t-reporting/){target=_blank} na *SDKs do Adobe Target* guia.

Para começar:

1. Ao criar uma atividade de Teste A/B, no **[!UICONTROL Direcionamento]** selecione uma das opções a seguir como **[!UICONTROL Método de alocação de tráfego]**:

   * [!UICONTROL Alocação automática para a melhor experiência]
   * [!UICONTROL Direcionamento automático para experiências personalizadas]

   ![Opções de métodos de alocação de tráfego: Manual, Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/assets/traffic-allocation-methods.png)

   Para obter mais informações e instruções passo a passo, consulte [Criar uma atividade de alocação automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md) e [Criar uma atividade de Direcionamento automático](/help/main/c-activities/auto-target/create-auto-target.md).

1. Selecionar **[!UICONTROL Adobe Analytics]** para seu **[!UICONTROL Fonte de geração de relatórios]** no **[!UICONTROL Metas e configurações]** e selecione o conjunto de relatórios correspondente à meta de otimização desejada.

   ![Seção Fonte de geração de relatórios na página Metas e configurações](/help/main/c-integrating-target-with-mac/a4t/assets/a4t-select.png)

1. Escolha uma métrica de meta primária. A primeira lista suspensa permite que você especifique uma meta em [!DNL Adobe Target] (que será rastreado por [!DNL Adobe Analytics] como a métrica &quot;Conversões de atividade&quot;), ou, para usar um [!DNL Analytics] como sua meta.

   * Para usar [!DNL Adobe Target] para especificar a meta de otimização, escolha **[!UICONTROL Conversão]** e, em seguida, especifique a ação que deve ser executada pelo seu público-alvo para indicar que a meta de conversão foi alcançada.
   * Em vez disso, selecione **[!UICONTROL Usar uma métrica do Analytics]**, você terá a opção de qual tipo de critério de otimização deve ser usado.  Consulte [Métricas de meta e critérios de otimização compatíveis](#supported) abaixo para obter mais informações. Após especificar o critério de otimização, você pode selecionar uma métrica compatível em [!DNL Analytics] para uso como meta de otimização. Você pode usar um [!DNL Analytics] métrica de conversão ou uma [!DNL Analytics] evento personalizado.


1. Salve e ative a atividade.

   [!UICONTROL Alocação automática] O usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para a experiência que maximiza sua métrica de meta.

   Ou

   [!UICONTROL Direcionamento automático] O usa a métrica selecionada para otimizar a atividade, direcionando os visitantes para uma melhor experiência personalizada.

1. Use o **[!UICONTROL Relatórios]** para exibir os relatórios da atividade e clique em **[!UICONTROL Exibir no Analytics]** para aprofundar e segmentar seus dados de relatórios no Adobe Analytics Workspace. Você pode seguir os tutoriais abaixo para ver como configurar seus relatórios no Workspace:
* Alocação automática: see [Como configurar relatórios do A4T no Analysis Workspace para atividades de Alocação automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) em *Adobe Target Tutorials*
* Direcionamento automático: see [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) em *Adobe Target Tutorials*.

## Métricas de meta e critérios de otimização compatíveis {#supported}

[!UICONTROL A4T] para [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] permite escolher qualquer um dos seguintes tipos de métricas como sua métrica de meta principal para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

No entanto, [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] os modelos otimizarão para **normalizada** versões dessas métricas, com a normalização exata dependendo do tipo de atividade. As opções para os critérios de otimização para cada tipo de atividade são explicadas pela tabela abaixo:

| Tipo de atividade | Fonte da métrica | Critério de Otimização | Descrição |
|---------------|---------------|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Alocação automática | Analytics | Maximizar a taxa de conversão de visitantes únicos | Os modelos tentam encontrar a Experiência com a maior taxa de conversão de visitantes únicos, que é definida como o número de visitantes para os quais a métrica de análise é diferente de zero, dividido pelo número total de visitantes (que receberam essa Experiência). Isso significa que a métrica é tratada como binária - 0 ou 1 para cada visitante único na atividade.   Use essa opção se você se importar apenas com a fração de usuários que fazem uma ação específica ou quando vários eventos de conversão para um único usuário não forem significativos. |
| Alocação automática | Analytics | Maximizar valor de métrica por visitante | Os modelos tentam encontrar a Experiência com o valor de métrica mais alto por visitante, que é definido como o valor total da métrica para todos os usuários expostos a essa Experiência, dividido pelo número total de visitantes que receberam essa Experiência. Isso significa que a métrica pode receber qualquer valor para cada visitante único na atividade. Por exemplo, se um visitante converter várias vezes, cada conversão será contada.  Use essa opção se estiver interessado em maximizar uma métrica contínua, como a receita total, ou se vários eventos de conversão para um único usuário forem mais significativos do que um (por exemplo, vários pedidos valem mais do que um) |
| Alocação automática | Target | (não configurável) | A métrica é tratada como binária e a taxa de conversão de visitante único é maximizada. |
| Direcionamento automático | Analytics | Maximizar a taxa de conversão de visitas únicas | Diferente da alocação automática ou dos testes A/B manuais, a natureza personalizada do Direcionamento automático significa que a experiência que um visitante vê pode mudar para cada nova visita. A taxa apropriada é então uma taxa de conversão normalizada pela visita, que é definida como a fração de visitas na qual uma métrica diferente de zero é registrada. Essa é a taxa de conversão otimizada pelo Direcionamento automático.   Semelhante à alocação automática, essa opção deve ser escolhida quando você se importa com a fração de visitas em que ocorre uma conversão, ou seja, quando vários eventos de conversão ocorrem para uma única visita não é importante. |
| Direcionamento automático | Analytics | Maximizar valor de métrica por visita | Quando a métrica que está sendo otimizada for contínua (por exemplo, receita) ou quando a presença de vários eventos de conversão em uma única visita é significativa (por exemplo, vários pedidos), você pode optar por maximizar o valor da métrica por visita. A &quot;taxa&quot; que está sendo otimizada é o valor total da métrica, dividido pelo número de visitas. |
| Direcionamento automático | Target | (não configurável) | A métrica é tratada como binária e a taxa de conversão de visita exclusiva é maximizada. |



Observe que, dependendo do critério de otimização, determinados [!DNL Adobe Analytics] métricas não serão suportadas.

* [!DNL Adobe Analytics] métricas calculadas não são compatíveis.
* [!DNL Adobe Analytics] as métricas sempre devem ser segmentáveis e, se o valor por visitante/visita estiver sendo otimizado, a métrica deverá ter polaridade positiva (ou seja, os valores positivos são melhores que os negativos)
* [!DNL Adobe Analytics] métrica usada em [!DNL Auto-Target] As atividades devem estar disponíveis nas exportações do DataWarehouse.

## Limitações e observações

Algumas limitações e observações se aplicam a [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades. Outras limitações e observações se aplicam a um tipo de atividade ou ao outro.

### Alocação automática e Direcionamento automático {#both}

* Ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], você sempre deve visualizar os relatórios em [!DNL Analytics].
* A origem de relatório não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou, inversamente, após uma atividade ter sido ativada.
* Embora as métricas calculadas não sejam suportadas como métricas de meta primária, geralmente é possível alcançar o resultado pretendido selecionando, em vez disso, um evento personalizado como a métrica de meta principal. Por exemplo, se você deseja otimizar para uma métrica, como &quot;preenchimentos de formulário por visitante&quot;, selecione um evento personalizado correspondente a &quot;preenchimentos de formulário&quot; como a métrica de meta principal. Conforme explicado em [Métricas de meta e critérios de otimização compatíveis](#supported), dependendo do tipo de atividade e do critério de otimização, [!DNL Target] O normalizará automaticamente as métricas de conversão, de modo que não é necessário usar uma métrica calculada para executar a normalização.


### Alocação automática {#aa}

* **Frequência de treinamento**: [!UICONTROL Alocação automática] Os modelos continuam treinando a cada hora, como de costume.
* **Modelos de atribuição**: [!DNL Target] usa a variável [!DNL Adobe Analytics] modelo de atribuição padrão para[!UICONTROL  Alocação automática] atividades que usam o A4T.
* **Confiança**: A fórmula de confiança usada por [!UICONTROL Alocação automática] As atividades do são diferentes da fórmula exibida por padrão no [!DNL Adobe Analytics] [!UICONTROL A4T] painel. [Conforme descrito aqui](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md), [!UICONTROL Alocação automática] O usa intervalos de confiança mais conservadores do que o regular [!UICONTROL Teste A/B] atividades. Esses níveis conservadores de confiança compensam avaliações repetidas (picos) nos dados. Como resultado, o relatório padrão em [!DNL Adobe Analytics] mostra intervalos de confiança mais estreitos em comparação aos usados pelo [!UICONTROL Alocação automática] algoritmo. No entanto, você pode determinar qual experiência é favorecida pelos algoritmos com base na qual a experiência tem mais visitantes únicos sendo enviados para ela.
* **Status do vencedor**: Atualmente, o [Semblemas &quot;Ainda não há vencedor&quot; e &quot;Vencedor&quot;](/help/main/c-activities/automated-traffic-allocation/determine-winner.md) não estão disponíveis no [!UICONTROL A4T] no painel [!DNL Analysis Workspace]. Esses selos também não estarão disponíveis se o mesmo relatório for visualizado em [!DNL Target]. Um símbolo de &quot;estrela&quot; vencedora exibido em um [!DNL Target] relatório para um [!UICONTROL Alocação automática] atividade usando A4T deve ser ignorada. Esse selo reflete cálculos de confiança regulares, e não aqueles usados pelo [!UICONTROL Alocação automática].

### Direcionamento automático {#at}

* **Frequência de treinamento**: [!UICONTROL Direcionamento automático] Os modelos continuam a treinar a cada 24 horas, como de costume. No entanto, os dados do evento de conversão são provenientes de [!DNL Analytics] é atrasada em 6 a 24 horas adicionais. Esse atraso significa a distribuição do tráfego por [!DNL Target] rastreia os eventos mais recentes registrados em [!DNL Analytics]. Esse atraso tem o maior efeito nas primeiras 48 horas após uma atividade ser ativada inicialmente. O desempenho da atividade refletirá mais detalhadamente [!DNL Analytics] o comportamento de conversão após cinco dias passou. Considere usar [!UICONTROL Alocação automática] em vez de [!UICONTROL Direcionamento automático] para atividades de curta duração em que a maior parte do tráfego ocorra nos primeiros cinco dias da vida da atividade.
* Ao usar [!DNL Analytics] como a fonte de dados de um [!UICONTROL Direcionamento automático] , as sessões terminam após seis horas decorrido. Conversões que ocorrem após seis horas não são contadas.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Guia de ferramentas do Analytics*.

## Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático e Alocação automática {#tutorial}

Embora os recursos de análise avançada estejam disponíveis em [!DNL Adobe Analytics] [!UICONTROL Analysis Workspace], algumas modificações no padrão [!UICONTROL Analytics para Target] são necessários para interpretar corretamente as atividades de Alocação automática e Direcionamento automático.

Estas modificações são necessárias devido às definições variadas das taxas de conversão descritas no [Métricas de meta e critérios de otimização compatíveis](#supported), bem como as diferenças entre as atividades de experimentação (manual A/B e [!UICONTROL Alocação automática]) e atividades de personalização ([!UICONTROL Direcionamento automático]).

Esses tutoriais orientam você pelas modificações recomendadas para analisar [!UICONTROL A4T] [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] atividades em [!UICONTROL Workspace].

Para obter mais informações, consulte 
* [Como configurar relatórios do A4T no Analysis Workspace para atividades de Alocação automática](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) em *Adobe Target Tutorials*.
* [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) em *Adobe Target Tutorials*.
