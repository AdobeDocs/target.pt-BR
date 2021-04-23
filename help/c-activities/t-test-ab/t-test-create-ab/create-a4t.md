---
keywords: Direcionamento, analytics, servidor de rastreamento, analytics for target, a4t
description: Saiba como configurar uma atividade no Adobe [!DNL Target] to use Adobe Analytics as the reporting source. This integration is called Analytics for [!DNL Target] (A4T).
title: Como posso usar os dados do Analytics no Target?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '543'
ht-degree: 88%

---

# Uso de dados do Analytics

Você pode configurar uma atividade em [!DNL Adobe Target] para usar [!DNL Adobe Analytics] como fonte de relatórios (A4T).

Para obter informações detalhadas sobre como configurar o Analytics como fonte de dados para o Target, consulte [Adobe Analytics como fonte de relatórios para Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

Antes de configurar uma atividade que usa o Analytics como fonte de relatórios, estabeleça a meta da atividade, como melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Escolha uma métrica de sucesso final para a campanha. Apesar de poder selecionar métricas adicionais a qualquer momento no Analytics, você ainda precisa especificar uma métrica específica que espera que seja afetada por esse teste.

>[!NOTE]
>
>A opção do Adobe Analytics está disponível caso tenha vinculado sua conta da Adobe Experience Cloud com o Analytics e o Target, mesmo que a integração entre o Target e o Analytics não tenha sido definida para a sua conta.

Ao selecionar o Analytics como fonte de relatórios para o Target, você seleciona um conjunto de relatórios do Analytics para receber os dados de atividade do Target. Para fazer isso, primeiro escolha uma das empresas do Analytics vinculadas à sua conta e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para se conectar ao Adobe Target estarão disponíveis para seleção. Se não vir os conjuntos de relatórios esperados, primeiro, experimente sair e entrar na Adobe Experience Cloud para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, entre em contato com o atendimento ao cliente.

O Analytics for Target exige que um servidor de rastreamento informe os resultados corretamente. Um servidor de rastreamento padrão aparecerá no campo Servidor de rastreamento. Se você usar mais de um servidor de rastreamento, verifique se incluiu o servidor de rastreamento correto nesse campo. Consulte [Usar um servidor de rastreamento do Analytics](/help/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obter mais informações.

>[!NOTE]
>
>Se você usar o Adobe Analytics como a fonte de relatórios da sua atividade, não será necessário especificar um servidor de rastreamento durante a criação da atividade usando a mbox.js versão 61 (ou posterior) ou a at.js versão 0.9.1 (ou posterior). A biblioteca mbox.js ou at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].

Ao configurar uma atividade após definir o Analytics como sua fonte de relatórios, não há opção para configurar os públicos-alvo para a geração de relatórios. Os segmentos do Analytics estão disponíveis no relatório de Atividades do Target.

Você deve selecionar uma métrica de sucesso para usar como uma meta para cada teste. Sua meta da atividade é a atividade de conversão que sinaliza uma campanha bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. Você pode selecionar qualquer métrica do Analytics disponível no seletor de métrica do Analytics.

Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com o teste.

Depois que um visitante concluir sua meta, ele não estará mais incluído na campanha. Se o visitante entrar novamente na sua campanha após concluir uma atividade, ele será contado como um novo visitante.
