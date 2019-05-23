---
description: Ative ou desative a autenticação para atualizações em lote pela API e gere um token de autenticação de perfil.
keywords: implementação; api; perfil; configurações da api de perfil
seo-description: Ative ou desative a autenticação para atualizações em lote pela API e gere um token de autenticação de perfil.
seo-title: Configurações da API de perfil
solution: Target
subtopic: Introdução
title: Configurações da API de perfil
topic: Padrão
uuid: 481b4a14-f10f-47cd-988d-9e6b8c4d5c00
translation-type: tm+mt
source-git-commit: 19a73ca8d1f165a5279b2b76f5f22057a070f0a9

---


# Configurações da API de perfil{#profile-api-settings}

Ative ou desative a autenticação para atualizações em lote pela API e gere um token de autenticação de perfil.

O Adobe Target cria e mantém um perfil para cada usuário individual. Esse perfil é armazenado no cluster de borda do Target e atualizado em tempo real após cada visita, no entanto, você pode atualizar um perfil individualmente ou em massa via API.

Para maior segurança, você pode fazer com que uma chamada de API de atualização em massa solicite um token de acesso válido a ser enviado no cabeçalho da solicitação. Usuários com permissões de Aprovador podem gerar e ativar tokens de autenticação da API de perfil.

**Para solicitar a autenticação e gerar um token de acesso usando a interface de usuário do Target:**

1. Clique em **[!UICONTROL Configuração]** &gt; **[!UICONTROL Implementação]**.
1. Em **[!UICONTROL Configurações de API de perfil]**, use a lista suspensa **Requer autenticação]para ativar ou desativar os requisitos de autenticação.[!UICONTROL **

   ![](assets/profile_api_settings.png)

1. (Condicional) se você ativou requisitos de autenticação, clique em **[!UICONTROL Gerar token de autenticação de perfil]**.

   ![](assets/profile_api_settings_2.png)

   O token expira de acordo com o tempo listado na caixa [!UICONTROL Expira em].

   >[!NOTE]
   >
   >Também é possível gerar um token de autenticação de perfil por meio da API. Para obter mais informações, consulte [Perfis](https://developers.adobetarget.com/api/#profiles) no site de [desenvolvedores do Adobe Target](https://developers.adobetarget.com/).

1. Copie o token e inclua-o no cabeçalho da solicitação, em formato: &quot;Autorização&quot; : &quot;Portador&quot;

Clique em [!UICONTROL Gerar novamente token de autenticação de perfil] para gerar novamente o token, conforme necessário.

>[!IMPORTANT]
>
>Redefinir esse token resulta em falha das chamadas de API usando o token atual. Isso necessitará da atualização de qualquer script ou aplicativo que use esse token.

