---
keywords: direcionamento automático;direcionamento;alocação de tráfego;perguntas frequentes;faq;solução de problemas;solucionar problemas
description: Saiba como uma atividade de [!UICONTROL Direcionamento automático] fornece a experiência mais personalizada para cada visitante com base nos perfis dos clientes e no comportamento de visitantes semelhantes.
title: O Que É Uma Atividade De [!UICONTROL Direcionamento Automático]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Auto-Target
exl-id: 59ca30dc-45a0-4129-b832-84e1132d3b69
TQID: 'https://experienceleague.adobe.com/uKmfIlOcT-tZgOjuvERXuif-Y5-2Jw3prtPbuBjv1is'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: fff07a91-d479-45f4-ae95-9762e79b1b7c
    internal-label: Shared audiences
  - id: db15a02f-03cd-46fe-a53e-02064cdeadfa
    internal-label: Auto target
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
    internal-label: Customer profiles
source-git-commit: de439134b0ee5aa795ae255bba852b9b6f10da12
workflow-type: tm+mt
source-wordcount: '2072'
ht-degree: 12%
---
# Introdução ao [!UICONTROL Direcionamento automático] {#auto-target-overview}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como uma atividade de **[!UICONTROL Direcionamento automático]** fornece a experiência mais personalizada para cada visitante, como ela funciona, como escolher a alocação de tráfego e como ela se compara à **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

As atividades de **[!UICONTROL Direcionamento automático]** no [!DNL Adobe Target] usam aprendizagem de máquina avançada para selecionar várias experiências de alto desempenho definidas pelo profissional de marketing para personalizar o conteúdo e gerar conversões. O **[!UICONTROL Direcionamento automático]** retorna a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares.

>[!NOTE]
>
>* O **[!UICONTROL Direcionamento automático]** está disponível como parte da solução [!DNL Target Premium]. Este recurso não está disponível no [!DNL Target Standard] sem uma licença do [!DNL Target Premium]. Para obter mais informações sobre os recursos avançados fornecidos por esta licença, consulte [Target Premium](/help/main/c-intro/intro.md).
>
>* O **[!UICONTROL Analytics for Target]** (A4T) dá suporte a **[!UICONTROL atividades de Direcionamento automático]**. Para obter mais informações, consulte [Suporte ao A4T para atividades de Alocação automática e Direcionamento automático](/help/main/c-integrating-target-with-mac/a4t/a4t-at-aa.md).

Ao [criar uma atividade A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) com o fluxo de trabalho guiado de três etapas, escolha a opção **[!UICONTROL Direcionamento automático para experiências personalizadas]** na página **[!UICONTROL Direcionamento]** (etapa 2). Para as etapas, consulte [Criar uma atividade de Direcionamento automático](/help/main/c-activities/auto-target/create-auto-target.md).

![Configurações do Método de Alocação de Tráfego](/help/main/c-activities/automated-traffic-allocation/assets/auto-target.png)

Essa opção no fluxo de atividade A/B permite usar o aprendizado de máquina para personalizar o conteúdo, com base em um conjunto de experiências definidas pelo profissional de marketing, em um clique. O **[!UICONTROL Direcionamento automático]** foi projetado para fornecer otimização máxima, em comparação com o teste A/B tradicional ou a **[!UICONTROL Alocação automática]**, determinando qual experiência exibir para cada visitante. Ao contrário de uma atividade A/B, na qual o objetivo é encontrar um único vencedor, o **[!UICONTROL Direcionamento automático]** determina automaticamente a melhor experiência para um determinado visitante. A melhor experiência é baseada no perfil do visitante e em outras informações contextuais.

De modo semelhante ao **[!UICONTROL Automated Personalization]**, o **[!UICONTROL Direcionamento automático]** usa um [algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md), um dos principais métodos de conjunto de ciência de dados, para determinar a melhor experiência para mostrar a um visitante. O **[!UICONTROL Direcionamento automático]** pode se adaptar às mudanças no comportamento do visitante, para que possa ser executado perpetuamente para fornecer um aumento. Às vezes, esse método é chamado de modo &quot;sempre ativo&quot;.

Ao contrário de uma atividade A/B, na qual a alocação de experiência para um determinado visitante é fixa, o **[!UICONTROL Direcionamento automático]** otimiza a meta de negócios especificada em cada visita. Como no **[!UICONTROL Automated Personalization]**, o **[!UICONTROL Direcionamento automático]** reserva parte do tráfego da atividade como um grupo de controle por padrão, para medir o aumento. Os visitantes do grupo de controle recebem uma experiência aleatória na atividade.

## Considerações {#considerations}

Lembre-se dos seguintes pontos ao usar o **[!UICONTROL Direcionamento automático]**:

* Preste atenção à forma de atividade. O desempenho depende mais do número de locais × ofertas do que da contagem bruta de experiência. Combinações cartesianas grandes podem retardar o carregamento e a edição no **[!UICONTROL Visual Experience Composer]**, mesmo abaixo dos limites de experiência documentados.

  Como prática recomendada, mantenha as atividades do **[!UICONTROL Direcionamento automático]** e do **[!UICONTROL Automated Personalization]** em 4 a 6 locais com 4 a 6 ofertas por local. Configurações maiores não são recomendadas. Estas atividades são compiladas diretamente na etapa **[!UICONTROL Experiências]**, portanto, a interface do usuário do [!DNL Target] poderá mostrar avisos incorporados ou bloquear o salvamento quando a configuração exceder os limites com suporte.

* Você não pode alternar uma atividade específica de **[!UICONTROL Direcionamento automático]** para **[!UICONTROL Automated Personalization]**, ou o oposto.
* Você não pode alternar de **[!UICONTROL Alocação de tráfego manual]** (tradicional **[!UICONTROL Teste A/B]**) para **[!UICONTROL Direcionamento automático]**, ou o oposto, depois que uma atividade é salva como rascunho.
* Um modelo é criado para identificar o desempenho da estratégia personalizada em relação ao tráfego disponibilizado aleatoriamente em relação ao envio de todo o tráfego para a experiência vencedora geral. Esse modelo considera somente ocorrências e conversões no ambiente padrão.

  Um segundo conjunto de modelos é criado para cada grupo de modelagem (AP) ou experiência (AT). Para cada um desses modelos, são consideradas ocorrências e conversões em todos os ambientes.

  As solicitações são atendidas com o mesmo modelo, independentemente do ambiente. No entanto, a pluralidade do tráfego deve vir do ambiente padrão para garantir que a experiência vencedora geral identificada seja consistente com o comportamento real.

* Use no mínimo duas experiências.

## Terminologia {#section_A309B7E0B258467789A5CACDC1D923F3}

Os termos a seguir são úteis quando falamos de **[!UICONTROL Direcionamento automático]**:

| Termo | Definição |
|---|---|
| [Bandit multi-armado](https://en.wikipedia.org/wiki/Multi-armed_bandit){target=_blank} | Uma abordagem multi-armed bandit à otimização equilibra o aprendizado exploratório e o aproveitamento desse aprendizado. |
| [Floresta Aleatória](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | Random Forest é uma abordagem de aprendizado de máquina líder. Em termos de ciência de dados, é uma classificação de conjunto, ou método de regressão, que funciona construindo muitas árvores de decisão com base nos atributos do visitante e da visita. Dentro de [!DNL Target], o Random Forest é usado para determinar qual experiência deve ter a maior probabilidade de conversão (ou a maior receita por visita) para cada visitante específico. |
| [Amostragem de Thompson](https://en.wikipedia.org/wiki/Thompson_sampling){target=_blank} | O objetivo do Thompson Sampling é determinar qual experiência é a melhor em geral (não personalizada), minimizando o &quot;custo&quot; de encontrar essa experiência. O Thompson Sampling sempre escolhe um vencedor, mesmo se não houver diferença estatística entre duas experiências. |

## Como funciona o [!UICONTROL Direcionamento automático] {#section_77240E2DEB7D4CD89F52BE0A85E20136}

As páginas a seguir descrevem os dados e algoritmos subjacentes ao **[!UICONTROL Direcionamento automático]** e ao **[!UICONTROL Automated Personalization]**:

| Tópico | Detalhes |
|--- |--- |
| [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) | O principal algoritmo de personalização de [!DNL Target], usado no **[!UICONTROL Direcionamento automático]** e no **[!UICONTROL Automated Personalization]**, é o Random Forest. Métodos de conjunto, como Random Forest, usam vários algoritmos de aprendizagem para obter um melhor desempenho preditivo do que poderia ser obtido a partir de qualquer um dos algoritmos de aprendizagem constituintes. O algoritmo Random Forest nas atividades **[!UICONTROL Automated Personalization]** e **[!UICONTROL Direcionamento automático]** é um método de classificação ou regressão, que opera através da construção de várias árvores de decisão no momento do treinamento. |
| [Carregando Dados Para [!DNL Target] Algoritmos Personalization](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md) | Há várias maneiras de inserir dados para modelos **[!UICONTROL Direcionamento automático]** e **[!UICONTROL Automated Personalization]**. |
| [Coleta de Dados para [!DNL Target] Algoritmos Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md) | Os algoritmos de personalização do [!DNL Target] coletam vários dados automaticamente. |

## Determine a alocação de tráfego {#section_AB3656F71D2D4C67A55A24B38092958F}

Dependendo da meta da sua atividade, você pode escolher uma alocação de tráfego diferente entre experiências de controle e personalizadas. A prática recomendada é determinar esse objetivo antes de tornar sua atividade ativa.

A lista suspensa **[!UICONTROL Alocação personalizada]** permite escolher as seguintes opções:

* **[!UICONTROL Avaliar Algoritmo Personalization (50/50)]**
* **[!UICONTROL Maximizar tráfego do Personalization (90/10)]**
* **[!UICONTROL Alocação personalizada]**

![Lista suspensa Meta de alocação](/help/main/c-activities/assets/split-new-ui.png)

A tabela a seguir explica as três opções:

| Objetivo da atividade | Sugestão de alocação de tráfego | Compensações |
|--- |--- |--- |
| **[!UICONTROL Avaliar o algoritmo de personalização (50/50):]** se o objetivo for testar o algoritmo, use uma divisão de visitantes de 50/50% entre o controle e o algoritmo de destino. Esta divisão fornece a estimativa mais precisa do aumento. Recomenda-se usar com &quot;experiências aleatórias&quot; como controle. | Divisão de 50% controle / 50% experiência personalizada | <ul><li>Maximiza a precisão do aumento entre controle e personalizado</li><li>Relativamente menos visitantes têm uma experiência personalizada</li></ul> |
| **[!UICONTROL Maximizar o tráfego do Personalization (90/10)]**: se o objetivo for criar uma atividade &quot;sempre ativa&quot;, coloque 10% dos visitantes no controle, a fim de garantir que haja dados suficientes para que os algoritmos continuem aprendendo ao longo do tempo. A desvantagem aqui é que, em troca da personalização de uma proporção maior de seu tráfego, você tem menos precisão em saber qual é o aumento exato. Independentemente da meta, esta é a divisão de tráfego recomendada ao usar uma experiência específica como controle. | A prática recomendada é usar uma divisão de 10% a 30% Controle / 70% - 90% Experiência personalizada | <ul><li>Maximiza o número de visitantes que têm uma experiência personalizada</li><li>Maximiza o aumento</li><li>Menos precisão quanto ao que é o aumento para a atividade</li></ul> |
| **[!UICONTROL Alocação personalizada]** | Divida manualmente a porcentagem conforme desejado. | <ul><li>Você pode não conseguir os resultados desejados. Se você não tiver certeza, siga as sugestões para qualquer uma das opções anteriores</li></ul> |

Para ajustar a porcentagem de **[!UICONTROL Controle]**, clique em **[!UICONTROL Experiências]** no painel **[!UICONTROL Alocação de tráfego]** e ajuste as porcentagens conforme desejado. Você não pode diminuir o grupo de controle para menos de 10%.

Você pode [selecionar uma experiência específica para usar como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md) ou usar a opção **[!UICONTROL Experiência aleatória]**.

## Comparar [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] {#compare-at-ap}

O **[!UICONTROL Direcionamento automático]** e o **[!UICONTROL Automated Personalization]** compartilham o mesmo algoritmo e dados, mas diferem em como as experiências são criadas e quanto tráfego os modelos precisam.

### O que os dois tipos de atividade têm em comum {#section_2A601F482F9A44E38D4B694668711319}

* **Otimização para cada visita.** O algoritmo prevê a propensão de um visitante para converter (ou a receita estimada da conversão) para fornecer a melhor experiência. Um visitante está qualificado para uma nova experiência no final de uma sessão existente. A exceção é um visitante do grupo de controle, que mantém a experiência atribuída na primeira visita. Em uma sessão, a previsão não muda para manter a consistência visual.
* **Adaptação a alterações no comportamento do visitante.** O bandido multi-armado sempre &quot;gasta&quot; uma pequena fração de tráfego para continuar a aprender durante a vida da atividade e para evitar a exploração excessiva de tendências previamente aprendidas. Os modelos subjacentes são recriados a cada 24 horas usando os dados de comportamento do visitante mais recentes. Se o algoritmo não puder determinar experiências vencedoras para indivíduos, ele alternará automaticamente para mostrar a experiência geral com melhor desempenho, encontrada usando o [Thompson Sampling](https://en.wikipedia.org/wiki/Thompson_sampling), enquanto continua a procurar vencedores personalizados.
* **Uma única métrica de meta.** O algoritmo otimiza continuamente para uma métrica, que pode ser baseada em conversão ou em receita (mais especificamente, **[!UICONTROL Receita por visita]**).
* **Coleta de dados automática.** O [!DNL Target] coleta automaticamente informações sobre os visitantes para criar os modelos de personalização. Para obter mais informações sobre os parâmetros usados, consulte [Coleção de dados da Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-data.md).
* **Públicos-alvo compartilhados.** [!DNL Target] usa automaticamente todos os [!DNL Adobe Experience Cloud] públicos-alvo compartilhados para criar os modelos de personalização. Não é necessário fazer nada específico para adicionar públicos-alvo ao modelo. Para obter informações sobre como usar o [!DNL Experience Cloud Audiences] com [!DNL Target], consulte [Públicos-alvo da Experience Cloud](/help/main/c-integrating-target-with-mac/mmp.md).
* **Dados personalizados.** Os profissionais de marketing podem fazer upload de dados offline, pontuações de propensão ou outros dados personalizados para criar modelos de personalização. Saiba mais sobre [como carregar dados para Direcionamento automático e Automated Personalization](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md).

### Como os dois tipos de atividades diferem {#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB}

Considere o **[!UICONTROL Direcionamento automático]** em vez do **[!UICONTROL Automated Personalization]** quando quiser definir toda a experiência, use o conjunto completo de recursos do **[!UICONTROL Visual Experience Composer]** (VEC) ou faça alterações estruturais na sua página.

| | [!UICONTROL Direcionamento automático] | [!UICONTROL Personalização automatizada] |
|---|---|---|
| **Definição de experiência** | Você define toda a experiência, que pode conter várias alterações. | Ofertas individuais são combinadas automaticamente para formar uma experiência. |
| **[!UICONTROL Recursos do Visual Experience Composer]** | O **[!UICONTROL Direcionamento automático]** está incorporado no fluxo de trabalho da atividade A/B, portanto, ele se beneficia do VEC mais maduro e completo. Você também pode usar [links de controle de qualidade](/help/main/c-activities/c-activity-qa/activity-qa.md). | O editor de código personalizado, vários públicos-alvo de experiência e outros recursos não são compatíveis. |
| **Alterações estruturais na página** | Mais apropriado. Por exemplo, você pode reorganizar elementos em sua página inicial. | Menos apropriado. |
| **Número de experiências** | Normalmente, menos, pois uma experiência pode conter várias alterações. | Normalmente mais, porque as experiências são todas as combinações de ofertas e locais. |
| **Tráfego necessário para criar os modelos** | Frequentemente menos no total. | Frequentemente, mais no total. |

A quantidade de tráfego *por experiência* necessária para criar os modelos é a mesma para ambos os tipos de atividade. O **[!UICONTROL Direcionamento automático]** exige frequentemente menos tráfego total porque geralmente tem menos experiências.

Por exemplo, em uma atividade do **[!UICONTROL Automated Personalization]** com duas ofertas por localização e dois locais, há quatro (2 × 2 = 4) experiências totais na atividade (sem exclusões). Em **[!UICONTROL Direcionamento automático]**, você pode definir a experiência 1 para incluir a oferta 1 no local 1 e a oferta 2 no local 2 e a experiência 2 para incluir a oferta 2 no local 1 e a oferta 1 no local 2. O **[!UICONTROL Direcionamento automático]** permite várias alterações em uma experiência, para que você possa reduzir o número total de experiências em sua atividade.

### Requisitos de tráfego para [!UICONTROL Direcionamento automático] {#traffic-requirements}

As seguintes regras básicas ajudam a entender os requisitos de tráfego:

* **Quando [!UICONTROL Conversão] for sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia por experiência. Além disso, a atividade deve ter pelo menos 7.000 visitas e 350 conversões.
* **Quando [!UICONTROL Receita por visita] for sua métrica de sucesso:** 1.000 visitas e pelo menos 50 conversões por dia por experiência. Além disso, a atividade deve ter pelo menos 1.000 conversões por experiência. **[!UICONTROL Receita por visita]** geralmente requer mais dados para criar modelos, pois a variação na receita de visitas geralmente é maior do que na taxa de conversão.

**[!UICONTROL Direcionamento automático]** também fornece uma extensa estrutura de testes online. O multi-armed bandit faz parte de uma estrutura maior de testes online que permite que cientistas e pesquisadores de dados do [!DNL Adobe] entendam os benefícios de suas melhorias contínuas nas condições do mundo real. Futuramente, este aparelho de teste permitirá que o [!DNL Adobe] abra sua plataforma de aprendizado de máquina para clientes com alto conhecimento de dados, para que eles possam trazer seus próprios modelos para aumentar os modelos [!DNL Target].

Para obter mais informações sobre relatórios, consulte [Relatórios e Direcionamento automático](/help/main/c-activities/auto-target/reporting-and-auto-target.md).
