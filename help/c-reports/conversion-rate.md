---
keywords: Targeting
description: A taxa de conversão, o incentivo, a confiança (significância estatística) e o intervalo de confiança são reportados para cada experiência.
title: Índice de conversão
feature: reports
topic: Advanced,Standard,Classic
uuid: c42d7683-2eec-4443-9545-5695a122c9de
translation-type: tm+mt
source-git-commit: 3cf1f4fa56f86c106dccdc2c97c080c17c3982b4
workflow-type: tm+mt
source-wordcount: '1621'
ht-degree: 96%

---


# Índice de conversão{#conversion-rate}

A taxa de conversão, o incentivo, a confiança (significância estatística) e o intervalo de confiança são reportados para cada experiência.

A ilustração a seguir mostra o cabeçalho do gráfico para uma atividade de amostra com os cabeçalhos [!UICONTROL Índice de conversão], [!UICONTROL Aumento] e [!UICONTROL Confiança] destacados.

![](assets/conversion-rate.jpg)

>[!NOTE]
>
>Em todos os dados, pedidos duplicados são ignorados se uma `orderID` for enviada. O relatório de auditoria relaciona os pedidos duplicados ignorados.

## Índice de conversão {#section_07A36846C4E84D0881906809B9CE5A74}

Mostra a taxa de conversão mediana, a confiança, o intervalo e o número de conversões.

Por exemplo, examine a seguinte coluna Índice de conversão do relatório:

![](assets/conversion-rate-detail.jpg)

A primeira linha é a experiência de controle. Mostra uma taxa de conversão de 15%, com três conversões. A segunda linha, Experiência B, mostra uma taxa de conversão de 15%, com um intervalo de confiança de aproximadamente 15,65% e três conversões.

>[!NOTE]
>
>No momento, o intervalo de confiança é calculado somente para métricas binárias.

## Aumento {#section_0F409572C720433D9378092ABC999982}

Compara o índice de conversão de cada experiência com a experiência de controle.

Aumento = (CR da experiência - CR de controle) / CR de controle

Se o controle for 0, não há aumento percentual.

## Confiança (significância estatística)  {#section_35DB6724813D40C7B0808DE18FE595C1}

Este número representa a probabilidade de que os resultados seriam duplicados se o teste fosse executado novamente. A confiança é arredondada para 100,00% sempre que for maior ou igual a 99,995%.

Consulte [Nível de confiança e intervalo de confiança](../c-reports/conversion-rate.md#concept_0D0002A1EBDF420E9C50E2A46F36629B).

## Dados de varejo {#section_30A674731BA6440E9BB93C421BE990EE}

Os dados de AOV, RPV e Vendas são exibidos para cada experiência se você inseriu uma mbox [de Pedido local](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/orderconfirm-create.md) (`orderConfirmPage`) e a selecionou como a mbox de conversão.

## Nível de confiança e intervalo de confiança {#concept_0D0002A1EBDF420E9C50E2A46F36629B}

Para cada experiência, o nível de confiança e o intervalo de confiança são exibidos.

As conversões e as variáveis contínuas das métricas baseadas no Target, como métricas de receita e de envolvimento, são calculadas da seguinte forma:

* **Conversão:** sim ou não
* **Todos os outros:** valores em um intervalo

Você pode realizar cálculos offline para o for Target (A4T), mas isso exige uma etapa com as exportações de dados no [!DNL Analytics]Analytics. Para obter mais informações, consulte &quot;Execução de cálculos offline no Analytics for Target (A4T)&quot; abaixo.

### Nível de confiança {#section_26FE5E44BDD5478792A65FCFD83DCCDC}

O *nível de confiança* é representado pelo percentual mais escuro na coluna Índice de conversão para cada experiência.

![](assets/conf_report.png)  ![](assets/conf_report_detail.png)

O nível de confiança, ou significância estatística, indica qual a probabilidade de o sucesso de uma experiência não resultar de simples acaso. Um nível de confiança mais alto indica:

* Que o desempenho da experiência é significativamente diferente do controle.
* Que o desempenho da experiência não se deve somente a ruídos.
* Se você executar esse teste novamente, provavelmente você verá os mesmos resultados.

Se o nível de confiança for superior a 90% ou 95%, o resultado poderá ser considerado estatisticamente significativo. Antes de tomar decisões comerciais, tente esperar até o tamanho da amostra ser grande o suficiente e as quatro barras de confiança de uma ou mais experiências ficarem consistentes por um período contínuo para garantir que os resultados sejam estáveis.

>[!NOTE]
>
>A confiança é arredondada para 100,00% sempre que for maior ou igual a 99,995%.

### Intervalo de confiança {#section_F582738DFE1648C78B93D81EBC6CACF7}

>[!NOTE]
>
>No momento, o intervalo de confiança é calculado somente para métricas binárias.

O *intervalo de confiança* é uma faixa dentro da qual o valor real pode ser encontrado em um determinado nível de confiança. O intervalo de confiança aparece como um percentual aproximado cinza claro na coluna Índice de conversão. No exemplo abaixo, o intervalo de confiança para o incentivo da Experiência B é aproximadamente 15,65%.

![](assets/conversion_rate.png)

**Exemplo:** o RPV de uma experiência é de US$ 10, seu nível de confiança é de 95% e seu **intervalo de confiança** é de US$ 5 a US$ 15. Se executarmos este teste diversas vezes, 95% das vezes o RPV seria entre US$ 5 e US$ 15.

**O que gera impacto sobre o intervalo de confiança?** A fórmula segue métodos estatísticos padrão para calcular intervalos de confiança.

* **Tamanho da amostra:** conforme a amostra aumenta, o intervalo diminui. Este é o método ideal, pois significa que os seus relatórios estão chegando mais perto do valor da métrica de sucesso.
* **Desvio padrão menor:** Resultados mais semelhantes, como AOVs semelhantes, números semelhantes ou visitantes convertidos a cada dia reduzem o desvio padrão.

## Cálculo de confiança e como executá-lo offline  {#section_86F7C231943043A5B8B6BFE67B706E3B}

O [download do relatório de CSV](../c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) inclui apenas dados brutos e não inclui métricas calculadas, como receita por visitante, aumento ou confiança usada para testes A/B.

To calculate these calculated metrics, download the Target&#39;s [Complete Confidence Calculator](/help/assets/complete_confidence_calculator.xlsx) Excel file to input the activity&#39;s value, or review the [statistical calculations used by Target](/help/assets/statistical-calculations.pdf).

>[!NOTE]
>
>Essa calculadora é para relatórios baseados em Target e não para relatórios A4T.

## Realização de cálculos offline para Analytics for Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics].

Para o A4T, usamos um cálculo de teste t de Estudante para variáveis contínuas (em vez de métricas binárias). No Analytics, um visitante é sempre rastreado e todas as ações realizadas são contadas. Portanto, se o visitante comprar várias vezes ou visitar uma métrica de sucesso várias vezes, esses hits adicionais serão contados. Isso torna a métrica uma variável contínua. Para realizar o cálculo do teste t de Estudante, é necessária a &quot;soma dos quadrados&quot;. Isto pode ser recuperado do [!DNL Analytics]. Para obter a soma dos dados dos quadrados, é necessário executar uma exportação no nível do visitante para a métrica para a qual você está otimizando, por um período de tempo de amostra.

Por exemplo, se você estiver otimizando para exibições de página por visitante, você exportaria uma amostra do número total de visualizações de página por visitante e por um período de tempo especificado, talvez alguns dias (alguns milhares de pontos de dados são tudo que você precisa). Você, então, elevaria ao quadrado de cada valor e somaria os totais (a ordem das operações é essencial aqui). Este valor de &quot;soma dos quadrados&quot; é então usado na Calculadora de confiança completa. Use a seção &quot;receita&quot; dessa planilha para esses valores.

**Para usar o recurso de exportação de dados do[!DNL Analytics]para fazer isso:**

1. Efetue logon no [!DNL Adobe Analytics].
1. Clique em **[!UICONTROL Ferramentas]** > **[!UICONTROL Data Warehouse]**.
1. Na guia **[!UICONTROL Solicitação de Data Warehouse]**, preencha os campos.

   Para obter mais informações sobre cada campo, consulte &quot;Descrições do Data Warehouse&quot; em [Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html).

   | Campo | Instruções |
   |--- |--- |
   | Nome da solicitação | Especifique um nome para sua solicitação. |
   | Data de relatório | Especifique um período de tempo e granularidade.<br>Como prática recomendada, escolha não mais que uma hora ou um dia de dados para sua primeira solicitação.  Os arquivos do Data Warehouse demoram mais para processar quanto mais longo for o tempo solicitado, por isso, é sempre uma prática recomendada solicitar primeiro um pequeno período de tempo para garantir que o arquivo retorne o resultado esperado. Em seguida, vá para o Gerenciador de solicitações, duplique sua solicitação e solicite mais dados pela segunda vez. Além disso, se você alternar a granularidade para algo diferente de &quot;Nenhum&quot;, o tamanho do arquivo aumentará drasticamente.<br>![Data Warehouse](/help/c-reports/assets/datawarehouse.png) |
   | Segmentos disponíveis | Aplique um segmento, se necessário. |
   | Detalhamentos | Selecione as dimensões desejadas:   O padrão é pronto (OOTB), enquanto o Personalizado inclui eVars e props. Recomenda-se a utilização de &quot;ID de visitante&quot; se forem necessárias informações ao nível da ID de visitante, em vez de &quot;ID de visitante da Experience Cloud&quot;.<ul><li>ID do visitante é a ID final usada pelo Analytics. Ela será AID (se o cliente for legado) ou MID (se o cliente for novo ou tiver eliminado os cookies desde que o serviço de identificação de visitante do MC foi iniciado).</li><li>A ID de visitante da Experience Cloud só será definida para clientes novos ou com cookies eliminados desde que o serviço de ID de visitante do MC foi iniciado.</li></ul> |
   | Métricas | Selecione sua métrica desejada. O padrão é OOTB, enquanto o Personalizado inclui eventos personalizados. |
   | Visualização de Relatório | Revise suas configurações antes de agendar o relatório.<br>![Data Warehouse 2](/help/c-reports/assets/datawarehouse2.png) |
   | Agendar entrega | Digite um endereço de email para entregar o arquivo, nomeie o arquivo e selecione [!UICONTROL Enviar imediatamente].<br>Observação: o arquivo pode ser entregue via FTP em [!UICONTROL Opções avançadas de entrega]<br>![Programar entrega](/help/c-reports/assets/datawarehouse3.png). |

1. Clique em **[!UICONTROL Solicitar esse relatório]**.

   A entrega do arquivo pode levar até 72 horas, dependendo da quantidade de dados solicitada. Você pode verificar o andamento de sua solicitação a qualquer momento clicando em [!UICONTROL Ferramentas] > [!UICONTROL Data Warehouse] > [!UICONTROL Gerenciador de solicitações].

   Se você deseja solicitar novamente os dados que solicitou no passado, você pode duplicar uma solicitação antiga do [!UICONTROL Gerenciador de solicitações,] conforme necessário.

Para obter mais informações sobre [!DNL Data Warehouse], consulte os seguintes links na documentação de ajuda do [!DNL Analytics]:

* [Criar uma solicitação do Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/t-dw-create-request.html)
* [Práticas recomendadas de Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse-bp.html)

## Metodologia de contagem {#concept_EC19BC897D66411BABAF2FA27BCE89AA}

É possível optar por exibir os relatórios por diferentes metodologias de contagem para entender como as suas atividades afetam os usuários durantes os ciclos de vida deles ou durante uma única sessão.

A metodologia de contagem é compatível com todos os outros tipos de atividade.

* Teste A/B

   Como exceção, as atividades A/B de Direcionamento automático são compatíveis apenas com a metodologia de contagem padrão &quot;Visita&quot;.

* Direcionamento de experiência (XT)
* Teste multivariado (MVT)

   Para o relatório de contribuição do Elemento MVT, o Target não suporta os tipos de Impressões de atividade para as métricas de receita.

* Recommendations

Somente a metodologia de contagem padrão (Visitas) é atualmente suportada para atividades de Personalização automatizada (AP).

Você pode visualizar relatórios pelas seguintes metodologias de contagem:

* **Visitante:** um participante exclusivo na atividade, pela duração da atividade.

   Uma pessoa será contada como um novo participante se visitar o site com um novo computador e um novo navegador, excluir o cookie ou converter e retornar para a atividade com o mesmo cookie. Um participante é identificado pela PCID no cookie mbox do visitante. Se o PCID mudar, a pessoa será considerada um novo visitante.

* **Visita:** um único participante em uma experiência durante uma sessão de navegador única de 30 minutos.

   Se uma conversão for alcançada ou um visitante retornar ao site após se ausentar por pelo menos 30 minutos, esse visitante será contado como um novo visitante. Uma visita é identificada pela `sessionID` do cookie da mbox do visitante. Quando a `sessionID` muda, a visita é considerada nova.

* **Impressão/Visualização da página:** contado cada vez que um visitante carrega qualquer página da atividade.

   Uma única visita pode incluir várias impressões de sua página inicial, por exemplo.

>[!NOTE]
>
>Normalmente, as contagens são determinadas por cookies e pela atividade da sessão. No entanto, se você alcançar o ponto de conversão final de uma atividade e, em seguida, entrar na atividade novamente, você será considerado um novo participante e uma nova visita à atividade. Isso é verdade mesmo se os valores PCID e `sessionID` não mudarem.