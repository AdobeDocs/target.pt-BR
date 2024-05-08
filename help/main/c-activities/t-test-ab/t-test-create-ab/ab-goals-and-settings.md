---
keywords: configurações de atividade, metas e configurações A/B, configurações de relatórios, métricas de meta, métricas de sucesso, métricas dependentes de sucesso, configurações avançadas, meta principal, métricas adicionais, objetivo, prioridade, duração, solução de relatórios, meta, públicos-alvo para relatórios, qual métrica de sucesso deve ser alcançada antes de incremento dessa métrica, o que acontecerá após o usuário encontrar essa métrica de meta, observações
description: Saiba como usar o [!UICONTROL Goals and Settings] para especificar informações sobre as metas de uma atividade A/B.
title: Como especificar metas e configurações em uma [!DNL Target] Atividade A/B?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: b5f508d283390c859085d4ee52c582312085addc
workflow-type: tm+mt
source-wordcount: '1252'
ht-degree: 35%

---

# Metas e Configurações

A variável [!UICONTROL Goals & Settings] página em [!DNL Adobe Target] é onde você especifica as informações sobre as metas da atividade.

As configurações disponíveis dependem se você usa o Target ou [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) como fonte de relatórios.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

A variável [!UICONTROL Activity Settings] seção do [!UICONTROL Goals & Settings] permite configurar as seguintes opções:

| Configurações | Descrição |
|--- |--- |
| [!UICONTROL Objective] | Digite um objetivo opcional. O objetivo pode ser qualquer informação que ajude você e os membros da equipe a identificar a atividade. |
| [!UICONTROL Priority] | Dependendo das configurações, a variável [!DNL Target] Interface e opções para [!UICONTROL Priority] variam. É possível usar as configurações herdadas de [!UICONTROL Low], [!UICONTROL Medium]ou [!UICONTROL High]ou você pode ativar as prioridades otimizadas de 0 a 999.<P>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<P>Se esta opção não estiver ativada no [!UICONTROL Administration] (o padrão), especifique uma prioridade: [!UICONTROL Low], [!UICONTROL Medium]ou [!UICONTROL High].<P>Para habilitar [prioridades otimizadas](/help/main/administrating-target/reporting.md), clique em [!UICONTROL Administration] > [!UICONTROL Reporting], em seguida, alterne a [!UICONTROL Enable Fine-Grained Priorities] para a posição &quot;Ligado&quot;. <P>Se esta opção estiver habilitada, especifique um valor de 0 a 999: 0 = [!UICONTROL Low] e 999 = [!UICONTROL High]. <P>Para atividades criadas em versões anteriores do [!DNL Target], [!UICONTROL Low] a prioridade é convertida em 0, [!UICONTROL Medium] é convertido em 5, e [!UICONTROL High] é convertido em 10. É possível ajustar esses valores conforme necessário.<P>Observação: antes de poder desativar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10. |
| Duração | A atividade pode começar quando aprovada ou você pode definir data e hora específicas. Da mesma maneira, a atividade não pode terminar quando é desativada, ou você pode definir uma data e hora. O seletor de hora usa um relógio de 24 horas, sendo 00h a meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o. |

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

A variável [!UICONTROL Reporting Settings] seção do [!UICONTROL Goals & Settings] permite configurar as seguintes opções:

| Configurações | Descrição |
|--- |--- |
| [!UICONTROL Reporting Source] | Especificar de qual solução os dados são coletados:<ul><li>[!DNL Adobe Target]</li><li>[!DNL Adobe Analytics]</li><li>[!DNL Adobe Customer Journey Analytics]</li></ul>Se uma fonte de relatórios for especificada no seu [configurações da conta](/help/main/administrating-target/reporting.md), a origem especificada será usada e essa configuração não ficará visível.<P>Não é possível alterar sua fonte de relatórios após a atividade entrar em vigor para manter os relatórios consistentes.<P>**Adobe Analytics**: Consulte [Adobe Analytics como origem de relatório do Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para saber mais sobre as diferenças entre as soluções de relatórios e as vantagens de cada uma. Ao selecionar [!DNL Analytics] como fonte de relatórios para [!DNL Target], você seleciona um [!DNL Analytics] conjunto de relatórios a ser recebido [!DNL Target] dados da atividade.<P>Para especificar uma origem de relatório, primeiro escolha uma das opções [!DNL Analytics] empresas às quais sua conta está vinculada e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para conexão com o [!DNL Adobe Target] estão disponíveis para seleção. Se você não vir os conjuntos de relatórios esperados, primeiro tente fazer logoff e logon novamente na [!DNL Adobe Experience Cloud] para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, entre em contato com o Atendimento ao cliente.<P><P>**Adobe Customer Journey Analytics**: Consulte [[!DNL Target] relatórios no [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obter mais informações sobre a integração entre [!DNL Adobe Customer Journey Analytics] e [!DNL Target].<P>[!DNL Target] relatórios no [!DNL Customer Journey Analytics] O é compatível com atividades A/B com divisão manual de tráfego. [!UICONTROL Auto-Target] e [!UICONTROL Auto-Allocate] As atividades A/B não podem usar [!DNL Target] relatórios no [!DNL Customer Journey Analytics]. |
| [!UICONTROL Goal Metric] | Selecione a ação executada por um visitante para atingir a meta. Por exemplo, escolha uma [!UICONTROL Conversion] e defina os parâmetros que determinam quando o sucesso é obtido. Para obter mais informações sobre como configurar métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Observação: se a solução de relatório estiver definida como [!DNL Analytics], a única métrica de meta disponível é [!UICONTROL Conversion]. [!DNL Analytics] as métricas não podem ser selecionadas como uma meta. Quando você selecionar sua métrica de sucesso, um seletor será exibido. Use esse seletor para escolher as especificações da métrica de sucesso.<P>Se ativado, a variável [!UICONTROL Estimated Value of the Conversion] (não disponível para o [!UICONTROL Page Score] ) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], e [!UICONTROL Orders]), a estimativa utiliza [!UICONTROL Revenue per Visitor]. O tipo de dados é a moeda.<P>Após atingir o objetivo da atividade, um visitante continua vendo o conteúdo da atividade, a menos que o visitante esteja qualificado para uma atividade de prioridade mais alta. Se o visitante atingir o objetivo novamente, será contado como outra conversão. Isso é diferente do comportamento padrão no [!DNL Target Classic], que conta os visitantes como novos se visualizarem a atividade novamente. |
| [!UICONTROL Additional Metrics] | Crie métricas de sucesso adicionais. Esta configuração não estará disponível se a solução de relatório estiver definida como [!DNL Analytics]. Nesse caso, as métricas definidas para o [!DNL Analytics] conjunto de relatórios são aplicados. |
| [!UICONTROL Audiences for Reporting] | Por padrão, os relatórios mostram os resultados para todos os visitantes qualificados. Você pode adicionar públicos-alvo do relatório para mostrar informações somente sobre públicos-alvo específicos. Esta configuração não estará disponível se você escolher [!DNL Analytics] como sua solução de relatórios. O público-alvo definido para a [!DNL Analytics] conjunto de relatórios for aplicado. |

## Configurações avançadas {#section_E2FE441AFB324E498793ABB025ED9974}

A variável [!UICONTROL Advanced Settings] seção do [!UICONTROL Goals & Settings] permite configurar as seguintes opções:

Para especificar configurações avançadas, clique no link **[!UICONTROL More]** (as reticências verticais) e clique em **[!UICONTROL Advanced Settings]**, conforme mostrado na ilustração a seguir.

![Menu Configurações avançadas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. A opção de configurações avançadas não está disponível.

![Configurações avançadas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Configuração | Descrição |
|--- |--- |
| [!UICONTROL Which success metric must be reached before incrementing this metric?] | Use essa opção para contar apenas alguém que atingiu a métrica de sucesso se já tiver atingido uma métrica de sucesso diferente. Por exemplo, uma conversão de atividade só pode ser válida se o visitante clicar na oferta ou acessar uma página específica antes da conversão. É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada. Defina ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra. A variável [!UICONTROL Add Dependency] permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada. Para adicionar uma dependência:<ul><li>Depois de adicionar outras métricas, clique em [!UICONTROL Advanced Settings].</li><li>Clique em [!UICONTROL Add Dependency] opção:</li><li>Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em [!UICONTROL Reached] para alternar a configuração entre [!UICONTROL Reached] e[!UICONTROL  Not Reached].</li><li>É possível editar ou remover dependências depois de adicioná-las.</li></ul> |
| [!UICONTROL What will happen after a user encounters this goal metric?] | Há três opções para o que acontece depois que um visitante atinge a métrica de meta:<ul><li>Selecionar [!UICONTROL Increment Count & Keep User in Activity] para especificar como a contagem é incrementada.</li><li>Selecionar [!UICONTROL Increment Count, Release User & Allow Reentry] para especificar a experiência que o usuário vê ao entrar na atividade novamente.</li><li>Selecionar [!UICONTROL Increment Count, Release User & Bar from Reentry] para especificar o que o usuário vê em vez do conteúdo da atividade.</li></ul> |
| [!UICONTROL How will the count be incremented?] | Existem três opções de como a contagem é incrementada:<ul><li>[!UICONTROL Once per Entrant]</li><li>[!UICONTROL On Every Impression (Excluding page refreshes)]</li><li>[!UICONTROL On Every Impression]</li></ul> |

Consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) para obter mais informações sobre configurações avançadas.

## Outros metadados {#section_2E8917BEFB954480A4206B9E9E917F80}

A variável [!UICONTROL Other Metadata] seção do [!UICONTROL Goals & Settings] permite especificar quaisquer informações sobre sua atividade que sejam úteis para você mesmo ou outros membros da equipe. O painel Anotações é redimensionável.|

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

>[!VIDEO](https://video.tv.adobe.com/v/17391)
