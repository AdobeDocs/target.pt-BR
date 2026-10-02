---
keywords: calculadora de tamanho de amostra;A/B;Alocação automática;significância estatística;volume de tráfego
description: Use a Calculadora de tamanho de amostra do Adobe Target para estimar a duração do experimento, o volume de tráfego ou o efeito mínimo detectável.
title: Calculadora de tamanho da amostra
feature: Activities
badge: label="Beta" type="Informative"
source-git-commit: d3fb1b69975951d41803be0eb902333332cb1ed1
workflow-type: tm+mt
source-wordcount: '1604'
ht-degree: 11%
---
# Calculadora de tamanho da amostra

>[!CONTEXTUALHELP]
>id="target_sample_size_ab_daily_traffic"
>title="Tráfego diário"
>abstract="Quantos usuários entram no experimento a cada dia. Se você não souber esse valor, escolha Volume de tráfego acima e a calculadora resolverá para ele usando as outras entradas."

>[!CONTEXTUALHELP]
>id="target_sample_size_confidence_level"
>title="Nível de confiança"
>abstract="Quão certo você precisa ser de que um resultado não se deve a uma chance aleatória antes de chamá-lo de significativo. Um nível de confiança de 95% significa que há no máximo 5% de chance de um falso positivo. Valores mais altos reduzem falsos positivos, mas também exigem mais dados."

>[!CONTEXTUALHELP]
>id="target_sample_size_statistical_power"
>title="Potência estatística"
>abstract="A probabilidade de detectar um efeito real, se existir. Um nível de energia de 80% significa que há uma chance de 80% de detectar um efeito verdadeiro. Uma potência mais alta reduz os falsos negativos, mas requer mais tráfego ou um tempo de execução mais longo."

>[!CONTEXTUALHELP]
>id="target_sample_size_setup_cja"
>title="Configurar o teste"
>abstract="Esses campos definem o experimento, o resultado esperado e o limite de confiança para o resultado. O campo vinculado ao valor selecionado acima é resolvido automaticamente; preencha os campos restantes com os valores esperados."


>[!AVAILABILITY]
>
>Ao usar esta calculadora de tamanho de exemplo (Beta), você reconhece que a Beta é fornecida &quot;no estado em que se encontra&quot; sem nenhum tipo de garantia. A Adobe não tem nenhuma obrigação de manter, corrigir, atualizar, alterar, modificar ou oferecer suporte à Beta. É recomendável ter cuidado e não depender de forma alguma do funcionamento ou desempenho correto desse Beta e/ou dos materiais que o acompanham. O Beta é considerado Informações confidenciais da Adobe.  Qualquer &quot;Feedback&quot; (informação sobre o Beta incluindo, mas não se limitando a, problemas ou defeitos encontrados durante o uso do Beta, sugestões, melhorias e recomendações) fornecido por Você ao Adobe é atribuído ao Adobe, incluindo todos os direitos, cargos e interesses no e no Feedback.

A **[!UICONTROL Calculadora de Tamanho da Amostra]** permite estimar as entradas necessárias para planejar um experimento antes de iniciá-lo. A calculadora ajuda a determinar quanto tráfego você precisa, quanto tempo o teste deve ser executado, quantas experiências devem ser incluídas ou qual efeito mínimo você pode detectar de forma confiável com base nos valores fornecidos.

Para acessar a **[!UICONTROL Calculadora de Tamanho da Amostra]**, acesse o menu **[!UICONTROL Atividades]**.

![](assets/calculator_menu.png)

## A/B (relatórios do Target)

>[!CONTEXTUALHELP]
>id="target_sample_size_bonferroni"
>title="Correção de Bonferroni"
>abstract="Ajusta o nível de confiança para considerar a comparação de mais de uma oferta com o controle ao mesmo tempo. Isso é importante somente quando o número de ofertas é maior que dois. Corresponde à mesma correção usada na ferramenta calculadora de público-alvo do Adobe."

>[!CONTEXTUALHELP]
>id="target_sample_size_metric_type"
>title="Tipo de métrica"
>abstract="Que tipo de métrica você está medindo. Use a Porcentagem para resultados binários, como cliques ou conversões, em que cada usuário conclui ou não a ação. Use Número para métricas como receita ou exibições de página, em que os valores podem variar amplamente de usuário para usuário."

>[!CONTEXTUALHELP]
>id="target_sample_size_number_offers"
>title="Número de ofertas"
>abstract="O número de experiências no experimento, incluindo o controle. Mais de duas ofertas aplicam automaticamente uma correção Bonferroni (quando ativada) para manter o nível de confiança geral preciso em todas as comparações."

>[!CONTEXTUALHELP]
>id="target_sample_size_lift"
>title="Aumento"
>abstract="A melhoria relativa em relação à linha de base que você deseja detectar. Insira-o como uma porcentagem da linha de base. Por exemplo, um aumento de 5% em uma taxa de conversão de linha de base de 11,8% tem como meta 12,39%."

>[!CONTEXTUALHELP]
>id="target_sample_size_baseline_conversion_rate"
>title="Índice de conversão de linha de base"
>abstract="Sua taxa de conversão atual antes do início do experimento, que é a média do braço de controle. Este valor é sempre obrigatório. Para métricas de porcentagem, insira uma porcentagem como 5 para 5%. Para métricas de contagem, insira o valor decimal bruto."

Estime as entradas necessárias para planejar e executar um teste A/B. Esses valores ajudam você a decidir quanto tráfego precisa, por quanto tempo o teste deve ser executado e qual tamanho de efeito pode ser detectado de forma realista.

1. Acesse a guia **[!UICONTROL A/B (Relatórios de Destino)]** para calcular entradas de planejamento para um teste A/B.

1. Habilite a opção **[!UICONTROL Aplicar correção]** para ajustar o nível de confiança e considerar a comparação de mais de uma oferta com o controle ao mesmo tempo.

1. Escolha seu **[!UICONTROL Tipo de métrica]**:

   * Índice de conversão: use essa opção para resultados binários, como cliques ou compras, em que cada visitante conclui ou não a ação.
   * Receita por visitante: use essa opção para métricas de estilo de receita, em que os valores podem variar bastante de visitante para visitante.

     ![](assets/calculator-target_reporting_1.png)

1. Especifique o **[!UICONTROL Tráfego diário]**, o número de usuários entrando no experimento a cada dia.

1. Em **[!UICONTROL Configurar o teste]**, insira os valores restantes:

   * **[!UICONTROL Número de ofertas]**: o número de experiências em seu experimento, incluindo o controle. Mais de duas ofertas aplicam uma correção Bonferroni, quando habilitada, para manter o nível geral de confiança.

   * **[!UICONTROL Aumento]**: a melhoria relativa em relação à linha de base que você deseja detectar. Insira-o como um percentual da linha de base, por exemplo, um aumento de 5% em uma meta de taxa de conversão de linha de base de 11,8% e 12,39%.

     ![](assets/calculator-target_reporting_2.png)

1. Especifique o **[!UICONTROL Índice de conversão da linha de base]** para a sua experiência atual antes do início do experimento.

1. Você pode expandir **[!UICONTROL Configurações estatísticas avançadas]** para fornecer entradas estatísticas adicionais quando elas estiverem disponíveis para o cálculo selecionado.

   * **[!UICONTROL Nível de confiança]**: a probabilidade de um resultado não ser aleatório. Um nível de 95% permite uma chance de 5% de um falso positivo.

   * **[!UICONTROL Potência estatística]**: a probabilidade de detectar um efeito real. Uma energia de 80% reduz falsos negativos, mas requer mais tráfego ou tempo.

1. Selecione **[!UICONTROL Executar cálculo]** para gerar a estimativa. Selecione **[!UICONTROL Redefinir]** para limpar as entradas atuais e iniciar novamente.

O painel **[!UICONTROL Resultado]** exibe a estimativa depois que você conclui os campos obrigatórios e executa o cálculo. Se os campos obrigatórios estiverem incompletos, o painel solicitará que você insira os valores ausentes.

![](assets/calculator-cja-analytics-3.png)

A calculadora fornece uma estimativa para planejar um experimento. Use o resultado junto com o design do experimento, o tráfego esperado, o desempenho da linha de base e os requisitos estatísticos ao decidir por quanto tempo executar a atividade.

## A/B (CJA/Adobe Analytics)

>[!CONTEXTUALHELP]
>id="target_sample_size_number_experiences"
>title="Número de experiências"
>abstract="Número de variantes no experimento, incluindo o controle. Um teste A/B tem 2 braços. Cinco variantes mais um controle é igual a 6. Mais braços exige proporcionalmente mais tráfego para manter a potência estatística."

>[!CONTEXTUALHELP]
>id="target_sample_size_duration"
>title="Duração do teste A/B"
>abstract="Por quantos dias o experimento será realizado. Durações mais longas dão ao experimento mais tempo para coletar dados, permitindo detectar efeitos menores de maneira confiável. Durações mais curtas precisam de efeitos maiores ou de mais tráfego diário para alcançar um resultado confiável."

>[!CONTEXTUALHELP]
>id="target_sample_size_expected_improvement"
>title="Melhorias esperadas"
>abstract="A menor melhoria que vale a pena detectar, a alteração mínima na métrica que motivaria uma ação. Este é o tamanho do aumento em pontos percentuais, não a alteração percentual em relação à linha de base. Por exemplo, se a linha de base for 5% e um aumento de 1 ponto percentual for relevante, digite 1."

>[!CONTEXTUALHELP]
>id="target_sample_size_variance"
>title="Variância"
>abstract="Como são distribuídos os valores da sua métrica, não o valor médio. Uma métrica, como a taxa de cliques (geralmente 0s e 1s), normalmente tem baixa variação, enquanto uma métrica, como a receita por usuário, pode ter uma variação muito maior. Se não tiver certeza, deixe o valor padrão como 1."

Estime as entradas de planejamento para uma atividade A/B que depende dos dados do Adobe Analytics ou do Customer Journey Analytics. Isso ajuda a definir o tamanho do experimento, o aumento esperado e a duração do teste antes de iniciar a atividade.

1. Acesse a guia **[!UICONTROL A/B (CJA/Adobe Analytics)]** para calcular entradas de planejamento para um teste A/B.

1. Em **[!UICONTROL O que você deseja saber?]**, selecione o valor que deseja que a calculadora determine:

   * **[!UICONTROL Duração]**: você tem um experimento em mente e deseja saber quanto tempo levaria para ser executado e se vale a pena executá-lo.
   * **[!UICONTROL Número de experiências]**: você tem um local para executar um experimento e deseja descobrir quantos tratamentos seu tráfego poderia suportar.
   * **[!UICONTROL Volume de tráfego]**: você tem um experimento em mente e deseja saber quantos visitantes precisam para atingir significância estatística.
   * **[!UICONTROL Efeito mínimo detectável]**: você tem um experimento que deseja executar, mas deseja saber quanto de um aumento é necessário para atingir significância estatística. Isso ajuda a avaliar se vale a pena executar ou planejar o experimento.

   Os campos no formulário mudam dependendo do valor selecionado. A calculadora usa as outras entradas para determinar o resultado selecionado.

   ![](assets/calculator-cja-analytics-1.png)

1. Especifique o **[!UICONTROL Tráfego diário]**, o número de usuários entrando no experimento a cada dia.

1. Em **[!UICONTROL Configurar o teste]**, insira os valores restantes:

   * **[!UICONTROL Número de experiências]**: o número de variantes, incluindo o controle. Mais variantes exigem mais tráfego.

   * **[!UICONTROL Duração do teste A/B]**: o número de dias que o experimento é executado. Testes mais longos podem detectar efeitos menores.

   * **[!UICONTROL Aperfeiçoamento esperado]**: o aprimoramento que você espera que o experimento produza.

   * **[!UICONTROL Variação]**: a extensão dos valores de métrica. Uma taxa de click-through geralmente tem baixa variação, a receita por usuário pode ser muito maior. Se não tiver certeza, deixe o valor padrão como 1.

     Saiba como calcular uma **[!UICONTROL Variação]** na [documentação do Analytics](https://experienceleague.adobe.com/en/docs/analytics/components/calculated-metrics/calcmetrics-reference/cm-functions#variance)

     ![](assets/calculator-cja-analytics-2.png)

1. Você pode expandir **[!UICONTROL Configurações estatísticas avançadas]** para fornecer entradas estatísticas adicionais quando elas estiverem disponíveis para o cálculo selecionado.

   * **[!UICONTROL Nível de confiança]**: a probabilidade de um resultado não ser aleatório. Um nível de 95% permite uma chance de 5% de um falso positivo. Níveis de confiança mais baixos significam menos tráfego, mas também aumentam o risco de um falso positivo.

   * **[!UICONTROL Potência estatística]**: a probabilidade de detectar um efeito real. Uma energia de 80% reduz falsos negativos, mas requer mais tráfego ou tempo.

1. Selecione **[!UICONTROL Executar cálculo]** para gerar a estimativa. Selecione **[!UICONTROL Redefinir]** para limpar as entradas atuais e iniciar novamente.

O painel **[!UICONTROL Resultado]** exibe a estimativa depois que você conclui os campos obrigatórios e executa o cálculo. Se os campos obrigatórios estiverem incompletos, o painel solicitará que você insira os valores ausentes.

![](assets/calculator-cja-analytics-4.png)

A calculadora fornece uma estimativa para planejar um experimento. Use o resultado junto com o design do experimento, o tráfego esperado, o desempenho da linha de base e os requisitos estatísticos ao decidir por quanto tempo executar a atividade.
