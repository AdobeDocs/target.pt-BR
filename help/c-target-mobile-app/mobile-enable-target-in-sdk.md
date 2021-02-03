---
keywords: aplicativo móvel, sdk de aplicativo móvel, aplicativo móvel target, sdk target móvel, sdk de aplicativo móvel, habilitar target no sdk
description: Adicione o SDK do Adobe Mobile Services ao seu aplicativo.
title: Habilitar o Target no SDK
feature: Implement Mobile
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 90%

---


# Ativar o Target no SDK{#enable-target-in-the-sdk}

Adicione o SDK do Adobe Mobile Services ao seu aplicativo.

1. Se ainda não tiver instalado o SDK do Adobe Mobile Services no aplicativo, use suas credenciais do Analytics ou da Experience Cloud e baixe o SDK do site do [Adobe Mobile Services](https://mobilemarketing.adobe.com).

1. Adicione o SDK do Adobe Mobile Services ao seu aplicativo.

   Você encontrará instruções em [Implementação principal e ciclo de vida](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/dev-qs.html).

1. Adicione o código do cliente, tempo limite e habilite o SSL.

   Na Experience Cloud, abra o Mobile Services, depois vá para **[!UICONTROL Administrar configurações do aplicativo]** > **[!UICONTROL Opções do SDK do Target]**.

   Adicione seu código do cliente Target e tempo limite. O código do cliente é único para sua conta e empresa. O tempo limite é o tempo em segundos que o Target irá aguardar por uma resposta antes de exibir o conteúdo padrão. Certifique-se de que a opção **[!UICONTROL Usar HTTPS]** está marcada na página Administrar configurações do aplicativo no Adobe Mobile Services. Se HTTPS não estiver ativado, todas as chamadas no iOS9+ serão bloqueadas, a menos que você lista de permissões no servidor do Público alvo.

   ![](assets/mobile-clientcode.png)

1. Após criar/localizar seu aplicativo, acesse as configurações do aplicativo e baixe o SDK desejado.

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> Se você não tiver acesso à interface de marketing para dispositivos móveis, poderá fazer alterações diretamente no arquivo de configuração no código do aplicativo; no entanto, não estará sincronizado com a página de configurações na interface do usuário.

