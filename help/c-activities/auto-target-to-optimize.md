---
keywords: auto-target;targeting;traffic allocation;frequently aske questions;faq;troubleshooting;trouble shooting
description: O Público alvo automático no Adobe Target usa o aprendizado de máquina avançado para selecionar entre várias experiências definidas pelo profissional de marketing de alto desempenho para personalizar o conteúdo e gerar conversões. O Direcionamento automático veicula a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares.
title: Direcionamento automático
feature: auto-target
topic: Standard
uuid: fce769d2-9e7f-4064-add7-76e1fc394b4f
translation-type: tm+mt
source-git-commit: 252bea6810e54c0592a14559874f872e39ae261d
workflow-type: tm+mt
source-wordcount: '3731'
ht-degree: 83%

---


# ![PREMIUM](/help/assets/premium.png) Direcionamento automático

O [!UICONTROL Direcionamento automático] usa aprendizagem de máquina avançada para selecionar várias experiências de alto desempenho definidas pelo profissional de marketing para personalizar o conteúdo e gerar conversões. O Direcionamento automático veicula a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares.

>[!NOTE]
>
>O [!UICONTROL Direcionamento automático] está disponível como parte da solução do [!DNL Target Premium]. Este recurso não está disponível no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações sobre os recursos avançados fornecidos por esta licença, consulte [Target Premium](/help/c-intro/intro.md).

## História de sucesso real usando o Público alvo automático {#success}

Recentemente, um grande varejista de roupas usou uma atividade de Público alvo  automático com dez experiências baseadas em categorias de produtos (além de controle aleatório) para fornecer o conteúdo correto a cada visitante. &quot;[!UICONTROL Adicionar ao carrinho]&quot; foi escolhida como a métrica de otimização primária. As experiências direcionadas tiveram um aumento médio de 29,09%. Depois de criar os modelos de Público alvo  automático, a atividade foi definida para 90% de experiências personalizadas.

Em apenas dez dias, mais de US$ 1.700.000 em incentivo foram alcançados.

Continue lendo para saber como usar o Público alvo  automático para aumentar o incentivo e a receita de sua organização.

## Visão geral {#section_972257739A2648AFA7E7556B693079C9}

[Ao criar uma atividade A/B usando o fluxo de trabalho guiado de três etapas](../c-activities/t-test-ab/t-test-create-ab/test-create-ab.md#task_68C8079BF9FF4625A3BD6680D554BB72), é possível optar por alocar o tráfego usando a opção [!UICONTROL Direcionamento automático para experiências personalizadas]:

![Opção de Direcionamento automático para experiências personalizadas](/help/c-activities/assets/auto-target-ui-new.png)

A opção de [!UICONTROL Direcionamento automático] no fluxo de atividade A/B permite aproveitar a aprendizagem de máquina para personalizar com base em um conjunto de experiências definidas pelo profissional de marketing em um clique. O [!UICONTROL direcionamento automático] foi projetado para fornecer otimização máxima, em comparação com o teste A/B tradicional ou Alocação automática, determinando qual experiência exibir para cada visitante. Ao contrário de uma atividade A/B na qual o objetivo é encontrar um único vencedor, o [!UICONTROL direcionamento automático] determina automaticamente a melhor experiência para um determinado visitante (com base em seu perfil e outras informações contextuais) para oferecer uma experiência altamente personalizada.

Do mesmo modo que a Personalização automatizada, o [!UICONTROL Direcionamento automático] usa um algoritmo Random Forest, um dos principais métodos de conjunto de ciência de dados, para determinar a melhor experiência para mostrar a um visitante. Como o [!UICONTROL Direcionamento automático] pode se adaptar às mudanças no comportamento do visitante, ele pode ser executado perpetuamente para fornecer um aumento. Às vezes, isso é chamado de modo &quot;sempre ativo&quot;.

Ao contrário de uma atividade A/B na qual a alocação de experiência para um determinado visitante é fixa, o [!UICONTROL Direcionamento automático] otimiza a meta de negócios especificada em cada visita. Como na [!UICONTROL Personalização automática], o [!UICONTROL Direcionamento automático], por padrão, reserva parte do tráfego da atividade como um grupo de controle para medir o aumento. Os visitantes do grupo de controle recebem uma experiência aleatória na atividade.

## Considerações

There are a few important considerations to keep in mind when using [!UICONTROL Auto-Target]:

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
| Floresta Aleatória | Random Forest é uma abordagem de aprendizado de máquina líder. No contexto da ciência de dados, é um método de classificação ou regressão de conjuntos que funciona por meio da construção de um grande número de árvores de decisão com base nos atributos do visitante e da visita. No Target, o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou maior receita por visita) para cada visitante específico. Para obter mais informações sobre o Random Forest no Target, consulte  [Algoritmo Random Forest](../c-activities/t-automated-personalization/algo-random-forest.md#concept_48F3CDAA16A848D2A84CDCD19DAAE3AA). |
| Amostragem de Thompson | O objetivo da Amostragem de Thompson é determinar qual experiência é a melhor em geral (não personalizada), enquanto minimiza o &quot;custo&quot; da procura dessa experiência. A amostragem de Thompson sempre escolhe um vencedor, mesmo que não haja diferença estatística entre duas experiências. Para obter mais informações, consulte [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling). |

## Como funciona o [!UICONTROL direcionamento automático] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Saiba mais sobre os dados e algoritmos subjacentes ao [!UICONTROL Direcionamento automático] e à Personalização automatizada nos links abaixo:

| Termo | Detalhes |
|--- |--- |
| [Algoritmo Random Forest](/help/c-activities/t-automated-personalization/algo-random-forest.md) | O principal algoritmo de personalização do Target usado no [!UICONTROL Direcionamento automático] e na Personalização automatizada é o Random Forest. Métodos de conjunto como a Random Forest usam vários algoritmos de aprendizagem para obter desempenhos preditivos melhores dos que poderiam ser obtidos de qualquer um dos algoritmos de aprendizagem constituintes. O algoritmo Random Forest no sistema de personalização automatizada é um método de classificação ou regressão que opera por meio da construção de várias árvores de decisão na hora do treinamento. |
| [Fazer upload de dados para os algoritmos de personalização do Target](/help/c-activities/t-automated-personalization/algo-random-forest.md) | Existem várias maneiras de inserir dados para modelos de [!UICONTROL Direcionamento automático] e Personalização automatizada. |
| [Coleta de dados para os algoritmos de personalização do Target](/help/c-activities/t-automated-personalization/ap-data.md) | Os algoritmos de personalização do Target coletam automaticamente uma variedade de dados. |

## Determinação da alocação de tráfego  {#section_AB3656F71D2D4C67A55A24B38092958F}

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

* Para obter mais informações sobre os parâmetros usados &#x200B;&#x200B;no [!UICONTROL Direcionamento automático] e na Personalização automatizada, consulte [Coleção de dados da personalização automatizada](../c-activities/t-automated-personalization/ap-data.md#reference_255BD3DE7AD04DC9B766E0BC78961058).

**O Target usa automaticamente todos os públicos-alvo compartilhados da Experience Cloud para criar os modelos de personalização.**

* Você não precisa fazer nada específico para adicionar públicos-alvo ao modelo. Para obter informações sobre como usar os públicos-alvo da Experience Cloud com o Target, consulte  [Públicos-alvo da Experience Cloud](../c-integrating-target-with-mac/mmp.md#concept_F4863DE4C92D4805AB690B4B3D487969)

**Os profissionais de marketing podem fazer upload de dados offline, pontuações de propensão ou outros dados personalizados para criar modelos de personalização.**

* Saiba mais sobre como[ carregar dados para Direcionamento automático e Personalização automatizada](../c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md#concept_85EA505B37E54514A1C8AB91553FEED6).

## Como o [!UICONTROL Direcionamento automático] difere da Personalização automatizada? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

**[!UICONTROL O Direcionamento automático] exige frequentemente menos tráfego do que a Personalização automatizada para um modelo personalizado a ser criado.**

Embora a quantidade de tráfego *por experiência* necessária para os modelos de [!UICONTROL Direcionamento automático] ou de [!UICONTROL Personalização automática] seja a mesma, geralmente há mais experiências em uma atividade de [!UICONTROL Personalização automatizada] do que uma atividade de Direcionamento automático. Por exemplo, se você tivesse uma atividade de [!UICONTROL Personalização automática] em que criou duas ofertas por local com dois locais, haveria quatro (2 = 4) experiências totais incluídas na atividade (sem exclusões). Usando o [!UICONTROL Direcionamento automático], você pode definir a experiência 1 para incluir a oferta 1 no local 1 e a oferta 2 no local 2 e a experiência 2 para incluir a oferta 1 no local 1 e a oferta 2 no local 2. Como o [!UICONTROL Direcionamento automático] permite que você tenha várias alterações em uma experiência, é possível reduzir o número total de experiências em sua atividade.

Para o [!UICONTROL Direcionamento automático], as regras básicas podem ser usadas para entender os requisitos de tráfego:

* **Quando a conversão é a sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia e por experiência, além disso, a atividade deve ter pelo menos 7.000 visitas e 350 conversões.
* **Quando a Receita por visita é sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia e por experiência, além disso, a atividade deve ter pelo menos 1.000 conversões por experiência. O RPV geralmente requer mais dados para criar modelos devido à maior variação de dados que normalmente existe na receita de visitas em comparação com a taxa de conversão.

**[!UICONTROL O Direcionamento automático] possui uma funcionalidade de configuração completa.**

* Como o [!UICONTROL Direcionamento automático] é incorporado no fluxo de trabalho da atividade A/B, o [!UICONTROL Direcionamento automático] se beneficia do Visual Experience Composer (VEC) mais maduro e completo. Você também pode utilizar os [links de controle de qualidade](../c-activities/c-activity-qa/activity-qa.md#concept_9329EF33DE7D41CA9815C8115DBC4E40) com o [!UICONTROL Direcionamento automático].

**[!UICONTROL O Direcionamento automático] fornece uma extensa estrutura de testes online.**

* O multi-arm bandit é parte de uma estrutura de testes online maior que permite que nossos cientistas de dados e pesquisadores entendam os benefícios de suas melhorias contínuas em condições do mundo real.
* No futuro, esse banco de testes nos permitirá abrir nossa plataforma de aprendizagem de máquina para nossos clientes com conhecimento de dados, de modo que eles possam trazer seus próprios modelos para aumentar os modelos do Target.

## Relatórios e [!UICONTROL Direcionamento automático] {#section_42EE7F5E65E84F89A872FE9921917F76}

Para obter mais informações, consulte [Relatório de resumo do direcionamento automático](../c-reports/auto-target-summary-report.md#concept_E2171F7B57C1417DAAD7E7909A3FB073) na seção [Relatórios](../c-reports/reports.md#concept_B5077F5503AA4C98901AA99EDCE6CDE6).

## Perguntas frequentes sobre direcionamento automático {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte as seguintes perguntas frequentes e respostas enquanto trabalha com atividades de Público alvo [!UICONTROL automático] :

### Quais são as práticas recomendadas para configurar uma atividade de [!UICONTROL Direcionamento automático]?

* Decida se o valor comercial de uma métrica de sucesso de Receita por visita (RPV) vale os requisitos adicionais de tráfego. O RPV normalmente precisa de pelo menos 1.000 conversões por experiência para que uma atividade funcione em comparação com a conversão.
* Decida sobre a alocação entre controle e experiências personalizadas antes de iniciar a atividade com base em suas metas.
* Determine se você tem tráfego suficiente para a página em que sua atividade de [!UICONTROL Direcionamento automático] será executada para modelos de personalização a serem criados em um período de tempo razoável.
   * Se você estiver testando o algoritmo de personalização, não altere experiências nem adicione/remova atributos de perfil enquanto a atividade estiver ativa.

* Considere a conclusão de uma atividade A/B entre as ofertas e os locais que você planeja usar em sua atividade de [!UICONTROL Direcionamento automático] para garantir que os locais e as ofertas tenham impacto na meta de otimização. Se uma atividade A/B não demonstrar uma diferença significativa, o [!UICONTROL Direcionamento automático] provavelmente também não gerará aumento.

   * Se um teste A/B não mostra diferenças estatisticamente significativas entre as experiências, é provável que as ofertas que você está considerando não são suficientemente diferentes umas das outras, os locais selecionados não afetam a métrica de sucesso ou a meta de otimização está muito distante no funil de conversão a ser afetado pelas ofertas escolhidas.

* Tente não fazer mudanças substanciais nas experiências durante o curso da atividade.

### As marcas de verificação que indicam que um modelo foi criado para aquela experiência são atualizadas se o intervalo de datas do relatório for alterado?

Não, as marcas de verificação para geração de modelos mostram apenas os modelos construídos até o momento. Não há como voltar e ver quando um modelo foi concluído.

### Se um visitante NÃO vir a atividade de [!UICONTROL Direcionamento automático] e converter, a conversão conta em minha atividade?

Não, apenas os visitantes qualificados para exibir a atividade de [!UICONTROL Direcionamento automático] são contados nos relatórios.

### Minha atividade de [!UICONTROL Direcionamento automático] parece não estar gerando nenhum aumento. O que está acontecendo?

Há quatro fatores necessários para uma atividade de [!UICONTROL Dimensionamento automático] gerar aumento:

* As ofertas precisam ser diferentes o suficiente para influenciar os visitantes.
* As ofertas precisam estar localizadas em um lugar que faça diferença na meta de otimização.
* Deve haver tráfego e &quot;potência&quot; estatística suficiente no teste para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

O melhor curso de ação é garantir que o conteúdo e os locais que compõem as experiências da atividade realmente façam diferença nas taxas de resposta geral usando um teste A/B simples e não personalizado. Certifique-se de calcular os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e executar o teste A/B por um período fixo sem interrompê-lo ou fazer quaisquer alterações.

Se os resultados de um teste A/B mostram um aumento estatisticamente significativo em uma ou mais das experiências, é provável que uma atividade personalizada funcione. Claro, a personalização pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre de ofertas/locais que não têm um impacto suficientemente grande na meta da otimização para serem detectados com significância estatística.

### Quando devo interromper minha atividade de [!UICONTROL Direcionamento automático]?

O [!UICONTROL Direcionamento automático] pode ser usado como personalização &quot;sempre ativa&quot; que otimizará constantemente. Especialmente para conteúdo permanente, não há necessidade de interromper sua atividade de [!UICONTROL Direcionamento automático].

Se você quiser fazer alterações substanciais no conteúdo em sua atividade de [!UICONTROL Direcionamento automático], a prática recomendada é iniciar uma nova atividade para que outros usuários que revisem relatórios não confundam ou relacionem resultados anteriores com conteúdo diferente.

### Por quanto tempo devo esperar que os modelos sejam construídos? {#how-long}

The length of time it takes for models to build in your [!UICONTROL Auto-Target] activity typically depends on the traffic to your selected activity location(s) and conversion rates associated with you activity success metric.

[!UICONTROL O Público alvo] automático não tentará criar um modelo personalizado para uma determinada experiência até que haja pelo menos 50 conversões para essa experiência. Além disso, se o modelo criado for de qualidade insuficiente (conforme determinado pela avaliação offline dos dados de &quot;teste&quot; em espera, usando [uma métrica conhecida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), o modelo não será usado para servir o tráfego de forma personalizada.

Alguns outros pontos para ter em mente sobre a construção de modelos do [!UICONTROL Público alvo]automático:

* Quando uma atividade está ativa, o [!UICONTROL AutoPúblico alvo] considera até os últimos 45 dias de dados servidos aleatoriamente ao tentar criar modelos (ou seja, controlar o tráfego, mais alguns dados fornecidos aleatoriamente pelo nosso algoritmo).
* Quando [!UICONTROL Receita por visita] é sua métrica de sucesso, essas atividades geralmente exigem mais dados para construir modelos devido à maior variação de dados que normalmente existe na receita da visita em comparação com a taxa de conversão.
* Como os modelos são criados por experiência, substituir uma experiência por outra significa que tráfego suficiente (ou seja, pelo menos 50 conversões) deve ser coletado para a nova experiência antes que os modelos personalizados possam ser recriados.

### Um modelo é construído na minha atividade. As visitas a essa experiência são personalizadas?

Não, deve haver pelo menos dois modelos construídos em sua atividade para que a personalização comece.

### Quando posso ver os resultados da minha atividade de [!UICONTROL Direcionamento automático]?

Você pode começar a ver os resultados da sua atividade de [!UICONTROL Direcionamento automático] depois de ter pelo menos duas experiências com modelos construídos (marca de seleção verde) para a experiência que os modelos construíram.

### Posso definir uma experiência específica para ser usada como controle?

É possível selecionar uma experiência para ser usada como controle ao criar uma atividade de [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou de [Direcionamento automático](/help/c-activities/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado com relação ao tráfego de controle para essa experiência única.

Para obter mais informações, consulte [Usar uma experiência específica como controle](/help/c-activities/t-automated-personalization/experience-as-control.md).

### É possível alterar a métrica de objetivo no meio de uma atividade de Público alvo automático? {#change-metric}

Não recomendamos que você altere a métrica de objetivo a meio de uma atividade. Embora seja possível alterar a métrica de objetivo durante uma atividade usando a [!DNL Target] interface do usuário, você deve sempre start uma nova atividade. Não garantimos o que acontece se você alterar a métrica de objetivo em uma atividade após sua execução.

Esta recomendação se aplica a [!UICONTROL Autoalocação], Público alvo automático e atividades [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como a fonte do relatórios.

### Posso usar a opção Redefinir dados do relatório ao executar uma atividade de Público alvo automático?

Não é recomendável usar a opção [!UICONTROL Redefinir dados] de relatório para atividades de Público alvo  automático. Embora remova os dados de relatórios visíveis, essa opção não remove todos os registros de treinamento do modelo de Público alvo  automático. Em vez de usar a opção [!UICONTROL Redefinir dados] do relatório para atividades de Público alvo  automático, crie uma nova atividade e desative a atividade original. (Observação: Esta orientação também se aplica a [!UICONTROL Autoalocação] e atividades [!UICONTROL Automated Personalization] .)

## Solução de problemas do [!UICONTROL Direcionamento automático] {#section_23995AB813F24525AF294D20A20875C8}

Às vezes, as atividades não acontecem como o esperado. Aqui estão alguns possíveis desafios que você pode enfrentar ao usar o [!UICONTROL Direcionamento automático] e algumas soluções sugeridas.

**Minha atividade de [!UICONTROL Direcionamento automático] está demorando muito para criar modelos.**

Há várias alterações de configuração de atividade que podem diminuir o tempo esperado para criar modelos, incluindo o número de experiências em sua atividade de [!UICONTROL Direcionamento automático], o tráfego para seu site e sua métrica de sucesso selecionada.

**Solução:** revise a configuração da atividade e veja se deseja fazer alguma alteração para melhorar a velocidade de criação dos modelos.

* Se sua métrica de sucesso estiver definida como RPV, será possível mudar para conversão? As atividades de conversão tendem a exigir menos tráfego para criar modelos. Você não perderá os dados da atividade se alterar a métrica de sucesso de RPV para conversão.
* Sua métrica de sucesso está bem abaixo do funil de vendas de suas experiências de atividade? Uma taxa de conversão de atividade menor aumentará os requisitos de tráfego necessários para a criação de modelos, pois é necessário um número mínimo de conversões.
* Há algumas experiências que você pode abandonar em sua atividade? A diminuição do número de experiências em uma atividade irá diminuir a quantidade de tempo para construir modelos.
* Existe uma página de tráfego mais alto onde essa atividade seria mais bem-sucedida? Quanto mais tráfego e conversões em seus locais de atividade, mais rápidos serão os modelos.

**Minha atividade de [!UICONTROL Direcionamento automático] não está gerando nenhum aumento.**

Há quatro fatores necessários para uma atividade de AP gerar aumento:

* As ofertas precisam ser diferentes o suficiente para influenciar os visitantes.
* As ofertas precisam estar localizadas em um lugar que faça diferença na meta de otimização.
* Deve haver tráfego e &quot;potência&quot; estatística suficiente no teste para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

**Solução:** primeiro, verifique se sua atividade está personalizando o tráfego. Se os modelos não são criados para todas as experiências, sua atividade de [!UICONTROL Direcionamento automático] ainda estará apresentando aleatoriamente uma parte significativa das visitas para tentar criar todos os modelos o mais rápido possível. Se os modelos não forem criados, o [!UICONTROL Direcionamento automático] não está personalizando o tráfego.

Em seguida, verifique se as ofertas e os locais de atividade realmente fazem diferença nas taxas de resposta gerais usando um teste A/B simples e não personalizado. Certifique-se de calcular os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e executar o teste A/B por um período fixo sem interrompê-lo ou fazer quaisquer alterações. Se um resultado do teste A/B mostrar um aumento estatisticamente significativo em uma ou mais das experiências, é provável que uma atividade personalizada funcione. Claro, a personalização pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre de ofertas/locais que não têm um impacto suficientemente grande na meta da otimização para serem detectados com significância estatística.

**As métricas dependentes de métrica de conversão nunca convertem.**

Isso é esperado.

Em uma atividade de [!UICONTROL Direcionamento automático], depois que uma métrica de conversão (objetivo de otimização ou de postagem) é convertida, o usuário é liberado da experiência e a atividade é reiniciada.

Por exemplo, há uma atividade com uma métrica de conversão (C1) e uma métrica adicional (A1). A1 depende de C1. Quando um visitante entra na atividade pela primeira vez, e os critérios de conversão de A1 e C1 não são convertidos, a métrica A1 não é convertida por depender da métrica de sucesso. Se o visitante converte C1 e depois converte A1, A1 ainda não é convertida porque, assim que C1 é convertida, o visitante é liberado.

## Vídeo de treinamento: Entendendo as atividades de direcionamento automático ![Etiqueta de visão geral](/help/assets/overview.png)

Este vídeo explica como configurar uma atividade A/B de [!UICONTROL Direcionamento automático].

Depois de concluir este treinamento, você será capaz de:

* Definir teste de [!UICONTROL Direcionamento automático]
* Comparar e contrastar Direcionamento automático para [!UICONTROL personalização automatizada]
* Criar atividades de [!UICONTROL Direcionamento automático]

>[!VIDEO](https://video.tv.adobe.com/v/18558)