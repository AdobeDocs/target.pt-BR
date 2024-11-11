---
keywords: ajo;adobe jornada otimizer;adobe jornada otimizer destino integração;recomendações;direcionar recomendações;integração;ajo;adobe otimizer;adobe otimizer target integration;recommendations;target recommendations
description: Integrar [!DNL Adobe Target Recommendations] com [!DNL Adobe Journey Optimizer].
title: Como usar o  [!DNL Target Recommendations] em jornadas de clientes usando o  [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#beta newtab=true" tooltip="O que são recursos beta no  [!DNL Adobe Target]."
hide: true
hidefromtoc: true
exl-id: 81bbbd51-47fc-4e23-a1cb-7c18fea1c159
source-git-commit: b4f9e14f9dfa94f8648686e43e66eee7e0f7daa1
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 1%

---

# Integrar [!DNL Adobe Target Recommendations] e [!DNL Adobe Journey Optimizer]

Este artigo fornece casos de uso e orientação para integrar o [!DNL Adobe Target Recommendations] ao [!DNL Adobe Journey Optimizer], permitindo que você forneça experiências conectadas, contextuais e personalizadas ao cliente.

Essa integração ajuda você a gerar mais conversões e ver o impacto de mensagens de email que contêm recomendações personalizadas.

## Pré-requisitos

Para usar a integração do [!DNL Target Recommendations] e do [!DNL Adobe Journey Optimizer], você precisa do seguinte:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementado usando o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/en/docs/target-dev/developer/client-side/aep-web-sdk){target=_blank}.

  Este recurso não está disponível com uma licença [!DNL Target Standard] ou ao implementar o [!DNL Target] com a at.js ou outros SDKs [!DNL Target].

* [[!DNL Adobe Journey Optimizer]1{target=_blank}.](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home)

## Casos de uso de exemplo

Estes casos de uso são apenas alguns possíveis para integrar o [!DNL Target Recommendations] ao [!DNL Adobe Journey Optimizer]:

* **[!DNL Adobe Journey Optimizer]envia um email personalizado após o abandono do carrinho**: este caso de uso se baseia em um cliente que visita um site, coloca itens no carrinho de compras e sai do site sem concluir o processo de compra.

  Suponha, por exemplo, que um visitante visite o site de uma empresa de roupas e coloque dois casacos de inverno e uma camiseta no carrinho de compras. O visitante então se distrai e sai do site ou não tem certeza das compras e fecha o navegador ou aplicativo.

  Após um período especificado, talvez algumas horas ou um dia, uma ação personalizada no [!DNL Journey Optimizer] faz uma chamada para [!DNL Target Recommendations] para determinar o conteúdo do carrinho de compras abandonado usando um algoritmo de [recomendações baseadas em carrinho](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). [!DNL Journey Optimizer] então envia a esse visitante um email personalizado como lembrete de que o processo de compra não foi concluído, juntamente com imagens e links para os itens abandonados.

* **[!DNL Adobe Journey Optimizer]envia um email em massa após visitas ao site para lembrar aos visitantes quais itens foram exibidos**: esse caso de uso se baseia em visitantes que visitam um site, visualizam vários itens e depois saem do site ou aplicativo sem colocar itens no carrinho de compras.

  Após um período especificado, uma ação personalizada no [!DNL Journey Optimizer] faz uma chamada para [!DNL Target Recommendations] determinar quais itens cada visitante visualizou, usando a [!DNL Adobe Experience Cloud Identifier] (EDID) de cada visitante, o perfil [!DNL Target] do visitante e um algoritmo [baseado no usuário](/help/main/c-recommendations/c-algorithms/base-the-recommendation-on-a-recommendation-key.md). [!DNL Adobe Journey Optimizer] em seguida, envia a cada membro do público qualificado um email personalizado com imagens e links para os itens visualizados de cada visitante para que o visitante retorne e faça uma compra.

  Neste cenário, o [!UICONTROL Experience Cloud Visitor ID] (ECID) e o conteúdo do perfil [!DNL Target] de cada visitante são usados para gerar a recomendação com base no algoritmo visualizado recentemente.

  Suponha, por exemplo, que um visitante visite um site de varejo e visualize vários relógios. O perfil [!DNL Target] deste visitante foi atualizado com uma lista de inspeções visualizadas. Usando a ECID e o perfil [!DNL Target] do visitante, [!DNL Target] envia a recomendação para [!DNL Journey Optimizer]. [!DNL Journey Optimizer] em seguida, envia um email contendo imagens e links para os relógios que este visitante visualizou, usando o algoritmo visualizado recentemente. Outro visitante recebe um email personalizado contendo imagens e links para os itens que esse visitante visualizou. Cada mensagem de email é personalizada para cada visitante.

* **[!DNL Adobe Journey Optimizer]envia um email em massa para visitantes qualificados após uma visita ao site para sugerir itens populares**: este caso de uso se baseia em um visitante que visita um site, mas não exibe nenhum item específico. O email é enviado em massa para todos os visitantes que se qualificam para um público-alvo específico, por exemplo:

  Suponha que o visitante não visualize nenhum relógio específico. Talvez o visitante simplesmente tenha clicado no site e visualizado páginas de categoria ou entradas do blog. Como resultado, o perfil [!DNL Target] não tem informações específicas sobre itens visualizados recentemente. Nesta situação, [!DNL Target Recommendations] usa uma [recomendação de backup](/help/main/c-recommendations/c-algorithms/backup-recs.md) para que [!DNL Journey Optimizer] possa enviar um email com imagens e links para itens populares no site para fazer com que o visitante retorne e possivelmente faça uma compra.
