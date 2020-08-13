---
keywords: offer;prefetch;iOS;android;sdk;mobile;mobile sdk
description: O recurso de busca prévia do Adobe Target usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.
title: Buscar previamente conteúdo da oferta
feature: mobile implementation
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 62%

---


# Buscar previamente conteúdo da oferta{#prefetch-offer-content}

O recurso de busca prévia do [!DNL Target] usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.

Esse processo reduz o tempo de carregamento, previne várias chamadas de rede e permite que o [!DNL Target] seja notificado sobre que mbox foi visitada pelo usuário do aplicativo móvel. Todo o conteúdo é recuperado e armazenado em cache durante a chamada da busca prévia e esse conteúdo é recuperado do cache para todas as chamadas futuras que contenham conteúdo armazenado em cache para o nome da mbox especificado.

Considere as seguintes limitações ao usar o método de busca prévia com os SDKs do iOS e Android Mobile:

* O conteúdo da busca prévia não persiste entre inicializações. O conteúdo da busca prévia é armazenado em cache enquanto o aplicativo está em uso ou até o método `clearPrefetchCache()` ser chamado.
* A funcionalidade de busca prévia não é compatível com os métodos de alocação de tráfego [!UICONTROL Autoalocação] e Público alvo  Automático, para tipos de atividade [!UICONTROL Automated Personalization] ou [!UICONTROL Recommendations] ou para ofertas de [recomendações em uma atividade](/help/c-recommendations/recommendations-as-an-offer.md)A/B ou XT.

Para obter mais informações, incluindo métodos de busca prévia, classes públicas e exemplos de código, consulte:

* **iOS:**  [Procure previamente o conteúdo da oferta no iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) na Ajuda *do SDK do iOS do* Mobile Services.
* **Android:**  [Procure previamente o conteúdo da oferta no Android](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) na Ajuda *do SDK do Android do* Mobile Services.
