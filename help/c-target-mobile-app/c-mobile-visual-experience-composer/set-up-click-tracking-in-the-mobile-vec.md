---
description: O Mobile Visual Experience Composer (VEC) oferece suporte à configuração de metas de rastreamento de cliques para atividades do Target.
keywords: VEC do aplicativo móvel; compositor de experiência visual móvel; opções do compositor de experiência móvel; opções de experiência móvel; exibição de destino; cliques; rastreamento de cliques; track
seo-description: O Mobile Visual Experience Composer (VEC) oferece suporte à configuração de metas de rastreamento de cliques para atividades do Adobe Target.
seo-title: Configurar o rastreamento de cliques no VEC do aplicativo móvel
solution: Target
title: Configurar o rastreamento de cliques no VEC do aplicativo móvel
topic: Padrão
uuid: 7e4ce7c0-0027-417c-8dae-45b6f5045e65
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Configurar o rastreamento de cliques no VEC do aplicativo móvel{#set-up-click-tracking-in-the-mobile-vec}

O VEC do aplicativo móvel oferece suporte à configuração de metas de rastreamento de cliques para [!DNL Target] atividades.

1. Ao definir suas metas na página Metas e configurações para a atividade, selecione a métrica de sucesso de [!UICONTROL Conversão].

   ![](assets/mobile-vec-clicktrack1.png)

1. Para ação, selecione **[!UICONTROL Clicou em um elemento]** e clique em **[!UICONTROL Selecionar elementos]**.

   Seu aplicativo móvel é aberto no Visual Experience Composer (VEC).

   ![](assets/mobile-vec-clicktrack2.png)

1. Selecione os elementos que deseja rastrear.

   Consulte a seção [!UICONTROL Considerações] abaixo para obter dicas sobre como selecionar elementos.

   ![](assets/mobile-vec-clicktrack3.png)

1. Clique na marca de seleção na parte superior da tela para salvar suas seleções.

Você também pode editar e alterar as seleções de cliques ou excluí-las se precisar começar do zero.

![](assets/mobile-vec-clicktrack4.png)

Quando um participante da atividade clica em um elemento selecionado, esse clique é contado como uma conversão.

## Considerações {#considerations}

Há várias coisas a considerar ao selecionar elementos:

* Quando mais de um elemento é selecionado e um visitante clica em um desses elementos, o clique é contado. Para contar cada clique separadamente, configure métricas de sucesso individuais para cada elemento.
* Os eventos de clique são enviados para o Target assim que o usuário clica no elemento.
* No VEC do aplicativo móvel, somente os elementos com um manipulador de cliques anexado podem ser selecionados.
* Você pode navegar para qualquer seção do aplicativo, mas certifique-se de que as [exibições](/help/c-target-mobile-app/c-mobile-visual-experience-composer/mobile-visual-experience-composer.md#target-views) estejam definidas para a seção em que você está selecionando elementos para o rastreamento de cliques.
* Ao editar uma atividade, se o dispositivo já estiver selecionado na Etapa 1, não será necessário selecionar o dispositivo novamente. No entanto, se você direcionar diretamente na página de rastreamento de cliques, será exibida a tela de seleção do dispositivo para selecionar um dispositivo autorizado.
