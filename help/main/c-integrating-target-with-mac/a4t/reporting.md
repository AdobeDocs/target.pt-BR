---
keywords: analytics para target;a4T;analytics como fonte de relatórios;analytics
description: Saiba como usar o Analytics para [!DNL Target] (A4T). O A4T fornece acesso aos relatórios do Analytics para [!DNL Target] atividades que usam métricas do Analytics e segmentos de público-alvo.
title: Como usar relatórios no A4T?
feature: Analytics for Target (A4T)
exl-id: cab5dc5f-166a-468e-8382-ae734684afdd
source-git-commit: 6857ba1a6410d3140a83a052efc50e9dd1776fd9
workflow-type: tm+mt
source-wordcount: '1310'
ht-degree: 46%

---

# Relatórios do A4T

Usar [!DNL Adobe Analytics] como sua fonte de relatórios para [!DNL Adobe Target] O (A4T) oferece acesso ao [!DNL Analytics] relatórios para o seu [!DNL Target] atividades.

Você pode exibir relatórios para suas atividades no [!DNL Analytics] e [!DNL Target].

Para relatar práticas recomendadas usando o [!DNL Analytics] para [!DNL Target], [visitar esta Adobe Spark Page](https://spark.adobe.com/page/Lo3Spm4oBOvwF/).

## Visão geral {#section_035A62D65608423285D8A5A54731E2C5}

Ambos [!DNL Analytics] e [!DNL Target] O relata os participantes da medida (as pessoas que entram nos testes), em vez dos visitantes do site.

Toda vez que um visitante visualizar o conteúdo da atividade na página, [!DNL Target] faz uma chamada direta de servidor para servidor para [!DNL Analytics], incluindo a atividade e a experiência que o visitante viu. [!DNL Target] também chama [!DNL Analytics] sempre que a conversão for feita. [!DNL Analytics] O adiciona a conversão como uma nova variável [!DNL Analytics] chamado &quot;Conversão de atividade&quot;, que é rastreado junto com outros dados coletados pelo [!DNL Analytics].

Quando a variável [!UICONTROL Selecionar] a operação é usada e você classifica por *Participantes*, somente as experiências que receberam participantes durante o período selecionado serão exibidas nos relatórios.

>[!NOTE]
>
>Relatórios fornecidos por [!DNL Target] têm uma latência de quatro minutos. Para atividades viabilizadas pelo A4T, em ambos os [!DNL Target] e [!DNL Analytics] Em relatórios do, pode levar até 24 horas após a atividade ser salva inicialmente para que os dados do relatório possam ser detalhados por experiências. Os dados coletados nas primeiras 24 horas ainda são precisos e são atribuídos à experiência correta.

## Relatórios no Analytics  {#analytics}

Entrada [!DNL Analytics], há várias dimensões e métricas disponibilizadas após a integração do A4T ser ativada.

### Dimensões

* [!UICONTROL Analytics for Target] - A ID principal transmitida pela integração. O formato dessa dimensão é `Activity ID:Experience ID:3rd ID`. As dimensões abaixo são classificações dessa dimensão.
* [!UICONTROL Atividades do Target]
* [!UICONTROL Experiências target]
* [!UICONTROL Atividade do Target] > [!UICONTROL Experiência]
* [!UICONTROL 3ª ID] - pode ser ignorado

### Métricas

* [!UICONTROL Impressões da atividade] - Corresponde à variável [!UICONTROL Participantes] número no [!DNL Target] relatório.
* [!UICONTROL Conversões de atividade] - Corresponde à variável [!UICONTROL Conversões personalizadas] número no [!DNL Target] relatório.

Entrada [!DNL Analysis Workspace], use o [!UICONTROL Analytics for Target] painel para analisar suas [!DNL Target] atividades e experiências com incentivo e confiança. Para obter mais informações, consulte [Painel Analytics for Target (A4T)](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/panels/a4t-panel.html?lang=pt-BR) no *Guia de ferramentas do Analytics*.

>[!IMPORTANT]
>
>Se o seu [!UICONTROL Atividades do Target] relatório em [!DNL Analytics] lista &quot;não especificado&quot; em vez de listar suas atividades, uma atualização é necessária para a conta provisionada. Entre em contato com o Atendimento ao cliente para resolver esse problema.

Para obter informações e exemplos detalhados, abra o [Analytics &amp; Target: práticas recomendadas para análise](https://spark.adobe.com/page/Lo3Spm4oBOvwF/) tutorial, fornecido pela Adobe Experience League.

## Relatórios em [!DNL Target] {#section_C0D1F17F88374B6690BF904D7B83B42E}

Quando [!DNL Analytics] é usada como fonte de geração de relatórios, informa no [!DNL Target] mostrar os dados coletados de [!DNL Analytics]. O relatório difere, de certa forma, de outros [!DNL Target] relatórios:

* A variável [!UICONTROL Públicos-alvo] mostra os públicos-alvo disponíveis para a sua [!DNL Analytics] conjunto de relatórios.
* A variável [!UICONTROL Métrica] A lista mostra cada métrica disponível até [!DNL Analytics].

   Todas as métricas estão disponíveis, incluindo as métricas personalizadas ou calculadas que estão integradas no [!DNL Analytics].

   Quaisquer números que aumentarem serão mostrados como positivos no relatório, mesmo quando um aumento for indesejado. Por exemplo, mesmo que você queira uma taxa de rejeição mais baixa, a taxa de rejeição mais alta é mostrada como vencedora com o maior incentivo. Considere essas métricas de métricas semelhantes, bem como sua preferência por diminuir ou aumentar os números, ao tomar decisões baseadas nos relatórios.

Você pode aplicar a métrica ou público-alvo ao relatório em [!DNL Target] após o início da atividade ou mesmo após a conclusão do teste. Você não precisa saber exatamente o que deseja medir com antecedência.

Clique para exibir a lista completa [!DNL Analytics] relatório diretamente da página do relatório de atividades.

## Criação da atividade {#section_311586E3FF5541E7A91D1A3CE5F9ACE3}

Durante a criação da atividade, você deve especificar uma meta para a atividade na página [!UICONTROL Configurações]. Esta meta torna-se a métrica padrão para o relatório e é sempre listada como a primeira opção no seletor de métricas. Não é possível selecionar os segmentos para os relatórios, como você faria para uma atividade padrão do Target. Um teste com [!DNL Analytics] usos [!DNL Adobe Analytics] segmentos em vez de [!DNL Target] públicos-alvo.

## Realização de cálculos offline para Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Você pode realizar cálculos offline para intervalos de confiança e confiança para o A4T usando o [!DNL Target] [Calculadora de confiança completa](/help/main/assets/complete_confidence_calculator.xlsx) arquivo do Excel, mas requer uma etapa com as exportações de dados no [!DNL Analytics].

Para o A4T, usamos um [Teste t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test){target=_blank} cálculo para variáveis contínuas (em vez de métricas binárias). No Analytics, um visitante é sempre rastreado e todas as ações realizadas são contadas. Portanto, se o visitante comprar várias vezes ou visitar uma métrica de sucesso várias vezes, esses hits adicionais serão contados. Isso torna a métrica uma variável contínua. Para realizar o cálculo t-test de Welch, a &quot;soma dos quadrados&quot; é necessária para calcular a variância, que é usada no denominador da estatística t. [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md) explica os detalhes das fórmulas matemáticas usadas. A soma dos quadrados pode ser recuperada de [!DNL Analytics]. Para obter a soma dos dados dos quadrados, é necessário executar uma exportação no nível do visitante para a métrica para a qual você está otimizando, por um período de tempo de amostra.

Por exemplo, se estiver otimizando para exibições de página por visitante, você exportaria uma amostra do número total de exibições de página por visitante por um período especificado, talvez alguns dias (alguns milhares de pontos de dados são tudo de que você precisa). Você, então, elevaria ao quadrado de cada valor e somaria os totais (a ordem das operações é essencial aqui). Este valor de &quot;soma dos quadrados&quot; é então usado na Calculadora de confiança completa. Use a seção &quot;receita&quot; dessa planilha para esses valores.

**Para usar o recurso de exportação de dados do [!DNL Analytics] para fazer isso:**

1. Efetue logon no [!DNL Adobe Analytics].
1. Clique em **[!UICONTROL Ferramentas]** > **[!UICONTROL Data Warehouse]**.
1. Na guia **[!UICONTROL Solicitação de Data Warehouse]**, preencha os campos.

   Para obter mais informações sobre cada campo, consulte &quot;Descrições do Data Warehouse&quot; em [Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse.html).

   | Campo | Instruções |
   |--- |--- |
   | Nome da solicitação | Especifique um nome para sua solicitação. |
   | Data de relatório | Especifique um período de tempo e granularidade.<br>Como prática recomendada, escolha não mais que uma hora ou um dia de dados para sua primeira solicitação.  Os arquivos do Data Warehouse demoram mais para processar quanto mais longo for o tempo solicitado, por isso, é sempre uma prática recomendada solicitar primeiro um pequeno período de tempo para garantir que o arquivo retorne o resultado esperado. Em seguida, vá para o Gerenciador de solicitações, duplique sua solicitação e solicite mais dados pela segunda vez. Além disso, se você alternar a granularidade para algo diferente de &quot;Nenhum&quot;, o tamanho do arquivo aumentará drasticamente.<br>![Data Warehouse](/help/main/c-reports/assets/datawarehouse.png) |
   | Segmentos disponíveis | Aplique um segmento, se necessário. |
   | Detalhamentos | Selecione as dimensões desejadas:   O padrão é pronto (OOTB), enquanto o Personalizado inclui eVars e props. É recomendável usar &quot;ID de visitante&quot; se as informações no nível de ID de visitante forem necessárias, em vez de &quot;ID de visitante do Experience Cloud&quot;.<ul><li>ID do visitante é a ID final usada pelo Analytics. Ela será AID (se o cliente for legado) ou MID (se o cliente for novo ou tiver eliminado os cookies desde que o serviço de identificação de visitante do MC foi iniciado).</li><li>A ID de visitante da Experience Cloud só será definida para clientes novos ou com cookies eliminados desde que o serviço de ID de visitante do MC foi iniciado.</li></ul> |
   | Métricas | Selecione sua métrica desejada. O padrão é OOTB, enquanto o Personalizado inclui eventos personalizados. |
   | Visualização de Relatório | Revise suas configurações antes de agendar o relatório.<br>![Data Warehouse 2](/help/main/c-reports/assets/datawarehouse2.png) |
   | Agendar entrega | Digite um endereço de email para entregar o arquivo, nomeie o arquivo e selecione [!UICONTROL Enviar imediatamente].<br>Observação: o arquivo pode ser entregue via FTP em [!UICONTROL Opções avançadas de entrega]<br>![Programar entrega](/help/main/c-reports/assets/datawarehouse3.png). |

1. Clique em **[!UICONTROL Solicitar esse relatório]**.

   A entrega do arquivo pode levar até 72 horas, dependendo da quantidade de dados solicitada. Você pode verificar o andamento de sua solicitação a qualquer momento clicando em [!UICONTROL Ferramentas] > [!UICONTROL Data Warehouse] > [!UICONTROL Gerenciador de solicitações].

   Se quiser solicitar novamente os dados solicitados no passado, duplique uma solicitação antiga da [!UICONTROL Gerenciador de solicitações] conforme necessário.

Para obter mais informações sobre [!DNL Data Warehouse], consulte os seguintes links na documentação de ajuda do [!DNL Analytics]:

* [Criar uma solicitação do Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/t-dw-create-request.html)
* [Práticas recomendadas do Data Warehouse](https://experienceleague.adobe.com/docs/analytics/export/data-warehouse/data-warehouse-bp.html)
