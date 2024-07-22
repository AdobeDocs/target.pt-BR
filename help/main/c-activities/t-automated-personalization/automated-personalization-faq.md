---
keywords: solução de problemas;perguntas frequentes;Perguntas frequentes;personalização automatizada;controle;experiência padrão;práticas recomendadas;troubleshooting;frequency asked questions;FAQs;automated personalization;control;default experience;best practices
description: Explore uma lista de perguntas frequentes e respostas sobre as atividades de [!UICONTROL Automated Personalization] (AP) em [!UICONTROL Adobe Target].
title: Como posso encontrar perguntas frequentes sobre atividades de [!UICONTROL Automated Personalization]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: 2bf62cc1-1781-4021-a400-2884e0bae893
source-git-commit: 336da9dd876243a0eea662b4604a8fc1e6a69b1a
workflow-type: tm+mt
source-wordcount: '1946'
ht-degree: 22%

---

# Perguntas frequentes sobre o Automated Personalization

Consulte as seguintes perguntas frequentes e respostas ao trabalhar com as atividades do [!UICONTROL Automated Personalization] no [!DNL Adobe Target].

## Posso definir uma experiência específica para ser usada como controle em uma atividade [!UICONTROL Automated Personalization]?

+++Ver detalhes

Você pode selecionar uma experiência para ser usada como controle ao criar uma atividade do [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou do [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado com relação ao tráfego de controle para essa experiência única.

Para obter mais informações, consulte [Usar uma experiência específica como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

## Como posso comparar [!UICONTROL Automated Personalization] a uma experiência padrão? {#section_46C1A620A2384C2C8392D6716DD18495}

+++Ver detalhes

Não há opção de chave na mão para comparar [!UICONTROL Automated Personalization] a uma experiência padrão. No entanto, como solução alternativa, se uma oferta ou experiência padrão existir como parte da atividade geral, para entender seu desempenho de linha de base, clique no segmento &quot;[!UICONTROL Control]&quot; nos relatórios e localize essa oferta específica no relatório de nível de oferta resultante. A taxa de conversão registrada para esta oferta pode ser usada para comparar com a taxa de conversa de todo o segmento &quot;Random Forest&quot;. Isso ajuda a comparar o desempenho da máquina em comparação com a oferta padrão.

+++

## Quais são as práticas recomendadas para configurar uma atividade [!UICONTROL Automated Personalization]? {#section_E155B26282BE49B58EA2683413D11DE6}

+++Ver detalhes

* Se você deseja personalizar uma página de tráfego mais baixo ou fazer alterações estruturais na experiência que está personalizando, considere usar uma atividade [!UICONTROL Auto-Target] no lugar de [!UICONTROL Automated Personalization]. Consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md).
* Considere a conclusão de uma atividade [!UICONTROL A/B Test] entre as ofertas e os locais que você planeja usar em sua atividade [!UICONTROL Automated Personalization] para garantir que a localização e as ofertas tenham impacto na meta de otimização. Se uma atividade [!UICONTROL A/B Test] não demonstrar uma diferença significativa, [!UICONTROL Automated Personalization] provavelmente também não gerará aumento.

   * Se um teste A/B...N não mostrar diferenças estatisticamente significativas entre as experiências, uma ou mais das seguintes situações provavelmente serão responsáveis:

      * É provável que as ofertas não sejam suficientemente diferentes umas das outras.
      * Os locais selecionados não afetam a métrica de sucesso.
      * A meta de otimização está muito longe no funil de conversão para ser afetada pelas ofertas escolhidas.

* Use o [Avaliador de tráfego](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para ter uma ideia de quanto tempo leva para modelos de personalização serem compilados na sua atividade [!UICONTROL Automated Personalization].
* Decida sobre a alocação entre o controle e o target antes de iniciar a atividade, com base em suas metas.

  Há três cenários a serem considerados com base na meta da atividade e no tipo de controle selecionado:

   * **Experiências aleatórias como controle e o objetivo da atividade é testar a eficácia do algoritmo de personalização**: se o objetivo é avaliar o algoritmo de personalização, você deseja ter uma imagem mais precisa do aumento. Você também pode querer comparar qual é a taxa de conversão de suas experiências ou ofertas se simplesmente fez um [!UICONTROL A/B Test] (um controle disponibilizado aleatoriamente). Nessa situação, recomenda-se utilizar uma alocação de 50% para um controle de experiências disponibilizadas aleatoriamente.
   * **&quot;Experiências aleatórias&quot; como controle e a meta da atividade é maximizar o tráfego personalizado**: se você estiver familiarizado com o algoritmo e quiser ter a quantidade máxima de tráfego personalizado, recomenda-se uma alocação de 10% a 30%. A compensação aqui é a precisão que você vê nas informações de lift. Os intervalos de confiança do tráfego de controle são maiores porque há menos tráfego fluindo para eles.
   * **Experiência específica como controle, com ambos os tipos de metas**: se você quiser comparar uma experiência específica orientada por um profissional de marketing aos modelos de personalização, recomenda-se uma alocação de 10% a 30% para controle. Quando você seleciona apenas uma experiência como controle, esse tráfego não é distribuído em cada oferta ou experiência da atividade.

* As regras de direcionamento devem ser usadas com toda moderação possível, pois podem interferir na capacidade do modelo de otimizar.
* Os grupos de relatórios podem limitar o sucesso da sua atividade [!UICONTROL Automated Personalization]. Usar grupos de relatórios somente sob condições específicas:

   * Use grupos de relatórios somente se as seguintes condições forem atendidas:

      * Você planeja substituir ou adicionar novas ofertas enquanto a atividade estiver em execução.
      * As ofertas no grupo de relatórios atraem os mesmos visitantes.
      * As ofertas nesse grupo de relatórios têm aproximadamente a mesma taxa de resposta geral.

   * Não há personalização entre ofertas em um grupo de relatórios. Todas as ofertas são tratadas como iguais pelo modelo de personalização.
   * Nunca coloque todas as ofertas em uma atividade em um único grupo de relatórios. Isso faz com que todas as ofertas sejam distribuídas uniformemente aleatoriamente para todos os visitantes na atividade.

+++

## Quais são alguns limites em [!UICONTROL Automated Personalization]? {#section_08BA09ED51B547299963C94FE6417CFA}

+++Ver detalhes

O [!DNL Target] tem um limite rígido de 30.000 experiências, mas funciona no seu melhor quando menos de 10.000 experiências são criadas.

Esse mesmo limite é aplicado mesmo quando a atividade tiver habilitado a opção [!UICONTROL Disalow Duplicates].

Para obter mais informações sobre limites de caracteres e outros limites (tamanho da oferta, públicos, valores, parâmetros e assim por diante) que afetam as atividades e outros elementos em [!DNL Target], consulte [Limites](/help/main/r-troubleshooting-target/target-limits.md).

+++

## Como é implementado o direcionamento no nível da oferta?  {#section_9D7A86EA93D74E9B8C81072A681263A4}

+++Ver detalhes

Quando cada visitante chega, o conjunto de possíveis ofertas que o visitante pode ver é determinado pelas regras de direcionamento no nível da oferta. Em seguida, o algoritmo escolhe a oferta que o modelo prevê que tenha a melhor receita esperada ou chance de conversão entre essas ofertas. O direcionamento de oferta afeta a eficácia dos algoritmos de aprendizado de máquina do [!DNL Target] e, como resultado, deve ser usado com a maior moderação possível.

+++

## Por que minha atividade [!UICONTROL Automated Personalization] não está mostrando o aumento? {#section_BFA07C8C258F45318F73A461B8F32737}

+++Ver detalhes

Há quatro fatores necessários para uma atividade [!UICONTROL Automated Personalization] gerar aumento:

* As ofertas em cada local devem ser diferentes o suficiente para influenciar os visitantes.
* Os locais devem estar em algum lugar que faça diferença para a meta de otimização.
* Deve haver tráfego e potência estatística suficiente na atividade para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

O melhor curso de ação é garantir que o conteúdo e os locais que compõem as experiências da atividade realmente façam diferença nas taxas de resposta geral usando uma atividade [!UICONTROL A/B Test] simples e não personalizada. Certifique-se de calcular os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e executar o teste A/B por um período fixo sem interrompê-lo ou fazer quaisquer alterações. Se os resultados do teste A/B mostrarem um aumento estatisticamente significativo em uma ou mais experiências, é provável que uma atividade personalizada seja bem-sucedida. O Personalization pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre das ofertas ou dos locais que não têm um impacto grande o suficiente na meta de otimização para serem detectados com significância estatística.

Para obter mais informações, consulte [Solução de problemas de personalização automatizada](/help/main/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

+++

## Como o [!UICONTROL Automated Personalization] está alocando o tráfego da minha atividade? {#section_4369364F77804E0D9B78BEE551DA5659}

+++Ver detalhes

[!UICONTROL Automated Personalization] encaminha os visitantes para a experiência com a maior métrica de sucesso prevista baseada nos modelos [Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md) mais recentes criados para cada modelo. Esta previsão baseia-se na informação específica do visitante e no contexto da visita.

Por exemplo, suponha que uma atividade [!UICONTROL Automated Personalization] tivesse dois locais com duas ofertas cada. No primeiro local, a Oferta A tem uma taxa de conversão prevista de 3% para um visitante específico e a Oferta B tem uma taxa de conversão prevista de 1%. No segundo local, a Oferta C tem uma taxa de conversão prevista de 2% para o mesmo visitante e a Oferta D tem uma taxa de conversão prevista de 5%. Portanto, [!UICONTROL Automated Personalization] oferece a este visitante uma experiência com a Oferta A e a Oferta D.

+++

## Quando devo interromper minha atividade [!UICONTROL Automated Personalization]? {#section_C51F3DAB8887463BB147373F6FE06B93}

+++Ver detalhes

[!UICONTROL Automated Personalization] pode ser usado como personalização &quot;sempre ativa&quot; que otimiza constantemente. Especialmente para conteúdo permanente, não há necessidade de interromper sua atividade [!UICONTROL Automated Personalization]. Se você quiser fazer alterações substanciais no conteúdo que não sejam semelhantes às ofertas que estão atualmente na sua atividade [!UICONTROL Automated Personalization], a prática recomendada é iniciar uma nova atividade. Iniciar uma nova atividade ajuda outros usuários a revisar relatórios para não confundir ou relacionar resultados anteriores com conteúdo diferente.

+++

## Por quanto tempo devo esperar que os modelos sejam construídos? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

+++Ver detalhes

O tempo que leva para os modelos serem construídos em sua atividade normalmente depende do tráfego para os locais de atividade selecionados e da métrica de sucesso da atividade. Use o [Avaliador de Tráfego](/help/main/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para determinar o período de tempo esperado para que os modelos compile sua atividade.

+++

## Um modelo é compilado dentro da minha atividade [!UICONTROL Automated Personalization]. As visitas a essa experiência são personalizadas? {#section_51EA953C6D1D4A3185FC9DD290D66621}

+++Ver detalhes

Não, deve haver pelo menos dois modelos construídos em sua atividade para que a personalização comece.

+++

## Quando posso ver os resultados da minha atividade [!UICONTROL Automated Personalization]? {#section_05DB5ACAE6AD429C9510766A7268EE2C}

+++Ver detalhes

Você pode começar a ver os resultados da sua atividade do [!UICONTROL Automated Personalization] depois de ter pelo menos duas experiências com modelos construídos (marca de seleção verde) para a experiência que os modelos construíram.

+++

## Como posso diminuir o tempo necessário para que os modelos compile minha atividade [!UICONTROL Automated Personalization]? {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

+++Ver detalhes

Analise sua configuração de atividade e veja se há alterações que você deseja fazer para melhorar a velocidade de criação dos modelos.

* Sua métrica de sucesso está bem abaixo do funil de vendas de suas experiências de atividade? Um índice de conversão de atividade mais baixo aumenta os requisitos de tráfego para a criação dos modelos, já que é necessário um número mínimo de conversões.
* Se sua métrica de sucesso estiver definida como RPV, será possível mudar para conversão? As atividades de conversão tendem a exigir menos tráfego para criar modelos.
* Há algumas experiências que você pode descartar da sua atividade? A diminuição do número de experiências em uma atividade acelera o tempo de criação de modelos.
* Há uma página de tráfego mais alto em que essa atividade seria mais bem-sucedida? Quanto mais tráfego e conversões houver nos locais de atividade, mais rápido será a criação de modelos.

+++

## Por que os visitantes veem experiências para uma atividade [!UICONTROL Automated Personalization] que não deveriam ver? {#section_41CECEAE0881446A8D9F3B016857914B}

+++Ver detalhes

[!UICONTROL Automated Personalization] atividades são avaliadas uma vez por sessão. Se houver sessões ativas que se qualificaram para uma experiência específica e agora novas ofertas forem adicionadas a ela, os visitantes verão o novo conteúdo junto com as ofertas mostradas anteriormente. Como esses visitantes se qualificaram anteriormente para essas experiências, eles ainda verão essas experiências durante a sessão. Para avaliar isso em cada visita de página, você deve alterar para o tipo de atividade [!UICONTROL Experience Targeting] (XT).

+++

## Posso alterar a métrica de meta durante uma atividade de [!UICONTROL Automated Personalization]? {#change-metric}

+++Ver detalhes

[!DNL Adobe] não recomenda que você altere a métrica de meta durante uma atividade. Embora seja possível alterar a métrica de meta durante uma atividade utilizando a interface do usuário [!DNL Target], você sempre deve iniciar uma nova atividade. [!DNL Adobe] não garante o que acontece se você alterar a métrica de meta em uma atividade após sua execução.

Esta recomendação se aplica às atividades de [!UICONTROL Auto-Allocate], [!UICONTROL Auto-Target] e [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

+++

## Posso usar a opção [!UICONTROL Reset Report Data] ao executar uma atividade [!UICONTROL Automated Personalization]?

+++Ver detalhes

[!DNL Adobe] não recomenda usar a opção [!UICONTROL Reset Report Data] para atividades [!UICONTROL Automated Personalization]. Embora ela remova os dados do relatório visíveis, essa opção não remove todos os registros de treinamento do modelo [!UICONTROL Automated Personalization]. Em vez de usar a opção [!UICONTROL Reset Report Data] para atividades [!UICONTROL Automated Personalization], crie uma nova atividade e desative a original. Esta orientação também se aplica às atividades [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target].

+++

## Como o [!UICONTROL Automated Personalization] cria modelos em relação a ambientes?

+++Ver detalhes

Um modelo é criado para identificar o desempenho da estratégia personalizada em relação ao tráfego disponibilizado aleatoriamente em relação ao envio de todo o tráfego para a experiência vencedora geral. Esse modelo considera somente ocorrências e conversões no ambiente padrão.

O tráfego de um segundo conjunto de modelos é criado para cada grupo de modelagem ([!UICONTROL Automated Personalization]) ou experiência ([!UICONTROL Auto-Target]). Para cada um desses modelos, são consideradas ocorrências e conversões em todos os ambientes.

Portanto, as solicitações são atendidas com o mesmo modelo, independentemente do ambiente. No entanto, a pluralidade do tráfego deve vir do ambiente padrão para garantir que a experiência vencedora geral identificada seja consistente com o comportamento real.

+++
