---
keywords: aplicativo móvel, sdk de aplicativo móvel, aplicativo móvel target, sdk target móvel, sdk de aplicativo móvel, habilitar target no sdk
description: Saiba como adicionar o SDK do Adobe Mobile Services ao seu aplicativo móvel.
title: Como faço para ativar o [!DNL Target] no SDK do Adobe Mobile?
feature: Implementar dispositivos móveis
role: Developer
exl-id: c34bd50c-e17f-4dfb-8470-8f4c8639ee9f
source-git-commit: c9c335c241727c4eff1d27f52853e32b8d18b6a5
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 79%

---

# Ativar [!DNL Target] no SDK

Adicione o SDK do Adobe Mobile Services ao seu aplicativo.

1. Se ainda não tiver instalado o SDK do Adobe Mobile Services no aplicativo, use suas credenciais do Analytics ou da Experience Cloud e baixe o SDK do site do [Adobe Mobile Services](https://mobilemarketing.adobe.com/).

1. Adicione o SDK do Adobe Mobile Services ao seu aplicativo.

   Você encontrará instruções em [Implementação principal e ciclo de vida](https://experienceleague.adobe.com/docs/mobile-services/ios/getting-started-ios/dev-qs.html).

1. Adicione o código do cliente, tempo limite e habilite o SSL.

   Na Experience Cloud, abra o Mobile Services, depois vá para **[!UICONTROL Administrar configurações do aplicativo]** > **[!UICONTROL Opções do SDK do Target]**.

   Adicione seu código do cliente Target e tempo limite. O código do cliente é único para sua conta e empresa. O tempo limite é o tempo em segundos que o Target irá aguardar por uma resposta antes de exibir o conteúdo padrão. Certifique-se de que a opção **[!UICONTROL Usar HTTPS]** está marcada na página Administrar configurações do aplicativo no Adobe Mobile Services. Se o HTTPS não estiver ativado, todas chamadas no iOS9+ serão bloqueadas a menos que você lista de permissões ao servidor Target.

   ![](assets/mobile-clientcode.png)

1. Após criar/localizar seu aplicativo, acesse as configurações do aplicativo e baixe o SDK desejado.

   ![](assets/download-sdk.png)

>[!IMPORTANT]
>
> Se você não tiver acesso à interface de marketing para dispositivos móveis, poderá fazer alterações diretamente no arquivo de configuração no código do aplicativo; no entanto, não estará sincronizado com a página de configurações na interface do usuário.
