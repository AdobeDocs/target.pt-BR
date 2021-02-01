---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
description: O Público alvo automático no Adobe Target usa o aprendizado de máquina avançado para selecionar entre várias experiências definidas pelo profissional de marketing de alto desempenho para personalizar o conteúdo e gerar conversões. O Direcionamento automático veicula a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares.
title: Visão geral do Público alvo automático
feature: Auto-Target
translation-type: tm+mt
source-git-commit: 95e2ed4d9ca22e18b91533365624bcc001d09c34
workflow-type: tm+mt
source-wordcount: '2016'
ht-degree: 85%

---


# ![Visão geral do ](/help/assets/premium.png) PREMIUMAuto-Público alvo

[!UICONTROL As atividades de ] direcionamento automático no Adobe Target usam o aprendizado de máquina avançado para selecionar entre várias experiências definidas pelo profissional de marketing de alto desempenho para personalizar o conteúdo e gerar conversões. O Direcionamento automático veicula a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares.

>[!NOTE]
>
>O [!UICONTROL Direcionamento automático] está disponível como parte da solução do [!DNL Target Premium]. Este recurso não está disponível no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações sobre os recursos avançados fornecidos por esta licença, consulte [Target Premium](/help/c-intro/intro.md).
>
>[!UICONTROL O Analytics for Público alvo] (A4T) oferece suporte para atividades de direcionamento  [!UICONTROL automático ] para usuários. Para obter mais informações, consulte [Suporte A4T para a Autoalocação e Público alvo de atividades](/help/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

## História de sucesso real usando o Público alvo automático {#success}

Um grande varejista de roupas recentemente usou uma atividade [!UICONTROL Público alvo automático] com dez experiências baseadas em categorias de produtos (além de controle aleatório) para fornecer o conteúdo correto para cada visitante. &quot;[!UICONTROL Adicionar ao carrinho]&quot; foi escolhido como a métrica de otimização primária. As experiências direcionadas tiveram um aumento médio de 29,09%. Depois de criar os modelos [!UICONTROL Público alvo automático], a atividade foi definida como 90% de experiências personalizadas.

Em apenas dez dias, mais de US$ 1.700.000 em incentivo foram alcançados.

Continue lendo para saber como usar [!UICONTROL Público alvo automático] para aumentar o incentivo e a receita de sua organização.

## Visão geral {#section_972257739A2648AFA7E7556B693079C9}

[Ao criar uma atividade A/B usando o fluxo de trabalho guiado de três etapas](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md), é possível optar por alocar o tráfego usando a opção [!UICONTROL Direcionamento automático para experiências personalizadas]:

![Opção de Direcionamento automático para experiências personalizadas](/help/c-activities/assets/auto-target-ui-new.png)

A opção de [!UICONTROL Direcionamento automático] no fluxo de atividade A/B permite aproveitar a aprendizagem de máquina para personalizar com base em um conjunto de experiências definidas pelo profissional de marketing em um clique. O [!UICONTROL direcionamento automático] foi projetado para fornecer otimização máxima, em comparação com o teste A/B tradicional ou Alocação automática, determinando qual experiência exibir para cada visitante. Ao contrário de uma atividade A/B na qual o objetivo é encontrar um único vencedor, o [!UICONTROL direcionamento automático] determina automaticamente a melhor experiência para um determinado visitante (com base em seu perfil e outras informações contextuais) para oferecer uma experiência altamente personalizada.

Do mesmo modo que a Personalização automatizada, o [!UICONTROL Direcionamento automático] usa um algoritmo Random Forest, um dos principais métodos de conjunto de ciência de dados, para determinar a melhor experiência para mostrar a um visitante. Como o [!UICONTROL Direcionamento automático] pode se adaptar às mudanças no comportamento do visitante, ele pode ser executado perpetuamente para fornecer um aumento. Às vezes, isso é chamado de modo &quot;sempre ativo&quot;.

Ao contrário de uma atividade A/B na qual a alocação de experiência para um determinado visitante é fixa, o [!UICONTROL Direcionamento automático] otimiza a meta de negócios especificada em cada visita. Como na [!UICONTROL Personalização automática], o [!UICONTROL Direcionamento automático], por padrão, reserva parte do tráfego da atividade como um grupo de controle para medir o aumento. Os visitantes do grupo de controle recebem uma experiência aleatória na atividade.

## Considerações

Há algumas considerações importantes a serem levadas em conta ao usar [!UICONTROL Público alvo automático]:

* Você não pode alternar uma atividade específica de [!UICONTROL Direcionamento automático] para Personalização automatizada, e vice-versa.
* Você não pode alternar de Alocação de tráfego manual (teste tradicional A/B) para [!UICONTROL Direcionamento automático] e vice-versa depois que uma atividade estiver ativa.
* Um modelo é criado para identificar o desempenho da estratégia personalizada em comparação ao tráfego atendido aleatoriamente em vez de enviar todo o tráfego para a experiência vencedora geral. Esse modelo considera somente ocorrências e conversões no ambiente padrão.

   O tráfego de um segundo conjunto de modelos é criado para cada grupo de modelagem (AP) ou experiência (AT). Para cada um desses modelos, as ocorrências e conversões em todos os ambientes são consideradas.

   Por conseguinte, os pedidos serão acompanhados do mesmo modelo, independentemente do ambiente, mas a pluralidade do tráfego deverá provir do ambiente por defeito, a fim de assegurar que a experiência globalmente identificada vencedora seja coerente com o comportamento no mundo real.

* Você deve usar no mínimo duas experiências.

## Terminologia {#section_A309B7E0B258467789A5CACDC1D923F3}

Os seguintes termos são úteis quando falamos de [!UICONTROL Direcionamento automático]:

| Termo | Definição |
|---|---|
| Multi-armed bandit | Uma abordagem multi-armed bandit à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado. |
| Floresta Aleatória | Random Forest é uma abordagem de aprendizado de máquina líder. No contexto da ciência de dados, é um método de classificação ou regressão de conjuntos que funciona por meio da construção de um grande número de árvores de decisão com base nos atributos do visitante e da visita. No Target, o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou maior receita por visita) para cada visitante específico. Para obter mais informações sobre o Random Forest no Target, consulte  [Algoritmo Random Forest](/help/c-activities/t-automated-personalization/algo-random-forest.md). |
| Amostragem de Thompson | O objetivo da Amostragem de Thompson é determinar qual experiência é a melhor em geral (não personalizada), enquanto minimiza o &quot;custo&quot; da procura dessa experiência. A amostragem de Thompson sempre escolhe um vencedor, mesmo que não haja diferença estatística entre duas experiências. Para obter mais informações, consulte [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Como funciona o [!UICONTROL direcionamento automático] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Saiba mais sobre os dados e algoritmos subjacentes ao [!UICONTROL Direcionamento automático] e à Personalização automatizada nos links abaixo:

| Termo | Detalhes |
|--- |--- |
| [Algoritmo Random Forest](/help/c-activities/t-automated-personalization/algo-random-forest.md) | O principal algoritmo de personalização do Target usado no [!UICONTROL Direcionamento automático] e na Personalização automatizada é o Random Forest. Métodos de conjunto como a Random Forest usam vários algoritmos de aprendizagem para obter desempenhos preditivos melhores dos que poderiam ser obtidos de qualquer um dos algoritmos de aprendizagem constituintes. O algoritmo Random Forest no sistema de personalização automatizada é um método de classificação ou regressão que opera por meio da construção de várias árvores de decisão na hora do treinamento. |
| [Fazer upload de dados para os algoritmos de personalização do Target](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Existem várias maneiras de inserir dados para modelos de [!UICONTROL Direcionamento automático] e Personalização automatizada. |
| [Coleta de dados para os algoritmos de personalização do Target](/help/c-activities/t-automated-personalization/ap-data.md) | Os algoritmos de personalização do Target coletam automaticamente uma variedade de dados. |

## Determinação da alocação de tráfego   {#section_AB3656F71D2D4C67A55A24B38092958F}

Dependendo do objetivo da sua atividade, você pode escolher uma alocação de tráfego diferente entre controle e experiências personalizadas. A prática recomendada é determinar esse objetivo antes de tornar sua atividade ativa.

A lista suspensa [!UICONTROL Alocação personalizada] permite escolher as seguintes opções:

* Avaliar o algoritmo de personalização
* Maximizar o tráfego de personalização
* Alocação personalizada

![Lista suspensa Meta de alocação](/help/c-activities/assets/split-new.png)

| Objetivo da atividade | Sugestão de alocação de tráfego | Compensações |
|--- |--- |--- |
| **Avaliar o algoritmo de personalização (50/50):** se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o controle e o algoritmo de destino. Esta divisão fornece a estimativa mais precisa do aumento. Recomenda-se usar com &quot;experiências aleatórias&quot; como controle. | Divisão de 50% controle / 50% experiência personalizada | <ul><li>Maximiza a precisão do aumento entre controle e personalizado</li><li>Relativamente menos visitantes terão uma experiência personalizada</li></ul> |
| **Maximizar o tráfego de personalização (90/10):** se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle, a fim de garantir que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. Observe que a desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você terá menos precisão em saber qual é o aumento exato. Independentemente da meta, esta é a divisão de tráfego recomendada ao usar uma experiência específica como controle. | A prática recomendada é usar uma divisão de 10% a 30% Controle / 70% - 90% Experiência personalizada | <ul><li>Maximiza o número de visitantes que têm uma experiência personalizada</li><li>Maximiza o aumento</li><li>Menos precisão quanto ao que é o aumento para a atividade</li></ul> |
| **Alocação personalizada** | Divida manualmente a porcentagem conforme desejado. | <ul><li>Você pode não conseguir os resultados desejados. Se você não tiver certeza, siga as sugestões para qualquer uma das opções anteriores</li></ul> |

Para ajustar a porcentagem de Controle, clique nos ícones na coluna Alocação. Você não pode diminuir o grupo de controle para menos de 10%.

![Alterar a alocação de tráfego do Direcionamento automático](/help/c-activities/assets/auto-target-control.png)

Você pode [selecionar uma experiência específica para usar como controle](/help/c-activities/t-automated-personalization/experience-as-control.md) ou usar a opção de experiência Aleatória.

## Quando você deve escolher o [!UICONTROL Direcionamento automático] em vez da Personalização automatizada? {#section_BBC4871C87944DD7A8B925811A30C633}

Existem vários cenários em que você pode preferir usar o [!UICONTROL Direcionamento automático] em vez da Personalização automatizada:

* Se você quiser definir toda a experiência, em vez de ofertas individuais que serão combinadas automaticamente para formar uma experiência.
* Se você quiser aproveitar o conjunto completo de recursos do Visual Experience Composer (VEC) não suportados pela [!UICONTROL Personalização automatizada]: o editor de código personalizado, vários públicos-alvo de experiência e muito mais.
* Se você quiser fazer mudanças estruturais na sua página em diferentes experiências. Por exemplo, se você quisesse reorganizar a ordem dos elementos em sua página inicial, o [!UICONTROL Direcionamento automático] seria mais apropriado para uso do que a Personalização automatizada.

## O que o [!UICONTROL Direcionamento automático] tem em comum com a personalização automatizada? {#section_2A601F482F9A44E38D4B694668711319}

**O algoritmo otimiza para um resultado favorável para cada visita.**

* O algoritmo prevê a propensão do visitante para a conversão (ou receita estimada da conversão) para oferecer a melhor experiência.
* Um visitante é elegível para uma nova experiência ao final de uma sessão existente (a menos que o visitante esteja no grupo de controle; nesse caso, a experiência que o visitante recebe em sua primeira visita permanece a mesma para visitas subsequentes).
* Em uma sessão, a previsão não muda, para manter a consistência visual.

**O algoritmo se adapta às mudanças no comportamento do visitante.**

* O multi-arm bandit garante que o modelo esteja sempre &quot;gastando&quot; uma pequena fração do tráfego para continuar aprendendo durante toda a vida do aprendizado da atividade e para evitar a exploração excessiva de tendências aprendidas anteriormente.
* Os modelos subjacentes são reconstruídos a cada 24 horas usando os dados mais recentes sobre o comportamento do visitante para garantir que o Target esteja sempre explorando as preferências atuais do visitante.
* Se o algoritmo não puder determinar as experiências vencedoras para os indivíduos, ele alternará automaticamente para mostrar a experiência geral de melhor desempenho enquanto continua a procurar por vencedores personalizados. A experiência de melhor desempenho é encontrada usando a [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

**O algoritmo otimiza continuamente para uma métrica de meta única.**

* Essa métrica pode ser baseada em conversão ou baseada em receita (mais especificamente, Receita por visitante).

**O Target coleta automaticamente informações sobre os visitantes para criar os modelos de personalização.**

* Para obter mais informações sobre os parâmetros usados &#x200B;&#x200B;no [!UICONTROL Direcionamento automático] e na Personalização automatizada, consulte [Coleção de dados da personalização automatizada](/help/c-activities/t-automated-personalization/ap-data.md).

**O Target usa automaticamente todos os públicos-alvo compartilhados da Experience Cloud para criar os modelos de personalização.**

* Você não precisa fazer nada específico para adicionar públicos-alvo ao modelo. Para obter informações sobre como usar os públicos-alvo da Experience Cloud com o Target, consulte  [Públicos-alvo da Experience Cloud](/help/c-integrating-target-with-mac/mmp.md)

**Os profissionais de marketing podem fazer upload de dados offline, pontuações de propensão ou outros dados personalizados para criar modelos de personalização.**

* Saiba mais sobre como[ carregar dados para Direcionamento automático e Personalização automatizada](/help/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## Como o [!UICONTROL Direcionamento automático] difere da Personalização automatizada? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL O Direcionamento automático] exige frequentemente menos tráfego do que a Personalização automatizada para um modelo personalizado a ser criado.**

Embora a quantidade de tráfego *por experiência* necessária para os modelos de [!UICONTROL Direcionamento automático] ou de [!UICONTROL Personalização automática] seja a mesma, geralmente há mais experiências em uma atividade de [!UICONTROL Personalização automatizada] do que uma atividade de Direcionamento automático. Por exemplo, se você tivesse uma atividade de [!UICONTROL Personalização automática] em que criou duas ofertas por local com dois locais, haveria quatro (2 = 4) experiências totais incluídas na atividade (sem exclusões). Usando o [!UICONTROL Direcionamento automático], você pode definir a experiência 1 para incluir a oferta 1 no local 1 e a oferta 2 no local 2 e a experiência 2 para incluir a oferta 1 no local 1 e a oferta 2 no local 2. Como o [!UICONTROL Direcionamento automático] permite que você tenha várias alterações em uma experiência, é possível reduzir o número total de experiências em sua atividade.

Para o [!UICONTROL Direcionamento automático], as regras básicas podem ser usadas para entender os requisitos de tráfego:

* **Quando a conversão é a sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia e por experiência, além disso, a atividade deve ter pelo menos 7.000 visitas e 350 conversões.
* **Quando a Receita por visita é sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia e por experiência, além disso, a atividade deve ter pelo menos 1.000 conversões por experiência. O RPV geralmente requer mais dados para criar modelos devido à maior variação de dados que normalmente existe na receita de visitas em comparação com a taxa de conversão.

**[!UICONTROL O Direcionamento automático] possui uma funcionalidade de configuração completa.**

* Como o [!UICONTROL Direcionamento automático] é incorporado no fluxo de trabalho da atividade A/B, o [!UICONTROL Direcionamento automático] se beneficia do Visual Experience Composer (VEC) mais maduro e completo. Você também pode utilizar os [links de controle de qualidade](/help/c-activities/c-activity-qa/activity-qa.md) com o [!UICONTROL Direcionamento automático].

**[!UICONTROL O Direcionamento automático] fornece uma extensa estrutura de testes online.**

* O multi-arm bandit é parte de uma estrutura de testes online maior que permite que nossos cientistas de dados e pesquisadores entendam os benefícios de suas melhorias contínuas em condições do mundo real.
* No futuro, esse banco de testes nos permitirá abrir nossa plataforma de aprendizagem de máquina para nossos clientes com conhecimento de dados, de modo que eles possam trazer seus próprios modelos para aumentar os modelos do Target.

## Relatórios e [!UICONTROL Direcionamento automático] {#section_42EE7F5E65E84F89A872FE9921917F76}

Para obter mais informações, consulte [Relatório de resumo do direcionamento automático](/help/c-reports/auto-target-summary-report.md) na seção [Relatórios](/help/c-reports/reports.md).

## Vídeo de treinamento: Compreensão das Atividades de Público alvo automático ![emblema de visão geral](/help/assets/overview.png)

Este vídeo explica como configurar uma atividade A/B de [!UICONTROL Direcionamento automático].

Depois de concluir este treinamento, você será capaz de:

* Definir teste de [!UICONTROL Direcionamento automático]
* Comparar e contrastar Direcionamento automático para [!UICONTROL personalização automatizada]
* Criar atividades de [!UICONTROL Direcionamento automático]

>[!VIDEO](https://video.tv.adobe.com/v/18558)