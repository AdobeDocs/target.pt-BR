---
keywords: Direcionamento;análise;servidor de rastreamento;análise para destino;a4T
description: Saiba como configurar uma atividade no [!DNL Adobe Target] para usar [!DNL Adobe Analytics] como fonte de relatórios (A4T).
title: Como posso usar o [!DNL Analytics] Entrada de dados [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 19%

---

# Usar [!DNL Adobe Analytics] dados

Você pode configurar uma atividade no [!DNL Adobe Target] para usar [!DNL Adobe Analytics] como fonte de relatórios (A4T).

Para obter informações detalhadas sobre a configuração [!DNL Analytics] como fonte de dados para [!DNL Target], consulte [Adobe Analytics como origem de relatório do Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

Antes de configurar uma atividade que use [!DNL Analytics] como fonte de relatórios, estabeleça a meta para a atividade, como melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Escolha uma métrica de sucesso final para a atividade. Embora seja possível selecionar métricas adicionais a qualquer momento no [!DNL Analytics], você ainda deve especificar uma métrica específica que espera que esse teste afete.

>[!NOTE]
>
>A variável [!DNL Adobe Analytics] está disponível se você vinculou seu [!DNL Adobe Experience Cloud] conta com ambos [!DNL Analytics] e [!DNL Target], mesmo que a integração entre [!DNL Target] e [!DNL Analytics] O não foi configurado para a sua conta.

Ao selecionar [!DNL Analytics] como fonte de relatórios para [!DNL Target], você seleciona um [!DNL Analytics] conjunto de relatórios a ser recebido [!DNL Target] dados da atividade. Para especificar uma fonte de geração de relatórios, primeiro escolha uma das opções [!DNL Analytics] empresas às quais sua conta está vinculada e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para conexão com o [!DNL Adobe Target] estão disponíveis para seleção. Se você não vir o conjunto de relatórios esperado, primeiro tente fazer logoff e logon novamente na [!DNL Adobe Experience Cloud] para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, entre em contato com o Atendimento ao cliente.

[!UICONTROL Analytics for Target] O (A4T) exige um servidor de rastreamento para relatar os resultados corretamente. Um servidor de rastreamento padrão é exibido no [!UICONTROL Servidor de rastreamento] campo. Se você usar mais de um servidor de rastreamento, certifique-se de incluir o servidor de rastreamento correto neste campo. Consulte [Uso de um servidor de rastreamento de análise](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obter mais informações.

>[!NOTE]
>
>Se você usar [!DNL Adobe Analytics] como fonte de relatórios da atividade, não é necessário especificar um servidor de rastreamento durante a criação da atividade, se você estiver usando a at.js versão 0.9.1 (ou posterior). A biblioteca at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].

Ao configurar a atividade após a configuração [!DNL Analytics] como fonte de relatórios, não há opção para configurar públicos-alvo para relatórios. [!DNL Analytics] segmentos estão disponíveis no [!DNL Target] [!UICONTROL Atividades] relatório.

Você deve selecionar uma métrica de sucesso para usar como meta para cada atividade. Sua meta da atividade é a atividade de conversão que sinaliza uma atividade bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. Você pode escolher qualquer [!DNL Analytics] métrica disponível no [!DNL Analytics] seletor de métricas.

Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com o teste.

Depois que um visitante conclui sua meta, ele não é mais incluído na atividade. Se o visitante entrar novamente na atividade após concluir uma atividade, ele será contado como um novo visitante.
