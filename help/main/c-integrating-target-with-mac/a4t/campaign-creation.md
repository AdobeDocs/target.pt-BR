---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: Saiba como configurar uma atividade no Adobe [!DNL Target]  que usa o Adobe Analytics como fonte de relatórios (A4T).
title: Como criar uma atividade que use o A4T?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '646'
ht-degree: 30%

---

# Crie uma atividade que use o Analytics como fonte de relatórios

Você pode configurar uma atividade no [!DNL Adobe Target] para usar o [!DNL Adobe Analytics] como fonte de relatórios (A4T).

Antes de configurar uma atividade que use o [!DNL Analytics] como fonte de relatórios, estabeleça a meta para a atividade, como melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Escolha uma métrica de sucesso final para a atividade. Embora seja possível selecionar mais métricas a qualquer momento em [!DNL Analytics], você ainda deve especificar uma métrica específica que este teste deve afetar.

## Criar a atividade

A criação de uma atividade [!DNL Target] que use [!DNL Analytics] como fonte de relatórios é semelhante à configuração de uma atividade [!DNL Target] comum, com algumas diferenças importantes. Por exemplo, você não pode selecionar um segmento para relatório ao criar a atividade porque todos os segmentos disponíveis em [!DNL Analytics] podem ser aplicados quando um relatório é exibido.

1. Clique em **[!UICONTROL Create Activity]**.

   >[!NOTE]
   >
   >Um nome de atividade não pode incluir o caractere &quot;%&quot; se [!DNL Analytics] for usado como a fonte de relatórios.
   >
   >Não use o mesmo nome de atividade para duas atividades de [espaços de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) separados que estejam usando o relatório A4T.

1. Selecione o tipo de atividade e comece a configurar a atividade.

   Se você quiser criar uma atividade [!UICONTROL Auto-Allocate] ou [!UICONTROL Auto-Target], consulte o [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) para obter mais informações.

1. Quando chegar na parte **[!UICONTROL Settings]** do fluxo de criação de atividade, escolha **[!UICONTROL Adobe Analytics]** e especifique a empresa.
1. Selecione um conjunto de relatórios.

   Você pode escolher qualquer conjunto de relatórios que esteja disponível para você no [!DNL Analytics]. O conjunto de relatórios define onde os dados coletados estão disponíveis. Os conjuntos de relatórios virtuais não estão incluídos na lista de conjuntos de relatórios.

   É possível encontrar dois erros ao selecionar o conjunto de relatórios:

   * Você recebe um erro informando que nenhum conjunto de relatórios está disponível, mas sua conta está configurada corretamente.

     Verifique sua empresa [!DNL Analytics]. Se sua conta do [!DNL Adobe Experience Cloud] estiver vinculada a mais de uma empresa do [!DNL Analytics], saia do [!DNL Target] e faça logon no [!DNL Analytics] na empresa correta. Em seguida, retorne a [!DNL Target] e o conjunto de relatórios seja carregado.

   * Você não vê o conjunto de relatórios esperado.

     Somente conjuntos de relatórios provisionados para conexão com [!DNL Target] estão disponíveis para seleção. Se você não vir os conjuntos de relatórios esperados, primeiro tente fazer logoff e fazer logon novamente no [!DNL Adobe Experience Cloud] para tentar novamente.

   Se um ou mais conjuntos de relatórios ainda estiverem ausentes na lista, [entre em contato com o Atendimento ao Cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Especificar o servidor de rastreamento.

   Consulte [Uso de um servidor de rastreamento do Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina a experiência.
1. Especifique a meta da atividade.

   É necessário selecionar uma métrica de sucesso para usar como meta para cada atividade. Sua meta da atividade é a atividade de conversão que sinaliza uma atividade bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. Você pode escolher qualquer métrica [!DNL Analytics] disponível no seletor de métricas [!DNL Analytics].

   >[!NOTE]
   >
   >Você pode enviar uma métrica personalizada com base no Target para [!DNL Analytics], em vez de depender apenas dos dados de [!DNL Analytics]. Por exemplo, você pode monitorar ao clicar em uma página, que normalmente não é acompanhada por [!DNL Analytics]. Esta métrica personalizada é enviada para [!DNL Analytics] automaticamente do servidor [!DNL Target] e aparece como a métrica de &quot;[!DNL Target] Conversão&quot; no seletor de métricas em [!DNL Analytics]. A métrica de Conversão [!DNL Target] fica vazia se você optar por usar [!DNL Analytics] métricas.

   Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com a atividade.

   O visitante permanece em atividade após atingir a meta. O visitante continua a ver o conteúdo da atividade, mas não é contado como uma nova entrada da atividade.

   >[!NOTE]
   >
   >Ao configurar uma atividade após configurar o [!DNL Analytics] como fonte de relatórios, não há opção para configurar audiences para relatórios. [!DNL Analytics] segmentos estão disponíveis no relatório de [!DNL Target] atividades.

1. Clique em **[!UICONTROL Save]**.

## Atividades do A4T e de Alocação automática e Direcionamento automático

Para obter mais informações, consulte [Suporte ao A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
