---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: É possível configurar uma atividade no Target Standard/Premium para usar o Adobe Analytics como fonte de relatórios (A4T).
title: Criação da atividade
feature: null
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '1130'
ht-degree: 25%

---


# Criação da atividade{#activity-creation}

You can configure an activity in [!DNL Target] to use [!DNL Adobe Analytics] as the reporting source (A4T).

Before you set up an activity that uses [!DNL Analytics] as the reporting source, establish the goal for the activity, such as improving revenue per visitor (RPV) or increasing clicks on your shopping cart. Escolha uma métrica de sucesso final para a atividade. Although you can select additional metrics at any time in [!DNL Analytics], you must still specify a particular metric you expect this test to affect.

## Crie uma atividade que use o Analytics como a fonte do relatórios

Creating a [!DNL Target] activity that uses [!DNL Analytics] as the reporting source is similar to setting up a regular [!DNL Target] activity, with a few important differences. For example, you cannot select a segment for reporting while creating the activity because all segments available in [!DNL Analytics] can be applied when viewing a report.

1. Clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >An activity name cannot include the &quot;%&quot; character if [!DNL Analytics] is used as the reporting source.

1. Selecione o tipo de atividade e comece a configurar a atividade.
1. Quando chegar na parte de **[!UICONTROL Configurações]** do fluxo de criação de atividade, escolha **[!UICONTROL Adobe Analytics]** e especifique a empresa.
1. Selecione um conjunto de relatórios.

   Você pode escolher qualquer conjunto de relatório que esteja disponível no [!DNL Analytics]. O conjunto de relatórios define onde os dados coletados estarão disponíveis. Os conjuntos de relatórios virtuais não estão incluídos na lista de conjuntos de relatórios.

   É possível encontrar dois erros ao selecionar o conjunto de relatórios:

   * Você recebe um erro informando que nenhum conjunto de relatórios está disponível, mas sua conta está configurada corretamente.

      You might need to check your [!DNL Analytics] company. If your [!DNL Adobe Experience Cloud] account is tied to more than one [!DNL Analytics] company, log out of [!DNL Target], and log in to [!DNL Analytics] under the right company. Then return to [!DNL Target], and the report suites will load.

   * Você não vê o conjunto de relatórios esperado.

      Only report suites that are provisioned to connect to [!DNL Target] will be available for selection. If you don&#39;t see the report suite(s) you expect, first try logging out and logging back in to the [!DNL Adobe Experience Cloud] to try again.
   Se o conjunto de relatórios ainda estiver ausente na lista,  [entre em contato com o Atendimento ao cliente](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Especificar o servidor de rastreamento.

   Consulte [Uso de um servidor de rastreamento do Analytics](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina a experiência.
1. Especifique a meta da atividade.

   É necessário selecionar uma métrica de sucesso para usar como meta para cada atividade. Sua meta da atividade é a atividade de conversão que sinaliza uma atividade bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. You can choose any [!DNL Analytics] metric available in the [!DNL Analytics] metric selector.

   >[!NOTE]
   >
   >You can send a custom Target-based metric to [!DNL Analytics] rather than relying only on [!DNL Analytics] data. Por exemplo, você pode monitorar ao clicar em uma página que normalmente não é rastreada pelo [!DNL Analytics]. This custom metric is sent to [!DNL Analytics] automatically from the [!DNL Target] server, and appears as the &quot;[!DNL Target] Conversion&quot; metric in the metrics selector in [!DNL Analytics]. The [!DNL Target] Conversion metric is empty if you choose to use [!DNL Analytics] metrics.

   Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com a atividade.

   O visitante permanece em atividade após atingir a meta. O visitante continua a ver o conteúdo da atividade, mas não é contado como uma nova entrada da atividade.

   >[!NOTE]
   >
   >When setting up an activity after setting up [!DNL Analytics] as your reporting source, there is no option to set up audiences for reporting. [!DNL Analytics] segmentos estão disponíveis no relatório [!DNL Target] Atividade.

1. Clique em **[!UICONTROL Salvar]**.

## Suporte do Analytics para Públicos alvos (A4T) para alocação automática de atividades {#a4t-aa}

Atualizamos a integração entre Adobe Target e Adobe Analytics, conhecida como [Analytics para Públicos alvos](/help/c-integrating-target-with-mac/a4t/a4t.md).

[!UICONTROL A Autoalocação] de atividades agora é compatível com o [!UICONTROL Analytics para Público alvo]. Essa integração permite que você use o recurso de alocação automática de banco multiarcado para direcionar o tráfego para experiências vencedoras, ao mesmo tempo que usa uma métrica de [!DNL Adobe Analytics] objetivo e/ou recursos de [!DNL Adobe Analytics] relatórios e análise. Se você já tiver [implementado o A4T para uso com atividades](/help/c-integrating-target-with-mac/a4t/a4timplementation.md)de teste A/B e direcionamento de experiência, você estará pronto!

Para começar:

1. Crie uma atividade de teste A/B e selecione **[!UICONTROL Autoalocar para a melhor experiência]** como o Método **[!UICONTROL de alocação de]** tráfego na página [!UICONTROL Direcionamento] .
1. Selecione **[!UICONTROL Adobe Analytics]** para a Fonte **[!UICONTROL do]** Relatórios na página **[!UICONTROL Metas e configurações]** e selecione o conjunto de relatórios correspondente à meta de otimização desejada.
1. Escolha uma métrica de Objetivo principal.

   Escolha **[!UICONTROL Conversão]** para usar [!DNL Adobe Target] para especificar a meta de otimização.

   Ou

   Escolha **[!UICONTROL Usar uma métrica]** do Analytics e, em seguida, selecione uma métrica [!DNL Analytics] para usar como meta de otimização. Você pode usar uma métrica de conversão [!DNL Analytics] predefinida ou um evento [!DNL Analytics] personalizado.

1. Salve e ative sua atividade.

   [!UICONTROL A Autoalocação] usará sua métrica selecionada para otimizar a atividade, levando visitantes para a experiência que maximiza sua métrica de meta.

1. Use a guia **[!UICONTROL Relatórios]** para visualização do relatórios de sua atividade por sua escolha de [!DNL Adobe Analytics] métricas. Clique em **[!UICONTROL Visualização no Analytics]** para detalhar e segmentar ainda mais seus dados de relatórios.

### Métricas de meta suportadas

O A4T para [!UICONTROL Autoalocação] permite escolher qualquer um dos seguintes tipos de métricas como sua métrica de meta principal para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

A A4T para [!UICONTROL Autoalocação] exige que você escolha uma métrica baseada em um evento binômico, ou seja, um evento que ocorra ou não, por exemplo, um clique, uma conversão, um pedido etc. (Esses tipos de eventos às vezes também são chamados de eventos Bernoulli, binários ou discretos.)

A A4T para [!UICONTROL Autoalocação] não oferece suporte à otimização para métricas contínuas, como receita, número de produtos solicitados, duração da sessão, número de visualizações de página na sessão etc. (Esses tipos de métricas não suportados às vezes também são chamadas de métricas não-binomiais ou não-Bernoulli.)

Os seguintes tipos de métricas não são suportados como métricas de objetivo principal:

* [!DNL Adobe Target] métricas de envolvimento e receita
* [!DNL Adobe Analytics] métricas de envolvimento e receita

   >[!NOTE]
   >
   >Pode ser possível selecionar [!DNL Analytics] métricas de envolvimento e receita como sua métrica de objetivo principal porque não é possível [!DNL Target] identificar todas as métricas de envolvimento e receita [!DNL Analytics]. Tenha cuidado para selecionar somente métricas de conversão binomial ou eventos personalizados de [!DNL Analytics].

* Métricas calculadas da Adobe Analytics

### Limitações e notas

* A fonte do relatórios não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade é ativada.
* Embora as métricas calculadas não sejam suportadas como métricas de objetivo principal, geralmente é possível alcançar o resultado pretendido selecionando, em vez disso, um evento personalizado como a métrica de objetivo principal. Por exemplo, se você deseja otimizar para uma métrica como &quot;conclusões de formulário por visitante&quot;, selecione um evento personalizado que corresponda a &quot;conclusões de formulário&quot; como sua métrica de objetivo principal. [!DNL Target] normaliza automaticamente as métricas de conversão com base em cada visita para contabilizar uma distribuição de tráfego desigual, de modo que não é necessário usar uma métrica calculada para executar a normalização.
* [!DNL Target] usa o modelo de atribuição &quot;Mesmo toque&quot; na implementação de Autoalocação A4T.

Para obter mais informações, consulte Visão geral [da](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/panels/attribution/attribution.html) atribuição no Guia *de ferramentas do* Analytics.
