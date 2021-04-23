---
keywords: oferta; pré-busca; iOS; android; sdk; móvel; sdk móvel
description: Use o recurso de busca prévia do Adobe [!DNL Target] nos SDKs móveis para iOS e Android para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.
title: Posso realizar uma busca prévia por conteúdo de oferta para aplicativos móveis?
feature: Implementar dispositivos móveis
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 47%

---

# Buscar previamente conteúdo da oferta

O recurso de busca prévia do [!DNL Target] usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.

Esse processo reduz o tempo de carregamento, previne várias chamadas de rede e permite que o [!DNL Target] seja notificado sobre que mbox foi visitada pelo usuário do aplicativo móvel. Todo o conteúdo é recuperado e armazenado em cache durante a chamada da busca prévia e esse conteúdo é recuperado do cache para todas as chamadas futuras que contenham conteúdo armazenado em cache para o nome da mbox especificado.

Considere as seguintes limitações ao usar o método de busca prévia com os SDKs móveis para iOS e Android:

* O conteúdo da busca prévia não persiste entre inicializações. O conteúdo da busca prévia é armazenado em cache enquanto o aplicativo está em uso ou até o método `clearPrefetchCache()` ser chamado.
* A funcionalidade de busca prévia não é compatível com os métodos de alocação de tráfego [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático], para os tipos de atividade [!UICONTROL Automated Personalization] ou [!UICONTROL Recommendations] ou para [ofertas de recomendações em uma atividade A/B ou XT](/help/c-recommendations/recommendations-as-an-offer.md).

Para obter mais informações, incluindo métodos de busca prévia, classes públicas e exemplos de código, consulte:

* **iOS:**  [Buscar previamente conteúdo de oferta no ](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) iOS na Ajuda do SDK do iOS do  *Mobile Services*.
* **Android:**  [busque previamente conteúdo de oferta no ](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) Android na Ajuda do SDK do Android do  *Mobile Services*.
