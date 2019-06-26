---
description: É possível configurar uma atividade no Target Standard/Premium para usar o Adobe Analytics como fonte de relatórios (A4T).
keywords: a4t; A4T; Analytics como fonte de relatórios para Target
seo-description: É possível configurar uma atividade no Target Standard/Premium para usar o Adobe Analytics como fonte de relatórios (A4T).
seo-title: Criação da atividade
solution: Target
title: Criação da atividade
topic: Advanced,Standard,Classic
uuid: b04ad535-62fb-4dd3-ab3f-23da60fbffbd
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Criação da atividade{#activity-creation}

É possível configurar uma atividade no Target Standard/Premium para usar o Adobe Analytics como fonte de relatórios (A4T).

Antes de configurar uma atividade que usa o Analytics como fonte de relatórios, estabeleça a meta da atividade, como melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Escolha uma métrica de sucesso final para a atividade. Apesar de poder selecionar métricas adicionais a qualquer momento no Analytics, você ainda precisa especificar uma métrica específica que espera que seja afetada por esse teste.

Criar uma atividade do Target Standard que usa o Analytics como a fonte de geração de relatórios é semelhante à configuração de uma atividade regular do Target Standard, com algumas diferenças importantes. Por exemplo, você não pode selecionar um segmento para reportar, enquanto cria uma atividade, porque todos os segmentos disponíveis no Analytics podem ser aplicados ao visualizar um relatório.

1. Clique em **[!UICONTROL Criar atividade]**.

   >[!NOTE]
   >
   >Um nome de atividade não pode incluir o caractere &quot;%&quot; se o Analytics for usado como a fonte de relatórios.

1. Selecione o tipo de atividade e comece a configurar a atividade.
1. Quando chegar na parte de **[!UICONTROL Configurações]** do fluxo de criação de atividade, escolha **[!UICONTROL Adobe Analytics]** e especifique a empresa.
1. Selecione um conjunto de relatórios.

   Você pode escolher qualquer conjunto de relatório que esteja disponível no Adobe Analytics. O conjunto de relatórios define onde os dados coletados estarão disponíveis. Os conjuntos de relatórios virtuais não estão incluídos na lista de conjuntos de relatórios.

   É possível encontrar dois erros ao selecionar o conjunto de relatórios:

   * Você recebe um erro informando que nenhum conjunto de relatórios está disponível, mas sua conta está configurada corretamente.
   Pode ser necessário verificar sua empresa do Analytics. Se sua conta da Experience Cloud estiver vinculada a mais de uma empresa do Analytics, saia do Target e faça logon no Analytics na empresa certa. Em seguida, retorne ao Target e os conjuntos de relatórios serão carregados.

   * Você não vê o conjunto de relatórios esperado.
   Somente conjuntos de relatórios provisionados para se conectar ao Adobe Target estarão disponíveis para seleção. Se não vir os conjuntos de relatórios esperados, primeiro, experimente sair e entrar na Adobe Experience Cloud para tentar novamente.

   Se o conjunto de relatórios ainda estiver ausente na lista, [entre em contato com o Atendimento ao cliente](../../cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).
1. Especificar o servidor de rastreamento.

   Consulte [Uso de um servidor de rastreamento do Analytics](../../c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823).

1. Definir a experiência.
1. Especifique a meta da atividade.

   Você deve selecionar uma métrica de sucesso para usar como uma meta para cada teste. Sua meta da atividade é a atividade de conversão que sinaliza uma atividade bem sucedida. Faz parte das práticas recomendadas nunca executar um teste sem ter uma meta para aprimorá-la de alguma maneira específica. Você pode selecionar qualquer métrica do Analytics disponível no seletor de métrica do Analytics.

   >[!NOTE]
   >
   >Você pode enviar uma métrica personalizada com base no Target para o Analytics, em vez de confiar apenas nos dados do Analytics. Por exemplo, você pode monitorar ao clicar em uma página que normalmente não é rastreada pelo Analytics. Essa métrica personalizada é enviada para o Analytics automaticamente do servidor do Target e aparece como a métrica de &quot;Conversão do Target&quot; no seletor de métricas do Analytics. A métrica de conversão do Target estará vazia se você optar por usar as métricas do Analytics.

   Estabelecer uma meta não significa que você não pode usar outras métricas ao avaliar os resultados do teste. A meta, no entanto, é um lembrete de algo que deseja melhorar com a atividade.

   O visitante permanece em atividade após atingir a meta. O visitante continua a ver o conteúdo da atividade, mas não é contado como uma nova entrada da atividade.

   >[!NOTE]
   >
   >Ao configurar uma atividade após definir o Analytics como fonte de relatórios, não há opção para configurar audiences para relatórios. Os segmentos do Analytics estão disponíveis no relatório de Atividades do Target.

1. Clique em **[!UICONTROL Salvar]**.

