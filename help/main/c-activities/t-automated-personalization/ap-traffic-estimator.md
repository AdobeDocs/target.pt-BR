---
keywords: avaliador de tráfego;personalização automatizada;ap;estimar tráfego;traffic estimor;automated personalization;ap;estimate traffic
description: Use o [!DNL Adobe Target] [!UICONTROL Avaliador de tráfego] para determinar se você tem tráfego suficiente para o seu [!UICONTROL Automated Personalization] atividade para ter sucesso.
title: Quanto tráfego é necessário para um evento bem-sucedido [!UICONTROL Automated Personalization] Atividade?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: eacee6f353aa685d17b781ac82d3f79574384dfe
workflow-type: tm+mt
source-wordcount: '779'
ht-degree: 11%

---

# Estimativa de tráfego exigido para o sucesso

A variável [!DNL Adobe Target] [!UICONTROL Avaliador de tráfego] O fornece feedback que permite saber se você tem tráfego suficiente para o seu [!UICONTROL Automated Personalization] (AP) para ter sucesso.

Porque [!UICONTROL Automated Personalization] As atividades do usam várias combinações de ofertas. É importante saber quanto tráfego é necessário para fornecer resultados significativos. A variável [!UICONTROL Avaliador de tráfego] O usa estatísticas sobre a sua página e o número de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessárias para tornar a atividade bem-sucedida.

A variável [!UICONTROL Avaliador de tráfego] determina se há tráfego suficiente para gerar modelos personalizados comparando as impressões de página estimadas e o índice de conversão típico para as páginas. Idealmente, para uma atividade bem-sucedida, o tamanho de amostra correto garante que o conteúdo personalizado esteja pronto em 50% da duração da atividade ou 14 dias, o que for menor. Esse processo permite tempo suficiente para obter conteúdo personalizado e saber qual conteúdo fornecer.

Lembre-se [!DNL Target] disponibiliza experiências aleatoriamente até que os algoritmos de personalização sejam criados. O ícone de marca de seleção ao lado de cada oferta mostra quando o modelo dessa oferta está pronto e [!DNL Target] O pode começar a fornecer conteúdo personalizado. Como o aumento é esperado somente depois que os modelos estiverem prontos, a indicação visual permite definir a expectativa correta. Use o [!UICONTROL Avaliador de tráfego] no [!UICONTROL Visual Experience Composer] (VEC) para obter uma diretriz sobre quando os modelos estão prontos.

## Usar o Avaliador de tráfego

1. No [!UICONTROL Experiências] página do [!UICONTROL Visual Experience Composer] em um [!UICONTROL Automated Personalization] clique na guia  **[!UICONTROL Tráfego]** ícone.

   ![Ícone de tráfego](/help/main/c-activities/t-automated-personalization/assets/icon-traffic.png)

   A variável [!UICONTROL Avaliador de tráfego] é aberto. Você pode clicar em **[!UICONTROL Tráfego]**[!UICONTROL  novamente para ocultar o Avaliador de tráfego].

   ![Interface do usuário do Avaliador de tráfego](assets/ap_est.png)

1. Especifique o índice de conversão típico (ou o índice de conversão que você espera dessa atividade), as impressões de atividade estimadas por dia e a duração do teste.

   | Métrica | Descrição |
   | --- | --- |
   | **[!UICONTROL Número de ofertas]** | Essa métrica é calculada automaticamente com base no número de experiências que estão sendo criadas como parte da atividade, após as exclusões. |
   | **[!UICONTROL Taxa comum de conversão]** | Essa métrica é expressa como uma porcentagem, com base na estimativa ou dados anteriores do sistema de análise. |
   | **[!UICONTROL Visitas estimadas por dia]** | Essa métrica é o número de visitas por dia dos visitantes que podem visualizar a atividade com base nos critérios de direcionamento. Essa métrica pode se basear nos dados de análise. Esse número deve ser de visitas, não de visitantes únicos. |
   | **[!UICONTROL Duração do teste]** | A quantidade de dias de duração da execução da atividade. |

   A variável [!UICONTROL Avaliador de tráfego] O usa essas métricas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   Próximo à parte superior do [!UICONTROL Avaliador de tráfego], os valores inseridos são calculados e os resultados são mostrados.

   ![Estimativa de tráfego com valores e resultados exibidos](assets/ap_est_no.png)

   A estimativa muda, à medida que você muda os números. Por exemplo, se você estiver testando muitas combinações e sua taxa de conversão e impressões estiverem muito baixas, a variável [!UICONTROL Avaliador de tráfego] mostra por quanto tempo o teste deve ser executado para ter sucesso. Ou, se o tráfego estiver baixo, a variável [!UICONTROL Avaliador de tráfego] O pode sugerir um número menor de combinações de ofertas para que você possa executar o teste pelo número desejado de dias.

   Se você não tiver tráfego suficiente, considere o seguinte:

   * Considere usar um [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) atividade em vez de [!UICONTROL Automated Personalization] para criar experiências com várias alterações de oferta em uma variação de experiência.
   * Reduza o número de combinações de ofertas em seu [!UICONTROL Automated Personalization] atividade.
   * Aumente a duração da atividade.

   Ajuste os números até a variável [!UICONTROL Avaliador de tráfego] indica que você tem tráfego suficiente e, em seguida, projete seu teste adequadamente.

   ![Avaliador de tráfego mostrando mensagem de tráfego suficiente](assets/ap_est_yes.png)

   Se o tráfego for suficiente, a variável [!UICONTROL Tráfego] O ícone mostra uma marca de seleção verde. Se não for suficiente, o ícone mostrará um rótulo de aviso vermelho.

## Perguntas frequentes sobre o avaliador de tráfego

Considere as seguintes perguntas frequentes ao trabalhar com a [!UICONTROL Avaliador de tráfego]:

### Por que os modelos personalizados não são criados mesmo que minha atividade de AP tenha tráfego suficiente?

Em determinadas circunstâncias, seu tráfego é grande o suficiente para um modelo personalizado ser criado, mas esse tráfego pode informar [!DNL Target] que não há diferença significativa entre o modelo personalizado e o aleatório. Embora o modelo seja incorporado no [!DNL Target] e testado, ele não é implantado porque o modelo não é melhor que o aleatório.

Uma possível razão para o modelo não ser melhor do que aleatório pode ser que as ofertas não são suficientemente diferentes umas das outras. Em caso positivo, você pode tentar tornar as ofertas visualmente diferentes se a mensagem for semelhante, ou pode tentar alterar a própria mensagem.
