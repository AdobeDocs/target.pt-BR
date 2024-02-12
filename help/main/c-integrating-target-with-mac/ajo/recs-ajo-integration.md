---
keywords: ajo;adobe jornada otimizer;adobe jornada otimizer destino integração;recomendações;direcionar recomendações;integração;ajo;adobe otimizer;adobe otimizer target integration;recommendations;target recommendations
description: Integrar [!DNL Adobe Target Recommendations] com [!DNL Adobe Journey Optimizer].
title: Como usar [!DNL Target Recommendations] nas jornadas do cliente usando [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#beta newtab=true" tooltip="O que são recursos beta no  [!DNL Adobe Target]."
hide: true
hidefromtoc: true
source-git-commit: ce74c85380333476b97f47fab4d2659a3c9c86e1
workflow-type: tm+mt
source-wordcount: '605'
ht-degree: 1%

---

# Integrar [!DNL Adobe Target Recommendations] e [!DNL Adobe Journey Optimizer]

Este artigo explica casos de uso e informações para ajudar você a configurar a integração entre o [!DNL Adobe Target Recommendations] e [!DNL Adobe Journey Optimizer] para ajudar você a fornecer experiências conectadas, contextuais e personalizadas aos seus clientes.

Essa integração ajuda você a gerar mais conversões e ver o impacto de mensagens de email que contêm recomendações personalizadas.

## Pré-requisitos

Para usar o [!DNL Target Recommendations] e [!DNL Adobe Journey Optimizer] integração, você precisará do seguinte:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementado usando o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}.

  Este recurso não está disponível com uma [!DNL Target Standard] licença ou ao implementar [!DNL Target] com at.js ou outro [!DNL Target] SDKs.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## Casos de uso de exemplo

Estes são apenas alguns casos de uso possíveis para integrar o [!DNL Target Recommendations] com [!DNL Adobe Journey Optimizer]:

* **[!DNL Adobe Journey Optimizer]envia um email personalizado após o abandono do carrinho**: esse caso de uso se baseia no fato de um cliente visitar um site, colocar itens no carrinho de compras e sair do site sem concluir o processo de compra.

  Suponha, por exemplo, que um visitante visite o site de uma empresa de roupas e coloque dois casacos de inverno e uma camiseta no carrinho de compras. O visitante então se distrai e sai do site ou não tem certeza das compras e fecha o navegador ou aplicativo.

  Após um período especificado, talvez algumas horas ou um dia, uma ação personalizada no [!DNL Adobe Journey Optimizer] faz uma chamada para [!DNL Target Recommendations] para determinar o conteúdo do carrinho de compras abandonado usando um [recomendações baseadas em carrinho](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algoritmo. [!DNL Adobe Journey Optimizer] em seguida, envia a esse visitante um email personalizado como um lembrete de que o processo de compra não foi concluído, juntamente com imagens e links para os itens abandonados.

* **[!DNL Adobe Journey Optimizer]envia um email em massa após visitas ao site para lembrar aos visitantes quais itens foram visualizados**: esse caso de uso se baseia nos visitantes que visitam um site, visualizam vários itens e depois saem do site ou aplicativo sem colocar itens no carrinho de compras.

  Após um período especificado, uma ação personalizada no [!DNL Adobe Journey Optimizer] faz uma chamada para [!DNL Target Recommendations] para determinar quais itens cada visitante visualizou, usando a [!DNL Adobe Experience Cloud Identifier] (EDID), a conta do visitante [!DNL Target] e um [baseado no usuário](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md) algoritmo. [!DNL Adobe Journey Optimizer] em seguida, o envia a cada membro do público qualificado um email personalizado com imagens e links para os itens visualizados de cada visitante, para que o visitante retorne e faça uma compra.

  Neste cenário, a variável [!UICONTROL ID de visitante Experience Cloud] (ECID) e o conteúdo do relatório de cada visitante [!DNL Target] O perfil é usado para gerar a recomendação com base no algoritmo visualizado recentemente.

  Suponha, por exemplo, que um visitante visite um site de varejo e visualize vários relógios. Do visitante [!DNL Target] o perfil é atualizado com uma lista dos relógios visualizados. Usar a ECID e a permissão do visitante [!DNL Target] perfil, [!DNL Target] envia a recomendação para [!DNL Adobe Journey Optimizer]. [!DNL Adobe Journey Optimizer] em seguida, envia um email contendo imagens e links para os relógios que esse visitante visualizou, usando o algoritmo visualizado recentemente. Outro visitante recebe um email personalizado contendo imagens e links para os itens que esse visitante visualizou. Cada mensagem de email é personalizada para cada visitante.

* **[!DNL Adobe Journey Optimizer]envia um email em massa para visitantes qualificados após uma visita ao site para sugerir itens populares**: este caso de uso se baseia em um visitante que visita um site, mas não visualiza itens específicos. O email é enviado em massa para todos aqueles que se qualificam para um público-alvo específico, por exemplo:

  Suponha que o visitante não visualize nenhum relógio específico. Talvez o visitante simplesmente tenha clicado no site e visualizado páginas de categoria ou entradas do blog. Como resultado, a [!DNL Target] o perfil não tem informações específicas sobre os itens visualizados recentemente. Nesta situação, [!DNL Target Recommendations] usa um [recomendação de backup](/help/main/c-recommendations/c-algorithms/backup-recs.md) para que [!DNL Adobe Journey Optimizer] O pode enviar um email com imagens e links para itens populares no site para fazer com que o visitante retorne e possivelmente faça uma compra.


