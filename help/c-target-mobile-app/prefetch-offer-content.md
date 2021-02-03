---
keywords: oferta;pré-busca;iOS;android;sdk;mobile;mobile sdk
description: O recurso de busca prévia do Adobe Target usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.
title: Buscar previamente conteúdo da oferta
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 60%

---


# Buscar previamente conteúdo da oferta{#prefetch-offer-content}

O recurso de busca prévia do [!DNL Target] usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.

Esse processo reduz o tempo de carregamento, previne várias chamadas de rede e permite que o [!DNL Target] seja notificado sobre que mbox foi visitada pelo usuário do aplicativo móvel. Todo o conteúdo é recuperado e armazenado em cache durante a chamada da busca prévia e esse conteúdo é recuperado do cache para todas as chamadas futuras que contenham conteúdo armazenado em cache para o nome da mbox especificado.

Considere as seguintes limitações ao usar o método de busca prévia com os SDKs do iOS e Android Mobile:

* O conteúdo da busca prévia não persiste entre inicializações. O conteúdo da busca prévia é armazenado em cache enquanto o aplicativo está em uso ou até o método `clearPrefetchCache()` ser chamado.
* A funcionalidade de busca prévia não é compatível com os métodos de alocação de tráfego [!UICONTROL Autoalocação] e [!UICONTROL Público alvo automático], para os tipos de atividade [!UICONTROL Automated Personalization] ou [!UICONTROL Recommendations], ou para as ofertas de [recomendações dentro de uma atividade A/B ou XT](/help/c-recommendations/recommendations-as-an-offer.md).

Para obter mais informações, incluindo métodos de busca prévia, classes públicas e exemplos de código, consulte:

* **iOS:**  [faça uma busca prévia do conteúdo da oferta no ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) iOS na Ajuda *do SDK do iOS do* Mobile Services.
* **Android:**  [Procure previamente o conteúdo da oferta no ](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) Android na Ajuda *do SDK do Android do* Mobile Services.
