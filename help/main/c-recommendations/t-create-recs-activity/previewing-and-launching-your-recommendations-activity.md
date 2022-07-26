---
keywords: Recommendations, oferta, visualização, lançamento, status, critérios, algoritmo
description: 'Saiba como visualizar o Adobe [!DNL Target] Atividade do Recommendations para garantir que os resultados estejam disponíveis antes de iniciar a atividade. '
title: Como visualizar e iniciar uma atividade do Recommendations?
feature: Recommendations
exl-id: 60391778-4d48-4c41-a7c5-fedcfabf2530
source-git-commit: 7732f3af0fd995309035a8a214afd438ab7a1823
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 17%

---

# Pré-visualizar e iniciar atividade do Recommendations

Depois de criar o [!UICONTROL Recommendations], [!UICONTROL Teste A/B]ou [!UICONTROL Direcionamento de experiência] (XT) atividade contendo [Ofertas da Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md), você deverá visualizar suas recomendações para garantir que os resultados estejam disponíveis antes de iniciar a atividade. [!DNL Target Recommendations] O oferece várias maneiras de visualizar suas recomendações.

## Verificando o status do algoritmo Recommendations

Depois de criar uma atividade, [!DNL Recommendations] executa um algoritmo para gerar recomendações. Esse algoritmo pode levar algumas horas para ser executado.

Você pode verificar se o algoritmo terminou de ser executado no [!UICONTROL Atividade] diagrama de visão geral, onde o status dos critérios é listado. A ilustração a seguir mostra o status no diagrama de atividades em um [!DNL Recommendations] da atividade [!UICONTROL Visão geral] página:

![Página Visão geral da atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview.png)

A ilustração a seguir descreve o status em um [!UICONTROL Teste A/B] ou da atividade XT [!UICONTROL Visão geral] página:

![Página Visão geral do teste A/B](/help/main/c-recommendations/t-create-recs-activity/assets/ab-overview.png)

Os resultados do status incluem o seguinte, conforme ilustrado abaixo:

* [!UICONTROL Resultados prontos]: Indica que o algoritmo retornou resultados
* [!UICONTROL Resultados não prontos]: Indica que o algoritmo não terminou de ser executado.
* [!UICONTROL Falha do feed]: Indica que o arquivo de feed de critérios personalizados não pôde ser recuperado.

![Caixa de diálogo Resultados](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Quanto tempo o algoritmo levará para ser executado?

Depois de salvar uma atividade contendo um critério, [!DNL Target] O calcula as recomendações com base na coleção, critérios, design e promoções selecionadas. Esse cálculo leva algum tempo para ser executado e o período difere com base na lógica de recomendação selecionada, no intervalo de dados, no número de itens no catálogo, na quantidade de dados comportamentais gerados pelos clientes e na fonte de dados comportamentais selecionada.

A fonte de dados comportamentais tem o maior impacto no tempo de processamento, da seguinte maneira:

### mboxes

Se as mboxes forem selecionadas como a fonte de dados comportamentais, depois de criados, os critérios serão executados imediatamente. Dependendo da quantidade de dados comportamentais usados&#x200B; e do tamanho do catálogo, o algoritmo pode levar até 12 horas para ser executado. Fazer alterações na configuração dos critérios geralmente resulta na repetição do algoritmo. Dependendo da alteração feita, as recomendações calculadas anteriormente podem não estar disponíveis até que uma nova execução seja concluída ou, para alterações maiores, somente o backup ou o conteúdo padrão estejam disponíveis até que uma nova execução seja concluída. Se um algoritmo não for modificado, ele será executado automaticamente pelo [!DNL Target] a cada 12-48 horas, dependendo do intervalo de dados selecionado.

### Adobe Analytics

Se os critérios usarem o [!DNL Adobe Analytics] como a fonte de dados comportamentais, depois de criados, o tempo para a disponibilidade dos critérios dependerá se o conjunto de relatórios selecionado e a janela de lookback foram usados para quaisquer outros critérios.

* **Configuração única do conjunto de relatórios**: a primeira vez que um conjunto de relatórios é usado com determinada janela de lookback do intervalo de dados, [!DNL Target Recommendations] pode levar de dois a sete dias para baixar completamente os dados comportamentais do conjunto de relatórios selecionado no [!DNL Analytics]. Esse período depende da carga do sistema do [!DNL Analytics].
* **Critérios novos ou editados usando um conjunto de relatórios já disponível**: Ao criar um novo critério ou editar um critério existente, se o conjunto de relatórios selecionado já tiver sido usado com o [!DNL Target Recommendations], com um intervalo de dados igual ou inferior ao intervalo de dados selecionado, os dados são imediatamente disponibilizados e nenhuma configuração única é necessária. Nesse caso ou se as configurações de um algoritmo forem editadas, enquanto o conjunto de relatórios ou intervalo de dados selecionado não for modificado, o algoritmo será executado ou executado novamente em 12 horas.
* **O algoritmo contínuo é executado**: os dados fluem do [!DNL Analytics] para [!DNL Target Recommendations] diariamente. Por exemplo, para a recomendação [!UICONTROL Afinidade visualizada], quando um usuário exibe um produto, uma chamada de rastreamento de exibições do produto é passada para o [!DNL Analytics] quase em tempo real. O [!DNL Analytics] os dados são enviados para [!DNL Target] no início do dia seguinte e [!DNL Target] O executa o algoritmo em menos de 12 horas.

>[!NOTE]
>
>[!UICONTROL Itens visualizados recentemente] não requer algoritmo offline executado e os resultados são disponibilizados instantaneamente. [!UICONTROL Mais visualizados] e [!UICONTROL Mais vendidos] algoritmos baseados em dados de mbox geralmente produzem resultados muito rapidamente devido ao cálculo mais simples necessário. Essas podem ser boas opções quando você deseja visualizar uma alteração de design ou confirmar que os dados comportamentais estão sendo coletados corretamente.

## Uso de links de controle de qualidade para visualizar o Recommendations

Depois que o algoritmo tiver os resultados prontos, você poderá visualizar esses resultados usando a [Link de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) funcionalidade de [!DNL Adobe Target]. Os links de controle de qualidade estão disponíveis no [!UICONTROL Controle de qualidade da atividade] da página Visão geral da atividade :

![Link de controle de qualidade da atividade](/help/main/c-recommendations/t-create-recs-activity/assets/qa-link.png)

>[!NOTE]
>
>Por padrão, [!DNL Target] O adiciona automaticamente você ao público-alvo necessário para o link de controle de qualidade. Se essa configuração estiver desativada e sua atividade tiver regras de direcionamento, o perfil do usuário precisará atender a essas regras de direcionamento para ver a experiência que contém as recomendações.

Usar um link de controle de qualidade permite visualizar as recomendações em sua página:

![Produtos em destaque](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* O modo de controle de qualidade do Target é &quot;aderente&quot; e salvo em um cookie. Se você não sair do modo de controle de qualidade, continuará vendo os resultados do controle de qualidade em todo o site. Para sair do modo de QA, use o [bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* Enquanto estiver no modo de QA, navegar no site não afetará o [!UICONTROL Itens visualizados recentemente] ou [!UICONTROL Itens comprados recentemente]. Esse comportamento ocorre por design para evitar a poluição não intencional de dados comportamentais de produção. Para visualizar os resultados de uma [!UICONTROL Itens visualizados recentemente] ou [!UICONTROL Recommendations baseado em usuário] critérios, primeiro navegue pelo site fora do modo de QA e use a mesma sessão para abrir um link do modo de QA.


## Uso do download do CSV para visualizar as recomendações

Em alguns casos, você pode querer auditar os itens específicos que são recomendados. Isso é particularmente útil ao usar algoritmos como [!UICONTROL Pessoas que visualizaram isto, viram aquilo], onde um conjunto diferente de itens é recomendado, dependendo do item que o usuário está visualizando no momento, e você pode ter milhares ou milhões de itens diferentes em seu catálogo.

Os resultados não estão disponíveis para download até que uma [!UICONTROL Resultados prontos] O status é mostrado para pelo menos um algoritmo na atividade.

Para baixar os resultados para visualização, clique no ícone de menu no canto superior direito da página Visão geral da atividade e clique em **[!UICONTROL Baixar dados]**.

![Opção Baixar dados](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

Um arquivo CSV é baixado. Abra-o para ver os itens recomendados:

![Arquivo CSV de itens recomendados](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

Da esquerda para a direita é uma lista de itens recomendados, nesse caso os exibidos com mais frequência. As recomendações são separadas por ambiente, nesse caso, apenas o ambiente de Produção tem recomendações. Para este algoritmo, não aplicamos restrições baseadas em valor principal, portanto, a linha rotulada com um asterisco (*) contém o conjunto completo de recomendações. Para outros tipos de algoritmo com base em um valor principal, como [!UICONTROL Pessoas que visualizaram isto, viram aquilo], os valores principais (ou seja, os itens &quot;Este&quot;) são listados na coluna mais à esquerda e os itens recomendados (ou seja, os itens &quot;Que&quot;) são listados da esquerda para a direita nas colunas Recommendation_X.

>[!NOTE]
>
>Os downloads de resultados não estão disponíveis para atividades que contêm um [!UICONTROL Recommendations baseado em usuário] algoritmo. Os downloads de resultados não estão disponíveis para critérios que usam a variável [!UICONTROL Itens visualizados recentemente] lógica de recomendação.

## Ativação da atividade do Recommendations

No [!UICONTROL Visão geral da atividade] , clique na seta suspensa ao lado do status e selecione **[!UICONTROL Ativar]**.

![Opção Ativar](/help/main/c-recommendations/t-create-recs-activity/assets/activate.png)

Observe que o status se torna [!UICONTROL Ativando]:

![Ativando](/help/main/c-recommendations/t-create-recs-activity/assets/activating.png)

Após alguns segundos a alguns minutos, o status muda para [!UICONTROL Ao vivo]:

![On-line](/help/main/c-recommendations/t-create-recs-activity/assets/live.png)

Observe que você também pode desativar ou arquivar a atividade usando a mesma lista suspensa.

## Como evitar interrupções ao alterar configurações do Recommendations

Alterar [!DNL Recommendations] coleções, critérios, promoções ou configurações de design em uma atividade ativa podem resultar em resultados de algoritmo ficarem inválidos e o status de um algoritmo mudar para [!UICONTROL Resultados não prontos].

Para evitar interromper uma atividade ativa, recomendamos seguir a abordagem a seguir ao modificar uma atividade ativa:

1. Duplique a atividade original (atividade 1) e os critérios que deseja modificar para criar uma nova atividade (atividade 2).
1. Faça alterações na atividade duplicada (atividade 2) e nos critérios e aguarde o algoritmo gerar resultados.
1. Visualize a atividade nova e modificada (atividade 2) e confirme se os resultados estão conforme desejado.
1. Ative a nova atividade (atividade 2).
1. Desative a atividade original (atividade 1).

Se você precisar manter os resultados históricos do relatório na mesma atividade, uma abordagem alternativa será possível, o que pode resultar em uma interrupção temporária da disponibilidade das recomendações:

1. Duplique a atividade original (atividade 1) e os critérios que deseja modificar para criar uma nova atividade (atividade 2).
1. Faça alterações na atividade duplicada (atividade 2) e nos critérios e aguarde o algoritmo gerar resultados.
1. Visualize a atividade nova e modificada (atividade 2) e confirme se os resultados estão conforme desejado.
1. Pause a atividade nova e modificada (atividade 2) e troque as configurações/critérios pela atividade original (atividade 1).
1. Visualize a atividade original (atividade 1) e confirme se os resultados estão conforme desejado.
1. Reative a atividade original (atividade 1).
