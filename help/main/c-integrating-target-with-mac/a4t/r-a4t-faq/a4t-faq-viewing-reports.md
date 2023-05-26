---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; relatório; relatórios; exibir relatórios; relatórios; metodologia de contagem; impressões; visitantes; visitas; métrica padrão; conversões de atividade; não especificado
description: Encontre respostas para perguntas frequentes sobre como visualizar relatórios ao usar o Analytics para [!DNL Target] (A4T). O A4T permite usar os relatórios do Analytics para [!DNL Target] atividades.
title: Encontre respostas para perguntas sobre a exibição de relatórios com o A4T?
feature: Analytics for Target (A4T)
exl-id: a02eeb34-3975-424b-a046-e51f10ae1823
source-git-commit: 79ae58377c9eea0faca1ade11f2ab53da56b7bc1
workflow-type: tm+mt
source-wordcount: '2714'
ht-degree: 30%

---

# Exibição de relatórios - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre exibição de relatórios ao usar o [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T).

## Posso exibir meus [!DNL Target] dados da atividade em [!DNL Analysis Workspace]? {#workspace}

+++Resposta Você pode usar [!DNL Analysis Workspace] para analisar o [!DNL Target] atividades e experiências. A variável [Painel Analytics for Target](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=pt-BR) O permite ver o incentivo e a confiança para até três métricas de sucesso. Também é possível pesquisar mais usando tabelas e visualizações.

Para obter informações e exemplos detalhados, abra o [Tutorial do Analytics &amp; Target: práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido por [!UICONTROL Adobe Experience League].

+++

## Onde os segmentos podem ser aplicados no [!DNL Analysis Workspace]? {#segmentation}

+++Segmentos de resposta são usados com mais frequência na parte superior de um painel na área de soltar do segmento. O segmento é aplicado a todas as tabelas e visualizações no painel. Essa técnica é mais útil para ver como o teste afeta um subconjunto de pessoas (por exemplo, como esse teste foi executado para pessoas no Reino Unido)?

Um segmento também pode ser sobreposto diretamente na tabela de forma livre, mas observe que você deve sobrepô-lo na tabela inteira para preservar os cálculos de aumento e confiança no Painel A4T. No momento, os segmentos de nível de coluna não são compatíveis com o painel.

+++

## Posso aplicar o modelo &quot;Mesmo toque&quot; no Attribution IQ [!DNL Analysis Workspace]?

+++Atender ao usar [!DNL Target] impressões e conversões de atividades no [!DNL Analysis Workspace], aplique o modelo de Attribution IQ &quot;Mesmo toque&quot; às métricas para garantir uma contagem precisa. Para aplicar um [modelo de atribuição não padrão](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/build-workspace-project/column-row-settings/column-settings.html?lang=pt-BR), clique com o botão direito do mouse na métrica para **modificar Configurações de coluna > habilitar Usar modelo de atribuição não padrão > selecione Modelo de mesmo toque**. Sem esse modelo aplicado, as métricas são sobrescritas.

Todos os atuais [!DNL Adobe Analytics] os pacotes podem adicionar esse modelo com [!UICONTROL Attribution IQ]. Se você não tiver acesso ao [!UICONTROL Attribution IQ], confie nos dados do A4T em [!UICONTROL Reports &amp; Analytics].

+++

## Quando eu aplicar um segmento de ocorrência para um [!DNL Target] atividade, por que experiências não relacionadas são retornadas? {#activity-segmentation}

+++Responder A [!DNL Target] variável enviada para [!DNL Analytics] O tem um período de expiração padrão de 90 dias. (Observação: esse período de expiração pode ser ajustado pelo Atendimento ao cliente, se necessário). À medida que os visitantes navegam pelo site em toda essa janela de expiração, eles fazem parte de muitos [!DNL Target] atividades, todas coletadas na dimensão.

Ao segmentar para que uma atividade esteja presente em uma ocorrência, você obtém todas as experiências que fazem parte dessa atividade *mais* quaisquer outras experiências que persistam nessa ocorrência.

+++

## Ao configurar meu [!UICONTROL Métricas de meta], por que não posso acessar [!UICONTROL Configurações avançadas]?

+++Resposta Para atividades que usam o [!DNL Analytics] como fonte de relatórios (A4T), a métrica de meta usa o &quot;[!UICONTROL Incrementar contagem e manter usuário em atividade]&quot; e &quot;[!UICONTROL Em todas as impressões]&quot;. Essas configurações são *não* configurável.

Para obter mais informações, consulte &quot;Ao configurar minhas métricas de meta, por que não posso acessar as opções de Configurações avançadas?&quot; in [Definições de métricas - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Devo usar visitantes, visitas ou impressões de atividade como minha métrica de normalização (ou seja, metodologia de contagem)? {#metrics}

+++Resposta Há várias opções para normalizar métricas nos relatórios do A4T. Essa métrica, também conhecida como metodologia de contagem, torna-se o denominador do cálculo do incentivo. Além disso, afeta a maneira como os dados são agregados antes da aplicação do cálculo “confidence”.

* ***Visitantes únicos*** aumentam uma vez quando um usuário se qualifica primeiro para uma atividade.
* ***Visitas*** aumentam a cada sessão quando um usuário (Visitante único) insere uma atividade, mesmo se a atividade não for exibida em visitas subsequentes.
* ***Impressões de atividade*** aumentam sempre que o conteúdo da atividade é distribuído. (Medido por [!DNL Target]).

Quando um visitante exibe uma página que contém uma atividade, uma variável é definida para esse visitante e contém o nome dessa atividade. Veja os cenários detalhados abaixo sobre como cada metodologia de contagem é comparada.

Considere o seguinte:

* As métricas acima são acionadas quando um usuário se qualifica para uma atividade e o conteúdo é retornado do [!DNL Target]. Isso não significa necessariamente que o usuário viu a oferta. Se uma experiência de atividade estiver abaixo da dobra e o usuário não rolar a página para baixo, a oferta foi distribuída pelo [!DNL Target], mas não foi vista pelo usuário.
* [!UICONTROL Impressões de atividade] (medidas pelo [!DNL Target]) e [!UICONTROL Instâncias] (medidas pelo [!DNL Analytics]) são iguais, a menos que haja várias chamadas de mbox na mesma página e na mesma atividade. Isso faz com que várias [!UICONTROL Impressões de atividade] sejam contadas, mas somente uma única [!UICONTROL Instância].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html?lang=pt-BR) in *Adobe Target Tutorials*.

+++

## Por que as &quot;impressões de atividades&quot; e as &quot;conversões de atividades&quot; são maiores em [!DNL Analysis Workspace] do que [!UICONTROL Reports &amp; Analytics]? {#sametouch}

+++Resposta
[!DNL Reports & Analytics] aplica um modelo de atribuição do mesmo toque a &quot;impressões de atividade&quot; e &quot;conversões de atividade&quot;, enquanto [!DNL Analysis Workspace] exibe as métricas brutas, que podem parecer infladas devido à persistência das [!DNL Target] dimensão.

Para avaliar a precisão [!UICONTROL Impressões da atividade] e [!UICONTROL Conversões de atividade] métricas no [!DNL Analysis Workspace], verifique se ambas as métricas [!UICONTROL Mesmo contato] modelos de atribuição aplicados. Os modelos podem ser aplicados clicando na engrenagem das configurações de coluna, ativando [!UICONTROL Modelos de atribuição não padrão] e selecionando o [!UICONTROL Mesmo toque]. Saiba mais sobre atribuição em [Visão geral do Attributes IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) no *Guia de ferramentas do Analytics*.

+++

## O que significa &quot;conversões de atividade&quot; se o profissional de marketing escolher um [!DNL Analytics] durante a configuração da atividade? {#section_F3EBACF85AF846E9B366A549AAB64356}

+++Resposta &quot;Conversões de atividade&quot; ficam vazias se um [!DNL Analytics] foi selecionada como a métrica de conversão para a atividade.

+++

## Por que vejo &quot;não especificado&quot; na variável [!DNL Analytics] relatórios? O que isso significa?  {#unspecified}

+++Resposta Em outros relatórios, &quot;não especificado&quot; significa que os dados não atenderam a uma regra de classificação, mas no A4T isso nunca deve acontecer. Se você vir &quot;não especificado&quot;, o serviço de classificação ainda não foi executado. Em geral, pode levar entre 24 e 72 horas para que os dados da atividade apareçam nos relatórios. Mesmo que as atividades não apareçam neste relatório até esse momento, todos os dados de visitantes vinculados a essas atividades serão capturados e exibidos quando a classificação for concluída.

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

Caso a classificação tenha sido feita para aquela atividade e você ainda vir uma linha &quot;Não especificado&quot; no relatório, verifique se ele não está usando um parâmetro não-[!DNL Target] para exibir os dados. A menos que o relatório esteja usando um [!DNL Target]-específica, que a linha &quot;Não especificado&quot; contém eventos para chamadas que não estão associadas a [!DNL Target]. Essa linha não conterá nenhuma [!DNL Target]Informações associadas ao (por exemplo, visitantes/visitas/impressões).

+++

## Por que [!DNL Target] métricas enviadas para o [!DNL Analytics] mesmo depois de a atividade ter sido desativada? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

+++Responder A [!DNL Target] variável enviada para [!DNL Analytics] O tem um período de expiração padrão de 90 dias. Esse período de expiração pode ser ajustado pelo Atendimento ao cliente, se necessário. Essa configuração é global para todas as atividades; no entanto, não deve ser ajustada para um caso.

Você pode ver [!DNL Target] variáveis enviadas para [!DNL Analytics] após o período de expiração, pois a expiração é de 90 dias, mas somente se esse usuário nunca vir outro A4T habilitado [!DNL Target] atividade. Se um usuário voltar ao site no dia 45 e vir outra atividade, todo o valor eVar do A4T terá seu contador redefinido para 90 dias. Isso significa que a primeira campanha do dia 1 agora pode persistir por até 45 + 90 = 135 dias. Se o usuário continuar voltando, você pode chegar ao ponto em que vê as métricas enviadas para o [!DNL Analytics] em seus relatórios de atividades muito mais antigas. À medida que os usuários excluem cookies e não retornam ao site, os números nessa atividade caem, mas você ainda pode vê-los.

Isso significa que as atividades continuam a obter exibições de página, visitas e assim por diante, por até 90 dias após o término da atividade para visitantes que se tornaram parte da atividade enquanto ela estava ativa. No entanto, se você observar a métrica [!UICONTROL Impressões de atividades], não verá impressões depois que a atividade terminar.

Esse é um comportamento normal e esperado. A variável A4T funciona como qualquer outro eVar. O valor é associado ao usuário até atingir o período de expiração (90 dias). Como resultado, se uma atividade estiver ativa por apenas duas semanas, o valor ainda será associado ao usuário pelos próximos 90 dias.

A prática recomendada é ver relatórios para essa atividade apenas durante o período em que a atividade foi ao vivo. As datas devem ser definidas corretamente por padrão ao visualizar a atividade em [!DNL Analytics], portanto, a menos que você tenha estendido manualmente a data, isso não deve ser um problema do ponto de vista do relatório.

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

Como ambas as experiências foram vistas antes da conversão, ambas recebem &quot;crédito&quot; pelo pedido. Mas, apenas um pedido ocorreu no sistema e o total reflete isso. Para [!DNL Target] relatório, porque você não está colocando um [!DNL Target] atividade em relação a outra atividade para ver qual é mais bem-sucedido, não importa se todas as atividades que o usuário viu receberam crédito. Você está comparando os resultados de dois itens em uma única atividade. Não é possível para um usuário ver experiências diferentes na mesma atividade, de modo que você não precisa se preocupar com a contaminação cruzada do crédito do pedido.

Para obter mais informações, consulte [Variáveis de conversão (eVar)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) no *Guia de administração do Analytics*.

+++

## Por que continuo vendo mais impressões depois que minha atividade é desativada? {#deactivated}

+++Resposta Uma fonte de impressões para um relatório de atividade do A4T após a desativação pode ser tráfego no modo de QA. O Target normalmente não registra eventos para uma atividade desativada, mas o Analytics não tem uma maneira de saber que as impressões vêm do modo de QA. Quando o relatório de atividade do Target é recuperado do Analytics, ele mostra essas impressões. Isso está funcionando como projetado porque os clientes precisam de uma maneira de verificar os relatórios do A4T, mesmo se a atividade não estiver ativa usando o modo de QA.

+++

## Por que [!DNL Analytics] e [!UICONTROL Analytics para Adobe Target] (A4T) calcule números para o [!UICONTROL Visitantes únicos] métrica de forma diferente? {#section_0C3B648AB54041F9A2AA839D51791883}

+++Resposta Ao executar um teste A/B, que usa o método [Teste t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} (a métrica de confiança) para escolher um vencedor de um teste, uma das suposições é que haja um horizonte de tempo fixo. O teste não é estatisticamente válido a menos que você esteja observando o tamanho fixo da amostra.

A variável [!UICONTROL Visitantes únicos] a métrica é diferente em [!DNL Analytics] e [!DNL Target] somente quando você estiver observando um período menor do que o teste real. Se você não tiver atingido o tamanho da amostra, o teste não será tão confiável. Consulte [Como não executar um teste A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) no [site de Evan Miller](https://www.evanmiller.org/index.html) para obter mais informações.

A variável [!UICONTROL Visitantes únicos] métrica exibe o número de pessoas que foram expostas ao teste que visitaram o site durante o período especificado. Essas pessoas fazem parte do teste e devem ser contadas. Se quiser ver apenas o número de pessoas que foram expostas durante uma única semana, você pode criar um segmento de visitantes que tiveram uma impressão de atividade e aplicá-lo ao relatório.

Você pode reduzir a quantidade de tempo que o [!DNL Target] persiste até uma sessão; no entanto, isso é problemático para testes em que o evento de conversão não tem a mesma probabilidade de ocorrer na mesma sessão.

+++

## Por que o mesmo visitante às vezes é contado em várias experiências no [!DNL Analytics]? {#section_1397E972D31C4207A142E4D2D6D794A2}

+++Resposta A lista a seguir explica os motivos pelos quais um mesmo visitante pode ser contado em várias experiências no [!DNL Analytics]:

* A variável [!DNL Target] o perfil expirou, mas a variável [!DNL Analytics] o cookie ainda está lá. Nesta situação, [!DNL Target] reavalia o usuário, mas [!DNL Analytics] O considera o visitante a mesma pessoa.
* Se o visitante estiver usando a variável `mbox3rdPartyId`, quando o visitante anônimo é mesclado com o perfil de ID de terceiros, [!DNL Target] O pode colocar o visitante em uma experiência diferente para corresponder à ID de terceiros. Para obter mais informações, consulte [Sincronização de perfil em tempo real para mbox3rdPartyID](/help/main/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] pode estar rastreando diferentes dispositivos como o mesmo visitante de uma maneira diferente da [!DNL Target] rastreia esses dispositivos: a configuração da ID de terceiros no [!DNL Target] é diferente do Analytics.

+++

## O A4T suporta conjuntos de relatórios virtuais? {#virtual}

+++Resposta Embora os conjuntos de relatórios virtuais não estejam incluídos no [!UICONTROL Report Suite] , quaisquer dados A4T compartilhados com um conjunto de relatórios que esteja vinculado a um conjunto de relatórios virtual no [!DNL Analytics] tem acesso a esses dados. Observe que qualquer público-alvo criado a partir de um conjunto de relatórios virtual não pode ser compartilhado de volta para [!DNL Target].

+++

## É possível alterar a porcentagem da alocação de tráfego em uma atividade que usa o A4T depois de ativá-la?

+++Resposta Alterar a porcentagem da alocação de tráfego em uma atividade após a ativação pode causar relatórios inconsistentes no [!DNL Analytics] porque a alteração afeta somente os novos visitantes. Os visitantes recorrentes não são afetados.

Como prática recomendada, você deve interromper a atividade existente e criar uma nova atividade, em vez de alterar a porcentagem depois da ativação. Os relatórios para a nova atividade começam com os novos visitantes e os dados de visitantes recorrentes não causam relatórios inconsistentes.

+++

## Como as visitas são contadas no [!DNL Analytics] e crédito de conversão atribuídos em um [!UICONTROL Direcionamento automático] atividade que usa o A4T?

+++Resposta Quando um visitante é qualificado para, visualiza conteúdo ou converte em uma atividade A4T, [!DNL Target] envia dados do evento para o [!DNL Analytics]. Esses dados do evento permitem [!DNL Analytics] para atribuir eventos de conversão e outros eventos de sequência de cliques que ocorrem na página ao relevante [!DNL Target] atividades e experiências.

Lembre-se de alguns pontos ao visualizar [!DNL Analytics] relatórios:

* Em geral, como prática recomendada, a janela de relatórios deve começar a partir da data de início da atividade.
* Se uma conversão ocorrer fora da janela do relatório, a conversão não estará visível no [!DNL Analytics].
* Quando estiver na parte &quot;direcionada&quot; do tráfego para [!UICONTROL Direcionamento automático] atividades, os visitantes podem ver experiências diferentes de uma sessão para outra. Por exemplo, se o perfil ou contexto tiver sido alterado e [!DNL Target]Os algoritmos de aprendizado de máquina do decidem que têm mais probabilidade de conversão em uma nova experiência. À medida que os visitantes mudam de experiência para experiência, a contagem de visitas é incrementada para cada experiência vista. Isso é diferente das atividades normais de Teste A/B, onde as experiências são fixas a um visitante nas visitas.
* Se um visitante visualizar várias experiências nas visitas, qualquer conversão será sempre atribuída à última experiência que o visitante viu. Como mencionado, a contagem de visitas aumenta para cada experiência que o visitante viu. Isso pode reduzir artificialmente as taxas de conversão por experiência ao visualizar experiências na &quot;[!UICONTROL Direcionado]dimensão &quot; em [!DNL Adobe Analytics] relatórios.

+++

## Como rastrear impressões de atividade no [!DNL Analysis Workspace] ao usar o [!UICONTROL Analytics for Target] (A4T)? {#activity-impressions}

+++Resposta

Para exibir impressões de atividades no [!DNL Analysis Workspace]:

1. No [!DNL Target] Interface, clique em **[!UICONTROL Exibir no Analytics]**.
1. Adicione o **[!UICONTROL Impressões da atividade]** para a [[!DNL Analytics Workspace]](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/home.html){target=_blank} relatório.
1. No **[!UICONTROL Impressões da atividade]** clique na guia [!UICONTROL Engrenagem] ícone.
1. Clique em **[!UICONTROL Usar modelo de atribuição não-padrão]**.
1. Selecionar **[!UICONTROL Modelo do mesmo toque]** > **[!UICONTROL Aplicar]**.

+++