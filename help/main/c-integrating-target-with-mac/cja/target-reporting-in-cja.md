---
keywords: customer jornada analytics;customer jornada analytics for target;fonte de relatórios do customer jornada analytics;customer jornada analytics como fonte de relatórios para o target;relatórios do target no cja; relatórios do target no Customer Journey Analytics
description: Use os [!DNL Target] relatórios [!DNL Adobe Customer Journey Analytics] para criar atividades baseadas em [!DNL Customer Journey Analytics] métricas de conversão e segmentos de público-alvo, e use os [!DNL Customer Journey Analytics] relatórios para examinar os resultados.
title: O que é  [!DNL Target] um relatório em  [!DNL Adobe Customer Journey Analytics]?
feature: Integrations
exl-id: 67b20bf6-ffbe-4220-9455-cb3886bb9227
TQID: https://experienceleague.adobe.com/bEwtqdwOsXyDbBUdxZKMl3I3LLTgxdxURvXjrfco-WI
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: c93393a4-e558-47e1-992e-c91ed4d480ceid: f7c7de77-382f-4f48-8b36-61a170f06d3d
subfeature_v2: id: df62f171-ac37-440f-8f0f-f41a72ebdd34id: fd0ff162-b6d3-4a11-8aeb-e165a01c0f0a
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bcc5edb5-84c3-4940-9f84-ed88b6c16274id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: 5b60a40e83437c535ccb3a7e7800493619fc62c8
workflow-type: tm+mt
source-wordcount: 1754
ht-degree: 20%

---

# [!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics]

A integração entre o [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/customer-journey-analytics){target=_blank} e o [!DNL Target] fornece ferramentas poderosas de análise e economia de tempo para o seu programa de otimização.

Os principais benefícios de usar o [!DNL Customer Journey Analytics] como fonte de relatórios para o [!DNL Target] são:

* Profissionais de marketing podem aplicar dinamicamente as métricas de sucesso do [!DNL Customer Journey Analytics] nos relatórios de atividades do [!DNL Target] a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Os profissionais de marketing podem aproveitar os recursos do [!DNL Customer Journey Analytics], como o [Painel de experimentação](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation){target=_blank}, para analisar ainda mais a personalização do site.
* Os profissionais de marketing podem ter uma única fonte de relatórios para [!DNL Adobe Journey Optimizer] e [!DNL Target]. Ambos os produtos de personalização podem ser conectados ao [!DNL Customer Journey Analytics] para obter uma visão mais completa da personalização na Web.

## Considerações

Considere as informações a seguir antes de usar a integração [!DNL Customer Journey Analytics] e [!DNL Target]:

>[!IMPORTANT]
>
>Esta integração não é a mesma que [[!UICONTROL Adobe Analytics for Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). A implementação e os tipos de atividade compatíveis são diferentes. Leia atentamente este artigo antes de usar esta integração para suas atividades do [!DNL Target].

* Para usar o [!DNL Customer Journey Analytics] como a fonte de relatórios do [!DNL Target], você e sua empresa devem ter acesso ao [!DNL Customer Journey Analytics] e ao [!DNL Target]. Se precisar de acesso a qualquer uma das soluções, entre em contato com o(a) administrador(a) da organização ou representante da conta.
* Para criar atividades [!DNL Target] com relatórios [!DNL Customer Journey Analytics], você deve ter a função &quot;[!UICONTROL Aprovador]&quot; ou &quot;[!UICONTROL Editor]&quot; em [!DNL Target].
  * Se tiver uma conta do [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consulte [Especificar funções e permissões](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) em *Usuários*.
  * Se tiver uma conta do [Target Premium](/help/main/c-intro/intro.md#premium), consulte [Funções e permissões](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) em *Permissões para usuários corporativos*.

* Faça parte de uma função em [!DNL Adobe Experience Platform] para configurar uma atividade [!DNL Target] com [!DNL Customer Journey Analytics] como fonte de relatórios. Para obter mais informações, consulte [Adicionar uma função em [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/platform-learn/getting-started-for-data-architects-and-data-engineers/configure-permissions#add-a-role-in-adobe-experience-platform-requires-a-system-administrator-or-product-admin){target=_blank} em *Configurar permissões* no *Tutorial do arquiteto e engenheiro de dados.*
* Dependendo das configurações, os relatórios podem ser alterados por atividade ou no nível da organização. Consulte [Solução de relatórios na nuvem](/help/main/administrating-target/reporting.md#solution) em *Configurar relatórios no Target*.
* Você deve usar uma fonte de relatórios ou outra. Não é possível coletar dados de uma única atividade para diversas fontes de relatórios.
* Ao definir [!DNL Customer Journey Analytics] como fonte de relatórios, você será solicitado a especificar a sandbox e a exibição de dados para os relatórios. Durante a configuração, você vê somente as sandboxes e as visualizações de dados às quais tem acesso.
* Quaisquer atividades existentes do [!DNL Target] continuam a usar a coleta de dados do [!DNL Target] e não são afetadas pela habilitação dessa integração.
* Para usar essa integração, o método de implementação preferido é ter [[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/en/docs/experience-platform){target=_blank} e [!DNL Target] implementados através de [[!DNL Adobe Experience Platform Web SDK]](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank}.

  Se você não tiver o [!DNL Adobe Experience Platform Web SDK] implementado, também poderá criar uma [[!DNL Adobe Analytics] conexão de origem](https://experienceleague.adobe.com/en/docs/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics) para trazer os dados para [!DNL Adobe Experience Platform]. Se você planeja usar esse método, selecione um conjunto de relatórios [!DNL Analytics] junto com a sandbox [!DNL Adobe Experience Platform] que você usa com [!DNL Customer Journey Analytics].

  ![Opção de sandbox na caixa de diálogo Configurações de Relatório](/help/main/c-integrating-target-with-mac/cja/assets/aep-sandbox.png)

  >[!NOTE]
  >
  >Se você usar uma conexão de origem [!DNL Adobe Analytics], terá relatórios em [!DNL Adobe Analytics] e [!DNL Customer Journey Analytics]. No entanto, devido a algoritmos diferentes entre essas duas soluções, os resultados provavelmente não serão correspondentes.

* Para perguntas sobre tempo, consulte [Considerações de latência](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-faq#latency){target=_blank} em *Perguntas frequentes* no *[!DNL Adobe Customer Analytics]Guia*.

## Tipos de atividades aceitas {#supported-activities}

Os seguintes tipos de atividades são suportados ao usar a [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep/aep-web-sdk-overview){target=_blank} ou a biblioteca JavaScript [at.js](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/at-js-implementation/overview){target=_blank}:

| Tipos de atividades | Suportado? |
|--- |--- |
| [Atividade A/B com divisão manual de tráfego](/help/main/c-activities/t-test-ab/test-ab.md) | Sim |
| [Atividade A/B com alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Sim |
| [Atividade A/B com direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Não |
| [Direcionamento de experiência (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sim |
| [Teste multivariado (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sim |
| [Atividade de Automated Personalization (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Não |
| [Atividade do Recomendações](/help/main/c-recommendations/recommendations.md) | Sim |

As atividades de [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] ainda não oferecem suporte para [!DNL Customer Journey Analytics] como a fonte de relatórios.

## Criar uma atividade que use o [!DNL Customer Journey Analytics] como fonte de relatórios {#create-an-activity-that-uses-customer-journey-analytics-as-the-reporting-source}

Criar uma atividade do [!DNL Target] que usa o [!DNL Customer Journey Analytics] como fonte de relatórios é semelhante à configurar uma atividade comum do [!DNL Target]. Este fluxo de trabalho se aplica a todos os tipos de atividades com suporte na tabela acima, incluindo [!UICONTROL Alocação automática] testes A/B.

>[!TIP]
>
>Você também pode especificar que [!DNL Target] use os relatórios em [!DNL Customer Journey Analytics] para todas as atividades criadas em sua conta (**[!UICONTROL Administração]** > **[!UICONTROL Relatórios]** > **[!UICONTROL Solução Reporting Experience Cloud]**). Para obter mais informações, consulte *Solução da Reporting Cloud* em [Configurar relatórios em [!DNL Target]](/help/main/administrating-target/reporting.md#solution).

1. Na lista **[!UICONTROL Atividades]**, clique em **[!UICONTROL Criar Atividade]**, selecione o tipo de atividade (de acordo com o [gráfico de atividades com suporte acima](#supported-activities)) e comece a configurar a atividade.

1. Ao chegar na página **[!UICONTROL Metas e configurações]** do fluxo de trabalho de criação da atividade de três partes, selecione **[!DNL Customer Journey Analytics]** como fonte de relatórios.

   ![Opção do Customer Journey Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/cja/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >A fonte de relatórios não pode ser alterada após uma atividade do [!DNL Target] entrar em funcionamento.

1. Selecione a sandbox [!DNL Adobe Experience Platform] que corresponde aos dados usados para os relatórios [!DNL Customer Journey Analytics]. Você vê apenas as sandboxes às quais tem acesso nesta lista suspensa. Se uma ou mais sandboxes às quais você tem acesso não estiverem na lista, verifique se você tem acesso à sandbox. Entre em contato com o [Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) se continuar a ter problemas.

   ![Opção de selecionar a sandbox](/help/main/c-integrating-target-with-mac/cja/assets/sandbox.png)

1. Selecione uma **[!UICONTROL Visualização de dados]**. Uma visualização de dados funciona como um conjunto de relatórios [!DNL Analytics] para relatórios [!DNL Customer Journey Analytics]. Somente as visualizações de dados na sandbox selecionada à qual você tem acesso são exibidas.

   ➡️ [Saiba mais sobre a Visualização de dados na documentação do Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/data-views)

1. Especifique a métrica de meta. Escolha uma das seguintes opções:

   * **[!UICONTROL Conversão]**: escolha a ação que seu público-alvo deve realizar para indicar que a meta foi atingida. [Saiba mais sobre métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md).

   * **[!UICONTROL Usar uma métrica do Customer Journey Analytics]**: escolha uma métrica [!DNL Customer Journey Analytics] ou uma métrica calculada na exibição de dados selecionada. Essa métrica serve como critério de otimização. O modelo é executado em dados [!DNL Customer Journey Analytics] e atualiza os dados de desempenho na mesma cadência usada para os relatórios [!DNL Customer Journey Analytics].

   ![Opção de usar uma métrica do Customer Journey Analytics em Métrica de meta](/help/main/c-integrating-target-with-mac/cja/assets/goal-metric.png)

1. Clique em **[!UICONTROL Salvar e fechar]**.

## Configurar uma conexão do [!DNL Customer Journey Analytics]

Depois de criar a atividade [!DNL Target], configure o [!DNL Customer Journey Analytics] para obter dados para os relatórios. A instalação segue o fluxo de trabalho de conexão [!DNL Customer Journey Analytics] padrão. Se você já tiver uma conexão configurada, poderá usar sua conexão existente e pular para [Configurar visualizações de dados](#set-up-data-views).

1. Em [!DNL Customer Journey Analytics], vá para **[!UICONTROL Gerenciamento de Dados]** > **[!UICONTROL Conexões]** e clique em **[!UICONTROL Criar uma nova conexão]**.

   ![Criar novo link de conexão em [!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/assets/create-connection.png)

1. Defina suas [configurações de conexão e dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/overview){target=_blank} com as informações corretas, incluindo a mesma sandbox [!DNL Adobe Experience Platform] selecionada para a atividade.
1. Adicione o conjunto de dados do evento usado ao configurar seu fluxo de dados.
1. Adicione o conjunto de dados de pesquisa **[!UICONTROL Eventos de Classificação da Adobe Target]** e clique em **[!UICONTROL Avançar]**.

   ![Caixa de diálogo Adicionar conjuntos de dados no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/add-datasets.png)

1. Configure o conjunto de dados do evento.

   Para obter mais informações, consulte [Adicionar e configurar conjuntos de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-connections/create-connection#add-dataset){target=_blank} em *Criar uma conexão* no *[!DNL Adobe Customer Journey Analytics]Guia*.

1. Configure seu conjunto de dados de pesquisa com o campo [!UICONTROL Chave] como &quot;chave&quot; e o campo de chave [!UICONTROL Correspondência] com o seguinte caminho:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Caixa de diálogo Evento de classificações do Adobe Target no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/classifications-events.png)

1. Clique em **[!UICONTROL Adicionar conjuntos de dados]** e em **[!UICONTROL Salvar]** na próxima tela para concluir a conexão.

## Configurar visualizações de dados {#set-up-data-views}

Configure no [!DNL Customer Journey Analytics] uma visualização de dados que aponte para a conexão criada. Uma visualização de dados garante que os dados da sua conexão possam ser usados corretamente para análise e para o painel [!UICONTROL Experimentação].

1. Configure sua visualização de dados e certifique-se de que ela aponta para a conexão criada acima.

   Para obter mais informações, consulte [Criar ou editar uma visualização de dados](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/create-dataview){target=_blank} no *[!DNL Adobe Customer Journey Analytics]Guia*.

1. Para exibir corretamente os dados do [!DNL Target] em [!DNL Customer Journey Analytics], adicione os seguintes campos do conjunto de dados de pesquisa como dimensões (incluindo a [!UICONTROL Experience ID] e a [!UICONTROL Activity ID]):

   * [!UICONTROL Nome da experiência]
   * [!UICONTROL ID da experiência]
   * [!UICONTROL Nome da atividade]
   * [!UICONTROL ID da atividade]

   ![Opções de nomes e IDs no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Para garantir que [!DNL Customer Journey Analytics] atribua métricas à experiência [!DNL Target] correta na jornada do visitante, configure a persistência para as dimensões [!UICONTROL Nome da atividade] e [!UICONTROL ID da atividade].

   Sem a persistência configurada, o [!DNL Customer Journey Analytics] vincula somente métricas que ocorrem no mesmo evento que a experiência [!DNL Target]. Por exemplo, se um visitante visualizar uma experiência do Target na página inicial, a métrica de receita desse visitante de uma compra em uma página posterior não será atribuída à atividade do Target.

   Para obter mais informações sobre persistência, consulte a [documentação do Adobe Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-dataviews/component-settings/persistence){target=_blank}.

1. Para usar dimensões [!DNL Target] no painel [!UICONTROL Experimentação], configure os seguintes rótulos de contexto:

   * Para [!UICONTROL Nome da atividade], use &quot;Experimento de experimentação&quot;.
   * [!UICONTROL Nome da experiência], use &quot;Variante de experimentação&quot;.

   ![Rótulos de contexto no painel Experimentação](/help/main/c-integrating-target-with-mac/cja/assets/context-labels.png){width="600" zoomable="yes"}

1. Termine de configurar outros campos, em seguida, clique em **[!UICONTROL Salvar e continuar]** quando terminar.

## Criar e exibir relatórios de atividades em [!DNL Customer Journey Analytics]

Depois que a atividade estiver ativa e você concluir a configuração da conexão e da visualização de dados, os dados de relatórios ficarão disponíveis no [!DNL Customer Journey Analytics]. Na guia **[!UICONTROL Relatórios]** da atividade em [!DNL Target], use a **[!UICONTROL Exibição no Customer Journey Analytics]** para abrir o [!DNL Customer Journey Analytics] para análise. Atualmente, esse link o redireciona para a página inicial de [!DNL Customer Journey Analytics].

![link para relatórios do CJA](/help/main/c-integrating-target-with-mac/cja/assets/report-link.png)

>[!NOTE]
>
>Esta integração não é a mesma que [!UICONTROL Adobe Analytics for Target] (A4T).
>
>* A integração [!DNL Target]/[!DNL Customer Journey Analytics] não inclui um relatório pré-compilado como A4T. Relatórios de atividade devem ser compilados em [!DNL Customer Journey Analytics].
>
>* Se [!UICONTROL Usar uma métrica de CJA] como métrica de meta da atividade for selecionada, esta opção oferecerá flexibilidade para quando métricas de sucesso específicas precisarem ser definidas. A métrica de sucesso é selecionada ao configurar o painel [!UICONTROL Experimentação]. O incentivo e a confiança são calculados a partir da métrica CJA selecionada.

1. Em [!DNL Customer Journey Analytics], crie um painel Experimentação e selecione a atividade no menu suspenso **[!UICONTROL Experimento]**.

   Para obter mais informações, consulte [Painel de experimentação](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation?lang=en#use){target=_blank} em *Painel de experimentação* no guia *[!DNL Customer Journey Analytics]*.

   ![Painel de experimentação no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja/assets/experimentation-panel.png)

   >[!IMPORTANT]
   >
   >Se a atividade não aparecer na lista suspensa [!UICONTROL Experimento], verifique se a exibição de dados correta está selecionada e se as dimensões [!DNL Target] incluem os rótulos de contexto necessários (consulte Etapa 3 em [Configurar exibições de dados](https://experienceleague.adobe.com/en/docs/target/using/integrate/cja/target-reporting-in-cja#set-up-data-views){target=_blank}).

1. Clique em **[!UICONTROL Construir]**.

   O painel [!UICONTROL Experimentação] retorna um conjunto avançado de dados e visualizações para ajudá-lo a entender melhor o desempenho de seus experimentos. Para obter mais informações, consulte [[!UICONTROL Saída do painel]](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/panels/experimentation#panel-output){target=_blank} em *Painel de experimentação* no guia *[!DNL Customer Journey Analytics]*.

   ![Experimentação](/help/main/c-integrating-target-with-mac/cja/assets/experimentation.png)