---
keywords: Targeting;analytics;tracking server
description: É possível configurar uma Atividade no Target Standard para usar o Adobe Analytics como origem de geração de relatórios (A4T).
title: Uso de dados do Analytics
feature: a4t general
uuid: 4ac0c181-030b-4cf5-b138-acf02c7af4f6
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 95%

---


# Uso de dados do Analytics{#using-analytics-data}

É possível configurar uma Atividade no Target Standard para usar o Adobe Analytics como origem de geração de relatórios (A4T).

For detailed information about setting up Analytics as the data source for Target, see [Adobe Analytics as the Reporting Source for Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md).

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
