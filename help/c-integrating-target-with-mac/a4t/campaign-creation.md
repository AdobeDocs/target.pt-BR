---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: Saiba como configurar uma atividade no Adobe [!DNL Target] que usa o Adobe Analytics como fonte de relatórios (A4T).
title: Como faço para criar uma atividade que usa o A4T?
feature: Analytics for Target (A4T)
exl-id: 6a09764a-8bf1-4f69-b871-fb23136f933e
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 35%

---

# Crie uma atividade que use o Analytics como fonte de relatórios

Você pode configurar uma atividade em [!DNL Adobe Target] para usar [!DNL Adobe Analytics] como fonte de relatórios (A4T).

Antes de configurar uma atividade que use [!DNL Analytics] como fonte de relatórios, estabeleça a meta da atividade, como melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Escolha uma métrica de sucesso final para a atividade. Embora seja possível selecionar mais métricas a qualquer momento em [!DNL Analytics], você ainda deve especificar uma métrica específica que espera que o teste afete.

## Crie a atividade

Criar uma atividade [!DNL Target] que usa [!DNL Analytics] como fonte de relatórios é semelhante à configuração de uma atividade regular [!DNL Target], com algumas diferenças importantes. Por exemplo, não é possível selecionar um segmento para relatórios ao criar a atividade, pois todos os segmentos disponíveis em [!DNL Analytics] podem ser aplicados ao visualizar um relatório.

1. Clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >Um nome de atividade não pode incluir o caractere &quot;%&quot; se [!DNL Analytics] for usado como a fonte de relatórios.

1. Selecione o tipo de atividade e comece a configurar a atividade.

   Se quiser criar uma atividade de [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], consulte [Suporte A4T para atividades de Alocação automática e Direcionamento automático](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) para obter mais informações.

1. Quando chegar na parte de **[!UICONTROL Configurações]** do fluxo de criação de atividade, escolha **[!UICONTROL Adobe Analytics]** e especifique a empresa.
1. Selecione um conjunto de relatórios.

   Você pode escolher qualquer conjunto de relatório que esteja disponível no [!DNL Analytics]. O conjunto de relatórios define onde os dados coletados estão disponíveis. Os conjuntos de relatórios virtuais não estão incluídos na lista de conjuntos de relatórios.

   É possível encontrar dois erros ao selecionar o conjunto de relatórios:

   * Você recebe um erro informando que nenhum conjunto de relatórios está disponível, mas sua conta está configurada corretamente.

      Verifique sua empresa [!DNL Analytics]. Se sua conta [!DNL Adobe Experience Cloud] estiver vinculada a mais de uma [!DNL Analytics] empresa, saia de [!DNL Target] e faça logon em [!DNL Analytics] na empresa correta. Em seguida, retorne para [!DNL Target] e os conjuntos de relatórios serão carregados.

   * Você não vê o conjunto de relatórios esperado.

      Somente conjuntos de relatórios provisionados para se conectar a [!DNL Target] estão disponíveis para seleção. Se você não vir os conjuntos de relatórios esperados, primeiro tente sair e fazer logon novamente no [!DNL Adobe Experience Cloud] para tentar novamente.
   Se um ou mais conjuntos de relatórios ainda estiverem faltando na lista, [entre em contato com o Atendimento ao cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

1. Especificar o servidor de rastreamento.

   Consulte [Uso de um servidor de rastreamento do Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Defina a experiência.
1. Especifique a meta da atividade.

   É necessário selecionar uma métrica de sucesso para usar como meta para cada atividade. Sua meta da atividade é a atividade de conversão que sinaliza uma atividade bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. Você pode escolher qualquer métrica [!DNL Analytics] disponível no seletor de métrica [!DNL Analytics].

   >[!NOTE]
   >
   >Você pode enviar uma métrica personalizada com base no Target para [!DNL Analytics] em vez de confiar apenas nos dados [!DNL Analytics]. Por exemplo, você pode monitorar o clique em uma página, que normalmente não é rastreada por [!DNL Analytics]. Essa métrica personalizada é enviada para [!DNL Analytics] automaticamente do servidor [!DNL Target] e aparece como a métrica &quot;[!DNL Target] Conversão&quot; no seletor de métricas em [!DNL Analytics]. A métrica de conversão [!DNL Target] fica vazia se você optar por usar as métricas [!DNL Analytics].

   Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com a atividade.

   O visitante permanece em atividade após atingir a meta. O visitante continua a ver o conteúdo da atividade, mas não é contado como uma nova entrada da atividade.

   >[!NOTE]
   >
   >Ao configurar uma atividade após definir [!DNL Analytics] como fonte de relatórios, não há opção para configurar públicos para relatórios. [!DNL Analytics] segmentos estão disponíveis no relatório de  [!DNL Target] Atividades .

1. Clique em **[!UICONTROL Salvar]**.

## Atividades de A4T e Alocação automática e Direcionamento automático

Para obter mais informações, consulte [Suporte do A4T para atividades de Alocação automática e Direcionamento automático](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).
