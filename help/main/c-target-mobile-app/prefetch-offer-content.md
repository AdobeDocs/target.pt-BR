---
keywords: oferta; pré-busca; iOS; android; sdk; móvel; sdk móvel
description: Use o Adobe [!DNL Target] recurso de busca prévia no SDK móvel do iOS e do Android para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.
title: Posso realizar uma busca prévia por conteúdo de oferta para aplicativos móveis?
feature: Implement Mobile
role: Developer
exl-id: 83a96a41-cf27-4ed8-8169-277f3ef3f249
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 47%

---

# Buscar previamente conteúdo da oferta

O recurso de busca prévia do [!DNL Target] usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.

Esse processo reduz o tempo de carregamento, previne várias chamadas de rede e permite que o [!DNL Target] seja notificado sobre que mbox foi visitada pelo usuário do aplicativo móvel. Todo o conteúdo é recuperado e armazenado em cache durante a chamada da busca prévia e esse conteúdo é recuperado do cache para todas as chamadas futuras que contenham conteúdo armazenado em cache para o nome da mbox especificado.

Considere as seguintes limitações ao usar o método de busca prévia com os SDKs móveis da iOS e do Android:

* O conteúdo da busca prévia não persiste entre inicializações. O conteúdo da busca prévia é armazenado em cache enquanto o aplicativo está em uso ou até o método `clearPrefetchCache()` ser chamado.
* A funcionalidade de busca prévia não é compatível com o [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático] métodos de alocação de tráfego, para [!UICONTROL Automated Personalization] ou [!UICONTROL Recommendations] tipos de atividade ou para [ofertas do recommendations em uma atividade A/B ou XT](/help/main/c-recommendations/recommendations-as-an-offer.md).

Para obter mais informações, incluindo métodos de busca prévia, classes públicas e exemplos de código, consulte:

* **iOS:**  [Realizar uma busca prévia por conteúdos em oferta no iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) no *Ajuda do SDK do iOS do Mobile Services*.
* **Android:**  [Realizar uma busca prévia por conteúdos em oferta no Android](https://experienceleague.adobe.com/docs/mobile-services/android/target-android/c-mob-target-prefetch-android.html) no *Ajuda do SDK do Android do Mobile Services*.
