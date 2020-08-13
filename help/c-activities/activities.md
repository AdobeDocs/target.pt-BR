---
keywords: activities list;activities;activity;activity types;edit activity;activity actions;activity attribute;activity list filter;activity limitations;personalize;personalization
description: As atividades no Adobe Target permitem que você personalize o conteúdo para audiências específicas e teste designs de página
title: As atividades no Adobe Target permitem que você personalize o conteúdo para audiências específicas e teste designs de página.
feature: activities
topic: Standard
uuid: 89dca5b4-c23d-4dfa-8f13-f1b05c7ab22c
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '2094'
ht-degree: 97%

---


# Atividades{#activities}

As atividades no Adobe Target permitem que você personalize o conteúdo para audiências específicas e teste designs de página.

Por exemplo, você pode criar uma atividade que teste duas landing pages diferentes, uma destacando informações sobre sapatos femininos de verão e outra destacando um vestuário de verão mais amplo. A atividade determina as condições que controlam quando cada uma dessas páginas de aterrissagem será exibida e as métricas que determinam qual página tem maior sucesso. A atividade está configurada para iniciar e terminar quando as condições específicas forem cumpridas, como entre datas específicas, ou para iniciar quando a atividade for aprovada e terminar quando ela for desativada.

Ao projetar uma atividade, você deve planejar com cuidado. Determine quando a atividade vai começar e quanto tempo ela durará. Depois, relacione as ofertas e atribua um público-alvo a cada uma.

## Tipos de atividades

O Target inclui vários tipos de atividades. A tabela a seguir fornece uma visão geral de cada tipo de atividade com links para ajudá-lo a saber mais. Para ajudá-lo a escolher de maneira mais eficaz o melhor tipo de atividade para suas finalidades, também criamos o [Guia de atividades do Adobe Target](/help/c-activities/target-activities-guide.md).

| Tipo de atividade | Descrição |
|--- |--- |
| [Teste A/B](/help/c-activities/t-test-ab/test-ab.md) | O teste A/B compara duas ou mais versões do conteúdo do seu site para ver qual versão melhora suas conversões durante um período de teste pré-especificado.<br>**Observação:** agora você pode incluir [recomendações nas atividades de Teste A/B](/help/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/c-intro/intro.md#premium). |
| [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | A Alocação automática identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor a fim de aumentar as conversões enquanto o teste continua a ser executado e aprendido.<br>**Observação:** agora você pode incluir [recomendações nas atividades de Alocação automática](/help/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/c-intro/intro.md#premium). |
| [Direcionamento automático](/help/c-activities/auto-target-to-optimize.md)<br>![Target Premium](/help/assets/premium.png) | O Direcionamento automático usa aprendizagem de máquina avançada para identificar várias experiências definidas pelo profissional de marketing com desempenho elevado e retorna a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares, a fim de personalizar o conteúdo e gerar conversões.<br>**Observação:** agora você pode incluir [recomendações nas atividades de Direcionamento automático](/help/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/c-intro/intro.md#premium). |
| [Uso de dados do Analytics](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A4T) | Você pode configurar uma atividade para usar o [!DNL Adobe Analytics] como fonte de geração de relatórios. Este tipo de atividade requer a vinculação da sua conta da [!DNL Adobe Experience Cloud] ao [!DNL Analytics] e ao [!DNL Target]. |
| [Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | O Teste multivariado (MVT) compara combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico e identifica qual elemento afeta mais o sucesso da atividade. |
| [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md) | O Direcionamento de experiência (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.<br>**Observação:** agora você pode incluir [recomendações nas atividades de Direcionamento de experiência](/help/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/c-intro/intro.md#premium). |
| [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![Target Premium](/help/assets/premium.png) | A Personalização automatizada (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançada para corresponder diferentes variações a cada visitante com base em seu perfil de cliente individual, a fim de personalizar o conteúdo e impulsionar conversões. |
| [Recommendations](/help/c-recommendations/recommendations.md)<br>![Target Premium](/help/assets/premium.png) | Uma recomendação determina como um produto é sugerido para um usuário do site, dependendo das atividades desse usuário no site.<br>Por exemplo, talvez você queira incentivar as pessoas que compraram uma mochila a pensar em comprar um tênis para caminhada e bastões de marcha. Você pode criar uma recomendação que mostre itens que são frequentemente comprados juntos, usando o algoritmo &quot;Pessoas que compraram isso também compraram aquilo&quot;. Ou talvez você queira incentivar os visitantes a passarem mais tempo no seu site de mídia recomendando vídeos semelhantes aos que eles assistiram, usando o algoritmo &quot;Pessoas que visualizaram isso também visualizaram aquilo&quot;.<br>**Observação:** agora, você pode incluir recomendações nas atividades de Teste A/B (incluindo Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT). Consulte [Recommendations como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md). |

## Lista de atividades {#section_DE8E2DB30D534962A931EF8BB48240F5}

A lista de [!UICONTROL Atividades] é a exibição padrão ao abrir o [!DNL Target]. Você pode criar novas atividades nesta página e gerenciar as atividades existentes.

Você também pode exibir a lista de [!UICONTROL Atividades] clicando na guia [!UICONTROL Atividades] na parte superior da interface do usuário do [!DNL Target].

![Lista de atividades](/help/c-activities/assets/activities-list.png)

A lista de Atividades fornece uma visão geral de todas as atividades:

| Elemento | Descrição |
|--- |--- |
| Tipo | O tipo de atividade, como A/B ou MVT. |
| Nome | O nome da atividade. |
| URL | O URL aparece em texto mais claro sob o nome.<br>O URL da atividade identifica onde a atividade é exibida. Isso o ajuda a identificar uma atividade rapidamente e determinar se uma determinada página já tem um teste em execução.<br>Se um teste for executado em vários URLs, um link mostrará quantos outros URLs serão usados. Clique no link para exibir a lista completa de URLs dessa atividade.<br>Você pode pesquisar com base no URL. Use a lista suspensa próxima à caixa de pesquisa e selecione [!UICONTROL Pesquisar URL]. |
| Status | O status da atividade pode ser um dos seguintes:<ul><li>**Ao vivo**: A atividade está em execução atualmente.</li><li>**Rascunho**: A configuração da atividade foi iniciada, mas a atividade ainda não está pronta para execução.</li><li>**Programado**: A atividade está pronta para ser ativada na data e hora de início especificadas.</li><li>**Inativo**: a atividade foi pausada ou desativada.</li><li>**Sincronização**: a atividade foi salva e está sendo sincronizada com a rede de entrega do Target.</li><li>**Encerrado**: A data e hora de término especificadas foram atingidas e a atividade não está mais sendo veiculada.</li><li>**Arquivado**: a atividade foi arquivada. Você pode ativar uma atividade arquivada para usá-la novamente.</li></ul>**Observação**: Quando você executa determinadas ações, como ativar uma atividade fora da interface do usuário usando métodos de API, a atualização pode levar até dez minutos para se propagar para a interface do usuário. |
| Fonte | Mostra onde a atividade foi criada:<ul><li>Adobe Target</li><li>Adobe Target Classic</li><li>Adobe Experience Manager (AEM)</li><li>Adobe Mobile Services (AMS)</li></ul> |
| Propriedade | Mostra a [propriedade](/help/administrating-target/c-user-management/property-channel/property-channel.md) da atividade. |
| Aumento estimado na receita | Mostra o aumento previsto na receita se 100% do público-alvo visualizar a experiência vencedora.<br>Calculado usando a seguinte fórmula:<br>`(<winning experience> - <control experience>)*<total number of visitors>`<br>Esse número é arredondado para uma casa decimal, no máximo, se o formulário condensado tiver apenas um único dígito antes do decimal. Por exemplo: $ 1.6 milhão, $ 60 mil, $ 900, $ 8.5 mil, $ 205 mil<br>Essa coluna mostra &quot;---&quot; para atividades que não têm dados suficientes para chamar uma exibição vencedora ou não têm uma estimativa de custo.<br>Consulte [Aumento estimado na receita](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações. |
| Última atualização | A data em que a atividade foi atualizada pela última vez e por quem. |

Passe o mouse sobre uma atividade para ver as ações disponíveis.

![Ações de focalização da lista de atividades](/help/c-activities/assets/activities_list_hover.png)

As seguintes ações estão disponíveis (dependendo das suas permissões):

| Ação | Descrição |
| --- | --- |
| Editar | Alterar a atividade. Qualquer atividade pode ser editada.<br>Para obter mais informações sobre as várias maneiras de editar atividades, consulte [Editar uma atividade ou salvar como rascunho](/help/c-activities/edit-activity.md). |
| Desativar | Interrompe uma atividade ao vido ou programada. Uma campanha desativada pode ser reativada ou arquivada<br>Se você desativar ou arquivar uma atividade e depois reativá-la, um visitante continuará fazendo parte dessa atividade após a reativação se ele estiver nela antes de ser desativado ou arquivado. Qualquer métrica de conversão registrada durante o tempo entre os dois eventos não será atribuída àquela atividade. |
| Ativar | Inicia uma atividade inativa ou pronta. |
| Arquivar | Envie a atividade para o arquivo. Por padrão, atividades arquivadas não aparecem mais na lista de atividades. Para ver atividades arquivadas, altere o filtro para que a lista de atividades as inclua. Você pode ativar uma atividade arquivada para usá-la novamente.<br>Se você desativar ou arquivar uma atividade e depois mais tarde reativá-la, um visitante continuará sendo parte daquela atividade após a reativação se estiver nela antes que seja desativada ou arquivada. Qualquer métrica de conversão registrada durante o tempo entre os dois eventos não será atribuída àquela atividade. |
| Copiar | Copia uma atividade. Qualquer atividade pode ser copiada. A cópia de uma atividade cria uma nova atividade com o mesmo nome, com o termo &quot;Cópia&quot; anexado. Por exemplo, um teste chamado &quot;Ofertas do navegador&quot; é copiada para &quot;Cópia de ofertas do navegador&quot;.<br>Ofertas visuais são copiadas com a atividade. As ofertas podem ser editas em segurança na cópia sem afetar a atividade original. As únicas exceções são ofertas e imagens salvas na pasta Conteúdo/Ativos. |
| Excluir | Exclui um rascunho ou atividade.<BR>**OBSERVAÇÃO**: não é possível recuperar as atividades excluídas. A menos que você tenha certeza de que nunca precisará dessa atividade novamente, use a ação [!UICONTROL Arquivar] . Se necessário, é possível reativar a atividade. |

Observe os detalhes a seguir sobre a lista Atividade:

* Atividades arquivadas e encerradas não aparecem na lista [!UICONTROL Atividades]. Para exibir essas atividades, filtre-as pelas configurações de filtro avançadas na grade à esquerda.
* Assim que uma atividade originalmente criada no [!DNL Target Classic] for desativada ou excluída, ela será excluída do [!DNL Target Standard/Premium]. Atividades excluídas criadas originalmente no [!DNL Target Classic] não são enviadas para a pasta [!UICONTROL Arquivo] no [!DNL Target Standard/Premium]. A funcionalidade de pasta arquivada se aplica somente a atividades criadas no [!DNL Target Standard/Premium].
* Todos os tipos de atividades diferentes de [!UICONTROL Personalização automatizada] (AP), [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] oferecem a opção de usar [!DNL Target] ou [!DNL Adobe Analytics] como fonte de dados. [!UICONTROL AP], [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] sempre *usam* dados[!DNL Target].
* As atividades estão disponíveis para vários canais:

   * Sites da Web e de dispositivos móveis
   * Telas e dispositivos conectados à Internet, incluindo quiosques e caixas eletrônicos
   * Email e outros canais de aquisição ou sites parceiros
   * Aplicativos móveis
   * Em qualquer outro lugar você pode entregar conteúdo marcado

## Classificação e filtragem da lista de atividades {#section_41DAD479FFF740E2BB67BF4825955670}

Por padrão, a lista é classificada pela data em que a atividade foi modificada pela última vez, com a mais recente no topo. No entanto, há várias opções de filtro para ajudar a personalizar a lista a fim de mostrar as atividades que você deseja ver.

### Pesquisa  {#search-heading}

Use o campo de pesquisa para procurar atividades que correspondam a seus critérios de pesquisa.

![Pesquisa de atividades](/help/c-activities/assets/activities_search_new.png)

O campo de pesquisa inclui um menu suspenso que ajuda a limitar a pesquisa com a especificação de um dos seguintes filtros de pesquisa: [!UICONTROL Nome da atividade] e [!UICONTROL URL].

### Filtros da lista de atividades

Você pode determinar quais atividades aparecem na lista de atividades pela seleção de filtros da lista.

![Filtrar atividades por tipo](/help/c-activities/assets/activities_filters_new.png)

Você pode filtrar pelas opções a seguir. Em cada categoria, se nada for selecionado, o padrão será Tudo.

| Filtrar categoria | Filtro |
|--- |--- |
| Tipo | Teste A/B: [Manual](/help/c-activities/t-test-ab/test-ab.md), [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) e [Direcionamento automático](/help/c-activities/auto-target-to-optimize.md).<br>[Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>[Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md)<br>[Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md)<br>[Recommendations](/help/c-recommendations/recommendations.md) |
| Status | Ao vivo<br>Rascunho<br>Programado<br>Inativo<br>Sincronização<br>Encerrado<br>Arquivado |
| Fonte de geração de relatórios | Target<br>Analytics |
| Criador de experiência | Visual<br>Baseado em formulário |
| Tipo de métrica | Conversão<br>Receita<br>Envolvimento |
| Fonte da atividade | Adobe Target<br>Adobe Target Classic<br>Adobe Experience Manager<br>Adobe Mobile Services |

### Classificar por atributo de atividade

Clique em um dos seguintes cabeçalhos para definir que as atividades sejam listadas em ordem crescente ou decrescente de acordo com o cabeçalho selecionado.

* Nome da atividade
* Tipo de atividade

![Ordem crescente da lista de atividades](/help/c-activities/assets/activities_list_ascending.png)

## Dicas e truques {#section_F77F30A246A14B538D9363B7F3639F97}

Aproveite o máximo do Adobe Target, aprenda sobre os vários recursos e veja por que você deveria experimentá-los. O recurso de Dicas e truques oferece links para vídeos, casos de uso, blogs, documentação e muito mais.

O recurso Dicas e truques é exibido periodicamente na página de lista de Atividades. Depois de ler ou dispensar uma dica, ela não será exibida novamente até que a próxima dica esteja disponível. Como opção, você pode desativar a exibição de todas as dicas clicando no ícone de Ajuda > [!UICONTROL Desativar a dica do dia].

![Desativar dica do dia](/help/c-activities/assets/tip-disable-new.png)

## Limitações {#section_049D4684403A4E07B998067EB8E9BE56}

Cada atividade do Target tem as seguintes limitações de conteúdo:

| Item | Limite |
|--- |--- |
| Seletores exclusivos | 300  se um seletor se repete em uma experiência diferente, ele é contado uma vez. No entanto, se ele se repete na mesma experiência, ele é contado novamente. |
| Ofertas em cada experiência | 350 |
| Seletores de rastreamento de cliques nas métricas | 50 |
| Mboxes nas métricas | 50 |
| Públicos-alvo e localizações | 50 A combinação de públicos-alvo e localizações (mbox) não deve ser maior do que 50. |

A atividade não pode ser salva se exceder qualquer um desses limites.

O aumento dos números desses itens na atividade também aumenta o tempo necessário para sincronizar a atividade no Target.

Para conhecer outros limites do Visual Experience Composer, consulte [Limitações do Visual Experience Composer](../c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Atributos importados para o Target de atividades atualizadas externamente {#section_802B0D174E6A44E1A96F404CA81AAE44}

Se atividades criadas no [!DNL Target] forem carregadas de fora do [!DNL Target] (por exemplo, através do Adobe I/O), os seguintes atributos de atividade serão importados novamente ao [!DNL Target]:

`thirdpartyId`

`startDate`

`endDate`

`status`

`priority`

`marketingCloudMetadata(remoteModifiedBy)`

Esse trabalho de importação será executado quando a página de atividades for aberta, com um atraso máximo de dez minutos. (KB-1526)

## Vídeos de treinamento {#section_BE80D13A2E81460C885F902010E1AD87}

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Etiqueta de ![Visão Geral de Tipos de atividades (9:03)](/help/assets/overview.png)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium].

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Como gerenciar o selo de ![visão geral do Atividade (5:55)](/help/assets/overview.png)

Este vídeo explica como usar a lista de Atividades para gerenciar as atividades.

* Defina o termo *atividade*
* Encontre atividades na lista de Atividades
* Editar, desativar, copiar e excluir atividades

>[!VIDEO](https://video.tv.adobe.com/v/18550)
