---
keywords: ajo;adobe jornada otimizer;adobe jornada otimizer destino integração;recomendações;direcionar recomendações;integração;ajo;adobe otimizer;adobe otimizer target integration;recommendations;target recommendations
description: Integrar [!DNL Adobe Target Recommendations] com [!DNL Adobe Journey Optimizer].
title: Como usar [!DNL Target Recommendations] nas jornadas do cliente usando [!DNL Adobe Journey Optimizer]?
feature: Integrations
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
badgeBeta: label="Beta" type="Informative" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#beta newtab=true" tooltip="O que são recursos beta no  [!DNL Adobe Target]."
hide: true
hidefromtoc: true
source-git-commit: 1faedc44c4f8f95000b666af8eecaf1eca5bf48d
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 3%

---

# Integrar [!DNL Adobe Target Recommendations] e [!DNL Adobe Journey Optimizer]

Este artigo explica casos de uso e informações para ajudar você a configurar a integração entre o [!DNL Adobe Target Recommendation] e [!DNL Adobe Journey Optimizer] para ajudar você a fornecer experiências conectadas, contextuais e personalizadas aos seus clientes.

## Pré-requisitos

Para usar o [!DNL Target Recommendations] e [!DNL Adobe Journey Optimizer] integração, você precisará do seguinte:

* [[!DNL Adobe Target Premium]](/help/main/c-intro/intro.md#premium) implementado usando o [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}.

  O recurso não está disponível com uma [!DNL Target Standard] licença ou ao implementar [!DNL Target] com at.js ou outro [!DNL Target] SDKs.

* [[!DNL Adobe Journey Optimizer]](https://experienceleague.adobe.com/docs/journey-optimizer/using/ajo-home.html){target=_blank}.

## Casos de uso de exemplo

Veja a seguir apenas dois casos de uso possíveis para integração do [!DNL Target Recommendations] com [!DNL Adobe Journey Optimizer]:

* **[!DNL Customer Journey Optimizer]envia um email personalizado após o abandono do carrinho**: esse caso de uso se baseia no fato de um cliente visitar um site, colocar itens no carrinho de compras e sair do site sem concluir o processo de compra.

  Suponha, por exemplo, que um visitante visite o site de uma empresa de roupas e coloque dois casacos de inverno e uma camiseta no carrinho de compras. O visitante então se distrai e sai do site ou não tem certeza das compras e fecha o navegador ou aplicativo.

  Após um período especificado, talvez algumas horas ou um dia, uma ação personalizada no [!DNL Adobe Journey Optimizer] faz uma chamada para [!DNL Target Recommendations] para determinar o conteúdo do carrinho de compras abandonado. [!DNL Adobe Journey Optimizer] em seguida, envia a esse visitante um email personalizado como um lembrete de que o processo de compra não foi concluído, juntamente com imagens e links para os itens abandonados.

* **[!DNL Customer Journey Optimizer]envia um email após a visita ao site usando o perfil do usuário**: esse caso de uso se baseia em um cliente que visita um site, visualiza vários itens e depois sai do site sem colocar itens no carrinho de compras.

  Após um período especificado, uma ação personalizada no [!DNL Adobe Journey Optimizer] faz uma chamada para [!DNL Target Recommendations] para determinar quais itens este visitante visualizou usando a [!DNL Adobe Experience Cloud Identifier] (EDID) [!DNL Adobe Journey Optimizer] em seguida, envia a esse visitante um email personalizado como um lembrete de que o processo de compra não foi concluído, juntamente com imagens e links para os itens abandonados.

