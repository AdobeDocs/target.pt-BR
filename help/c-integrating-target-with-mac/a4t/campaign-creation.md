---
keywords: a4t;A4T;Analytics as the reporting source for Target
description: É possível configurar uma atividade no Target Standard/Premium para usar o Adobe Analytics como fonte de relatórios (A4T).
title: Criar uma atividade que usa a A4T como fonte do relatórios
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: cf47b7f3625bb1c3430b9fba00c573f489efc448
workflow-type: tm+mt
source-wordcount: '1394'
ht-degree: 20%

---


# Crie uma atividade que use o Analytics como a fonte do relatórios

Você pode configurar uma atividade em [!DNL Target] para usar [!DNL Adobe Analytics] como a fonte do relatórios (A4T).

Antes de configurar uma atividade que use [!DNL Analytics] como fonte de relatórios, estabeleça a meta para a atividade, como melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Escolha uma métrica de sucesso final para a atividade. Embora seja possível selecionar métricas adicionais a qualquer momento em [!DNL Analytics], você ainda deve especificar uma métrica específica que espera que esse teste afete.

## Crie a atividade

A criação de uma atividade [!DNL Target] que usa [!DNL Analytics] como fonte de relatórios é semelhante à configuração de uma atividade regular [!DNL Target], com algumas diferenças importantes. Por exemplo, não é possível selecionar um segmento para relatórios ao criar a atividade, pois todos os segmentos disponíveis em [!DNL Analytics] podem ser aplicados ao visualizar um relatório.

1. Clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >Um nome de atividade não pode incluir o caractere &quot;%&quot; se [!DNL Analytics] for usado como a origem do relatórios.

1. Selecione o tipo de atividade e comece a configurar a atividade.
1. Quando chegar na parte de **[!UICONTROL Configurações]** do fluxo de criação de atividade, escolha **[!UICONTROL Adobe Analytics]** e especifique a empresa.
1. Selecione um conjunto de relatórios.

   Você pode escolher qualquer conjunto de relatório que esteja disponível no [!DNL Analytics]. O conjunto de relatórios define onde os dados coletados estarão disponíveis. Os conjuntos de relatórios virtuais não estão incluídos na lista de conjuntos de relatórios.

   É possível encontrar dois erros ao selecionar o conjunto de relatórios:

   * Você recebe um erro informando que nenhum conjunto de relatórios está disponível, mas sua conta está configurada corretamente.

      Talvez seja necessário verificar sua empresa [!DNL Analytics]. Se sua conta [!DNL Adobe Experience Cloud] estiver vinculada a mais de uma empresa [!DNL Analytics], faça logout de [!DNL Target] e faça logon em [!DNL Analytics] na empresa direita. Em seguida, volte para [!DNL Target] e os conjuntos de relatórios serão carregados.

   * Você não vê o conjunto de relatórios esperado.

      Somente conjuntos de relatórios provisionados para conexão com [!DNL Target] estarão disponíveis para seleção. Se você não vir o(s) conjunto(s) de relatórios esperado(s), experimente sair e fazer login novamente no [!DNL Adobe Experience Cloud] para tentar novamente.
   Se o conjunto de relatórios ainda estiver ausente na lista,  [entre em contato com o Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Especificar o servidor de rastreamento.

   Consulte [Uso de um servidor de rastreamento do Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina a experiência.
1. Especifique a meta da atividade.

   É necessário selecionar uma métrica de sucesso para usar como meta para cada atividade. Sua meta da atividade é a atividade de conversão que sinaliza uma atividade bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. Você pode escolher qualquer métrica [!DNL Analytics] disponível no seletor de métricas [!DNL Analytics].

   >[!NOTE]
   >
   >Você pode enviar uma métrica personalizada baseada em Públicos alvos para [!DNL Analytics] em vez de depender apenas dos dados [!DNL Analytics]. Por exemplo, você pode monitorar ao clicar em uma página que normalmente não é rastreada pelo [!DNL Analytics]. Essa métrica personalizada é enviada para [!DNL Analytics] automaticamente do servidor [!DNL Target] e aparece como a métrica &quot;[!DNL Target] Conversão&quot; no seletor de métricas em [!DNL Analytics]. A métrica de conversão [!DNL Target] fica vazia se você optar por usar as métricas [!DNL Analytics].

   Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com a atividade.

   O visitante permanece em atividade após atingir a meta. O visitante continua a ver o conteúdo da atividade, mas não é contado como uma nova entrada da atividade.

   >[!NOTE]
   >
   >Ao configurar uma atividade depois de configurar [!DNL Analytics] como fonte de relatórios, não há opção para configurar o audiência para relatórios. [!DNL Analytics] segmentos estão disponíveis no relatório  [!DNL Target] Atividade.

1. Clique em **[!UICONTROL Salvar]**.

## Suporte do Analytics para Públicos alvos (A4T) para alocação automática e atividades de Público alvo automático {#a4t-aa}

Atualizamos a integração entre Adobe Target e Adobe Analytics, conhecida como [Analytics para Público alvo](/help/c-integrating-target-with-mac/a4t/a4t.md). As atividades de Autoalocação e Público alvo automático agora são compatíveis com o Analytics para Públicos alvos.

Essa integração permite:

* Use o recurso de [Autoalocar](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) bandit multiarmed para direcionar o tráfego para experiências vencedoras
* Use o algoritmo de aprendizado de máquina montado de [Público alvo automático](/help/c-activities/auto-target/auto-target-to-optimize.md) para escolher uma melhor experiência para cada visitante com base em seu perfil, comportamento e contexto, tudo isso usando uma métrica de [!DNL Adobe Analytics] objetivo e recursos ricos de relatórios e análise [!DNL Adobe Analytics].

Certifique-se de que [implementou A4T para uso com atividades de teste A/B e direcionamento de experiência](/help/c-integrating-target-with-mac/a4t/a4timplementation.md). Se você estiver usando `analyticsLogging = client_side`, também será necessário passar o valor `sessionId` para [!DNL Analytics]. Para obter mais informações, consulte [relatórios do Analytics for Público alvo (A4T)](https://adobetarget-sdks.gitbook.io/docs/integration-with-experience-cloud/analytics-for-target-a4t-reporting) no guia *SDKs do Adobe Target*.

Para começar:

1. Ao criar uma atividade de teste A/B, na página **[!UICONTROL Definição de metas]**, selecione uma das seguintes opções como **[!UICONTROL Método de alocação de tráfego]**:

   * Autoalocar para a melhor experiência
   * Público alvo automático para experiências personalizadas

1. Selecione **[!UICONTROL Adobe Analytics]** para a sua **[!UICONTROL Origem do Relatórios]** na página **[!UICONTROL Metas e Definições]** e selecione o conjunto de relatórios correspondente à sua meta de otimização desejada.

1. Escolha uma métrica de Objetivo principal.

   * Escolha **[!UICONTROL Conversão]** para usar [!DNL Adobe Target] para especificar a meta de otimização.
   * Escolha **[!UICONTROL Use uma métrica do Analytics]** e selecione uma métrica de [!DNL Analytics] para usar como objetivo de otimização. Você pode usar uma métrica de conversão [!DNL Analytics] predefinida ou um evento personalizado [!DNL Analytics].

1. Salve e ative sua atividade.

   [!UICONTROL A ] alocação automática usará sua métrica selecionada para otimizar a atividade, direcionando os visitantes para a experiência que maximiza sua métrica de objetivo.

   Ou

   [!UICONTROL O Auto-] Target usará sua métrica selecionada para otimizar a atividade, conduzindo visitantes a uma melhor experiência personalizada.

1. Use a guia **[!UICONTROL Relatórios]** para visualização do relatórios de sua atividade por sua escolha de [!DNL Adobe Analytics] métricas. Clique em **[!UICONTROL Visualização no Analytics]** para detalhar e segmentar ainda mais seus dados de relatórios.

### Métricas de meta suportadas

[!UICONTROL A4] Tfor  [!UICONTROL Auto] Allocate and  [!UICONTROL Auto-] Targetpermite escolher qualquer um dos seguintes tipos de métricas como sua principal métrica de meta para otimização:

* [!DNL Adobe Target] métricas de conversão
* [!DNL Adobe Analytics] métricas de conversão
* [!DNL Adobe Analytics] eventos personalizados

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Allocate and  [!UICONTROL Auto-] Targetexige que você escolha uma métrica baseada em um evento binomial, ou seja, um evento que ocorra ou não, por exemplo, um clique, uma conversão, um pedido etc. (Esses tipos de eventos às vezes também são chamados de eventos Bernoulli, binários ou discretos.)

[!UICONTROL A4] Tfor  [!UICONTROL Auto-] Alocate and  [!UICONTROL Auto-] Targett não suporta otimização para métricas contínuas, como receita, número de produtos solicitados, duração da sessão, número de visualizações de página na sessão etc. (Esses tipos de métricas não suportados às vezes também são chamadas de métricas não-binomiais ou não-Bernoulli.)

Os seguintes tipos de métricas não são suportados como métricas de objetivo principal:

* [!DNL Adobe Target] métricas de envolvimento e receita
* [!DNL Adobe Analytics] métricas de envolvimento e receita

   Pode ser possível selecionar uma métrica de envolvimento ou de receita [!DNL Analytics] como sua métrica de objetivo principal porque [!DNL Target] não pode identificar e excluir todas as métricas de envolvimento e receita de [!DNL Analytics]. Tenha cuidado para selecionar somente métricas de conversão binomial ou eventos personalizados de [!DNL Analytics].

* [!DNL Adobe Analytics] métricas calculadas

### Limitações e notas

Algumas limitações e observações se aplicam à Autoalocação e ao Público alvo automático. Outras limitações e observações se aplicam a um tipo de atividade ou outro.

#### Autoalocar e Público alvo automático

* A fonte do relatórios não pode ser alterada de [!DNL Analytics] para [!DNL Target] ou vice-versa depois que uma atividade é ativada.
* Embora as métricas calculadas não sejam suportadas como métricas de objetivo principal, geralmente é possível alcançar o resultado pretendido selecionando, em vez disso, um evento personalizado como a métrica de objetivo principal. Por exemplo, se você deseja otimizar para uma métrica como &quot;conclusões de formulário por visitante&quot;, selecione um evento personalizado que corresponda a &quot;conclusões de formulário&quot; como sua métrica de objetivo principal. [!DNL Target] normaliza automaticamente as métricas de conversão com base em cada visita para contabilizar uma distribuição de tráfego desigual, de modo que não é necessário usar uma métrica calculada para executar a normalização.
* [!DNL Target] usa o modelo de atribuição &quot;Mesmo toque&quot; no recurso  [!UICONTROL Autoalocação ] : Analytics for Público alvo (A4T).

#### Alocação automática

* [!UICONTROL A autoalocação ] continua a treinar a cada duas horas, como de costume.

#### Direcionamento automático

* [!UICONTROL Os modelos de ] direcionamento automático continuam treinando a cada 24 horas, como de costume. No entanto, os dados do evento de conversão provenientes de [!DNL Analytics] são atrasados em mais 6 a 24 horas. Esse atraso significa que a distribuição do tráfego por [!DNL Target] rastreará os eventos mais recentes registrados em [!DNL Analytics]. Este fato terá o maior efeito nas primeiras 48 horas após a primeira ativação de uma atividade; o desempenho da atividade refletirá melhor o comportamento de conversão [!DNL Analytics] após cinco dias. Você deve considerar o uso de [!UICONTROL Autoalocar] em vez de [!UICONTROL Público alvo automático] para atividades de curta duração nas quais a maioria do tráfego ocorre nos primeiros cinco dias de vida da atividade.
* Ao usar [!DNL Analytics] como fonte de dados para uma atividade [!UICONTROL Público alvo automático], as sessões são consideradas como encerradas após seis horas. As conversões que ocorrerem após seis horas não serão contadas.

Para obter mais informações, consulte [Modelos de atribuição e janelas de pesquisa](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html) no *Guia de ferramentas do Analytics*.
