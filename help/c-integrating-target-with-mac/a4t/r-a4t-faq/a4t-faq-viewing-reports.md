---
description: Este tópico contém respostas para perguntas frequentes sobre como visualizar relatórios ao usar o Analytics como a origem de geração de relatórios do Target (A4T).
keywords: perguntas frequentes; perguntas frequentes; analytics para target; a4T; relatório; relatórios; exibir relatórios; relatórios; metodologia de contagem; impressões; visitantes; visitas; métrica padrão; conversões de atividade; não especificado
seo-description: Este tópico contém respostas para perguntas frequentes sobre como visualizar relatórios ao usar o Analytics como a origem de geração de relatórios do Target (A4T).
seo-title: Exibição de relatórios - Perguntas frequentes sobre o A4T
solution: Target
title: Exibição de relatórios - Perguntas frequentes sobre o A4T
topic: Padrão
uuid: d51991f7-cdda-4a59-b64c-7ef1c3f8380d
translation-type: tm+mt
source-git-commit: 1f55bf1c407ce2c00d6e1a7b63a9901ea68f6a16

---


# Exibição de relatórios - Perguntas frequentes sobre o A4T{#view-reports-a-t-faq}

Este tópico contém respostas para perguntas frequentes sobre como visualizar relatórios ao usar o Analytics como a origem de geração de relatórios do Target (A4T).

## Qual é a metodologia de contagem e como usá-la? {#section_E9C21C47B5BE4E54BABF0CD7F03D3945}

A metodologia de contagem especifica o que o Target usa como denominador para as taxas de conversão. As opções são:

* impressões
* visitantes
* visitas

## Posso definir uma métrica padrão para os relatórios do Target? {#section_50C20D286AA042CCA958184C9C0767DD}

Para o relatório Atividades, os administradores podem alterar a métrica padrão para que, toda vez que executem o relatório, mostrem as mesmas métricas. Caso contrário, o relatório será padronizado com a última métrica aplicada ao seu último relatório.

Para mais informações, consulte [Selecionar métricas de relatório padrão](https://marketing.adobe.com/resources/help/en_US/sc/user/t_metrics_set_default.html) no guia *Ajuda da interface de Reports and Analytics*.

## Quando aplico um segmento à métrica (com uma métrica calculada) ao aplicar o segmento ao relatório? {#section_BC29DEE6D2734911A5CD6FBF1189EB89}

Os segmentos aplicados aos relatórios seguem a mesma forma de aplicar segmentos no Target classic. Essa técnica é mais útil para ver como um teste afeta um subgrupo de pessoas (por exemplo, como esse teste foi realizado para pessoas no Reino Unido?).

É possível aplicar segmentos a métricas com uma métrica calculada. Isso geralmente é feito quando você deseja criar um novo tipo de evento de sucesso. Por exemplo, se você quiser ver quantos visitantes retornados sua atividade gerou, ou quantos visitantes chegaram a uma determinada página para ver seu teste. Observe que o aumento e a confiança não podem ser atualmente gerados para métricas calculadas.

## Devo usar visitantes, impressões de atividades ou visitas ao exibir relatórios? {#section_46D0CC450B414B4DA6853BFFEE87D7BE}

Existem várias opções, cada uma com suas próprias vantagens:

* ***Visitantes únicos*** aumentam uma vez quando um usuário se qualifica primeiro para uma atividade.
* ***Visitas*** aumentam a cada sessão quando um usuário (Visitante único) insere uma atividade, mesmo se a atividade não for exibida em visitas subsequentes.
* ***Impressões de atividade*** aumentam sempre que o conteúdo da atividade é distribuído. (Medidas pelo Target)
* ***Instâncias*** aumentam uma vez por página quando o conteúdo da atividade é distribuído. (Medidas por Analytics)

Quando um visitante exibe uma página que contém uma atividade, uma variável é definida para esse visitante e contém o nome dessa atividade. Veja os cenários detalhados abaixo sobre como cada metodologia de contagem é comparada.

Considere o seguinte:

* Todas as métricas acima são acionadas quando um usuário se qualifica para uma atividade e o conteúdo é retornado do [!DNL Target]. Isso não significa necessariamente que o usuário viu a oferta. Se uma experiência de atividade estiver abaixo da dobra e o usuário não rolar a página para baixo, a oferta foi distribuída pelo [!DNL Target], mas não foi vista pelo usuário.
* [!UICONTROL Impressões de atividade] (medidas pelo [!DNL Target]) e [!UICONTROL Instâncias] (medidas pelo [!DNL Analytics]) são iguais, a menos que haja várias chamadas de mbox na mesma página e na mesma atividade. Isso faz com que várias [!UICONTROL Impressões de atividade] sejam contadas, mas somente uma única [!UICONTROL Instância].
* Atualmente, as métricas de [!UICONTROL Impressões de atividades] e [!UICONTROL Conversão de atividades] são aumentadas no [!DNL Analysis Workspace] e não devem ser usadas até que esse problema seja resolvido.

## O que significa &quot;conversões de atividade&quot; se o profissional de marketing escolher uma métrica do Analytics durante a configuração da atividade? {#section_F3EBACF85AF846E9B366A549AAB64356}

&quot;Conversões de atividades&quot; estarão vazias se uma métrica do Analytics foi selecionada como a métrica de conversão da atividade.

## Por que vejo &quot;não especificado&quot; nos relatórios do Analytics? O que isso significa? {#section_AF38D32DAFEF4DDD95E07424CF682CCA}

![](assets/unspecified.png)

Em outros relatórios, &quot;não especificado&quot; significa que os dados não atendem a uma regra de classificação, mas no A4T isso nunca deve acontecer. Se você vir &quot;não especificado&quot;, o serviço de classificação ainda não foi executado. Pode levar até 36 horas para que os dados da atividade apareçam nos relatórios. Mesmo que as atividades não apareçam neste relatório até esse momento, todos os dados de visitantes vinculados a essas atividades serão capturados e aparecerão quando a classificação estiver concluída.

Após o período de classificação, os dados são exibidos nesses relatórios, aproximadamente uma hora depois de serem coletados no site. Todas as métricas, os segmentos e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

## Por que as métricas do Target são enviadas ao Analytics mesmo após a desativação da atividade? {#section_38AA8380A4D54A18972F1EF3E73E22EF}

A variável do [!DNL Target] enviada para o [!DNL Analytics] tem um período de expiração padrão de 90 dias. Este período de expiração pode ser ajustado pelo Atendimento ao cliente, se necessário. Essa configuração é global para todas as atividades, no entanto, não deve ser ajustada para um caso.

Você pode ver as variáveis de destino enviadas ao Analytics após o período de expiração porque a expiração é de 90 dias, mas apenas se esse usuário nunca vir outra atividade do Target habilitada para A4T. Se um usuário voltar ao site no dia 45 e vir outra atividade, todo o valor eVar do A4T terá seu contador redefinido para 90 dias. Isso significa que a primeira campanha do dia 1 agora pode persistir por até 45 + 90 = 135 dias. Se o usuário continuar voltando, você pode chegar ao ponto em que vê as métricas enviadas para o Analytics nos relatórios de atividades muito mais antigas. À medida que os usuários excluem cookies e não retornam ao site, os números dessa atividade diminuem, mas você ainda os vê.

Isso significa que as atividades continuam recebendo visualizações de página, visitas e assim por diante, até 90 dias após o término da atividade para os visitantes que se tornaram parte da atividade enquanto ela estava ativa. No entanto, se você observar a métrica [!UICONTROL Impressões de atividades], não verá impressões depois que a atividade terminar.

Esse é um comportamento normal e esperado. A variável A4T funciona como qualquer outro eVar. O valor é associado ao usuário até atingir o período de expiração (90 dias). Como resultado, se uma atividade estiver ativa por apenas duas semanas, o valor ainda será associado ao usuário por pelo menos os próximos 90 dias.

A prática recomendada é ver relatórios para essa atividade apenas durante o período em que a atividade foi ao vivo. As datas devem ser definidas corretamente por padrão quando você visualiza a atividade no Analytics. Portanto, a menos que você tenha estendido manualmente a data, isso não deve ser um problema do ponto de vista do relatório.

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

Como as duas experiências foram vistas antes da conversão, ambas recebem &quot;crédito&quot; pelo pedido. Mas, apenas um pedido ocorreu no sistema e o total reflete isso. Para geração de relatório do Target, porque você não está comparando a atividade com atividade do Target para ver qual é mais bem-sucedida, não importa que todas as atividades que o usuário viu recebam crédito. Você está comparando os resultados de dois itens na atividade única, e não é possível que um usuário veja experiências diferentes na mesma atividade para que você não precise se preocupar com a contaminação cruzada do crédito do pedido.

Para obter mais informações, consulte [Variáveis de conversão (eVar)](https://marketing.adobe.com/resources/help/en_US/reference/conversion_var_admin.html) na ajuda do Analytics.

## Por que o Analytics e o Analytics for Target (A4T) calculam números para a métrica de visitantes únicos de maneira diferente? {#section_0C3B648AB54041F9A2AA839D51791883}

Quando você executa um teste A/B, que usa o teste t de Estudante (a métrica de confiança) para escolher um vencedor de um teste, uma das suposições é que existe um horizonte de tempo fixo. O teste não é estatisticamente válido, a menos que você esteja olhando para esse tamanho de amostra fixo.

A métrica de visitantes únicos é diferente no Analytics e no Target apenas quando você está analisando um período de tempo menor do que o teste real. Se você não atingiu o tamanho da amostra, o teste não é tão confiável. Consulte [Como não executar um teste A/B](https://www.evanmiller.org/how-not-to-run-an-ab-test.html) no [site de Evan Miller](https://www.evanmiller.org/index.html) para obter mais informações.

A métrica Visitantes únicos exibe o número de pessoas que foram expostas ao teste que visitaram o site durante o período especificado. Essas pessoas ainda fazem parte do teste e devem ser contadas. Se quiser ver apenas o número de pessoas que foram expostas durante uma única semana, você pode criar um segmento de visitantes que tiveram uma impressão de atividade e aplicá-lo ao relatório.

Você pode diminuir o tempo que a variável do Target persiste em uma sessão; no entanto, isso geralmente é problemático para testes em que o evento de conversão não é tão provável de acontecer na mesma sessão.

## Por que o mesmo visitante às vezes é contado em várias experiências no Analytics? {#section_1397E972D31C4207A142E4D2D6D794A2}

A lista a seguir explica os motivos pelos quais o mesmo visitante pode ser contado em várias experiências no Analytics:

* O perfil do Target expirou, mas o cookie do Analytics ainda está lá. Nessa situação, o Target reavalia o usuário, mas o Analytics considera o visitante como a mesma pessoa.
* Se o visitante estiver usando o `mbox3rdPartyId`, quando o visitante anônimo for mesclado ao perfil de ID de terceiros, o Target poderá colocar o visitante em uma experiência diferente para corresponder ao ID de terceiros. Para obter mais informações, consulte [Sincronização de perfil em tempo real para mbox3rdPartyID](../../../c-target/c-visitor-profile/3rd-party-id.md#concept_BF4113593F614987B1D3E359AE1C5732).
* O Analytics pode estar rastreando diferentes dispositivos como o mesmo visitante de uma maneira diferente que o Target rastreia esses dispositivos. A configuração da ID de terceiros no Target é diferente da configuração do Analytics.

## O A 4 T suporta conjuntos de relatórios virtuais?

Os conjuntos de relatórios virtuais *não* estão incluídos na lista Conjunto de relatórios e nos públicos-alvo de conjuntos de relatórios virtuais não são suportados nos relatórios A 4 T.

## É possível alterar a porcentagem da alocação de tráfego em uma atividade que usa A 4 T depois que a atividade foi ativada?

Alterar a porcentagem de alocação de tráfego em uma atividade após a ativação pode causar relatórios inconsistentes no Analytics, pois a alteração afeta apenas os novos visitantes. Os visitantes recorrentes não são afetados.

Como prática recomendada, você deve parar a atividade existente e criar uma nova atividade em vez de alterar a porcentagem depois da ativação. O relatório para a nova atividade começa com novos visitantes e os dados de visitantes recorrentes não geram relatórios inconsistentes.

## É possível exibir meus dados de atividade do Target na Adobe Analysis Workspace?

É possível usar [!DNL Adobe Analysis Workspace] para pesquisar mais fundo e visualizar os dados ou descobrir insights ocultos abaixo da superfície.

Para obter informações detalhadas e exemplos, abra o [Analytics &amp; Target: Práticas recomendadas para tutorial de Análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecidas pela Adobe Experience Manager.