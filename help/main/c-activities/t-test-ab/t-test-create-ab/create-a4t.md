---
keywords: Direcionamento;análise;servidor de rastreamento;análise para destino;a4T
description: Saiba como configurar uma atividade no [!DNL Adobe Target] para usar [!DNL Adobe Analytics] como fonte de relatórios (A4T).
title: Como posso usar os dados do  [!DNL Analytics]  no  [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 16%

---

# Usando dados de [!DNL Adobe Analytics]

Você pode configurar uma atividade no [!DNL Adobe Target] para usar o [!DNL Adobe Analytics] como fonte de relatórios (A4T).

Para obter informações detalhadas sobre como configurar o [!DNL Analytics] como fonte de dados para [!DNL Target], consulte [Adobe Analytics como Source de Relatórios para o Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Antes de configurar uma atividade que use o [!DNL Analytics] como fonte de relatórios, estabeleça a meta para a atividade, como melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Escolha uma métrica de sucesso final para a atividade. Embora seja possível selecionar métricas adicionais a qualquer momento em [!DNL Analytics], você ainda deve especificar uma métrica específica que espera que este teste afete.

>[!NOTE]
>
>A opção [!DNL Adobe Analytics] estará disponível se você tiver vinculado sua conta do [!DNL Adobe Experience Cloud] ao [!DNL Analytics] e ao [!DNL Target], mesmo que a integração entre o [!DNL Target] e o [!DNL Analytics] não tenha sido configurada para a sua conta.

Ao selecionar [!DNL Analytics] como fonte de relatórios para [!DNL Target], você seleciona um conjunto de relatórios [!DNL Analytics] para receber os dados de atividade [!DNL Target]. Para especificar uma fonte de relatórios, primeiro escolha uma das empresas [!DNL Analytics] vinculadas à sua conta e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para conexão com [!DNL Adobe Target] estão disponíveis para seleção. Se você não vir o conjunto de relatórios esperado, primeiro tente fazer logoff e depois fazer logon novamente no [!DNL Adobe Experience Cloud] para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, entre em contato com o Atendimento ao cliente.

O [!UICONTROL Analytics for Target] (A4T) requer um servidor de rastreamento para relatar os resultados corretamente. Um servidor de rastreamento padrão é exibido no campo [!UICONTROL Tracking Server]. Se você usar mais de um servidor de rastreamento, certifique-se de incluir o servidor de rastreamento correto neste campo. Consulte [Usando um servidor de rastreamento do Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obter mais informações.

>[!NOTE]
>
>Se você usar [!DNL Adobe Analytics] como a fonte de relatórios da sua atividade, não será necessário especificar um servidor de rastreamento durante a criação da atividade se você estiver usando a at.js versão 0.9.1 (ou posterior). A biblioteca at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Tracking Server] vazio na página [!UICONTROL Goals & Settings].

Ao configurar a atividade após configurar o [!DNL Analytics] como fonte de relatórios, não há opção para configurar os públicos-alvo para relatórios. [!DNL Analytics] segmentos estão disponíveis no relatório [!DNL Target] [!UICONTROL Activities].

Você deve selecionar uma métrica de sucesso para usar como meta para cada atividade. Sua meta da atividade é a atividade de conversão que sinaliza uma atividade bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. Você pode escolher qualquer métrica [!DNL Analytics] disponível no seletor de métricas [!DNL Analytics].

Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com o teste.

Depois que um visitante conclui sua meta, ele não é mais incluído na atividade. Se o visitante entrar novamente na atividade após concluir uma atividade, ele será contado como um novo visitante.
