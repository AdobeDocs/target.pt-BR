---
keywords: direcionamento automático; direcionamento; alocação de tráfego; perguntas frequentes; faq; solução de problemas; solucionar problemas; tráfego
description: Explore tópicos de solução de problemas e perguntas frequentes sobre [!UICONTROL Direcionamento automático] atividades.
title: Como posso solucionar problemas [!UICONTROL Direcionamento automático] Atividades?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Auto-Target
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
source-git-commit: 3e8c2d77f300bf0e2ca83a53d30e7b9eee48894e
workflow-type: tm+mt
source-wordcount: '1925'
ht-degree: 40%

---

# [!UICONTROL Direcionamento automático] Perguntas frequentes e solução de problemas

Solução de problemas e perguntas frequentes sobre o [!UICONTROL Direcionamento automático] atividades no [!DNL Adobe Target].

## [!UICONTROL Perguntas frequentes sobre direcionamento automático] {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte as seguintes perguntas frequentes e respostas ao trabalhar com as atividades de [!UICONTROL Direcionamento automático]:

### Quais são as práticas recomendadas para configurar uma atividade de [!UICONTROL Direcionamento automático]?

+++Resposta
* Decidir se o valor comercial de um [!UICONTROL Receita por visita] (RPV) A métrica de sucesso vale os requisitos adicionais de tráfego. O RPV normalmente precisa de pelo menos 1.000 conversões por experiência para que uma atividade funcione em comparação com a conversão.
* Decida sobre a alocação entre controle e experiências personalizadas antes de iniciar a atividade com base em suas metas.
* Determine se você tem tráfego suficiente para a página em que [!UICONTROL Direcionamento automático] A atividade do é executada para modelos de personalização a serem criados em um período de tempo razoável.
* Se você estiver testando o algoritmo de personalização, não altere experiências nem adicione ou remova atributos de perfil enquanto a atividade estiver ativa.
* Considere a conclusão de uma atividade A/B entre as ofertas e os locais que você planeja usar em sua [!UICONTROL Direcionamento automático] atividade para garantir que os locais e as ofertas tenham impacto na meta de otimização. Se uma atividade A/B não demonstrar uma diferença significativa, [!UICONTROL Direcionamento automático] também pode falhar ao gerar aumento.

  Se um teste A/B não mostra diferenças estatisticamente significativas entre as experiências, é provável que as ofertas que você está considerando não são suficientemente diferentes umas das outras, os locais selecionados não afetam a métrica de sucesso ou a meta de otimização está muito distante no funil de conversão a ser afetado pelas ofertas escolhidas.

* Tente não fazer alterações substanciais nas experiências durante a atividade.

+++

### Faz [!UICONTROL Adobe] que você recomenda usar [!UICONTROL Direcionamento automático] com uma divisão de 90(Controle)/10(Direcionado) até que os modelos sejam criados?

+++Responda A divisão de alocação de tráfego ideal depende do que você deseja realizar.

Se o objetivo for personalizar o máximo de tráfego possível, você poderá manter a alocação direcionada de 90% e o controle de 10% durante todo o tempo de vida útil da atividade. Se o objetivo for executar um experimento comparando como os algoritmos personalizados são executados em relação ao controle, uma divisão 50/50 é melhor para o tempo de vida da atividade.

A prática recomendada é manter a divisão de alocação de tráfego para o tempo de vida da atividade para que os visitantes não alternem entre experiências de direcionamento e de controle.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

+++

### Se um visitante não **não** consulte a [!UICONTROL Direcionamento automático] atividade e converte, a conversão conta em minha atividade?

+++Resposta Não, somente visitantes qualificados para visualizar a [!UICONTROL Direcionamento automático] As atividades são contadas nos relatórios.

+++

### Por que o meu [!UICONTROL Direcionamento automático] parece estar gerando algum aumento.

+++Resposta Há quatro fatores necessários para uma [!UICONTROL Direcionamento automático] atividade para gerar aumento:

* As ofertas devem ser diferentes o suficiente para influenciar os visitantes.
* As ofertas devem estar localizadas em algum lugar que faça diferença para a meta de otimização.
* Deve haver tráfego e &quot;potência&quot; estatística suficiente no teste para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

O melhor curso de ação é garantir que o conteúdo e os locais que compõem as experiências da atividade realmente façam diferença nas taxas de resposta geral usando um teste A/B simples e não personalizado. Certifique-se de calcular os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e executar o teste A/B por um período fixo sem interrompê-lo ou fazer quaisquer alterações.

Se os resultados de um teste A/B mostram um aumento estatisticamente significativo em uma ou mais das experiências, é provável que uma atividade personalizada funcione. Claro, a personalização pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre das ofertas e dos locais que não têm um impacto grande o suficiente na meta de otimização para serem detectados com significância estatística.

+++

### Quando devo interromper minha atividade de [!UICONTROL Direcionamento automático]?

+++Resposta
[!UICONTROL Direcionamento automático] O pode ser usado como personalização &quot;sempre ativa&quot; que otimiza constantemente. Especialmente para conteúdo permanente, não há necessidade de interromper sua atividade de [!UICONTROL Direcionamento automático].

Se você quiser fazer alterações substanciais no conteúdo em seu [!UICONTROL Direcionamento automático] atividade, a prática recomendada é iniciar uma nova atividade para que outros usuários que revisem relatórios não confundam ou relacionem resultados anteriores com conteúdo diferente.

+++

### Por quanto tempo devo esperar que os modelos sejam construídos? {#how-long}

+++Responder O tempo que leva para os modelos serem construídos em seu [!UICONTROL Direcionamento automático] A atividade geralmente depende do tráfego para os locais de atividade selecionados e das taxas de conversão associadas à métrica de sucesso da atividade.

[!UICONTROL Direcionamento automático] O não tenta criar um modelo personalizado para uma determinada experiência até que haja pelo menos 50 conversões para ela. Além disso, se o modelo criado for de qualidade insuficiente (conforme determinado pela avaliação offline dos dados de &quot;teste&quot; de espera, utilizando [uma métrica conhecida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), o modelo não é usado para veicular o tráfego de maneira personalizada.

Alguns outros pontos para ter em mente sobre a criação de modelo do [!UICONTROL Direcionamento automático]:

* Depois que uma atividade está ativa, [!UICONTROL Direcionamento automático] O considera até os últimos 45 dias de dados fornecidos aleatoriamente ao tentar criar modelos. Por exemplo, controlar o tráfego, além de alguns dados adicionais fornecidos aleatoriamente e retidos pelo algoritmo.
* Quando [!UICONTROL Receita por visita] é sua métrica de sucesso, essas atividades normalmente exigem mais dados para criar modelos devido à maior variação de dados que normalmente existe na receita de visitas em comparação com a taxa de conversão.
* Como os modelos são criados com base na experiência, a substituição de uma experiência por outra significa que o tráfego suficiente (pelo menos 50 conversões) deve ser coletado para a nova experiência antes que os modelos personalizados possam ser recriados.

+++

### Um modelo é construído na minha atividade. As visitas a essa experiência são personalizadas?

+++Resposta Não, deve haver pelo menos dois modelos construídos em sua atividade para que a personalização comece.

+++

### Quando posso ver os resultados do meu [!UICONTROL Direcionamento automático] atividade?

+++Resposta Você pode começar a ver os resultados de seus [!UICONTROL Direcionamento automático] faça o teste depois de ter pelo menos duas experiências com modelos construídos (marca de seleção verde) para a experiência que os modelos construíram.

+++

### Posso definir uma experiência específica para ser usada como controle?

+++Resposta É possível selecionar uma experiência para ser usada como controle ao criar uma [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado com relação ao tráfego de controle para essa experiência única.

Para obter mais informações, consulte [Usar uma experiência específica como controle](/help/main/c-activities/t-automated-personalization/experience-as-control.md).

+++

### Posso alterar a métrica de meta durante uma [!UICONTROL Direcionamento automático] atividade? {#change-metric}

+++Adobe de resposta não recomenda que você altere a métrica de meta durante uma atividade. Embora seja possível alterar a métrica de meta durante uma atividade utilizando a interface do usuário [!DNL Target], você sempre deve iniciar uma nova atividade. O Adobe não garante o que acontece se você alterar a métrica de meta em uma atividade após sua execução.

Esta recomendação se aplica às atividades de [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

+++

### Posso usar o [!UICONTROL Redefinir dados de relatório] durante a execução de um [!UICONTROL Direcionamento automático] atividade?

+++Atender usando o [!UICONTROL Redefinir dados de relatório] opção para [!UICONTROL Direcionamento automático] não é sugerido. Embora ela remova os dados do relatório visíveis, essa opção não remove todos os registros de treinamento do modelo de [!UICONTROL Direcionamento automático]. Em vez de usar a opção [!UICONTROL Redefinir dados do relatório] para atividades de [!UICONTROL Direcionamento automático], crie uma nova atividade e desative a original.

As presentes orientações aplicam-se igualmente aos [!UICONTROL Alocação automática] e [!UICONTROL Automated Personalization] atividades.

+++

### O que acontece se eu remover uma única experiência de um [!UICONTROL Direcionamento automático] atividade?

+++Resposta
[!DNL Target] O cria um modelo por experiência, portanto, remover uma experiência significa [!DNL Target] O cria um modelo a menos e não afeta os modelos das outras experiências.

Por exemplo, suponha que você tenha uma atividade de [!UICONTROL Direcionamento automático] com oito experiências e não goste do desempenho de uma experiência. Você pode remover essa experiência e ela não afeta os modelos das sete restantes.

+++

## Solução de problemas do [!UICONTROL Direcionamento automático] {#section_23995AB813F24525AF294D20A20875C8}

Às vezes, as atividades não acontecem como o esperado. Estes são alguns possíveis desafios que você pode enfrentar ao usar o [!UICONTROL Direcionamento automático] e algumas soluções sugeridas.

### Minha atividade de [!UICONTROL Direcionamento automático] está demorando muito para criar modelos.

+++Sugestões de solução de problemas Há várias alterações na configuração de atividades que podem diminuir o tempo esperado para criar modelos, incluindo o número de experiências em suas [!UICONTROL Direcionamento automático] atividade, o tráfego para o site e a métrica de sucesso selecionada.

**Solução:** Analise sua configuração de atividade e veja se há alterações que você deseja fazer para melhorar a velocidade de criação dos modelos.

* Se sua métrica de sucesso estiver definida como [!UICONTROL RPV], é possível alterar para conversão? As atividades de conversão tendem a exigir menos tráfego para criar modelos. Você não perderá os dados da atividade se alterar a métrica de sucesso de RPV para conversão.
* Sua métrica de sucesso está bem abaixo do funil de vendas de suas experiências de atividade? Uma taxa de conversão de atividade mais baixa aumenta os requisitos de tráfego necessários para a criação de modelos, pois é necessário um número mínimo de conversões.
* Há algumas experiências que você pode abandonar em sua atividade? Diminuir o número de experiências em uma atividade diminui o tempo para criar modelos.
* Existe uma página de tráfego mais alto onde essa atividade seria mais bem-sucedida? Quanto mais tráfego e conversões houver nos locais de atividade, mais rápido será a criação de modelos.

+++

### Minha atividade de [!UICONTROL Direcionamento automático] não está gerando nenhum aumento.

+++Sugestões de solução de problemas Há quatro fatores necessários para uma [!UICONTROL Direcionamento automático] atividade para gerar aumento:

* As ofertas devem ser diferentes o suficiente para influenciar os visitantes.
* As ofertas devem estar localizadas em algum lugar que faça diferença para a meta de otimização.
* Deve haver tráfego e &quot;potência&quot; estatística suficiente no teste para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

**Solução:** primeiro, verifique se sua atividade está personalizando o tráfego. Se os modelos não são criados para todas as experiências, sua atividade de [!UICONTROL Direcionamento automático] ainda estará apresentando aleatoriamente uma parte significativa das visitas para tentar criar todos os modelos o mais rápido possível. Se os modelos não forem criados, o [!UICONTROL Direcionamento automático] não está personalizando o tráfego.

Em seguida, verifique se as ofertas e os locais de atividade realmente fazem diferença nas taxas de resposta geral usando um teste A/B simples e não personalizado. Certifique-se de calcular os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e executar o teste A/B por um período fixo sem interrompê-lo ou fazer quaisquer alterações. Se os resultados de um teste A/B mostrarem um aumento estatisticamente significativo em uma ou mais experiências, será provável que uma atividade personalizada funcione. A personalização pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre das ofertas e dos locais que não têm um impacto grande o suficiente na meta de otimização para serem detectados com significância estatística.

+++

### As métricas dependentes de uma métrica de conversão nunca convertem.

+++Sugestões de solução de problemas Isso é esperado.

Em um [!UICONTROL Direcionamento automático] atividade, depois que uma métrica de conversão (objetivo de otimização ou de postagem) é convertida, o usuário é liberado da experiência e a atividade é reiniciada.

Por exemplo, há uma atividade com uma métrica de conversão (C1) e uma métrica adicional (A1). A1 depende de C1. Quando um visitante entra na atividade pela primeira vez, e os critérios de conversão de A1 e C1 não são convertidos, a métrica A1 não é convertida por depender da métrica de sucesso. Se o visitante converter C1 e depois converter A1, A1 ainda não será convertido porque quando C1 é convertido, o visitante é liberado.

+++
