---
keywords: personalização automatizada;ap
description: Saiba como criar uma atividade do [!UICONTROL Automated Personalization] (AP) no [!DNL Adobe Target] usando o [!UICONTROL Visual Experience Composer].
title: Como criar uma atividade do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: c467f629596b37c334276d6f095f19b639a8518d
workflow-type: tm+mt
source-wordcount: '1927'
ht-degree: 30%

---

# Criar uma atividade do [!UICONTROL Automated Personalization]

Crie uma atividade do [!UICONTROL Automated Personalization] (AP) em [!DNL Adobe Target] usando o [!UICONTROL Visual Experience Composer] (VEC).

O fluxo de trabalho da atividade [!UICONTROL Automated Personalization] (AP) em [!DNL Target] varia do fluxo de trabalho dos outros tipos de atividade.

1. Na lista [!DNL Target] [!UICONTROL Atividades], clique em **[!UICONTROL Criar Atividade]** > **[!UICONTROL Automated Personalization]**.

   ![Criar atividade: Personalização automatizada](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. Para usar o [!UICONTROL Visual Experience Composer] (VEC), clique em **[!UICONTROL Visual]**.

   Para usar o [!UICONTROL Experience Composer baseado em formulário], selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Experience Composer baseado em formulário], o [!DNL Target] oferece o [!UICONTROL VEC para aplicativos de página única]. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) [Escolha um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Verifique ou insira a URL da atividade e clique em **[!UICONTROL Criar]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://wwww.adobe.com`] são correspondentes.

   A página com o URL especificado é aberta no VEC.

1. Clique no campo **[!UICONTROL Nome]** e digite o nome da atividade.

   ![Campo nome](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

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

1. Clique em **[!UICONTROL Gerenciar Conteúdo]** para configurar as combinações disponíveis.

   ![Opção Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Uma caixa de diálogo é exibida com três opções na parte superior da tela: [!UICONTROL Experiências], [!UICONTROL Ofertas] e [!UICONTROL Grupos de Exclusão].

   ![Caixa de diálogo Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Embora você possa criar até 30.000 experiências em uma atividade AP, a atividade funciona melhor quando menos de 5.000 experiências são usadas. Esse mesmo limite é aplicado mesmo quando a atividade tiver habilitado a opção [!UICONTROL Não permitir duplicatas].

   A lista [!UICONTROL Experiências] mostra cada parte do conteúdo selecionado para a atividade e o local onde está atribuído.

   Você pode excluir experiências específicas ao passar o mouse sobre a experiência desejada e clicar no ícone [!UICONTROL Excluir].

   ![Cursor do mouse sobre o ícone Excluir](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Você pode excluir ou incluir em lote as experiências marcando a caixa de seleção das experiências relevantes e, em seguida, clicando no ícone [!UICONTROL Excluir] no canto superior direito da caixa de diálogo.

   ![Opções de exclusão em lote](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   É possível filtrar essa exibição de lista para ver apenas as atividades excluídas ou incluídas, clicando na lista suspensa [!UICONTROL Status].

1. (Condicional) Clique em **[!UICONTROL Ofertas]** para selecionar partes do conteúdo e as atribuir a grupos de relatórios ou somente permitir que alguns visitantes vejam determinadas ofertas com o direcionamento.

   Para obter mais informações sobre grupos de relatórios, consulte [Oferecer grupos de relatórios no Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. (Condicional) Clique em **[!UICONTROL Grupos de exclusão]** para escolher qualquer combinação de elementos que você deseja excluir da atividade.

   ![Guia Grupos de exclusão da caixa de diálogo Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Embora seja possível criar até 30.000 experiências em um teste de AP, o algoritmo tem melhor desempenho quando são usadas menos de 10.000 experiências distintas. Esse mesmo limite é aplicado mesmo quando a atividade tiver habilitado a opção [!UICONTROL Não permitir duplicatas].

   Se, atualmente, você não tem grupos de exclusão incluídos na atividade, clique em **Criar grupo de exclusão**. É possível filtrar para criar uma lista que mostre apenas as combinações que deseja excluir. Nomeie o grupo de exclusão e clique em **Salvar**.

   Para editar um grupo de exclusão existente, passe o mouse sobre o grupo que deseja editar e clique no ícone de lápis.

1. Clique em **[!UICONTROL Concluído]** quando terminar de configurar o conteúdo de sua atividade.

1. A etapa **Direcionamento** lhe parece familiar se você já tiver usado outros tipos de atividades [!DNL Target]. Aqui, é possível selecionar um público-alvo e especificar a porcentagem de visitantes que verão a experiência de controle clicando na lista suspensa **[!UICONTROL Alocação personalizada]** e em **Avançar**.

   A lista suspensa [!UICONTROL Alocação personalizada] permite escolher as seguintes opções:

   ![Lista suspensa Meta de alocação de tráfego](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Avaliar o Algoritmo Personalization (50/50)]:** Se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o controle e o algoritmo de destino. Esta divisão fornece a estimativa mais precisa do aumento. Recomenda-se usar com &quot;experiências aleatórias&quot; como controle.
   * **[!UICONTROL Maximizar o tráfego do Personalization (90/10)]:** Se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle. Essa opção garante que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. A desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você tem menos precisão em saber qual é o aumento exato. Independentemente da meta, essa opção é a divisão de tráfego recomendada ao usar uma experiência específica como controle.
   * **[!UICONTROL Alocação personalizada]:** divida manualmente a porcentagem conforme desejado.

1. (Condicional) Na lista suspensa [!UICONTROL Controle], [selecione uma experiência específica a ser usada como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou selecione [!UICONTROL Experiência Aleatória.]

   A experiência de controle fornece uma comparação para determinar a quantidade de elevação proporcionada pelo teste automatizado.

   O [!UICONTROL Automated Personalization] sempre mede o desempenho em relação a um grupo de controle. A prática recomendada é colocar, pelo menos, 10% dos participantes no grupo de controle. Se o objetivo for testar se o algoritmo de personalização nos dados fornecidos tem melhor desempenho do que nenhuma personalização (por exemplo, o controle disponibilizado aleatoriamente), uma divisão de tráfego de 50/50% entre o controle e o algoritmo de personalização é a maneira mais rápida e precisa de atingir essa meta. Se você quiser maximizar a quantidade de tráfego que é personalizado e estiver menos preocupado em entender o aumento exato que sua atividade está gerando, uma divisão de tráfego de 10/90% entre o controle e o algoritmo de personalização é a maneira mais rápida e precisa de atingir essa meta.

   >[!NOTE]
   >
   >Em atividades do [!UICONTROL Automated Personalization], os critérios de entrada (direcionamento por URL, regras de modelo e público-alvo) são avaliados para cada solicitação. Nas versões anteriores, os critérios de entrada eram avaliados uma vez por sessão.

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
