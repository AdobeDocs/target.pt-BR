---
keywords: Direcionamento
description: Saiba como Adobe [!DNL Target] mostra e calcula a taxa de conversão, o incentivo, a confiança e o intervalo de confiança para cada experiência.
title: Como vejo a taxa de conversão, o incentivo e o nível de confiança?
feature: Reports
exl-id: b4cfe926-eb36-4ce1-b56c-7378150b0b09
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '2162'
ht-degree: 52%

---

# Índice de conversão

A taxa de conversão, o incentivo, a confiança e o intervalo de confiança são reportados para cada experiência.

A ilustração a seguir mostra o cabeçalho do gráfico para uma atividade de amostra com os cabeçalhos [!UICONTROL Índice de conversão], [!UICONTROL Aumento] e [!UICONTROL Confiança] destacados.

![imagem com taxa de conversão](assets/conversion-rate.jpg)

>[!NOTE]
>
>Em todos os dados, pedidos duplicados são ignorados se uma `orderID` for enviada. O relatório de auditoria relaciona os pedidos duplicados ignorados.

## Índice de conversão {#section_07A36846C4E84D0881906809B9CE5A74}

Mostra a taxa de conversão mediana, a confiança, o intervalo e o número de conversões.

Por exemplo, examine a seguinte coluna Índice de conversão do relatório:

![imagem detalhes da taxa de conversão](assets/conversion-rate-detail.jpg)

A primeira linha é a experiência de controle. Mostra uma taxa de conversão de 15%, com três conversões. A segunda linha, Experiência B, mostra uma taxa de conversão de 15%, com um intervalo de confiança de aproximadamente 15,65% e três conversões.

>[!NOTE]
>
>No momento, o intervalo de confiança é calculado somente para métricas binárias.

## Aumento {#section_0F409572C720433D9378092ABC999982}

Compara o índice de conversão de cada experiência com a experiência de controle.

Aumento = (CR da experiência - CR de controle) / CR de controle

Se o controle for 0, não há aumento percentual.


## Dados de varejo {#section_30A674731BA6440E9BB93C421BE990EE}

Dados de AOV, RPV e Vendas são exibidos para cada experiência se você inseriu um Fazer pedido (`orderConfirmPage`) mbox e a selecionou como a mbox de conversão.

## Nível de confiança e intervalo de confiança {#concept_0D0002A1EBDF420E9C50E2A46F36629B}

Para cada experiência, o intervalo de confiança e confiança é exibido.

Você pode realizar cálculos offline para o for Target (A4T), mas isso exige uma etapa com as exportações de dados no [!DNL Analytics]Analytics. Para obter mais informações, consulte &quot;Execução de cálculos offline no Analytics for Target (A4T)&quot; abaixo.

### Confiança {#section_26FE5E44BDD5478792A65FCFD83DCCDC}

A confiança de uma experiência ou oferta exibida é uma probabilidade (expressa como uma porcentagem) de obter um resultado menos extremo do que o realmente observado, se a hipótese nula for verdadeira (em essência, se não houver diferença nos índices de conversão entre essa experiência ou oferta e a experiência/oferta de controle). Em termos de valores p, essa confiança exibida é de 1 - valor p. Em termos mais simples, uma maior confiança indica que os dados são menos consistentes, com o pressuposto de que a oferta/experiência de controle e não controle têm taxas de conversão iguais.

A confiança é arredondada para 100,00% sempre que for maior ou igual a 99,995%.

![imagem conf_report](assets/conf_report.png)  ![imagem conf_report_detail](assets/conf_report_detail.png)

Antes de tomar decisões comerciais, tente esperar até o tamanho da amostra ser grande o suficiente e as quatro barras de confiança de uma ou mais experiências ficarem consistentes por um período contínuo para garantir que os resultados sejam estáveis.


### Intervalo de confiança {#section_F582738DFE1648C78B93D81EBC6CACF7}

>[!NOTE]
>
>No momento, o intervalo de confiança é calculado somente para métricas binárias.

A variável *intervalo de confiança* é um intervalo de estimativas dentro do qual o valor real da métrica pode ser encontrado em um determinado nível de confiança. O Target sempre exibe intervalos de confiança de 95%. O intervalo de confiança aparece como um percentual aproximado cinza claro na coluna Índice de conversão. No exemplo abaixo, o intervalo de confiança para o incentivo da Experiência B é aproximadamente 15,65%.

![imagem conversion_rate](assets/conversion_rate.png)

**Exemplo:** O RPV observado de uma experiência é de US$ 10 e seus 95% **intervalo de confiança** é de US$ 5 a US$ 15. Desconhecido para nós, seu verdadeiro RPV é $12. Em seguida, se executarmos esse teste várias vezes, 95% do tempo em que o intervalo de confiança calculado conterá o _true_ valor do RPV de US$ 12.

**O que gera impacto sobre o intervalo de confiança?** A fórmula segue métodos estatísticos padrão para calcular intervalos de confiança.

* **Tamanho da amostra:** conforme a amostra aumenta, o intervalo diminui. Este é o método ideal, pois significa que os seus relatórios estão chegando mais perto do valor da métrica de sucesso.
* **Desvio padrão menor:** Resultados mais semelhantes, como AOVs semelhantes, números semelhantes ou visitantes convertidos a cada dia reduzem o desvio padrão.

## Cálculo de confiança e como executá-lo offline  {#section_86F7C231943043A5B8B6BFE67B706E3B}

O [download do relatório de CSV](/help/main/c-reports/downloading-data-in-csv-file.md#concept_3F276FF2BBB2499388F97451D6DE2E75) inclui apenas dados brutos e não inclui métricas calculadas, como receita por visitante, aumento ou confiança usada para testes A/B.

Para calcular essas métricas, baixe o relatório do Target [Calculadora de confiança completa](/help/main/assets/complete_confidence_calculator.xlsx) Arquivo do Excel para inserir o valor da atividade ou revisar [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

>[!NOTE]
>
>Essa calculadora é para relatórios baseados em Target e não para relatórios A4T.

## Realização de cálculos offline para Analytics for Adobe Target (A4T) {#section_B34BD016C8274C97AC9564F426B9607E}

Você pode realizar cálculos offline para o A4T, mas isso exige uma etapa com as exportações de dados no [!DNL Analytics].

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

* **Visitante:** um participante único na atividade, pela duração da atividade.

   Uma pessoa será contada como um novo participante se visitar o site com um novo computador e um novo navegador, excluir o cookie ou converter e retornar para a atividade com o mesmo cookie. Um participante é identificado pela PCID no cookie mbox do visitante. Se o PCID mudar, a pessoa será considerada um novo visitante.

* **Visita:** um único participante em uma experiência durante uma sessão de navegador única de 30 minutos.

   Se uma conversão for alcançada ou um visitante retornar ao site após se ausentar por pelo menos 30 minutos, esse visitante será contado como um novo visitante. Uma visita é identificada pela `sessionID` do cookie da mbox do visitante. Quando a `sessionID` muda, a visita é considerada nova.

* **Impressão/Visualização da página:** contado cada vez que um visitante carrega qualquer página da atividade.

   Uma única visita pode incluir várias impressões de sua página inicial, por exemplo.

>[!NOTE]
>
>Normalmente, as contagens são determinadas por cookies e pela atividade da sessão. No entanto, se você alcançar o ponto de conversão final de uma atividade e, em seguida, entrar na atividade novamente, você será considerado um novo participante e uma nova visita à atividade. Isso é verdade mesmo se os valores PCID e `sessionID` não mudarem.

## Por que [!DNL Target] recomendar o uso dos testes t de Welch? {#t-test}

Os testes A/B são experimentos para comparar o valor médio de alguma métrica de negócios em uma variante de controle (também conhecida como experiência) com o valor médio da mesma métrica em uma ou mais experiências alternativas.

[!DNL Target] recomenda usar [Teste t de Welch](https://en.wikipedia.org/wiki/Welch%27s_t-test), pois exigem menos suposições do que alternativas como os testes z, e são o teste estatístico apropriado para fazer comparações emparelhadas de métricas de negócios (quantitativas) entre experiências de controle e experiências alternativas.

### Em mais detalhes

Ao executar testes A/B online, cada usuário/visitante é atribuído aleatoriamente a uma única variante. Posteriormente, fazemos medições das métricas de negócios de interesse (por exemplo, conversões, pedidos, receita etc.) para visitantes em cada variante. O teste estatístico que usamos então testa a hipótese de que a métrica média de negócios (por exemplo, taxa de conversão, pedidos por usuário, receita por usuário etc.) é igual para o controle e uma determinada variante alternativa.

Embora a própria métrica de negócios possa ser distribuída de acordo com alguma distribuição arbitrária, a distribuição da média dessa métrica (dentro de cada variante) deve convergir para uma distribuição normal por meio do [Teorema do limite central](https://en.wikipedia.org/wiki/Central_limit_theorem). Observe que, embora não haja garantias sobre a rapidez com que essa distribuição de amostragem da média convergirá para o normal, essa condição é normalmente alcançada dada a escala de visitantes em testes online.

Dada esta normalidade da média, pode demonstrar-se que a estatística de ensaio a utilizar segue uma distribuição t, uma vez que é o rácio entre um valor normalmente distribuído (a diferença nos meios da métrica de negócio) e um termo de escala baseado numa estimativa dos dados (o erro-padrão da diferença nos meios). A variável **teste t** é então o teste de hipótese apropriado, dado que a estatística do teste segue uma distribuição t.

### Por que outros testes não são usados

A **teste z** é tecnicamente inadequado, uma vez que, no cenário de ensaio A/B típico, o denominador da estatística de ensaio não é derivado de uma variância conhecida, devendo, em vez disso, ser estimado a partir dos dados. No entanto, para tamanhos de amostra grandes o suficiente, o teste z e o teste t são idênticos.

**Testes qui-quadrados** não são usados porque são apropriados para determinar se há uma relação qualitativa entre duas variantes (ou seja, uma hipótese nula de que não há diferença entre variantes). Os testes T são mais adequados para o cenário de _quantitativamente_ comparação de métricas.

A variável **Teste U de Mann-Whitney** é um teste não paramétrico, que é apropriado quando a distribuição de amostragem da métrica média de negócios (para cada variante) não é normalmente distribuída. No entanto, como discutido anteriormente, dada a magnitude do tráfego envolvido em testes online, o Teorema do Limite Central normalmente se aplica, e assim o teste t pode ser aplicado com segurança.

Métodos mais complexos como **ANOVA** (que generaliza testes t para mais de duas variantes) pode ser aplicado quando um teste tem mais de duas experiências (&quot;testes A/Bn&quot;). No entanto, a ANOVA responde à pergunta &quot;se todas as variantes têm a mesma média&quot;, enquanto no teste A/Bn típico estamos mais interessados em _qual variante específica_ é melhor. Entrada [!DNL Target]Portanto, aplicamos testes t regulares comparando cada variante a um controle, com uma correção de Bonferroni para levar em conta comparações múltiplas.