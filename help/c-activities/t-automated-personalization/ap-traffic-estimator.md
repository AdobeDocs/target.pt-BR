---
description: O Avaliador de tráfego fornece feedback que permite saber se há tráfego suficiente para a atividade ser bem-sucedida.
title: Estimativa de tráfego exigido para o sucesso
feature: null
topic: Standard
uuid: 9961ebaa-8761-431d-9605-852025ca580f
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 100%

---


# ![PREMIUM](/help/assets/premium.png) Estimativa do tráfego necessário para o sucesso{#estimate-the-traffic-required-for-success}

O Avaliador de tráfego fornece feedback que permite saber se há tráfego suficiente para a atividade ser bem-sucedida.

Como uma atividade de Personalização automatizada usa várias combinações de ofertas, é importante saber a quantidade de tráfego que é necessária para oferecer resultados significativos. O Avaliador de tráfego usa estatísticas sobre a página e a quantidade de experiências que estão sendo testadas para estimar a quantidade de tráfego e a duração do teste necessárias para que a atividade seja bem-sucedida.

O Avaliador de tráfego determina se existe tráfego suficiente para gerar modelos personalizados, através da comparação das impressões de página estimadas e do índice de conversão típico para as páginas. Idealmente, para uma atividade bem-sucedida, o tamanho de amostra correto garante que o conteúdo personalizado esteja pronto em 50% da duração da atividade ou 14 dias, o que for menor. Isso proporciona tempo suficiente para obter um conteúdo personalizado e aprender sobre qual conteúdo disponibilizar.

Lembre-se de que o Target oferece experiências aleatoriamente até que os algoritmos de personalização sejam criados. O ícone de marca de verificação ao lado de cada oferta mostra quando o modelo dessa oferta está pronto e o Target pode começar a entregar conteúdo personalizado. Como aumento é esperado somente depois que os modelos estão prontos, a indicação visual permite definir a expectativa correta. Use o avaliador de tráfego no Visual Experience Composer (VEC) para obter uma orientação sobre quando os modelos estarão prontos.

1. No Criador de experiências, clique em **[!UICONTROL Tráfego]**.

   ![Ícone de tráfego](/help/c-activities/t-automated-personalization/assets/icon-traffic.png)

   O Avaliador de tráfego é aberto. Você pode clicar em **[!UICONTROL Tráfego]** novamente para ocultar o Avaliador de tráfego.

   ![](assets/ap_est.png)

1. Forneça o índice de conversão típico (ou o índice de conversão que você espera dessa atividade), as impressões de atividade estimadas por dia e a duração do teste.

   * Número de combinações de conteúdo: calculado automaticamente com base no número de experiências que estão sendo criadas como parte da atividade após as exclusões.
   * Taxa de conversão típica: a taxa de conversão é expressa como uma porcentagem, com base na estimativa ou dados passados do sistema de análise.
   * Visitas estimadas por dia: esse é o número de visitas por dia dos visitantes que podem visualizar a atividade com base nos critérios de direcionamento. Isso pode se basear nos dados da análise. Observe que esse número deve ser de visitas e não de visitantes únicos.
   * Duração do teste: a quantidade de dias de duração da execução da atividade.

   O Avaliador de tráfego usa essas estatísticas para determinar quais ajustes são necessários para executar um teste bem-sucedido.

   Próximo da parte superior do Avaliador de tráfego, os valores inseridos são calculados, e os resultados são exibidos.

   ![](assets/ap_est_no.png)

   A estimativa muda, à medida que você muda os números. Por exemplo, se você estiver testando um grande número de combinações e o índice de conversão e as impressões forem muito baixos, o Avaliador de tráfego exibirá quanto tempo o teste precisará para ser executado com sucesso. Ou, se o tráfego for baixo, o Avaliador de tráfego pode sugerir um número menor de combinações de ofertas para que você possa executar o teste no número desejado de dias.

   Caso não tenha tráfego suficiente, é possível fazer uma ou todas as opções a seguir:

   * Considere o uso do Direcionamento automático em vez da Personalização automatizada para criar experiências com várias alterações de oferta em uma variação de experiência.
   * Reduza o número de combinações de ofertas na sua atividade de Personalização automatizada.
   * Aumente a duração da atividade.

   Ajuste os números até que o Avaliador de tráfego indique que você tem tráfego suficiente, então, crie seu teste de acordo.

   ![](assets/ap_est_yes.png)

   Se o tráfego for suficiente, o ícone de Tráfego mostrará uma marca de seleção verde. Se não for suficiente, o ícone mostrará um rótulo de aviso vermelho.
