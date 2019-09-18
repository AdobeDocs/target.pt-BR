---
description: O recurso de busca prévia do Adobe Target usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.
keywords: oferta, busca prévia, iOS, android;sdk;mobile;mobile sdk
seo-description: O recurso de busca prévia do Adobe Target usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.
seo-title: Buscar previamente conteúdo da oferta
solution: Target
title: Buscar previamente conteúdo da oferta
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: ce8a890d0d662c0eec4d7fe254da371694811822

---


# Buscar previamente conteúdo da oferta{#prefetch-offer-content}

O recurso de busca prévia do [!DNL Target] usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.

Esse processo reduz o tempo de carregamento, previne várias chamadas de rede e permite que o [!DNL Target] seja notificado sobre que mbox foi visitada pelo usuário do aplicativo móvel. Todo o conteúdo é recuperado e armazenado em cache durante a chamada de busca prévia, e esse conteúdo é recuperado do cache para todas as chamadas futuras que contêm conteúdo em cache para o nome da mbox especificada.

Considere o seguinte ao usar o método de busca prévia com os SDKs do iOS e Android Mobile:

* O conteúdo da busca prévia não persiste entre inicializações. O conteúdo da busca prévia é armazenado em cache enquanto o aplicativo está em uso ou até o método `clearPrefetchCache()` ser chamado.
* A funcionalidade de busca prévia nos SDKs móveis do iOs e Android não é compatível com os tipos de atividades de Destino automático, Autoalocação e Personalização automatizada.

Para obter mais informações, incluindo métodos de busca prévia, classes públicas e exemplos de código, consulte:

* **** iOS:  Procure [previamente o conteúdo da oferta no iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/target-ios/c-mob-target-prefetch-ios.html) na Ajuda *do SDK do iOS do* Mobile Services.
* **** Android:  Procure [previamente o conteúdo da oferta no Android](https://docs.adobe.com/content/help/en/mobile-services/android/target-android/c-mob-target-prefetch-android.html) na Ajuda *do SDK do Android do* Mobile Services.
