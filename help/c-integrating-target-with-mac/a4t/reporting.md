---
keywords: analytics for target;a4t;analytics as the reporting source
description: Usar o Analytics como sua fonte de geração de relatórios para o Target (A4T) dá a você acesso aos relatórios do Analytics de suas atividades do Target.
title: Relatórios do A4T
feature: a4t reports
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '667'
ht-degree: 37%

---


# Relatórios do A4T{#a-t-reporting}

Usar [!DNL Analytics] como fonte de relatórios para [!DNL Target] (A4T) fornece acesso aos relatórios [!DNL Analytics] de [!DNL Target] atividades.

Você pode visualização relatórios para suas atividades em [!DNL Analytics] e [!DNL Target].

Para obter as práticas recomendadas do relatórios que usam [!DNL Analytics] para [!DNL Target], [visite esta página do Adobe Spark](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Visão geral {#section_035A62D65608423285D8A5A54731E2C5}

Os relatórios [!DNL Analytics] e [!DNL Target] avaliam os participantes (as pessoas que entram nos testes), em vez de visitantes no site.

Toda vez que um visitante vê o conteúdo da atividade na página, [!DNL Target] faz uma chamada direta de servidor para servidor para [!DNL Analytics], incluindo qual atividade e experiência o visitante viu. [!DNL Target] também chama  [!DNL Analytics] sempre que a conversão é feita. [!DNL Analytics] adiciona a conversão como um novo  [!DNL Analytics] evento específico chamado &quot;Conversão de Atividade&quot;, que é rastreado junto com outros dados coletados por  [!DNL Analytics].

Quando a operação [!UICONTROL Select] for usada e você classificar em *Participantes*, somente as experiências que receberam participantes durante o período selecionado serão exibidas nos relatórios.

>[!NOTE]
>
>Os relatórios alimentados por [!DNL Target] têm uma latência de quatro minutos. Para atividades ativadas por A4T, nos relatórios [!DNL Target] e [!DNL Analytics], pode levar até 24 horas após a atividade ser salva inicialmente antes que os dados do relatório possam ser detalhados por experiências. Os dados coletados nas primeiras 24 horas ainda são precisos e são atribuídos à experiência correta.

## Relatórios no Analytics   {#analytics}

Em [!DNL Analytics], há várias dimensões e métricas disponibilizadas depois que a integração A4T é ativada.

### Dimensões

* [!UICONTROL Analytics for Público alvo]  - a ID pai transmitida pela integração. O formato desta dimensão é `Activity ID:Experience ID:3rd ID`. As dimensões abaixo são classificações dessa dimensão.
* [!UICONTROL Atividades do Target]
* [!UICONTROL Experiências target]
* [!UICONTROL Atividade]  do público alvo >  [!UICONTROL Experiência]
* [!UICONTROL 3ª ID]  - pode ser ignorada

### Métricas

* [!UICONTROL Impressões]  de atividade - Corresponde ao número de   participantes no  [!DNL Target] relatório.
* [!UICONTROL Conversões]  de atividade - Corresponde ao número  [!UICONTROL Personalizado ] de Conversões no  [!DNL Target] relatório.

Em [!DNL Analysis Workspace], use o painel [!UICONTROL Analytics for Público alvo] para analisar as atividades e experiências [!DNL Target] com incentivo e confiança. Para obter mais informações, consulte [Painel do Analytics for Público alvo (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html) no *Guia de ferramentas do Analytics*.

>[!IMPORTANT]
>
>Se seu relatório [!UICONTROL Atividades do Público alvo] no [!DNL Analytics] lista &quot;não especificado&quot; em vez de listar suas atividades, uma atualização será necessária para sua conta provisionada. Entre em contato com o Atendimento ao cliente para resolver esse problema.

Para obter informações detalhadas e exemplos, abra o [Analytics &amp; Público alvo: Tutorial de práticas recomendadas para Análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido pela Adobe Experience League.

## Relatórios no Target   {#section_C0D1F17F88374B6690BF904D7B83B42E}

Quando [!DNL Analytics] é usado como a fonte do relatórios, os relatórios em [!DNL Target] mostram os dados coletados de [!DNL Analytics]. O relatório difere um pouco de outros relatórios [!DNL Target]:

* A lista [!UICONTROL Audiência] mostra as audiências disponíveis para o conjunto de relatórios [!DNL Analytics].
* A lista [!UICONTROL Metric] mostra todas as métricas disponíveis por meio de [!DNL Analytics].

   Todas as métricas estão disponíveis, incluindo as métricas personalizadas ou calculadas que estão integradas no [!DNL Analytics].

   Esteja ciente de que qualquer número que aumente é mostrado como positivos no relatório, mesmo quando um aumento for realmente indesejado. Por exemplo, mesmo que você queira uma taxa de rejeição mais baixa, a taxa de rejeição mais alta é mostrada como vencedora com o maior incentivo. Considere essas métricas de métricas semelhantes, bem como sua preferência por diminuir ou aumentar os números, ao tomar decisões baseadas nos relatórios.

Você pode aplicar a métrica ou a audiência ao relatório em [!DNL Target] depois que a atividade for iniciada, ou mesmo após a conclusão do teste. Você não precisa saber exatamente o que deseja medir com antecedência.

Clique para visualização o relatório completo [!DNL Analytics] diretamente da página de relatório de atividade.

## Criação da atividade {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante a criação da atividade, você deve especificar uma meta para a atividade na página [!UICONTROL Configurações]. Esta meta torna-se a métrica padrão para o relatório e é sempre listada como a primeira opção no seletor de métricas. Não é possível selecionar os segmentos para os relatórios, como você faria para uma atividade padrão do Target. Um teste com [!DNL Analytics] usa [!DNL Adobe Analytics] segmentos em vez de [!DNL Target] audiências.

## Realização de cálculos offline para o Analytics para Público alvo (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics].

Para obter mais informações, consulte [Execução de cálculos offline no Analytics for Target (A4T)](/help/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B) em.
