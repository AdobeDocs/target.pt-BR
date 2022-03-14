---
keywords: analytics para target; a4t; analytics como fonte de relatórios; analytics
description: Saiba como usar o Analytics para [!DNL Target] (A4T). O A4T fornece acesso aos relatórios do Analytics para [!DNL Target] atividades que usam métricas do Analytics e segmentos de público-alvo.
title: Como uso os relatórios no A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 31%

---

# Relatórios do A4T

Usando [!DNL Adobe Analytics] como sua fonte de relatórios para [!DNL Adobe Target] (A4T) fornece acesso a [!DNL Analytics] relatórios para seus [!DNL Target] atividades.

Você pode exibir relatórios de suas atividades em [!DNL Analytics] e [!DNL Target].

Para obter as práticas recomendadas de relatório usando [!DNL Analytics] para [!DNL Target], [visitar esta Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Visão geral {#section_035A62D65608423285D8A5A54731E2C5}

Ambos [!DNL Analytics] e [!DNL Target] Os relatórios avaliam os participantes (as pessoas que entram nos testes), em vez dos visitantes do site.

Toda vez que um visitante vê o conteúdo da atividade na página, [!DNL Target] faz uma chamada direta de servidor para servidor [!DNL Analytics], incluindo qual atividade e experiência o visitante visualizou. [!DNL Target] também chama [!DNL Analytics] sempre que a conversão for feita. [!DNL Analytics] adiciona a conversão como um novo [!DNL Analytics] chamado de &quot;Conversão de atividade&quot;, que é rastreado junto com outros dados coletados por [!DNL Analytics].

Quando a variável [!UICONTROL Selecionar] é usada e você classifica em *Participantes*, então somente as experiências que receberam participantes durante o período selecionado são exibidas nos relatórios.

>[!NOTE]
>
>Relatórios fornecidos por [!DNL Target] têm uma latência de quatro minutos. Para atividades fornecidas pelo A4T, em [!DNL Target] e [!DNL Analytics] relatórios, pode levar até 24 horas após a atividade ser inicialmente salva, antes que os dados do relatório possam ser detalhados por experiências. Os dados coletados nas primeiras 24 horas ainda são precisos e são atribuídos à experiência correta.

## Relatórios no Analytics  {#analytics}

Em [!DNL Analytics], há várias dimensões e métricas disponibilizadas após a ativação da integração A4T.

### Dimensões

* [!UICONTROL Analytics para Target] - A ID principal transmitida pela integração. O formato dessa dimensão é `Activity ID:Experience ID:3rd ID`. As dimensões abaixo são classificações dessa dimensão.
* [!UICONTROL Atividades do Target]
* [!UICONTROL Experiências target]
* [!UICONTROL Atividade do Target] > [!UICONTROL Experiência]
* [!UICONTROL 3º ID] - pode ser ignorado

### Métricas

* [!UICONTROL Impressões da atividade] - Corresponde à variável [!UICONTROL Participantes] no [!DNL Target] relatório.
* [!UICONTROL Conversões de atividade] - Corresponde à variável [!UICONTROL Conversões personalizadas] no [!DNL Target] relatório.

Em [!DNL Analysis Workspace], use o [!UICONTROL Analytics para Target] painel para analisar seu [!DNL Target] atividades e experiências com incentivo e confiança. Para obter mais informações, consulte [Painel Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=pt-BR) no *Guia de ferramentas do Analytics*.

>[!IMPORTANT]
>
>Se o seu [!UICONTROL Atividades do Target] relatório em [!DNL Analytics] lista &quot;não especificado&quot; em vez de listar suas atividades, uma atualização é necessária para sua conta provisionada. Entre em contato com o Atendimento ao cliente para resolver esse problema.

Para obter informações e exemplos detalhados, abra o [Analytics &amp; Target: Práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, fornecido pela Adobe Experience League.

## Relatórios em [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

When [!DNL Analytics] é usado como fonte de relatórios, relatórios em [!DNL Target] mostrar os dados coletados de [!DNL Analytics]. O relatório difere um pouco de outro [!DNL Target] relatórios:

* O [!UICONTROL Públicos-alvo] mostra os públicos-alvo disponíveis para sua [!DNL Analytics] conjunto de relatórios.
* O [!UICONTROL Métrica] lista mostra todas as métricas disponíveis por [!DNL Analytics].

   Todas as métricas estão disponíveis, incluindo as métricas personalizadas ou calculadas que estão integradas no [!DNL Analytics].

   Qualquer número que aumente é mostrado como positivo no relatório, mesmo quando um aumento é indesejado. Por exemplo, mesmo que você queira uma taxa de rejeição mais baixa, a taxa de rejeição mais alta é mostrada como vencedora com o maior incentivo. Considere essas métricas de métricas semelhantes, bem como sua preferência por diminuir ou aumentar os números, ao tomar decisões baseadas nos relatórios.

Você pode aplicar a métrica ou o público-alvo ao relatório em [!DNL Target] após o início da atividade ou mesmo após a conclusão do teste. Você não precisa saber exatamente o que deseja medir com antecedência.

Clique para exibir o relatório completo [!DNL Analytics] diretamente da página do relatório de atividades.

## Criação da atividade {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante a criação da atividade, você deve especificar uma meta para a atividade na página [!UICONTROL Configurações]. Esta meta torna-se a métrica padrão para o relatório e é sempre listada como a primeira opção no seletor de métricas. Não é possível selecionar os segmentos para os relatórios, como você faria para uma atividade padrão do Target. Um teste com [!DNL Analytics] uses [!DNL Adobe Analytics] em vez de [!DNL Target] públicos-alvo.

## Realização de cálculos offline para Analytics for Adobe Target (A4T) {#section_33A97A691F3A45D497DAF57A844388F0}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics].

Para obter mais informações, consulte [Execução de cálculos offline no Analytics for Target (A4T)](/help/main/c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B) em.
