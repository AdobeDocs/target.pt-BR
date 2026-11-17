---
keywords: direcionamento automático; direcionamento; alocação de tráfego; perguntas frequentes; faq; solução de problemas; solucionar problemas; tráfego
description: Explore tópicos de solução de problemas e perguntas frequentes sobre as atividades de [!UICONTROL Direcionamento automático].
title: Como Posso Solucionar Problemas De Atividades De [!UICONTROL Direcionamento Automático]?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
TQID: 'https://experienceleague.adobe.com/LXOa1Ma0y8VbncCPN1Az33p-GDsd-bW-BDqJjSGbVQU'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
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
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
source-git-commit: 878df20c7fb08c893239135c20f358b5606d0c6f
workflow-type: tm+mt
source-wordcount: '1841'
ht-degree: 10%
---
# Perguntas frequentes e solução de problemas do [!UICONTROL Direcionamento automático] {#auto-target-faqs}

>[!BEGINSHADEBOX]

**Nesta página:** encontre respostas para perguntas frequentes sobre as atividades do **[!UICONTROL Direcionamento automático]** e soluções sugeridas para problemas comuns.

>[!ENDSHADEBOX]

Esta página responde às perguntas frequentes e descreve as etapas de solução de problemas das atividades de **[!UICONTROL Direcionamento automático]** em [!DNL Adobe Target].

## Perguntas frequentes {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte as seguintes perguntas e respostas ao trabalhar com atividades de **[!UICONTROL Direcionamento automático]**.

+++ Quais são as práticas recomendadas para configurar uma atividade de [!UICONTROL Direcionamento automático]?

* Decida se o valor comercial de uma métrica de sucesso de **[!UICONTROL Receita por visita]** (RPV) vale os requisitos adicionais de tráfego. O RPV geralmente precisa de pelo menos 1.000 conversões por experiência para que uma atividade funcione, em comparação com a conversão.
* Decida sobre a alocação entre experiências de controle e personalizadas antes de iniciar a atividade, com base em suas metas.
* Determine se você tem tráfego suficiente para a página em que sua atividade de **[!UICONTROL Direcionamento automático]** é executada para os modelos de personalização a serem criados em um período de tempo razoável.
* Se você estiver testando o algoritmo de personalização, não altere experiências nem adicione ou remova atributos de perfil enquanto a atividade estiver ativa.
* Considere a conclusão de uma atividade A/B entre as ofertas e os locais que você planeja usar em sua atividade de **[!UICONTROL Direcionamento automático]**, para garantir que os locais e as ofertas tenham impacto na meta de otimização. Se uma atividade A/B não demonstrar uma diferença significativa, o **[!UICONTROL Direcionamento automático]** provavelmente também não gerará aumento.

  Se um teste A/B não mostrar diferenças estatisticamente significativas entre as experiências, é provável que as ofertas que você está considerando não sejam suficientemente diferentes umas das outras, que os locais selecionados não afetem a métrica de sucesso ou que a meta de otimização esteja muito longe na conversão do funnel para ser afetada pelas ofertas escolhidas.

* Não faça alterações substanciais nas experiências durante a atividade.

+++

+++ A Adobe recomenda usar o Direcionamento automático com uma divisão de 90 (controle) / 10 (direcionado) até que os modelos sejam criados?

A divisão de alocação de tráfego ideal depende do que você deseja realizar.

Se o objetivo for personalizar o máximo de tráfego possível, você poderá manter a alocação direcionada de 90% e o controle de 10% durante todo o tempo de vida útil da atividade. Se o objetivo for executar um experimento que compare como os algoritmos de personalização fazem com o controle, uma divisão 50/50 é melhor para o tempo de vida da atividade.

A prática recomendada é manter a divisão de alocação de tráfego para o tempo de vida da atividade, para que os visitantes não alternem entre experiências de direcionamento e de controle.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There is no way to go back and see when a model was completed.
-->

+++

+++ Se um visitante não vir a atividade [!UICONTROL Direcionamento automático] e converter, a conversão conta em minha atividade?

Não. Somente os visitantes qualificados para exibir a atividade **[!UICONTROL Direcionamento automático]** são contados nos relatórios.

+++

+++ Por que minha atividade [!UICONTROL de Direcionamento automático] não está gerando nenhum aumento?

Para os quatro fatores necessários para gerar aumento e a solução sugerida, consulte o item de solução de problemas [Minha atividade de Direcionamento automático não está gerando aumento](#section_23995AB813F24525AF294D20A20875C8).

+++

+++ Quando devo interromper minha atividade de [!UICONTROL Direcionamento automático]?

O **[!UICONTROL Direcionamento automático]** pode ser usado como uma personalização &quot;sempre ativa&quot; que otimiza constantemente. Especialmente para conteúdo permanente, não há necessidade de interromper sua atividade de **[!UICONTROL Direcionamento automático]**.

Se você quiser fazer alterações substanciais no conteúdo em sua atividade de **[!UICONTROL Direcionamento automático]**, a prática recomendada é iniciar uma nova atividade para que outros usuários que revisem relatórios não confundam ou relacionem resultados anteriores com conteúdo diferente.

+++

+++ Por quanto tempo devo esperar que os modelos sejam construídos?

O tempo que leva para os modelos serem construídos em sua atividade de **[!UICONTROL Direcionamento automático]** normalmente depende do tráfego para as localizações de atividades selecionadas e as taxas de conversão associadas à métrica de sucesso da atividade.

O **[!UICONTROL Direcionamento automático]** não tenta criar um modelo personalizado para uma determinada experiência até que haja pelo menos 50 conversões para ela. Além disso, se o modelo criado for de qualidade insuficiente (conforme determinado pela avaliação offline dos dados de &quot;teste&quot; em espera, usando [uma métrica conhecida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), o modelo não será usado para veicular o tráfego de maneira personalizada.

Lembre-se dos seguintes pontos sobre a criação de modelos no **[!UICONTROL Direcionamento automático]**:

* Depois que uma atividade está ativa, o **[!UICONTROL Direcionamento automático]** considera até os últimos 45 dias de dados fornecidos aleatoriamente quando tenta compilar modelos. Por exemplo, controlar o tráfego, além de alguns dados adicionais fornecidos aleatoriamente e retidos pelo algoritmo.
* Quando **[!UICONTROL Receita por visita]** é sua métrica de sucesso, essas atividades normalmente exigem mais dados para criar modelos, pois a variação na receita de visitas geralmente é maior do que na taxa de conversão.
* Os modelos são criados com base na experiência, portanto, a substituição de uma experiência por outra significa que o tráfego suficiente (pelo menos 50 conversões) deve ser coletado para a nova experiência antes que os modelos personalizados possam ser recriados.

Se os modelos demorarem muito para serem compilados, consulte [Minha atividade de Direcionamento automático está demorando muito para compilar modelos](#section_23995AB813F24525AF294D20A20875C8).

+++

+++ Um modelo é construído na minha atividade. As visitas a essa experiência são personalizadas?

Não. Deve haver pelo menos dois modelos construídos em sua atividade para que a personalização comece.

+++

+++ Quando posso ver os resultados da minha atividade [!UICONTROL de Direcionamento automático]?

Você pode começar a ver os resultados da sua atividade de **[!UICONTROL Direcionamento automático]** depois que pelo menos duas experiências tiverem modelos criados (marca de seleção verde).

+++

+++ Posso definir uma experiência específica para ser usada como controle?

É possível selecionar uma experiência para ser usada como controle ao criar uma atividade do [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou do [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado em relação ao tráfego de controle para essa experiência única.

Para obter mais informações, consulte [Usar uma experiência específica como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

+++ Posso alterar a métrica de meta durante uma atividade de [!UICONTROL Direcionamento automático]?

A Adobe não recomenda alterar a métrica de meta durante uma atividade. Embora seja possível alterar a métrica de meta durante uma atividade utilizando a interface do usuário [!DNL Target], você sempre deve iniciar uma nova atividade. A Adobe não garante o que acontece se você alterar a métrica de meta em uma atividade após sua execução.

Esta recomendação se aplica às atividades de **[!UICONTROL Alocação Automática]**, **[!UICONTROL Direcionamento Automático]** e **[!UICONTROL Automated Personalization]** que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

+++

+++ Posso usar a opção [!UICONTROL Redefinir dados de relatório] ao executar uma atividade [!UICONTROL de Direcionamento automático]?

Não é recomendado usar a opção **[!UICONTROL Redefinir Dados de Relatório]** para atividades de **[!UICONTROL Direcionamento Automático]**. Embora ela remova os dados do relatório visíveis, essa opção não remove todos os registros de treinamento do modelo **[!UICONTROL Direcionamento automático]**. Em vez de usar a opção **[!UICONTROL Redefinir dados de relatório]**, crie uma nova atividade e desative a original.

Esta orientação também se aplica às atividades de **[!UICONTROL Alocação automática]** e **[!UICONTROL Automated Personalization]**.

+++

+++ O que acontece se eu remover uma única experiência de uma atividade de [!UICONTROL Direcionamento automático]?

[!DNL Target] cria um modelo por experiência, portanto, remover uma experiência significa que [!DNL Target] cria um modelo a menos e não afeta os modelos para as outras experiências.

Por exemplo, suponha que você tenha uma atividade **[!UICONTROL de Direcionamento automático]** com oito experiências e não goste do desempenho de uma experiência. Você pode remover essa experiência e ela não afeta os modelos das sete restantes.

+++

## Solução de problemas do [!UICONTROL Direcionamento automático] {#section_23995AB813F24525AF294D20A20875C8}

Às vezes, as atividades não acontecem conforme o esperado. Os itens a seguir descrevem possíveis desafios que você poderá enfrentar ao usar o **[!UICONTROL Direcionamento automático]**, com soluções sugeridas.

+++ Minha atividade de [!UICONTROL Direcionamento automático] está demorando muito para criar modelos.

Várias alterações de configuração de atividade podem diminuir o tempo esperado para criar modelos, incluindo o número de experiências em sua atividade de **[!UICONTROL Direcionamento automático]**, o tráfego para seu site e sua métrica de sucesso selecionada.

**Solução:** revise sua configuração de atividade e veja se há alterações que você deseja fazer para melhorar a velocidade de criação dos modelos.

* Se sua métrica de sucesso estiver definida como **[!UICONTROL RPV]**, você poderá alterar para conversão? As atividades de conversão tendem a exigir menos tráfego para criar modelos. Você não perderá os dados da atividade se alterar a métrica de sucesso de RPV para conversão.
* Sua métrica de sucesso está bem abaixo do funil de vendas de suas experiências de atividade? Uma taxa de conversão de atividade mais baixa aumenta os requisitos de tráfego para a criação de modelos, pois é necessário um número mínimo de conversões.
* Há algumas experiências que você pode abandonar em sua atividade? Diminuir o número de experiências em uma atividade diminui o tempo para criar modelos.
* Existe uma página de tráfego mais alto onde essa atividade seria mais bem-sucedida? Quanto mais tráfego e conversões houver em seus locais de atividade, mais rápido será a criação dos modelos.

Para obter mais informações sobre o tempo que os modelos precisam, consulte [Por quanto tempo devo esperar que os modelos sejam compilados?](#section_5C120A2B11D14D9BAF767BBAB50FED23).

+++

+++ Minha atividade [!UICONTROL de Direcionamento automático] não está gerando nenhum aumento.

Quatro fatores são necessários para uma atividade de **[!UICONTROL Direcionamento automático]** gerar aumento:

* As ofertas devem ser diferentes o suficiente para influenciar os visitantes.
* As ofertas devem estar localizadas em algum lugar que faça diferença para a meta de otimização.
* Deve haver tráfego e &quot;potência&quot; estatística suficiente no teste para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

**Solução:** primeiro, verifique se sua atividade está personalizando o tráfego. Se os modelos não forem criados para todas as experiências, sua atividade de **[!UICONTROL Direcionamento automático]** ainda estará apresentando aleatoriamente uma parte significativa das visitas para tentar criar todos os modelos o mais rápido possível. Se os modelos não forem criados, o **[!UICONTROL Direcionamento automático]** não está personalizando o tráfego.

Em seguida, verifique se as ofertas e os locais de atividade realmente fazem diferença nas taxas de resposta geral, usando um teste A/B simples e não personalizado. Calcule os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e execute o teste A/B por uma duração fixa sem interrompê-lo ou fazer alterações. Se os resultados do teste A/B mostrarem um aumento estatisticamente significativo em uma ou mais experiências, é provável que uma atividade personalizada funcione. O Personalization pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre das ofertas e dos locais que não têm um impacto grande o suficiente na meta de otimização para serem detectados com significância estatística.

+++

+++ As métricas dependentes de uma métrica de conversão nunca convertem.

Isso é esperado.

Em uma atividade de **[!UICONTROL Direcionamento automático]**, depois que uma métrica de conversão (objetivo de otimização ou de postagem) é convertida, o usuário é liberado da experiência e a atividade é reiniciada.

Por exemplo, há uma atividade com uma métrica de conversão (C1) e uma métrica adicional (A1). A1 depende de C1. Quando um visitante entra na atividade pela primeira vez e os critérios para converter A1 e C1 não são atendidos, a métrica A1 não é convertida devido à dependência da métrica de sucesso. Se o visitante converter C1 e depois converter A1, A1 ainda não será convertido, porque quando C1 é convertido, o visitante é liberado.

+++
