---
keywords: cja4t;Customer Journey Analytics;Customer Journey Analytics for Target;fonte de relatórios do Customer Journey Analytics;Customer Journey Analytics como fonte de relatório para o Target
description: Use o  [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target]  (A4T) para criar atividades baseadas em métricas de conversão e segmentos de público-alvo do  [!DNL Customer Journey Analytics]  e use relatórios do  [!DNL Customer Journey Analytics]  para examinar os resultados.
title: Qual é o objetivo do  [!DNL Adobe Customer Journey Analytics]  for  [!DNL Target]  (CJA4T)?
feature: Integrations
hide: true
hidefromtoc: true
source-git-commit: 13c899b656d9f15e7368d981ac25540c46caccb2
workflow-type: ht
source-wordcount: '919'
ht-degree: 100%

---

# [!DNL Adobe Customer Journey Analytics] como fonte de relatórios para o [!DNL Adobe Target] (CJA4T)

A integração [!DNL Customer Journey Analytics for Target] (CJA4T), que une o [Adobe Customer Journey Analytics (CJA)](https://experienceleague.adobe.com/docs/customer-journey-analytics.html?lang=pt-BR){target=_blank} e o [!DNL Target], fornece ferramentas avançadas de análise e economia de tempo para o seu programa de otimização.

Os principais benefícios de usar dados do [!DNL Customer Journey Analytics] no [!DNL Target] são:

* Profissionais de marketing podem aplicar dinamicamente as métricas de sucesso do [!DNL Customer Journey Analytics] nos relatórios de atividades do [!DNL Target] a qualquer momento. Não há necessidade de especificar tudo antes de executar a atividade.
* Uma única fonte de dados minimiza a variação que ocorre ao coletar dados em dois sistemas separados.

## Considerações

Considere as seguintes informações antes de usar a integração CJA4T:

* Para usar o [!DNL Customer Journey Analytics] como a fonte de relatórios do [!DNL Target], você e sua empresa devem ter acesso ao [!DNL Customer Journey Analytics] e ao [!DNL Target]. Se precisar de acesso a qualquer uma das soluções, entre em contato com o(a) administrador(a) da organização ou representante da conta.
* Para criar atividades do [!DNL Target] com relatórios do [!DNL Customer Journey Analytics], você deve ter a função “[!UICONTROL Aprovador]” ou “[!UICONTROL Editor]” no [!DNL Target].
   * Se tiver uma conta do [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consulte [Especificar funções e permissões](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) em *Usuários*.
   * Se tiver uma conta do [Target Premium](/help/main/c-intro/intro.md#premium), consulte [Funções e permissões](/help/main/administrating-target/c-user-management/property-channel/property-channel.md#roles-permissions) em *Permissões para usuários corporativos*.

* Dependendo das configurações, os relatórios podem ser alterados por atividade ou no nível da organização. Consulte [Solução de relatórios na nuvem](/help/main/administrating-target/reporting.md#solution) em *Configurar relatórios no Target*.
* Você deve usar uma fonte de relatórios ou outra. Não é possível coletar dados de uma única atividade para diversas fontes de relatórios.
* Ao definir o [!DNL Customer Journey Analytics] como fonte de relatórios, será solicitado que você especifique a sandbox para relatórios. Durante a configuração, somente as sandboxes às quais você tem acesso serão exibidas.
* Quaisquer atividades do [!DNL Target] existentes continuam a usar a coleta de dados do [!DNL Target] e não são afetadas pela habilitação do CJA4T.
* O CJA4T só estará disponível se você tiver a [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=pt-BR){target=_blank} and [!DNL Target] implemented through the [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}. A compatibilidade com o [!DNL Analytics Data Connector] está planejada para uma data futura.
* Para perguntas sobre tempo, consulte [Considerações sobre latência](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-faq.html?lang=pt-BR#latency){target=_blank} nas *Perguntas frequentes* do *Guia do Adobe Customer Analytics*.

## Tipos de atividades aceitas {#supported-activities}

Os seguintes tipos de atividades são permitidas ao usar a biblioteca JavaScript do [SDK da Web da Adobe Experience Platform](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank} or the [at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=pt-BR){target=_blank}:

| Tipos de atividades | Compatível com o CJA4T? |
|--- |--- |
| [Atividade A/B com divisão manual de tráfego](/help/main/c-activities/t-test-ab/test-ab.md) | Sim |
| [Atividade A/B com alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | Não |
| [Atividade A/B com direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) | Não |
| [Direcionamento de experiência (XT)](/help/main/c-activities/t-experience-target/experience-target.md) | Sim |
| [Teste multivariado (MVT)](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | Sim |
| [Atividade de Automated Personalization (AP)](/help/main/c-activities/t-automated-personalization/automated-personalization.md) | Não |
| [Atividade do Recommendations](/help/main/c-recommendations/recommendations.md) | Sim |

## Criar uma atividade que use o [!DNL Customer Journey Analytics] como fonte de relatórios

Criar uma atividade do [!DNL Target] que usa o [!DNL Customer Journey Analytics] como fonte de relatórios é semelhante à configurar uma atividade comum do [!DNL Target].

1. Na lista **[!UICONTROL Atividades]**, clique em **[!UICONTROL Criar atividade]**, selecione o tipo de atividade (de acordo com o [gráfico de atividades compatíveis acima](#supported-activities)) e comece a configurar a atividade.
1. Quando chegar na página **[!UICONTROL Metas e configurações]** do fluxo de trabalho de criação de três partes, selecione o **[!DNL Customer Journey Analytics]** como fonte de relatórios.

   ![Opção do Customer Journey Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/cja4t/assets/cja-as-reporting-source.png)

   >[!NOTE]
   >
   >A fonte de relatórios não pode ser alterada após uma atividade do [!DNL Target] entrar em funcionamento.

1. Selecionar uma sandbox.

   Você pode ver apenas as sandboxes às quais tem acesso nesta lista suspensa. Se uma ou mais sandboxes às quais você tem acesso não estiverem na lista, verifique se você tem acesso à sandbox. Entre em contato com o [Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C) se continuar a ter problemas.

   ![Opção de selecionar a sandbox](/help/main/c-integrating-target-with-mac/cja4t/assets/sandbox.png)

1. Especifique a meta da atividade.

   Selecione uma métrica de sucesso para usar como meta para cada atividade. Você pode escolher uma das métricas de conversão do [!DNL Target] ou usar uma métrica do [!DNL Customer Journey Analytics].

   ![Opção de usar uma métrica do Customer Journey Analytics em Métrica de meta](/help/main/c-integrating-target-with-mac/cja4t/assets/goal-metric.png)

1. Clique em **[!UICONTROL Salvar e fechar]**.

## Configurar uma conexão do [!DNL Customer Journey Analytics]

Depois de criar uma atividade do [!DNL Target], você deverá criar uma conexão no [!DNL Customer Journey Analytics]. Se você já tiver uma conexão configurada, poderá utilizá-la e pular para a etapa 4 abaixo. A conexão permite que o [!DNL Customer Journey Analytics] comece a extrair dados do conjunto de dados para relatórios.

1. Na página **[!UICONTROL Conexões]** do [!DNL Customer Journey Analytics], clique em **[!UICONTROL Criar uma nova conexão]**.

   ![Link para criar uma nova conexão no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/create-connection.png)

1. Defina suas [configurações de conexão e dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/overview.html?lang=pt-BR){target=_blank} com as informações corretas.
1. Adicione o conjunto de dados do evento usado ao configurar seu fluxo de dados.
1. Adicione o conjunto de dados de pesquisa **[!UICONTROL Eventos de classificação do Adobe Target]** e clique em **[!UICONTROL Próximo]**.

   ![Caixa de diálogo Adicionar conjuntos de dados no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/add-datasets.png)

1. Configure o conjunto de dados do evento.

   Para obter mais informações, consulte [Adicionar e configurar conjuntos de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-connections/create-connection.html?lang=pt-BR#add-dataset){target=_blank} na seção *Criar uma conexão* do *Guia do Adobe Customer Journey Analytics*.

1. Configure seu conjunto de dados de pesquisa com o campo [!UICONTROL Chave] definido como “key” e o campo Chave correspondente com o seguinte caminho:

   ```
   _experience.decisioning.propositions.scopeDetails.correlationID
   ```

   ![Caixa de diálogo Evento de classificações do Adobe Target no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/classifications-events.png)

1. Clique em **[!UICONTROL Adicionar conjuntos de dados]** e selecione **[!UICONTROL Salvar]** na próxima tela para concluir a conexão.

## Configurar visualizações de dados

Configure uma visualização de dados no [!DNL Customer Journey Analytics]. Uma visualização de dados garante que os dados da sua conexão possam ser usados corretamente.

1. Configure sua visualização de dados e certifique-se de que ela aponta para a conexão criada acima.

   Para obter mais informações, consulte [Criar ou editar uma visualização de dados](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-dataviews/create-dataview.html?lang=pt-BR){target=_blank} no *Guia do Adobe Customer Journey Analytics*.

1. Para visualizar corretamente seus dados do [!DNL Target] no [!DNL Customer Journey Analytics], você deve adicionar os seguintes campos do conjunto de dados de pesquisa como dimensões:

   * Nome da experiência
   * ID da experiência
   * Nome da atividade
   * ID da atividade

   ![Opções de nomes e IDs no Customer Journey Analytics](/help/main/c-integrating-target-with-mac/cja4t/assets/names-and-ids.png){width="600" zoomable="yes"}

1. Termine de configurar outros campos e clique em **[!UICONTROL Salvar e continuar]** após concluído.
