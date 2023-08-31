---
keywords: cja4t;customer jornada analytics;customer jornada analytics for target;customer jornada analytics reporting source;customer jornada analytics como fonte de relatório para o target
description: Use o  [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target]  (A4T) para criar atividades baseadas em métricas de conversão e segmentos de público-alvo do  [!DNL Customer Journey Analytics]  e use relatórios do  [!DNL Customer Journey Analytics]  para examinar os resultados.
title: O que é o [!DNL Adobe Customer Journey Analytics] para [!DNL Target] (CJA4T)?
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 13c899b656d9f15e7368d981ac25540c46caccb2
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 12%

---

# [!DNL Adobe Customer Journey Analytics] como fonte de relatórios para [!DNL Adobe Target] (CJA4T)

A variável [!DNL Customer Journey Analytics for Target] (CJA4T) integração entre [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html){target=_blank} e [!DNL Target] O fornece ferramentas poderosas de análise e economia de tempo para o seu programa de otimização.

Os principais benefícios de usar [!DNL Customer Journey Analytics] entrada de dados [!DNL Target] são:

* Os profissionais de marketing podem aplicar [!DNL Customer Journey Analytics] métricas de sucesso para [!DNL Target] relatórios de atividades a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Uma única fonte de dados minimiza a variação que ocorre ao coletar dados em dois sistemas separados.

## Considerações

Considere as seguintes informações antes de usar a integração do CJA4T:

* Para usar o [!DNL Customer Journey Analytics] como a fonte de relatórios do [!DNL Target], você e sua empresa devem ter acesso ao [!DNL Customer Journey Analytics] e ao [!DNL Target]. Se precisar de acesso a qualquer uma das soluções, entre em contato com o administrador da organização ou com o representante de conta.
* Para criar [!DNL Target] atividades com [!DNL Customer Journey Analytics] relatórios, você deve ter a opção &quot;[!UICONTROL Aprovador]&quot; ou &#39;[!UICONTROL Editor]&quot; função no [!DNL Target].
   * Se você tiver uma [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905) conta, consulte [Especificar funções e permissões](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) in *Usuários*.
   * Se você tiver uma [Target Premium](/help/main/c-intro/intro.md#premium) conta, consulte [Funções e permissões](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) in *Permissões de usuário empresarial*.

* Dependendo das configurações, os relatórios podem ser alterados por atividade ou no nível da organização. Consulte [Solução da Reporting Cloud](/help/main/administrating-target/reporting.md#solution) in *Configurar relatórios no Target*.
* Você deve usar uma fonte de relatórios ou outra. Não é possível coletar dados para uma única atividade em várias fontes de relatórios.
* Ao definir [!DNL Customer Journey Analytics] como fonte de relatórios, você será solicitado a especificar a sandbox para relatórios. Durante a configuração, você vê somente as sandboxes às quais tem acesso.
* Qualquer existente [!DNL Target] As atividades do continuam a usar [!DNL Target] coleção de dados e não são afetados pela ativação do CJA4T.
* O CJA4T só estará disponível se você tiver [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank}. Suporte para o [!DNL Analytics Data Connector] está planejado para o futuro.
* Para perguntas sobre tempo, consulte [Considerações de latência](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html#latency){target=_blank} in *Perguntas frequentes* no *Guia do Adobe Customer Analytics*.

## Tipos de atividades aceitas {#supported-activities}

Os seguintes tipos de atividades são compatíveis ao usar o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html){target=_blank} Biblioteca JavaScript:

| Tipos de atividades | Compatível com CJA4T? |
|--- |--- |
| [Atividade A/B com divisão manual de tráfego](/help/main/c-activities/t-test-ab/test-ab.md) | Sim |
| [Atividade A/B com alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Não |
| [Atividade A/B com direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Não |
| [Direcionamento de experiência (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sim |
| [Teste multivariado (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sim |
| [Atividade de Automated Personalization (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Não |
| [Atividade do Recommendations](/help/main/c-recommendations/recommendations.md) | Sim |

## Crie uma atividade que use [!DNL Customer Journey Analytics] como fonte de relatórios

Criação de um [!DNL Target] atividade que usa [!DNL Customer Journey Analytics] como a fonte de geração de relatórios é semelhante à configuração de um [!DNL Target] atividade.

1. No **[!UICONTROL Atividades]** clique em **[!UICONTROL Criar atividade]** e selecione o tipo de atividade (de acordo com as [gráfico de atividades suportado acima](#supported-activities)) e comece a configurar a atividade.
1. Quando você chegar ao **[!UICONTROL Metas e configurações]** do fluxo de trabalho de criação da atividade de três partes, selecione **[!DNL Customer Journey Analytics]** como fonte de relatórios.

   ![Customer Journey Analytics como a opção de fonte de relatórios](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >A fonte de relatórios não pode ser alterada após um [!DNL Target] atividade entra em funcionamento.

1. Selecionar uma sandbox.

   Você pode ver apenas as sandboxes às quais você tem acesso nesta lista suspensa. Se uma ou mais sandboxes às quais você tem acesso estiverem ausentes na lista, verifique se você tem acesso à sandbox. Contato [Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) se você continuar a ver problemas.

   ![Selecionar opção de sandbox](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. Especifique a meta da atividade.

   Selecione uma métrica de sucesso para usar como meta para cada atividade. Você pode escolher uma das opções [!DNL Target] métricas de conversão ou usar um [!DNL Customer Journey Analytics] métrica.

   ![Use uma opção de métrica Customer Journey Analytics em Métrica de meta](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. Clique em **[!UICONTROL Salvar e fechar]**.

## Configurar um [!DNL Customer Journey Analytics] conexão

Depois de um [!DNL Target] atividade foi criada, você deve criar uma conexão no [!DNL Customer Journey Analytics]. Se você já tiver uma conexão configurada, poderá usar sua conexão existente e pular para a Etapa 4 abaixo. A conexão permite [!DNL Customer Journey Analytics] para começar a extrair dados do conjunto de dados para relatórios.

1. Entrada [!DNL Customer Journey Analytics], no **[!UICONTROL Conexões]** clique em **[!UICONTROL Criar uma nova conexão]**.

   ![Criar novo link de conexão no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. Configurar o [configurações de conexão e dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html){target=_blank} com as informações corretas.
1. Adicione o conjunto de dados do evento usado ao configurar seu fluxo de dados.
1. Adicione o **[!UICONTROL Eventos de classificação do Adobe Target]** pesquisar conjunto de dados e, em seguida, clique em **[!UICONTROL Próxima]**.

   ![Caixa de diálogo Adicionar conjuntos de dados no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. Configurar o conjunto de dados do evento.

   Para obter mais informações, consulte [Adicionar e configurar conjuntos de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=en#add-dataset){target=_blank} in *Criar uma conexão* no *Guia do Adobe Customer Journey Analytics*.

1. Configure seu conjunto de dados de pesquisa com o [!UICONTROL Chave] como &quot;key&quot; e o campo Matching key com o seguinte caminho:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Caixa de diálogo Evento de classificações do Adobe Target no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. Clique em **[!UICONTROL Adicionar conjuntos de dados]** e, em seguida, clique em **[!UICONTROL Salvar]** na próxima tela para concluir a conexão.

## Configurar visualizações de dados

Configurar uma visualização de dados no [!DNL Customer Journey Analytics]. Uma visualização de dados garante que os dados da sua conexão possam ser usados corretamente.

1. Configure sua visualização de dados e verifique se ela aponta para a conexão criada acima.

   Para obter mais informações, consulte [Criar ou editar uma visualização de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html){target=_blank} no *Guia do Adobe Customer Journey Analytics*.

1. Para visualizar corretamente suas [!DNL Target] entrada de dados [!DNL Customer Journey Analytics], você deve adicionar os seguintes campos do Conjunto de dados de pesquisa como dimensões:

   * Nome da experiência
   * ID da experiência
   * Nome da atividade
   * ID da atividade

   ![Opções de nomes e IDs no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Termine de configurar outros campos e clique em **[!UICONTROL Salvar e continuar]** quando terminar.
