---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: Saiba como configurar uma atividade no Adobe [!DNL Target] que usa o Adobe Analytics como fonte de relatórios (A4T).
title: Como criar uma atividade que use o A4T?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '654'
ht-degree: 30%

---

# Crie uma atividade que use o Analytics como fonte de relatórios

Você pode configurar uma atividade no [!DNL Adobe Target] para usar [!DNL Adobe Analytics] como fonte de relatórios (A4T).

Antes de configurar uma atividade que use [!DNL Analytics] como fonte de relatórios, estabeleça a meta para a atividade, como melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Escolha uma métrica de sucesso final para a atividade. Embora seja possível selecionar mais métricas a qualquer momento no [!DNL Analytics], você ainda deve especificar uma métrica específica que espera que esse teste afete.

## Criar a atividade

Criação de um [!DNL Target] atividade que usa [!DNL Analytics] como a fonte de geração de relatórios é semelhante à configuração de um [!DNL Target] atividade, com algumas diferenças importantes. Por exemplo, não é possível selecionar um segmento para relatório ao criar a atividade, pois todos os segmentos disponíveis no [!DNL Analytics] podem ser aplicados na exibição de um relatório.

1. Clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >Um nome de atividade não pode incluir o caractere &quot;%&quot; se [!DNL Analytics] é usada como a fonte de geração de relatórios.
   >
   >Não use o mesmo nome de atividade para duas atividades de [espaços de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) que estão usando os relatórios A4T.

1. Selecione o tipo de atividade e comece a configurar a atividade.

   Se quiser criar um [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático] atividade, consulte [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md) para obter mais informações.

1. Quando você chegar ao **[!UICONTROL Configurações]** parte do fluxo de criação de atividade, escolha **[!UICONTROL Adobe Analytics]** e especifique a empresa.
1. Selecione um conjunto de relatórios.

   Você pode escolher qualquer conjunto de relatórios que esteja disponível no [!DNL Analytics]. O conjunto de relatórios define onde os dados coletados estão disponíveis. Os conjuntos de relatórios virtuais não estão incluídos na lista de conjuntos de relatórios.

   É possível encontrar dois erros ao selecionar o conjunto de relatórios:

   * Você recebe um erro informando que nenhum conjunto de relatórios está disponível, mas sua conta está configurada corretamente.

     Verifique o seu [!DNL Analytics] empresa. Se o seu [!DNL Adobe Experience Cloud] a conta está vinculada a mais de um [!DNL Analytics] empresa, fazer logoff de [!DNL Target]e faça logon no [!DNL Analytics] na empresa certa. Em seguida, volte para [!DNL Target], e os conjuntos de relatórios serão carregados.

   * Você não vê o conjunto de relatórios esperado.

     Somente conjuntos de relatórios provisionados para conexão com o [!DNL Target] estão disponíveis para seleção. Se você não vir os conjuntos de relatórios esperados, primeiro tente fazer logoff e logon novamente na [!DNL Adobe Experience Cloud] para tentar novamente.

   Se um ou mais conjuntos de relatórios ainda estiverem ausentes na lista, [entre em contato com o Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Especificar o servidor de rastreamento.

   Consulte [Uso de um servidor de rastreamento do Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina a experiência.
1. Especifique a meta da atividade.

   É necessário selecionar uma métrica de sucesso para usar como meta para cada atividade. Sua meta da atividade é a atividade de conversão que sinaliza uma atividade bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. Você pode escolher qualquer [!DNL Analytics] métrica disponível no [!DNL Analytics] seletor de métricas.

   >[!NOTE]
   >
   >Você pode enviar uma métrica personalizada com base no Target para [!DNL Analytics] em vez de depender apenas de [!DNL Analytics] dados. Por exemplo, é possível monitorar clicando em uma página, que geralmente não é rastreada por [!DNL Analytics]. Essa métrica personalizada é enviada para [!DNL Analytics] automaticamente do [!DNL Target] e aparece como o &quot;[!DNL Target] Métrica &quot;Conversão&quot; no seletor de métricas do [!DNL Analytics]. A variável [!DNL Target] A métrica de conversão estará vazia se você optar por usar [!DNL Analytics] métricas.

   Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com a atividade.

   O visitante permanece em atividade após atingir a meta. O visitante continua a ver o conteúdo da atividade, mas não é contado como uma nova entrada da atividade.

   >[!NOTE]
   >
   >Ao configurar uma atividade após a configuração [!DNL Analytics] como fonte de relatórios, não há opção para configurar públicos-alvo para relatórios. [!DNL Analytics] segmentos estão disponíveis no [!DNL Target] Relatório de atividades.

1. Clique em **[!UICONTROL Salvar]**.

## Atividades do A4T e de Alocação automática e Direcionamento automático

Para obter mais informações, consulte [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
