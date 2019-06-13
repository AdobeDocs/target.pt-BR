---
description: Usar o Analytics como sua fonte de geração de relatórios para o Target (A4T) dá a você acesso aos relatórios do Analytics de suas atividades do Target.
keywords: analytics para target; a4T; análise como fonte de relatórios
seo-description: Usar o Analytics como sua fonte de geração de relatórios para o Target (A4T) dá a você acesso aos relatórios do Analytics de suas atividades do Target.
seo-title: Relatórios do A4T
solution: Target
subtopic: Teste multivariado
title: Relatórios do A4T
topic: Padrão
uuid: bd3a7fa4-ba45-4ea3-81b6-fc2584831ce4
translation-type: ht
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Relatórios do A4T{#a-t-reporting}

Usar o Analytics como sua fonte de geração de relatórios para o Target (A4T) dá a você acesso aos relatórios do Analytics de suas atividades do Target.

Você pode exibir os relatórios de suas atividades no Analytics e Target Standard/Premium.

Para obter as práticas recomendadas de relatório usando o Analytics para Target, [visite esta Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Visão geral {#section_035A62D65608423285D8A5A54731E2C5}

O Analytics e Target informam a medição dos participantes (as pessoas que entram nos testes), em vez dos visitantes no site.

Cada vez que um visitante vê o conteúdo de atividade na página, o Target faz uma chamada direta de servidor para o Analytics, incluindo qual atividade e experiência foram visualizadas pelo visitante. O Target também chama o Analytics sempre que a conversão é feita. O Analytics acrescenta a conversão como um novo evento específico do Analytics chamado &quot;Atividade de conversão&quot;, que é traçado junto com outros dados coletados pelo Analytics.

Quando você classifica como *Participantes* usando a operação Selecionar, apenas experiências que receberam os participantes durante o período selecionado serão exibidos nos relatórios.

>[!NOTE]
>
>Os relatórios fornecidos pelo Target têm uma latência de quatro minutos. Para atividades fornecidas pelo A4T, nos relatórios do Target e Analytics, pode demorar até 24 horas após a atividade ser inicialmente salva, antes que os dados do relatório possam ser detalhados por experiências. Os dados coletados nas primeiras 24 horas ainda são precisos e são atribuídos à experiência correta.

## Relatórios no Analytics {#section_F6884872DC864AE7913587FAED4CD11C}

No Analytics, clique em **[!UICONTROL Target]** &gt; **[!UICONTROL Atividades do Target]** no menu à esquerda. No Target, os relatórios de atividade mostram automaticamente os dados do Analytics, métricas e segmentos. Os dados são exibidos nesses relatórios aproximadamente uma hora depois de serem coletados do site. Todas as métricas, os públicos-alvo e os valores nos relatórios vêm do conjunto de relatórios selecionado ao configurar a atividade.

No Analytics, use o relatório de Atividades do Target para visualizar os resultados da sua atividade do Target. Os Relatórios do Test&amp;Target (Legacy) fornecem informações sobre suas integrações de página estilo plug-in antigas do Test&amp;Target e não incluem os dados do Analytics for Target. No relatório de Atividades, visualize as informações sobre as suas experiências do Target. Clique em **[!UICONTROL Métricas]** e selecione o tipo de métrica do **[!UICONTROL Target]**. Duas métricas estão disponíveis para o relatório:

* **Entradas de atividade:** corresponde ao número de Participantes no relatório do Target.
* **Conversões de atividade:** corresponde ao número de Conversões personalizadas no relatório do Target.

>[!NOTE]
>
>Os detalhes de incentivo e confiança do Target também estão disponíveis no Analytics. Para obter mais informações, consulte [Tipo de relatório de aumento e confiança do Target](https://marketing.adobe.com/resources/help/pt_BR/reference/report_target_lift_confidence.html) na documentação de produto do Adobe Analytics.

>[!IMPORTANT]
>
>Se o seu relatório de Atividades do Target no Analytics listar &quot;não especificado&quot;, em vez de listar suas atividades, é necessária uma atualização para a sua conta provisionada. Entre em contato com o Atendimento ao cliente para resolver esse problema.

## Relatórios no Target {#section_C0D1F17F88374B6690BF904D7B83B42E}

Quando o Analytics é usado como fonte de geração de relatórios, os relatórios no Target Standard mostram os dados coletados do Analytics. O relatório difere um pouco dos outros relatórios do Target Standard:

* A lista de Públicos-alvo mostra os públicos disponíveis para o conjunto de relatórios do Analytics.
* A lista de Métrica mostra todas as métricas disponíveis no Analytics.

   Todas as métricas estão disponíveis, incluindo as métricas personalizadas ou calculadas que estão integradas no Analytics.

   Esteja ciente de que qualquer número que aumente é mostrado como positivos no relatório, mesmo quando um aumento for realmente indesejado. Por exemplo, mesmo que você queira uma taxa de rejeição mais baixa, a taxa de rejeição mais alta é mostrada como vencedora com o maior incentivo. Considere essas métricas de métricas semelhantes, bem como sua preferência por diminuir ou aumentar os números, ao tomar decisões baseadas nos relatórios.

Você pode aplicar a métrica ou público-alvo ao relatório no Target após iniciar o teste ou mesmo após sua conclusão. Você não precisa saber exatamente o que deseja medir com antecedência.

Clique para exibir o relatório completo do Analytics diretamente da página de relatório da atividade.

## Relatórios na Analysis Workspace {#reports-in-analysis-workspace}

É possível usar a [!DNL Adobe Analysis Workspace] para pesquisar mais e visualizar os dados ou descobrir insights ocultos nas entrelinhas.

Para obter informações e exemplos detalhados, abra o [tutorial Analytics e Target: práticas recomendadas da Analysis](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido pelo Adobe Experience League.

## Criação da atividade {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante a criação da atividade, você deve especificar uma meta para a atividade na página [!UICONTROL Configurações]. Esta meta torna-se a métrica padrão para o relatório e é sempre listada como a primeira opção no seletor de métricas. Não é possível selecionar os segmentos para os relatórios, como você faria para uma atividade padrão do Target. Um teste com Analytics usa segmentos do Adobe Analytics, em vez de públicos-alvo do Target Standard.

## Realização de cálculos offline para Analytics for Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics].

Para obter mais informações, consulte [Execução de cálculos offline no Analytics for Target (A4T)](../../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B) em.
