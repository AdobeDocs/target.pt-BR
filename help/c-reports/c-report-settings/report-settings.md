---
description: Informações para ajudar a definir os elementos que você quer que apareçam em seu relatório. As definições de relatório podem ser salvas para uso posterior.
keywords: Target, relatórios, configurações de relatório, predefinição, predefinição de direcionamento, métrica, público-alvo, intervalo de datas, configurações, download, exibição de tabela, exibição em gráfico, elevação média, elevação, limite de elevação, intervalo de confiança, confiança, contribuição de localização, média de execução, metodologia de contagem
seo-description: Informações para ajudar a definir os elementos que você quer que apareçam em seu relatório. As definições de relatório podem ser salvas para uso posterior.
seo-title: Configurações do relatório
solution: Target
title: Configurações do relatório
topic: Premium
uuid: c3463f0d-8f09-4be2-9c85-f933578cce50
translation-type: tm+mt
source-git-commit: 3325da8e4c0d67ba9b882554f225e00e97c735cc

---


# Configurações do relatório{#report-settings}

Informações para ajudar a definir os elementos que você quer que apareçam em seu relatório. As definições de relatório podem ser salvas para uso posterior.

Para exibir um relatório, clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista e na guia **Relatórios[!UICONTROL .]**

![Interface do usuário do relatório](/help/c-reports/c-report-settings/assets/report_ui-new.png)

## Predefinição do Target {#section_51F67341465045BEB4F1A2FB638A8EB1}

Você pode salvar até dez predefinições diferentes de um relatório de atividade individual, após configurá-lo como desejado (métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante). Todos os usuários do Target podem exibir, editar e excluir as diversas predefinições, independentemente de quem as criou.

Você também pode configurar um relatório de atividade individual, como desejado, e depois salvar essa configuração como sua predefinição padrão/favorita. A partir de agora, esta será a exibição apresentada sempre que você visualizar o relatório dessa atividade.

**Criar uma predefinição ou uma predefinição padrão**

1. Configure o relatório de atividade como desejado (métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante).
1. Perto de **[!UICONTROL Predefinição do Target]**, clique no ícone de três elipses verticais &gt; **[!UICONTROL Salvar como novo]**.

   ![Predefinição de relatório](/help/c-reports/c-report-settings/assets/report_preset-new.png)

   A caixa de diálogo Nova predefinição é exibida:

   ![Caixa de diálogo Nova predefinição](/help/c-reports/c-report-settings/assets/report_preset_dialog-new.png)

1. Revise as informações nas seções Filtros e Configurações para garantir que o relatório esteja configurado como desejado e especifique o **[!UICONTROL Nome de predefinição]** (até 50 caracteres).
1. (Condicional) Se desejar que isso seja a exibição de relatório padrão/favorita, deslize o botão **[!UICONTROL Definir isto como padrão]para a posição Ativado.**
1. Clique em **[!UICONTROL Salvar]**.

**Selecione uma predefinição diferente**

Selecione a predefinição desejada na lista suspensa **[!UICONTROL Predefinição do Target].**

![Lista suspensa predefinida](/help/c-reports/c-report-settings/assets/report_preset_drop-down-new.png)

**Editar uma predefinição**

1. Selecione a predefinição que deseja editar.
1. Edite a configuração do relatório como desejado (métricas, intervalos de datas, públicos-alvo, configurações avançadas e assim por diante).

   Depois de clicar em [!UICONTROL Salvar], após a edição da configuração do relatório, um asterisco ( * ) será exibido depois do nome predefinido para indicar que a predefinição foi alterada, como mostrado abaixo:

   ![Predefinição de relatório com asterisco](/help/c-reports/c-report-settings/assets/report_preset_asterisk-new.png)

1. Clique no ícone de três elipses verticais &gt; **[!UICONTROL Salvar como novo]para criar uma nova predefinição.**

   Ou

   Clique no ícone de três elipses verticais &gt; **[!UICONTROL Atualizar]para atualizar a predefinição atual.**

   ![Atualização padrão do relatório](/help/c-reports/c-report-settings/assets/report_preset_update-new.png)

**Excluir uma predefinição**

1. Selecione a predefinição que deseja excluir.
1. Clique no ícone de três elipses verticais &gt; **[!UICONTROL Excluir]**.

   ![Excluir padrão do relatório](/help/c-reports/c-report-settings/assets/report_preset_delete-new.png)

1. Clique novamente em **[!UICONTROL Excluir]para confirmar a exclusão.**

**Tratamento de erros predefinidos**

Alertas e mensagens dentro de relatórios informam se uma predefinição se tornar inválida. O alerta ou a mensagem instrui a escolher outro público-alvo, métrica, grupo de hosts ou experiência para tornar uma predefinição válida.

A lista a seguir descreve algumas das situações que podem fazer com que uma predefinição se torne inválida:

* Um público-alvo do relatório foi removido da atividade, mas é referenciado na definição predefinida.
* Uma (ou mais) métrica foi excluída, mas referenciada na definição predefinida. Por exemplo, você pode excluir uma ou mais métricas da atividade e, em seguida, adicionar novas métricas.
* Um (ou mais) grupo de hosts (ambiente) não existe, mas é referenciado na definição predefinida.
* Uma (ou mais) experiência foi excluída depois que a predefinição foi criada, mas é referenciada na definição predefinida.
* Uma predefinição é semanticamente inválida, pois as entidades referenciadas ainda existem, mas foram atualizadas de forma a alterar a definição semântica da predefinição. Por exemplo, suponha que você crie inicialmente uma predefinição chamada &quot;Receita no Chrome&quot;. Posteriormente, você atualiza a atividade para medir a Métrica de conversão, em vez da Receita. Esta atualização para a definição de atividade invalidou a definição predefinida semanticamente.

## Métrica de relatório {#section_894ABD7148244806B7CE556EBBA2AD62}

Clique na lista suspensa **[!UICONTROL Métrica do relatório]** para selecionar outra [métrica de sucesso](../../c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) ou várias métricas para exibir no gráfico.

Por padrão, a métrica principal é determinada na configuração de métricas de sucesso ao criar a atividade. Se você alterar a configuração e salvar novamente a atividade, a métrica principal da geração de relatórios será atualizada.

Para obter mais informações sobre a seleção de várias métricas para visualização nos relatórios, consulte [Exibir várias métricas em um relatório](../../c-reports/c-report-settings/view-multiple-metrics.md#concept_9E3C3F6F3EC1412FAF252975AC0720B7).

## Público-alvo {#section_70926EB4618945D9AFF2B0564FF3717B}

Clique na lista suspensa [!UICONTROL Público] para alterar o [público](../../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522) exibido no relatório.

Para obter mais informações, consulte [Públicos](../../c-target/target.md#concept_A782F8481A5041EBA75103CB26376522).

## Intervalo de datas {#section_A410A768403C4E01891F95CB357E63ED}

A caixa Intervalo de datas exibe o intervalo de datas atual do relatório. Clique no ícone suspenso para exibir um calendário que permite alterar o intervalo de datas do relatório.

![Calendário](/help/c-reports/c-report-settings/assets/date_range-new.png)

Selecione as datas **[!UICONTROL Iniciais]** e **[!UICONTROL Finais]** para o relatório. Você também pode usar as caixas de seleção **[!UICONTROL Do início da atividade]** e **Até o final da atividade[!UICONTROL .]**

Clique em **[!UICONTROL Personalizar datas]** para selecionar intervalos de datas predefinidos: Últimos 7 dias, Últimos 15 dias ou Últimos 30 dias. Esses intervalos de datas predefinidos são intervalos acumulados. Se a data de início for menor do que o número de dias escolhido, o calendário mostrará o intervalo desde a data de início, mas acumulará quando a data de início se tornar mais anterior do que o número de dias escolhido conforme a duração da atividade aumenta.

Os relatórios têm as seguintes restrições de data:

* A data de início do relatório deve ficar dentro dos últimos dois anos.
* Os relatórios diários estão limitados a 100 dias.
* Os relatórios por hora estão limitados a 15 dias.

## Configurações {#section_D99CE462107D45CABE0960F820E1E972}

Clique no ícone de engrenagem para configurar o relatório e, em seguida, clique em **[!UICONTROL Salvar configurações]quando concluído.**

A ilustração a seguir mostra a caixa de diálogo Configurações para uma atividade A/B:

![Caixa de diálogo Configurações](/help/c-reports/c-report-settings/assets/ab_settings_dialog-new.png)

Dependendo do tipo de atividade selecionada, as opções variam:

* **Metodologia de contagem:** selecione a metodologia desejada:

   * Visitantes
   * Visitas
   * Impressões de atividade

* **Controle:** selecione a experiência de controle para usar o cálculo e comparar o incentivo.
* **Ambiente:** selecione o ambiente (grupo de host) para usar no relatório.  Para obter mais informações, consulte [Hosts](../../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
* **Redefinir dados de relatório:** redefina os dados de relatório para remover os dados antigos. Os visitantes atuais permanecerão na atividade.  Essa opção está disponível somente para os que tem permissões do aprovador.

   >[!IMPORTANT]
   >
   >Essa é uma ação permanente que não pode ser desfeita.

* **Excluir valores extremos:** a opção de alternar [!UICONTROL Excluir valores extremos] é aplicada apenas para atividades com métricas do tipo receita e envolvimento. Para obter mais informações, consulte [Exceto pedidos extremos](../../c-reports/c-report-settings/excluding-extreme-orders.md#task_2AE7743FFCDD466DAEEB720BE5F33DAA).

## Baixar {#section_77E65C50BAAF4AB79242DB3A8778ADEF}

Clique no ícone de download para baixar dados de relatório em um formato [!DNL .csv] para permitir uma importação rápida para Excel, Access ou outros programas de análise de dados. Para obter mais informações, consulte [Fazendo download de dados em um arquivo CSV](../../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75).

## Atualizar {#section_E203729F2F314DF3856D2EE67C60B370}

Clique em no ícone de Atualização para atualizar a tabela do relatório e a exibição em gráfico sem atualizar a página inteira, sua configuração ou seu intervalo de datas.

## Mais opções {#section_AB1B5C695D7045A0A0AC0E2698D2E7DE}

Clique no ícone de Mais opções (três elipses verticais) para acessar as opções [!UICONTROL Editar atividade] e [!UICONTROL Exibir URLs de experiência].

## Exibição em tabela {#section_4E7E75955A964847ADFF2C2314EC0F21}

Clique no ícone de **[!UICONTROL Exibição em tabela]para exibir o relatório como uma tabela.**

## Exibição em gráfico {#section_0D24B902A8D142468ADB7EEF1D941786}

Clique no ícone de **[!UICONTROL Exibição em gráfico]para exibir o relatório como um gráfico.**

## Média de aumento, Limites de aumento e Intervalo de confiança {#section_0D87615B1D3344B3858BA494EEBC16FB}

Os relatórios incluem vários pontos de dados e representações de visualização que entendem os limites de aumento e o nível de confiança associados à sua atividade. Isso ajuda você a determinar um vencedor com mais precisão.

Para obter mais informações, consulte [Média de aumento, Limites de aumento e Intervalo de confiança](../../c-reports/c-report-settings/average-lift-bounds-and-confidence-interval.md#topic_AFFDC672A8A34D028B100EF6BE5D8129).

Considere o seguinte:

* Disponível somente quando os relatórios estão sendo exibidos em Exibição em tabela.
* Este recurso não está disponível para atividades que usam o Analytics como fonte de relatórios (A4T).

## Contribuição de localização {#section_5832F126AC114AE1ABFFF4D9B904393B}

Clique no ícone de **[!UICONTROL Contribuição de localização]para que o relatório mostre a contribuição por localização.**

## Experiências {#section_3A450DE1FA7E43F0AAB73165EC3D1C34}

(Disponível somente ao exibir o relatório em gráficos)

Marque ou desmarque as experiências à esquerda do gráfico para exibir ou ocultar as experiências correspondentes no gráfico.

Se a ilustração a seguir, somente as experiências Padrão, Mid-Leste e Total forem exibidas no relatório. A experiência da Ásia está oculta no gráfico.

![Experiências](/help/c-reports/c-report-settings/assets/report_experiences-new.png)

## Média móvel {#section_59066693158C4433B87D07402C2BC6CD}

(Disponível somente ao exibir o relatório em gráficos)

Selecione a exibição de gráfico desejada:

* Média móvel
* Executar aumento médio
* Diariamente
* Aumento diário

![Média de geração de relatório](/help/c-reports/c-report-settings/assets/report_running_average-new.png)

>[!NOTE]
>
>O nome dessa lista suspensa varia dependendo da exibição selecionada, mas será uma das exibições listadas acima.

## Metodologia de contagem {#section_01B0ED5665C74AE1AE97259800190C3E}

(Disponível somente ao exibir o relatório em gráficos)

É possível escolher a metodologia de contagem de gráficos nos relatórios. Observe que isso não é suportado nas atividades de Personalização automatizada (AP).

Para acessar a opção de Metodologia de contagem, ao exibir um relatório em modo de gráfico, clique na lista suspensa **[!UICONTROL Minha meta primária], em seguida, selecione a metodologia de contagem.**

A metodologia de contagem será a mesma que a selecionada na caixa de diálogo [!UICONTROL Configurações], descrita acima.

![Metodologia de contagem](/help/c-reports/c-report-settings/assets/counting_methodology-new.png)

Como padrão, o gráfico é criado em modo [!UICONTROL Diário].

Você pode alterar o modo clicando na lista suspensa [!UICONTROL Diário], em seguida, selecionando [!UICONTROL Cumulativo].

![Cumulativo](/help/c-reports/c-report-settings/assets/counting_methodology_2-new.png)

>[!NOTE]
>
>O nome dessa lista suspensa varia dependendo do modo selecionado.

Há quatro modos para atividades de direcionamento automático: Controle diário, Direcionamento diário, Controle cumulativo e Direcionamento cumulativo.

A seguir, a ordem padrão na qual o gráfico é criado:

* Testes A/B (incluindo alocação automática e personalização automatizada): ordem da criação da experiência, em ordem descendente.
* Direcionamento de experiência (XT): ordem das experiências na atividade.
* Teste multivariado (MVT): ordem alfabética, por nome da experiência.
* Recommendations: ordem da criação da experiência, na ordem descendente.

À medida que usa as opções de Metodologia de contagem, considere os seguintes avisos:

* Para uma atividade de direcionamento automático, há a opção de selecionar &quot;Visitantes&quot; como a metodologia de contagem. O direcionamento automático é o único tipo de atividade que você não pode colocar em gráfico por visitantes.
* Para atividades que usam o Analytics, como fonte de geração de relatório (A4T), você não pode colocar em gráfico Visitante, Visita ou Impressão, de forma cumulativa.

**Utilização de gráficos com mais de 16 experiências na atividade**

Se uma atividade tem menos de 16 experiências, cada experiência é representada em uma cor diferente no gráfico.

Se uma atividade tiver mais de 16 experiências, as linhas coloridas das primeiras 16 são exibidas no gráfico. As experiências restantes estão cinzas no painel Experiências à esquerda e nenhuma linha de gráfico correspondente é exibida no gráfico. As linhas para somente 16 experiências podem ser mostradas em qualquer momento.

Se você passa o cursor do mouse sobre as experiências em cinza, uma nova linha de gráfico cinza, correspondente à tais experiências, é exibida temporariamente no gráfico. Para exibir em cores a linha de gráfico de uma experiência cinza, você pode desmarcar uma experiência colorida, ao clicar no nome dela, e, em seguida, selecionar a experiência em cinza desejada ao clicar no nome dela.

Como exemplo, a ilustração a seguir mostra um gráfico de atividade com 26 experiências:

![](assets/graph_1.png)

O gráfico exibe as linhas para as primeiras 16 experiências (algumas se sobrepõem, então parece que há menos de 16 linhas). O ponto colorido no painel Experiências à esquerda, perto de cada nome da experiência, indica que a linha do gráfico da experiência é exibida na cor correspondente.

Se você faz a rolagem no painel Experiência, observará que os nomes de das experiências 17 até 26 estão em cinza, conforme mostrado na ilustração a seguir:

![](assets/graph_2.png)

Se você passa o cursor do mouse sobre uma experiência em cinza, uma nova linha de gráfico cinza, correspondente à tal experiência, é exibida temporariamente no gráfico.

Pressuponha que você deseje exibir a linha de gráfico para a Experiência R e não quer ver a linha para a Experiência P. É possível clicar no nome da Experiência P para desmarcá-la e, em seguida, clicar no nome da Experiência R para selecioná-la, conforme mostrado a seguir:

![](assets/graph_3.png)

