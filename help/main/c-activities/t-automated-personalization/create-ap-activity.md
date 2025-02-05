---
keywords: personalização automatizada;ap
description: Saiba como criar uma atividade de [!UICONTROL Automated Personalization] (AP) usando o [!UICONTROL Visual Experience Composer].
title: Como criar uma atividade [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '1844'
ht-degree: 23%

---

# Criar uma atividade [!UICONTROL Automated Personalization]

Crie uma atividade [!UICONTROL Automated Personalization] (AP) em [!DNL Adobe Target] usando o [!UICONTROL Visual Experience Composer] (VEC).

O fluxo de trabalho da atividade de [!UICONTROL Automated Personalization] (AP) em [!DNL Target] varia do fluxo de trabalho dos outros tipos de atividade.

1. Na lista [!DNL Target] [!UICONTROL Activities], clique em **[!UICONTROL Create Activity]** > **[!UICONTROL Automated Personalization]**.

1. Para usar o [!UICONTROL Visual Experience Composer] (VEC), clique em **[!UICONTROL Visual]**.

   Para usar o [!UICONTROL Form-Based Experience Composer], selecione [!UICONTROL Form]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Form-Based Experience Composer], o [!DNL Target] oferece o [!UICONTROL Single Page Application VEC]. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) [Escolha um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Na caixa **[!UICONTROL Enter Activity URL]**, especifique sua [URL de atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Se sua conta foi [configurada com um URL padrão](/help/main/administrating-target/visual-experience-composer-set-up.md), esse URL aparece por padrão. Você pode alterar o URL padrão para outro, se necessário.

   [!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://wwww.adobe.com`] são correspondentes.

1. Clique em **[!UICONTROL Create]**.

   A página com o URL especificado é aberta no VEC.

1. Clique no ícone **[!UICONTROL Rename]** ( ![Ícone Renomear](/help/main/assets/icons/MoreSmallListVert.svg) ), clique em **[!UICONTROL Rename]**, especifique um nome para a atividade e clique em **[!UICONTROL Save]**.

   O nome da atividade não pode começar com nenhum dos seguintes caracteres:

   | Caractere | Descrição |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

   O nome da atividade não pode conter nenhuma das sequências de caracteres a seguir:

   | Sequência de caracteres | Descrição |
   |--- |--- |
   | ;= | Ponto e vírgula, Igual a |
   | ;+ | Ponto-e-vírgula, Mais |
   | ;- | Ponto e vírgula, sinal de subtração |
   | ;@ | Ponto e vírgula, no sinal |
   | ,= | Vírgula, Igual a |
   | ,+ | Vírgula, Mais |
   | - | Vírgula, menos |
   | ,@ | Vírgula, No sinal |
   | `[`&quot; | Colchete de abertura, aspas duplas |
   | &quot;`]` | Aspas duplas, colchete de fechamento |

1. Modifique os elementos da página conforme explicado nas [opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Você pode selecionar várias imagens de uma vez no gerenciador de ativos. Isso permite visualizar rapidamente a página com cada uma das imagens configuradas para a atividade. Você também pode editar facilmente os elementos de texto em suas ofertas. Quando você edita um elemento, barras aparecem nele para indicar que foi alterado.

1. Clique no ícone **[!UICONTROL Manage Content]** ( ![Ícone Gerenciar conteúdo](/help/main/assets/icons/Experience.svg) ) para configurar as combinações disponíveis.

   Uma caixa de diálogo é exibida com duas opções na parte superior da tela: [!UICONTROL Experiences] e [!UICONTROL Offers].

   >[!NOTE]
   >
   >Embora você possa criar até 30.000 experiências em uma atividade AP, a atividade funciona melhor quando menos de 5.000 experiências são usadas. Esse mesmo limite é aplicado mesmo quando a atividade tiver habilitado a opção [!UICONTROL Disalow Duplicates].

   A lista [!UICONTROL Experiences] mostra cada parte do conteúdo selecionado para a atividade e o local ao qual está atribuído.

   Você pode excluir experiências específicas marcando a caixa de seleção ao lado da experiência desejada e clicando no ícone [!UICONTROL Exclude].

   Você pode excluir ou incluir em lote as experiências marcando a caixa de seleção das experiências relevantes e, em seguida, clicando no ícone [!UICONTROL Exclude].

1. (Condicional) Clique em **[!UICONTROL Offers]** para selecionar partes do conteúdo e as atribuir a grupos de relatórios ou somente permitir que alguns visitantes vejam determinadas ofertas com o direcionamento.

   Para obter mais informações sobre grupos de relatórios, consulte [Oferecer grupos de relatórios no Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the [!UICONTROL Disalow Duplicates] option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.-->

1. Clique em **[!UICONTROL Done]** quando terminar de configurar o conteúdo da sua atividade.

1. Clique em **[!UICONTROL Targeting]** na parte superior de [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado em três etapas.

   A etapa **Direcionamento** lhe parece familiar se você já tiver usado outros tipos de atividades [!DNL Target]. Aqui, é possível selecionar um público-alvo e especificar a porcentagem de visitantes que visualizarão cada experiência.

   O diagrama do fluxo é aberto.

   ![Etapa de teste de direcionamento de AP](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

   O diagrama do fluxo guia você pelas etapas da atribuição de um público-alvo e sua porcentagem de tráfego, selecionando o método de alocação de tráfego e especificando a alocação de tráfego para cada experiência na atividade.

1. (Condicional) Clique no controle **[!UICONTROL All Visitors]** para selecionar outro público-alvo para a atividade.

   O público-alvo [!UICONTROL All Visitors] está definido como padrão. Se você selecionar outro público-alvo, o nome dele será exibido no controle mais à esquerda.

   O quadro direito é exibido, permitindo adicionar ou excluir um público-alvo e atribuir a porcentagem de visitante à atividade.

   1. Para alterar o público-alvo, clique no ícone **[!UICONTROL Replace]** ( ![Ícone Substituir](/help/main/assets/icons/Retweet.svg) ) no quadro direito.
   1. Na caixa de diálogo [!UICONTROL Add Audience], [selecione o público desejado](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) e clique em **[!UICONTROL Assign Audience]**.

      Você pode clicar em **Combinar Públicos-alvo** para [criar um público-alvo que combine vários públicos-alvo](/help/main/c-target/combining-multiple-audiences.md).

      Se você precisar criar um novo público-alvo que ainda não esteja no [!UICONTROL Audience Library], clique em **Criar público-alvo**. Durante o [fluxo de trabalho de criação de público-alvo](/help/main/c-target/c-audiences/audiences.md), você pode escolher entre as seguintes opções:

      * **[!UICONTROL Audience Library]**: Crie um público-alvo sob demanda que seja salvo no [!UICONTROL Audience Library] e que possa ser reutilizado em outras atividades.
      * **[!UICONTROL This activity only]**: Crie um [público-alvo específico da atividade](/help/main/c-target/creating-activity-only-audience.md) que não seja salvo no [!UICONTROL Audience Library] e possa ser usado somente na atividade atual.

   1. Clique em **[!UICONTROL Visitor Percentage]** no quadro direito e escolha a porcentagem de visitantes qualificados que você deseja inserir na atividade.

   Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Clique no controle **[!UICONTROL Traffic Allocation]** para escolher entre as seguintes opções:

   ![Opções da Meta de alocação de tráfego](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   * **[!UICONTROL Evaluate Personalization Algorithm (50/50)]:** Se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o controle e o algoritmo de destino. Esta divisão fornece a estimativa mais precisa do aumento. Recomenda-se usar com &quot;experiências aleatórias&quot; como controle.
   * **[!UICONTROL Maximizing Personalization Traffic (90/10)]:** Se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle. Essa opção garante que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. A desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você tem menos precisão em saber qual é o aumento exato. Independentemente da meta, essa opção é a divisão de tráfego recomendada ao usar uma experiência específica como controle.
   * **[!UICONTROL Custom Allocation]:** Divida manualmente a porcentagem conforme desejado.

1. (Condicional) Na lista suspensa [!UICONTROL Control], [selecione uma experiência específica para ser usada como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou selecione [!UICONTROL Random Experience.]

   A experiência de controle fornece uma comparação para determinar a quantidade de elevação proporcionada pelo teste automatizado.

   [!UICONTROL Automated Personalization] sempre mede o desempenho contra um grupo de controle. A prática recomendada é colocar, pelo menos, 10% dos participantes no grupo de controle. Se o objetivo for testar se o algoritmo de personalização nos dados fornecidos tem melhor desempenho do que nenhuma personalização (por exemplo, o controle disponibilizado aleatoriamente), uma divisão de tráfego de 50/50% entre o controle e o algoritmo de personalização é a maneira mais rápida e precisa de atingir essa meta. Se você quiser maximizar a quantidade de tráfego que é personalizado e estiver menos preocupado em entender o aumento exato que sua atividade está gerando, uma divisão de tráfego de 10/90% entre o controle e o algoritmo de personalização é a maneira mais rápida e precisa de atingir essa meta.

   >[!NOTE]
   >
   >Em [!UICONTROL Automated Personalization] atividades, os critérios de entrada (definição de metas de URL, regras de modelo e metas de público-alvo) são avaliados para cada solicitação. Nas versões anteriores, os critérios de entrada eram avaliados uma vez por sessão.

1. Clique em **[!UICONTROL Next]** para exibir a página **[!UICONTROL Goals & Settings]**.
1. Defina a atividade com as seguintes configurações e clique em **[!UICONTROL Save & Close]**.

   | Configuração | Descrição |
   |--- |--- |
   | [!UICONTROL Name] | Nomeie a atividade. Nomeie a atividade de forma descritiva o suficiente para que os membros da equipe possam reconhecê-la na lista [!UICONTROL Activities]. Consulte a tabela acima para ver quais caracteres não são permitidos em um nome de atividade. |
   | [!UICONTROL Objective] | (Opcional) Digite o objetivo do teste. O objetivo ajuda a lembrar o propósito da atividade. |
   | [!UICONTROL Priority] | Dependendo das configurações, a interface do usuário do [!DNL Target] e as opções para [!UICONTROL Priority] variam. Você pode usar as configurações herdadas de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou pode habilitar prioridades otimizadas de 0 a 999.<P>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<P>Se esta opção não estiver habilitada em [!UICONTROL Administration] > [!UICONTROL Reporting] (padrão), especifique uma prioridade: [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High].<P>Para habilitar prioridades otimizadas, clique em [!UICONTROL Administration] > [!UICONTROL Reporting] e alterne a opção [!UICONTROL Enable Fine-Grained Priorities] para a posição &quot;Ativado&quot;.<P>Se esta opção estiver ativada, especifique um valor de 0 a 999:<ul><li>0 = Baixo</li><li>999 = Alto</li></ul>Para atividades criadas em versões anteriores do [!DNL Target Standard/Premium], a prioridade [!UICONTROL Low] é convertida para 0, a prioridade [!UICONTROL Medium] é convertida para 5 e a prioridade [!UICONTROL High] é convertida para 10. É possível ajustar esses valores conforme necessário.<P>**Observação**: antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10. |
   | [!UICONTROL Duration] | Defina as datas de início e término da atividade. Você pode selecionar [!UICONTROL When Activated] ou especificar uma data e hora específicas. |
   | [!UICONTROL Optimization Goal] | Especifique a meta de otimização, que consiste em dois parâmetros:<ul><li>O que você deseja medir com a atividade</li><li>A ação tomada por um participante da atividade que mostra que a meta foi alcançada.</li></ul>Você pode optar por nomear a meta de otimização selecionando os três pontos à direita de [!UICONTROL My Primary Goal]. [!UICONTROL Automated Personalization] atividades podem medir [!UICONTROL Conversion] ou [!UICONTROL Revenue]. A conversão pode ser obtida ao visualizar uma página ou ao visualizar uma mbox. Os cliques também podem ser monitorados.<P>A meta primária torna-se também a métrica de modelagem usada pelo sistema de modelagem para calcular o sucesso da experiência.<P>Os visitantes podem ser mantidos na atividade para fins de rastreamento depois de atingir a meta de modelagem. Por exemplo, uma atividade [!UICONTROL Automated Personalization] é frequentemente usada para melhorar taxas de clique, e isso é definido como a meta de modelagem. No entanto, é importante ver como as maiores taxas de clique levam à conversão final, então o rastreamento pela conversão final é essencial.<P>É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada.<P>Você deve definir ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra.<P>A opção [!UICONTROL Add Dependency] permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada.<P>Para adicionar uma dependência:<ol><li>Depois de adicionar outras métricas, clique em **[!UICONTROL Advanced Settings]** no menu de três pontos à direita de [!UICONTROL Additional Goal].</li><li>Clique na opção **[!UICONTROL Add Dependency]** na parte inferior da seção [!UICONTROL Reporting Settings].</li><li>Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em [!UICONTROL Reached] para alternar a configuração entre [!UICONTROL Reached] e [!UICONTROL Not Reached].</li></ol>É possível editar ou remover dependências depois de adicioná-las. |
   | [!UICONTROL Conversion Metric] | Por padrão, a métrica de conversão é igual à métrica de meta de otimização. No entanto, é possível definir uma métrica de conversão separada ao desmarcar a opção [!UICONTROL Same as Optimization Goal]. |
   | [!UICONTROL Additional Metrics] | Adicione outras métricas de relatório que deseja usar. É possível adicionar métricas de conversão ou receita.<P>**Observação**: a métrica [!UICONTROL Engagement] não tem suporte como uma métrica adicional. A interface do usuário do [!DNL Target] pode permitir a seleção da métrica [!UICONTROL Engagement], mas os dados não são exibidos com precisão nos relatórios. |
   | [!UICONTROL Audiences for Reporting] | Adicione públicos-alvo para permitir a filtragem por público-alvo nos relatórios. Por padrão, o relatório mostra os resultados para todos os visitantes qualificados. Adicione públicos para filtrar os resultados de subconjuntos de visitantes mais específicos.<P>**Observação**: diferentemente de outros tipos de atividades, [!UICONTROL Automated Personalization] não pode usar [!UICONTROL Adobe Analytics] como sua fonte de relatórios (A4T). |
   | [!UICONTROL Notes] | Digite quaisquer informações sobre sua atividade que sejam úteis para você ou para outros membros da equipe. O painel [!UICONTROL Notes] é redimensionável. |

   Ao nomear ou renomear uma métrica, os seguintes caracteres não são permitidos:

   | Caractere | Descrição |
   |--- |--- |
   | / | Barra |
   | ? | Ponto de interrogação |
   | # | Sinal numérico |
   | : | Dois-pontos |
   | = | Igual a |
   | + | Plus |
   | - | Menos |
   | @ | Sinal de arroba |

Depois de clicar em **[!UICONTROL Save & Close]**, a página [!UICONTROL Overview] da atividade é exibida. Clique em **Visualizar experiências** para visualizar como serão suas experiências quando entregues. Um pop-up é exibido e pode ser usado para exibir e compartilhar links das suas experiências de AP no site, para obter uma &quot;visualização verdadeira&quot; das experiências fora do [!UICONTROL Target] [!UICONTROL Visual Experience Composer] (VEC). É necessário compartilhar os links da mensagem para compartilhar a visualização. Clicar em um link e, em seguida, copiar o URL diretamente do navegador não funciona. Copiar o link faz com que o URL contenha um parâmetro que exibe a página corretamente somente quando você acessa a página do link na mensagem.

Para obter informações sobre relatórios, consulte [Relatórios do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
