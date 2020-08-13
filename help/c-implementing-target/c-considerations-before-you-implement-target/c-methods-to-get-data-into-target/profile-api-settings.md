---
keywords: implementation;api;profile;profile api settings;authentication token
description: Ative ou desative a autenticação para atualizações em lote pela API e gere um token de autenticação de perfil.
title: Configurações da API de perfil
feature: api
subtopic: Getting Started
topic: Standard
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 64%

---


# Configurações da API de perfil{#profile-api-settings}

Ative ou desative a autenticação para atualizações em lote pela API e gere um token de autenticação de perfil.

[!DNL Adobe Target]O cria e mantém um perfil para cada usuário individual. This profile is stored on the [!DNL Target] edge cluster and is updated in real time after every visit, however, you can update a profile individually or in bulk via API.

Para maior segurança, você pode fazer com que uma chamada de API de atualização em massa solicite um token de acesso válido a ser enviado no cabeçalho da solicitação. Users with [!UICONTROL Approver] permissions can generate and enable profile API authentication tokens.

**Para solicitar a autenticação e gerar um token de acesso usando a interface de usuário do Target:**

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.
1. Em API **[!UICONTROL de]** Perfil, alterne a opção **[!UICONTROL Exigir autenticação]** para a posição ativada ou desativada.

   ![](assets/profile_api_settings.png)

1. (Conditional) If you enabled authentication requirements, click **[!UICONTROL Generate New Pfofile Authentication Token]**.

   ![](assets/profile_api_settings_2.png)

   O token expira de acordo com o tempo listado na caixa [!UICONTROL Expira em].

   >[!NOTE]
   >
   >Também é possível gerar um token de autenticação de perfil por meio da API. Para obter mais informações, consulte [Perfis](https://developers.adobetarget.com/api/#profiles) no site de [desenvolvedores do Adobe Target](https://developers.adobetarget.com/).

1. Copie o token e inclua-o no cabeçalho da solicitação, em formato: &quot;Autorização&quot; : &quot;Portador&quot;

Click [!UICONTROL Generate New Profile Authentication Token] to regenerate the token as needed.

>[!IMPORTANT]
>
>Redefinir esse token resulta em falha das chamadas de API usando o token atual. Isso necessitará da atualização de qualquer script ou aplicativo que use esse token.
