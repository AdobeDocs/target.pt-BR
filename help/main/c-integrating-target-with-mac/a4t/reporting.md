---
keywords: analytics para target;a4T;analytics como fonte de relatórios;analytics
description: Saiba como usar o Analytics for [!DNL Target] (A4T). O A4T fornece acesso aos relatórios do Analytics para [!DNL Target] atividades que usam métricas do Analytics e segmentos de público-alvo.
title: Como usar relatórios no A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1212'
ht-degree: 39%

---

# Relatórios do A4T

Usar o [!DNL Adobe Analytics] como sua fonte de relatórios para o [!DNL Adobe Target] (A4T) dá a você acesso aos relatórios do [!DNL Analytics] para suas atividades do [!DNL Target].

Você pode exibir relatórios para suas atividades em [!DNL Analytics] e [!DNL Target].

Para obter as práticas recomendadas de relatório usando o [!DNL Analytics] para [!DNL Target], [visite esta Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Visão geral {#section_035A62D65608423285D8A5A54731E2C5}

Os relatórios de [!DNL Analytics] e [!DNL Target] medem os participantes (as pessoas que entram nos testes), em vez dos visitantes do site.

Toda vez que um visitante visualiza o conteúdo da atividade na página, o [!DNL Target] faz uma chamada direta de servidor para servidor para [!DNL Analytics], incluindo qual atividade e experiência o visitante viu. [!DNL Target] também chama [!DNL Analytics] sempre que a conversão é feita. [!DNL Analytics] adiciona a conversão como um novo evento [!DNL Analytics] específico chamado &quot;Conversão de Atividade&quot;, que é rastreado junto com outros dados coletados por [!DNL Analytics].

Quando a operação [!UICONTROL Select] é usada e você classifica em *Participantes*, somente as experiências que receberam participantes durante o período selecionado são exibidas nos relatórios.

>[!NOTE]
>
>Os relatórios fornecidos por [!DNL Target] têm uma latência de quatro minutos. Para atividades viabilizadas pelo A4T, nos relatórios do [!DNL Target] e do [!DNL Analytics], pode levar até 24 horas após a atividade ser salva inicialmente para que os dados do relatório possam ser analisados por experiências. Os dados coletados nas primeiras 24 horas ainda são precisos e são atribuídos à experiência correta.

## Relatórios no Analytics  {#analytics}

No [!DNL Analytics], há várias dimensões e métricas disponibilizadas após a integração A4T ser habilitada.

### Dimensões

* [!UICONTROL Analytics for Target] - A ID do pai que é passada pela integração. O formato dessa dimensão é `Activity ID:Experience ID:3rd ID`. As dimensões abaixo são classificações dessa dimensão.
* [!UICONTROL Target Activities]
* [!UICONTROL Target Experiences]
* [!UICONTROL Target Activity] > [!UICONTROL Experience]
* [!UICONTROL 3rd ID] - pode ser ignorado

### Métricas

* [!UICONTROL Activity Impressions] - Corresponde ao número [!UICONTROL Entrants] no relatório [!DNL Target].
* [!UICONTROL Activity Conversions] - Corresponde ao número [!UICONTROL Custom Conversions] no relatório [!DNL Target].

No [!DNL Analysis Workspace], use o painel [!UICONTROL Analytics for Target] para analisar suas atividades e experiências do [!DNL Target] com incentivo e confiança. Para obter mais informações, consulte [Painel do Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=pt-BR) no *Guia de Ferramentas do Analytics*.

>[!IMPORTANT]
>
>Se o seu relatório do [!UICONTROL Target Activities] no [!DNL Analytics] lista &quot;não especificado&quot; em vez de listar suas atividades, será necessária uma atualização para sua conta provisionada. Entre em contato com o Atendimento ao cliente para resolver esse problema.

Para obter informações e exemplos detalhados, abra o [tutorial Analytics &amp; Target: práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/), fornecido pela Adobe Experience League.

## Relatórios em [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

Quando [!DNL Analytics] é usado como fonte de relatórios, os relatórios em [!DNL Target] mostram os dados coletados de [!DNL Analytics]. O relatório é um pouco diferente de outros [!DNL Target] relatórios:

* A lista [!UICONTROL Audiences] mostra os públicos-alvo disponíveis para o conjunto de relatórios [!DNL Analytics].
* A lista [!UICONTROL Metric] mostra cada métrica disponível até [!DNL Analytics].

  Todas as métricas estão disponíveis, inclusive as métricas personalizadas ou calculadas que estão integradas no [!DNL Analytics].

  Quaisquer números que aumentarem serão mostrados como positivos no relatório, mesmo quando um aumento for indesejado. Por exemplo, mesmo que você queira uma taxa de rejeição mais baixa, a taxa de rejeição mais alta é mostrada como vencedora com o maior incentivo. Considere essas métricas de métricas semelhantes, bem como sua preferência por diminuir ou aumentar os números, ao tomar decisões baseadas nos relatórios.

Você pode aplicar a métrica ou público-alvo ao relatório em [!DNL Target] após o início da atividade ou mesmo após a conclusão do teste. Você não precisa saber exatamente o que deseja medir com antecedência.

Clique para exibir o relatório [!DNL Analytics] completo diretamente na página do relatório de atividades.

## Criação da atividade {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante a criação da atividade, você deve especificar uma meta para a atividade na página [!UICONTROL Settings]. Esta meta torna-se a métrica padrão para o relatório e é sempre listada como a primeira opção no seletor de métricas. Não é possível selecionar os segmentos para os relatórios, como você faria para uma atividade padrão do Target. Um teste com [!DNL Analytics] usa [!DNL Adobe Analytics] segmentos em vez de [!DNL Target] públicos-alvo.

## Realização de cálculos offline para Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Você pode realizar cálculos offline para intervalos de confiança e confiança para A4T usando o arquivo do Excel [!DNL Target] [Concluir Calculadora de Confiança](/help/main/assets/complete_confidence_calculator.xlsx), mas isso requer uma etapa com exportações de dados em [!DNL Analytics].

Para o A4T, usamos um cálculo [Welch&#39;s t-test](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} para variáveis contínuas (em vez de métricas binárias). No Analytics, um visitante é sempre rastreado e todas as ações realizadas são contadas. Portanto, se o visitante comprar várias vezes ou visitar uma métrica de sucesso várias vezes, esses hits adicionais serão contados. Isso torna a métrica uma variável contínua. Para realizar o cálculo t-test de Welch, a &quot;soma dos quadrados&quot; é necessária para calcular a variância, que é usada no denominador da estatística t. [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explica os detalhes das fórmulas matemáticas usadas. A soma dos quadrados pode ser recuperada de [!DNL Analytics]. Para obter a soma dos dados dos quadrados, é necessário executar uma exportação no nível do visitante para a métrica para a qual você está otimizando, por um período de tempo de amostra.

Por exemplo, se estiver otimizando para exibições de página por visitante, você exportaria uma amostra do número total de exibições de página por visitante por um período especificado, talvez alguns dias (alguns milhares de pontos de dados são tudo de que você precisa). Você, então, elevaria ao quadrado de cada valor e somaria os totais (a ordem das operações é essencial aqui). Este valor de &quot;soma dos quadrados&quot; é então usado na Calculadora de confiança completa. Use a seção &quot;receita&quot; dessa planilha para esses valores.

**Para usar o recurso de exportação de dados do [!DNL Analytics] para fazer isso:**

1. Efetue logon no [!DNL Adobe Analytics].
1. Clique em **[!UICONTROL Tools]** > **[!UICONTROL Data Warehouse]**.
1. Na guia **[!UICONTROL Data Warehouse Request]**, preencha os campos.

   Para obter mais informações sobre cada campo, consulte &quot;Descrições do Data Warehouse&quot; em [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html?lang=pt-BR).

   | Campo | Instruções |
   |--- |--- |
   | Nome da solicitação | Especifique um nome para sua solicitação. |
   | Data de relatório | Especifique um período de tempo e granularidade.<br>Como prática recomendada, escolha não mais que uma hora ou um dia de dados para sua primeira solicitação.  Os arquivos do Data Warehouse demoram mais para processar quanto mais longo for o tempo solicitado, por isso, é sempre uma prática recomendada solicitar primeiro um pequeno período de tempo para garantir que o arquivo retorne o resultado esperado. Em seguida, vá para o Gerenciador de solicitações, duplique sua solicitação e solicite mais dados pela segunda vez. Além disso, se você alternar a granularidade para algo diferente de &quot;Nenhum&quot;, o tamanho do arquivo aumentará drasticamente.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Segmentos disponíveis | Aplique um segmento, se necessário. |
   | Detalhamentos | Selecione as dimensões desejadas: Padrão é pronto (OOTB), enquanto Personalizado inclui eVars e props. É recomendável usar &quot;ID de visitante&quot; se as informações no nível de ID de visitante forem necessárias, em vez de &quot;ID de visitante do Experience Cloud&quot;.<ul><li>ID do visitante é a ID final usada pelo Analytics. Ela será AID (se o cliente for legado) ou MID (se o cliente for novo ou tiver eliminado os cookies desde que o serviço de identificação de visitante do MC foi iniciado).</li><li>A ID de visitante da Experience Cloud só será definida para clientes novos ou com cookies eliminados desde que o serviço de ID de visitante do MC foi iniciado.</li></ul> |
   | Métricas | Selecione sua métrica desejada. O padrão é OOTB, enquanto o Personalizado inclui eventos personalizados. |
   | Visualização de Relatório | Revise suas configurações antes de agendar o relatório.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Agendar entrega | Digite um endereço de email para entregar o arquivo, nomeie o arquivo e selecione [!UICONTROL Send Immediately].<br>Observação: o arquivo pode ser entregue via FTP em [!UICONTROL Advanced Delivery Options]<br>![Agendar Entrega](/help/main/c-reports/assets/datawarehouse3.png). |

1. Clique em **[!UICONTROL Request this Report]**.

   A entrega do arquivo pode levar até 72 horas, dependendo da quantidade de dados solicitada. Você pode verificar o progresso de sua solicitação a qualquer momento clicando em [!UICONTROL Tools] > [!UICONTROL Data Warehouse] > [!UICONTROL Request Manager].

   Se quiser solicitar novamente os dados solicitados anteriormente, duplique uma solicitação antiga do [!UICONTROL Request Manager], conforme necessário.

Para obter mais informações sobre [!DNL Data Warehouse], consulte os seguintes links na documentação de ajuda do [!DNL Analytics]:

* [Criar uma solicitação de Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html?lang=pt-BR)
* [práticas recomendadas do Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html?lang=pt-BR)
