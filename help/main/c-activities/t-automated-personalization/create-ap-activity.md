---
keywords: personalização automatizada;ap
description: Saiba como criar uma atividade do [!UICONTROL Automated Personalization] (AP) usando o [!UICONTROL Visual Experience Composer].
title: Como criar uma atividade do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
TQID: https://experienceleague.adobe.com/5eUFwob4BekIJP4SM2lrSDQam4h1AXIByJjM7-1RNL8
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: c467f629596b37c334276d6f095f19b639a8518d
workflow-type: tm+mt
source-wordcount: 2032
ht-degree: 23%

---

# Criar uma atividade do [!UICONTROL Automated Personalization]

Crie uma atividade do [!UICONTROL Automated Personalization] (AP) em [!DNL Adobe Target] usando o [!UICONTROL Visual Experience Composer] (VEC).

O fluxo de trabalho da atividade [!UICONTROL Automated Personalization] (AP) em [!DNL Target] varia do fluxo de trabalho dos outros tipos de atividade.

Este procedimento segue o fluxo de trabalho guiado de três etapas no [!UICONTROL Visual Experience Composer]:

1. [Etapa 1: criar experiências](#build-experiences)
1. [Etapa 2: definir o direcionamento](#set-targeting)
1. [Etapa 3: definir metas e configurações](#configure-goals-and-settings)

## Etapa 1: criar experiências {#build-experiences}

Defina o pool de variações de conteúdo que o [!UICONTROL Automated Personalization] pode personalizar. Quanto mais ricas e distintas forem suas experiências e ofertas, melhor o algoritmo poderá corresponder ao conteúdo correto para cada visitante.

1. Na lista [!DNL Target] [!UICONTROL Atividades], clique em **[!UICONTROL Criar Atividade]** > **[!UICONTROL Automated Personalization]**.

1. Para usar o [!UICONTROL Visual Experience Composer] (VEC), clique em **[!UICONTROL Visual]**.

   Para usar o [!UICONTROL Experience Composer baseado em formulário], selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Experience Composer baseado em formulário], o [!DNL Target] oferece o [!UICONTROL VEC para aplicativos de página única]. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) [Escolha um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Na caixa **[!UICONTROL Inserir URL da atividade]**, especifique sua [URL da atividade](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-activity-url.md).

   Se sua conta foi [configurada com um URL padrão](/help/main/administrating-target/visual-experience-composer-set-up.md), esse URL aparece por padrão. Você pode alterar o URL padrão para outro, se necessário.

   [!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://wwww.adobe.com`] são correspondentes.

1. Clique em **[!UICONTROL Criar]**.

   A página com o URL especificado é aberta no VEC.

1. Para nomear a atividade, clique no ícone **[!UICONTROL Editar]** ( ![Ícone Editar](/help/main/assets/icons/Edit.svg) ) ao lado de &quot;[!UICONTROL Atividade sem título]&quot;, especifique um nome descritivo para a atividade e clique em **[!UICONTROL Salvar]**.

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
   | ,- | Vírgula, menos |
   | ,@ | Vírgula, No sinal |
   | `[`&quot; | Colchete de abertura, aspas duplas |
   | &quot;`]` | Aspas duplas, colchete de fechamento |

1. Modifique os elementos da página conforme explicado nas [opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Você pode selecionar várias imagens de uma vez no gerenciador de ativos. Isso permite visualizar rapidamente a página com cada uma das imagens configuradas para a atividade. Você também pode editar facilmente os elementos de texto em suas ofertas. Quando você edita um elemento, barras aparecem nele para indicar que foi alterado.

1. Clique no ícone **[!UICONTROL Gerenciar Conteúdo]** ( ![Ícone Gerenciar Conteúdo](/help/main/assets/icons/Experience.svg) ) para configurar as combinações disponíveis.

   Uma caixa de diálogo é exibida com duas guias: [!UICONTROL Experiências] e [!UICONTROL Ofertas]. A guia [!UICONTROL Experiências] lista cada parte do conteúdo e o local onde está atribuído. Para excluir uma ou mais experiências, marque as caixas de seleção correspondentes e clique no ícone [!UICONTROL Excluir]. Para obter mais opções, consulte [Gerenciando exclusões](/help/main/c-activities/t-automated-personalization/managing-exclusions.md).

   >[!IMPORTANT]
   >
   >Para um desempenho ideal, limite as atividades do [!UICONTROL Automated Personalization] e do [!UICONTROL Direcionamento automático] para 4 a 6 locais com 4 a 6 ofertas por local. O número total de experiências cresce com a combinação cartesiana de locais e ofertas. Configurações maiores podem resultar em carregamento ou edição lento no [!UICONTROL Visual Experience Composer]. Mantenha o total abaixo de 5.000 experiências para obter melhores resultados; o limite rígido é 30.000 (o mesmo limite se aplica quando a opção [!UICONTROL Não permitir duplicatas] está habilitada).

1. (Condicional) Clique em **[!UICONTROL Ofertas]** para selecionar partes do conteúdo e as atribuir a grupos de relatórios ou somente permitir que alguns visitantes vejam determinadas ofertas com o direcionamento.

   Para obter mais informações sobre grupos de relatórios, consulte [Oferecer grupos de relatórios no Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

<!--
1. (Conditional) Click **[!UICONTROL Exclusion Groups]** to choose any combination of elements that you want to exclude from the activity.

   ![Exclusion Groups tab of Manage Content dialog box](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Although you can create up to 30,000 experiences in an AP test, the algorithm performs its best when fewer than 10,000 distinct experiences are used. This same limit is applied even when the activity has enabled the [!UICONTROL Disallow Duplicates] option.

   If you do not currently have any exclusion groups included in your activity, click **Create Exclusion Group**. You can filter to create a list that shows only the combinations you want to exclude. Name your exclusion group, then click **Save**.

   To edit an existing exclusion group, hover over the group you want to edit, then click the pencil icon.
-->

1. Clique em **[!UICONTROL Concluído]** quando terminar de configurar o conteúdo de sua atividade.

## Etapa 2: definir o direcionamento {#set-targeting}

Decida quais visitantes entram na atividade e quanto do seu tráfego é exposto. Emparelhe-os com um grupo de controle para que [!DNL Target] possa medir o aumento que a personalização oferece.

1. Clique em **[!UICONTROL Direcionamento]** na parte superior do [!UICONTROL Visual Experience Composer] para ir até a próxima etapa do fluxo de trabalho guiado de três etapas.

   A etapa **Direcionamento** lhe parece familiar se você já tiver usado outros tipos de atividades [!DNL Target]. Aqui, é possível selecionar um público-alvo e especificar a porcentagem de visitantes que visualizarão cada experiência.

1. O diagrama do fluxo guia você pelas etapas da atribuição de um público-alvo e sua porcentagem de tráfego, selecionando o método de alocação de tráfego e especificando a alocação de tráfego para cada experiência na atividade.

   ![Etapa de teste de direcionamento de AP](/help/main/c-activities/t-automated-personalization/assets/ap-traffic-flow.png)

1. (Condicional) Clique no controle **[!UICONTROL Todos os visitantes]** para [selecionar outro público-alvo](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-audience.md) para a atividade e definir sua porcentagem de visitantes.

   O público-alvo [!UICONTROL Todos os visitantes] está definido como padrão. Se você selecionar outro público, o nome dele será exibido no controle mais à esquerda. Por exemplo, você pode limitar as entradas a 50% de todos os visitantes ou 45% do público-alvo na Califórnia.

1. Clique no controle **[!UICONTROL Alocação de tráfego]** para escolher entre as seguintes opções:

   ![Opções da Meta de alocação de tráfego](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap-new.png)

   * **[!UICONTROL Avaliar o Algoritmo Personalization (50/50)]:** Se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o controle e o algoritmo de destino. Esta divisão fornece a estimativa mais precisa do aumento. Recomenda-se usar com &quot;experiências aleatórias&quot; como controle.
   * **[!UICONTROL Maximizar o tráfego do Personalization (90/10)]:** Se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle. Essa opção garante que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. A desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você tem menos precisão em saber qual é o aumento exato. Independentemente da meta, essa opção é a divisão de tráfego recomendada ao usar uma experiência específica como controle.
   * **[!UICONTROL Alocação personalizada]:** divida manualmente a porcentagem conforme desejado.

1. (Condicional) Na lista suspensa [!UICONTROL Controle], [selecione uma experiência específica a ser usada como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou selecione [!UICONTROL Experiência Aleatória.]

   A experiência de controle fornece uma comparação para determinar a quantidade de elevação proporcionada pelo teste automatizado.

   O [!UICONTROL Automated Personalization] sempre mede o desempenho em relação a um grupo de controle. A prática recomendada é colocar, pelo menos, 10% dos participantes no grupo de controle. Se o objetivo for testar se o algoritmo de personalização nos dados fornecidos tem melhor desempenho do que nenhuma personalização (por exemplo, o controle disponibilizado aleatoriamente), uma divisão de tráfego de 50/50% entre o controle e o algoritmo de personalização é a maneira mais rápida e precisa de atingir essa meta. Se você quiser maximizar a quantidade de tráfego que é personalizado e estiver menos preocupado em entender o aumento exato que sua atividade está gerando, uma divisão de tráfego de 10/90% entre o controle e o algoritmo de personalização é a maneira mais rápida e precisa de atingir essa meta.

   >[!NOTE]
   >
   >Em atividades do [!UICONTROL Automated Personalization], os critérios de entrada (direcionamento por URL, regras de modelo e público-alvo) são avaliados para cada solicitação. Nas versões anteriores, os critérios de entrada eram avaliados uma vez por sessão.

## Etapa 3: definir metas e configurações {#configure-goals-and-settings}

Conte a [!DNL Target] como é o sucesso. A meta de otimização escolhida é a métrica para a qual o algoritmo de personalização é treinado, portanto, escolha o resultado mais importante para essa atividade.

1. Clique em **[!UICONTROL Avançar]** para exibir a página **[!UICONTROL Metas e Configurações]**.
1. Configure a atividade com as seguintes configurações e clique em **[!UICONTROL Salvar e fechar]**.

   | Configuração | Descrição |
   |--- |--- |
   | [!UICONTROL Nome] | Nomeie a atividade. Nomeie a atividade de forma descritiva o suficiente para que os membros da equipe possam reconhecê-la na lista [!UICONTROL Atividades]. Consulte a tabela acima para ver quais caracteres não são permitidos em um nome de atividade. |
   | [!UICONTROL Objetivo] | (Opcional) Digite o objetivo do teste. O objetivo ajuda a lembrar o propósito da atividade. |
   | [!UICONTROL Prioridade] | Dependendo das configurações, a interface do usuário do [!DNL Target] e as opções de [!UICONTROL Prioridade] variam. Você pode usar as configurações herdadas de [!UICONTROL Baixo], [!UICONTROL Medium] ou [!UICONTROL Alto], ou pode habilitar prioridades otimizadas de 0 a 999.<P>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<P>Se esta opção não estiver habilitada em [!UICONTROL Administração] > [!UICONTROL Relatórios] (padrão), especifique uma prioridade: [!UICONTROL Baixa], [!UICONTROL Medium] ou [!UICONTROL Alta].<P>Para habilitar prioridades otimizadas, clique em [!UICONTROL Administração] > [!UICONTROL Relatórios] e alterne a opção [!UICONTROL Habilitar Prioridades Otimizadas] para a posição &quot;Ativado&quot;.<P>Se esta opção estiver ativada, especifique um valor de 0 a 999:<ul><li>0 = Baixo</li><li>999 = Alto</li></ul>Para atividades criadas em versões anteriores do [!DNL Target Standard/Premium], a prioridade [!UICONTROL Baixa] é convertida para 0, a prioridade [!UICONTROL Medium] é convertida para 5 e a prioridade [!UICONTROL Alta] é convertida para 10. É possível ajustar esses valores conforme necessário.<P>**Observação**: antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10. |
   | [!UICONTROL Duração] | Defina as datas de início e fim da atividade. Você pode selecionar [!UICONTROL Quando ativado] ou especificar uma data e hora específicas. |
   | [!UICONTROL Meta de otimização] | Especifique a meta de otimização, que consiste em dois parâmetros:<ul><li>O que você deseja medir com a atividade</li><li>A ação tomada por um participante da atividade que mostra que a meta foi alcançada.</li></ul>Você pode optar por nomear a meta de otimização selecionando os três pontos à direita de [!UICONTROL Minha meta principal]. As atividades de [!UICONTROL Automated Personalization] podem medir [!UICONTROL Conversão] ou [!UICONTROL Receita]. A conversão pode ser obtida ao visualizar uma página ou ao visualizar uma mbox. Os cliques também podem ser monitorados.<P>A meta primária torna-se também a métrica de modelagem usada pelo sistema de modelagem para calcular o sucesso da experiência.<P>Os visitantes podem ser mantidos na atividade para fins de rastreamento depois de atingir a meta de modelagem. Por exemplo, uma atividade [!UICONTROL Automated Personalization] é frequentemente usada para melhorar taxas de clique, e isso é definido como a meta de modelagem. No entanto, é importante ver como as maiores taxas de clique levam à conversão final, então o rastreamento pela conversão final é essencial.<P>É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada.<P>Você deve definir ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra.<P>A opção [!UICONTROL Adicionar dependência] permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada.<P>Para adicionar uma dependência:<ol><li>Depois de adicionar outras métricas, clique em **[!UICONTROL Configurações avançadas]** no menu de três pontos à direita de [!UICONTROL Meta adicional].</li><li>Clique na opção **[!UICONTROL Adicionar dependência]** na parte inferior da seção [!UICONTROL Configurações de relatório].</li><li>Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em [!UICONTROL Alcançado] para alternar a configuração entre [!UICONTROL Alcançado] e [!UICONTROL Não alcançado].</li></ol>É possível editar ou remover dependências depois de adicioná-las. |
   | [!UICONTROL Métrica de conversão] | Por padrão, a métrica de conversão é igual à métrica de meta de otimização. No entanto, é possível definir uma métrica de conversão separada ao desmarcar a opção [!UICONTROL Igual à meta de otimização]. |
   | [!UICONTROL Métricas adicionais] | Adicione outras métricas de relatório que deseja usar. É possível adicionar métricas de conversão ou receita.<P>**Observação**: a métrica [!UICONTROL Envolvimento] não é suportada como uma métrica adicional. A interface do usuário do [!DNL Target] pode permitir a seleção da métrica [!UICONTROL Envolvimento], mas os dados não são exibidos com precisão nos relatórios. |
   | [!UICONTROL Públicos-alvo para relatórios] | Adicione públicos-alvo para permitir a filtragem por público-alvo nos relatórios. Por padrão, o relatório mostra os resultados para todos os visitantes qualificados. Adicione públicos para filtrar os resultados de subconjuntos de visitantes mais específicos.<P>**Observação**: diferentemente de outros tipos de atividades, o [!UICONTROL Automated Personalization] não pode usar o [!UICONTROL Adobe Analytics] como sua fonte de relatórios (A4T). |
   | [!UICONTROL Notas] | Digite quaisquer informações sobre sua atividade que sejam úteis para você ou para outros membros da equipe. O painel [!UICONTROL Notas] é redimensionável. |

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

Depois de clicar em **[!UICONTROL Salvar e fechar]**, a página [!UICONTROL Visão geral] da atividade é exibida. Clique em **Visualizar experiências** para visualizar como serão suas experiências quando entregues. Um pop-up é exibido e pode ser usado para exibir e compartilhar links com suas experiências de AP no site, para obter uma &quot;visualização verdadeira&quot; das experiências fora do [!UICONTROL Target] [!UICONTROL Visual Experience Composer] (VEC). É necessário compartilhar os links da mensagem para compartilhar a visualização. Clicar em um link e, em seguida, copiar o URL diretamente do navegador não funciona. Copiar o link faz com que o URL contenha um parâmetro que exibe a página corretamente somente quando você acessa a página do link na mensagem.

Para obter informações sobre relatórios, consulte [Relatórios do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md).
