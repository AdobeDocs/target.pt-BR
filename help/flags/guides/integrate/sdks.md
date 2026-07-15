---
title: SDKs
description: Saiba mais sobre a arquitetura do SDK em Sinalizadores e as extensões disponíveis do AEP Web SDK e do AEP Mobile SDK.
hide: true
exl-id: 110a440d-b52a-4e1e-a94f-86f9741a223a
source-git-commit: 35fa45d2a5374dcc47a02bb737f28f24847d7fc6
workflow-type: tm+mt
source-wordcount: '200'
ht-degree: 3%

---

# SDKs {#sdks}

Os sinalizadores fornecem SDKs para integrar sinalizadores de recursos aos seus aplicativos. Os sinalizadores são implantados por meio do AEP Web SDK e do AEP Mobile SDK.

## Arquitetura do SDK {#architecture}

Todos os SDKs de Sinalizadores compartilham a mesma arquitetura principal:

* **Inicialização** — A SDK está configurada na inicialização e se registra no serviço de Sinalizadores.
* **Recuperação de recursos** — O SDK recupera dados de sinalizador de recursos e avalia sinalizadores localmente.
* **Armazenamento em cache** — O SDK armazena em cache dados de sinalizador de recurso e os atualiza em um intervalo de sondagem configurável.
* **Tratamento de erros** — Se o serviço não estiver disponível, a SDK continuará a fornecer avaliações de sinalizador de recursos do cache local.

## SDKs disponíveis {#available-sdks}

### AEP Web SDK {#web-sdk}

A extensão Sinalizadores para a Web se integra ao Adobe Experience Platform Web SDK.

>[!NOTE]
>
>O suporte ao Web SDK será disponibilizado em breve. Entre em contato com o representante da Adobe para obter orientação de acesso antecipado.

### Extensão do Android {#android-extension}

A extensão Sinalizadores para o Android integra-se ao Adobe Experience Platform Mobile SDK.

Consulte o [guia de integração de extensão do Android](../sdk-releases/android/android-extension-integration-guide.md) para obter instruções de configuração.

### Extensão do iOS {#ios-extension}

A extensão Sinalizadores para o iOS integra-se ao Adobe Experience Platform Mobile SDK.

Consulte o [guia de integração de extensão do iOS](../sdk-releases/ios/ios-extension-integration-guide.md) para obter instruções de configuração.

## Consulte também {#see-also}

* [guia de integração de extensão do Android](../sdk-releases/android/android-extension-integration-guide.md)
* [Serviços web](web-services.md)
* [Etapas de integração](integration-steps.md)

<!-- -->
