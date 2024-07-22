---
keywords: lista de atividades;atividades;atividade;tipos de atividade;editar atividade;ações da atividade;atributo da atividade;filtro da lista de atividades;limitações da atividade;personalizar;personalização
description: Saiba como as atividades do  [!DNL Target] permitem personalizar o conteúdo para públicos específicos e testar designs de página.
title: Como posso personalizar o conteúdo e testar designs de página com o  [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: be63fa4c89f229e3f4566cb400e1268d2cdf08d2
workflow-type: tm+mt
source-wordcount: '2290'
ht-degree: 36%

---

# Atividades

As atividades no [!DNL Adobe Target] permitem personalizar o conteúdo para públicos específicos e testar designs de página.

Por exemplo, você pode criar uma atividade que teste duas landing pages diferentes, uma destacando informações sobre sapatos femininos de verão e outra destacando um vestuário de verão mais amplo. A atividade determina as condições que controlam quando cada uma dessas páginas de aterrissagem será exibida e as métricas que determinam qual página tem maior sucesso. A atividade está configurada para iniciar e terminar quando as condições específicas forem cumpridas, como entre datas específicas, ou para iniciar quando a atividade for aprovada e terminar quando ela for desativada.

Ao projetar uma atividade, você deve planejar com cuidado. Determine quando a atividade começa e quanto tempo ela dura. Depois, relacione as ofertas e atribua um público-alvo a cada uma.

## Lista de atividades {#section_DE8E2DB30D534962A931EF8BB48240F5}

A lista [!UICONTROL Activities] é o modo de exibição padrão quando você abre [!DNL Target]. Você pode criar atividades nesta página e gerenciar atividades existentes.

Você também pode exibir a lista [!UICONTROL Activities] clicando na guia [!UICONTROL Activities] na parte superior da interface do usuário do [!DNL Target].

![Lista de atividades](/help/main/c-activities/assets/activities-list-new.png)

A lista [!UICONTROL Activities] fornece uma visão geral de todas as atividades e permite executar várias ações:

| Elemento | Descrição |
|--- |--- |
| Painel de navegação esquerdo | Alterne entre suas atividades salvas ou ativas e as [atividades de rascunho](/help/main/c-activities/edit-activity.md) ou com falha. |
| Ícone do [!UICONTROL Show filters]<P>![Ícone Mostrar Filtros](/help/main/c-activities/assets/show-filters-icon.png) | Acesse filtros clicando no ícone **[!UICONTROL Show Filters]** próximo à parte superior da lista.<P>Para obter mais informações, consulte [Aplicar filtros à lista de Atividades](#filters) abaixo. |
| Caixa de pesquisa | Localize rapidamente uma atividade ou reduza o número de atividades exibidas na lista [!UICONTROL Activity]. Você pode pesquisar por [!UICONTROL Name], [!UICONTROL URL] ou [!UICONTROL ID]. |
| [!UICONTROL Create Activity] | Crie uma atividade. Para obter mais informações sobre como criar os vários tipos de atividades, consulte: <ul><li>[Criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Criar uma atividade de alocação automática](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Criar uma atividade de direcionamento automático](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Criar uma atividade de Automated Personalization](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Criar uma atividade de direcionamento de experiência](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Criar um teste multivariado](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Criar uma atividade do Recommendations](/help/main/c-recommendations/recommendations.md)</li></ul>Para obter mais informações sobre cada tipo, consulte [Tipos de atividade](#types) abaixo. |
| [!UICONTROL Create mobile preview link]<P>![Mais menu de ações](/help/main/c-activities/assets/icon-create-mobile-link.png) | Use os [links de visualização móvel](https://experienceleague.adobe.com/docs/target-dev/developer/mobile-apps/target-mobile-preview.html?lang=pt-BR) para realizar facilmente tarefas completas de controle da qualidade em atividades de aplicativos para dispositivos móveis.<P>Clique no ícone **Mais opções** (as reticências verticais), selecione o **Criar link de visualização móvel** e escolha as atividades que deseja testar em dispositivos móveis. |
| Personalizar tabela<P>![Ícone Personalizar tabela](/help/main/c-activities/assets/icon-customize-table.png) | Altere quais colunas são exibidas na lista [!UICONTROL Activity] clicando no ícone **[!UICONTROL Customize Table]** no lado superior direito da tabela e selecionando ou desmarcando as colunas desejadas.<P>As alterações são aplicadas à sua conta e permanecem ativas mesmo depois que você sair do [!DNL Target]. |
| Caixas de seleção de operações em massa | Executar operações em massa em todas as atividades ou em atividades selecionadas.<P>Para obter uma lista de ações disponíveis (dependendo das suas permissões e do status da atividade), consulte [Executar ações rápidas](#quick-actions) abaixo. |
| [!UICONTROL Type] | O tipo de atividade. A coluna [!UICONTROL Type] permite identificar rapidamente cada atividade por tipo. <ul><li>AB-M: manual [!UICONTROL A/B Test]</li><li>AB-AA: [!UICONTROL Auto-Allocate]</li><li>AB-AT: [!UICONTROL Auto-Target]</li><li>PA: [!UICONTROL Automated Personalization]</li><li>XT: [!UICONTROL Experience Targeting]</li><li>MVT: [!UICONTROL Multivariate Test]</li><li>GRAVAÇÃO: [!UICONTROL Recommendations]</li></ul>Para obter mais informações sobre cada tipo, consulte [Tipos de atividade](#types) abaixo. |
| [!UICONTROL Name] | O nome da atividade. Clique em um nome de atividade para exibir a página [!UICONTROL Overview] dessa atividade. <P>Clique no ícone **[!UICONTROL Quick Info]** ao lado de cada nome de atividade para exibir mais informações sobre essa atividade em um cartão pop-up.<p>Clique no ícone **[!UICONTROL More actions]** (as reticências horizontais) ao lado de cada nome de atividade para abrir um menu que permite executar ações rápidas em uma atividade. As seguintes ações estão disponíveis (dependendo das suas permissões e do status da atividade): [!UICONTROL Edit], [!UICONTROL Activate], [!UICONTROL Deactivate], [!UICONTROL Copy], [!UICONTROL Delete] e [!UICONTROL Archive]. Para obter mais informações sobre cada ação, consulte [Executar ações rápidas](#quick-actions) abaixo.<P>Clique no cabeçalho da tabela para classificar a lista alfabeticamente em ordem crescente ou decrescente por nome. |
| [!UICONTROL Status] | O status da atividade pode ser um dos seguintes:<ul><li>**Ao vivo**: A atividade está em execução atualmente.</li><li>**Rascunho**: A configuração da atividade foi iniciada, mas a atividade está em [modo de rascunho](/help/main/c-activities/edit-activity.md) e ainda não está pronta para execução.</li><li>**Programado**: A atividade está pronta para ser ativada na data e hora de início especificadas.</li><li>**Inativo**: a atividade foi pausada ou desativada.</li><li>**Sincronizando**: a atividade foi salva e está sendo sincronizada com a rede de entrega [!DNL Target].</li><li>**Encerrado**: a data e hora de término especificadas foram atingidas e a atividade não está mais sendo veiculada.</li><li>**Arquivado**: a atividade foi arquivada. Você pode ativar uma atividade arquivada para usá-la novamente.</li></ul>**Observação**: quando você executa determinadas ações, como ativar uma atividade fora da interface do usuário [!DNL Target] usando métodos de API, a atualização pode levar até dez minutos para se propagar para a interface do usuário [!DNL Target]. |
| [!UICONTROL Last Updated] | A data e a hora em que a atividade foi atualizada pela última vez e por quem.<P>Clique no cabeçalho da tabela para classificar a lista em ordem crescente ou decrescente por data. |
| [!UICONTROL Priority] | A prioridade da atividade.<P>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<P>Dependendo das [configurações](/help/main/administrating-target/reporting.md), a interface do usuário do [!DNL Target] e as opções para [!UICONTROL Priority] variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999. |
| [!UICONTROL Property] | Mostra a [propriedade](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) da atividade.<P>As permissões de usuários corporativos são um recurso do [Target Premium](/help/main/c-intro/intro.md#premium). |
| [!UICONTROL Estimated Lift in Revenue] | Mostra o aumento previsto na receita se 100% do público-alvo visualizar a experiência vencedora.<P>Calculado com o uso da seguinte fórmula:<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>Esse número é arredondado para uma casa decimal, no máximo, se a forma condensada tiver apenas um único dígito antes do decimal. Por exemplo: US$ 1,6 milhões, US$ 60 mil, US$ 900, US$ 8,5 mil, US$ 205 mil<P>Essa coluna mostra &quot;---&quot; para atividades que não têm dados suficientes para chamar um uma exibição vencedora ou não têm uma estimativa de custo.<P>Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações. |
| [!UICONTROL Source] | Mostra onde a atividade foi criada: [!DNL Adobe Target], [API do Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=pt-BR), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=pt-BR), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=pt-BR) ou [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Location] | O URL da atividade identifica onde a atividade é exibida. Essa coluna ajuda você a identificar rapidamente uma atividade e determinar se uma determinada página já tem uma atividade em execução nela.<P>Se uma atividade for executada em vários URLs, um link mostrará quantos outros URLs serão usados. Clique no link para exibir a lista completa de URLs dessa atividade.<P>Você pode pesquisar com base no URL. Use a lista suspensa próxima à caixa de pesquisa e selecione [!UICONTROL URL]. |
| Autor | O nome da pessoa que criou a atividade. |
| [!UICONTROL Decisioning Method] | O método de decisão usado em cada atividade: [Server-Side](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=pt-BR) ou [Client-Side](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html). |

## Tipos de atividades  {#types}

[!DNL Target] inclui vários tipos de atividades. A tabela a seguir fornece uma visão geral de cada tipo de atividade com links para ajudá-lo a saber mais. Para ajudá-lo a escolher de maneira mais eficaz o melhor tipo de atividade para suas finalidades, também criamos o [Guia de atividades do Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Tipo de atividade | Descrição |
|--- |--- |
| [Teste A/B](/help/main/c-activities/t-test-ab/test-ab.md) | O teste A/B compara duas ou mais versões do conteúdo do site para ver qual versão melhora mais suas conversões durante um período de teste pré-especificado. |
| [Alocação automática](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate], um tipo de teste A/B, identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor a fim de aumentar as conversões enquanto o teste continua a ser executado e aprendido. |
| [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | O Direcionamento automático, um tipo de teste A/B, usa aprendizagem de máquina avançada para identificar várias experiências definidas pelo profissional de marketing com desempenho elevado e retorna a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares, para personalizar o conteúdo e gerar conversões. |
| [Teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | O [!UICONTROL Multivariate Testing] (MVT) compara combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico e identifica qual elemento afeta mais o sucesso da atividade. |
| [Direcionamento de experiência](/help/main/c-activities/t-experience-target/experience-target.md) | O [!UICONTROL Experience Targeting] (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing. |
| [Personalização automatizada](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | A [!UICONTROL Automated Personalization] (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançada para corresponder diferentes variações a cada visitante com base em seu perfil de cliente individual, para personalizar o conteúdo e gerar conversões. |
| [Recommendations](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Uma recomendação determina como um produto é sugerido para um visitante do site, dependendo das atividades desse visitante no site.<P>Por exemplo, talvez você queira incentivar as pessoas que compraram uma mochila a pensar em comprar um tênis para caminhada e bastões de marcha. Você pode criar uma recomendação que mostre itens que são frequentemente comprados juntos, usando o algoritmo &quot;Pessoas que compraram isso também compraram aquilo&quot;. Ou talvez você queira incentivar os visitantes a passar mais tempo em seu site de mídia, recomendando vídeos semelhantes ao vídeo que estão assistindo, usando o algoritmo &quot;Pessoas que viram isto viram aquilo&quot;.<P>**OBSERVAÇÃO**: você também pode incluir recomendações nas atividades [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] e [!UICONTROL Experience Targeting] (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/main/c-intro/intro.md#premium). |

## Aplicar filtros à lista de Atividades {#filters}

Acesse filtros clicando no ícone **[!UICONTROL Show Filters]** próximo à parte superior da lista.

![Opções de filtro](/help/main/c-activities/assets/show-filters-options.png)

O menu permite filtrar atividades pelos seguintes atributos:
|Detalhes do atributo|
| — | — |
|[!UICONTROL Type]|Filtrar por [tipo de atividade](#types).|
|[!UICONTROL Status]|Filtrar por status de atividade.|
|[!UICONTROL Reporting Source]|Filtrar por fonte de relatórios.<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md): Exibir atividades que usam [!UICONTROL Analytics for Target] (A4T) como fonte de relatórios.</li><li>[[!DNL Target]](/help/main/c-reports/reports.md): Exibir atividades que usam [!DNL Target] como fonte de relatórios.</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md): Exibir atividades que usam [!DNL Adobe Customer Analytics] como fonte de relatórios.</li></ul>|
|[!UICONTROL Experience Composer]|Filtro pelo qual o Experience Composer foi usado durante a criação da atividade:<ul><li>[Visual](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): mostra as atividades que foram criadas usando o [!UICONTROL Visual Experience Composer] (VEC).</li><li>[Baseado em Formulário](/help/main/c-experiences/form-experience-composer.md): exibir atividades que foram criadas usando o [!UICONTROL Form-Based Experience Composer].</li></ul>|
|[!UICONTROL Metrics Type]|Filtro pelo qual [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md) foi escolhida durante a criação da atividade.<ul><li>Conversão</li><li>Receita</li><li>Envolvimento</li></ul>|
|[!UICONTROL Decisioning Method]|Filtre pelo método de decisão usado em cada atividade<ul><li>[Lado do servidor](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=pt-BR): exibir atividades que usam a decisão do lado do servidor.</li><li>[Lado do cliente](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html): exibir atividades que usam decisões do lado do cliente.</li></ul>|
|[!UICONTROL Activity Source]|Filtre pela fonte de atividade usada para criar cada atividade.<ul><li>[!DNL Adobe Target]</li><li>[API Adobe Target](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=pt-BR)</li><li>[Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=pt-BR)</li><li>[Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=pt-BR)</li><li>[Serviços Adobe Mobile](https://developer.adobe.com/client-sdks/documentation/)</li></ul>|
|[!UICONTROL Property]|Filtre pela [propriedade](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) em que a atividade foi criada.|

## Executar ações rápidas {#quick-actions}

Clique no ícone **[!UICONTROL More actions]** (as reticências horizontais) ao lado de cada nome de atividade para abrir um menu que permite executar ações rápidas em uma atividade.

![Opções de ações rápidas](/help/main/c-activities/assets/quick-actions.png)

As seguintes ações estão disponíveis (dependendo das suas permissões e do status da atividade):

| Ação | Descrição |
| --- | --- |
| [!UICONTROL Edit] | Alterar a atividade. Qualquer atividade pode ser editada.<P>Para obter mais informações sobre as várias maneiras de editar atividades, consulte [Editar uma atividade ou salvar como rascunho](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Deactivate] | Interrompe uma atividade ao vido ou programada. Uma atividade desativada pode ser reativada ou arquivada.<P>Se você desativar ou arquivar uma atividade e depois mais tarde reativá-la, um visitante continuará sendo parte daquela atividade após a reativação se estiver nela antes que seja desativada ou arquivada. Qualquer métrica de conversão registrada durante o tempo entre os dois eventos não será atribuída àquela atividade. |
| [!UICONTROL Activate] | Inicie uma atividade inativa ou uma atividade que esteja pronta para ser ativada. |
| [!UICONTROL Archive] | Envie a atividade para o arquivo. Por padrão, as atividades arquivadas não aparecem mais na lista [!UICONTROL Activities]. Para ver atividades arquivadas, altere o filtro para que a lista de atividades as inclua. Você pode ativar uma atividade arquivada para usá-la novamente.<P>Se você desativar ou arquivar uma atividade e depois mais tarde reativá-la, um visitante continuará sendo parte daquela atividade após a reativação se estiver nessa atividade antes que ela seja desativada ou arquivada. Qualquer métrica de conversão registrada durante o tempo entre os dois eventos não será atribuída àquela atividade. |
| [!UICONTROL Copy] | Copia uma atividade. Qualquer atividade pode ser copiada. A cópia de uma atividade cria uma nova atividade com o mesmo nome, com o termo &quot;Cópia&quot; anexado. Por exemplo, um teste chamado &quot;Ofertas do navegador&quot; é copiada para &quot;Cópia de ofertas do navegador&quot;.<P>Ofertas visuais são copiadas com a atividade. As ofertas podem ser editas em segurança na cópia sem afetar a atividade original. As únicas exceções são ofertas e imagens salvas na pasta Conteúdo/Ativos. |
| [!UICONTROL Delete] | Exclui um rascunho ou atividade.<P>**OBSERVAÇÃO**: as atividades excluídas não podem ser recuperadas. A menos que você tenha certeza de que nunca precisará dessa atividade novamente, use a ação [!UICONTROL Archive]. Se necessário, é possível reativar a atividade. |

## Considerações

Observe os seguintes detalhes sobre a lista [!UICONTROL Activity]:

* Atividades arquivadas e encerradas não aparecem na lista [!UICONTROL Activities]. Para exibir essas atividades, filtre-as usando o [ícone de Filtros](#filters) na parte superior da lista.
* Quando uma atividade originalmente criada em [!DNL Target Classic] é desativada ou excluída, ela é excluída de [!DNL Target Standard/Premium]. Atividades excluídas criadas originalmente em [!DNL Target Classic] não são enviadas para a pasta [!UICONTROL Archive] em [!DNL Target Standard/Premium]. A funcionalidade de pasta arquivada se aplica somente a atividades criadas no [!DNL Target Standard/Premium].
* Todos os tipos de atividades diferentes de [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] oferecem a opção de usar [!DNL Target] ou [!DNL Adobe Analytics] como fonte de dados. [!UICONTROL AP], [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] *sempre* usam os dados [!DNL Target].
* As atividades estão disponíveis para vários canais:

   * Sites da Web e de dispositivos móveis
   * Telas e dispositivos conectados à Internet, incluindo quiosques e caixas eletrônicos
   * Email e outros canais de aquisição ou sites parceiros
   * Aplicativos móveis
   * Em qualquer outro lugar você pode entregar conteúdo marcado

## Limitações {#section_049D4684403A4E07B998067EB8E9BE56}

Cada atividade do Target tem as seguintes limitações de conteúdo:

| Item | Limite |
|--- |--- |
| Seletores únicos | 300 se um seletor se repete em uma experiência diferente, ele é contado uma vez. No entanto, se ele se repete na mesma experiência, ele é contado novamente. |
| Ofertas em cada experiência | 350 |
| Seletores de rastreamento de cliques nas métricas | 50 |
| Mboxes nas métricas | 50 |
| Públicos-alvo e localizações | 50 combinações de públicos-alvo e localizações (mbox) não devem ser maiores que 50. |

A atividade não pode ser salva se exceder qualquer um desses limites.

O aumento do número desses itens na sua atividade também aumenta o tempo necessário para sincronizar a atividade em [!DNL Target].

Para obter limites adicionais do VEC do V[!UICONTROL isual Experience Composer], consulte [Limitações do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Atributos importados para [!DNL Target] de atividades atualizadas fora de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Se atividades criadas em [!DNL Target] forem atualizadas de fora de [!DNL Target] (por exemplo, via API), os seguintes atributos de atividade serão importados novamente para [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority` e `marketingCloudMetadata(remoteModifiedBy)`.

Esse trabalho de importação é executado quando a página de atividades é aberta, com um atraso máximo de dez minutos.

## Vídeos de treinamento {#section_BE80D13A2E81460C885F902010E1AD87}

O vídeo a seguir contém mais informações sobre os conceitos discutidos neste artigo.

### Tipos de atividades (9:03)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium].

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)

