---
description: O recurso de busca prévia do Adobe Target usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.
keywords: oferta, busca prévia, iOS, android; sdk; dispositivos móveis; sdk móvel
seo-description: O recurso de busca prévia do Adobe Target usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.
seo-title: Buscar previamente conteúdo da oferta
solution: Target
title: Buscar previamente conteúdo da oferta
topic: Advanced,Standard,Classic
uuid: 715e0e77-bfd9-437b-b42c-899d66f2890c
translation-type: tm+mt
source-git-commit: 95bf4b2070cc2de235ac09ac164f0f9ec48dd6cd

---


# Buscar previamente conteúdo da oferta{#prefetch-offer-content}

O recurso de busca prévia do [!DNL Target] usa o SDK móvel do Android e do iOS para buscar conteúdo de oferta a menor quantidade de vezes possível, armazenando as respostas do servidor em cache.

Esse processo reduz o tempo de carregamento, previne várias chamadas de rede e permite que o [!DNL Target] seja notificado sobre que mbox foi visitada pelo usuário do aplicativo móvel. Todo o conteúdo é recuperado e armazenado em cache durante a chamada de busca prévia, e este conteúdo é recuperado do cache para todas as chamadas futuras que contenham conteúdo em cache para o nome da mbox especificada.

Considere o seguinte quando usa o método prefetch com os sdks móveis iOS e Android:

* O conteúdo da busca prévia não persiste entre inicializações. O conteúdo da busca prévia é armazenado em cache enquanto o aplicativo está em uso ou até o método `clearPrefetchCache()` ser chamado.
* A funcionalidade de busca prévia nos sdks móveis do iOs e Android não é compatível com tipos de atividade Auto-alvo, Alocação automática e Personalização automatizada.

Para obter mais informações, incluindo métodos de busca prévia, classes públicas e exemplos de código, consulte:

* **iOS:**[Conteúdo de oferta de busca prévia no iOS](https://marketing.adobe.com/resources/help/en_US/mobile/ios/c_mob_target-prefetch_ios.html) no guia *iOS SDK 4.x for Experience Cloud Solutions*.
* **Android:**[Conteúdo de oferta de busca prévia no Android](https://marketing.adobe.com/resources/help/en_US/mobile/android/c_mob_target-prefetch_android.html) no guia *Android SDK 4.x for Experience Cloud Solutions*.
