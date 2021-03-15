---
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; relatório; relatórios; exibir relatórios; relatórios; metodologia de contagem; impressões; visitantes; visitas; métrica padrão; conversões de atividade; não especificado
description: Encontre respostas para as perguntas mais frequentes sobre a exibição de relatórios ao usar o Analytics for Target (A4T). O A4T permite usar os relatórios do Analytics para as atividades do Target.
title: Encontrar respostas para perguntas sobre como visualizar relatórios com o A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: 29df46273639b87f10502e8d9f04d2bc429637f9
workflow-type: tm+mt
source-wordcount: '2434'
ht-degree: 40%

---


# Exibição de relatórios - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre como visualizar relatórios ao usar [!DNL Adobe Analytics] como fonte de relatórios para [!DNL Adobe Target] (A4T).

## Posso exibir meus dados de atividade do Target na Analysis Workspace? {#workspace}

Você pode usar [!DNL Analysis Workspace] para analisar suas atividades e experiências [!DNL Target]. O [painel Analytics for Target](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) permite que você veja o incentivo e a confiança de até três métricas de sucesso. Também é possível pesquisar mais fundo usando tabelas e visualizações.

Para obter informações e exemplos detalhados, abra o [Analytics &amp; Target: Tutorial de práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido pela Adobe Experience League.

## Onde os segmentos podem ser aplicados na Analysis Workspace? {#segmentation}

Os segmentos são usados com mais frequência na parte superior de um painel na área de soltar segmentos. O segmento é aplicado a todas as tabelas e visualizações no painel. Essa técnica é mais útil para ver como o teste afeta um subconjunto de pessoas (por exemplo, como esse teste funcionou para pessoas no Reino Unido)?

Um segmento também pode ser colocado diretamente na tabela de forma livre, mas observe que você deve sobrepô-lo em toda a tabela para preservar os cálculos de incentivo e confiança no painel A4T. Os segmentos de nível de coluna não são suportados atualmente no painel.

## Quando eu aplico um segmento de ocorrência para uma atividade específica do Target, por que as experiências não relacionadas são retornadas? {#activity-segmentation}

A variável do [!DNL Target] enviada para o [!DNL Analytics] tem um período de expiração padrão de 90 dias. (Observação: esse período de expiração pode ser ajustado pelo Atendimento ao cliente (se necessário). À medida que os visitantes navegam pelo site durante essa janela de expiração, eles fazem parte de muitas [!DNL Target] atividades, todas coletadas na dimensão.

Ao segmentar para que uma atividade esteja presente em uma ocorrência, você obtém todas as experiências que fazem parte dessa atividade *mais* quaisquer outras experiências que persistem nessa ocorrência.

## Ao configurar minhas Métricas de meta, por que não posso acessar as Configurações avançadas?

Para atividades que usam [!DNL Analytics] como fonte de relatórios (A4T), a métrica de meta usa as configurações &quot;[!UICONTROL Aumentar contagem e manter o usuário na atividade]&quot; e &quot;[!UICONTROL Em todas as impressões]&quot;. Essas configurações são *não* configuráveis.

Para obter mais informações, consulte &quot;Ao configurar minhas métricas de meta, por que não posso acessar as opções de Configurações avançadas?&quot; em [Definições de métrica - Perguntas frequentes sobre o A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Devo usar visitantes, visitas ou impressões de atividades como minha métrica de normalização (ou seja, metodologia de contagem)? {#metrics}

Há várias opções para normalizar métricas nos relatórios do A4T. Essa métrica, também chamada de metodologia de contagem, torna-se o denominador do cálculo do incentivo. Além disso, afeta a maneira como os dados são agregados antes da aplicação do cálculo “confidence”.

* ***Visitantes únicos*** aumentam uma vez quando um usuário se qualifica primeiro para uma atividade.
* ***Visitas*** aumentam a cada sessão quando um usuário (Visitante único) insere uma atividade, mesmo se a atividade não for exibida em visitas subsequentes.
* ***Impressões de atividade*** aumentam sempre que o conteúdo da atividade é distribuído. (Medido por [!DNL Target]).

Quando um visitante exibe uma página que contém uma atividade, uma variável é definida para esse visitante e contém o nome dessa atividade. Veja os cenários detalhados abaixo sobre como cada metodologia de contagem é comparada.

Considere o seguinte:

* As métricas acima são acionadas quando um usuário se qualifica para uma atividade e o conteúdo é retornado de [!DNL Target]. Isso não significa necessariamente que o usuário viu a oferta. Se uma experiência de atividade estiver abaixo da dobra e o usuário não rolar a página para baixo, a oferta foi distribuída pelo [!DNL Target], mas não foi vista pelo usuário.
* [!UICONTROL Impressões de atividade] (medidas pelo [!DNL Target]) e [!UICONTROL Instâncias] (medidas pelo [!DNL Analytics]) são iguais, a menos que haja várias chamadas de mbox na mesma página e na mesma atividade. Isso faz com que várias [!UICONTROL Impressões de atividade] sejam contadas, mas somente uma única [!UICONTROL Instância].

Para obter mais informações, consulte [Como configurar relatórios do A4T no Analysis Workspace para atividades de Direcionamento automático](https://experienceleague.adobe.com/docs/target-learn/tutorials/integrations/set-up-a4t-reports-in-analysis-workspace-for-auto-target-activities.html) em *Adobe Target Tutorials*.

## Por que as &quot;impressões de atividade&quot; e as &quot;conversões de atividade&quot; são mais altas no Analysis Workspace do que no Reports &amp; Analytics? {#sametouch}

[!DNL Reports & Analytics] aplica um modelo de atribuição de mesmo toque a &quot;impressões de atividade&quot; e &quot;conversões de atividade&quot;, enquanto  [!DNL Analysis Workspace] exibe as métricas brutas, que podem aparecer infladas devido à persistência da  [!DNL Target] dimensão.

Para avaliar métricas precisas [!UICONTROL Impressões de atividade] e [!UICONTROL Conversões de atividade] em [!DNL Analysis Workspace], verifique se ambas as métricas têm modelos de atribuição [!UICONTROL Mesmo toque] aplicados. Os modelos podem ser aplicados clicando na engrenagem das configurações de coluna, ativando [!UICONTROL Modelos de atribuição não padrão] e selecionando o [!UICONTROL Mesmo toque]. Saiba mais sobre atribuição em [Visão geral do IQ de atributos](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) no *Guia de Ferramentas do Analytics*.

## O que significa &quot;conversões de atividade&quot; se o profissional de marketing escolher uma métrica do Analytics durante a configuração da atividade? {#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Conversões de atividade&quot; ficam vazias se uma métrica [!DNL Analytics] foi selecionada como a métrica de conversão da atividade.

## Por que vejo &quot;não especificado&quot; nos relatórios do Analytics? O que isso significa?   {#unspecified}

Em outros relatórios, &quot;não especificado&quot; significa que os dados não atendem a uma regra de classificação, mas no A4T isso nunca deve acontecer. Se você vir &quot;não especificado&quot;, o serviço de classificação ainda não foi executado. Em geral, pode levar entre 24 e 72 horas para que os dados da atividade apareçam nos relatórios. Mesmo que as atividades não apareçam neste relatório até esse momento, todos os dados de visitantes vinculados a essas atividades serão capturados e aparecerão quando a classificação estiver concluída.

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

Caso a classificação tenha sido feita para essa atividade e você ainda veja uma linha &quot;Não especificado&quot; no relatório, verifique se o relatório não está usando uma métrica não [!DNL Target] para exibir os dados. A menos que o relatório esteja usando uma métrica específica de [!DNL Target], essa linha &quot;Não especificado&quot; contém eventos para chamadas que não estão associadas a [!DNL Target]. Essa linha não conterá informações [!DNL Target] associadas (por exemplo, visitantes/visitas/impressões).

## Por que as métricas do Target são enviadas ao Analytics mesmo após a desativação da atividade? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

A variável do [!DNL Target] enviada para o [!DNL Analytics] tem um período de expiração padrão de 90 dias. Esse período de expiração pode ser ajustado pelo Atendimento ao cliente, se necessário. Essa configuração é global para todas as atividades, no entanto, não deve ser ajustada para um caso.

Você pode ver variáveis [!DNL Target] enviadas para [!DNL Analytics] após o período de expiração, pois a expiração é de 90 dias, mas somente se esse usuário nunca vir outra atividade [!DNL Target] habilitada para A4T. Se um usuário voltar ao site no dia 45 e vir outra atividade, todo o valor eVar do A4T terá seu contador redefinido para 90 dias. Isso significa que a primeira campanha do dia 1 agora pode persistir por até 45 + 90 = 135 dias. Se o usuário continuar voltando, você pode chegar ao ponto em que vê as métricas enviadas para [!DNL Analytics] em seu relatório de atividades muito mais antigas. À medida que os usuários excluem cookies e não retornam ao site, os números dessa atividade caem, mas você ainda pode visualizá-los.

Isso significa que as atividades continuam a ter exibições de página, visitas e assim por diante, por até 90 dias após o término da atividade para visitantes que se tornaram parte da atividade enquanto ela estava ativa. No entanto, se você observar a métrica [!UICONTROL Impressões de atividades], não verá impressões depois que a atividade terminar.

Esse é um comportamento normal e esperado. A variável A4T funciona como qualquer outro eVar. O valor é associado ao usuário até atingir o período de expiração (90 dias). Como resultado, se uma atividade estiver ativa por apenas duas semanas, o valor ainda será associado ao usuário por pelo menos os próximos 90 dias.

A prática recomendada é ver relatórios para essa atividade apenas durante o período em que a atividade foi ao vivo. As datas devem ser definidas corretamente por padrão ao visualizar a atividade em [!DNL Analytics], portanto, a menos que você tenha estendido manualmente a data, isso não deve ser um problema do ponto de vista do relatório.

Como exemplo, vamos supor que a variável A4T expire após 90 dias e o teste esteja ativo de 1 de janeiro a 15 de janeiro.

Em 1 de janeiro, o usuário acessa o site e vê a atividade XYZ uma vez e tem cinco exibições de página depois disso. Nas próximas duas semanas, o usuário nunca retorna ao site. Os dados ficariam assim para este usuário:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 3 |

O usuário retorna em 1 de fevereiro, visualiza mais cinco páginas e não encontra mais nenhuma atividade do Target e a atividade original não está mais ativa. Mesmo que a atividade não esteja mais ativa, ela ainda está seguindo o usuário por meio da persistência de eVar. Agora os dados ficam assim:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 3 | 10 | 2 | 3 |

O usuário volta em 1 de março e vê uma nova atividade, ABC. O usuário também visualiza cinco páginas. Como a atividade XYZ ainda segue o usuário por meio da persistência, e esse usuário tem ABC definido, você verá dois itens de linha no relatório:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 3 | 15 | 3 | 3 |
| ABC | 3 | 5 | 3 | 1 |

O usuário volta em 1 de abril, visualiza outras cinco páginas e faz uma compra. A expiração de 90 dias desse valor de eVar é redefinida em 1 de abril, portanto, você vê isso nos relatórios. E todas as atividades do Target que o usuário vê recebem o crédito pela conversão, mas o número total de conversões é deduplicado:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos | Pedidos |
|--- |--- |--- |--- |--- |--- |
| XYZ | 3 | 20 | 4 | 3 | 1 |
| ABC | 1 | 10º | 2 | 3 | 3 |
| Total | 2 | 20º | 3 | 3 | 3 |

Como ambas as experiências foram vistas antes da conversão, ambas recebem &quot;crédito&quot; pelo pedido. Mas, apenas um pedido ocorreu no sistema e o total reflete isso. Para relatórios [!DNL Target], como você não está colocando uma atividade [!DNL Target] em relação a outra atividade para ver qual é mais bem sucedida, não importa que todas as atividades que o usuário viu recebam crédito. Você está comparando os resultados de dois itens na atividade única. Não é possível que um usuário veja experiências diferentes na mesma atividade para que você não tenha que se preocupar com a contaminação cruzada do crédito do pedido.

Para obter mais informações, consulte [Variáveis de conversão (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) no *Guia de administração do Analytics*.

## Por que o Analytics e o Analytics for Target (A4T) calculam números para a métrica de visitantes únicos de maneira diferente? {#section_0C3B648AB54041F9A2AA839D51791883}

Quando você executa um teste A/B, que usa o teste t de Estudante (a métrica de confiança) para escolher um vencedor de um teste, uma das suposições é que existe um horizonte de tempo fixo. O teste não é estatisticamente válido, a menos que você esteja olhando para esse tamanho de amostra fixo.

A métrica [!UICONTROL Visitantes únicos] é diferente em [!DNL Analytics] e [!DNL Target] somente quando você está olhando para um período menor que o teste real. Se você não atingiu o tamanho da amostra, o teste não é tão confiável. Consulte [Como não executar um teste A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) no [site de Evan Miller](https://www.evanmiller.org/index.html) para obter mais informações.

A métrica [!UICONTROL Visitantes únicos] exibe o número de pessoas que foram expostas ao teste que visitaram o site durante o período de tempo especificado. Essas pessoas fazem parte do teste e devem ser contadas. Se quiser ver apenas o número de pessoas que foram expostas durante uma única semana, você pode criar um segmento de visitantes que tiveram uma impressão de atividade e aplicá-lo ao relatório.

Você pode encurtar o tempo em que a variável [!DNL Target] persiste até uma sessão; no entanto, isso é problemático para testes em que o evento de conversão não é tão provável de acontecer na mesma sessão.

## Por que o mesmo visitante às vezes é contado em várias experiências no Analytics?   {#section_1397E972D31C4207A142E4D2D6D794A2}

A lista a seguir explica os motivos pelos quais o mesmo visitante pode ser contado em várias experiências no [!DNL Analytics]:

* O perfil [!DNL Target] expirou, mas o cookie [!DNL Analytics] ainda está lá. Nessa situação, [!DNL Target] reavalia o usuário, mas [!DNL Analytics] considera o visitante como a mesma pessoa.
* Se o visitante estiver usando o `mbox3rdPartyId`, quando o visitante anônimo for mesclado ao perfil de ID de terceiros, [!DNL Target] poderá colocar o visitante em uma experiência diferente para corresponder ao ID de terceiros. Para obter mais informações, consulte [Sincronização de perfil em tempo real para mbox3rdPartyID](/help/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] O pode estar rastreando diferentes dispositivos como o mesmo visitante de uma maneira diferente que  [!DNL Target] rastreia esses dispositivos: a configuração da ID de terceiros no  [!DNL Target] é diferente da configuração do Analytics.

## O A4T suporta conjuntos de relatórios virtuais?

Os conjuntos de relatórios virtuais *não* estão incluídos na lista de Conjunto de relatórios e os públicos-alvo de conjuntos de relatórios virtuais não são suportados nos relatórios A4T.

## É possível alterar a porcentagem da alocação de tráfego em uma atividade que usa o A4T depois de ativá-la?

Alterar a porcentagem da alocação de tráfego em uma atividade após a ativação pode causar relatórios inconsistentes em [!DNL Analytics] porque a alteração afeta apenas novos visitantes. Os visitantes recorrentes não são afetados.

Como prática recomendada, você deve interromper a atividade existente e criar uma nova atividade, em vez de alterar a porcentagem depois da ativação. Os relatórios para a nova atividade começam com novos visitantes e os dados de visitantes recorrentes não causam relatórios inconsistentes.

## Como as visitas são contadas no Analytics e o crédito de conversão são alocados em uma atividade de Direcionamento automático que usa o A4T?

Quando um visitante se qualifica para, exibe conteúdo ou converte em uma atividade A4T, [!DNL Target] envia dados de evento para [!DNL Analytics]. Esses dados de evento permitem que [!DNL Analytics] atribua eventos de conversão e outros eventos de sequência de cliques que ocorrem na página às atividades e experiências [!DNL Target] relevantes.

Estes são alguns pontos para ter em mente ao visualizar relatórios [!DNL Analytics]:

* Em geral, como uma prática recomendada, sua janela de relatórios deve começar a partir da data de início da atividade.
* Se uma conversão ocorrer fora da janela do relatório, a conversão não estará visível em [!DNL Analytics].
* Quando na parte &quot;direcionada&quot; do tráfego para atividades de [!UICONTROL Direcionamento automático], os visitantes podem ver experiências diferentes de uma sessão para a próxima. Por exemplo, se o perfil ou contexto mudou e os algoritmos de aprendizado de máquina de [!DNL Target] decidem que têm mais probabilidade de conversão em uma nova experiência. Conforme os visitantes mudam de experiência para experiência, a contagem de visitas é incrementada para cada experiência vista. Isso não é parecido com atividades comuns de Teste A/B, onde as experiências são aderentes a um visitante em visitas.
* Se um visitante visualizar várias experiências em visitas, qualquer conversão será sempre atribuída à última experiência que o visitante viu. Conforme mencionado, a contagem de visitas é incrementada para cada experiência que o visitante viu. Isso pode reduzir artificialmente as taxas de conversão por experiência ao visualizar experiências na dimensão &quot;[!UICONTROL Segmentado]&quot; nos relatórios [!DNL Adobe Analytics].
