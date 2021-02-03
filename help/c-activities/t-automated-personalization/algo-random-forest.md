---
keywords: floresta aleatória;árvore decisória;ap;Automated Personalization
description: O principal algoritmo de personalização do Target usado na Personalização automatizada e no Direcionamento automático é o Random Forest. Métodos de conjunto como a Random Forest usam vários algoritmos de aprendizagem para obter desempenhos preditivos melhores dos que poderiam ser obtidos de qualquer um dos algoritmos de aprendizagem constituintes. O algoritmo Random Forest da Personalização automatizada é um método de classificação ou regressão que funciona por meio da construção de várias de árvores de decisão durante o treinamento.
title: Algoritmo Random Forest
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '1463'
ht-degree: 97%

---


# ![PREMIUM](/help/assets/premium.png) Algoritmo Random Forest

O principal algoritmo de personalização do Target usado na Personalização automatizada e no Direcionamento automático é o Random Forest. Métodos de conjunto como a Random Forest usam vários algoritmos de aprendizagem para obter desempenhos preditivos melhores dos que poderiam ser obtidos de qualquer um dos algoritmos de aprendizagem constituintes. O algoritmo Random Forest da Personalização automatizada é um método de classificação ou regressão que funciona por meio da construção de várias de árvores de decisão durante o treinamento.

Quando você pensa em estatísticas, um único modelo de regressão usado para prever um resultado pode vir à mente. A pesquisa mais recente em ciência de dados sugere que &quot;métodos conjuntos&quot;, em que vários modelos são criados a partir do mesmo conjunto de dados e depois combinados de forma inteligente, produzem melhores resultados do que a previsão baseada em um único modelo.

O algoritmo Random Forest é a chave subjacente ao algoritmo de personalização usado nas atividades de Personalização automatizada e Direcionamento automático. A Random Forest combina centenas de árvores de decisões para chegar a uma melhor previsão do que uma única árvore poderia fazer sozinha.

## O que é uma árvore decisória? {#section_7F5865D8064447F4856FED426243FDAC}

O objetivo de uma árvore de decisão é decompor todos os dados de visita disponíveis que um sistema pode aprender e, em seguida, agrupar esses dados, onde as visitas dentro de cada grupo são tão semelhantes quanto possível umas às outras em relação à métrica de meta. Nos grupos, no entanto, as visitas são tão diferentes quanto possível, com relação à métrica de meta (por exemplo, taxa de conversão). A árvore de decisão analisa as diferentes variáveis que possui no conjunto de treinamento para determinar como dividir os dados em um modo MECE (Mutualmente-Exclusivo-Coletivamente-Exaustivo) nesses grupos (ou &quot;folhas&quot;) para maximizar esse objetivo.

Em um exemplo simples, vamos supor que temos apenas duas variáveis de entrada:

* Gênero (com dois valores possíveis, Masculino ou Feminino)
* CEP (com cinco valores possíveis em nosso pequeno conjunto de dados: 11111, 22222, 33333, 44444 ou 55555)

Se nossa métrica de meta for conversão, a árvore primeiro determinará qual das nossas duas variáveis explica a maior quantidade de variação na taxa de conversão dos dados da visita.

Vamos dizer que o código postal é mais preditivo. Esta variável formaria então a primeira &quot;ramificação&quot; da árvore. A árvore de decisão determinaria então como dividir os dados da visita, como a taxa de conversão dos registros dentro de cada divisão que seria a mais semelhante possível, e a taxa de conversão entre as divisões que seria tão diferente quanto possível. Em nosso exemplo, assumiremos que 11111, 22222, 33333 pertencem a uma divisão e 44444 e 55555 pertencem à segunda divisão.

Esta ação resultaria na primeira camada da nossa árvore de decisão:

![](assets/decsion_tree_1.png)

A árvore de decisão faria a pergunta: &quot;Qual é a variável mais previsível?&quot; No nosso exemplo, temos apenas duas variáveis, então a resposta aqui é claramente de gênero. A árvore agora procurará concluir um exercício semelhante para dividir os dados *dentro de cada ramificação*. Primeiro, vamos considerar a ramificação 11111, 22222 e 33333. Nestes códigos postais, se houver uma diferença na conversão entre homens e mulheres, então haveria duas folhas (homens e mulheres), e esta ramificação estaria completa. Na outra ramificação, 44444 e 55555, vamos supor que não há diferença estatística entre a conversão de mulheres e homens. Neste caso, a primeira ramificação torna-se a divisão final.

Nosso exemplo resultaria na árvore abaixo:

![](assets/decsion_tree_2.png)

## Como as árvores de decisão são usadas pela Random Forest? {#section_536C105EF9F540C096D60450CAC6F627}

Árvores de decisão podem ser uma poderosa ferramenta estatística. No entanto, elas têm algumas desvantagens. Mais criticamente, elas podem &quot;encaixar&quot; os dados de modo que uma árvore individual mal possa prever os dados futuros que não foram usados para construir a árvore inicial. Este desafio é conhecido como [compensação de viés-variância](https://en.wikipedia.org/wiki/Bias%E2%80%93variance_tradeoff) na aprendizagem estatística. Random forests ajudam a superar esse desafio de superajuste. No nível mais alto, uma random forest é uma coleção de árvores de decisão que são construídas de forma ligeiramente diferente no mesmo conjunto de dados que &quot;votam&quot; juntos para produzir um modelo melhor que uma árvore individual. As árvores são construídas aleatoriamente selecionando um subconjunto de registros de visitas com substituição (conhecida como embalagem), bem como selecionando aleatoriamente um subconjunto dos atributos, de modo que a floresta consista em árvores de decisão ligeiramente diferentes. Este método introduz pequenas variações nas árvores criadas na Random forest. Adicionar essa quantidade controlada de variação ajuda a melhorar a precisão da previsão do algoritmo.

## Como os algoritmos de personalização do Público alvo usam Floresta Aleatória? {#section_32FB53CAD8DF40FB9C0F1217FBDBB691}

**Como são construídos os modelos**

O diagrama a seguir resume como os modelos são criados para atividades do Target automático ou da Personalização automatizada:

![](assets/random_forest_flow.png)

1. O Target coleta dados sobre os visitantes enquanto oferece aleatoriamente experiências/ofertas
1. Depois que o Target atinge uma massa crítica de dados, ele executa a engenharia de recursos
1. O Target cria modelos Random Forest para cada experiência/oferta
1. O Target verifica se o modelo atende a um índice de qualidade limite
1. O Target empurra o modelo para a produção para personalizar o tráfego futuro

O Target usa dados coletados automaticamente, bem como dados personalizados fornecidos por você, para criar seus algoritmos de personalização. Esses modelos preveem a melhor experiência ou oferta para mostrar aos visitantes. Geralmente, um modelo é construído por experiência (se for uma atividade do Target automático) ou por oferta (se for uma atividade de Personalização automatizada). O Target escolhe, então, exibir a experiência ou oferta que gera a maior métrica de sucesso prevista (por exemplo, taxa de conversão). Esses modelos devem ser treinados em visitas aleatoriamente atendidas antes que possam ser usados para previsão. Como resultado, quando uma atividade é iniciada pela primeira vez, até mesmo os visitantes que estão no grupo personalizado são apresentados aleatoriamente a diferentes experiências ou ofertas até que os algoritmos de personalização estejam prontos.

Cada modelo deve ser validado para garantir que seja bom em prever o comportamento dos visitantes antes de ser usado em sua atividade. Os modelos são validados com base na sua AUC (área sob a curva). Devido à necessidade de validação, o momento exato em que um modelo começará a servir experiências personalizadas depende dos detalhes dos dados. Na prática, e para fins de planejamento de tráfego, geralmente é necessário mais do que o número mínimo de conversões antes que cada modelo seja válido.

Quando um modelo se torna válido para uma experiência ou oferta, o ícone do relógio à esquerda da experiência/nome da oferta é alterado para uma caixa de seleção verde. Quando existem modelos válidos para pelo menos duas experiências/ofertas, algumas visitas começam a se tornar personalizadas.

**Transformação de recurso **

Antes de os dados passarem pelo algoritmo de personalização, eles passam por uma transformação de recurso, que pode ser considerada como preparação dos dados coletados nos registros de treinamento para uso pelos modelos de personalização.

As transformações de recurso dependem do tipo de atributo. Principalmente, existem dois tipos de atributos (ou &quot;recursos&quot;, como às vezes são descritos pelos cientistas de dados):

* **Categóricos:** os recursos categóricos não podem ser contados, mas podem ser classificados em grupos diferentes. Eles podem ser recursos como país, gênero ou CEP.
* **Numérico:** os recursos numéricos podem ser medidos ou contados, como idade, renda etc.

Para recursos categóricos, um conjunto de todos os recursos possíveis é mantido e a transformação de probabilidade é usada para reduzir o tamanho dos dados. Para recursos numéricos, o redimensionamento assegura que os recursos sejam equivalentes no quadro.

**Equilibrar aprendizagem vs. personalização com o Multi-Armed Bandit**

Depois que o Target tiver modelos de personalização criados para personalizar seu tráfego, haverá uma compensação clara para os futuros visitantes de sua atividade: você deve personalizar todo o tráfego com base no modelo atual ou continuar aprendendo com novos visitantes apresentado-lhes ofertas aleatórias? Você quer ter certeza de que o algoritmo de personalização está sempre aprendendo sobre novas tendências em seus visitantes, enquanto personaliza a maior parte do tráfego.

O multi-arm bandit é usando pelo Target para ajudar você a atingir esta meta. O multi-arm bandit garante que o modelo esteja sempre &quot;gastando&quot; uma pequena fração do tráfego para continuar aprendendo durante toda a vida do aprendizado da atividade e para evitar a exploração excessiva de tendências aprendidas anteriormente.

No mundo da ciência de dados, o problema multi-armed bandit (MAB) é um exemplo clássico de exploração versus o dilema de exploração no qual uma coleção de one-armed bandits, todos com probabilidade de recompensa desconhecida, é atribuída. A ideia principal é desenvolver uma estratégia, que resulta na execução do segmento com a maior probabilidade de sucesso para que a recompensa total obtida seja maximizada. O multi-armed bandit é usado no sistema quando a pontuação online após os modelos online é criada. Isso o ajuda com o aprendizado online durante a exploração. O algoritmo multi-armed atual é o algoritmo ganancioso epsílon (ε). Nesse algoritmo, com probabilidade 1- ε, o melhor segmento é escolhido. E, com a probabilidade ε, qualquer outro segmento é escolhido aleatoriamente.
