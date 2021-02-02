---
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
description: É possível configurar uma atividade no Target Standard/Premium para usar o Adobe Analytics como fonte de relatórios (A4T).
title: Criar uma atividade que usa a A4T como fonte do relatórios
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 4f0f1df1bcb6baad0e20c4dc1ae7e12751080d91
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 43%

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

   Se quiser criar uma atividade [!UICONTROL Autoalocar] ou [!UICONTROL Público alvo automático], consulte [Suporte A4T para Autoalocar e Público alvo automático atividades](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md) para obter mais informações.

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

## Atividades A4T e Autoalocação e Público alvo automático

Para obter mais informações, consulte [Suporte A4T para a Autoalocação e Público alvo de atividades](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).