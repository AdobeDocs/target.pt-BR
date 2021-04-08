---
keywords: avaliador de tráfego, personalização automatizada, ap, estimar tráfego, direcionamento automático
description: Use o Avaliador de tráfego do Adobe Target para determinar se você tem tráfego suficiente para que sua atividade do Automated Personalization seja bem-sucedida.
title: Quanto tráfego é necessário para uma atividade bem-sucedida?
feature: Personalização automatizada
exl-id: 11f9e239-700b-45cd-bf77-39f7f8967a2e
translation-type: tm+mt
source-git-commit: 6ba670ef69fa23c0023636a1920eed15dcd9dd06
workflow-type: tm+mt
source-wordcount: '753'
ht-degree: 14%

---

# ![PREMIUM](/help/assets/premium.png) Estimativa do tráfego necessário para o sucesso

O [!DNL Adobe Target] [!UICONTROL Avaliador de tráfego] fornece feedback que permite saber se você tem tráfego suficiente para sua atividade [!UICONTROL Automated Personalization] ser bem-sucedida.

Como uma atividade [!UICONTROL Automated Personalization] usa várias combinações de ofertas, é importante saber quanto tráfego é necessário para fornecer resultados significativos. O [!UICONTROL Avaliador de tráfego] usa estatísticas sobre a página e o número de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessárias para que a atividade seja bem-sucedida.

O [!UICONTROL Avaliador de tráfego] determina se há tráfego suficiente para gerar modelos personalizados, comparando as impressões de página estimadas e o índice de conversão típico das páginas. Idealmente, para uma atividade bem-sucedida, o tamanho de amostra correto garante que o conteúdo personalizado esteja pronto em 50% da duração da atividade ou 14 dias, o que for menor. Esse processo permite tempo suficiente para obter conteúdo personalizado e saber qual conteúdo fornecer.

Lembre-se de que [!DNL Target] fornece experiências aleatoriamente até que os algoritmos de personalização sejam criados. O ícone de marca de seleção ao lado de cada oferta mostra quando o modelo dessa oferta está pronto e [!DNL Target] é capaz de começar a entregar conteúdo personalizado. Como aumento é esperado somente depois que os modelos estão prontos, a indicação visual permite definir a expectativa correta. Use o [!UICONTROL Avaliador de tráfego] no [!UICONTROL Visual Experience Composer] (VEC) para obter uma orientação sobre quando os modelos estão prontos.

## Usar o Avaliador de Tráfego

1. No [!UICONTROL Visual Experience Composer], clique em **[!UICONTROL Tráfego]**.

   ![Ícone de tráfego](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   O [!UICONTROL Avaliador de tráfego] é aberto. Você pode clicar em **[!UICONTROL Tráfego]**[!UICONTROL  novamente para ocultar o Avaliador de tráfego].

   ![Interface do usuário do Avaliador de tráfego](assets/ap_est.png)

1. Especifique o índice de conversão típico (ou o índice de conversão que você espera dessa atividade), as impressões de atividade estimadas por dia e a duração do teste.

   | Métrica | Descrição |
   | --- | --- |
   | **[!UICONTROL Número de ofertas]** | Essa métrica é calculada automaticamente com base no número de experiências que estão sendo criadas como parte da atividade, após as exclusões. |
   | **[!UICONTROL Taxa comum de conversão]** | Essa métrica é expressa como uma porcentagem, com base na estimativa ou dados anteriores do sistema de análise. |
   | **[!UICONTROL Visitas estimadas por dia]** | Essa métrica é o número de visitas por dia dos visitantes que podem visualizar a atividade com base nos critérios de direcionamento. Essa métrica pode ser baseada nos dados analíticos. Esse número deve ser de visitas, não de visitantes únicos. |
   | **[!UICONTROL Duração do teste]** | A quantidade de dias de duração da execução da atividade. |

   O [!UICONTROL Avaliador de tráfego] usa essas métricas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   Próximo à parte superior do [!UICONTROL Avaliador de tráfego], os valores inseridos são calculados e os resultados são mostrados.

   ![Estimativa de tráfego com valores e resultados exibidos](assets/ap_est_no.png)

   A estimativa muda, à medida que você muda os números. Por exemplo, se você estiver testando muitas combinações e sua taxa de conversão e impressões for muito baixa, o [!UICONTROL Avaliador de tráfego] mostrará por quanto tempo o teste deve ser executado para ser bem-sucedido. Ou, se o tráfego for baixo, o [!UICONTROL Avaliador de tráfego] poderá sugerir um número menor de combinações de ofertas para que você possa executar o teste no número desejado de dias.

   Se você não tiver tráfego suficiente, considere o seguinte:

   * Considere usar uma atividade [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) em vez de [!UICONTROL Automated Personalization] para criar experiências com várias alterações de oferta em uma variação de experiência.
   * Reduza o número de combinações de ofertas em sua atividade [!UICONTROL Automated Personalization].
   * Aumente a duração da atividade.

   Ajuste os números até que o [!UICONTROL Avaliador de tráfego] indique que você tem tráfego suficiente e, em seguida, crie seu teste de acordo.

   ![Avaliador de tráfego mostrando mensagem de tráfego suficiente](assets/ap_est_yes.png)

   Se o tráfego for suficiente, o ícone [!UICONTROL Tráfego] mostrará uma marca de seleção verde. Se não for suficiente, o ícone mostrará um rótulo de aviso vermelho.

## Perguntas frequentes sobre o Avaliador de tráfego

Considere as seguintes perguntas frequentes ao trabalhar com o [!UICONTROL Avaliador de tráfego]:

### Por que os modelos personalizados não são criados mesmo que minha atividade de AP tenha tráfego suficiente?

Em determinadas circunstâncias, seu tráfego é grande o suficiente para um modelo personalizado ser criado, mas esse tráfego pode informar [!DNL Target] que não há diferença significativa entre o modelo personalizado e o aleatório. Embora o modelo seja construído em [!DNL Target] e testado, ele não é implantado porque o modelo não é melhor do que aleatório.

Uma possível razão para o modelo não ser melhor do que aleatório poderia ser que as ofertas não são suficientemente diferentes umas das outras. Em caso positivo, você pode tentar tornar as ofertas mais visualmente diferentes se as mensagens forem semelhantes, ou pode tentar alterar as próprias mensagens.
