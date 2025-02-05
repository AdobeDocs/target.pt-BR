---
keywords: Target, relatórios, configurações de relatório, predefinição, predefinição de direcionamento, métrica, público-alvo, intervalo de datas, configurações, download, exibição de tabela, exibição em gráfico, elevação média, elevação, limite de elevação, intervalo de confiança, confiança, contribuição de localização, média de execução, metodologia de contagem
description: Saiba como definir configurações de relatório no Adobe Target, incluindo métricas, públicos, intervalos de datas e muito mais.
title: Como Definir Configurações De Relatório?
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '1778'
ht-degree: 48%

---

# Configurações do relatório

Informações para ajudar a definir os elementos que você deseja que apareçam em seu relatório no [!DNL Adobe Target]. As definições de relatório podem ser salvas para uso posterior.

Para exibir um relatório:

1. Clique em **[!UICONTROL Activities]** e depois clique na atividade desejada na lista.
1. Clique na guia **[!UICONTROL Reports]**.

   ![Interface de relatórios](/help/main/c-reports/c-report-settings/assets/report-ui-refresh.png)

## Predefinição do Target {#section_51F67341465045BEB4F1A2FB638A8EB1}

Você pode salvar até dez predefinições diferentes de um relatório de atividade individual, após configurá-lo como desejado (métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante). Todos os usuários do [!DNL Target] podem exibir, editar e excluir as várias predefinições, independentemente de quem as criou.

Você também pode configurar um relatório de atividade individual, como desejado, e depois salvar essa configuração como sua predefinição padrão/favorita. A partir de agora, esta será a exibição apresentada sempre que você visualizar o relatório dessa atividade.

### Criar uma predefinição ou uma predefinição padrão

1. Configure o relatório de atividade conforme desejado.

   As configurações disponíveis, incluindo métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante, são explicadas abaixo.

1. Ao lado de **[!UICONTROL Target Preset]**, clique no ícone **[!UICONTROL More Options]** ( ![Mais Opções ícone](/help/main/assets/icons/MoreSmallListVert.svg) ) ícone > **[!UICONTROL Save as New]**.

   A caixa de diálogo [!UICONTROL Create Preset] é exibida.

   ![Caixa de diálogo Nova predefinição](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Revise as informações nas seções **[!UICONTROL Filters]** para garantir que o relatório esteja configurado como desejado e especifique o **[!UICONTROL Preset Name]** (até 50 caracteres).
1. (Condicional) Se desejar que isso seja o modo de exibição de relatório padrão/favorito, deslize o botão **[!UICONTROL Set as default preset]** para a posição Ativado.
1. Clique em **[!UICONTROL Create]**.

### Selecionar uma predefinição diferente

Selecione a predefinição desejada na lista suspensa **[!UICONTROL Target Preset]**.

### Editar uma predefinição

1. Selecione a predefinição que deseja editar.
1. Edite a configuração do relatório como desejado (métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante).

   Depois de clicar em [!UICONTROL Save], após a edição da configuração do relatório, um asterisco ( &#42; ) será exibido depois do nome predefinido para indicar que a predefinição foi alterada.

1. Clique no ícone **[!UICONTROL More Options]** ( ![Mais Opções ícone](/help/main/assets/icons/MoreSmallListVert.svg) ) > **[!UICONTROL Save as New]** para criar uma nova predefinição.

### Excluir uma predefinição

1. Selecione a predefinição que deseja excluir.
1. Clique no ícone **[!UICONTROL More Options]** ( ![Mais Opções ícone](/help/main/assets/icons/MoreSmallListVert.svg) ) > **[!UICONTROL Delete]**.

1. Clique em **[!UICONTROL Delete]** novamente para confirmar a exclusão (predefinições excluídas não podem ser recuperadas).

### Tratamento de erros de predefinição

Alertas e mensagens dentro de relatórios informam se uma predefinição se tornar inválida. O alerta ou a mensagem instrui a escolher outro público-alvo, métrica, grupo de hosts ou experiência para tornar uma predefinição válida.

A lista a seguir descreve algumas das situações que podem fazer com que uma predefinição se torne inválida:

* Um público-alvo do relatório foi removido da atividade, mas é referenciado na definição predefinida.
* Uma (ou mais) métrica foi excluída, mas referenciada na definição predefinida. Por exemplo, você pode excluir uma ou mais métricas da atividade e, em seguida, adicionar novas métricas.
* Um (ou mais) grupo de hosts (ambiente) não existe, mas é referenciado na definição predefinida.
* Uma (ou mais) experiência foi excluída depois que a predefinição foi criada, mas é referenciada na definição predefinida.
* Uma predefinição é semanticamente inválida, pois as entidades referenciadas ainda existem, mas foram atualizadas de forma a alterar a definição semântica da predefinição. Por exemplo, suponha que você crie inicialmente uma predefinição chamada &quot;Receita no Chrome&quot;. Posteriormente, você atualiza a atividade para medir a Métrica de conversão, em vez da Receita. Essa atualização na definição de atividade invalida semanticamente a definição da predefinição.

## [!UICONTROL Report Metric] {#section_894ABD7148244806B7CE556EBBA2AD62}

Clique na lista suspensa **[!UICONTROL Report Metric]** para selecionar outra [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) ou várias métricas para exibir no gráfico.

Por padrão, a métrica principal é determinada na configuração de métricas de sucesso ao criar a atividade. Se você alterar a configuração e salvar novamente a atividade, a métrica principal da geração de relatórios será atualizada.

Para obter mais informações sobre como selecionar várias métricas para exibir em relatórios, consulte [Exibir Várias Métricas em um Relatório](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7).

## [!UICONTROL Audience] {#section_70926EB4618945D9AFF2B0564FF3717B}

Clique na lista suspensa **[!UICONTROL Audience]** para alterar o público exibido no relatório.

Para obter mais informações, consulte [Públicos-alvo](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522).

## [!UICONTROL Preset Date Range]

Clique na lista suspensa **[!UICONTROL Preset Date Range]** para escolher intervalos de datas predefinidos.

Selecione as novas datas **[!UICONTROL Start]** e **[!UICONTROL End]** para o relatório. Você também pode usar os intervalos **[!UICONTROL Start of Activity]** e **[!UICONTROL Start of activity - End of Activity]**.

Os intervalos de datas predefinidos incluem: Últimos 7 dias, Últimos 15 dias ou Últimos 30 dias. Esses intervalos de datas predefinidos são intervalos acumulados. Se a data inicial for menor que o número de dias escolhido, o calendário exibirá o intervalo da data inicial, mas será aplicado assim que a data inicial for mais antiga que o número de dias escolhido à medida que a duração da atividade aumentar.

Os relatórios têm as seguintes restrições de data:

* A data de início do relatório deve ficar dentro dos últimos dois anos.
* Os relatórios do grupo de ofertas são limitados a 99 dias a partir do dia atual.
* Os relatórios por hora estão limitados a 15 dias.

## Intervalo de datas {#section_A410A768403C4E01891F95CB357E63ED}

A caixa [!UICONTROL Date Range] exibe o intervalo de datas atual do relatório. Clique no ícone **[!UICONTROL Calendar]** ( ![Ícone de calendário](/help/main/assets/icons/Calendar.svg) ) para exibir um calendário que permita alterar o intervalo de datas do relatório.

## Configurações {#section_D99CE462107D45CABE0960F820E1E972}

Para definir configurações de relatório:

1. Clique no ícone **[!UICONTROL Report Settings]** ( ![Ícone Configurações de Relatório](/help/main/assets/icons/Setting.svg) ) e faça as alterações desejadas (conforme explicado abaixo).
1. Clique em **[!UICONTROL Save]** quando terminar.

Dependendo do tipo de atividade selecionada, as opções variam:

### Metodologia de contagem

Selecione a metodologia desejada:

* Visitantes
* Visitas
* Impressões de atividade

### Controle

Selecione a experiência de controle a ser usada ao calcular e comparar o aumento.

### Ambiente {#environment}

Selecione o ambiente (grupo de hosts) a ser usado para o relatório. Para obter mais informações, consulte [Hosts](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

>[!NOTE]
>
>Se sua organização estiver usando o [Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/landing/home.html){target=_blank} (AEP) para enviar dados de métricas para [!DNL Target], o ambiente na sequência de dados do AEP deve corresponder ao ambiente nas configurações de relatório do [!DNL Target].

### Redefinir dados do relatório

Clique em [!UICONTROL Reset Report Data]. Redefina os dados de relatórios para remover os dados antigos. Os visitantes atuais permanecem na atividade.  Esta opção está disponível somente para aqueles com [!UICONTROL Approver] permissões.

>[!IMPORTANT]
>
>Essa é uma ação permanente que não pode ser desfeita.

Excluir valores extremos

A opção [!UICONTROL Exclude Extreme Values] se aplica somente a atividades com métricas do tipo receita e envolvimento. Para obter mais informações, consulte [Exceto pedidos extremos](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

## Baixar {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Clique no ícone **[!UICONTROL Download]** ( ![Ícone de download](/help/main/assets/icons/Download.svg) ) para baixar dados de relatório em um formato [!DNL .csv] para permitir uma importação rápida para Excel, Access ou outros programas de análise de dados.

Para obter mais informações, consulte [Fazendo download de dados em um arquivo CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md).

## Atualizar {#section_E203729F2F314DF3856D2EE67C60B370}

Clique no ícone **[!UICONTROL Refresh]** ( ![Atualizar ícone](/help/main/assets/icons/Refresh.svg) ) para atualizar a tabela e a exibição em gráfico de um relatório sem atualizar a página inteira, sua configuração ou seu intervalo de datas.

## Mais opções {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

Clique no ícone **[!UICONTROL More Options]** ( ![ícone de Mais Opções](/help/main/assets/icons/MoreSmallListVert.svg) ) para acessar as opções [!UICONTROL Save as New] e [!UICONTROL Delete].

## Exibir opções

É possível exibir o relatório em vários formatos, dependendo do tipo de atividade. Selecione a opção desejada.

* **Exibição de tabela**: clique no ícone **[!UICONTROL Table View]** ( ![Exibição de tabela](/help/main/assets/icons/Table.svg) ) para exibir o relatório como uma tabela.
* **Exibição em gráfico**: clique no ícone **[!UICONTROL Graph View]** ( ![Exibição em gráfico](/help/main/assets/icons/GraphTrend.svg) ) para exibir o relatório como um gráfico.
* **Segmentos automatizados**:(Disponível somente para atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] (AT).) Clique no ícone **[!UICONTROL Automated Segments] ( ![Ícone de Segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) para exibir o [Relatório de segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).
* **Atributos Importantes**: (Disponível somente para atividades de [!DNL Automated Personalization] (AP) e [!UICONTROL Auto-Target] (AT).) Clique no ícone **[!UICONTROL Important Attributes]** ( ![Atributos importantes](/help/main/assets/icons/ViewList.svg) ) para exibir o [relatório de Atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Média de aumento, Limites de aumento e Intervalo de confiança {#section_0D87615B1D3344B3858BA494EEBC16FB}

Os relatórios incluem vários pontos de dados e representações de visualização que entendem os limites de aumento e o nível de confiança associados à sua atividade. Isso ajuda você a determinar um vencedor com mais precisão.

Para obter mais informações, consulte [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

Considere o seguinte:

* Disponível somente ao exibir relatórios em [!UICONTROL Table View].
* Este recurso não está disponível para atividades que usam o [Analytics como fonte de relatórios (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Contribuição de localização  {#section_5832F126AC114AE1ABFFF4D9B904393B}

Clique no ícone de [[!UICONTROL Location Contribution]](/help/main/c-reports/multivariate-test-reports/location-contribution-report.md) ( ![Contribuição de localização](/help/main/assets/icons/LocationContribution.svg) ) para que o relatório mostre a contribuição por localização para as atividades de Teste multivariado (MVT).

## Experiências {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

Disponível somente ao exibir o relatório em [!UICONTROL Graph View].

Marque ou desmarque as experiências à esquerda do gráfico para exibir ou ocultar as experiências correspondentes no gráfico.

## Média móvel  {#section_59066693158C4433B87D07402C2BC6CD}

Disponível somente ao exibir o relatório em [!UICONTROL Graph View].

&quot;Média de execução&quot; reflete as conversões cumulativas (do início da janela de relatórios para a data representada no gráfico) divididas pelos visitantes cumulativos.

Selecione a exibição de gráfico desejada:

* Média móvel
* Executar aumento médio
* Diariamente
* Aumento diário

O nome dessa lista suspensa varia dependendo da exibição selecionada, mas será uma das exibições listadas acima.

## Metodologia de contagem {#section_01B0ED5665C74AE1AE97259800190C3E}

Disponível somente ao exibir o relatório em [!UICONTROL Graph View].

É possível escolher a metodologia de contagem de gráficos nos relatórios. Observe que isso não é suportado para atividades de [!UICONTROL Automated Personalization] (AP).

Para acessar a opção [!UICONTROL Counting Methodology], ao exibir um relatório em modo de gráfico, clique na lista suspensa **[!UICONTROL My Primary Goal]** e selecione a metodologia de contagem.

A metodologia de contagem será a mesma que a selecionada na caixa de diálogo [!UICONTROL Settings], descrita acima.

Por padrão, o gráfico é representado no modo [!UICONTROL Daily].

Você pode alterar o modo clicando na lista suspensa [!UICONTROL Daily] e selecionando uma opção cumulativa.

>[!NOTE]
>
>O nome dessa lista suspensa varia dependendo do modo selecionado.

Há quatro modos para [!UICONTROL Auto-Target] atividades: [!UICONTROL Daily Control], [!UICONTROL Daily Targeted], [!UICONTROL Cumulative Control] e [!UICONTROL Cumulative Targeted].

A seguir, a ordem padrão na qual o gráfico é criado:

* **[!UICONTROL A/B Test](incluindo [!UICONTROL Auto-Allocate] e [!UICONTROL Automated Personalization])**: Ordem de criação da experiência, em ordem decrescente.
* **[!UICONTROL Experience Targeting](XT)**: ordem das experiências na atividade.
* **[!UICONTROL Multivariate Test](MVT)**: ordem alfabética por nome de experiência.
* **[!UICONTROL Recommendations]**: Ordem de criação da experiência, em ordem decrescente.

Ao trabalhar com as opções [!UICONTROL Counting Methodology], considere as seguintes limitações:

* Para [[!UICONTROL Auto-Target] atividades](/help/main/c-activities/auto-target/auto-target-to-optimize.md), não há opção para selecionar &quot;Visitantes&quot; como a metodologia de contagem. [!UICONTROL Auto-Target] é o único tipo de atividade que você não pode plotar por visitantes.
* Para atividades que usam o [Analytics como fonte de relatórios (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md), não é possível plotar Visitante, Visita ou Impressão cumulativamente.

## Trabalhar com gráficos com mais de 16 experiências na atividade

Se uma atividade tem menos de 16 experiências, cada experiência é representada em uma cor diferente no gráfico.

Se uma atividade tiver mais de 16 experiências, as linhas coloridas das primeiras 16 são exibidas no gráfico. As experiências restantes estão cinzas no painel Experiências à esquerda e nenhuma linha de gráfico correspondente é exibida no gráfico. As linhas para somente 16 experiências podem ser mostradas em qualquer momento.

Se você passa o cursor do mouse sobre as experiências em cinza, uma nova linha de gráfico cinza, correspondente à tais experiências, é exibida temporariamente no gráfico. Para exibir em cores a linha de gráfico de uma experiência cinza, você pode desmarcar uma experiência colorida, ao clicar no nome dela, e, em seguida, selecionar a experiência em cinza desejada ao clicar no nome dela.

O gráfico exibe as linhas para as primeiras 16 experiências (algumas se sobrepõem, então parece que há menos de 16 linhas). O ponto colorido no painel Experiências à esquerda, perto de cada nome da experiência, indica que a linha do gráfico da experiência é exibida na cor correspondente.

Se você faz a rolagem no painel Experiência, observará que os nomes de das experiências 17 até 26 estão em cinza, conforme mostrado na ilustração a seguir:

Se você passa o cursor do mouse sobre uma experiência em cinza, uma nova linha de gráfico cinza, correspondente à tal experiência, é exibida temporariamente no gráfico.

Pressuponha que você deseje exibir a linha de gráfico para a Experiência R e não quer ver a linha para a Experiência P. É possível clicar no nome da Experiência P para desmarcá-la e, em seguida, clicar no nome da Experiência R para selecioná-la, conforme mostrado a seguir:
