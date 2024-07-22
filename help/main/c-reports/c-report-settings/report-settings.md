---
keywords: Target, relatórios, configurações de relatório, predefinição, predefinição de direcionamento, métrica, público-alvo, intervalo de datas, configurações, download, exibição de tabela, exibição em gráfico, elevação média, elevação, limite de elevação, intervalo de confiança, confiança, contribuição de localização, média de execução, metodologia de contagem
description: Saiba como definir configurações de relatório no Adobe Target, incluindo métricas, públicos, intervalos de datas e muito mais.
title: Como Definir Configurações De Relatório?
feature: Reports
exl-id: 337579d1-c678-43b6-9e80-b5abe159c2d3
source-git-commit: 7de7bb1b3bc70a559d41edece8cae2d388cb0dda
workflow-type: tm+mt
source-wordcount: '1892'
ht-degree: 55%

---

# Configurações do relatório

Informações para ajudar a definir os elementos que você deseja que apareçam em seu relatório no [!DNL Adobe Target]. As definições de relatório podem ser salvas para uso posterior.

Para exibir um relatório:

1. Clique em **[!UICONTROL Activities]** e depois clique na atividade desejada na lista.
1. Clique na guia **[!UICONTROL Reports]**.

   ![Interface de relatórios](/help/main/c-reports/c-report-settings/assets/report_ui-new.png)

## Predefinição do Target {#section_51F67341465045BEB4F1A2FB638A8EB1}

Você pode salvar até dez predefinições diferentes de um relatório de atividade individual, após configurá-lo como desejado (métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante). Todos os usuários do [!DNL Target] podem exibir, editar e excluir as várias predefinições, independentemente de quem as criou.

Você também pode configurar um relatório de atividade individual, como desejado, e depois salvar essa configuração como sua predefinição padrão/favorita. A partir de agora, esta será a exibição apresentada sempre que você visualizar o relatório dessa atividade.

### Criar uma predefinição ou uma predefinição padrão

1. Configure o relatório de atividade conforme desejado.

   As configurações disponíveis, incluindo métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante são explicadas abaixo.

1. Ao lado de **[!UICONTROL Target Preset]**, clique no ícone de três elipses verticais > **[!UICONTROL Save as New]**.

   ![Predefinição de relatório](/help/main/c-reports/c-report-settings/assets/report_preset-new.png)

   A caixa de diálogo Nova predefinição é exibida:

   ![Caixa de diálogo Nova predefinição](/help/main/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Revise as informações nas seções **[!UICONTROL Filters]** e **[!UICONTROL Settings]** para garantir que o relatório esteja configurado como desejado e especifique o **[!UICONTROL Preset Name]** (até 50 caracteres).
1. (Condicional) Se desejar que isso seja o modo de exibição de relatório padrão/favorito, deslize o botão **[!UICONTROL Set as default preset]** para a posição Ativado.
1. Clique em **[!UICONTROL Save]**.

### Selecionar uma predefinição diferente

Selecione a predefinição desejada na lista suspensa **[!UICONTROL Target Preset]**.

![Lista suspensa Predefinição](/help/main/c-reports/c-report-settings/assets/report_preset_drop-down-new.png)

### Editar uma predefinição

1. Selecione a predefinição que deseja editar.
1. Edite a configuração do relatório como desejado (métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante).

   Depois de clicar em [!UICONTROL Save], após a edição da configuração do relatório, um asterisco ( &#42; ) será exibido depois do nome predefinido para indicar que a predefinição foi alterada, como mostrado abaixo:

   ![Predefinição de relatório com asterisco](/help/main/c-reports/c-report-settings/assets/report_preset_asterisk-new.png)

1. Clique no ícone de três elipses verticais > **[!UICONTROL Save as New]** para criar uma nova predefinição.

   Ou

   Clique no ícone de três elipses verticais > **[!UICONTROL Update]** para atualizar a predefinição atual.

   ![Atualização do Padrão do relatório](/help/main/c-reports/c-report-settings/assets/report_preset_update-new.png)

### Excluir uma predefinição

1. Selecione a predefinição que deseja excluir.
1. Clique no ícone de três elipses verticais > **[!UICONTROL Delete]**.

   ![Exclusão Padrão do relatório](/help/main/c-reports/c-report-settings/assets/report_preset_delete-new.png)

1. Clique em **[!UICONTROL Delete]** novamente para confirmar a exclusão (predefinições excluídas não podem ser recuperadas).

### Tratamento de erros de predefinição

Alertas e mensagens dentro de relatórios informam se uma predefinição se tornar inválida. O alerta ou a mensagem instrui a escolher outro público-alvo, métrica, grupo de hosts ou experiência para tornar uma predefinição válida.

A lista a seguir descreve algumas das situações que podem fazer com que uma predefinição se torne inválida:

* Um público-alvo do relatório foi removido da atividade, mas é referenciado na definição predefinida.
* Uma (ou mais) métrica foi excluída, mas referenciada na definição predefinida. Por exemplo, você pode excluir uma ou mais métricas da atividade e, em seguida, adicionar novas métricas.
* Um (ou mais) grupo de hosts (ambiente) não existe, mas é referenciado na definição predefinida.
* Uma (ou mais) experiência foi excluída depois que a predefinição foi criada, mas é referenciada na definição predefinida.
* Uma predefinição é semanticamente inválida, pois as entidades referenciadas ainda existem, mas foram atualizadas de forma a alterar a definição semântica da predefinição. Por exemplo, suponha que você crie inicialmente uma predefinição chamada &quot;Receita no Chrome&quot;. Posteriormente, você atualiza a atividade para medir a Métrica de conversão, em vez da Receita. Essa atualização na definição de atividade invalida semanticamente a definição da predefinição.

## Métrica de relatório {#section_894ABD7148244806B7CE556EBBA2AD62}

Clique na lista suspensa **[!UICONTROL Report Metric]** para selecionar outra [métrica de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) ou várias métricas para exibir no gráfico.

Por padrão, a métrica principal é determinada na configuração de métricas de sucesso ao criar a atividade. Se você alterar a configuração e salvar novamente a atividade, a métrica principal da geração de relatórios será atualizada.

Para obter mais informações sobre como selecionar várias métricas para exibir em relatórios, consulte [Exibir Várias Métricas em um Relatório](/help/main/c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7).

## Público-alvo {#section_70926EB4618945D9AFF2B0564FF3717B}

Clique na lista suspensa [!UICONTROL Audience] para alterar o público exibido no relatório.

Para obter mais informações, consulte [Públicos-alvo](/help/main/c-target/target.md#concept_A782F8481A5041EBA75103CB26376522).

## Intervalo de datas {#section_A410A768403C4E01891F95CB357E63ED}

A caixa Intervalo de datas exibe o intervalo de datas atual do relatório. Clique no ícone suspenso para exibir um calendário que permite alterar o intervalo de datas do relatório.

![Calendário](/help/main/c-reports/c-report-settings/assets/date_range-new.png)

Selecione as novas datas **[!UICONTROL Start]** e **[!UICONTROL End]** para o relatório. Você também pode usar as caixas de seleção **[!UICONTROL From start of Activity]** e **[!UICONTROL Till end of Activity]**.

Clique em **[!UICONTROL Custom Dates]** para selecionar intervalos de datas predefinidos: Últimos 7 dias, Últimos 15 dias ou Últimos 30 dias. Esses intervalos de datas predefinidos são intervalos acumulados. Se a data de início for anterior ao número de dias escolhido, o calendário mostrará o intervalo da data de início, mas será aplicado assim que a data de início for anterior ao número de dias escolhido à medida que a duração da atividade aumentar.

Os relatórios têm as seguintes restrições de data:

* A data de início do relatório deve ficar dentro dos últimos dois anos.
* Os relatórios do grupo de ofertas são limitados a 99 dias a partir do dia atual.
* Os relatórios por hora estão limitados a 15 dias.

## Configurações {#section_D99CE462107D45CABE0960F820E1E972}

Para definir configurações de relatório:

1. Clique no ícone de engrenagem e faça as alterações desejadas (conforme explicado abaixo).
1. Clique em **[!UICONTROL Save]** quando terminar.

A ilustração a seguir mostra a caixa de diálogo Configurações para uma atividade A/B:

![Caixa de diálogo Configurações](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog-new.png)

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

Redefina os dados de relatórios para remover os dados antigos. Os visitantes atuais permanecerão na atividade.  Esta opção está disponível somente para aqueles com [!UICONTROL Approver] permissões.

>[!IMPORTANT]
>
>Essa é uma ação permanente que não pode ser desfeita.

### Excluir valores extremos

A opção [!UICONTROL Exclude Extreme Values] se aplica somente a atividades com métricas do tipo receita e envolvimento. Para obter mais informações, consulte [Exceto pedidos extremos](/help/main/c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

## Baixar {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Clique no ícone **[!UICONTROL Download]** para baixar dados de relatório em um formato [!DNL .csv] para permitir uma importação rápida para Excel, Access ou outros programas de análise de dados.

![Ícone de download](/help/main/c-reports/c-report-settings/assets/download-icon.png)

Para obter mais informações, consulte [Fazendo download de dados em um arquivo CSV](/help/main/c-reports/c-report-settings/downloading-data-in-csv-file.md).

## Atualizar {#section_E203729F2F314DF3856D2EE67C60B370}

Clique no ícone **[!UICONTROL Refresh]** para atualizar a tabela e a exibição em gráfico de um relatório sem atualizar a página inteira, sua configuração ou seu intervalo de datas.

## Mais opções {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

Clique no ícone Mais Opções (três elipses verticais) para acessar as opções [!UICONTROL Edit Activity] e [!UICONTROL View Experience URLs].

## Exibir opções

É possível exibir o relatório em vários formatos, dependendo do tipo de atividade. Selecione a opção desejada.

![Exibir ícones de opções](/help/main/c-reports/c-report-settings/assets/view-options.png)

* **Exibição de tabela**: clique no ícone **[!UICONTROL Table View]** para exibir o relatório como uma tabela.
* **Exibição em gráfico**: clique no ícone **[!UICONTROL Graph View]** para exibir o relatório como um gráfico.
* **Segmentos automatizados**:(Disponível apenas para atividades de Automated Personalization (AP) e Direcionamento automático (AT).) Clique no ícone **[!UICONTROL Automated Segments] para exibir o [Relatório de segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).
* **Atributos importantes**: (disponível somente para atividades de Automated Personalization (AP) e Direcionamento automático (AT).) Clique no ícone **[!UICONTROL Important Attributes] para exibir o [relatório de Atributos Importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Média de aumento, Limites de aumento e Intervalo de confiança {#section_0D87615B1D3344B3858BA494EEBC16FB}

Os relatórios incluem vários pontos de dados e representações de visualização que entendem os limites de aumento e o nível de confiança associados à sua atividade. Isso ajuda você a determinar um vencedor com mais precisão.

Para obter mais informações, consulte [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

Considere o seguinte:

* Disponível somente quando os relatórios estão sendo exibidos em Exibição em tabela.
* Este recurso não está disponível para atividades que usam o [Analytics como fonte de relatórios (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Contribuição de localização  {#section_5832F126AC114AE1ABFFF4D9B904393B}

Clique no ícone **[!UICONTROL Location Contribution]** para que o relatório mostre a contribuição por localização.

## Experiências {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

(Disponível somente ao exibir o relatório em gráficos)

Marque ou desmarque as experiências à esquerda do gráfico para exibir ou ocultar as experiências correspondentes no gráfico.

Na ilustração a seguir, somente as experiências Padrão, Centro-este e Total são exibidas no relatório. A experiência na Ásia está oculta no gráfico.

![Experiências](/help/main/c-reports/c-report-settings/assets/report_experiences-new.png)

## Média móvel  {#section_59066693158C4433B87D07402C2BC6CD}

(Disponível somente ao exibir o relatório em gráficos)

&quot;Média de execução&quot; reflete as conversões cumulativas (do início da janela de relatórios para a data representada no gráfico) divididas pelos visitantes cumulativos.

Selecione a exibição de gráfico desejada:

* Média móvel
* Executar aumento médio
* Diariamente
* Aumento diário

![Média de execução do relatório](/help/main/c-reports/c-report-settings/assets/report_running_average-new.png)

O nome dessa lista suspensa varia dependendo da exibição selecionada, mas será uma das exibições listadas acima.

## Metodologia de contagem {#section_01B0ED5665C74AE1AE97259800190C3E}

(Disponível somente ao exibir o relatório em gráficos)

É possível escolher a metodologia de contagem de gráficos nos relatórios. Observe que isso não é suportado para atividades de [!UICONTROL Automated Personalization] (AP).

Para acessar a opção [!UICONTROL Counting Methodology], ao exibir um relatório em modo de gráfico, clique na lista suspensa **[!UICONTROL My Primary Goal]** e selecione a metodologia de contagem.

A metodologia de contagem será a mesma que a selecionada na caixa de diálogo [!UICONTROL Settings], descrita acima.

![Metodologia de contagem](/help/main/c-reports/c-report-settings/assets/counting_methodology_2-new.png)

Por padrão, o gráfico é representado no modo [!UICONTROL Daily].

Você pode alterar o modo clicando na lista suspensa [!UICONTROL Daily] e selecionando uma opção cumulativa.

![Cumulativo](/help/main/c-reports/c-report-settings/assets/counting_methodology-new.png)

>[!NOTE]
>
>O nome dessa lista suspensa varia dependendo do modo selecionado.

Há quatro modos para atividades de direcionamento automático: Controle diário, Direcionamento diário, Controle cumulativo e Direcionamento cumulativo.

A seguir, a ordem padrão na qual o gráfico é criado:

* **Testes A/B (incluindo Alocação automática e Automated Personalization)**: ordem da criação da experiência, em ordem decrescente.
* **Direcionamento de experiência (XT)**: ordem das experiências na atividade.
* **Teste multivariado (MVT)**: em ordem alfabética por nome de experiência.
* **Recommendations**: ordem da criação da experiência, em ordem decrescente.

À medida que usa as opções de Metodologia de contagem, considere os seguintes avisos:

* Para [atividades de Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md), não há opção para selecionar &quot;Visitantes&quot; como a metodologia de contagem. O direcionamento automático é o único tipo de atividade que você não pode colocar em gráfico por visitantes.
* Para atividades que usam o [Analytics como fonte de relatórios (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md), não é possível plotar Visitante, Visita ou Impressão cumulativamente.

## Trabalhar com gráficos com mais de 16 experiências na atividade

Se uma atividade tem menos de 16 experiências, cada experiência é representada em uma cor diferente no gráfico.

Se uma atividade tiver mais de 16 experiências, as linhas coloridas das primeiras 16 são exibidas no gráfico. As experiências restantes estão cinzas no painel Experiências à esquerda e nenhuma linha de gráfico correspondente é exibida no gráfico. As linhas para somente 16 experiências podem ser mostradas em qualquer momento.

Se você passa o cursor do mouse sobre as experiências em cinza, uma nova linha de gráfico cinza, correspondente à tais experiências, é exibida temporariamente no gráfico. Para exibir em cores a linha de gráfico de uma experiência cinza, você pode desmarcar uma experiência colorida, ao clicar no nome dela, e, em seguida, selecionar a experiência em cinza desejada ao clicar no nome dela.

Como exemplo, a ilustração a seguir mostra um gráfico de atividade com 26 experiências:

![gráfico_1 imagem](assets/graph_1.png)

O gráfico exibe as linhas para as primeiras 16 experiências (algumas se sobrepõem, então parece que há menos de 16 linhas). O ponto colorido no painel Experiências à esquerda, perto de cada nome da experiência, indica que a linha do gráfico da experiência é exibida na cor correspondente.

Se você faz a rolagem no painel Experiência, observará que os nomes de das experiências 17 até 26 estão em cinza, conforme mostrado na ilustração a seguir:

![imagem graph_2](assets/graph_2.png)

Se você passa o cursor do mouse sobre uma experiência em cinza, uma nova linha de gráfico cinza, correspondente à tal experiência, é exibida temporariamente no gráfico.

Pressuponha que você deseje exibir a linha de gráfico para a Experiência R e não quer ver a linha para a Experiência P. É possível clicar no nome da Experiência P para desmarcá-la e, em seguida, clicar no nome da Experiência R para selecioná-la, conforme mostrado a seguir:

![imagem graph_3](assets/graph_3.png)
