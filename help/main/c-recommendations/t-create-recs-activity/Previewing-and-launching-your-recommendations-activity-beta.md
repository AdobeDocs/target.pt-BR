---
keywords: Recomendações;oferta;visualização;iniciar;status;critérios;algoritmo;Recommendations;offer;preview;launch;status;criteria;algorithm
description: Saiba como visualizar sua atividade do Adobe [!DNL Target] Recommendations para garantir que os resultados estejam disponíveis antes de iniciar a atividade.
title: Como visualizar e iniciar uma atividade do Recommendations?
feature: Recommendations
hide: true
hidefromtoc: true
source-git-commit: ed400ad0ecf62a74283d2f24038bacab6a275461
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 15%

---

# Pré-visualizar e iniciar atividade do Recommendations

Depois de criar sua atividade do [!UICONTROL Recommendations], [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] (XT) contendo [ofertas do Recommendations](/help/main/c-recommendations/recommendations-as-an-offer.md), você pré-visualizará suas recomendações para garantir que os resultados estejam disponíveis antes de iniciar a atividade. O [!DNL Target Recommendations] oferece várias maneiras de visualizar suas recomendações.

## Verificação do status do algoritmo do Recommendations

Depois de criar uma atividade, [!DNL Recommendations] executa um algoritmo para gerar recomendações. Esse algoritmo pode levar algumas horas para ser executado.

Você pode verificar se a execução do algoritmo foi concluída no diagrama de visão geral [!UICONTROL Activity], onde o status dos critérios está listado. A ilustração a seguir mostra o status no diagrama de atividades na página [!DNL Recommendations] de uma atividade [!UICONTROL Overview]:

![Página de visão geral da atividade do Recommendations](/help/main/c-recommendations/t-create-recs-activity/assets/recs-overview-new.png)

Os resultados do status incluem o seguinte, conforme ilustrado abaixo:

* [!UICONTROL Results Ready]: indica que o algoritmo retornou resultados
* [!UICONTROL Results Not Ready]: indica que a execução do algoritmo não foi concluída.
* [!UICONTROL Feed Failure]: indica que o arquivo de feed de critérios personalizados não pôde ser recuperado.

![Caixa de diálogo Resultados](/help/main/c-recommendations/c-algorithms/assets/criteria_status_multi.png)

## Quanto tempo levará para o algoritmo ser executado?

Depois de salvar uma atividade contendo um critério, o [!DNL Target] calcula as recomendações com base na coleção, nos critérios, no design e nas promoções selecionados. Esse cálculo leva algum tempo para ser executado e o período difere com base na lógica de recomendação selecionada, no intervalo de dados, no número de itens no catálogo, na quantidade de dados comportamentais gerados pelos clientes e na fonte de dados comportamentais selecionada.

A fonte de dados comportamentais tem o maior impacto no tempo de processamento, da seguinte maneira:

### mboxes

Se as mboxes forem selecionadas como a fonte de dados comportamentais, depois de criados, os critérios serão executados imediatamente. Dependendo da quantidade de dados comportamentais usados&#x200B; e do tamanho do catálogo, o algoritmo pode levar até 12 horas para ser executado. Fazer alterações na configuração dos critérios geralmente resulta na repetição do algoritmo. Dependendo da alteração feita, as recomendações calculadas anteriormente podem não estar disponíveis até que uma nova execução seja concluída ou, para alterações maiores, somente o backup ou o conteúdo padrão estará disponível até que uma nova execução seja concluída. Se um algoritmo não for modificado, ele será executado automaticamente pelo [!DNL Target] a cada 12-48 horas, dependendo do intervalo de dados selecionado.

### [!DNL Adobe Analytics]

Se os critérios usarem o [!DNL Adobe Analytics] como a fonte de dados comportamentais, depois de criados, o tempo para a disponibilidade dos critérios dependerá se o conjunto de relatórios selecionado e a janela de lookback foram usados para quaisquer outros critérios.

* **Configuração única do conjunto de relatórios**: a primeira vez que um conjunto de relatórios é usado com determinada janela de lookback do intervalo de dados, [!DNL Target Recommendations] pode levar de dois a sete dias para baixar completamente os dados comportamentais do conjunto de relatórios selecionado no [!DNL Analytics]. Esse período depende da carga do sistema do [!DNL Analytics].
* **Critérios novos ou editados usando um conjunto de relatórios já disponível**: ao criar um novo critério ou editar um critério existente, se o conjunto de relatórios selecionado já tiver sido usado com [!DNL Target Recommendations], com um intervalo de dados igual ou menor que o intervalo de dados selecionado, os dados serão imediatamente disponibilizados e a configuração única não será necessária. Nesse caso ou se as configurações de um algoritmo forem editadas, enquanto o conjunto de relatórios ou intervalo de dados selecionado não for modificado, o algoritmo será executado ou executado novamente em 12 horas.
* **O algoritmo contínuo é executado**: os dados fluem do [!DNL Analytics] para [!DNL Target Recommendations] diariamente. Por exemplo, para a recomendação do [!UICONTROL Viewed Affinity], quando um usuário exibe um produto, uma chamada de rastreamento de exibições do produto é passada para o [!DNL Analytics] quase em tempo real. Os dados do [!DNL Analytics] são encaminhados para [!DNL Target] no início do dia seguinte e o [!DNL Target] executa o algoritmo em menos de 12 horas.

>[!NOTE]
>
>[!UICONTROL Recently Viewed Items] não requer a execução de algoritmo offline e os resultados são disponibilizados instantaneamente. Os algoritmos [!UICONTROL Top Viewed] e [!UICONTROL Top Sellers] baseados em dados de mbox geralmente produzem resultados muito rapidamente devido ao cálculo mais simples necessário. Essas podem ser boas opções quando você deseja visualizar uma alteração de design ou confirmar se os dados comportamentais estão sendo coletados corretamente.

## Uso de links de controle de qualidade para visualizar Recommendations

Depois que o algoritmo tiver os resultados prontos, você poderá visualizar esses resultados usando a funcionalidade [Link de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) de [!DNL Adobe Target]. Os links de controle de qualidade estão disponíveis na seção [!UICONTROL Activity Location] da página de visão geral [!UICONTROL Activity]:

>[!NOTE]
>
>Por padrão, o [!DNL Target] adiciona você automaticamente ao público-alvo necessário para o link de controle de qualidade. Se essa configuração estiver desativada e sua atividade tiver regras de direcionamento, seu perfil de usuário precisará atender a essas regras de direcionamento para ver a experiência que contém recomendações.

Usar um link de controle de qualidade permite visualizar as recomendações na sua página:

![Produtos em destaque](/help/main/c-recommendations/t-create-recs-activity/assets/featured-products.png)

>[!NOTE]
>
>* O modo de controle de qualidade do Target é &quot;aderente&quot; e salvo em um cookie. Se você não sair do modo de controle de qualidade, continuará vendo os resultados do controle de qualidade em todo o site. Para sair do modo de controle de qualidade, use o [bookmarklet](/help/main/c-activities/c-activity-qa/activity-qa-bookmark.md).
>
>* Enquanto estiver no modo de controle de qualidade, navegar no site não afetará o [!UICONTROL Recently Viewed Items] ou o [!UICONTROL Recently Purchased Items] do seu perfil. Esse comportamento ocorre por design para evitar a poluição não intencional dos dados comportamentais de produção. Para visualizar os resultados de um critério de [!UICONTROL Recently Viewed Items] ou [!UICONTROL User-Based Recommendations], primeiro navegue no site fora do modo de QA e, em seguida, use a mesma sessão para abrir um link de modo de QA.

## Uso do download de CSV para visualizar recomendações

Em alguns casos, talvez você queira auditar os itens específicos recomendados. Isso é particularmente útil ao usar algoritmos como o [!UICONTROL People Who Viewed This, Viewed That], em que um conjunto diferente de itens é recomendado dependendo do item que o usuário está visualizando no momento, e você pode ter milhares ou milhões de itens diferentes no catálogo.

Os resultados não estão disponíveis para download até que um status [!UICONTROL Results Ready] seja mostrado para pelo menos um algoritmo na atividade.

Para baixar os resultados para visualização, clique no ícone de menu no canto superior direito da página Visão geral da atividade e clique em **[!UICONTROL Download data]**.

![Opção Baixar dados](/help/main/c-recommendations/t-create-recs-activity/assets/download-data.png)

Um arquivo CSV está sendo baixado. Abra-o para ver os itens recomendados:

![Arquivo CSV de itens recomendados](/help/main/c-recommendations/t-create-recs-activity/assets/recommended-items.png)

Da esquerda para a direita é uma lista de itens recomendados, neste caso, os mais vistos. As recomendações são separadas por ambiente. Nesse caso, somente o ambiente de Produção tem recomendações.

Se um asterisco (*) for o primeiro valor de uma linha, ele indicará [itens de backup](/help/main/c-recommendations/c-algorithms/backup-recs.md). Os itens de backup são exibidos se nem todos os slots de um design puderem ser preenchidos pelos itens recomendados do algoritmo (critérios).

Para outros tipos de algoritmo baseados em um valor de chave, como [!UICONTROL People Who Viewed This, Viewed That], os valores de chave (ou seja, os itens &quot;Este&quot;) são listados na coluna mais à esquerda e os itens recomendados (ou seja, os itens &quot;Aquele&quot;) são listados da esquerda para a direita nas colunas Recommendation_X.

>[!NOTE]
>
>Os downloads de resultados não estão disponíveis para atividades que contêm um algoritmo [!UICONTROL User-Based Recommendations]. Os downloads de resultados não estão disponíveis para os critérios que usam a lógica de recomendação [!UICONTROL Recently-Viewed Items].

## Ativar sua atividade do Recommendations

Na guia [!UICONTROL Activity Overview], clique na seta suspensa Status e selecione **[!UICONTROL Activate]**.

Se sua atividade [!UICONTROL Recommendations] estiver atualmente no estado [!UICONTROL Inactive], a lista suspensa será rotulada [!UICONTROL Inactive].

Após alguns segundos a alguns minutos, o status muda para [!UICONTROL Live].

Também é possível desativar ou arquivar a atividade usando a mesma lista suspensa.

## Como evitar interrupções ao alterar as configurações do Recommendations

Alterar as configurações de coleções, critérios, promoções ou design do [!DNL Recommendations] em uma atividade ativa pode resultar na invalidade dos resultados do algoritmo e na alteração do status de um algoritmo para [!UICONTROL Results Not Ready].

Para evitar interromper uma atividade ativa, recomendamos seguir a seguinte abordagem ao modificar uma atividade ativa:

1. Duplique a atividade original (atividade 1) e os critérios que deseja modificar para criar uma nova atividade (atividade 2).
1. Faça alterações na atividade duplicada (atividade 2) e nos critérios e aguarde o algoritmo gerar resultados.
1. Pré-visualize a atividade nova e modificada (atividade 2) e confirme se os resultados foram os desejados.
1. Ative a nova atividade (atividade 2).
1. Desative a atividade original (atividade 1).

Se você precisar reter resultados históricos de relatórios na mesma atividade, uma abordagem alternativa é possível, o que pode resultar em uma interrupção temporária na disponibilidade das recomendações:

1. Duplique a atividade original (atividade 1) e os critérios que deseja modificar para criar uma nova atividade (atividade 2).
1. Faça alterações na atividade duplicada (atividade 2) e nos critérios e aguarde o algoritmo gerar resultados.
1. Pré-visualize a atividade nova e modificada (atividade 2) e confirme se os resultados foram os desejados.
1. Pause a atividade nova e modificada (atividade 2) e troque as configurações/critérios pela atividade original (atividade 1).
1. Pré-visualize a atividade original (atividade 1) e confirme se os resultados foram os desejados.
1. Reative a atividade original (atividade 1).
