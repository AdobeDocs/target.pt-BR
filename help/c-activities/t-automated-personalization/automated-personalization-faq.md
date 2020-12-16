---
keywords: troubleshooting;frequently asked questions;FAQ;FAQs;automated personalization
description: Lista de perguntas frequentes sobre a Personalização automatizada (AP).
title: Perguntas frequentes sobre a personalização automatizada
feature: ap
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1962'
ht-degree: 85%

---


# ![Perguntas frequentes sobre personalização ](/help/assets/premium.png) PREMIUMAutomated{#automated-personalization-faq}

Lista de perguntas frequentes sobre a Personalização automatizada (AP).

## Posso definir uma experiência específica para ser usada como controle?

É possível selecionar uma experiência para ser usada como controle ao criar uma atividade de [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou de [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado com relação ao tráfego de controle para essa experiência única.

Para obter mais informações, consulte [Usar uma experiência específica como controle](/help/c-activities/t-automated-personalization/experience-as-control.md).

## Como posso comparar personalização automatizada a uma experiência padrão? {#section_46C1A620A2384C2C8392D6716DD18495}

Não há opção completa para comparar a AP a uma experiência padrão. No entanto, como solução alternativa, se existir uma oferta ou experiência padrão como parte da atividade geral, para entender seu desempenho de linha de base, clique no segmento &quot;Controle&quot; nos relatórios e localize essa oferta específica no relatório de nível de oferta resultante. A taxa de conversão registrada para esta oferta pode ser usada para comparar com a taxa de conversação de todo o segmento &quot;Random Forest&quot;. Isso ajuda a comparar o desempenho da máquina em comparação com a oferta padrão.

## Quais são as práticas recomendadas para configurar uma atividade de Personalização automatizada?   {#section_E155B26282BE49B58EA2683413D11DE6}

* Se você deseja personalizar uma página de tráfego mais baixo ou quer fazer alterações estruturais na experiência que está personalizando, considere o uso do direcionamento automático no lugar da personalização automatizada. Consulte  [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md).
* Considere a conclusão de uma atividade A/B entre as ofertas e os locais que você planeja usar em sua atividade de Personalização automatizada para garantir que os locais e as ofertas tenham impacto na meta de otimização. Se uma atividade A/B não demonstrar uma diferença significativa, a Personalização automatizada provavelmente também não gerará aumento.

   * Se um teste A/B…N não mostra diferenças estatisticamente significativas entre as experiências, provavelmente as ofertas que você está considerando não são suficientemente diferentes umas das outras, os locais selecionados não afetam a métrica de sucesso ou a meta de otimização está muito distante no funil de conversão a ser afetado pelas ofertas escolhidas.

* Certifique-se de usar o  [Avaliador de tráfego](/help/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para que você tenha uma noção de quanto tempo levará para que os modelos de personalização sejam incorporados à sua atividade de Personalização automatizada.
* Decida sobre a alocação entre controle e segmentado antes de iniciar a atividade com base em suas metas.

   Há três cenários a serem considerados com base na meta da atividade e no tipo de controle selecionado:

   * **Experiências aleatórias como controle e o objetivo da atividade é testar a eficácia do algoritmo de personalização**: se o objetivo é avaliar o algoritmo de personalização, você desejará ter uma imagem mais precisa do seu aumento. Você também pode querer fazer a comparação de como seria a taxa de conversão de suas experiências/ofertas se simplesmente fizesse um Teste A/B (um controle disponibilizado aleatoriamente). Nessa situação, recomenda-se utilizar uma alocação de 50% para um controle de experiências disponibilizadas aleatoriamente.
   * **&quot;Experiências aleatórias&quot; como controle e a meta da atividade é maximizar o tráfego personalizado**: se você estiver familiarizado com o algoritmo e quiser ter a quantidade máxima de tráfego personalizado, recomenda-se uma alocação de 10% a 30%. A compensação aqui é a precisão que você poderá ver em suas informações de lift (já que os intervalos de confiança do tráfego de controle estarão maiores, pois há menos tráfego fluindo para eles).
   * **Experiência específica como controle, com ambos os tipos de metas**: se você quiser comparar uma experiência específica orientada por um profissional de marketing aos modelos de personalização, recomenda-se uma alocação de 10% a 30% para controle. Quando você seleciona apenas uma experiência como controle, o tráfego não é distribuído em cada oferta/experiência da atividade.

* As regras de direcionamento devem ser usadas com toda moderação possível, pois podem interferir na capacidade do modelo de otimizar.
* Grupos de relatórios podem limitar o sucesso da sua atividade de Personalização automatizada. Eles só devem ser usados sob condições específicas.

   * Use grupos de relatórios somente se as seguintes condições forem atendidas: (1) você planeja substituir/ adicionar novas ofertas enquanto a atividade está em execução, (2) as ofertas no grupo de relatórios atraem os mesmos visitantes e (3) as ofertas em esse grupo de relatórios têm aproximadamente a mesma taxa de resposta geral.
   * Não há personalização entre ofertas em um grupo de relatórios: todas as ofertas são tratadas como iguais pelo modelo de personalização.
   * Nunca coloque todas as ofertas em uma atividade em um único grupo de relatórios. Esta decisão fará com que todas as ofertas sejam uniformemente distribuídas aleatoriamente para todos os visitantes da atividade.

## Perguntas frequentes

Consulte as seguintes perguntas frequentes e respostas enquanto trabalha com atividades de autoalocação:

### Quais são alguns limites na personalização automatizada?   {#section_08BA09ED51B547299963C94FE6417CFA}

O Target tem um limite rígido de 30.000 experiências, mas funciona no seu melhor quando menos de 10.000 experiências são criadas.

### Como é implementado o direcionamento no nível da oferta?   {#section_9D7A86EA93D74E9B8C81072A681263A4}

Quando cada visitante chega, o conjunto de possíveis ofertas que o visitante pode ver é determinado pelas regras de direcionamento no nível da oferta. Em seguida, o algoritmo escolhe a oferta que o modelo prevê que terá a melhor receita esperada ou a chance de conversão entre essas ofertas. Observe que o direcionamento por oferta afeta a eficácia dos algoritmos de aprendizagem de máquina do Target e, como resultado, deve ser usado com toda moderação possível.

### Minha atividade não está apresentando nenhum aumento. O que está acontecendo? {#section_BFA07C8C258F45318F73A461B8F32737}

Há quatro fatores necessários para uma atividade de AP gerar aumento:

* As ofertas em cada local precisam ser diferentes o suficiente para influenciar os visitantes.
* Os locais precisam estar em um lugar que faça diferença na meta de otimização.
* Deve haver tráfego e potência estatística suficiente na atividade para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

O melhor curso de ação é garantir que o conteúdo e os locais que compõem as experiências da atividade realmente façam diferença nas taxas de resposta geral usando um teste A/B simples e não personalizado. Certifique-se de calcular os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e executar o teste A/B por um período fixo sem interrompê-lo ou fazer quaisquer alterações. Se um resultado do teste A/B mostrar um aumento estatisticamente significativo em uma ou mais das experiências, é provável que uma atividade personalizada funcione. Claro, a personalização pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre de ofertas/locais que não têm um impacto suficientemente grande na meta da otimização para serem detectados com significância estatística.

Para obter mais informações, consulte [Solução de problemas de personalização automatizada](/help/c-activities/t-automated-personalization/ap-trouble.md#reference_281954549C3E49E2B5498009BBDC62CA).

### Como a Personalização automatizada está alocando o tráfego da minha atividade? {#section_4369364F77804E0D9B78BEE551DA5659}

A Personalização automatizada encaminha os visitantes da experiência com a maior métrica de sucesso prevista baseada nos modelos [Random Forest](/help/c-activities/t-automated-personalization/algo-random-forest.md) mais recentes criados para cada modelo. Esta previsão baseia-se na informação específica do visitante e no contexto da visita.

Por exemplo, suponha que uma atividade de AP tenha dois locais com duas ofertas cada. No primeiro local, a Oferta A tem uma taxa de conversão prevista de 3% para um visitante específico e a Oferta B tem uma taxa de conversão prevista de 1%. No segundo local, a Oferta C tem uma taxa de conversão prevista de 2% para o mesmo visitante e a Oferta D tem uma taxa de conversão prevista de 5%. Portanto, a Personalização automatizada ofereceria a esse visitante uma experiência com a Oferta A e a Oferta D.

### Quando devo interromper minha atividade de Personalização automatizada?   {#section_C51F3DAB8887463BB147373F6FE06B93}

A Personalização automatizada pode ser usada como personalização &quot;sempre ativa&quot; que otimizará constantemente. Especialmente para conteúdo permanente, não há necessidade de interromper sua atividade de Personalização automatizada. Se você quiser fazer alterações substanciais no conteúdo que não são semelhantes às ofertas atualmente em sua atividade de Personalização automatizada, a prática recomendada é iniciar uma nova atividade para que outros usuários que revisem relatórios não confundam ou relacionem resultados anteriores com conteúdo diferente.

### Por quanto tempo devo esperar que os modelos sejam construídos? {#section_6F6A5A9DB3564BE6B22FFEDFA5B29619}

O tempo que leva para os modelos serem construídos em sua atividade normalmente depende do tráfego para a(s) localização(ões) de atividades selecionada(s) e a métrica de sucesso da atividade. Use a variável [Avaliador de tráfego](/help/c-activities/t-automated-personalization/ap-traffic-estimator.md#task_71AA6922AFD447EA8C5E610A78ABA714) para determinar o período de tempo esperado para que os modelos construam sua atividade.

### Um modelo é construído dentro da minha atividade. As visitas a essa experiência são personalizadas? {#section_51EA953C6D1D4A3185FC9DD290D66621}

Não, deve haver pelo menos dois modelos construídos em sua atividade para que a personalização comece.

### Quando posso ver os resultados da minha atividade de Personalização automatizada?   {#section_05DB5ACAE6AD429C9510766A7268EE2C}

Você pode começar a ver os resultados da sua atividade de Personalização automatizada depois de ter pelo menos duas experiências com modelos construídos (marca de seleção verde) para a experiência que os modelos construíram.

### Como posso diminuir o tempo necessário para que os modelos construam minha atividade?   {#section_CCB8CEE98DAA40BA93AADCD596C48D82}

Revise a configuração da atividade e veja se deseja fazer alguma alteração para melhorar a velocidade de criação dos modelos.

* Sua métrica de sucesso está bem abaixo do funil de vendas de suas experiências de atividade? Uma taxa de conversão de atividade menor aumentará os requisitos de tráfego necessários para a criação de modelos, pois é necessário um número mínimo de conversões.
* Se sua métrica de sucesso estiver definida como RPV, será possível mudar para conversão? As atividades de conversão tendem a exigir menos tráfego para criar modelos.
* Há algumas experiências que você pode abandonar em sua atividade? A diminuição do número de experiências em uma atividade irá acelerar a quantidade de tempo para construir modelos.
* Existe uma página de tráfego mais alto, em tal página essa atividade seria mais bem-sucedida? Quanto mais tráfego e conversões em seus locais de atividade, mais rápidos serão os modelos.

### Por que os visitantes veem experiências para uma atividade de AP que não deveriam ver? {#section_41CECEAE0881446A8D9F3B016857914B}

As atividades de Personalização automatizada são avaliadas uma vez por sessão. Se houver sessões ativas que se qualificaram para uma experiência específica e agora novas ofertas foram adicionadas a elas, os usuários verão o novo conteúdo junto com as ofertas exibidas anteriormente. Como elas se qualificaram previamente para essas experiências, eles ainda as veriam durante a sessão. Se houver um desejo de avaliar isso em todas as visitas a uma página única, você deverá mudar para o tipo de atividade de Direcionamento de experiência (XT).

### É possível alterar a métrica de objetivo no meio de uma atividade Automated Personalization? {#change-metric}

Não recomendamos que você altere a métrica de objetivo a meio de uma atividade. Embora seja possível alterar a métrica de objetivo durante uma atividade usando a interface do usuário [!DNL Target], você deve sempre start uma nova atividade. Não garantimos o que acontece se você alterar a métrica de objetivo em uma atividade após sua execução.

Esta recomendação se aplica às atividades [!UICONTROL Autoalocar], [!UICONTROL Público alvo automático] e [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como a origem do relatórios.

### Posso usar a opção Redefinir dados do relatório ao executar uma atividade do Automated Personalization?

Não é sugerido usar a opção [!UICONTROL Redefinir dados de relatório] para [!UICONTROL Automated Personalization] atividade. Embora remova os dados de relatórios visíveis, essa opção não remove todos os registros de treinamento do modelo [!UICONTROL Automated Personalization]. Em vez de usar a opção [!UICONTROL Redefinir dados do relatório] para [!UICONTROL Automated Personalization] atividade, crie uma nova atividade e desative a atividade original. (Observação: Esta orientação também se aplica às atividades [!UICONTROL Autoalocação] e [!UICONTROL Público alvo automático].)

### Como a Automated Personalization constrói modelos em relação aos ambientes?

Um modelo é criado para identificar o desempenho da estratégia personalizada em comparação ao tráfego atendido aleatoriamente em vez de enviar todo o tráfego para a experiência vencedora geral. Esse modelo considera somente ocorrências e conversões no ambiente padrão.

O tráfego de um segundo conjunto de modelos é criado para cada grupo de modelagem (AP) ou experiência (AT). Para cada um desses modelos, as ocorrências e conversões em todos os ambientes são consideradas.

Por conseguinte, os pedidos serão acompanhados do mesmo modelo, independentemente do ambiente, mas a pluralidade do tráfego deverá provir do ambiente por defeito, a fim de assegurar que a experiência globalmente identificada vencedora seja coerente com o comportamento no mundo real.
