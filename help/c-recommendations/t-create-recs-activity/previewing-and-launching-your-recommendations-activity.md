---
keywords: Recommendations;offer;preview;launch
description: 'Depois de criar sua atividade Recommendations, teste A/B ou direcionamento de experiência (XT) contendo ofertas Adobe Target Recommendations, você deverá pré-visualização-la para garantir que os resultados estejam disponíveis antes de iniciar a atividade. O Público alvo Recommendations oferta várias maneiras de pré-visualização de suas recomendações. '
title: 'Depois de criar sua atividade Recommendations, teste A/B ou direcionamento de experiência (XT) contendo ofertas Adobe Target Recommendations, você deverá pré-visualização-la para garantir que os resultados estejam disponíveis antes de iniciar a atividade. O Público alvo Recommendations oferta várias maneiras de pré-visualização de suas recomendações. '
feature: recs creation
subtopic: Recommendations
translation-type: tm+mt
source-git-commit: afbec50cb0ec4e689bfaa77296ffda91bc6de3a5
workflow-type: tm+mt
source-wordcount: '1398'
ht-degree: 16%

---


# Pré-visualizar e iniciar atividade do Recommendations

Depois de criar a atividade [!UICONTROL Recommendations], Teste A/B ou Definição de metas [!UICONTROL de] experiência (XT) que contém o [Recommendations oferta](/help/c-recommendations/recommendations-as-an-offer.md), você desejará pré-visualização nas recomendações para garantir que os resultados estejam disponíveis antes de iniciar a atividade. [!DNL Target Recommendations] oferta várias maneiras de pré-visualização de suas recomendações.

## Verificando o status do algoritmo Recommendations

Depois de criar uma atividade, [!DNL Recommendations] executa um algoritmo para gerar recomendações. Esse algoritmo pode levar algumas horas para ser executado.

Você pode verificar se o algoritmo terminou de ser executado no diagrama de visão geral da [!UICONTROL Atividade] , onde o status do critério está listado. The following illustration shows the status in the activity diagram on a [!DNL Recommendations] activity&#39;s [!UICONTROL Overview] page:

![Página Visão geral da atividade Recommendations](/help/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

A ilustração a seguir descreve o status em um teste [!UICONTROL A/B ou na página] Visão geral  da atividade XT:

![Página Visão geral do teste A/B](/help/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

Os resultados de status incluem o seguinte, conforme ilustrado abaixo:

* [!UICONTROL Resultados prontos]: Indica que o algoritmo retornou resultados
* [!UICONTROL Resultados Não Prontos]: Indica que o algoritmo não terminou de ser executado.
* [!UICONTROL Falha]do feed: Indica que o arquivo de feed de critérios personalizados não pôde ser recuperado.

![Caixa de diálogo Resultados](/help/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Quanto tempo o algoritmo levará para ser executado?

Depois de salvar uma atividade que contém um critério, [!DNL Target] calcula as recomendações com base na coleção, critérios, design e promoções selecionados. Esse cálculo leva algum tempo para ser executado e o período é diferente com base na lógica de recomendação selecionada, no intervalo de dados, no número de itens no catálogo, na quantidade de dados comportamentais que seus clientes geraram e na fonte de dados comportamentais selecionada.

A fonte de dados comportamentais tem o maior impacto no tempo de processamento, da seguinte maneira:

### mboxes

Se as mboxes forem selecionadas como a fonte de dados comportamentais, depois de criados, os critérios serão executados imediatamente. Dependendo da quantidade de dados comportamentais usados&#x200B; e do tamanho do catálogo, o algoritmo pode levar até 12 horas para ser executado. Fazer alterações na configuração dos critérios geralmente resulta na repetição do algoritmo. Dependendo da alteração feita, as recomendações calculadas anteriormente podem não estar disponíveis até que uma nova execução seja concluída ou, para alterações maiores, apenas o conteúdo padrão ou de backup esteja disponível até que uma nova execução seja concluída. Se um algoritmo não for modificado, ele será executado automaticamente pelo [!DNL Target] a cada 12-48 horas, dependendo do intervalo de dados selecionado.

### Adobe Analytics

Se os critérios usarem o [!DNL Adobe Analytics] como a fonte de dados comportamentais, depois de criados, o tempo para a disponibilidade dos critérios dependerá se o conjunto de relatórios selecionado e a janela de lookback foram usados para quaisquer outros critérios.

* **Configuração única do conjunto de relatórios**: a primeira vez que um conjunto de relatórios é usado com determinada janela de lookback do intervalo de dados, [!DNL Target Recommendations] pode levar de dois a sete dias para baixar completamente os dados comportamentais do conjunto de relatórios selecionado no [!DNL Analytics]. Esse período depende da carga do sistema do [!DNL Analytics].
* **Critérios novos ou editados usando um conjunto** de relatórios já disponível: Ao criar um novo critério ou editar um critério existente, se o conjunto de relatórios selecionado já tiver sido usado com [!DNL Target Recommendations], com um intervalo de dados igual ou inferior ao intervalo de dados selecionado, os dados estarão imediatamente disponíveis e nenhuma configuração única será necessária. Nesse caso ou se as configurações de um algoritmo forem editadas, enquanto o conjunto de relatórios ou intervalo de dados selecionado não for modificado, o algoritmo será executado ou executado novamente em 12 horas.
* **O algoritmo contínuo é executado**: os dados fluem do [!DNL Analytics] para [!DNL Target Recommendations] diariamente. Por exemplo, para a recomendação [!UICONTROL Afinidade visualizada], quando um usuário exibe um produto, uma chamada de rastreamento de exibições do produto é passada para o [!DNL Analytics] quase em tempo real. The [!DNL Analytics] data is pushed to [!DNL Target] early the next day and [!DNL Target] runs the algorithm in fewer than 12 hours.

>[!NOTE]
>
>[!UICONTROL Itens] visualizados recentemente não exigem execução de algoritmos offline e os resultados estão disponíveis instantaneamente. [!UICONTROL Os algoritmos de Mais Visualizados] e [!UICONTROL Mais Vendidos] com base nos dados da mbox geralmente produzem resultados muito rapidamente devido à computação mais simples necessária. Essas podem ser boas opções quando você deseja pré-visualização uma alteração de design ou confirmar que os dados comportamentais estão sendo coletados corretamente.

## Usar links de QA para a pré-visualização Recommendations

Depois que o algoritmo tiver os resultados prontos, você poderá pré-visualização-los usando a funcionalidade de link [de](/help/c-activities/c-activity-qa/activity-qa.md) QA do [!DNL Adobe Target]. Os links de controle de qualidade estão disponíveis na seção de controle de qualidade [!UICONTROL da] Atividade da página de visão geral da Atividade:

![Link de controle de qualidade da atividade](/help/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>Por padrão, [!DNL Target] o adiciona automaticamente à audiência necessária para o link de QA. Se essa configuração estiver desativada e sua atividade tiver regras de definição de metas, seu perfil de usuário precisará atender a essas regras de definição de metas para ver a experiência que contém as recomendações.

Usar um link de QA permite que você pré-visualização as recomendações na sua página:

![Produtos em destaque](/help/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* O modo de QA do público alvo é &quot;aderente&quot; e salvo em um cookie. Se você não sair do modo de controle de qualidade, continuará vendo os resultados de controle de qualidade em todo o site. Para sair do modo de QA, use o [bookmarklet](/help/c-activities/c-activity-qa/activity-qa-bookmark.md).
   >
   >
* Enquanto estiver no modo de controle de qualidade, a navegação no site não afetará os itens [!UICONTROL visualizados] recentemente ou os itens [!UICONTROL comprados]recentemente do perfil.&quot; Esse comportamento ocorre por projeto para evitar poluição não intencional dos dados comportamentais de produção. Para pré-visualização dos resultados de um critério de Itens [!UICONTROL visualizados] recentemente ou Recommendations [!UICONTROL baseado no] usuário, navegue primeiro no site fora do modo de QA e use a mesma sessão para abrir um link do modo de QA.


## Uso do download CSV para recomendações de pré-visualização

Em alguns casos, talvez você queira auditar os itens específicos recomendados. Isso é particularmente útil ao usar algoritmos como [!UICONTROL Pessoas que visualizaram isso, viram aquilo], onde um conjunto diferente de itens é recomendado dependendo do item que o usuário está visualizando no momento, e você pode ter milhares ou milhões de itens diferentes em seu catálogo.

Os resultados não estão disponíveis para download até que o status [!UICONTROL Resultados prontos] seja mostrado para pelo menos um algoritmo na atividade.

Para baixar os resultados da pré-visualização, clique no ícone de menu no canto superior direito da página de visão geral da Atividade e clique em **[!UICONTROL Download de dados]**.

![Opção de download de dados](/help/c-recommendations/t-create-recs-activity/assets/download-data.png)

Um arquivo CSV é baixado. Abra-o para ver os itens recomendados:

![Arquivo CSV de itens recomendados](/help/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

Da esquerda para a direita é uma lista de itens recomendados, neste caso os exibidos com mais frequência. As recomendações são separadas por ambiente, nesse caso apenas o ambiente de Produção tem recomendações. Para este algoritmo, não aplicamos restrições baseadas no valor chave, portanto a linha rotulada com um asterisco (*) contém o conjunto completo de recomendações. Para outros tipos de algoritmos com base em um valor-chave, como [!UICONTROL Pessoas que viram isso, viram que]os valores-chave (ou seja, os itens &quot;This&quot;) estão listados na coluna mais à esquerda e os itens recomendados (ou seja, os itens &quot;This&quot;) estão listados da esquerda para a direita nas colunas Recommendation_X.

>[!NOTE]
>
>Os downloads de resultados não estão disponíveis para atividades que contêm um algoritmo Recommendations [!UICONTROL baseado em] usuário. Os downloads de resultados não estão disponíveis para critérios usando a lógica de recomendação Itens [!UICONTROL visualizados] recentemente.

## Como ativar sua atividade Recommendations

Na guia Visão geral [!UICONTROL da] Atividade, clique na seta suspensa ao lado do status e selecione **[!UICONTROL Ativar]**.

![Opção Ativar](/help/c-recommendations/t-create-recs-activity/assets/activate.png)

Observe que o status se torna [!UICONTROL Ativando]:

![Ativando](/help/c-recommendations/t-create-recs-activity/assets/activating.png)

Após alguns segundos a alguns minutos, o status muda para [!UICONTROL Online]:

![On-line](/help/c-recommendations/t-create-recs-activity/assets/live.png)

Observe que você também pode desativar ou arquivar a atividade usando a mesma lista suspensa.

## Evitar interrupções ao alterar configurações do Recommendations

Alterar [!DNL Recommendations] coleções, critérios, promoções ou configurações de design em uma atividade ao vivo pode resultar em resultados do algoritmo se tornando inválidos e no status de um algoritmo alterando para [!UICONTROL Resultados não prontos].

Para evitar interromper uma atividade ao vivo, recomendamos adotar a seguinte abordagem ao modificar uma atividade ao vivo:

1. Duplicado a atividade e os critérios que você deseja modificar.
1. Faça alterações na atividade e nos critérios duplicados e aguarde até que o algoritmo gere resultados.
1. Pré-visualização a nova atividade modificada e confirme se os resultados são os desejados.
1. Ative a nova atividade.
1. Desative a atividade antiga.

Se você precisar manter os resultados do relatórios histórico na mesma atividade, uma abordagem alternativa será possível, o que pode resultar em uma interrupção temporária da disponibilidade das recomendações:

1. Duplicado a atividade e os critérios que você deseja modificar.
1. Faça alterações na atividade e nos critérios duplicados e aguarde até que o algoritmo gere resultados.
1. Pré-visualização a nova atividade modificada e confirme se os resultados são os desejados.
1. Pause a atividade existente e troque as configurações/critérios pelos novos critérios.
1. Pré-visualização a atividade existente e confirme se os resultados são os desejados.
1. Reative a atividade.
