---
keywords: personalização automatizada, ap, audiences, conjunto, random forest, variação residual, variação de erro, valor histórico
description: Saiba como criar um [!UICONTROL Automated Personalization] (AP) em [!DNL Adobe Target] usando o [!UICONTROL Visual Experience Composer].
title: Como criar um [!UICONTROL Automated Personalization] Atividade?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Automated Personalization
exl-id: eadc2bbc-310b-479f-b75b-253e8d7aa812
source-git-commit: bde5506033fbca1577fad1cda1af203702fc4bb3
workflow-type: tm+mt
source-wordcount: '1853'
ht-degree: 62%

---

# Criar uma atividade de [!UICONTROL Automated Personalization]

Crie um [!UICONTROL Automated Personalization] (AP) em [!DNL Adobe Target] usando o [!UICONTROL Visual Experience Composer] (VEC).

O [!UICONTROL Automated Personalization] Fluxo de trabalho da atividade (AP) em [!DNL Adobe Target] O varia do fluxo de trabalho dos outros tipos de atividade.

1. No [!DNL Target] [!UICONTROL Atividades] listar, clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Automated Personalization]**.

   ![Criar atividade: Personalização automatizada](/help/main/c-activities/t-automated-personalization/assets/ap-create-new.png)

1. Para usar o VEC, clique em **[!UICONTROL Visual (Padrão)]**.

   ![Caixa de diálogo Criar atividade de Personalização automatizada](/help/main/c-activities/t-automated-personalization/assets/ap_url-new.png){width="300"}

   Para usar o [!UICONTROL Experience Composer baseado em formulário], selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/main/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do [!UICONTROL Experience Composer baseado em formulário], [!DNL Target] ofertas [!UICONTROL VEC para aplicativos de página única]. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/main/c-experiences/experiences.md).
   >
   >Para obter informações de solução de problemas sobre o VEC, consulte [Solução de problemas do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).

1. (Condicional) [Escolher um espaço de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md).

1. Verifique ou insira o URL da atividade e clique em **[!UICONTROL Avançar]**.

   >[!NOTE]
   >
   >[!DNL Target] não diferencia os protocolos de URL ([!DNL https] e [!DNL http]). Como resultado, [!DNL `http://www.adobe.com`] e [!DNL `https://wwww.adobe.com`] têm correspondência.

   A página com o URL especificado é aberta no VEC.

1. Para nomear a atividade, clique no botão **[!UICONTROL Nome]** e digite o nome da atividade.

   ![Campo nome](/help/main/c-activities/t-automated-personalization/assets/ap-new-name.png)

   O nome da atividade não pode começar com nenhum dos seguintes caracteres:

   | Caractere | Descrição |
   |--- |--- |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

   Além disso, o nome da atividade não pode conter nenhuma das seguintes sequências de caracteres: &#39;;=&#39;, &#39;;+&#39;, &#39;;-&#39;, &#39;;@&#39;, &#39;,=&#39;, &#39;,+&#39;, &#39;,-&#39;, &#39;,@&#39;, &#39;[&quot;&#39;, &#39;&quot;]&#39;, &#39;[&#39;&#39;, &#39;&#39;]&quot;.

1. Modifique os elementos da página conforme explicado nas [opções do Visual Experience Composer](/help/main/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Você pode selecionar várias imagens de uma vez no gerenciador de ativos. Isso permite que você visualize rapidamente a página com cada uma das imagens configuradas para a atividade. Você também pode editar facilmente os elementos de texto em suas ofertas. Quando você edita um elemento, barras aparecem nele para indicar que foi alterado.

1. Clique em **[!UICONTROL Gerenciar conteúdo]** para configurar as combinações disponíveis.

   ![Opção Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/manage-content.png)

   Uma caixa de diálogo é exibida com três opções na parte superior da tela: [!UICONTROL Experiências], [!UICONTROL Ofertas]e [!UICONTROL Grupos de exclusão].

   ![Caixa de diálogo Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/ap_content-new.png)

   >[!NOTE]
   >
   >Embora você possa criar até 30.000 experiências em uma atividade AP. A atividade funciona melhor quando menos de 5.000 experiências são usadas. Esse mesmo limite é aplicado mesmo quando a atividade tiver ativado a opção [!UICONTROL Não permitir duplicações].

   O [!UICONTROL Experiências] lista mostra cada parte do conteúdo selecionado para a atividade e o local onde está atribuído.

   Você pode excluir experiências específicas ao passar o mouse sobre a experiência desejada e clicar no botão [!UICONTROL Excluir] ícone .

   ![Cursor do mouse sobre o ícone Excluir](/help/main/c-activities/t-automated-personalization/assets/icon-exclude.png)

   Você pode excluir/incluir em lote as experiências marcando a caixa de seleção das experiências relevantes e clicando no botão [!UICONTROL Excluir] no canto superior direito da caixa de diálogo.

   ![Opções de exclusão em lote](/help/main/c-activities/t-automated-personalization/assets/batch-exclude.png)

   É possível filtrar essa exibição de lista para ver apenas as atividades excluídas ou incluídas, clicando na lista suspensa [!UICONTROL Status].

1. (Condicional) Clique em **[!UICONTROL Ofertas]** para selecionar partes do conteúdo e as atribuir a grupos de relatórios ou somente permitir que alguns visitantes vejam determinadas ofertas com o direcionamento.

   Para obter mais informações sobre grupos de relatórios, consulte [Grupos de relatórios de oferta no Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

1. (Condicional) Clique em **[!UICONTROL Grupos de exclusão]** para escolher qualquer combinação de elementos que você deseja excluir da atividade.

   ![Guia Grupos de exclusão da caixa de diálogo Gerenciar conteúdo](/help/main/c-activities/t-automated-personalization/assets/exclusion_groups-new.png)

   Embora seja possível criar até 30.000 experiências em um teste de AP, o algoritmo tem melhor desempenho quando são usadas menos de 10.000 experiências distintas. Esse mesmo limite é aplicado mesmo quando a atividade tiver ativado a opção [!UICONTROL Não permitir duplicações].

   Se, atualmente, você não tem grupos de exclusão incluídos na atividade, clique em **Criar grupo de exclusão**. É possível filtrar para criar uma lista que mostre apenas as combinações que deseja excluir. Nomeie o grupo de exclusão e clique em **Salvar**.

   Para editar um grupo de exclusão existente, passe o mouse sobre o grupo que deseja editar e clique no ícone de lápis.

1. Clique em **[!UICONTROL Concluído]** quando terminar de configurar o conteúdo da sua atividade.

1. O **Direcionamento** O passo parece familiar se tiver usado outros [!DNL Target] tipos de atividades. Aqui, você pode selecionar um público-alvo e especificar a porcentagem de visitantes que visualizam a experiência de controle clicando no botão **[!UICONTROL Alocação personalizada]** lista suspensa e clique em **Próximo**.

   A lista suspensa [!UICONTROL Alocação personalizada] permite escolher as seguintes opções:

   ![Lista suspensa Meta de alocação de tráfego](/help/main/c-activities/t-automated-personalization/assets/traffic-allocation-goal-ap.png)

   * **[!UICONTROL Avaliar o algoritmo de personalização (50/50)]:** Se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o algoritmo de controle e o direcionado. Esta divisão fornece a estimativa mais precisa do aumento. Sugestão para uso com &quot;experiências aleatórias&quot; como controle.
   * **[!UICONTROL Maximizar o tráfego de personalização (90/10)]:** Se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle. Essa opção garante que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. Observe que a desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você tem menos precisão em saber qual é o aumento exato. Independentemente da meta, esta é a divisão de tráfego recomendada ao usar uma experiência específica como controle.
   * **[!UICONTROL Alocação personalizada]:** Divida manualmente a porcentagem conforme desejado.

1. (Condicional) Na lista suspensa [!UICONTROL Controle], [selecione uma experiência específica a ser usada como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou selecione [!UICONTROL Experiência aleatória.]

   A experiência de controle fornece uma comparação para determinar a quantidade de elevação proporcionada pelo teste automatizado.

   [!UICONTROL A Personalização automatizada sempre mede o desempenho comparado a um grupo de controle. ] A prática recomendada é colocar, pelo menos, 10% dos participantes no grupo de controle. Se o objetivo for testar se, nos dados recebidos, o algoritmo de personalização tem desempenho melhor do que sem uma personalização (ou seja, o controle fornecido aleatoriamente), um tráfego de 50/50% dividido entre o algoritmo de controle e o de personalização será a maneira mais rápida e precisa de atingir esse objetivo. Se você quiser maximizar a quantidade de tráfego personalizado e não estiver muito preocupado em compreender o aumento exato que sua atividade está gerando, um tráfego de 10/90% dividido entre o algoritmo de controle e o de personalização será a maneira mais rápida e precisa de atingir esse objetivo.

   >[!NOTE]
   >
   >Em [!UICONTROL Automated Personalization] atividades, critérios de entrada (direcionamento por URL, regras de modelo e públicos-alvo) são avaliados para cada solicitação. Nas versões anteriores, os critérios de entrada eram avaliados uma vez por sessão.

1. Clique em **[!UICONTROL Próximo]** para exibir a página **[!UICONTROL Metas e configurações]**.
1. Configure a atividade com as seguintes configurações e clique em **[!UICONTROL Salvar e fechar]**.

   | Configuração | Descrição |
   |--- |--- |
   | [!UICONTROL Nome] | Nomeie a atividade. Nomeie a atividade de forma descritiva o suficiente para que os membros da equipe possam reconhecê-la no [!UICONTROL Atividades] lista. Consulte a tabela acima para ver quais caracteres não são permitidos em um nome de atividade. |
   | [!UICONTROL Objetivo] | (Opcional) Digite o objetivo do teste. O objetivo ajuda a lembrar o propósito da atividade. |
   | [!UICONTROL Prioridade] | Dependendo das configurações, a interface do usuário e as opções de [!UICONTROL Prioridade] variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.<br>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<br>Se esta opção não estiver ativada em [!UICONTROL Administração] > [!UICONTROL Relatório] (o padrão), especifique uma prioridade: Baixo, Médio ou Alto.<br>Para ativar as prioridades otimizadas, clique em [!UICONTROL Administração] > [!UICONTROL Relatório], em seguida, alterne a [!UICONTROL Ativar prioridades otimizadas] para a posição &quot;Ligado&quot;.<br>Se esta opção estiver ativada, especifique um valor entre 0 e 999:<ul><li>0 = Baixo</li><li>999 = Alto</li></ul>Para atividades criadas em versões anteriores do [!DNL Target Standard/Premium], a prioridade Baixa é convertida para 0, a Média é convertida para 5 e a Alta é convertida para 10. É possível ajustar esses valores conforme necessário.<br>**Observação**: antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10. |
   | [!UICONTROL Duração] | Defina as datas de início e fim da atividade. Você pode selecionar [!UICONTROL Quando ativado] ou você pode especificar uma data e hora específicas. |
   | [!UICONTROL Meta de otimização] | Especifique a meta de otimização, que consiste em dois parâmetros:<ul><li>O que você deseja medir com a atividade</li><li>A ação tomada por um participante da atividade que mostra que a meta foi alcançada.</li></ul>Você pode escolher nomear a meta de otimização selecionando os três pontos à direita de [!UICONTROL Meu objetivo principal]. [!UICONTROL Automated Personalization] as atividades podem medir [!UICONTROL Conversão] ou [!UICONTROL Receita]. A conversão pode ser alcançada através da visualização de uma página ou exibição de uma mbox. Os cliques também podem ser monitorados.<br>A meta primária torna-se também a métrica de modelagem, usada pelo sistema de modelagem para calcular o sucesso da experiência.<br>Os visitantes podem ser mantidos na atividade para fins de rastreamento depois de atingir a meta de modelagem. Por exemplo, muitas vezes uma [!UICONTROL Automated Personalization] A atividade é usada para melhorar as taxas de clique, e isso é definido como o objetivo de modelagem. No entanto, é importante ver como as maiores taxas de clique levam à conversão final, então o rastreamento pela conversão final é essencial.<br>É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada.<br>Você deve definir ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra.<br>A opção Adicionar dependência permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada.<br>Para adicionar uma dependência:<ol><li>Depois de adicionar outras métricas, clique em **[!UICONTROL Configurações avançadas]**[!UICONTROL  no menu de três pontos à direita de Meta adicional].</li><li>Clique na opção **[!UICONTROL Adicionar dependência]** na parte inferior da seção [!UICONTROL Configurações de relatório].</li><li>Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em [!UICONTROL Alcançado] para alternar a configuração entre [!UICONTROL Alcançado] e [!UICONTROL Não alcançado]</li></ol>É possível editar ou remover dependências depois de adicioná-las. |
   | [!UICONTROL Métricas de conversão] | Por padrão, a métrica de conversão é igual à métrica de meta de otimização. No entanto, é possível definir uma métrica de conversão separada ao desmarcar a opção [!UICONTROL Igual à meta de otimização]. |
   | [!UICONTROL Métricas adicionais] | Adicione outras métricas de relatórios que deseja usar. É possível adicionar métricas de conversão ou receita.<br>**Observação**: a métrica Envolvimento também não é compatível como uma métrica adicional. A interface do usuário pode permitir que você selecione a variável [!UICONTROL Envolvimento] , mas os dados não são exibidos com precisão nos relatórios. |
   | [!UICONTROL Públicos-alvo para geração de relatórios] | Adicione públicos-alvo para permitir a filtragem por público-alvo nos relatórios. Por padrão, o relatório mostra os resultados para todos os visitantes qualificados. Adicione públicos para filtrar os resultados de subconjuntos de visitantes mais específicos.<br>**Observação**: Diferente de outros tipos de atividades, [!UICONTROL Automated Personalization] não pode usar [!UICONTROL Adobe Analytics] como fonte de geração de relatórios (A4T). |
   | [!UICONTROL Notas] | Digite qualquer informação sobre sua atividade que seja útil para manter ao seu alcance ou de outros membros da equipe. O [!UICONTROL Notas] O painel é redimensionável. |

   Quando você nomeia ou renomeia uma métrica, os seguintes caracteres não são permitidos:

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

Depois de clicar em **[!UICONTROL Salvar e fechar]**, o [!UICONTROL Visão geral] será exibida. Clique em **Visualizar experiências** para visualizar a aparência das experiências quando entregues. Um pop-up é exibido e pode ser usado para exibir e compartilhar links para suas experiências de AP no site para obter uma &quot;visualização real&quot; das experiências fora do [!UICONTROL Target]Visual Experience Composer (VEC) do . É necessário compartilhar os links da mensagem para compartilhar a visualização. Clicar em um link e copiar o URL diretamente do navegador não funcionará. Copiar o link faz com que o URL contenha um parâmetro que exibe a página corretamente somente quando você acessa a página do link na mensagem.

Para obter informações sobre os relatórios, consulte  [Relatórios de personalização automatizada](/help/main/c-reports/personalization-reports/reports-ap.md).
