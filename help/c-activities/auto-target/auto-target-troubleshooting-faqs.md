---
keywords: direcionamento automático, direcionamento, alocação de tráfego, perguntas frequentes, perguntas frequentes, solução de problemas, solução de problemas, tráfego
description: Explore tópicos de solução de problemas e perguntas frequentes sobre as atividades do Direcionamento automático no Adobe Target.
title: Como posso solucionar problemas de atividades de direcionamento automático?
feature: Direcionamento automático
exl-id: 934f738e-560a-4847-9608-432ecfa2afe7
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1919'
ht-degree: 68%

---

# ![](/help/assets/premium.png) PREMIUMAuto-Target Solução de problemas e perguntas frequentes

Solução de problemas e perguntas frequentes sobre o [!UICONTROL Direcionamento automático] em [!DNL Adobe Target].

## Perguntas frequentes sobre direcionamento automático {#section_5C120A2B11D14D9BAF767BBAB50FED23}

Consulte as seguintes perguntas frequentes e respostas ao trabalhar com as atividades de [!UICONTROL Direcionamento automático]:

### Quais são as práticas recomendadas para configurar uma atividade de [!UICONTROL Direcionamento automático]?

* Decida se o valor comercial de uma métrica de sucesso de Receita por visita (RPV) vale os requisitos adicionais de tráfego. O RPV normalmente precisa de pelo menos 1.000 conversões por experiência para que uma atividade funcione em comparação com a conversão.
* Decida sobre a alocação entre controle e experiências personalizadas antes de iniciar a atividade com base em suas metas.
* Determine se você tem tráfego suficiente para a página em que sua atividade de [!UICONTROL Direcionamento automático] será executada para modelos de personalização a serem criados em um período de tempo razoável.
   * Se você estiver testando o algoritmo de personalização, não altere experiências nem adicione/remova atributos de perfil enquanto a atividade estiver ativa.

* Considere a conclusão de uma atividade A/B entre as ofertas e os locais que você planeja usar em sua atividade de [!UICONTROL Direcionamento automático] para garantir que os locais e as ofertas tenham impacto na meta de otimização. Se uma atividade A/B não demonstrar uma diferença significativa, o [!UICONTROL Direcionamento automático] provavelmente também não gerará aumento.

   * Se um teste A/B não mostra diferenças estatisticamente significativas entre as experiências, é provável que as ofertas que você está considerando não são suficientemente diferentes umas das outras, os locais selecionados não afetam a métrica de sucesso ou a meta de otimização está muito distante no funil de conversão a ser afetado pelas ofertas escolhidas.

* Tente não fazer mudanças substanciais nas experiências durante o curso da atividade.

### Você recomenda usar Auto [!DNL Target] com uma divisão 90(Controle)/10 (Direcionado) até que os modelos sejam criados?

A divisão de alocação de tráfego ideal depende do que você deseja realizar.

Se a sua meta for personalizar o máximo tráfego possível, você poderá manter o 90% de direcionamento e o controle de 10% durante toda a vida útil da atividade. Se o objetivo é executar um experimento comparando o desempenho dos algoritmos personalizados com o controle, uma divisão 50/50 é melhor para a duração da atividade.

A prática recomendada é manter a divisão de alocação de tráfego para a duração da atividade, para que os visitantes não alterem entre experiências de direcionamento e de controle.

<!-- 
### Do the check marks indicating a model is built for that experience update if the report date range changes?

No, check marks for model generation show only the models built to date. There's no way to go back and see when a model was completed.
-->

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

O tempo que leva para os modelos serem construídos em sua atividade de [!UICONTROL Direcionamento automático] normalmente depende do tráfego para os locais de atividade selecionados e das taxas de conversão associadas à métrica de sucesso da atividade.

[!UICONTROL O ] Direcionamento automático não tentará criar um modelo personalizado para uma determinada experiência até que haja pelo menos 50 conversões para ela. Além disso, se o modelo criado for de qualidade insuficiente (conforme determinado pela avaliação offline dos dados de &quot;teste&quot; em espera, usando [uma métrica conhecida como AUC](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)), o modelo não será usado para veicular o tráfego de maneira personalizada.

Alguns outros pontos para ter em mente sobre a criação de modelo do [!UICONTROL Direcionamento automático]:

* Quando uma atividade está ativa, o [!UICONTROL Direcionamento automático] considera até os últimos 45 dias de dados fornecidos aleatoriamente ao tentar criar modelos (ou seja, controlar o tráfego, além de alguns dados fornecidos aleatoriamente extras retidos pelo algoritmo).
* Quando [!UICONTROL Receita por visita] é sua métrica de sucesso, essas atividades normalmente exigem mais dados para criar modelos devido à maior variação de dados que normalmente existe na receita de visitas em comparação com a taxa de conversão.
* Como os modelos são criados com base na experiência, a substituição de uma experiência por outra significa que o tráfego suficiente (ou seja, pelo menos 50 conversões) deve ser coletado para a nova experiência antes que os modelos personalizados possam ser recriados.

### Um modelo é construído na minha atividade. As visitas a essa experiência são personalizadas?

Não, deve haver pelo menos dois modelos construídos em sua atividade para que a personalização comece.

### Quando posso ver os resultados da minha atividade de [!UICONTROL Direcionamento automático]?

Você pode começar a ver os resultados da sua atividade de [!UICONTROL Direcionamento automático] depois de ter pelo menos duas experiências com modelos construídos (marca de seleção verde) para a experiência que os modelos construíram.

### Posso definir uma experiência específica para ser usada como controle?

É possível selecionar uma experiência para ser usada como controle ao criar uma atividade de [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md) (AP) ou de [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) (AT).

Esse recurso permite rotear todo o tráfego de controle para uma experiência específica, com base na porcentagem de alocação de tráfego configurada na atividade. Em seguida, você pode avaliar os relatórios de desempenho do tráfego personalizado com relação ao tráfego de controle para essa experiência única.

Para obter mais informações, consulte [Usar uma experiência específica como controle](/help/c-activities/t-automated-personalization/experience-as-control.md).

### Posso alterar a métrica de meta até o meio de uma atividade de Direcionamento automático ? {#change-metric}

Não recomendamos que você altere a métrica de meta para a metade de uma atividade. Embora seja possível alterar a métrica de meta durante uma atividade usando a interface do usuário [!DNL Target], você sempre deve iniciar uma nova atividade. Não garantimos o que acontece se você alterar a métrica de meta em uma atividade após sua execução.

Esta recomendação se aplica às atividades de [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Automated Personalization] que usam [!DNL Target] ou [!DNL Analytics] (A4T) como fonte de relatórios.

### Posso usar a opção Redefinir dados de relatório ao executar uma atividade de Direcionamento automático?

Não é sugerido usar a opção [!UICONTROL Redefinir dados de relatório] para atividades de [!UICONTROL Direcionamento automático]. Embora ela remova os dados de relatório visíveis, essa opção não remove todos os registros de treinamento do modelo [!UICONTROL Direcionamento automático]. Em vez de usar a opção [!UICONTROL Reset Report Data] para [!UICONTROL Direcionamento automático] atividades, crie uma nova atividade e desative a atividade original. (Observação: Esta orientação também se aplica às atividades de [!UICONTROL Alocação automática] e [!UICONTROL Automated Personalization].)

### O que acontece se eu remover uma única experiência de uma atividade de Direcionamento automático ?

[!DNL Target] O cria um modelo por experiência, portanto, remover uma experiência significa  [!DNL Target] apenas criar um modelo a menos e não afetará os modelos para as outras experiências.

Por exemplo, suponha que você tenha uma atividade de [!UICONTROL Direcionamento automático] com oito experiências e não goste do desempenho de uma experiência. Você pode remover essa experiência e ela não afetará os modelos das sete experiências restantes.

## Solução de problemas do [!UICONTROL Direcionamento automático] {#section_23995AB813F24525AF294D20A20875C8}

Às vezes, as atividades não acontecem como o esperado. Aqui estão alguns possíveis desafios que você pode enfrentar ao usar o [!UICONTROL Direcionamento automático] e algumas soluções sugeridas.

### Minha atividade de [!UICONTROL Direcionamento automático] está demorando muito para criar modelos.

Há várias alterações de configuração de atividade que podem diminuir o tempo esperado para criar modelos, incluindo o número de experiências em sua atividade de [!UICONTROL Direcionamento automático], o tráfego para seu site e sua métrica de sucesso selecionada.

**Solução:** revise a configuração da atividade e veja se deseja fazer alguma alteração para melhorar a velocidade de criação dos modelos.

* Se sua métrica de sucesso estiver definida como RPV, será possível mudar para conversão? As atividades de conversão tendem a exigir menos tráfego para criar modelos. Você não perderá os dados da atividade se alterar a métrica de sucesso de RPV para conversão.
* Sua métrica de sucesso está bem abaixo do funil de vendas de suas experiências de atividade? Uma taxa de conversão de atividade menor aumentará os requisitos de tráfego necessários para a criação de modelos, pois é necessário um número mínimo de conversões.
* Há algumas experiências que você pode abandonar em sua atividade? A diminuição do número de experiências em uma atividade irá diminuir a quantidade de tempo para construir modelos.
* Existe uma página de tráfego mais alto onde essa atividade seria mais bem-sucedida? Quanto mais tráfego e conversões em seus locais de atividade, mais rápidos serão os modelos.

### Minha atividade de [!UICONTROL Direcionamento automático] não está gerando nenhum aumento.

Há quatro fatores necessários para uma atividade de AP gerar aumento:

* As ofertas precisam ser diferentes o suficiente para influenciar os visitantes.
* As ofertas precisam estar localizadas em um lugar que faça diferença na meta de otimização.
* Deve haver tráfego e &quot;potência&quot; estatística suficiente no teste para detectar o aumento.
* O algoritmo de personalização deve funcionar corretamente.

**Solução:** primeiro, verifique se sua atividade está personalizando o tráfego. Se os modelos não são criados para todas as experiências, sua atividade de [!UICONTROL Direcionamento automático] ainda estará apresentando aleatoriamente uma parte significativa das visitas para tentar criar todos os modelos o mais rápido possível. Se os modelos não forem criados, o [!UICONTROL Direcionamento automático] não está personalizando o tráfego.

Em seguida, verifique se as ofertas e os locais de atividade realmente fazem diferença nas taxas de resposta gerais usando um teste A/B simples e não personalizado. Certifique-se de calcular os tamanhos das amostras antecipadamente para garantir que haja energia suficiente para ver um aumento razoável e executar o teste A/B por um período fixo sem interrompê-lo ou fazer quaisquer alterações. Se um resultado do teste A/B mostrar um aumento estatisticamente significativo em uma ou mais das experiências, é provável que uma atividade personalizada funcione. Claro, a personalização pode funcionar mesmo se não houver diferenças nas taxas de resposta geral das experiências. Normalmente, o problema decorre de ofertas/locais que não têm um impacto suficientemente grande na meta da otimização para serem detectados com significância estatística.

### As métricas dependentes de métrica de conversão nunca convertem.

Isso é esperado.

Em uma atividade de [!UICONTROL Direcionamento automático], depois que uma métrica de conversão (objetivo de otimização ou de postagem) é convertida, o usuário é liberado da experiência e a atividade é reiniciada.

Por exemplo, há uma atividade com uma métrica de conversão (C1) e uma métrica adicional (A1). A1 depende de C1. Quando um visitante entra na atividade pela primeira vez, e os critérios de conversão de A1 e C1 não são convertidos, a métrica A1 não é convertida por depender da métrica de sucesso. Se o visitante converte C1 e depois converte A1, A1 ainda não é convertida porque, assim que C1 é convertida, o visitante é liberado.
