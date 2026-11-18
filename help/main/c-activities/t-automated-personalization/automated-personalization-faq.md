---
keywords: solução de problemas;perguntas frequentes;Perguntas frequentes;personalização automatizada;controle;experiência padrão;práticas recomendadas;troubleshooting;frequency asked questions;FAQs;automated personalization;control;default experience;best practices
description: Explore uma lista de perguntas frequentes e respostas sobre as atividades do [!UICONTROL Automated Personalization] (AP) no [!UICONTROL Adobe Target].
title: Como posso encontrar perguntas frequentes sobre atividades do [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
TQID: 'https://experienceleague.adobe.com/cYdFwvkJDlfGYdcxql9iWGwNiTed4Lb2kC7JdN7xgdo'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: f0055dd2-93f3-4ac8-9abc-d69d4ed2d977
    internal-label: Automated personalization
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
    internal-label: Optimization
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
    internal-label: Machine learning
source-git-commit: 44c6bdd4ab818226e76477782d7e4238b49d5cdc
workflow-type: tm+mt
source-wordcount: '2088'
ht-degree: 6%
---
# Perguntas frequentes sobre o Automated Personalization {#ap-faq}

>[!BEGINSHADEBOX]

**Nesta página:** encontre respostas para perguntas frequentes sobre as atividades do **[!UICONTROL Automated Personalization]**.

>[!ENDSHADEBOX]

As perguntas e respostas a seguir abordam como configurar atividades do **[!UICONTROL Automated Personalization]** no [!DNL Adobe Target], como os modelos de personalização são criados, como o tráfego é alocado e como ler os resultados.

## Configurar uma atividade {#set-up-an-activity}

+++ Quais são as práticas recomendadas para configurar uma atividade do [!UICONTROL Automated Personalization]?

* Preste muita atenção à *forma de atividade* (número de locais × número de ofertas), não apenas à contagem total de experiências. As combinações cartesianas de locais e ofertas afetam mais o desempenho no tempo de criação do que o número bruto de experiências. Para obter o desempenho e a capacidade de gerenciamento ideais, limite as atividades do **[!UICONTROL Automated Personalization]** e do **[!UICONTROL Direcionamento automático]** para 4 a 6 locais com 4 a 6 ofertas por local, conforme descrito na pergunta &quot;Quais são alguns limites do Automated Personalization?&quot; nesta seção. Configurações maiores não são recomendadas e podem resultar em carregamento ou edição lento no **[!UICONTROL Visual Experience Composer]**.
* Para personalizar uma página de tráfego mais baixo ou fazer alterações estruturais na experiência que você está personalizando, considere usar uma [**[!UICONTROL atividade de Direcionamento automático &#x200B;]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) em vez da&#x200B;**[!UICONTROL &#x200B; Automated Personalization &#x200B;]**.
* Considere executar uma atividade de **[!UICONTROL Teste A/B]** entre as ofertas e os locais que você planeja usar em sua atividade do **[!UICONTROL Automated Personalization]** para confirmar se os locais e as ofertas têm impacto na meta de otimização. Se a atividade **[!UICONTROL Teste A/B]** não demonstrar uma diferença significativa, o **[!UICONTROL Automated Personalization]** provavelmente também não gerará aumento.

  Se um teste A/B...N não mostrar diferenças estatisticamente significativas entre as experiências, uma ou mais das seguintes situações provavelmente serão responsáveis:

  * É provável que as ofertas não sejam suficientemente diferentes umas das outras.
  * Os locais selecionados não afetam a métrica de sucesso.
  * A meta de otimização está muito longe no funnel de conversão para ser afetada pelas ofertas escolhidas.

* Use o [Avaliador de Tráfego](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator) para ter uma ideia de quanto tempo leva para que os modelos de personalização sejam incorporados à sua atividade do **[!UICONTROL Automated Personalization]**.
* Decida sobre a alocação entre o controle e o tráfego direcionado antes de iniciar a atividade, com base em suas metas. A tabela a seguir lista os três cenários a serem considerados, com base na meta da atividade e no tipo de controle selecionado.

  | Meta de controle e atividade | Alocação recomendada para o controle | Detalhes |
  | --- | --- | --- |
  | **[!UICONTROL Experiências aleatórias]** como controle, e o objetivo é testar a eficácia do algoritmo de personalização | 50% | Esta meta requer uma imagem mais precisa do aumento. É provável que você também queira comparar a taxa de conversão de suas experiências ou ofertas com a taxa que um simples **[!UICONTROL Teste A/B]** (um controle disponibilizado aleatoriamente) ofereceria. |
  | **[!UICONTROL Experiências aleatórias]** como controle e o objetivo é maximizar o tráfego personalizado | 10% a 30% | Use essa opção se estiver familiarizado com o algoritmo e quiser que a quantidade máxima de tráfego seja personalizada. A compensação é a precisão das informações de lift: os intervalos de confiança do tráfego de controle são maiores, à medida que menos tráfego flui para eles. |
  | **[!UICONTROL Experiência específica]** como controle, com uma das metas | 10% a 30% | Use essa opção para comparar uma experiência específica orientada por um profissional de marketing aos modelos de personalização. Quando você seleciona apenas uma experiência como controle, esse tráfego não é distribuído em cada oferta ou experiência da atividade. |

* Use as regras de direcionamento com a menor quantidade possível, pois elas podem interferir na capacidade de otimização do modelo. Para obter mais informações, consulte [Ofertas de Personalização automatizada do Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).
* Os grupos de relatórios podem limitar o sucesso da sua atividade do **[!UICONTROL Automated Personalization]**, portanto, use-os somente sob condições específicas. Para obter mais informações, consulte [Oferecer grupos de relatórios no Automated Personalization](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md).

  * Use grupos de relatórios somente se todas as seguintes condições forem atendidas:

    * Você planeja substituir ou adicionar ofertas enquanto a atividade estiver em execução.
    * As ofertas no grupo de relatórios atraem os mesmos visitantes.
    * As ofertas do grupo de relatórios têm aproximadamente a mesma taxa de resposta geral.

  * Não há personalização entre ofertas em um grupo de relatórios. O modelo de personalização trata todas as ofertas como uma mesma.
  * Nunca coloque todas as ofertas em uma atividade em um único grupo de relatórios. Isso faz com que todas as ofertas sejam distribuídas uniformemente aleatoriamente para todos os visitantes na atividade.

+++

+++ Quais são alguns limites no [!UICONTROL Automated Personalization]?

O [!DNL Target] tem um limite rígido de 30.000 experiências, mas funciona no seu melhor quando menos de 10.000 experiências são criadas. O mesmo limite se aplica quando a atividade tem a opção **[!UICONTROL Não permitir Duplicatas]** habilitada.

Embora as atividades do **[!UICONTROL Automated Personalization]** e do **[!UICONTROL Direcionamento automático]** possam oferecer suporte a um grande número de experiências, o desempenho da criação depende muito da *forma da atividade* (número de locais × número de ofertas). Certas configurações criam grandes combinações cartesianas que podem afetar significativamente o desempenho de carga e edição, mesmo abaixo dos limites de experiência documentados.

Para obter o desempenho e a capacidade de gerenciamento ideais, limite as atividades do **[!UICONTROL Automated Personalization]** e do **[!UICONTROL Direcionamento automático]** para 4 a 6 locais com 4 a 6 ofertas por local. Configurações maiores não são recomendadas e podem ser restritas na interface do usuário do [!DNL Target].

Na interface atual do [!DNL Target], as atividades do **[!UICONTROL Automated Personalization]** e do **[!UICONTROL Direcionamento automático]** estão configuradas diretamente na etapa **[!UICONTROL Experiências]**. [!DNL Target] pode exibir avisos incorporados ou impedir que você salve uma atividade quando a configuração exceder os limites permitidos, e revalida a forma da atividade em **[!UICONTROL Próximo]**, **[!UICONTROL Salvar]** e **[!UICONTROL Publicar]**.

Para obter mais informações sobre limites de caracteres e outros limites (tamanho da oferta, públicos, valores, parâmetros e assim por diante) que afetam as atividades e outros elementos em [!DNL Target], consulte [Limites](/help/main/r-troubleshooting-target/target-limits.md).

+++

+++ Posso especificar uma experiência específica para ser usada como controle em uma atividade do [!UICONTROL Automated Personalization]?

Você pode selecionar uma experiência específica para ser usada como controle ao criar uma atividade do [**[!UICONTROL Automated Personalization]**](/help/main/c-activities/t-automated-personalization/automated-personalization.md#automated-personalization-overview) (AP) ou do [**[!UICONTROL Direcionamento automático]**](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear todo o tráfego de controle para essa experiência, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado em relação ao tráfego de controle para essa experiência única.

Para obter mais informações, consulte [Selecionar a experiência de controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

+++ Como é implementado o direcionamento no nível da oferta?

Quando cada visitante chega, as regras de direcionamento no nível da oferta determinam o conjunto de ofertas que o visitante pode ver. O algoritmo então escolhe, dentre essas ofertas, a oferta que o modelo prevê que tenha a melhor receita esperada ou chance de conversão. O direcionamento de oferta afeta a eficácia dos algoritmos de aprendizado de máquina do [!DNL Target]; portanto, use-o com a maior moderação possível. Para obter mais informações, consulte [Ofertas de Personalização automatizada do Target](/help/main/c-activities/t-automated-personalization/ap-target-offers.md).

+++

## Construção de modelos e alocação de tráfego {#models-and-traffic}

+++ Como o [!UICONTROL Automated Personalization] está alocando o tráfego da minha atividade?

O **[!UICONTROL Automated Personalization]** encaminha os visitantes para a experiência que tem a maior métrica de sucesso prevista, com base nos modelos [Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) mais recentes. Essa previsão é baseada nas informações específicas e no contexto de visita do visitante.

Por exemplo, suponha que uma atividade **[!UICONTROL Automated Personalization]** tenha dois locais com duas ofertas cada. No primeiro local, a Oferta A tem uma taxa de conversão prevista de 3% para um visitante específico e a Oferta B tem uma taxa de conversão prevista de 1%. No segundo local, a Oferta C tem uma taxa de conversão prevista de 2% para o mesmo visitante e a Oferta D tem uma taxa de conversão prevista de 5%. Portanto, o **[!UICONTROL Automated Personalization]** fornece a este visitante uma experiência com a Oferta A e a Oferta D.

+++

+++ Como o [!UICONTROL Automated Personalization] cria modelos em relação a ambientes?

Um modelo é criado para identificar o desempenho da estratégia personalizada em relação ao tráfego disponibilizado aleatoriamente em relação ao envio de todo o tráfego para a experiência vencedora geral. Esse modelo considera somente ocorrências e conversões no ambiente padrão.

Um segundo conjunto de modelos foi criado para cada grupo de relatórios (**[!UICONTROL Automated Personalization]**) ou experiência (**[!UICONTROL Direcionamento automático]**). Para cada um desses modelos, são consideradas ocorrências e conversões em todos os ambientes.

Portanto, as solicitações são atendidas com o mesmo modelo, independentemente do ambiente. No entanto, a pluralidade do tráfego deve vir do ambiente padrão para garantir que a experiência vencedora geral identificada seja consistente com o comportamento real.

+++

+++ Por quanto tempo devo esperar que os modelos sejam construídos?

O tempo que leva para os modelos serem construídos em sua atividade normalmente depende do tráfego para os locais de atividade selecionados e da métrica de sucesso da atividade. Use o [Avaliador de Tráfego](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#use-traffic-estimator) para determinar o período de tempo esperado para que os modelos compile sua atividade.

+++

+++ Como posso reduzir o tempo necessário para que os modelos compile minha atividade do [!UICONTROL Automated Personalization]?

Revise sua configuração de atividade para alterações que melhorem a velocidade de criação dos modelos. Por exemplo, altere uma métrica de sucesso de RPV para conversão, escolha uma métrica de sucesso mais próxima de suas experiências de atividade no funnel de vendas, remova algumas experiências da atividade ou use uma página de tráfego mais alto. Para obter mais informações, consulte [Solução de problemas do Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md).

+++

+++ Um modelo é compilado dentro da minha atividade [!UICONTROL Automated Personalization]. As visitas a essa experiência são personalizadas?

Não. Pelo menos dois modelos devem ser criados em sua atividade para que a personalização comece.

+++

## Resultados e aumento {#results-and-lift}

+++ Quando posso ver os resultados da minha atividade [!UICONTROL Automated Personalization]?

Você pode começar a ver os resultados da sua atividade do **[!UICONTROL Automated Personalization]** depois que pelo menos duas experiências tiverem modelos criados (indicados por uma marca de seleção verde).

+++

+++ Por que minha atividade [!UICONTROL Automated Personalization] não está mostrando o aumento?

Quatro fatores são necessários para uma atividade **[!UICONTROL Automated Personalization]** gerar aumento:

* As ofertas em cada local devem ser diferentes o suficiente para influenciar os visitantes.
* Os locais devem estar em algum lugar que faça diferença para a meta de otimização.
* Deve haver tráfego e potência estatística suficiente na atividade para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

O melhor curso de ação é garantir, usando uma atividade simples e não personalizada do **[!UICONTROL Teste A/B]**, que o conteúdo e os locais que compõem as experiências da atividade realmente façam diferença nas taxas de resposta geral. Para obter o procedimento completo, consulte [Solução de problemas do Automated Personalization](/help/main/c-activities/t-automated-personalization/ap-trouble.md).

+++

+++ Como posso comparar o [!UICONTROL Automated Personalization] a uma experiência padrão?

Não há opção turnkey para comparar o **[!UICONTROL Automated Personalization]** a uma experiência padrão. Como solução, se uma oferta ou experiência padrão existir como parte da atividade, clique no segmento **[!UICONTROL Controle]** nos relatórios e localize essa oferta no relatório de nível de oferta resultante. A taxa de conversão registrada para essa oferta pode ser comparada com a taxa de conversão do segmento &quot;Random Forest&quot; inteiro. Esta comparação mostra o desempenho do modelo em comparação com a oferta padrão.

+++

## Gerenciar uma atividade ativa {#manage-live-activity}

+++ Quando devo interromper minha atividade do [!UICONTROL Automated Personalization]?

O **[!UICONTROL Automated Personalization]** pode ser usado como uma personalização &quot;sempre ativa&quot; que otimiza constantemente. Especialmente para conteúdo permanente, não há necessidade de interromper sua atividade do **[!UICONTROL Automated Personalization]**. Se você quiser fazer alterações substanciais no conteúdo que não sejam semelhantes às ofertas atualmente em sua atividade, a prática recomendada é iniciar uma nova atividade. Iniciar uma nova atividade ajuda outros usuários que revisam relatórios a evitar a confusão ou a relacionar resultados anteriores com conteúdo diferente.

+++

+++ Posso alterar a métrica de meta durante uma atividade de [!UICONTROL Automated Personalization]?

[!DNL Adobe] não recomenda que você altere a métrica de meta durante uma atividade. Embora seja possível alterar a métrica de meta durante uma atividade usando a interface do usuário [!DNL Target], sempre inicie uma nova atividade. [!DNL Adobe] não garante o que acontece se você alterar a métrica de meta em uma atividade após sua execução.

Esta recomendação se aplica às atividades de **[!UICONTROL Alocação Automática]**, **[!UICONTROL Direcionamento Automático]** e **[!UICONTROL Automated Personalization]** que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

+++

+++ Posso usar a opção [!UICONTROL Redefinir Dados de Relatório] ao executar uma atividade do [!UICONTROL Automated Personalization]?

A [!DNL Adobe] não recomenda usar a opção **[!UICONTROL Redefinir Dados de Relatório]** para atividades do **[!UICONTROL Automated Personalization]**. Embora ela remova os dados do relatório visíveis, essa opção não remove todos os registros de treinamento do modelo **[!UICONTROL Automated Personalization]**. Em vez de usar a opção **[!UICONTROL Redefinir dados de relatório]**, crie uma nova atividade e desative a original. Esta orientação também se aplica às atividades de **[!UICONTROL Alocação automática]** e **[!UICONTROL Direcionamento automático]**.

+++

+++ Por que os visitantes veem experiências para uma atividade do [!UICONTROL Automated Personalization] que não deveriam ver?

**[!UICONTROL As atividades do Automated Personalization]** são avaliadas uma vez por sessão. Se houver sessões ativas que se qualificaram para uma experiência específica e novas ofertas tiverem sido adicionadas a ela desde então, os visitantes verão o novo conteúdo junto com as ofertas mostradas anteriormente. Esses visitantes se qualificaram anteriormente para essas experiências, para que ainda vejam essas experiências durante a sessão. Para avaliar a atividade em cada visita de página, altere para o tipo de atividade **[!UICONTROL Direcionamento de experiência]** (XT).

+++
