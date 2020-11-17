---
keywords: faq;frequently asked questions;analytics for target;a4T;report;reports;view reports;reporting;counting methodology;impressions;visitors;visits;default metric;activity conversions;unspecified
description: Este tópico contém respostas para perguntas frequentes sobre como visualizar relatórios ao usar o Analytics como a origem de geração de relatórios do Target (A4T).
title: Exibição de relatórios - Perguntas frequentes sobre o A4T
feature: a4t troubleshooting
translation-type: tm+mt
source-git-commit: 7ad57c6f3814140df0826f57d8052f6db3fda301
workflow-type: tm+mt
source-wordcount: '2196'
ht-degree: 58%

---


# Exibição de relatórios - Perguntas frequentes sobre o A4T

This topic contains answers to questions that are frequently asked about viewing reports when using [!DNL Analytics] as the reporting source for [!DNL Target] (A4T).

## Posso exibir meus dados de atividade do Target na Analysis Workspace? {#workspace}

Você pode usar [!DNL Analysis Workspace] para analisar suas [!DNL Target] atividades e experiências. O painel [](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) Analytics for Público alvo permite que você veja incentivo e confiança para até três métricas de sucesso. Você também pode pesquisar mais fundo usando tabelas e visualizações.

For detailed information and examples, open the [Analytics &amp; Target: Best Practices for Analysis tutorial](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), provided by Adobe Experience League.

## Onde os segmentos podem ser aplicados no Analysis Workspace? {#segmentation}

Os segmentos são aplicados com mais frequência à parte superior de um painel na área de segmentos. O segmento é aplicado a todas as tabelas e visualizações no painel. Esta técnica é mais útil para ver como o teste afeta um subgrupo de pessoas (por exemplo, como esse teste funcionou para pessoas no Reino Unido)?

## Quando eu aplico um segmento de ocorrência para uma atividade de Público alvo específica, por que vejo experiências não relacionadas retornadas? {#activity-segmentation}

A variável do [!DNL Target] enviada para o [!DNL Analytics] tem um período de expiração padrão de 90 dias. (Observação: esse período de expiração pode ser ajustado pelo Atendimento ao cliente, se necessário). À medida que os visitantes navegam pelo site durante essa janela de expiração, eles fazem parte de muitas [!DNL Target] atividades, todas coletadas na dimensão.

Como resultado, ao segmentar para que uma atividade esteja presente em uma ocorrência, você obterá todas as experiências que fazem parte dessa atividade, *além* de quaisquer outras experiências que persistem nessa ocorrência.

## Devo usar visitantes, visitas ou impressões atividades como minha métrica de normalização (ou seja, metodologia de contagem)? {#metrics}

Existem várias opções para normalizar métricas no relatórios A4T. Essa métrica, também chamada de metodologia de contagem, torna-se o denominador do cálculo do incentivo. Além disso, afeta a maneira como os dados são agregados antes da aplicação do cálculo “confidence”.

* ***Visitantes únicos*** aumentam uma vez quando um usuário se qualifica primeiro para uma atividade.
* ***Visitas*** aumentam a cada sessão quando um usuário (Visitante único) insere uma atividade, mesmo se a atividade não for exibida em visitas subsequentes.
* ***Impressões de atividade*** aumentam sempre que o conteúdo da atividade é distribuído. (Medido por [!DNL Target]).

Quando um visitante exibe uma página que contém uma atividade, uma variável é definida para esse visitante e contém o nome dessa atividade. Veja os cenários detalhados abaixo sobre como cada metodologia de contagem é comparada.

Considere o seguinte:

* All of the above metrics trigger when a user qualifies for an activity and content is returned from [!DNL [!DNL Target]]. Isso não significa necessariamente que o usuário viu a oferta. Se uma experiência de atividade estiver abaixo da dobra e o usuário não rolar a página para baixo, a oferta foi distribuída pelo [!DNL Target], mas não foi vista pelo usuário.
* [!UICONTROL Impressões de atividade] (medidas pelo [!DNL Target]) e [!UICONTROL Instâncias] (medidas pelo [!DNL Analytics]) são iguais, a menos que haja várias chamadas de mbox na mesma página e na mesma atividade. Isso faz com que várias [!UICONTROL Impressões de atividade] sejam contadas, mas somente uma única [!UICONTROL Instância].

## Por que as &quot;impressões de atividade&quot; e &quot;conversões de atividade&quot; são mais altas no Analysis Workspace do que no Relatórios e análises? {#sametouch}

[!DNL Reports & Analytics] aplica um modelo de atribuição de mesmo toque a &quot;impressões de atividade&quot; e &quot;conversões de atividade&quot;, enquanto [!DNL Analysis Workspace] exibe as métricas brutas, que podem aparecer infladas devido à persistência da [!DNL Target] dimensão.

To evaluate accurate [!UICONTROL Activity Impressions] and [!UICONTROL Activity Conversions] metrics in [!DNL Analysis Workspace], ensure that both metrics have [!UICONTROL Same Touch] attribution models applied. Os modelos podem ser aplicados clicando na engrenagem das configurações de coluna, ativando [!UICONTROL Modelos de atribuição não padrão] e selecionando o [!UICONTROL Mesmo toque]. Saiba mais sobre atribuição na visão geral [do IQ de](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/attribution.html) atributos no Guia *de ferramentas do* Analytics.

## O que significa &quot;conversões de atividade&quot; se o profissional de marketing escolher uma métrica do Analytics durante a configuração da atividade? {#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Activity conversions&quot; will be empty if an [!DNL Analytics] metric was selected as the conversion metric for the activity.

## Por que vejo &quot;não especificado&quot; nos relatórios do Analytics? O que isso significa?  {#unspecified}

Em outros relatórios, &quot;não especificado&quot; significa que os dados não atendem a uma regra de classificação, mas no A4T isso nunca deve acontecer. Se você vir &quot;não especificado&quot;, o serviço de classificação ainda não foi executado. Em geral, pode levar entre 24 e 72 horas para que os dados da atividade apareçam nos relatórios. Mesmo que as atividades não apareçam neste relatório até esse momento, todos os dados de visitantes vinculados a essas atividades serão capturados e aparecerão quando a classificação estiver concluída.

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

## Por que as métricas do Target são enviadas ao Analytics mesmo após a desativação da atividade? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

A variável do [!DNL Target] enviada para o [!DNL Analytics] tem um período de expiração padrão de 90 dias. Esse período de expiração pode ser ajustado pelo Atendimento ao cliente, se necessário. Essa configuração é global para todas as atividades, no entanto, não deve ser ajustada para um caso.

You might see [!DNL Target] variables sent to [!DNL Analytics] after the expiration period because the expiration is 90 days, but only if that user never sees another A4T-enabled [!DNL Target] activity. Se um usuário voltar ao site no dia 45 e vir outra atividade, todo o valor eVar do A4T terá seu contador redefinido para 90 dias. Isso significa que a primeira campanha do dia 1 agora pode persistir por até 45 + 90 = 135 dias. If the user keeps coming back, you might get to the point where you see metrics sent to [!DNL Analytics] in your reporting from much older activities. À medida que os usuários excluem cookies e não retornam ao site, os números dessa atividade diminuem, mas você ainda os vê.

Isso significa que as atividades continuam recebendo visualizações de página, visitas e assim por diante, até 90 dias após o término da atividade para os visitantes que se tornaram parte da atividade enquanto ela estava ativa. No entanto, se você observar a métrica [!UICONTROL Impressões de atividades], não verá impressões depois que a atividade terminar.

Esse é um comportamento normal e esperado. A variável A4T funciona como qualquer outro eVar. O valor é associado ao usuário até atingir o período de expiração (90 dias). Como resultado, se uma atividade estiver ativa por apenas duas semanas, o valor ainda será associado ao usuário por pelo menos os próximos 90 dias.

A prática recomendada é ver relatórios para essa atividade apenas durante o período em que a atividade foi ao vivo. The dates should be set correctly by default when you view the activity in [!DNL Analytics], so unless you have manually extended the date this shouldn’t be an issue from a reporting standpoint.

Como exemplo, suponhamos que a variável A4T expire após 90 dias e nosso teste esteja ativo de 1 de janeiro a 15 de janeiro.

Em 1 de janeiro, o usuário acessa o site e vê a atividade XYZ uma vez e tem cinco exibições de página depois disso. Nas próximas duas semanas, o usuário nunca retorna ao site. Os dados ficariam assim para este usuário:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 5 | 1 | 1 |

O usuário retorna em 1 de fevereiro, visualiza mais cinco páginas e não encontra mais nenhuma atividade do Target e a atividade original não está mais ativa. Mesmo que a atividade não esteja mais ativa, ela ainda está seguindo o usuário por meio da persistência de eVar. Agora os dados ficam assim:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 10 | 2 | 1 |

O usuário volta em 1 de março e vê uma nova atividade, ABC. O usuário também visualiza cinco páginas. Como a atividade XYZ ainda segue o usuário por meio da persistência, e esse usuário tem ABC definido, veremos dois itens de linha no relatório:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos |
|--- |--- |--- |--- |--- |
| XYZ | 1 | 15 | 3 | 1 |
| ABC | 1 | 5 | 1 | 1 |

O usuário volta em 1 de abril, visualiza outras cinco páginas e faz uma compra. A expiração de 90 dias desse primeiro valor eVar é redefinida em 1 de abril, então veremos isso nos relatórios. E todas as atividades do Target que o usuário vê recebem o crédito pela conversão, mas o número total de conversões é deduplicado:

| Nome da atividade | Instâncias (Impressões) | Exibições de página | Visitas | Visitantes únicos | Pedidos |
|--- |--- |--- |--- |--- |--- |
| XYZ | 1 | 20 | 4 | 1 | 1 |
| ABC | 1 | 10 | 2 | 1 | 1 |
| Total | 2 | 20 | 3 | 1 | 1 |

Como as duas experiências foram vistas antes da conversão, ambas recebem &quot;crédito&quot; pelo pedido. Mas, apenas um pedido ocorreu no sistema e o total reflete isso. For [!DNL Target] reporting, because you aren’t putting a [!DNL Target] activity against another activity to see which is more successful, it doesn’t matter that all activities the user saw got credit. Você está comparando os resultados de dois itens na atividade única, e não é possível que um usuário veja experiências diferentes na mesma atividade para que você não precise se preocupar com a contaminação cruzada do crédito do pedido.

For more information, see [Conversion Variables (eVar](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/conversion-variables/conversion-var-admin.html)) in the *Analytics Admin Guide*.

## Por que o Analytics e o Analytics for Target (A4T) calculam números para a métrica de visitantes únicos de maneira diferente? {#section_0C3B648AB54041F9A2AA839D51791883}

Quando você executa um teste A/B, que usa o teste t de Estudante (a métrica de confiança) para escolher um vencedor de um teste, uma das suposições é que existe um horizonte de tempo fixo. O teste não é estatisticamente válido, a menos que você esteja olhando para esse tamanho de amostra fixo.

The [!UICONTROL Unique Visitors] metric is different in [!DNL Analytics] and [!DNL Target] only when you are looking at a period of time that is shorter than the actual test. Se você não atingiu o tamanho da amostra, o teste não é tão confiável. Consulte [Como não executar um teste A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) no [site de Evan Miller](https://www.evanmiller.org/index.html) para obter mais informações.

The [!UICONTROL Unique Visitors] metric displays the number of people who have been exposed to the test who have visited the site during the specified time period. Essas pessoas ainda fazem parte do teste e devem ser contadas. Se quiser ver apenas o número de pessoas que foram expostas durante uma única semana, você pode criar um segmento de visitantes que tiveram uma impressão de atividade e aplicá-lo ao relatório.

You can shorten the amount of time the [!DNL Target] variable persists down to a session; however, that is usually problematic for tests where the conversion event isn’t as likely to happen within the same session.

## Por que o mesmo visitante às vezes é contado em várias experiências no Analytics?  {#section_1397E972D31C4207A142E4D2D6D794A2}

A lista a seguir explica os motivos pelos quais o mesmo visitante pode ser contado em várias experiências no [!DNL Analytics]:

* The [!DNL Target] profile expired but the [!DNL Analytics] cookie is still there. In this situation, [!DNL Target] re-evaluates the user but [!DNL Analytics] considers the visitor to be the same person.
* Se o visitante estiver usando o `mbox3rdPartyId`, quando o visitante anônimo for mesclado ao perfil de ID de terceiros, o poderá colocar o visitante em uma experiência diferente para corresponder ao ID de terceiros. [!DNL Target] Para obter mais informações, consulte [Sincronização de perfil em tempo real para mbox3rdPartyID](/help/c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* [!DNL Analytics] pode estar rastreando dispositivos diferentes do mesmo visitante de uma forma diferente do que [!DNL Target] rastreia esses dispositivos: a configuração da ID de terceiros em [!DNL Target] é diferente da do Analytics.

## O A4T suporta conjuntos de relatórios virtuais?

Os conjuntos de relatórios virtuais *não* estão incluídos na lista de Conjunto de relatórios e os públicos-alvo de conjuntos de relatórios virtuais não são suportados nos relatórios A4T.

## É possível alterar a porcentagem da alocação de tráfego em uma atividade que usa o A4T depois de ativá-la?

Changing the traffic allocation percentage in an activity after activation can cause inconsistent reporting in [!DNL Analytics] because the change impacts only new visitors. Os visitantes recorrentes não são afetados.

Como prática recomendada, você deve interromper a atividade existente e criar uma nova atividade, em vez de alterar a porcentagem depois da ativação. Os relatórios para a nova atividade começam com os novos visitantes e os dados de visitantes recorrentes não causam relatórios inconsistentes.

## Como as visitas são contadas no Analytics e o crédito de conversão são alocados em uma atividade de Público alvo automático que usa a A4T?

Quando um visitante se qualifica para, conteúdo de visualização ou conversão em uma atividade A4T, [!DNL Target] envia dados do evento para [!DNL Analytics], o que permite [!DNL Analytics] atribuir eventos de conversão e outros eventos de sequência de cliques que ocorrem na página para as [!DNL Target] atividades e experiências relevantes.

Estes são alguns pontos que devem ser lembrados ao exibir [!DNL Analytics] relatórios:

* Em geral, a janela do relatórios deve sempre começar a partir da data do start da atividade.
* Se uma conversão ocorrer fora da janela do relatório, ela não estará visível em [!DNL Analytics].
* Quando na parte &quot;direcionada&quot; do tráfego para atividades de Público alvo  automático, os visitantes podem ver experiências diferentes de uma sessão para a próxima. Por exemplo, seu perfil ou contexto foi alterado e os algoritmos de aprendizado [!DNL Target]automático decidem que têm maior probabilidade de conversão em uma nova experiência. Isso é diferente das atividades comuns de teste A/B, onde as experiências são aderentes a um visitante durante as visitas.
* Se um visitante visualizar várias experiências ao longo das visitas, qualquer conversão é sempre atribuída à última experiência que o visitante viu; no entanto, a contagem de visitas será aumentada para cada experiência que o visitante tiver visto. Isso pode deprimir artificialmente as taxas de conversão por experiência ao visualizar experiências na dimensão &quot;[!UICONTROL Direcionado]&quot; nos [!DNL Adobe Analytics] relatórios.
