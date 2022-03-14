---
keywords: direcionamento automático, direcionamento, alocação de tráfego, perguntas frequentes, faq, solução de problemas, solucionar problemas
description: Saiba como uma atividade de Direcionamento automático no [!DNL Target] O retorna a experiência mais personalizada para cada visitante com base nos perfis do cliente e no comportamento de visitantes semelhantes.
title: O que é uma atividade de direcionamento automático?
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '1991'
ht-degree: 70%

---

# ![PREMIUM](/help/main/assets/premium.png) Visão geral do direcionamento automático

[!UICONTROL Direcionamento automático] atividades em [!DNL Adobe Target] use aprendizagem de máquina avançada para selecionar entre várias experiências definidas pelo profissional de marketing com desempenho elevado para personalizar o conteúdo e gerar conversões. O Direcionamento automático veicula a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares.

>[!NOTE]
>
>O [!UICONTROL Direcionamento automático] está disponível como parte da solução do [!DNL Target Premium]. Este recurso não está disponível no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações sobre os recursos avançados fornecidos por esta licença, consulte [Target Premium](/help/main/c-intro/intro.md).
>
>[!UICONTROL Analytics para Target] (A4T) [!UICONTROL Direcionamento automático] atividades. Para obter mais informações, consulte [Suporte ao A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

## História de sucesso do mundo real usando o Direcionamento automático {#success}

Um grande varejista de vestuário utilizou recentemente uma [!UICONTROL Direcionamento automático] atividade com dez experiências baseadas em categorias de produto (além do controle aleatório) para fornecer o conteúdo correto a cada visitante. &quot;[!UICONTROL Adicionar ao carrinho]&quot; foi escolhida como a métrica de otimização principal. As experiências direcionadas tiveram um aumento médio de 29,09%. Depois de criar o [!UICONTROL Direcionamento automático] modelos, a atividade foi definida como 90% de experiências personalizadas.

Em apenas dez dias, mais de US$ 1.700.000 de incentivo foram alcançados.

Continue lendo para aprender a usar [!UICONTROL Direcionamento automático] para aumentar o incentivo e a receita de sua organização.

## Visão geral {#section_972257739A2648AFA7E7556B693079C9}

[Ao criar uma atividade A/B usando o fluxo de trabalho guiado de três etapas](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), é possível optar por alocar o tráfego usando a opção [!UICONTROL Direcionamento automático para experiências personalizadas]:

![Opção de Direcionamento automático para experiências personalizadas](/help/main/c-activities/assets/auto-target-ui-new.png)

A opção de [!UICONTROL Direcionamento automático] no fluxo de atividade A/B permite aproveitar a aprendizagem de máquina para personalizar com base em um conjunto de experiências definidas pelo profissional de marketing em um clique. O [!UICONTROL direcionamento automático] foi projetado para fornecer otimização máxima, em comparação com o teste A/B tradicional ou Alocação automática, determinando qual experiência exibir para cada visitante. Ao contrário de uma atividade A/B na qual o objetivo é encontrar um único vencedor, o [!UICONTROL direcionamento automático] determina automaticamente a melhor experiência para um determinado visitante (com base em seu perfil e outras informações contextuais) para oferecer uma experiência altamente personalizada.

Do mesmo modo que a Personalização automatizada, o [!UICONTROL Direcionamento automático] usa um algoritmo Random Forest, um dos principais métodos de conjunto de ciência de dados, para determinar a melhor experiência para mostrar a um visitante. Como o [!UICONTROL Direcionamento automático] pode se adaptar às mudanças no comportamento do visitante, ele pode ser executado perpetuamente para fornecer um aumento. Às vezes, isso é chamado de modo &quot;sempre ativo&quot;.

Ao contrário de uma atividade A/B na qual a alocação de experiência para um determinado visitante é fixa, o [!UICONTROL Direcionamento automático] otimiza a meta de negócios especificada em cada visita. Como na [!UICONTROL Personalização automática], o [!UICONTROL Direcionamento automático], por padrão, reserva parte do tráfego da atividade como um grupo de controle para medir o aumento. Os visitantes do grupo de controle recebem uma experiência aleatória na atividade.

## Considerações

Há algumas considerações importantes que você deve ter em mente ao usar [!UICONTROL Direcionamento automático]:

* Não é possível alternar uma atividade específica de [!UICONTROL Direcionamento automático] à Automated Personalization e vice-versa.
* Não é possível alternar de Alocação de tráfego Manual (Teste A/B tradicional) para [!UICONTROL Direcionamento automático]e vice-versa depois que uma atividade é ativa.
* Um modelo é criado para identificar o desempenho da estratégia personalizada vs. tráfego distribuído aleatoriamente vs. enviar todo o tráfego para a experiência vencedora geral. Esse modelo considera somente ocorrências e conversões no ambiente padrão.

   O tráfego de um segundo conjunto de modelos é criado para cada grupo de modelagem (AP) ou experiência (AT). Para cada um desses modelos, as ocorrências e conversões em todos os ambientes são consideradas.

   Os pedidos são apresentados com o mesmo modelo, independentemente do ambiente, mas a pluralidade do tráfego deve provir do ambiente predefinido para garantir que a experiência vencedora global identificada seja consistente com o comportamento do mundo real.

* Use no mínimo duas experiências.

## Terminologia {#section_A309B7E0B258467789A5CACDC1D923F3}

Os seguintes termos são úteis quando falamos de [!UICONTROL Direcionamento automático]:

| Termo | Definição |
|---|---|
| Multi-armed bandit | Uma abordagem multi-armed bandit à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado. |
| Floresta Aleatória | Random Forest é uma abordagem de aprendizado de máquina líder. No contexto da ciência de dados, é um método de classificação ou regressão de conjunto que funciona por meio da construção de muitas árvores de decisão com base nos atributos do visitante e da visita. No Target, o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou maior receita por visita) para cada visitante específico. Para obter mais informações sobre o Random Forest no Target, consulte  [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md). |
| Amostragem de Thompson | O objetivo da Amostragem de Thompson é determinar qual experiência é a melhor em geral (não personalizada), enquanto minimiza o &quot;custo&quot; da procura dessa experiência. A amostragem de Thompson sempre escolhe um vencedor, mesmo que não haja diferença estatística entre duas experiências. Para obter mais informações, consulte [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Como funciona o [!UICONTROL direcionamento automático] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Saiba mais sobre os dados e algoritmos subjacentes ao [!UICONTROL Direcionamento automático] e à Personalização automatizada nos links abaixo:

| Termo | Detalhes |
|--- |--- |
| [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | O principal algoritmo de personalização do Target usado no [!UICONTROL Direcionamento automático] e na Personalização automatizada é o Random Forest. Métodos de conjunto como a Random Forest usam vários algoritmos de aprendizagem para obter desempenhos preditivos melhores dos que poderiam ser obtidos de qualquer um dos algoritmos de aprendizagem constituintes. O algoritmo Random Forest no sistema Automated Personalization é um método de classificação ou regressão que opera por meio da construção de várias árvores de decisão no momento do treinamento. |
| [Fazer upload de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Existem várias maneiras de inserir dados para modelos de [!UICONTROL Direcionamento automático] e Personalização automatizada. |
| [Coleta de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md) | Os algoritmos de personalização do Target coletam automaticamente vários dados. |

## Determinação da alocação de tráfego  {#section_AB3656F71D2D4C67A55A24B38092958F}

Dependendo do objetivo da sua atividade, você pode escolher uma alocação de tráfego diferente entre controle e experiências personalizadas. A prática recomendada é determinar esse objetivo antes de tornar sua atividade ativa.

A lista suspensa [!UICONTROL Alocação personalizada] permite escolher as seguintes opções:

* Avaliar o algoritmo de personalização
* Maximizar o tráfego de personalização
* Alocação personalizada

![Lista suspensa Meta de alocação](/help/main/c-activities/assets/split-new.png)

| Objetivo da atividade | Sugestão de alocação de tráfego | Compensações |
|--- |--- |--- |
| **Avaliar o algoritmo de personalização (50/50):** se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o controle e o algoritmo de destino. Esta divisão fornece a estimativa mais precisa do aumento. Recomenda-se usar com &quot;experiências aleatórias&quot; como controle. | Divisão de 50% controle / 50% experiência personalizada | <ul><li>Maximiza a precisão do aumento entre controle e personalizado</li><li>Relativamente menos visitantes têm uma experiência personalizada</li></ul> |
| **Maximizar o tráfego de personalização (90/10):** se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle, a fim de garantir que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. Observe que a desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você tem menos precisão em saber qual é o aumento exato. Independentemente da meta, esta é a divisão de tráfego recomendada ao usar uma experiência específica como controle. | A prática recomendada é usar uma divisão de 10% a 30% Controle / 70% - 90% Experiência personalizada | <ul><li>Maximiza o número de visitantes que têm uma experiência personalizada</li><li>Maximiza o aumento</li><li>Menos precisão quanto ao que é o aumento para a atividade</li></ul> |
| **Alocação personalizada** | Divida manualmente a porcentagem conforme desejado. | <ul><li>Você pode não conseguir os resultados desejados. Se você não tiver certeza, siga as sugestões para qualquer uma das opções anteriores</li></ul> |

Para ajustar a porcentagem de Controle, clique nos ícones na coluna Alocação. Você não pode diminuir o grupo de controle para menos de 10%.

![Alterar a alocação de tráfego do Direcionamento automático](/help/main/c-activities/assets/auto-target-control.png)

Você pode [selecionar uma experiência específica para usar como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou usar a opção de experiência Aleatória.

## Quando você deve escolher o [!UICONTROL Direcionamento automático] em vez da Personalização automatizada? {#section_BBC4871C87944DD7A8B925811A30C633}

Existem vários cenários em que você pode preferir usar o [!UICONTROL Direcionamento automático][!UICONTROL  em vez da Personalização automatizada]:

* Se você quiser definir toda a experiência, em vez de ofertas individuais que serão combinadas automaticamente para formar uma experiência.
* Se você quiser usar o conjunto completo de recursos do Visual Experience Composer (VEC) não suportados pela [!UICONTROL Personalização automática]: o editor de código personalizado, vários públicos-alvo de experiência e muito mais.
* Se você quiser fazer mudanças estruturais na sua página em diferentes experiências. Por exemplo, se você deseja reorganizar elementos em sua página inicial, [!UICONTROL Direcionamento automático] seria mais apropriado usar do que o Automated Personalization.

## O que o [!UICONTROL Direcionamento automático] tem em comum com a personalização automatizada? {#section_2A601F482F9A44E38D4B694668711319}

**O algoritmo otimiza para um resultado favorável para cada visita.**

* O algoritmo prevê a propensão do visitante para a conversão (ou receita estimada da conversão) para oferecer a melhor experiência.
* Um visitante é qualificado para uma nova experiência ao final de uma sessão existente (a menos que o visitante esteja no grupo de controle, nesse caso, a experiência que o visitante recebe na primeira visita permanece a mesma para visitas subsequentes).
* Em uma sessão, a previsão não muda, para manter a consistência visual.

**O algoritmo se adapta às mudanças no comportamento do visitante.**

* O multi-arm bandit garante que o modelo esteja sempre &quot;gastando&quot; uma pequena fração do tráfego para continuar aprendendo durante toda a vida do aprendizado da atividade e para evitar a exploração excessiva de tendências aprendidas anteriormente.
* Os modelos subjacentes são reconstruídos a cada 24 horas usando os dados de comportamento do visitante mais recentes para garantir que o Target esteja sempre explorando as preferências atuais do visitante.
* Se o algoritmo não puder determinar as experiências vencedoras para os indivíduos, ele alternará automaticamente para mostrar a experiência geral de melhor desempenho enquanto continua a procurar por vencedores personalizados. A experiência de melhor desempenho é encontrada usando a [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**O algoritmo otimiza continuamente para uma métrica de meta única.**

* Essa métrica pode ser baseada em conversão ou baseada em receita (mais especificamente, Receita por visitante).

**O Target coleta automaticamente informações sobre os visitantes para criar os modelos de personalização.**

* Para obter mais informações sobre os parâmetros usados &#x200B;&#x200B;no [!UICONTROL Direcionamento automático] e na Personalização automatizada, consulte [Coleção de dados da personalização automatizada](/help/main/c-activities/t-automated-personalization/ap-data.md).

**O Target usa automaticamente todos os públicos-alvo compartilhados da Experience Cloud para criar os modelos de personalização.**

* Você não precisa fazer nada específico para adicionar públicos-alvo ao modelo. Para obter informações sobre como usar os públicos-alvo da Experience Cloud com o Target, consulte  [Públicos-alvo da Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md)

**Os profissionais de marketing podem fazer upload de dados offline, pontuações de propensão ou outros dados personalizados para criar modelos de personalização.**

* Saiba mais sobre como[ carregar dados para Direcionamento automático e Personalização automatizada](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## Como o [!UICONTROL Direcionamento automático] difere da Personalização automatizada? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL O Direcionamento automático] exige frequentemente menos tráfego do que a Personalização automatizada para um modelo personalizado a ser criado.**

Embora a quantidade de tráfego *por experiência* necessária para os modelos de [!UICONTROL Direcionamento automático] ou de [!UICONTROL Personalização automática] seja a mesma, geralmente há mais experiências em uma atividade de [!UICONTROL Personalização automatizada] do que uma atividade de Direcionamento automático. Por exemplo, se você tivesse uma atividade de [!UICONTROL Personalização automática] em que criou duas ofertas por local com dois locais, haveria quatro (2 = 4) experiências totais incluídas na atividade (sem exclusões). Usando o [!UICONTROL Direcionamento automático], você pode definir a experiência 1 para incluir a oferta 1 no local 1 e a oferta 2 no local 2 e a experiência 2 para incluir a oferta 1 no local 1 e a oferta 2 no local 2. Como o [!UICONTROL Direcionamento automático] permite que você tenha várias alterações em uma experiência, é possível reduzir o número total de experiências em sua atividade.

Para o [!UICONTROL Direcionamento automático], as regras básicas podem ser usadas para entender os requisitos de tráfego:

* **Quando a conversão é a sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia e por experiência, além disso, a atividade deve ter pelo menos 7.000 visitas e 350 conversões.
* **Quando a Receita por visita é sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia e por experiência, além disso, a atividade deve ter pelo menos 1.000 conversões por experiência. O RPV geralmente requer mais dados para criar modelos devido à maior variação de dados que normalmente existe na receita de visitas em comparação com a taxa de conversão.

**[!UICONTROL O Direcionamento automático] possui uma funcionalidade de configuração completa.**

* Como o [!UICONTROL Direcionamento automático] é incorporado no fluxo de trabalho da atividade A/B, o [!UICONTROL Direcionamento automático] se beneficia do Visual Experience Composer (VEC) mais maduro e completo. Você também pode utilizar os [links de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) com o [!UICONTROL Direcionamento automático].

**[!UICONTROL O Direcionamento automático] fornece uma extensa estrutura de testes online.**

* O multi-arm bandit é parte de uma estrutura de testes online maior que permite que nossos cientistas de dados e pesquisadores entendam os benefícios de suas melhorias contínuas em condições do mundo real.
* No futuro, esse banco de testes nos permitirá abrir nossa plataforma de aprendizagem de máquina para nossos clientes com conhecimento de dados, de modo que eles possam trazer seus próprios modelos para aumentar os modelos do Target.

## Relatórios e [!UICONTROL Direcionamento automático] {#section_42EE7F5E65E84F89A872FE9921917F76}

Para obter mais informações, consulte [Relatório de resumo do direcionamento automático](/help/main/c-reports/auto-target-summary-report.md) na seção [Relatórios](/help/main/c-reports/reports.md).

## Vídeo de treinamento: Noções básicas sobre atividades de direcionamento automático ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo explica como configurar uma atividade A/B de [!UICONTROL Direcionamento automático].

Depois de concluir este treinamento, você será capaz de:

* Definir teste de [!UICONTROL Direcionamento automático]
* Comparar e contrastar Direcionamento automático para [!UICONTROL personalização automatizada]
* Criar atividades de [!UICONTROL Direcionamento automático]

>[!VIDEO](https://video.tv.adobe.com/v/18558)
