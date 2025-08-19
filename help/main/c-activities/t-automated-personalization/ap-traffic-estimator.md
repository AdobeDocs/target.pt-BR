---
keywords: avaliador de tráfego;personalização automatizada;ap;estimar tráfego;traffic estimor;automated personalization;ap;estimate traffic
description: Use o [!UICONTROL Traffic Estimator] para avaliar se você tem tráfego suficiente para uma atividade [!UICONTROL Automated Personalization] ser bem-sucedida.
title: Quanto tráfego é necessário para uma atividade [!UICONTROL Automated Personalization] bem-sucedida?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Automated Personalization
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
source-git-commit: 3a44c05bea24c622292dd0b774f88f0c93be1d88
workflow-type: tm+mt
source-wordcount: '721'
ht-degree: 9%

---

# Estimativa de tráfego exigido para o sucesso

O [!DNL Adobe Target] [!UICONTROL Traffic Estimator] fornece feedback que permite saber se você tem tráfego suficiente para que sua atividade de [!UICONTROL Automated Personalization] (AP) tenha sucesso.

Como as atividades do [!UICONTROL Automated Personalization] usam várias combinações de ofertas, é importante saber quanto tráfego é necessário para fornecer resultados significativos. O [!UICONTROL Traffic Estimator] usa estatísticas sobre sua página e o número de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessárias para tornar a atividade bem-sucedida.

O [!UICONTROL Traffic Estimator] determina se há tráfego suficiente para gerar modelos personalizados, comparando as impressões de página estimadas e o índice de conversão típico para as páginas. Idealmente, para uma atividade bem-sucedida, o tamanho de amostra correto garante que o conteúdo personalizado esteja pronto em 50% da duração da atividade ou 14 dias, o que for menor. Esse processo permite tempo suficiente para obter conteúdo personalizado e saber qual conteúdo fornecer.

Lembre-se de que o [!DNL Target] fornece experiências aleatoriamente até que os algoritmos de personalização sejam compilados. O ícone de marca de seleção ao lado de cada oferta mostra quando o modelo dessa oferta está pronto e o [!DNL Target] pode começar a fornecer conteúdo personalizado. Como o aumento é esperado somente depois que os modelos estiverem prontos, a indicação visual permite definir a expectativa correta. Use o [!UICONTROL Traffic Estimator] no [!UICONTROL Visual Experience Composer] (VEC) para obter uma diretriz de quando os modelos estão prontos.

## Usar o Avaliador de tráfego

1. Na página [!UICONTROL Experiences] de [!UICONTROL Visual Experience Composer] em uma atividade [!UICONTROL Automated Personalization], clique no ícone **[!UICONTROL Traffic]** ( ![Ícone do Avaliador de Tráfego](/help/main/assets/icons/Gauge2.svg) ) no canto superior esquerdo da página [!UICONTROL Experiences].

   O [!UICONTROL Traffic Estimator] se abre.

   ![Interface de usuário do Avaliador de tráfego](assets/ap-est.png)

   Você pode clicar no ícone novamente para ocultar o [!UICONTROL Traffic Estimator].

1. Especifique o índice de conversão típico (ou o índice de conversão que você espera dessa atividade), as impressões de atividade estimadas por dia e a duração do teste.

   | Métrica | Descrição |
   | --- | --- |
   | **[!UICONTROL Number of Offers]** | Essa métrica é calculada automaticamente com base no número de experiências que estão sendo criadas como parte da atividade, após as exclusões. |
   | **[!UICONTROL Typical Conversion Rate]** | Essa métrica é expressa como uma porcentagem, com base na estimativa ou dados anteriores do sistema de análise. |
   | **[!UICONTROL Estimated Visits Per Day]** | Essa métrica é o número de visitas por dia dos visitantes que podem visualizar a atividade com base nos critérios de direcionamento. Essa métrica pode se basear nos dados de análise. Esse número deve ser de visitas, não de visitantes únicos. |
   | **[!UICONTROL Test Duration]** | A quantidade de dias de duração da execução da atividade. |

   O [!UICONTROL Traffic Estimator] usa essas métricas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   Próximo à parte superior de [!UICONTROL Traffic Estimator], os valores inseridos são calculados e os resultados são mostrados.

   ![Estimativa de tráfego com valores e resultados exibidos](assets/ap-est-no.png)

   A estimativa muda, à medida que você muda os números. Por exemplo, se você estiver testando muitas combinações e sua taxa de conversão e impressões estiverem muito baixas, o [!UICONTROL Traffic Estimator] mostra por quanto tempo o teste deve ser executado para ser bem-sucedido. Ou, se o tráfego for baixo, o [!UICONTROL Traffic Estimator] pode sugerir um número menor de combinações de ofertas para que você possa executar o teste pelo número desejado de dias.

   Se você não tiver tráfego suficiente, considere o seguinte:

   * Considere usar uma atividade [[!UICONTROL Auto-Target]](/help/main/c-activities/auto-target/auto-target-to-optimize.md) em vez de [!UICONTROL Automated Personalization] para criar experiências com várias alterações de oferta em uma variação de experiência.
   * Reduza o número de combinações de ofertas na atividade [!UICONTROL Automated Personalization].
   * Aumente a duração da atividade.

   Ajuste os números até que [!UICONTROL Traffic Estimator] indique que você tem tráfego suficiente e, em seguida, crie seu teste de acordo.

   ![Avaliador de tráfego mostrando mensagem de tráfego suficiente](assets/ap-est-yes.png)

   Se o tráfego for suficiente, o ícone [!UICONTROL Traffic] mostrará uma marca de seleção verde. Se não for suficiente, o ícone mostrará um rótulo de aviso vermelho.

## Perguntas frequentes sobre o avaliador de tráfego

Considere as seguintes perguntas frequentes ao trabalhar com o [!UICONTROL Traffic Estimator]:

### Por que os modelos personalizados não são criados mesmo que minha atividade de AP tenha tráfego suficiente?

Em determinadas circunstâncias, seu tráfego é grande o suficiente para um modelo personalizado ser criado, mas esse tráfego pode informar [!DNL Target] que não há diferença significativa entre o modelo personalizado e o aleatório. Embora o modelo seja compilado em [!DNL Target] e testado, ele não é implantado porque o modelo não é melhor que aleatório.

Uma possível razão para o modelo não ser melhor do que aleatório pode ser que as ofertas não são suficientemente diferentes umas das outras. Em caso positivo, você pode tentar tornar as ofertas visualmente diferentes se a mensagem for semelhante, ou pode tentar alterar a própria mensagem.
