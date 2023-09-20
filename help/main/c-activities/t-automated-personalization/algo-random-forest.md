---
keywords: floresta aleatória;árvore de decisão;ap;Automated Personalization
description: Saiba como [!DNL Adobe Target] O usa o algoritmo Random Forest em ambos [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] atividades.
title: Como o [!DNL Target] Usar o algoritmo Random Forest?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: 07a89525-4071-4434-ac96-c59a4f4422ad
source-git-commit: d5b24f298ae405d57c2ba639082cbe99c4e358fd
workflow-type: tm+mt
source-wordcount: '1431'
ht-degree: 41%

---

# Algoritmo Random Forest

O principal algoritmo de personalização usado no (AP) e no [!DNL Auto-Target] atividades é a Random Forest. Métodos de conjunto, como Random Forest, usam vários algoritmos de aprendizagem para obter um melhor desempenho preditivo do que poderia ser obtido a partir de qualquer um dos algoritmos de aprendizagem constituintes. O algoritmo Random Forest no [!UICONTROL Automated Personalization] e [!UICONTROL Direcionamento automático] é um método de classificação ou regressão que opera construindo uma variedade de árvores de decisão quando está sendo treinado.

Quando você pensa em estatísticas, um único modelo de regressão usado para prever um resultado pode vir à mente. A pesquisa mais recente em ciência de dados sugere que &quot;métodos conjuntos&quot;, em que vários modelos são criados a partir do mesmo conjunto de dados e depois combinados de forma inteligente, produzem melhores resultados do que a previsão baseada em um único modelo.

O algoritmo Random Forest é o principal algoritmo de personalização subjacente usado no [!UICONTROL Automated Personalization] e [!UICONTROL Direcionamento automático] atividades. A Random Forest combina centenas de árvores de decisão para chegar a uma previsão melhor do que uma única árvore poderia fazer sozinha.

## O que é uma árvore de decisão? {#section_7F5865D8064447F4856FED426243FDAC}

O objetivo de uma árvore decisória é analisar todos os dados de visita disponíveis com os quais um sistema pode aprender e, em seguida, agrupar esses dados, em que as visitas em cada grupo são o mais semelhantes possível entre si em relação à métrica de meta. No entanto, entre grupos, as visitas são as mais diferentes possíveis, em relação à métrica de objetivo (por exemplo, taxa de conversão). A árvore de decisão analisa as diferentes variáveis que tem no conjunto de treinamento para determinar como dividir os dados de uma forma Mutuamente Exclusiva Coletivamente Exaustiva (MECE) nesses grupos (ou &quot;folhas&quot;) para maximizar essa meta.

Em um exemplo simples, vamos supor duas variáveis de entrada:

* Gênero (com dois valores possíveis, Masculino ou Feminino)
* Código postal (com cinco valores potenciais no conjunto de dados pequeno: 11111, 22222, 3333, 44444 ou 55555)

Se a métrica de objetivo for conversão, a árvore determinará primeiro qual das duas variáveis explica a maior quantidade de variação na taxa de conversão dos dados de visita.

Vamos dizer que o código postal é mais preditivo. Esta variável formaria então a primeira &quot;ramificação&quot; da árvore. A árvore de decisão determinaria então como dividir os dados da visita, como a taxa de conversão dos registros dentro de cada divisão que seria a mais semelhante possível, e a taxa de conversão entre as divisões que seria tão diferente quanto possível. Neste exemplo, suponha que 11111, 2222, 33333 sejam uma divisão e 44444 e 55555 sejam uma segunda divisão.

Essa ação resulta na primeira camada da árvore decisória:

![imagem decision_tree_1](assets/decsion_tree_1.png)

A árvore de decisão coloca a questão: &quot;Qual é a variável mais preditiva?&quot; Neste exemplo, há apenas duas variáveis, então a resposta aqui é claramente gênero. A árvore agora procura concluir um exercício semelhante para dividir os dados *em cada ramificação*. Primeiro, vamos considerar a ramificação 11111, 22222 e 33333. Nestes códigos postais, se houver uma diferença na conversão entre homens e mulheres, então haveria duas folhas (homens e mulheres), e esta ramificação estaria completa. Nos outros ramos, 44444 e 55555, vamos supor que não haja diferença estatística entre a forma como mulheres e homens se convertem. Neste caso, a primeira ramificação torna-se a divisão final.

O exemplo resultaria na árvore abaixo:

![imagem decision_tree_2](assets/decsion_tree_2.png)

## Como as árvores de decisão são usadas pelo Random Forest? {#section_536C105EF9F540C096D60450CAC6F627}

Árvores de decisão podem ser uma poderosa ferramenta estatística. No entanto, elas têm algumas desvantagens. Mais criticamente, elas podem &quot;encaixar&quot; os dados de modo que uma árvore individual mal possa prever os dados futuros que não foram usados para construir a árvore inicial. Este desafio é conhecido como [compensação de viés-variância](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) na aprendizagem estatística. Florestas aleatórias ajudam a superar esse desafio de adaptação excessiva. No nível mais alto, uma random forest é uma coleção de árvores de decisão que são construídas de forma ligeiramente diferente no mesmo conjunto de dados que &quot;votam&quot; juntos para produzir um modelo melhor que uma árvore individual. As árvores são construídas selecionando aleatoriamente um subconjunto de registros de visita com substituição (conhecido como ensacamento) e selecionando aleatoriamente um subconjunto dos atributos, de modo que a floresta consiste em árvores de decisão ligeiramente diferentes. Este método introduz pequenas variações nas árvores criadas na Random forest. Adicionar essa quantidade controlada de variação ajuda a melhorar a precisão da previsão do algoritmo.

## Como o [!DNL Target] algoritmos de personalização usam o Random Forest? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

### Como os modelos são criados

O diagrama a seguir resume como os modelos são criados para [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] atividades:

![imagem random_forest_flow](assets/random_forest_flow.png){width="650" zoomable="yes"}

1. O Target coleta dados sobre os visitantes enquanto disponibiliza experiências ou ofertas aleatoriamente
1. Depois [!DNL Target] atinge uma massa crítica de dados, [!DNL Target] executa engenharia de recursos
1. [!DNL Target] O cria modelos do Random Forest para cada experiência ou oferta
1. [!DNL Target]O verifica se o modelo atende a um índice de qualidade limite
1. [!DNL Target]O empurra o modelo para a produção para personalizar o tráfego futuro

[!DNL Target] O usa dados coletados automaticamente e dados personalizados fornecidos por você para criar seus algoritmos de personalização. Esses modelos preveem a melhor experiência ou oferta para mostrar aos visitantes. Geralmente, um modelo é criado por experiência (se um [!UICONTROL Direcionamento automático] atividade) ou por oferta (se uma [!UICONTROL Automated Personalization] atividade). [!DNL Target] em seguida, o exibe a experiência ou a oferta que produz a métrica de sucesso mais alta prevista (por exemplo, taxa de conversão). Esses modelos devem ser treinados em visitas aleatoriamente atendidas antes que possam ser usados para previsão. Como resultado, quando uma atividade é iniciada pela primeira vez, até mesmo os visitantes que estão no grupo personalizado são apresentados aleatoriamente a diferentes experiências ou ofertas até que os algoritmos de personalização estejam prontos.

Cada modelo deve ser validado para garantir que seja bom em prever o comportamento dos visitantes antes de ser usado na atividade. Os modelos são validados com base em sua Área sob a curva (AUC). Devido à necessidade de validação, o momento exato em que um modelo começa a fornecer experiências personalizadas depende dos detalhes dos dados. Na prática, e para fins de planejamento de tráfego, geralmente é necessário mais do que o número mínimo de conversões antes que cada modelo seja válido.

Quando um modelo se torna válido para uma experiência ou oferta, o ícone do relógio à esquerda da experiência/nome da oferta é alterado para uma caixa de seleção verde. Quando há modelos válidos para pelo menos duas experiências ou ofertas, algumas visitas começam a se tornar personalizadas.

### Transformação de recursos

Antes de os dados passarem pelo algoritmo de personalização, eles passam por uma transformação de recurso, que pode ser considerada como preparação dos dados coletados nos registros de treinamento para uso pelos modelos de personalização.

As transformações de recurso dependem do tipo de atributo. Principalmente, existem dois tipos de atributos (ou &quot;recursos&quot;, como às vezes são descritos pelos cientistas de dados):

* **Categóricos:** os recursos categóricos não podem ser contados, mas podem ser classificados em grupos diferentes. Eles podem ser recursos como país, gênero ou CEP.
* **Numérico:** os recursos numéricos podem ser medidos ou contados, como idade, renda etc.

Para recursos categóricos, um conjunto de todos os recursos possíveis é mantido e a transformação de probabilidade é usada para reduzir o tamanho dos dados. Para recursos numéricos, o redimensionamento garante que os recursos sejam comparáveis em todos os segmentos.

### Equilíbrio entre aprendizagem e personalização com o multi-armed bandit.

Depois [!DNL Target] O tem modelos de personalização criados para personalizar seu tráfego. Você enfrenta uma clara compensação para futuros visitantes da sua atividade. Você deve personalizar todo o tráfego com base no modelo atual ou continuar a aprender com novos visitantes apresentando ofertas aleatórias? Você quer ter certeza de que o algoritmo de personalização está sempre aprendendo sobre novas tendências em seus visitantes, enquanto personaliza a maior parte do tráfego.

O bandit multi-arm é como [!DNL Target] O ajuda a atingir essa meta. O multi-arm bandit garante que o modelo está sempre &quot;gastando&quot; uma pequena fração de tráfego para continuar a aprender ao longo da vida da atividade de aprendizagem e para evitar a exploração excessiva de tendências anteriormente aprendidas.

No mundo da ciência de dados, o problema do bandido multi-armado é um exemplo clássico do dilema exploração versus exploração no qual uma coleção de bandidos armados, cada um com probabilidade de recompensa desconhecida, é dada. A ideia principal é desenvolver uma estratégia, que resulta na execução do segmento com a maior probabilidade de sucesso para que a recompensa total obtida seja maximizada. Multi-armed bandit é usado no sistema para pontuação online após a construção dos modelos online. Esse processo ajuda no aprendizado online durante a exploração. O algoritmo multi-armed atual é um algoritmo epsilon (ε) greedy. Nesse algoritmo, com probabilidade 1- ε, o melhor segmento é escolhido. E, com a probabilidade ε, qualquer outro segmento é escolhido aleatoriamente.
