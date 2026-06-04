---
keywords: configurações de atividade, metas e configurações A/B, configurações de relatórios, métricas de meta, métricas de sucesso, métricas dependentes de sucesso, configurações avançadas, meta principal, métricas adicionais, objetivo, prioridade, duração, solução de relatórios, meta, públicos-alvo para relatórios, qual métrica de sucesso deve ser alcançada antes de incremento dessa métrica, o que acontecerá após o usuário encontrar essa métrica de meta, observações
description: Saiba como usar a página [!UICONTROL Metas e configurações] para especificar informações sobre as metas de uma atividade A/B.
title: Como Especificar Metas e Configurações em uma Atividade A/B [!DNL Target] ?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: eb7e892a85fa3952ffc22172085d421756d0dfb5
workflow-type: tm+mt
source-wordcount: '1411'
ht-degree: 37%

---

# Metas e Configurações

A página [!UICONTROL Metas e Configurações] em [!DNL Adobe Target] é onde você especifica informações sobre as metas da atividade.

As configurações disponíveis dependem se você usa o Target ou o [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) como a fonte de relatórios.

## [!UICONTROL Configurações da atividade] {#section_DCBDC354261F420EBD4B43EA34947BAC}

A seção [!UICONTROL Configurações da Atividade] da página [!UICONTROL Metas e Configurações] permite configurar as seguintes opções:

| Configurações | Descrição |
|--- |--- |
| [!UICONTROL Objetivo] | Digite um objetivo opcional. O objetivo pode ser qualquer informação que ajude você e os membros da equipe a identificar a atividade. |
| [!UICONTROL Prioridade] | Dependendo das configurações, a interface do usuário do [!DNL Target] e as opções de [!UICONTROL Prioridade] variam. Você pode usar as configurações herdadas de [!UICONTROL Baixo], [!UICONTROL Medium] ou [!UICONTROL Alto], ou pode habilitar prioridades otimizadas de 0 a 999.<P>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<P>Se esta opção não estiver habilitada em [!UICONTROL Administration] (padrão), especifique uma prioridade: [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High].<P>Para habilitar [prioridades otimizadas](/help/main/administrating-target/reporting.md), clique em [!UICONTROL Administração] > [!UICONTROL Relatórios] e alterne a opção [!UICONTROL Habilitar Prioridades Otimizadas] para a posição &quot;Ativado&quot;. <P>Se esta opção estiver habilitada, especifique um valor de 0 a 999: 0 = [!UICONTROL Baixo] e 999 = [!UICONTROL Alto]. <P>Para atividades criadas em versões anteriores do [!DNL Target], a prioridade [!UICONTROL Baixa] é convertida para 0, a [!UICONTROL Medium] é convertida para 5 e a [!UICONTROL Alta] é convertida para 10. É possível ajustar esses valores conforme necessário.<P>Observação: antes de poder desativar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10. |
| Duração | A atividade pode começar quando aprovada ou você pode definir data e hora específicas. Da mesma maneira, a atividade não pode terminar quando é desativada, ou você pode definir uma data e hora. O seletor de hora usa um relógio de 24 horas, sendo 00:00 meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o. |

## [!UICONTROL Configurações da geração de relatórios] {#section_13119392051044FBA6387D9B3B1C43CF}

A seção [!UICONTROL Configurações de Relatórios] da página [!UICONTROL Metas e Configurações] permite configurar as seguintes opções:

| Configurações | Descrição |
|--- |--- |
| [!UICONTROL Source de Relatórios] | Especificar de qual solução os dados são coletados:<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>Se uma fonte de relatórios for especificada nas [configurações da conta](/help/main/administrating-target/reporting.md), a fonte especificada será usada e essa configuração não ficará visível.<P>Não é possível alterar sua fonte de relatórios após a atividade entrar em vigor para manter os relatórios consistentes.<P>**Adobe Analytics**: consulte [Adobe Analytics como o Source de Relatórios para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para saber mais sobre as diferenças entre as soluções de relatórios e as vantagens de cada uma. Ao selecionar [!DNL Analytics] como fonte de relatórios para [!DNL Target], você seleciona um conjunto de relatórios [!DNL Analytics] para receber os dados de atividade [!DNL Target].<P>Para especificar uma fonte de relatórios, primeiro escolha uma das [!DNL Analytics] empresas às quais sua conta está vinculada e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para conexão com [!DNL Adobe Target] estão disponíveis para seleção. Se você não vir os conjuntos de relatórios esperados, primeiro tente fazer logoff e fazer logon novamente no [!DNL Adobe Experience Cloud] para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, entre em contato com o Atendimento ao cliente.<P><P>**Adobe Customer Journey Analytics**: consulte [[!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obter mais informações sobre a integração entre [!DNL Adobe Customer Journey Analytics] e [!DNL Target].<P>Os relatórios [!DNL Target] em [!DNL Customer Journey Analytics] têm suporte em atividades A/B com divisão manual de tráfego. As atividades A/B de [!UICONTROL Direcionamento automático] e [!UICONTROL Alocação automática] não podem usar os relatórios [!DNL Target] em [!DNL Customer Journey Analytics]. |
| [!UICONTROL Métrica de objetivo] | Selecione a ação executada por um visitante para atingir a meta. Por exemplo, escolha uma métrica de [!UICONTROL Conversão] e defina os parâmetros que determinam quando o sucesso é obtido. Para obter mais informações sobre como configurar métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Observação: se a solução de relatório for definida como [!DNL Analytics], a única métrica de meta disponível será [!UICONTROL Conversão]. [!DNL Analytics] métricas não podem ser selecionadas como uma meta. Quando você selecionar sua métrica de sucesso, um seletor será exibido. Use esse seletor para escolher as especificações da métrica de sucesso.<P>Se estiver habilitado, o campo [!UICONTROL Valor estimado de Conversão] (não disponível para as métricas de [!UICONTROL Pontuação da página]) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Receita por visitante], [!UICONTROL Valor médio de pedido], [!UICONTROL Vendas totais] e [!UICONTROL Pedidos]), a estimativa usa [!UICONTROL Receita por visitante]. O tipo de dados é a moeda.<P>Após atingir o objetivo da atividade, um visitante continua vendo o conteúdo da atividade, a menos que o visitante esteja qualificado para uma atividade de prioridade mais alta. Se o visitante atingir o objetivo novamente, será contado como outra conversão. Isso é diferente do comportamento padrão em [!DNL Target Classic], que conta os visitantes como novos se visualizarem a atividade novamente. |
| [!UICONTROL Métricas adicionais] | Crie métricas de sucesso adicionais. Esta configuração não estará disponível se a solução de relatório estiver definida como [!DNL Analytics]. Nesse caso, as métricas definidas para o conjunto de relatórios [!DNL Analytics] são aplicadas. |
| [!UICONTROL Públicos-alvo para relatórios] | Por padrão, os relatórios mostram os resultados para todos os visitantes qualificados. Você pode adicionar públicos-alvo do relatório para mostrar informações somente sobre públicos-alvo específicos. Esta configuração não estará disponível se você escolher [!DNL Analytics] como sua solução de relatório. A audiência definida para o conjunto de relatórios [!DNL Analytics] é aplicada. |

## Configurações avançadas {#section_E2FE441AFB324E498793ABB025ED9974}

A seção [!UICONTROL Configurações Avançadas] da página [!UICONTROL Metas e Configurações] permite configurar as seguintes opções:

Para especificar as configurações avançadas, clique no ícone **[!UICONTROL Mais]** (as reticências verticais) e clique em **[!UICONTROL Configurações Avançadas]**, conforme mostrado na ilustração a seguir.

![Menu Configurações avançadas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. A opção de configurações avançadas não está disponível.

![Configurações avançadas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Configuração | Descrição |
|--- |--- |
| [!UICONTROL Qual métrica de sucesso deve ser alcançada antes do incremento dessa métrica?] | Use essa opção para contar apenas alguém que atingiu a métrica de sucesso se já tiver atingido uma métrica de sucesso diferente. Por exemplo, uma conversão de atividade só pode ser válida se o visitante clicar na oferta ou acessar uma página específica antes da conversão. É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada. Defina ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra. A opção [!UICONTROL Adicionar dependência] permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada. Para adicionar uma dependência:<ul><li>Depois de adicionar outras métricas, clique em [!UICONTROL Configurações avançadas].</li><li>Clique na opção [!UICONTROL Adicionar dependência]:</li><li>Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em [!UICONTROL Alcançado] para alternar a configuração entre [!UICONTROL Alcançado] e[!UICONTROL &#x200B; Não alcançado].</li><li>É possível editar ou remover dependências depois de adicioná-las.</li></ul> |
| [!UICONTROL O que acontecerá após o usuário encontrar esta métrica de meta?] | Há três opções para o que acontece depois que um visitante atinge a métrica de meta:<ul><li>Selecione [!UICONTROL Aumentar a contagem e manter o usuário na atividade] para especificar como é feito o aumento da contagem.</li><li>Selecione [!UICONTROL Aumentar a contagem, liberar o usuário e permitir a reentrada] para especificar a experiência que o usuário vê ao entrar na atividade novamente.</li><li>Selecione [!UICONTROL Incrementar contagem, liberar usuário e barra de reentrada] para especificar o que o usuário vê em vez do conteúdo da atividade.</li></ul> |
| [!UICONTROL Como a contagem será incrementada?] | Existem três opções de como a contagem é incrementada:<ul><li>[!UICONTROL Uma vez por participante]</li><li>[!UICONTROL Em Todas as Impressões (Excluindo atualizações de página)]</li><li>[!UICONTROL Em Todas As Impressões]</li></ul> |

Consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) para obter mais informações sobre configurações avançadas.

## Outros metadados {#section_2E8917BEFB954480A4206B9E9E917F80}

A seção [!UICONTROL Outros metadados] da página [!UICONTROL Metas e configurações] permite especificar qualquer informação sobre a sua atividade que seja útil para manter disponível para você mesmo ou para outros membros da equipe. O painel Anotações é redimensionável.|

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Configurações da atividade (3:02) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

(https://video.tv.adobe.com/v/17381?captions=por_br)

### Criação de testes A/B (8:36) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo demonstra como a configuração das atividades se encaixa no fluxo de trabalho guiado de três etapas ao criar uma atividade. Metas e configurações são discutidas a partir de 5:30.

* Criar uma atividade A/B no Adobe Target
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/31295?captions=por_br)
