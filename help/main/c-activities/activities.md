---
keywords: lista de atividades;atividades;atividade;tipos de atividade;editar atividade;ações da atividade;atributo da atividade;filtro da lista de atividades;limitações da atividade;personalizar;personalização
description: Personalize o conteúdo e teste designs de página para públicos-alvo específicos com  [!DNL Adobe Target]  atividades.
title: Como posso personalizar o conteúdo e testar designs de página com o  [!DNL Target]?
feature: Activities
exl-id: 7e61525d-b2db-44f6-a7c2-df5a8d28eca2
source-git-commit: 25b448ad99618dca8b5aa4b698976a3d9aa76dec
workflow-type: tm+mt
source-wordcount: '2237'
ht-degree: 26%

---

# Visão geral das atividades

Personalize o conteúdo e teste designs de página para públicos-alvo específicos com atividades [!DNL Adobe Target].

Por exemplo, você pode criar uma atividade que teste duas landing pages diferentes, uma destacando informações sobre sapatos femininos de verão e outra destacando um vestuário de verão mais amplo. A atividade determina as condições que controlam quando cada uma dessas landing pages é exibida e as métricas que determinam qual página é mais bem-sucedida. A atividade é configurada para começar e terminar quando condições específicas são atendidas, como entre datas específicas. Ou você pode optar por iniciar quando a atividade for aprovada e terminar quando ela for desativada.

Ao projetar uma atividade, você deve planejar com cuidado. Determine quando a atividade começa e quanto tempo ela dura. Depois, relacione as ofertas e atribua um público-alvo a cada uma.

## Lista de atividades {#section_DE8E2DB30D534962A931EF8BB48240F5}

A lista [!UICONTROL Activities] é o modo de exibição padrão quando você abre [!DNL Target]. Você pode criar atividades nesta página e gerenciar atividades existentes.

Você também pode exibir a lista [!UICONTROL Activities] clicando na guia [!UICONTROL Activities] na parte superior da interface do usuário do [!DNL Target].

A lista [!UICONTROL Activities] fornece uma visão geral de todas as atividades na implementação do [!DNL Target] e permite que você execute várias ações.

A tabela a seguir ajuda você a entender vários elementos da lista [!UICONTROL Activities] na interface do usuário [!DNL Target]:

| Elemento | Descrição |
|--- |--- |
| Ícone do [!UICONTROL Show filters]<P>![Ícone Mostrar Filtros](/help/main/assets/icons/Filter.svg) | Acesse filtros clicando no ícone **[!UICONTROL Show Filters]** próximo à parte superior da lista para filtrar as atividades por [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type], [!UICONTROL Decisioning Source], [!UICONTROL Activity Source] e [!UICONTROL Properties].<P>Os filtros configurados são persistentes na sessão atual.<P>Para obter mais informações, consulte [Aplicar filtros à [!UICONTROL Activities] lista](#filters) abaixo. |
| Pesquisar campos | Localize rapidamente uma atividade ou reduza o número de atividades exibidas na lista [!UICONTROL Activity]. Você pode pesquisar por [!UICONTROL Activity Name], [!UICONTROL URL] ou [!UICONTROL ID] usando o menu suspenso.<P>As opções de pesquisa configuradas são persistentes na sessão atual. |
| [!UICONTROL Create Activity] | Crie uma atividade.<P>Para obter mais informações sobre como criar os vários tipos de atividades, consulte: <ul><li>[Criar uma atividade [!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md)</li><li>[Criar uma atividade [!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/create-auto-allocate-activity.md)</li><li>[Criar uma atividade [!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/create-auto-target.md)</li><li>[Criar uma atividade [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/create-ap-activity.md)</li><li>[Criar uma atividade [!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/t-xt-create/xt-create.md)</li><li>[Criar uma atividade](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/create-multivariate-test.md)</li><li>[Criar uma atividade [!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)</li></ul>Para obter mais informações sobre cada tipo, consulte [Tipos de atividade](#types) abaixo. |
| [!UICONTROL Create mobile preview link]<P>![Mais menu de ações](/help/main/assets/icons/MoreVertical.svg) | Use os [links de visualização móvel](https://experienceleague.adobe.com/pt-br/docs/target-dev/developer/mobile-apps/target-mobile-preview) para realizar facilmente tarefas completas de controle da qualidade em atividades de aplicativos para dispositivos móveis.<P>Clique no ícone **Mais opções**, selecione o **Criar link de visualização móvel** e escolha as atividades que deseja testar em dispositivos móveis. |
| Personalizar tabela<P>![Ícone Personalizar tabela](/help/main/assets/icons/ColumnSetting.svg) | Altere quais colunas são exibidas na lista [!UICONTROL Activity] clicando no ícone **[!UICONTROL Customize Table]** no lado superior direito da página e selecionando ou desmarcando as colunas desejadas.<P>As alterações são aplicadas à sua conta e permanecem ativas mesmo depois que você sair do [!DNL Target]. |
| Caixas de seleção de operações em massa<P>![Ícone de Operações em Massa](/help/main/assets/icons/Rectangle.svg) | Executar operações em massa em todas as atividades ou em atividades selecionadas.<P>Para obter uma lista de ações disponíveis (dependendo das suas permissões e do status da atividade), consulte [Executar ações rápidas](#quick-actions) abaixo. |
| [!UICONTROL Type] | O tipo de atividade. A coluna [!UICONTROL Type] permite identificar rapidamente cada atividade por tipo. <ul><li>**AB-M**: manual [!UICONTROL A/B Test]</li><li>**AB-AA**: [!UICONTROL Auto-Allocate]</li><li>**AB-AT**: [!UICONTROL Auto-Target]</li><li>**AP**: [!UICONTROL Automated Personalization]</li><li>**XT**: [!UICONTROL Experience Targeting]</li><li>**MVT**: [!UICONTROL Multivariate Test]</li><li>**REC**: [!UICONTROL Recommendations]</li></ul>Para obter mais informações sobre cada tipo, consulte [Tipos de atividade](#types) abaixo. |
| [!UICONTROL Name] | O nome da atividade. Clique no ícone **[!UICONTROL Quick Info]** ( ![Ícone de Informações Rápidas](/help/main/assets/icons/InfoOutline.svg) ) ao lado de cada nome de atividade para exibir mais informações sobre essa atividade em um cartão pop-up, incluindo [!UICONTROL Activity ID], [!UICONTROL Activity Objective], [!UICONTROL Activity Location], [!UICONTROL Goal] e [!UICONTROL Status].<P>Clique no ícone **[!UICONTROL More actions]** ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmallList.svg) ) ao lado de cada nome de atividade para abrir um menu que permite executar ações rápidas em uma atividade. As seguintes ações estão disponíveis (dependendo das suas permissões e do status da atividade): [!UICONTROL Edit], [!UICONTROL Activate], [!UICONTROL Deactivate], [!UICONTROL Copy], [!UICONTROL Delete] e [!UICONTROL Archive].<P>Para obter mais informações sobre cada ação, consulte [Executar ações rápidas](#quick-actions) abaixo.<P>Clique no cabeçalho da tabela para classificar a lista alfabeticamente em ordem crescente ou decrescente por nome. |
| [!UICONTROL Status] | O status da atividade pode ser um dos seguintes:<ul><li>**[!UICONTROL Live]**: a atividade está em execução no momento.</li><li>**[!UICONTROL Draft]**: a configuração da atividade foi iniciada, mas a atividade está em [modo de rascunho](/help/main/c-activities/edit-activity.md) e ainda não está pronta para execução.</li><li>**[!UICONTROL Scheduled]**: A atividade está pronta para ser ativada na data e hora de início especificadas.</li><li>**[!UICONTROL Inactive]**: a atividade foi pausada ou desativada.</li><li>**[!UICONTROL Syncing]**: A atividade foi salva e está sendo sincronizada com a rede de entrega [!DNL Target].</li><li>**[!UICONTROL Ended]**: A data e hora de término especificadas foram atingidas e a atividade não está mais sendo veiculada.</li><li>**[!UICONTROL Archived]**: A atividade foi arquivada. Você pode ativar uma atividade arquivada para usá-la novamente.</li></ul>**Observação**: quando você executa determinadas ações, como ativar uma atividade fora da interface do usuário [!DNL Target] usando métodos de API, a atualização pode levar até dez minutos para se propagar para a interface do usuário [!DNL Target]. |
| [!UICONTROL Last Updated] | A data e a hora em que a atividade foi atualizada pela última vez e por quem.<P>Clique no cabeçalho da tabela para classificar a lista em ordem crescente ou decrescente por data. |
| [!UICONTROL Priority] | A prioridade da atividade.<P>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<P>Dependendo das [configurações](/help/main/administrating-target/reporting.md), a interface do usuário do [!DNL Target] e as opções para [!UICONTROL Priority] variam. Você pode usar as configurações herdadas de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou pode habilitar prioridades otimizadas de 0 a 999.<P>Para obter mais informações sobre configurações de prioridade, consulte [Prioridade](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#section_DCBDC354261F420EBD4B43EA34947BAC) em *Configurações da atividade* em *Metas e configurações*. |
| [!UICONTROL Property] | Mostra a [propriedade](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) da atividade.<P>As permissões de usuários corporativos são um recurso do [Target Premium](/help/main/c-intro/intro.md#premium). |
| [!UICONTROL Estimated Lift in Revenue] | Mostra o aumento previsto na receita se 100% do público-alvo visualizar a experiência vencedora.<P>Calculado com o uso da seguinte fórmula:<P>`(<winning experience> - <control experience>)*<total number of visitors>`<P>Esse número é arredondado para uma casa decimal, no máximo, se a forma condensada tiver apenas um único dígito antes do decimal. Por exemplo: US$ 1,6 milhões, US$ 60 mil, US$ 900, US$ 8,5 mil, US$ 205 mil<P>Essa coluna mostra &quot;---&quot; para atividades que não têm dados suficientes para chamar um uma exibição vencedora ou não têm uma estimativa de custo.<P>Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações. |
| [!UICONTROL Source] | Mostra onde a atividade foi criada: [!DNL Adobe Target], [API do Adobe Target](https://experienceleague.adobe.com/pt-br/docs/target-dev/developer/overview), [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform.html?lang=pt-BR), [Adobe Experience Manager](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=pt-BR) ou [Adobe Mobile Services](https://developer.adobe.com/client-sdks/documentation/). |
| [!UICONTROL Author] | O nome da pessoa que criou a atividade. |
| [!UICONTROL Decisioning Method] | O método de decisão usado em cada atividade: [Server-Side](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=pt-BR) ou [Client-Side](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html?lang=pt-BR). |

<!--|[!UICONTROL Location]|The URL for the activity identifies where the activity is displayed. This column helps you quickly identify an activity and determine whether a particular page already has an activity running on it.<P>If an activity runs on multiple URLs, a link shows how many more URLs are used. Click the link to view the complete list of URLs for that activity.<P>You can search based on the URL. Use the drop-down list next to the search box and select [!UICONTROL URL].|-->

## Tipos de atividades  {#types}

[!DNL Target] inclui vários tipos de atividades. A tabela a seguir fornece uma visão geral de cada tipo de atividade com links para ajudá-lo a saber mais. Para ajudá-lo a escolher de maneira mais eficaz o melhor tipo de atividade para suas finalidades, use o [Guia de Atividades do Adobe Target](/help/main/c-activities/target-activities-guide.md).

| Tipo de atividade | Descrição |
|--- |--- |
| [[!UICONTROL A/B Test]](/help/main/c-activities/t-test-ab/test-ab.md) | O teste A/B compara duas ou mais versões do conteúdo do site para ver qual versão melhora mais suas conversões durante um período de teste pré-especificado. |
| [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | [!UICONTROL Auto-Allocate], um tipo de teste A/B, identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor a fim de aumentar as conversões enquanto o teste continua a ser executado e aprendido. |
| [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md)<P>![Target Premium](/help/main/assets/premium.png) | O Direcionamento automático, um tipo de teste A/B, usa aprendizagem de máquina avançada para identificar várias experiências definidas pelo profissional de marketing com desempenho elevado e retorna a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares, para personalizar o conteúdo e gerar conversões. |
| [[!UICONTROL Multivariate Test]](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md) | O [!UICONTROL Multivariate Testing] (MVT) compara combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico e identifica qual elemento afeta mais o sucesso da atividade. |
| [[!UICONTROL Experience Targeting]](/help/main/c-activities/t-experience-target/experience-target.md) | O [!UICONTROL Experience Targeting] (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing. |
| [[!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/automated-personalization.md)<P>![Target Premium](/help/main/assets/premium.png) | A [!UICONTROL Automated Personalization] (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançada para corresponder diferentes variações a cada visitante com base em seu perfil de cliente individual, para personalizar o conteúdo e gerar conversões. |
| [[!UICONTROL Recommendations]](/help/main/c-recommendations/recommendations.md)<P>![Target Premium](/help/main/assets/premium.png) | Uma recomendação determina como um produto é sugerido para um visitante do site, dependendo das atividades desse visitante no site.<P>Por exemplo, talvez você queira incentivar as pessoas que compraram uma mochila a pensar em comprar um tênis para caminhada e bastões de marcha. Você pode criar uma recomendação que mostre itens que são frequentemente comprados juntos, usando o algoritmo &quot;Pessoas que compraram isso também compraram aquilo&quot;. Ou talvez você queira incentivar os visitantes a passar mais tempo em seu site de mídia, recomendando vídeos semelhantes ao vídeo que estão assistindo, usando o algoritmo &quot;Pessoas que viram isto viram aquilo&quot;.<P>**OBSERVAÇÃO**: você também pode incluir recomendações nas atividades [!UICONTROL A/B Test], [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] e [!UICONTROL Experience Targeting] (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/main/c-intro/intro.md#premium). |

## Aplicar filtros à lista de Atividades {#filters}

Acesse filtros clicando no ícone **[!UICONTROL Show Filters]** ( ![Ícone Mostrar filtros](/help/main/assets/icons/Filter.svg) ) próximo à parte superior da lista.

O menu permite filtrar atividades pelos seguintes atributos:

| Atributo | Detalhes |
| --- | --- |
| [!UICONTROL Type] | Filtrar por [tipo de atividade](#types). |
| [!UICONTROL Status] | Filtrar por status de atividade.<ul><li>**[!UICONTROL Live]**: a atividade está em execução no momento.</li><li>**[!UICONTROL Draft]**: a configuração da atividade foi iniciada, mas a atividade está em [modo de rascunho](/help/main/c-activities/edit-activity.md) e ainda não está pronta para execução.</li><li>**[!UICONTROL Scheduled]**: A atividade está pronta para ser ativada na data e hora de início especificadas.</li><li>**[!UICONTROL Inactive]**: a atividade foi pausada ou desativada.</li><li>**[!UICONTROL Syncing]**: A atividade foi salva e está sendo sincronizada com a rede de entrega [!DNL Target].</li><li>**[!UICONTROL Ended]**: A data e hora de término especificadas foram atingidas e a atividade não está mais sendo veiculada.</li><li>**[!UICONTROL Archived]**: A atividade foi arquivada. Você pode ativar uma atividade arquivada para usá-la novamente.</li></ul> |
| [!UICONTROL Reporting Source] | Filtrar por fonte de relatórios.<ul><li>[[!DNL Analytics]](/help/main/c-integrating-target-with-mac/a4t/a4t.md): Exibir atividades que usam [!UICONTROL Analytics for Target] (A4T) como fonte de relatórios.</li><li>[[!DNL Target]](/help/main/c-reports/reports.md): Exibir atividades que usam [!DNL Target] como fonte de relatórios.</li><li>[[!DNL Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md): Exibir atividades que usam [!DNL Adobe Customer Analytics] como fonte de relatórios.</li></ul> |
| [!UICONTROL Experience Composer] | Filtro pelo qual o Experience Composer foi usado durante a criação da atividade:<ul><li>[Visual](/help/main/c-experiences/c-visual-experience-composer/visual-experience-composer.md): mostra as atividades que foram criadas usando o [!UICONTROL Visual Experience Composer] (VEC).</li><li>[Baseado em Formulário](/help/main/c-experiences/form-experience-composer.md): exibir atividades que foram criadas usando o [!UICONTROL Form-Based Experience Composer].</li></ul> |
| [!UICONTROL Metrics Type] | Filtro pelo qual [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md) foi escolhida durante a criação da atividade.<ul><li>[!UICONTROL Conversion]</li><li>[!UICONTROL Revenue]</li><li>[!UICONTROL Engagement]</li><li>[!UICONTROL Use an Analytics metric]</lI></ul> |
| [!UICONTROL Decisioning Method] | Filtre pelo método de decisão usado em cada atividade.<ul><li>[Lado do servidor](https://experienceleague.adobe.com/docs/target-dev/developer/server-side/on-device-decisioning/overview.html?lang=pt-BR): exibir atividades que usam a decisão do lado do servidor.</li><li>[Lado do cliente](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/on-device-decisioning/on-device-decisioning.html?lang=pt-BR): exibir atividades que usam decisões do lado do cliente.</li></ul> |
| [!UICONTROL Activity Source] | Filtre pela fonte de atividade usada para criar cada atividade.<ul><li>[!DNL Adobe Target]</li><li>[[!DNL Adobe Target] API](https://experienceleague.adobe.com/docs/target-dev/developer/overview.html?lang=pt-BR)</li><li>[[!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/docs/experience-platform.html?lang=pt-BR)</li><li>[[!DNL Adobe Experience Manager]](https://experienceleague.adobe.com/docs/experience-manager-cloud-service.html?lang=pt-BR)</li><li>[[!DNL Adobe Mobile Services]](https://developer.adobe.com/client-sdks/home/)</li></ul> |
| [!UICONTROL Property] | Filtrar pela [propriedade](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) na qual a atividade foi criada. |

## Executar ações rápidas {#quick-actions}

Clique no ícone **[!UICONTROL More actions]** ( ![Mais menu de ações](/help/main/assets/icons/MoreVertical.svg) ) ao lado de cada nome de atividade para abrir um menu que permite executar ações rápidas em uma atividade.

As seguintes ações estão disponíveis (dependendo das suas permissões e do status da atividade):

| Ação | Descrição |
| --- | --- |
| [!UICONTROL Edit] | Alterar a atividade. Qualquer atividade pode ser editada.<P>Para obter mais informações sobre as várias maneiras de editar atividades, consulte [Editar uma atividade ou salvar como rascunho](/help/main/c-activities/edit-activity.md). |
| [!UICONTROL Deactivate] | Interrompe uma atividade ao vido ou programada. Uma atividade desativada pode ser reativada ou arquivada.<P>Se você desativar ou arquivar uma atividade e depois mais tarde reativá-la, um visitante continuará sendo parte daquela atividade após a reativação se estiver nela antes que seja desativada ou arquivada. Qualquer métrica de conversão registrada durante o tempo entre os dois eventos não será atribuída àquela atividade. |
| [!UICONTROL Activate] | Inicie uma atividade inativa ou uma atividade que esteja pronta para ser ativada. |
| [!UICONTROL Archive] | Envie a atividade para o arquivo. Por padrão, as atividades arquivadas não aparecem mais na lista [!UICONTROL Activities]. Altere o filtro da lista [!UICONTROL Activities] para incluir atividades arquivadas para vê-las. Você pode ativar uma atividade arquivada para usá-la novamente.<P>Se você desativar ou arquivar uma atividade e depois mais tarde reativá-la, um visitante continuará sendo parte daquela atividade após a reativação se estiver nessa atividade antes que ela seja desativada ou arquivada. Qualquer métrica de conversão registrada durante o tempo entre os dois eventos não será atribuída àquela atividade. |
| [!UICONTROL Copy] | Copia uma atividade. Qualquer atividade pode ser copiada. A cópia de uma atividade cria uma nova atividade com o mesmo nome, com o termo &quot;Cópia&quot; anexado. Por exemplo, um teste chamado &quot;Ofertas do navegador&quot; é copiada para &quot;Cópia de ofertas do navegador&quot;.<P>Ofertas visuais são copiadas com a atividade. As ofertas podem ser editas em segurança na cópia sem afetar a atividade original. As únicas exceções são ofertas e imagens salvas na pasta Conteúdo/Ativos. |
| [!UICONTROL Delete] | Exclui um rascunho ou atividade.<P>**OBSERVAÇÃO**: as atividades excluídas não podem ser recuperadas. A menos que você tenha certeza de que nunca precisará dessa atividade novamente, use a ação [!UICONTROL Archive]. Se necessário, é possível reativar a atividade. |

## Considerações

Observe os seguintes detalhes sobre a lista [!UICONTROL Activity]:

* As atividades [!UICONTROL Archived] e [!UICONTROL Ended] não aparecem na lista [!UICONTROL Activities]. Para exibir essas atividades, filtre-as usando o [ícone de Filtros](#filters) ( ![ícone Mostrar filtros](/help/main/assets/icons/Filter.svg) ) na parte superior da lista.
* Quando uma atividade originalmente criada em [!DNL Target Classic] é desativada ou excluída, ela é excluída de [!DNL Target Standard/Premium]. Atividades excluídas criadas originalmente em [!DNL Target Classic] não são enviadas para a pasta [!UICONTROL Archive] em [!DNL Target Standard/Premium]. A funcionalidade de pasta arquivada se aplica somente a atividades criadas no [!DNL Target Standard/Premium].
* Todos os tipos de atividades diferentes de [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] oferecem a opção de usar [!DNL Target] ou [!DNL Adobe Analytics] como fonte de dados. [!UICONTROL Automated Personalization], [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] *sempre* usam os dados [!DNL Target].
* As atividades estão disponíveis para vários canais:

   * Sites da Web e de dispositivos móveis
   * Telas e dispositivos conectados à Internet, incluindo quiosques e caixas eletrônicos
   * Email e outros canais de aquisição ou sites parceiros
   * Aplicativos móveis
   * Em qualquer outro lugar você pode entregar conteúdo marcado

## Limitações {#section_049D4684403A4E07B998067EB8E9BE56}

Cada atividade do [!DNL Target] tem as seguintes limitações de conteúdo:

| Item | Limite |
|--- |--- |
| Seletores únicos | 300 se um seletor se repete em uma experiência diferente, ele é contado uma vez. No entanto, se ele se repete na mesma experiência, ele é contado novamente. |
| Ofertas em cada experiência | 350 |
| Seletores de rastreamento de cliques nas métricas | 50 |
| Mboxes nas métricas | 50 |
| Públicos-alvo e localizações | 50 combinações de públicos-alvo e localizações (mbox) não devem ser maiores que 50. |

A atividade não pode ser salva se exceder qualquer um desses limites.

O aumento do número desses itens na sua atividade também aumenta o tempo necessário para sincronizar a atividade em [!DNL Target].

Para obter limites adicionais do [!UICONTROL Visual Experience Composer] (VEC), consulte [Limitações do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/experience-composer-best-practices.md#section_F33C2EA27F2E417AA036BC199DD6C721).

## Atributos importados para [!DNL Target] de atividades atualizadas fora de [!DNL Target] {#section_802B0D174E6A44E1A96F404CA81AAE44}

Se atividades criadas em [!DNL Target] forem atualizadas de fora de [!DNL Target] (por exemplo, via API), os seguintes atributos de atividade serão importados novamente para [!DNL Target]: `thirdpartyId`, `startDate`, `endDate`, `status`, `priority` e `marketingCloudMetadata(remoteModifiedBy)`.

Este trabalho de importação é executado quando a lista [!UICONTROL Activities] é aberta, com um atraso máximo de dez minutos.

