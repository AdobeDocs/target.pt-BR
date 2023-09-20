---
keywords: configurações de atividade, metas e configurações A/B, configurações de relatórios, métricas de meta, métricas de sucesso, métricas dependentes de sucesso, configurações avançadas, meta principal, métricas adicionais, objetivo, prioridade, duração, solução de relatórios, meta, públicos-alvo para relatórios, qual métrica de sucesso deve ser alcançada antes de incremento dessa métrica, o que acontecerá após o usuário encontrar essa métrica de meta, observações
description: Saiba como usar o [!UICONTROL Metas e Configurações] página em [!DNL Adobe Target] para especificar informações sobre as metas de uma atividade A/B.
title: Como especificar metas e configurações em uma [!DNL Target] Atividade A/B?
feature: A/B Tests
exl-id: 6c970289-a897-46bc-a8d2-ba8c045abe12
source-git-commit: 8682c24cf1740171dd2ce1862b3bdce1e2082869
workflow-type: tm+mt
source-wordcount: '1349'
ht-degree: 53%

---

# Metas e Configurações

A variável [!UICONTROL Metas e configurações] página em [!DNL Adobe Target] é onde você especifica as informações sobre as metas da atividade.

As configurações disponíveis dependem se você usa o Target ou [Analytics](/help/main/c-integrating-target-with-mac/a4t/a4t.md) como fonte de relatórios.

## [!UICONTROL Configurações da atividade] {#section_DCBDC354261F420EBD4B43EA34947BAC}

A variável [!UICONTROL Configurações da atividade] seção do [!UICONTROL Metas e configurações] permite configurar as seguintes opções:

| Configurações | Descrição |
|--- |--- |
| [!UICONTROL Objetivo] | Digite um objetivo opcional. O objetivo pode ser qualquer informação que ajude você e os membros da equipe a identificar a atividade. |
| [!UICONTROL Prioridade] | Dependendo das configurações, a variável [!DNL Target] Interface e opções para [!UICONTROL Prioridade] variam. É possível usar as configurações herdadas de [!UICONTROL Baixa], [!UICONTROL Medium]ou [!UICONTROL Alta]ou você pode ativar as prioridades otimizadas de 0 a 999.<P>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<P>Se esta opção não estiver ativada no [!UICONTROL Administração] (o padrão), especifique uma prioridade: [!UICONTROL Baixa], [!UICONTROL Medium]ou [!UICONTROL Alta].<P>Para habilitar [prioridades otimizadas](/help/main/administrating-target/reporting.md), clique em [!UICONTROL Administração] > [!UICONTROL Relatórios], em seguida, alterne a [!UICONTROL Ativar prioridades otimizadas] para a posição &quot;Ligado&quot;. <P>Se esta opção estiver habilitada, especifique um valor de 0 a 999: 0 = [!UICONTROL Baixa] e 999 = [!UICONTROL Alta]. <P>Para atividades criadas em versões anteriores do [!DNL Target], [!UICONTROL Baixa] a prioridade é convertida em 0, [!UICONTROL Medium] é convertido em 5, e [!UICONTROL Alta] é convertido em 10. É possível ajustar esses valores conforme necessário.<P>Observação: antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10. |
| Duração | A atividade pode começar quando aprovada ou você pode definir data e hora específicas. Da mesma maneira, a atividade não pode terminar quando é desativada, ou você pode definir uma data e hora. O seletor de hora usa um relógio de 24 horas, sendo 00h a meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o. |

## [!UICONTROL Configurações da geração de relatórios] {#section_13119392051044FBA6387D9B3B1C43CF}

A variável [!UICONTROL Configurações de relatório] seção do [!UICONTROL Metas e configurações] permite configurar as seguintes opções:

| Configurações | Descrição |
|--- |--- |
| [!UICONTROL Fonte de geração de relatórios] | Especificar se os dados são coletados de [!DNL Adobe Target] ou de [!DNL Adobe Analytics]. Consulte [Adobe Analytics como fonte de relatório para o Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para saber quais são as diferenças entre as soluções de relatório e as vantagens de cada uma. Ao selecionar [!DNL Analytics] como fonte de relatórios para [!DNL Target], você seleciona um [!DNL Analytics] conjunto de relatórios a ser recebido [!DNL Target] dados da atividade.<P>Para especificar uma origem de relatório, primeiro escolha uma das opções [!DNL Analytics] empresas às quais sua conta está vinculada e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para conexão com o [!DNL Adobe Target] estão disponíveis para seleção. Se você não vir os conjuntos de relatórios esperados, primeiro tente fazer logoff e logon novamente na [!DNL Adobe Experience Cloud] para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, entre em contato com o Atendimento ao cliente.<P>Se uma fonte de relatórios for especificada nas configurações da conta, a fonte especificada será usada e essa configuração não ficará visível.<P>Observação: não é possível alterar sua fonte de relatórios após a atividade entrar em vigor para manter os relatórios consistentes. |
| [!UICONTROL Métrica de objetivo] | Selecione a ação executada por um visitante para atingir a meta. Por exemplo, escolha uma [!UICONTROL Conversão] e defina os parâmetros que determinam quando o sucesso é obtido. Para obter mais informações sobre como configurar métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<P>Observação: se a solução de relatório estiver definida como [!DNL Analytics], a única métrica de meta disponível é [!UICONTROL Conversão]. [!DNL Analytics]As métricas do não podem ser selecionadas como uma meta. Quando você selecionar sua métrica de sucesso, um seletor será exibido. Use esse seletor para escolher as especificações da métrica de sucesso.<P>Se ativado, a variável [!UICONTROL Valor estimado da conversão] (não disponível para o [!UICONTROL Pontuação da página] ) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Receita por visitante], [!UICONTROL Valor médio de pedido], [!UICONTROL Total de vendas], e [!UICONTROL Pedidos]), a estimativa utiliza [!UICONTROL Receita por visitante]. O tipo de dados é a moeda.<P>Após atingir o objetivo da atividade, um visitante continua vendo o conteúdo da atividade, a menos que o visitante esteja qualificado para uma atividade de prioridade mais alta. Se o visitante atingir o objetivo novamente, será contado como outra conversão. Isso é diferente do comportamento padrão no [!DNL Target Classic], que conta os visitantes como novos se visualizarem a atividade novamente. |
| [!UICONTROL Métricas adicionais] | Crie métricas de sucesso adicionais. Essa configuração não estará disponível se a solução de relatório estiver definida como [!DNL Analytics]. Nesse caso, as métricas definidas para o [!DNL Analytics] conjunto de relatórios são aplicados. |
| [!UICONTROL Públicos-alvo para geração de relatórios] | Por padrão, os relatórios mostram os resultados para todos os visitantes qualificados. Você pode adicionar públicos-alvo do relatório para mostrar informações somente sobre públicos-alvo específicos. Esta configuração não estará disponível se você escolher [!DNL Analytics] como sua solução de relatórios. O público-alvo definido para a [!DNL Analytics] conjunto de relatórios for aplicado. |

## Configurações avançadas {#section_E2FE441AFB324E498793ABB025ED9974}

A variável [!UICONTROL Configurações avançadas] seção do [!UICONTROL Metas e configurações] permite configurar as seguintes opções:

Para especificar configurações avançadas, clique no link **[!UICONTROL Mais]** (as reticências verticais) e clique em **[!UICONTROL Configurações avançadas]**, conforme mostrado na ilustração a seguir.

![Menu Configurações avançadas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. A opção de configurações avançadas não está disponível.

![Configurações avançadas](/help/main/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Configuração | Descrição |
|--- |--- |
| [!UICONTROL Qual métrica de sucesso deve ser atingida antes do aumento dessa métrica?] | Use essa opção para contar apenas alguém que atingiu a métrica de sucesso se já tiver atingido uma métrica de sucesso diferente. Por exemplo, uma conversão de atividade só pode ser válida se o visitante clicar na oferta ou acessar uma página específica antes da conversão. É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada. Defina ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra. A opção [!UICONTROL Adicionar dependência] permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada. Para adicionar uma dependência:<ul><li>Depois de adicionar outras métricas, clique em [!UICONTROL Configurações avançadas].</li><li>Clique na opção [!UICONTROL Adicionar dependência]:</li><li>Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em [!UICONTROL Alcançado] para alternar a configuração entre [!UICONTROL Alcançado] e [!UICONTROL Não alcançado].</li><li>É possível editar ou remover dependências depois de adicioná-las.</li></ul> |
| [!UICONTROL O que acontece depois que um usuário atinge esta métrica de meta?] | Há três opções para o que acontece depois que um visitante atinge a métrica de meta:<ul><li>Selecione [!UICONTROL Aumentar a contagem e manter o usuário na atividade] para especificar como é feito o aumento da contagem.</li><li>Selecione [!UICONTROL Aumentar a contagem, liberar o usuário e permitir a reentrada] para especificar a experiência que o usuário vê ao entrar na atividade novamente.</li><li>Selecione [!UICONTROL Aumentar a contagem, liberar o usuário e impedir a reentrada] para especificar o que o usuário vê em lugar do conteúdo da atividade.</li></ul> |
| [!UICONTROL De que maneira a contagem será incrementada?] | Existem três opções de como a contagem é incrementada:<ul><li>[!UICONTROL Um para cada participante]</li><li>[!UICONTROL Em todas as impressões (excluindo as atualizações de página)]</li><li>[!UICONTROL Em todas as impressões]</li></ul> |

Consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) para obter mais informações sobre configurações avançadas.

## Outros metadados {#section_2E8917BEFB954480A4206B9E9E917F80}

A variável [!UICONTROL Outros metadados] seção do [!UICONTROL Metas e configurações] permite especificar quaisquer informações sobre sua atividade que sejam úteis para você mesmo ou outros membros da equipe. O painel de Observações é redimensionável.|

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
