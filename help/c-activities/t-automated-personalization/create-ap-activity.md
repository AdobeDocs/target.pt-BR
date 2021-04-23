---
keywords: personalização automatizada, ap, audiences, conjunto, random forest, variação residual, variação de erro, valor histórico
description: Saiba como criar uma atividade de Automated Personalization (AP) no Adobe [!DNL Target] usando o Visual Experience Composer (VEC).
title: Como criar uma atividade do Automated Personalization?
feature: Personalização automatizada
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2052'
ht-degree: 91%

---

# ![PREMIUM](/help/assets/premium.png) Criar uma atividade de personalização automatizada

O workflow da atividade [!UICONTROL Automated Personalization] (AP) em [!DNL Adobe Target] varia do workflow dos outros tipos de atividade.

1. Na lista [!DNL Target] [!UICONTROL Atividades], clique em **[!UICONTROL Criar Atividade]** > **[!UICONTROL Automated Personalization]**.

   ![Criar atividade: Personalização automatizada](/help/c-activities/t-automated-personalization/assets/ap_create-new.png)

1. Para usar o [!UICONTROL Visual Experience Composer] (VEC), clique em **[!UICONTROL Visual (Padrão)]**.

   ![Caixa de diálogo Criar atividade de Personalização automatizada](/help/c-activities/t-automated-personalization/assets/ap_url-new.png)

   Se preferir usar o [!UICONTROL Experience Composer baseado em formulário], selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Experience Composer baseado em formulário], [!DNL Target] oferece o [!UICONTROL VEC para aplicativos de página única] e o VEC para aplicativos móveis. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >A opção [!UICONTROL Escolher local de trabalho] na ilustração anterior é um recurso do [Target Premium](/help/c-intro/intro.md). Caso não veja essa opção, a licença da organização é do Target Standard.

1. (Condicional) Se você for um [!DNL Target] cliente Premium, [escolha um espaço de trabalho](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Verifique ou insira o URL da atividade e clique em **[!UICONTROL Avançar]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://wwww.adobe.com`] têm correspondência.

   A página com o URL especificado é aberta no Visual Experience Composer.

1. Para nomear a atividade, clique no campo **[!UICONTROL Nome]** e digite o nome da atividade.

   ![Campo nome](/help/c-activities/t-automated-personalization/assets/ab_newname-new.png)

   O nome da atividade não pode começar com nenhum dos seguintes caracteres:

   | Caractere | Descrição |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

1. Modifique os elementos da página conforme explicado nas [opções do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Você pode selecionar várias imagens de uma vez no gerenciador de ativos. Isso permite que você visualize rapidamente a página com cada uma das imagens configuradas para a atividade. Você também pode editar facilmente os elementos de texto em suas ofertas. Quando você edita um elemento, barras aparecem nele para indicar que foi alterado.

1. Clique em **[!UICONTROL Gerenciar conteúdo]** para configurar as combinações disponíveis.

   ![Opção Gerenciar conteúdo](/help/c-activities/t-automated-personalization/assets/manage-content.png)

   Uma caixa de diálogo é exibida com três opções na parte superior da tela: Experiências, Ofertas e Grupos de exclusão.

   ![Caixa de diálogo Gerenciar conteúdo](/help/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Embora você possa criar até 30.000 experiências em uma atividade AP. A atividade funciona melhor quando menos de 5.000 experiências são usadas.

   A lista de [!UICONTROL Experiências] mostra cada parte do conteúdo selecionado para a atividade e o local onde está atribuído.

   Você pode excluir as experiências específicas ao passar o cursor do mouse sobre a experiência desejada e clicar no ícone de exclusão.

   ![Cursor do mouse sobre o ícone Excluir](/help/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Você pode excluir/incluir em lote as experiências marcando a caixa de seleção das experiências relevantes e, em seguida, clicando no ícone Excluir no canto superior direito da caixa de diálogo.

   ![Opções de exclusão em lote](/help/c-activities/t-automated-personalization/assets/batch-exclude.png)

   É possível filtrar essa exibição de lista para ver apenas as atividades excluídas ou incluídas, clicando na lista suspensa **Status**.

1. (Condicional) Clique em **[!UICONTROL Ofertas]** para selecionar partes do conteúdo e as atribuir a grupos de relatórios ou somente permitir que alguns visitantes vejam determinadas ofertas com o direcionamento.

   Para obter mais informações, consulte [Oferecer grupos de relatórios na personalização automatizada](/help/c-reports/offer-reporting-groups-in-automated-personalization.md#concept_194128C0B56B4B26AAB57DB49892960C).

   Use a lista de [!UICONTROL Locais] para filtrar ofertas por local. Use a lista [!UICONTROL Grupos de relatórios] para filtrar ofertas a grupos de relatórios. Você também pode usar a lista [!UICONTROL Grupo de relatórios] para filtrar [!UICONTROL Ofertas não atribuídas], de modo que possa atribuir um grupo de relatórios a uma oferta que não está atualmente atribuída a qualquer grupo de relatórios.

   Você pode adicionar experiências específicas a um grupo de relatórios, passando o cursor do mouse sobre a oferta desejada e clicando no ícone de pasta.

   ![Cursor do mouse sobre o ícone de pasta](/help/c-activities/t-automated-personalization/assets/icon-folder.png)

   Você pode adicionar experiências em lote a um grupo de relatórios marcando a caixa de seleção das experiências relevantes e, em seguida, clicando no ícone de pasta Grupo de relatórios no canto superior direito da caixa de diálogo.

   ![Opções do Grupo de relatórios](/help/c-activities/t-automated-personalization/assets/report-group-options.png)

   É importante compreender que os grupos de relatórios afetam o modo como o Target cria seus modelos. Como resultado, recomendamos que você use grupos de relatórios somente se planejar substituir ou adicionar novas ofertas enquanto a atividade estiver ativa. Se uma nova oferta for introduzida em uma atividade ativa, colocá-la em um grupo existente com ofertas similares permitirá que a máquina use os dados já coletados das outras ofertas do grupo para aprender sobre a nova oferta. Você nunca deve colocar todas as ofertas em um único grupo de relatórios.

   Para obter informações sobre como segmentar uma oferta para públicos específicos, consulte  [Ofertas do Target AP](/help/c-activities/t-automated-personalization/ap-target-offers.md#task_F207ED7A41B84FD39BB6FCBFABF4B23E).

1. (Condicional) Clique em **[!UICONTROL Grupos de exclusão]** para escolher qualquer combinação de elementos que você deseja excluir da atividade.

   ![Guia Grupos de exclusão da caixa de diálogo Gerenciar conteúdo](/help/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Embora seja possível criar até 30.000 experiências em um teste de AP, o algoritmo tem melhor desempenho quando são usadas menos de 10.000 experiências distintas.

   Se, atualmente, você não tem grupos de exclusão incluídos na atividade, clique em **Criar grupo de exclusão**. É possível filtrar para criar uma lista que mostre apenas as combinações que deseja excluir. Nomeie o grupo de exclusão e clique em **Salvar**.

   Para editar um grupo de exclusão existente, passe o mouse sobre o grupo que deseja editar e clique no ícone de lápis.

1. Clique em **[!UICONTROL Concluído]** quando terminar de configurar o conteúdo da sua atividade.

1. A etapa de **Direcionamento** lhe parecerá familiar se já tiver usado outros tipos de atividades do Target. Aqui, é possível selecionar um público-alvo e especificar a porcentagem de visitantes que verão a experiência de controle clicando na lista suspensa **[!UICONTROL Alocação personalizada]** e em **Próximo**.

   A lista suspensa [!UICONTROL Alocação personalizada] permite escolher as seguintes opções:

   ![Lista suspensa Meta de alocação de tráfego](/help/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **Avaliar o algoritmo de personalização (50/50):** se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o controle e o algoritmo de destino. Esta divisão fornece a estimativa mais precisa do aumento. Recomenda-se usar com &quot;experiências aleatórias&quot; como controle.
   * **Maximizar o tráfego de personalização (90/10):** se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle, a fim de garantir que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. Observe que a desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você terá menos precisão em saber qual é o aumento exato. Independentemente da meta, esta é a divisão de tráfego recomendada ao usar uma experiência específica como controle.
   * A **Alocação personalizada** divide manualmente a porcentagem conforme desejado.

1. (Condicional) Na lista suspensa [!UICONTROL Controle], [selecione uma experiência específica a ser usada como controle](/help/c-activities/t-automated-personalization/experience-as-control.md) ou selecione [!UICONTROL Experiência aleatória.]

   A experiência de controle fornece uma comparação para determinar a quantidade de elevação proporcionada pelo teste automatizado.

   A Personalização automatizada sempre mede o desempenho comparado a um grupo de controle. A prática recomendada é colocar, pelo menos, 10% dos participantes no grupo de controle. Se o objetivo for testar se, nos dados recebidos, o algoritmo de personalização tem desempenho melhor do que sem uma personalização (ou seja, o controle fornecido aleatoriamente), um tráfego de 50/50% dividido entre o algoritmo de controle e o de personalização será a maneira mais rápida e precisa de atingir esse objetivo. Se você quiser maximizar a quantidade de tráfego personalizado e não estiver muito preocupado em compreender o aumento exato que sua atividade está gerando, um tráfego de 10/90% dividido entre o algoritmo de controle e o de personalização será a maneira mais rápida e precisa de atingir esse objetivo.

   >[!NOTE]
   >
   >Em atividades de Personalização automatizada, os critérios de entrada (definição de metas de URL, regras de modelo e público-alvo) são avaliados para cada solicitação. Nas versões anteriores, os critérios de entrada eram avaliados uma vez por sessão.

1. Clique em **[!UICONTROL Próximo]** para exibir a página **[!UICONTROL Metas e configurações]**.
1. Configure a atividade com as seguintes configurações e clique em **[!UICONTROL Salvar e fechar]**.

   | Configuração | Descrição |
   |--- |--- |
   | Nome | Nomeie a atividade. Nomeie a atividade de forma descritiva o suficiente para que os membros da equipe possam reconhecê-la na lista de Atividades. Consulte a tabela acima para ver quais caracteres não são permitidos em um nome de atividade. |
   | Objetivo | (Opcional) Digite o objetivo do teste. O objetivo ajuda a lembrar o propósito da atividade. |
   | Prioridade | Dependendo das configurações, a interface do usuário e as opções de Prioridade variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.<br>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<br>Se essa opção não estiver ativada em  [!UICONTROL Administração]  >  [!UICONTROL Relatórios]  (o padrão), especifique uma prioridade: Baixo, Médio ou Alto.<br>Para ativar as prioridades otimizadas, clique em  [!UICONTROL Administração]  >  [!UICONTROL Relatório] e alterne a opção  [!UICONTROL Ativar ] prioridades otimizadas para a posição &quot;Ativado&quot;.<br>Se esta opção estiver ativada, especifique um valor entre 0 e 999:<ul><li>0 = Baixo</li><li>999 = Alto</li></ul>Para atividades criadas em versões anteriores do Target Standard/Premium, a prioridade Baixa é convertida para 0, a Média é convertida para 5 e a Alta é convertida para 10. É possível ajustar esses valores conforme necessário.<br>**Observação**: antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10. |
   | Duração | Defina as datas de início e fim da atividade. |
   | Meta de otimização | Especifique a meta de otimização, que consiste em dois parâmetros:<ul><li>O que você deseja medir com a atividade</li><li>A ação tomada por um participante da atividade que mostra que a meta foi alcançada.</li></ul>É possível escolher nomear a meta de otimização selecionando os três pontos à direita de Minha meta principal. As atividades de Personalização automatizada podem medir a conversão, RPV e AOV. A conversão pode ser alcançada através da visualização de uma página ou exibição de uma mbox. Os cliques também podem ser monitorados.<br>A meta primária torna-se também a métrica de modelagem, usada pelo sistema de modelagem para calcular o sucesso da experiência.<br>Os visitantes podem ser mantidos na atividade para fins de rastreamento depois de atingir a meta de modelagem. Por exemplo, uma atividade de personalização automatizada é frequentemente usada para melhorar taxas de clique, e isso é definido como o objetivo de modelagem. No entanto, é importante ver como as maiores taxas de clique levam à conversão final, então o rastreamento pela conversão final é essencial.<br>É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada.<br>Você deve definir ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra.<br>A opção Adicionar dependência permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada.<br>Para adicionar uma dependência:<ol><li>Depois de adicionar outras métricas, clique em [!UICONTROL Configurações avançadas] no menu de três pontos à direita de Meta adicional.</li><li>Clique na opção [!UICONTROL Adicionar dependência] na parte inferior da seção [!UICONTROL Configurações de relatório].</li><li>Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em [!UICONTROL Alcançado] para alternar a configuração entre [!UICONTROL Alcançado] e [!UICONTROL Não alcançado]</li></ol>É possível editar ou remover dependências depois de adicioná-las. |
   | Métricas de conversão | Por padrão, a métrica de conversão é igual à métrica de meta de otimização. No entanto, é possível definir uma métrica de conversão separada ao desmarcar a opção [!UICONTROL Igual à meta de otimização]. |
   | Métricas adicionais | Adicione quaisquer métricas adicionais de relatórios que deseja usar. É possível adicionar métricas de conversão ou receita.<br>**Observação**: a métrica Envolvimento também não é compatível como uma métrica adicional. A interface do usuário pode permitir que você selecione a métrica de Envolvimento, mas os dados não serão exibidos com precisão nos relatórios. |
   | Públicos-alvo para geração de relatórios | Adicione públicos-alvo para permitir a filtragem por público-alvo nos relatórios. Por padrão, o relatório mostra os resultados para todos os visitantes qualificados. Adicione públicos para filtrar os resultados de subconjuntos de visitantes mais específicos.<br>**Observação**: diferentemente de outros tipos de atividades, a Personalização automatizada não pode usar o Adobe Analytics como fonte de geração de relatórios. |
   | Notas | Digite qualquer informação sobre sua atividade que seja útil para manter ao seu alcance ou de outros membros da equipe. O painel Anotações pode ser redimensionado. |

   Observe que quando você nomeia ou renomeia uma métrica, os seguintes caracteres não são permitidos:

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

Depois de clicar em **[!UICONTROL Criar]**, o Resumo da atividade é exibido. Clique em **Visualizar experiências** para visualizar como suas experiências aparecem depois de entregues. Uma pop-up é mostrada e pode ser usada para exibir e compartilhar links para as experiências de Personalização automatizada em seu site para obter uma &quot;visualização real&quot; das experiências fora do Visual Experience Composer do Target. É necessário compartilhar os links da mensagem para compartilhar a visualização. Clicar em um link e copiar o URL diretamente da página não funcionará porque o URL contém um parâmetro que somente exibe a página corretamente quando você acessa a página a partir do link da mensagem.

Para obter informações sobre os relatórios, consulte  [Relatórios de personalização automatizada](/help/c-reports/reports-ap.md#concept_C02BAFC922114A44846998FD956E345A).
