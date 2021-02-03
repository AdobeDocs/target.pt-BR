---
keywords: avaliador de tráfego;personalização automatizada;ap;estimar tráfego
description: O Estimador de tráfego fornece feedback que informa se você tem tráfego suficiente para que sua atividade Adobe Target tenha sucesso.
title: Estimativa de tráfego exigido para o sucesso
feature: Automated Personalization
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 26%

---


# ![PREMIUM](/help/assets/premium.png) Estimativa do tráfego necessário para o sucesso

O [!UICONTROL Estimador de Tráfego] fornece feedback que permite saber se você tem tráfego suficiente para que sua atividade [!DNL Adobe Target] tenha êxito.

Como uma atividade [!UICONTROL Automated Personalization] usa várias combinações de ofertas, é importante saber quanto tráfego é necessário para fornecer resultados significativos. O [!UICONTROL Estimador de Tráfego] usa estatísticas sobre sua página e o número de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessário para que a atividade seja bem-sucedida.

O [!UICONTROL Estimador de tráfego] determina se há tráfego suficiente para gerar modelos personalizados, comparando as impressões de página estimadas e a taxa de conversão típica das páginas. Idealmente, para uma atividade bem-sucedida, o tamanho de amostra correto garante que o conteúdo personalizado esteja pronto em 50% da duração da atividade ou 14 dias, o que for menor. Isso proporciona tempo suficiente para obter um conteúdo personalizado e aprender sobre qual conteúdo disponibilizar.

Lembre-se de que [!DNL Target] fornece experiências aleatoriamente até que os algoritmos de personalização sejam criados. O ícone de marca de seleção ao lado de cada oferta mostra quando o modelo dessa oferta está pronto e [!DNL Target] é capaz de começar a fornecer conteúdo personalizado. Como aumento é esperado somente depois que os modelos estão prontos, a indicação visual permite definir a expectativa correta. Use o [!UICONTROL Estimador de tráfego] no [!UICONTROL Visual Experience Composer] (VEC) para obter uma orientação sobre quando os modelos estarão prontos.

## Usar o Estimador de Tráfego

1. No [!UICONTROL Visual Experience Composer], clique em **[!UICONTROL Tráfego]**.

   ![Ícone de tráfego](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   O [!UICONTROL Estimador de Tráfego] é aberto. Você pode clicar em **[!UICONTROL Tráfego]**[!UICONTROL  novamente para ocultar o Avaliador de tráfego].

   ![](assets/ap_est.png)

1. Forneça o índice de conversão típico (ou o índice de conversão que você espera dessa atividade), as impressões de atividade estimadas por dia e a duração do teste.

   * **Número de Ofertas**: Calculado automaticamente com base no número de experiências que estão sendo criadas como parte da sua atividade após quaisquer exclusões.
   * **Taxa de conversão típica**: a taxa de conversão é expressa como uma porcentagem, com base na estimativa ou dados anteriores do sistema de análise.
   * **Visitas estimadas por dia**: Este é o número de visitas por dia de visitantes que podem visualização a atividade, com base nos critérios de definição de metas. Isso pode se basear nos dados da análise. Observe que esse número deve ser de visitas e não de visitantes únicos.
   * **Duração do teste**: a quantidade de dias de duração da execução da atividade.

   O [!UICONTROL Traffic Estimato]r utiliza essas estatísticas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   Próximo à parte superior do [!UICONTROL Estimador de tráfego], os valores inseridos são calculados e os resultados são mostrados.

   ![](assets/ap_est_no.png)

   A estimativa muda, à medida que você muda os números. Por exemplo, se você estiver testando um grande número de combinações e sua taxa de conversão e impressões forem muito baixas, o [!UICONTROL Estimador de tráfego] mostrará quanto tempo o teste precisará para ser executado com êxito. Ou, se seu tráfego for baixo, o [!UICONTROL Estimador de tráfego] poderá sugerir um número menor de combinações de oferta para que você possa executar o teste no número desejado de dias.

   Caso não tenha tráfego suficiente, é possível fazer uma ou todas as opções a seguir:

   * Considere usar uma atividade [Público alvo automático](/help/c-activities/auto-target/auto-target-to-optimize.md) em vez de [!UICONTROL Automated Personalization] para criar experiências com várias alterações de oferta em uma variação de experiência.
   * Reduza o número de combinações de ofertas na atividade [!UICONTROL Automated Personalization].
   * Aumente a duração da atividade.

   Ajuste os números até que o [!UICONTROL Estimador de tráfego] diga que você tem tráfego suficiente e, em seguida, projete seu teste de acordo.

   ![](assets/ap_est_yes.png)

   Se o tráfego for suficiente, o ícone [!UICONTROL Traffic] mostrará uma verificação verde. Se não for suficiente, o ícone mostrará um rótulo de aviso vermelho.

## Perguntas frequentes sobre o Estimador de tráfego

Considere as seguintes perguntas frequentes ao trabalhar com o [!UICONTROL Estimador de tráfego]:

### Por que [!DNL Target] não está criando modelos personalizados quando minha atividade AP tem tráfego suficiente?

Em determinadas circunstâncias, seu tráfego pode ser grande o suficiente para que um modelo personalizado seja criado, mas esse tráfego pode informar [!DNL Target] que não há diferença significativa entre o modelo personalizado e o aleatório. Embora o modelo seja construído em [!DNL Target] e testado, ele não será implantado porque o modelo não é significativamente melhor do que aleatório.

Uma possível razão para o modelo não ser melhor do que aleatório pode ser que as ofertas não sejam significativamente diferentes umas das outras. Se esse for o caso, você pode tentar tornar as ofertas mais visualmente diferentes se as mensagens forem semelhantes, ou pode tentar mudar as próprias mensagens.
