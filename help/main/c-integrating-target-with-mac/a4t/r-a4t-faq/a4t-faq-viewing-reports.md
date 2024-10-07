---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; relatório; relatórios; exibir relatórios; relatórios; metodologia de contagem; impressões; visitantes; visitas; métrica padrão; conversões de atividade; não especificado
description: Encontre respostas para perguntas frequentes sobre a exibição de relatórios ao usar o Analytics for [!DNL Target] (A4T). O A4T permite usar os relatórios do Analytics para  [!DNL Target]  atividades.
title: Encontre respostas para perguntas sobre a exibição de relatórios com o A4T?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: c747a8a0ed480130f254818e21b98addca16ca41
workflow-type: tm+mt
source-wordcount: '2539'
ht-degree: 24%

---

# Exibição de relatórios - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre exibição de relatórios ao usar o [!DNL Adobe Analytics] como fonte de relatórios para o [!DNL Adobe Target] (A4T).

## Posso exibir meus dados de atividade do [!DNL Target] em [!DNL Analysis Workspace]? {#workspace}

+++Resposta
Você pode usar o [!DNL Analysis Workspace] para analisar suas atividades e experiências no [!DNL Target]. O [painel Analytics for Target](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=pt-BR) permite que você veja o incentivo e a confiança para até três métricas de sucesso. Também é possível pesquisar mais usando tabelas e visualizações.

Para obter informações e exemplos detalhados, abra o [tutorial do Analytics &amp; Target: práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido por [!UICONTROL Adobe Experience League].

+++

## Onde os segmentos podem ser aplicados em [!DNL Analysis Workspace]? {#segmentation}

+++Resposta
Segmentos são usados com mais frequência na parte superior de um painel na área de soltar do segmento. O segmento é aplicado a todas as tabelas e visualizações no painel. Essa técnica é mais útil para ver como o teste afeta um subconjunto de pessoas (por exemplo, como esse teste foi executado para pessoas no Reino Unido)?

Um segmento também pode ser sobreposto diretamente na tabela de forma livre, mas observe que você deve sobrepô-lo na tabela inteira para preservar os cálculos de aumento e confiança no Painel A4T. No momento, os segmentos de nível de coluna não são compatíveis com o painel.

+++

## Qual modelo de Attribution IQ é usado em [!DNL Analysis Workspace]?

+++Resposta
Ao usar [!DNL Target] impressões e conversões de atividade no [!DNL Analysis Workspace], o modelo de Attribution IQ &quot;Mesmo toque&quot; é o modelo padrão aplicado às métricas para garantir uma contagem precisa. Esse modelo funciona bem em 99% dos casos. No entanto, você pode substituir essa atribuição padrão no Attribution IQ.

+++

## Quando eu aplicar um segmento de ocorrência para uma atividade [!DNL Target] específica, por que experiências não relacionadas são retornadas? {#activity-segmentation}

+++Resposta
A variável [!DNL Target] enviada para [!DNL Analytics] tem um período de expiração padrão de 90 dias. (Observação: esse período de expiração pode ser ajustado pelo Atendimento ao cliente, se necessário). À medida que os visitantes navegam pelo site em toda essa janela de expiração, eles fazem parte de muitas atividades [!DNL Target], todas coletadas na dimensão.

Ao segmentar para que uma atividade esteja presente em uma ocorrência, você obtém todas as experiências que fazem parte dessa atividade *mais* quaisquer outras experiências que persistam nessa ocorrência.

+++

## Ao configurar meu [!UICONTROL Goal Metrics], por que não posso acessar o [!UICONTROL Advanced Settings]?

+++Resposta
Para atividades que usam [!DNL Analytics] como fonte de relatórios (A4T), a métrica de meta usa as configurações &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; e &quot;[!UICONTROL On Every Impression]&quot;. Estas configurações são *não* configuráveis.

Para obter mais informações, consulte &quot;Ao configurar minhas métricas de meta, por que não posso acessar as opções de Configurações avançadas?&quot; em [Definições de métrica - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Devo usar visitantes, visitas ou impressões de atividade como minha métrica de normalização (ou seja, metodologia de contagem)? {#metrics}

+++Resposta
Há várias opções para normalizar métricas nos relatórios do A4T. Essa métrica, também conhecida como metodologia de contagem, torna-se o denominador do cálculo do incentivo. Além disso, afeta a maneira como os dados são agregados antes da aplicação do cálculo “confidence”.

* ***Visitantes únicos*** aumentam uma vez quando um usuário se qualifica pela primeira vez para uma atividade.
* O incremento de ***Visitas*** para cada sessão assim que um usuário (Visitante único) entra em uma atividade, mesmo que a atividade não seja visualizada em visitas subsequentes.
* ***Impressões de atividade*** aumentam sempre que o conteúdo da atividade é exibido. (Medido por [!DNL Target]).

Quando um visitante exibe uma página que contém uma atividade, uma variável é definida para esse visitante e contém o nome dessa atividade. Veja os cenários detalhados abaixo sobre como cada metodologia de contagem é comparada.

Considere o seguinte:

* As métricas acima são acionadas quando um usuário se qualifica para uma atividade e o conteúdo é retornado de [!DNL Target]. Isso não significa necessariamente que o usuário viu a oferta. Se uma experiência de atividade estiver abaixo da dobra e o usuário não rolar a página para baixo, a oferta foi distribuída pelo [!DNL Target], mas não foi vista pelo usuário.
* [!UICONTROL Activity Impressions] (medido por [!DNL Target]) e [!UICONTROL Instances] (medido por [!DNL Analytics]) são iguais, a menos que haja várias chamadas de mbox na mesma página e na mesma atividade. Isso faz com que vários [!UICONTROL Activity Impressions] sejam contados, mas somente um único [!UICONTROL Instance].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=pt-BR) em *Adobe Target Tutorials*.

+++

## Por que &quot;impressões de atividades&quot; e &quot;conversões de atividades&quot; são maiores em [!DNL Analysis Workspace] do que em [!UICONTROL Reports & Analytics]? {#sametouch}

+++Resposta
[!DNL Reports & Analytics] aplica um modelo de atribuição do mesmo toque a &quot;impressões de atividade&quot; e &quot;conversões de atividade&quot;, enquanto [!DNL Analysis Workspace] exibe as métricas brutas, que podem parecer infladas devido à persistência da dimensão [!DNL Target].

Para avaliar métricas [!UICONTROL Activity Impressions] e [!UICONTROL Activity Conversions] precisas em [!DNL Analysis Workspace], verifique se ambas as métricas aplicaram modelos de atribuição [!UICONTROL Same Touch]. Os modelos podem ser aplicados clicando na engrenagem das configurações de coluna, habilitando [!UICONTROL Non-default attribution models] e selecionando [!UICONTROL Same Touch]. Saiba mais sobre atribuição em [Visão geral de IQ dos atributos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) no *Guia de ferramentas do Analytics*.

+++

## O que significa &quot;conversões de atividade&quot; se o profissional de marketing escolher uma métrica [!DNL Analytics] durante a configuração da atividade? {#section_F3EBACF85AF846E9B366A549AAB64356}

+++Resposta
As &quot;Conversões de atividade&quot; estarão vazias se uma métrica [!DNL Analytics] tiver sido selecionada como a métrica de conversão para a atividade.

+++

## Por que vejo &quot;não especificado&quot; nos relatórios [!DNL Analytics]? O que isso significa?  {#unspecified}

+++Resposta
Em outros relatórios, &quot;não especificado&quot; significa que os dados não atenderam a uma regra de classificação, mas no A4T isso nunca deve acontecer. Se você vir &quot;não especificado&quot;, o serviço de classificação ainda não foi executado. Em geral, pode levar entre 24 e 72 horas para que os dados da atividade apareçam nos relatórios. Mesmo que as atividades não apareçam neste relatório até esse momento, todos os dados de visitantes vinculados a essas atividades serão capturados e exibidos quando a classificação for concluída.

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

Caso a classificação tenha sido feita para aquela atividade e você ainda vir uma linha &quot;Não especificado&quot; no relatório, verifique se o relatório não está usando uma métrica não-[!DNL Target] para exibir os dados. A menos que o relatório esteja usando uma métrica específica de [!DNL Target], que a linha &quot;Não especificado&quot; contenha eventos para chamadas que não estão associadas a [!DNL Target]. Essa linha não conterá nenhuma informação associada a [!DNL Target] (por exemplo, visitantes/visitas/impressões).

+++

## Por que as métricas [!DNL Target] são enviadas para [!DNL Analytics] mesmo após a desativação da atividade? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++Resposta
A variável [!DNL Target] enviada para [!DNL Analytics] tem um período de expiração padrão de 90 dias. Esse período de expiração pode ser ajustado pelo Atendimento ao cliente, se necessário. Essa configuração é global para todas as atividades; no entanto, não deve ser ajustada para um caso.

Você pode ver [!DNL Target] variáveis enviadas para [!DNL Analytics] após o período de expiração, pois a expiração é de 90 dias, mas somente se esse usuário nunca vir outra atividade [!DNL Target] habilitada para A4T. Se um usuário voltar ao site no dia 45 e vir outra atividade, todo o valor eVar do A4T terá seu contador redefinido para 90 dias. Isso significa que a primeira campanha do dia 1 agora pode persistir por até 45 + 90 = 135 dias. Se o usuário continuar voltando, você pode chegar ao ponto em que vê as métricas enviadas para [!DNL Analytics] em seus relatórios de atividades muito mais antigas. À medida que os usuários excluem cookies e não retornam ao site, os números nessa atividade caem, mas você ainda pode vê-los.

Isso significa que as atividades continuam a obter exibições de página, visitas e assim por diante, por até 90 dias após o término da atividade para visitantes que se tornaram parte da atividade enquanto ela estava ativa. No entanto, se você observar a métrica [!UICONTROL Activity Impressions], não verá nenhuma impressão após o término da atividade.

Esse é um comportamento normal e esperado. A variável A4T funciona como qualquer outro eVar. O valor é associado ao usuário até atingir o período de expiração (90 dias). Como resultado, se uma atividade estiver ativa por apenas duas semanas, o valor ainda será associado ao usuário pelos próximos 90 dias.

A prática recomendada é ver relatórios para essa atividade apenas durante o período em que a atividade foi ao vivo. As datas devem ser definidas corretamente por padrão ao exibir a atividade em [!DNL Analytics]. Portanto, a menos que você tenha estendido manualmente a data, isso não deve ser um problema do ponto de vista do relatório.

Como exemplo, vamos supor que a variável A4T expire após 90 dias e o teste esteja ativo de 1º de janeiro a 15 de janeiro.

Em 1 de janeiro, o usuário acessa o site e vê a atividade XYZ uma vez e tem cinco exibições de página depois disso. Nas próximas duas semanas, o usuário nunca retorna ao site. Os dados ficariam assim para este usuário:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

O usuário retorna em 1º de fevereiro, visualiza mais cinco páginas e não encontra mais nenhuma atividade do Target e a atividade original não está mais ativa. Mesmo que a atividade não esteja mais ativa, ela ainda está seguindo o usuário por meio da persistência de eVar. Agora os dados ficam assim:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

O usuário volta em 1 de março e vê uma nova atividade, ABC. O usuário também visualiza cinco páginas. Como a atividade XYZ ainda está seguindo o usuário por meio da persistência e esse usuário tem ABC definido, você verá dois itens de linha no relatório:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

O usuário volta em 1 de abril, visualiza outras cinco páginas e faz uma compra. A expiração de 90 dias desse primeiro valor de eVar é redefinida em 1º de abril, para que você veja isso no relatório. E todas as atividades do Target que o usuário vê recebem o crédito pela conversão, mas o número total de conversões é deduplicado:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos | Pedidos |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Total | 2 | 20 | 3 | 1 | 1 |

Como ambas as experiências foram vistas antes da conversão, ambas recebem &quot;crédito&quot; pelo pedido. Mas, apenas um pedido ocorreu no sistema e o total reflete isso. Para os relatórios de [!DNL Target], como você não está comparando uma atividade de [!DNL Target] com outra atividade para ver qual é mais bem-sucedida, não importa se todas as atividades que o usuário viu receberam crédito. Você está comparando os resultados de dois itens em uma única atividade. Não é possível para um usuário ver experiências diferentes na mesma atividade, de modo que você não precisa se preocupar com a contaminação cruzada do crédito do pedido.

Para obter mais informações, consulte [Variáveis de conversão (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) no *Guia de Administração do Analytics*.

+++

## Por que continuo vendo mais impressões depois que minha atividade é desativada? {#deactivated}

+++Resposta
Uma fonte de impressões para um relatório de atividade do A4T após a desativação pode ser o tráfego do modo de QA. O Target normalmente não registra eventos para uma atividade desativada, mas o Analytics não tem uma maneira de saber que as impressões vêm do modo de QA. Quando o relatório de atividade do Target é recuperado do Analytics, ele mostra essas impressões. Isso está funcionando como projetado porque os clientes precisam de uma maneira de verificar os relatórios do A4T, mesmo se a atividade não estiver ativa usando o modo de QA.

+++

## Por que o [!DNL Analytics] e o [!UICONTROL Analytics for Adobe Target] (A4T) calculam números para a métrica [!UICONTROL Unique Visitors] de forma diferente? {#section_0C3B648AB54041F9A2AA839D51791883}

+++Resposta
Quando você executa um teste A/B, que usa o [teste t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (a métrica de confiança) para escolher um vencedor de um teste, uma das premissas é que há um horizonte de tempo fixo. O teste não é estatisticamente válido a menos que você esteja olhando para esse tamanho fixo de amostra.

A métrica [!UICONTROL Unique Visitors] é diferente em [!DNL Analytics] e [!DNL Target] somente quando você está observando um período mais curto que o teste real. Se você não tiver atingido o tamanho da amostra, o teste não será tão confiável. Consulte [Como não executar um teste A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) no [site de Evan Miller](https://www.evanmiller.org/index.html) para obter mais informações.

A métrica [!UICONTROL Unique Visitors] exibe o número de pessoas que foram expostas ao teste que visitaram o site durante o período especificado. Essas pessoas fazem parte do teste e devem ser contadas. Se quiser ver apenas o número de pessoas que foram expostas durante uma única semana, você pode criar um segmento de visitantes que tiveram uma impressão de atividade e aplicá-lo ao relatório.

Você pode encurtar a quantidade de tempo que a variável [!DNL Target] persiste para uma sessão; no entanto, isso é problemático para testes em que o evento de conversão não tem a mesma probabilidade de ocorrer na mesma sessão.

+++

## Por que o mesmo visitante às vezes é contado em várias experiências no [!DNL Analytics]? {#section_1397E972D31C4207A142E4D2D6D794A2}

+++Resposta
A lista a seguir explica os motivos pelos quais o mesmo visitante pode ser contado em várias experiências no [!DNL Analytics]:

* O perfil [!DNL Target] expirou, mas o cookie [!DNL Analytics] ainda está lá. Nessa situação, [!DNL Target] reavalia o usuário, mas [!DNL Analytics] considera o visitante a mesma pessoa.
* Se o visitante estiver usando o `mbox3rdPartyId`, quando o visitante anônimo for mesclado ao perfil de ID de terceiros, o [!DNL Target] poderá colocar o visitante em uma experiência diferente para corresponder ao ID de terceiros. Para obter mais informações, consulte [Sincronização de perfil em tempo real para mbox3rdPartyID](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] pode estar rastreando diferentes dispositivos como o mesmo visitante de uma maneira diferente que [!DNL Target] rastreia esses dispositivos: a configuração da ID de terceiros em [!DNL Target] é diferente da configuração do Analytics.

+++

## O A4T suporta conjuntos de relatórios virtuais? {#virtual}

+++Resposta
Embora os conjuntos de relatórios virtuais não estejam incluídos na lista [!UICONTROL Report Suite], quaisquer dados A4T compartilhados com um conjunto de relatórios que esteja vinculado a um conjunto de relatórios virtual no [!DNL Analytics] terão acesso a esses dados. Observe que qualquer público criado a partir de um conjunto de relatórios virtual não pode ser compartilhado novamente com [!DNL Target].

+++

## É possível alterar a porcentagem da alocação de tráfego em uma atividade que usa o A4T depois de ativá-la?

+++Resposta
Alterar a porcentagem da alocação de tráfego em uma atividade após a ativação pode causar relatórios inconsistentes no [!DNL Analytics], pois a alteração afeta apenas os novos visitantes. Os visitantes recorrentes não são afetados.

Como prática recomendada, você deve interromper a atividade existente e criar uma nova atividade, em vez de alterar a porcentagem depois da ativação. Os relatórios para a nova atividade começam com os novos visitantes e os dados de visitantes recorrentes não causam relatórios inconsistentes.

+++

## Como as visitas são contadas em [!DNL Analytics] e o crédito de conversão é alocado em uma atividade [!UICONTROL Auto-Target] que usa o A4T?

+++Resposta
Quando um visitante é qualificado para, visualiza conteúdo ou converte em uma atividade A4T, [!DNL Target] envia dados do evento para [!DNL Analytics]. Estes dados de evento permitem que o [!DNL Analytics] atribua eventos de conversão e outros eventos de sequência de cliques que ocorrem na página às atividades e experiências relevantes do [!DNL Target].

Lembre-se de alguns pontos ao visualizar os relatórios de [!DNL Analytics]:

* Em geral, como prática recomendada, a janela de relatórios deve começar a partir da data de início da atividade.
* Se ocorrer uma conversão fora da janela do relatório, ela não estará visível em [!DNL Analytics].
* Quando estiver na parte &quot;direcionada&quot; do tráfego para [!UICONTROL Auto-Target] atividades, os visitantes poderão ver experiências diferentes de uma sessão para outra. Por exemplo, se o perfil ou contexto mudou e os algoritmos de aprendizado de máquina do [!DNL Target] decidem que têm mais probabilidade de ser convertidos em uma nova experiência. À medida que os visitantes mudam de experiência para experiência, a contagem de visitas é incrementada para cada experiência vista. Isso é diferente das atividades normais de Teste A/B, onde as experiências são fixas a um visitante nas visitas.
* Se um visitante visualizar várias experiências nas visitas, qualquer conversão será sempre atribuída à última experiência que o visitante viu. Como mencionado, a contagem de visitas aumenta para cada experiência que o visitante viu. Isso pode reduzir artificialmente as taxas de conversão por experiência ao exibir experiências na dimensão &quot;[!UICONTROL Targeted]&quot; nos relatórios [!DNL Adobe Analytics].

+++

## Como rastrear impressões de atividades no [!DNL Analysis Workspace] ao usar o [!UICONTROL Analytics for Target] (A4T)? {#activity-impressions}

+++Resposta

Para exibir as impressões da atividade em [!DNL Analysis Workspace]:

1. Na interface do usuário do [!DNL Target], clique em **[!UICONTROL View in Analytics]**.
1. Adicionar a coluna **[!UICONTROL Activity Impressions]** ao relatório [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html){target=_blank}.
1. Na coluna **[!UICONTROL Activity Impressions]**, clique no ícone [!UICONTROL Gear].
1. Clique em **[!UICONTROL Use non-default attribution model]**.
1. Selecione **[!UICONTROL Same Touch Model]** > **[!UICONTROL Apply]**.

+++
