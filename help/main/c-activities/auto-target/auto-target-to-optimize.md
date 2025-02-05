---
keywords: direcionamento automático;direcionamento;alocação de tráfego;perguntas frequentes;faq;solução de problemas;solucionar problemas
description: Saiba como uma atividade do [!UICONTROL Auto-Target] fornece a experiência mais personalizada para cada visitante com base nos perfis dos clientes e no comportamento de visitantes semelhantes.
title: O Que É Uma Atividade [!UICONTROL Auto-Target]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
source-git-commit: 32a91a41cd182d3a55ded7dea8c1c6ea6f46aa71
workflow-type: tm+mt
source-wordcount: '1828'
ht-degree: 18%

---

# Visão geral de [!UICONTROL Auto-Target]

[!UICONTROL Auto-Target] atividades no [!DNL Adobe Target] usam aprendizagem de máquina avançada para selecionar várias experiências de alto desempenho definidas pelo profissional de marketing para personalizar o conteúdo e gerar conversões. [!UICONTROL Auto-Target] oferece a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares.

>[!NOTE]
>
>* [!UICONTROL Auto-Target] está disponível como parte da solução [!DNL Target Premium]. Este recurso não está disponível no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações sobre os recursos avançados fornecidos por esta licença, consulte [Target Premium](/help/main/c-intro/intro.md).
>
>* [!UICONTROL Analytics for Target] (A4T) dá suporte a [!UICONTROL Auto-Target] atividades. Para obter mais informações, consulte [Suporte ao A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

## História de sucesso real usando o direcionamento automático {#success}

Um grande varejista de roupas usou recentemente uma atividade [!UICONTROL Auto-Target] com dez experiências baseadas em categorias de produto (além de controle aleatório) para fornecer o conteúdo correto a cada visitante. &quot;[!UICONTROL Add to Cart]&quot; foi escolhido como a métrica de otimização primária. As experiências direcionadas tiveram um aumento médio de 29,09%. Após a criação dos modelos [!UICONTROL Auto-Target], a atividade foi definida como 90% de experiências personalizadas.

Em apenas dez dias, mais de US$ 1.700.000 em aumento foram obtidos.

Continue lendo para saber como usar o [!UICONTROL Auto-Target] para aumentar o aumento e a receita para sua organização.

## Visão geral {#section_972257739A2648AFA7E7556B693079C9}

Ao [criar uma atividade A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) usando o fluxo de trabalho guiado de três etapas, escolha a opção **[!UICONTROL Auto-Target for personalized experiences]** na página **[!UICONTROL Targeting]** (etapa 2).

![Configurações do Método de Alocação de Tráfego](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

A opção [!UICONTROL Auto-Target] no fluxo de atividade A/B permite aproveitar a aprendizagem de máquina para personalizar com base em um conjunto de experiências definidas pelo profissional de marketing em um clique. O [!UICONTROL Auto-Target] foi projetado para fornecer otimização máxima, em comparação ao teste A/B tradicional ou [!UICONTROL Auto Allocate], determinando qual experiência exibir para cada visitante. Ao contrário de uma atividade A/B na qual o objetivo é encontrar um único vencedor, [!UICONTROL Auto-Target] determina automaticamente a melhor experiência para um determinado visitante. A melhor experiência é baseada no perfil do visitante e outras informações contextuais para fornecer uma experiência altamente personalizada.

De modo semelhante a [!UICONTROL Automated Personalization], [!UICONTROL Auto-Target] usa um [algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), um dos principais métodos de conjunto de ciência de dados, para determinar a melhor experiência para mostrar a um visitante. Como o [!UICONTROL Auto-Target] pode se adaptar às mudanças no comportamento do visitante, ele pode ser executado perpetuamente para fornecer um aumento. Às vezes, esse método é chamado de modo &quot;sempre ativo&quot;.

Ao contrário de uma atividade A/B na qual a alocação de experiência para um determinado visitante é fixa, o [!UICONTROL Auto-Target] otimiza a meta de negócios especificada em cada visita. Como em [!UICONTROL Auto Personalization], [!UICONTROL Auto-Target], por padrão, reserva parte do tráfego da atividade como um grupo de controle para medir o aumento. Os visitantes do grupo de controle recebem uma experiência aleatória na atividade.

## Considerações

Algumas considerações importantes devem ser levadas em conta ao usar o [!UICONTROL Auto-Target]:

* Você não pode alternar uma atividade específica de [!UICONTROL Auto-Target] para [!UICONTROL Automated Personalization], e o oposto.
* Você não pode alternar de [!UICONTROL Manual] alocação de tráfego (tradicional [!UICONTROL A/B Test]) para [!UICONTROL Auto-Target], e o oposto, depois que uma atividade é salva como rascunho.
* Um modelo é criado para identificar o desempenho da estratégia personalizada em relação ao tráfego disponibilizado aleatoriamente em relação ao envio de todo o tráfego para a experiência vencedora geral. Esse modelo considera somente ocorrências e conversões no ambiente padrão.

  O tráfego de um segundo conjunto de modelos é criado para cada grupo de modelagem (AP) ou experiência (AT). Para cada um desses modelos, são consideradas ocorrências e conversões em todos os ambientes.

  As solicitações são atendidas com o mesmo modelo, independentemente do ambiente. No entanto, a pluralidade do tráfego deve vir do ambiente padrão para garantir que a experiência vencedora geral identificada seja consistente com o comportamento real.

* Use no mínimo duas experiências.

## Terminologia {#section_A309B7E0B258467789A5CACDC1D923F3}

Os termos a seguir são úteis quando falamos de [!UICONTROL Auto-Target]:

| Termo | Definição |
|---|---|
| [Bandit multicampo](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | Uma abordagem multi-armed bandit à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado. |
| [Floresta Aleatória](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Random Forest é uma abordagem de aprendizado de máquina líder. Em linguagem da ciência de dados, é um método de classificação de conjunto, ou regressão, que funciona construindo muitas árvores de decisão com base nos atributos do visitante e da visita. Dentro de [!DNL Target], o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou a maior receita por visita) para cada visitante específico. |
| [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | O objetivo do Thompson Sampling é determinar qual experiência é a melhor em geral (não personalizada), minimizando o &quot;custo&quot; de encontrar essa experiência. A Amostragem de Thompson sempre escolhe um vencedor, mesmo se não houver diferença estatística entre duas experiências. |

## Como o [!UICONTROL Auto-Target] funciona {#section_77240E2DEB7D4CD89F52BE0A85E20136}

Saiba mais sobre os dados e algoritmos subjacentes ao [!UICONTROL Auto-Target] e ao [!UICONTROL Automated Personalization] nos links abaixo:

| Termo | Detalhes |
|--- |--- |
| [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | O principal algoritmo de personalização de [!DNL Target] usado em [!UICONTROL Auto-Target] e [!UICONTROL Automated Personalization] é o Random Forest. Métodos de conjunto, como Random Forest, usam vários algoritmos de aprendizagem para obter um melhor desempenho preditivo do que poderia ser obtido a partir de qualquer um dos algoritmos de aprendizagem constituintes. O algoritmo Random Forest nas atividades [!UICONTROL Automated Personalization] e [!UICONTROL Auto-Target] é um método de classificação ou regressão, que opera através da construção de uma variedade de árvores de decisão no momento do treinamento. |
| [Carregando Dados para os Algoritmos Personalization de  [!DNL Target]](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Há várias maneiras de inserir dados para modelos [!UICONTROL Auto-Target] e [!UICONTROL Automated Personalization]. |
| [Coleta de dados para os algoritmos Personalization de  [!DNL Target]](/help/main/c-activities/t-automated-personalization/ap-data.md) | Os algoritmos de personalização do [!DNL Target] coletam automaticamente vários dados. |

## Determinação da alocação de tráfego  {#section_AB3656F71D2D4C67A55A24B38092958F}

Dependendo do objetivo da sua atividade, você pode escolher uma alocação de tráfego diferente entre controle e experiências personalizadas. A prática recomendada é determinar esse objetivo antes de tornar sua atividade ativa.

A lista suspensa [!UICONTROL Custom Allocation] permite escolher entre as seguintes opções:

* [!UICONTROL Evaluate Personalization Algorithm (50/50)]
* [!UICONTROL Maximize Personalization Traffic (90/10)]
* [!UICONTROL Custom Allocation]

![Lista suspensa Meta de alocação](/help/main/c-activities/assets/split-new-ui.png)

A tabela a seguir explica as três opções:

| Objetivo da atividade | Sugestão de alocação de tráfego | Compensações |
|--- |--- |--- |
| **[!UICONTROL Evaluate Personalization Algorithm (50/50)]**: se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o controle e o algoritmo de destino. Esta divisão fornece a estimativa mais precisa do aumento. Recomenda-se usar com &quot;experiências aleatórias&quot; como controle. | Divisão de 50% controle / 50% experiência personalizada | <ul><li>Maximiza a precisão do aumento entre controle e personalizado</li><li>Relativamente menos visitantes têm uma experiência personalizada</li></ul> |
| **[!UICONTROL Maximize Personalization Traffic (90/10)]**: se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle, a fim de garantir que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. A desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você tem menos precisão em saber qual é o aumento exato. Independentemente da meta, esta é a divisão de tráfego recomendada ao usar uma experiência específica como controle. | A prática recomendada é usar uma divisão de 10% a 30% Controle / 70% - 90% Experiência personalizada | <ul><li>Maximiza o número de visitantes que têm uma experiência personalizada</li><li>Maximiza o aumento</li><li>Menos precisão quanto ao que é o aumento para a atividade</li></ul> |
| **Alocação personalizada** | Divida manualmente a porcentagem conforme desejado. | <ul><li>Você pode não conseguir os resultados desejados. Se você não tiver certeza, siga as sugestões para qualquer uma das opções anteriores</li></ul> |

Para ajustar a porcentagem de [!UICONTROL Control], clique em [!UICONTROL Experiences] no painel [!UICONTROL Traffic Allocation] e ajuste as porcentagens conforme desejado. Você não pode diminuir o grupo de controle para menos de 10%.

Você pode [selecionar uma experiência específica para usar como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou usar a opção de experiência Aleatória.

## Quando você deve escolher [!UICONTROL Auto-Target] em vez de [!UICONTROL Automated Personalization]? {#section_BBC4871C87944DD7A8B925811A30C633}

Há vários cenários nos quais você pode preferir usar o [!UICONTROL Auto-Target] sobre o [!UICONTROL Automated Personalization]:

* Se você quiser definir toda a experiência, em vez de ofertas individuais que são combinadas automaticamente para formar uma experiência.
* Se você quiser usar o conjunto completo de recursos do [!UICONTROL Visual Experience Composer] (VEC) não suportados pelo [!UICONTROL Auto Personalization]: o editor de código personalizado, vários públicos-alvo de experiência e muito mais.
* Se você quiser fazer mudanças estruturais na sua página em diferentes experiências. Por exemplo, se você deseja reorganizar elementos na sua página inicial, [!UICONTROL Auto-Target] é mais apropriado para uso do que [!UICONTROL Automated Personalization].

## O que [!UICONTROL Auto-Target] tem em comum com [!UICONTROL Automated Personalization]? {#section_2A601F482F9A44E38D4B694668711319}

### O algoritmo otimiza para um resultado favorável para cada visita.

* O algoritmo prevê a propensão de um visitante para conversão (ou receita estimada da conversão) para fornecer a melhor experiência.
* Um visitante é elegível para uma nova experiência no final de uma sessão existente (a menos que o visitante esteja no grupo de controle, nesse caso, a experiência atribuída ao visitante na primeira visita permanece a mesma para visitas subsequentes).
* Em uma sessão, a previsão não muda, para manter a consistência visual.

### O algoritmo se adapta a alterações no comportamento do visitante.

* O multi-arm bandit garante que o modelo está sempre &quot;gastando&quot; uma pequena fração de tráfego para continuar a aprender ao longo da vida da atividade de aprendizagem e para evitar a exploração excessiva de tendências anteriormente aprendidas.
* Os modelos subjacentes são recriados a cada 24 horas usando os dados de comportamento de visitante mais recentes para garantir que [!DNL Target] esteja sempre explorando as preferências de visitante em alteração.
* Se o algoritmo não puder determinar as experiências vencedoras para os indivíduos, ele alternará automaticamente para mostrar a experiência geral de melhor desempenho enquanto continua a procurar por vencedores personalizados. A experiência de melhor desempenho é encontrada usando a [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling).

### O algoritmo otimiza continuamente para uma única meta de métrica.

* Essa métrica pode ser baseada em conversão ou em receita (mais especificamente [!UICONTROL Revenue per Visit]).

### O [!DNL Target] coleta automaticamente informações sobre os visitantes para criar os modelos de personalização.

* Para obter mais informações sobre os parâmetros usados em [!UICONTROL Auto-Target] e [!UICONTROL Automated Personalization], consulte [Coleção de Dados da Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).

### [!DNL Target] usa automaticamente todos os [!DNL Adobe Experience Cloud] públicos-alvo compartilhados para criar os modelos de personalização.

* Você não precisa fazer nada específico para adicionar públicos-alvo ao modelo. Para obter informações sobre como usar o [!DNL Experience Cloud Audiences] com [!DNL Target], consulte [Públicos-alvo da Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).

### Os profissionais de marketing podem fazer upload de dados offline, pontuações de propensão ou outros dados personalizados para criar modelos de personalização.

* Saiba mais sobre [o carregamento de dados para [!UICONTROL Auto-Target] e [!UICONTROL Automated Personalization]](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

## Qual a diferença entre [!UICONTROL Auto-Target] e [!UICONTROL Automated Personalization]? {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

### O [!UICONTROL Auto-Target] exige frequentemente menos tráfego do que o [!UICONTROL Automated Personalization] para que um modelo personalizado seja compilado.

Embora a quantidade de tráfego *por experiência* necessária para os modelos [!UICONTROL Auto-Target] ou [!UICONTROL Auto Personalization] sejam a mesma, geralmente há mais experiências em uma atividade [!UICONTROL Automated Personalization] do que uma atividade [!UICONTROL Auto-Target].

Por exemplo, se você tivesse uma atividade [!UICONTROL Auto Personalization] em que criou duas ofertas por local com dois locais, haveria quatro (2 = 4) experiências totais incluídas na atividade (sem exclusões). Usando o [!UICONTROL Auto-Target], você pode definir a experiência 1 para incluir a oferta 1 no local 1 e a oferta 2 no local 2 e a experiência 2 para incluir a oferta 1 no local 1 e a oferta 2 no local 2. Como [!UICONTROL Auto-Target] permite que você tenha várias alterações em uma experiência, é possível reduzir o número total de experiências em sua atividade.

Para [!UICONTROL Auto-Target], as regras básicas podem ser usadas para entender os requisitos de tráfego:

* **Quando [!UICONTROL Conversion] for sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia por experiência, e além disso a atividade deve ter pelo menos 7.000 visitas e 350 conversões.
* **Quando [!UICONTROL Revenue per Visit] for sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia por experiência, e além disso a atividade deve ter pelo menos 1.000 conversões por experiência. O RPV geralmente requer mais dados para criar modelos devido à maior variação de dados que normalmente existe na receita de visitas em comparação com a taxa de conversão.

### [!UICONTROL Auto-Target] possui uma funcionalidade de configuração completa.

* Como [!UICONTROL Auto-Target] está inserido no fluxo de trabalho de atividade A/B, [!UICONTROL Auto-Target] se beneficia do [!UICONTROL Visual Experience Composer] (VEC) mais maduro e completo. Você também pode usar [links de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md) com [!UICONTROL Auto-Target].

### [!UICONTROL Auto-Target] fornece uma extensa estrutura de testes online.

* O multi-arm bandit faz parte de uma estrutura maior de testes online, permitindo que cientistas de dados e pesquisadores do [!DNL Adobe] entendam os benefícios de suas melhorias contínuas nas condições do mundo real.
* Futuramente, este teste permitirá a abertura da plataforma de aprendizado de máquina [!DNL Adobe] para clientes com conhecimento de dados, para que eles possam trazer seus próprios modelos para aumentar os modelos [!DNL Target].

## Relatórios e [!UICONTROL Auto-Target] {#section_42EE7F5E65E84F89A872FE9921917F76}

Para obter mais informações, consulte [Relatórios e Direcionamento automático](/help/main/c-activities/auto-target/reporting-and-auto-target.md).
