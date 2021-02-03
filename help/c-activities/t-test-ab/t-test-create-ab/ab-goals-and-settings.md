---
keywords: configurações de atividade, metas e configurações A/B, configurações de relatórios, métricas de meta, métricas de sucesso, métricas dependentes de sucesso, configurações avançadas, meta principal, métricas adicionais, objetivo, prioridade, duração, solução de relatórios, meta, públicos-alvo para relatórios, qual métrica de sucesso deve ser alcançada antes de incremento dessa métrica, o que acontecerá após o usuário encontrar essa métrica de meta, observações
description: A página Metas e configurações no Adobe Target é onde você insere informações sobre as metas do teste.
title: Metas e Configurações
feature: A/B Tests
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1316'
ht-degree: 93%

---


# Metas e Configurações

A página Metas e configurações em [!DNL Adobe Target] é onde você insere informações sobre as metas do teste.

As configurações disponíveis dependem se você usa o Target ou [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md) como a fonte de dados.

![Caixa de diálogo Configurações da atividade](/help/c-activities/t-test-ab/t-test-create-ab/assets/ab_settings-new.png)

## Configurações de atividade {#section_DCBDC354261F420EBD4B43EA34947BAC}

| Configurações | Descrição |
|--- |--- |
| Objetivo | Digite um objetivo opcional. O objetivo pode ser qualquer informação que ajuda você e os membros da sua equipe a identificarem a campanha. |
| Prioridade | Dependendo das configurações, a interface do usuário e as opções de Prioridade variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.<br>A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.<br>Se essa opção não estiver ativada em  [!UICONTROL Administração]  (o padrão), especifique uma prioridade: Baixa, Média ou Alta. <br>Para ativar prioridades refinadas, clique em   [!UICONTROL Administração] >  [!UICONTROL Relatórios] e, em seguida, alterne a opção Ativar prioridades granuladas para a posição &quot;Ativado&quot;. <br>Se essa opção estiver habilitada, especifique um valor entre 0 e 999: 0 = Baixo e 999 = Alto. <br>Para atividades criadas em versões anteriores do Target Standard/Premium, a prioridade Baixa é convertida para 0, a Média é convertida para 5 e a Alta é convertida para 10. É possível ajustar esses valores conforme necessário.<br>Observação: antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10. |
| Duração | A atividade pode começar quando aprovada ou você pode definir data e hora específicas. Da mesma maneira, a atividade não pode terminar quando é desativada, ou você pode definir uma data e hora. O seletor de hora usa um relógio de 24 horas, sendo 00h a meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o. |

## Configurações da geração de relatórios {#section_13119392051044FBA6387D9B3B1C43CF}

| Configurações | Descrição |
|--- |--- |
| Fonte de geração de relatórios | Especifique se os dados são coletados do Adobe Target ou do Adobe Analytics. Consulte [Adobe Analytics como fonte de relatório para o Target](/help/c-integrating-target-with-mac/a4t/a4t.md) para saber quais são as diferenças entre as soluções de relatório e as vantagens de cada uma.  Ao selecionar o Analytics como fonte de relatórios para o Target, você seleciona um conjunto de relatórios do Analytics para receber os dados de atividade do Target.<br>Para fazer isso, primeiro escolha uma das empresas do Analytics vinculadas à sua conta e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para se conectar ao Adobe Target estarão disponíveis para seleção. Se não vir os conjuntos de relatórios esperados, primeiro, experimente sair e entrar na Adobe Experience Cloud para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, entre em contato com o atendimento ao cliente.<br>Se uma fonte de relatórios for especificada nas configurações da conta, a fonte especificada será usada e essa configuração não ficará visível.<br>Observação: não é possível alterar sua fonte de relatórios após a atividade entrar em vigor a fim de manter os relatórios consistentes. |
| Meta | Selecione a ação executada por um visitante para atingir a meta. Por exemplo, escolha uma métrica de Conversão e defina os parâmetros que determinam quando o sucesso é obtido. Para obter mais informações sobre como configurar métricas, consulte [Definir métricas](/help/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md).<br>Observação: se a solução de relatório for definida como Analytics, a única métrica de meta disponível será Conversão. As métricas do Analytics não podem ser selecionadas como uma meta. Quando você selecionar sua métrica de sucesso, um seletor será exibido. Use esse seletor para escolher as especificações da métrica de sucesso.<br>Se estiver habilitado, o campo Valor estimado de Conversão (não disponível para as métricas de Pontuação da página) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o Target calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita (Receita por visitante, Valor médio de pedido, Total de vendas e Pedidos), a estimativa usa a Receita por visitante. O tipo de dados é a moeda.<br>Após atingir o objetivo da atividade, um visitante continua vendo o conteúdo da atividade, a menos que o visitante esteja qualificado para uma atividade de prioridade mais alta. Se o visitante atingir o objetivo novamente, será contado como outra conversão. Isso é diferente do comportamento padrão no Target Classic, que conta os visitantes como novos se eles veem o teste novamente. |
| Métricas adicionais | Crie métricas de sucesso adicionais. Essa configuração não estará disponível se a solução de relatório estiver definida como Analytics. Nesse caso, as métricas definidas para o conjunto de relatórios do Analytics serão aplicadas. |
| Públicos-alvo para geração de relatórios | Por padrão, os relatórios mostram os resultados para todos os visitantes qualificados. Você pode incluir públicos-alvo do relatório para mostrar apenas informações sobre públicos-alvo específicos. Esta configuração não está disponível quando você escolhe o Analytics como a solução de geração de relatórios. O público-alvo definido para o conjunto de relatórios do Analytics é aplicado. |

## Configurações avançadas {#section_E2FE441AFB324E498793ABB025ED9974}

Configurações avançadas estão disponíveis para métricas de meta de teste A/B.

![Menu Configurações avançadas](/help/c-activities/t-test-ab/t-test-create-ab/assets/menu-advanced-settings-new.png)

>[!NOTE]
>
>Caso use o Adobe Analytics como fonte de geração de relatórios, as configurações serão gerenciadas pelo servidor do Analytics. A opção de configurações avançadas não estará disponível.

![Configurações avançadas](/help/c-activities/t-test-ab/t-test-create-ab/assets/advanced-settings.png)

| Configuração | Descrição |
|--- |--- |
| Qual métrica de sucesso deve ser atingida antes do aumento dessa métrica? | Use esta opção para contar alguém que atingiu a métrica de sucesso somente se essa pessoa tiver atingido uma métrica de sucesso diferente antes. Por exemplo, uma conversão de teste só pode ser válida se o visitante clica na oferta ou alcança a uma página específica antes da conversão. É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada. Você deve definir ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra. A opção Adicionar dependência permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada. Para adicionar uma dependência:<ul><li>Depois de adicionar outras métricas, clique em Configurações avançadas.</li><li>Clique na opção Adicionar dependência:</li><li>Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em Alcançado para alternar a configuração entre Alcançado e Não alcançado.</li><li>É possível editar ou remover dependências depois de adicioná-las.</li></ul> |
| O que acontece depois que um usuário atinge esta métrica de meta? | Há três opções para o que acontece depois que um visitante atinge a métrica de meta:<ul><li>Selecione Aumentar a contagem e manter o usuário na atividade para especificar como é feito o aumento da contagem.</li><li>Selecione Aumentar a contagem, liberar o usuário e permitir a reentrada para especificar a experiência que o usuário vê ao entrar na atividade novamente.</li><li>Selecione Aumentar a contagem, liberar o usuário e impedir a reentrada para especificar o que o usuário vê em lugar do conteúdo da atividade.</li></ul> |
| De que maneira a contagem será incrementada? | Existem três opções de como a contagem é incrementada:<ul><li>Um para cada participante</li><li>Em todas as impressões (excluindo as atualizações de página)</li><li>Em todas as impressões</li></ul> |

Consulte [Métricas de sucesso](/help/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) para obter mais informações sobre configurações avançadas.

## Outros metadados {#section_2E8917BEFB954480A4206B9E9E917F80}

| Configurações | Descrição |
|---|---|
| Notas | Digite qualquer informação sobre sua atividade que seja útil para manter ao seu alcance ou de outros membros da equipe. O painel de Observações é redimensionável. |

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Configurações de atividade (3:02) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

(https://video.tv.adobe.com/v/17381?captions=por_br)

### Criando testes A/B (8:36) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo demonstra como a configuração das atividades se encaixa no fluxo de trabalho guiado de três etapas ao criar uma atividade. Metas e configurações são discutidas a partir de 5:30.

* Criar uma atividade A/B no Adobe Target
* Aloque o tráfego usando uma divisão manual ou automática

>[!VIDEO](https://video.tv.adobe.com/v/17391)
