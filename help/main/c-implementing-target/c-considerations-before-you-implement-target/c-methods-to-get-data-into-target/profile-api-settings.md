---
keywords: implementação, api, perfil, configurações da api de perfil, token de autenticação
description: Saiba como configurar a autenticação para atualizações em lote pelo Adobe [!DNL Target] APIs e gerar um token de autenticação de perfil.
title: Como uso as configurações da API de perfil para ativar ou desativar atualizações em lote?
feature: APIs/SDKs
role: Developer
exl-id: 6346e11b-0853-47f1-9706-69e8635a6f25
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 61%

---

# Configurações da API de perfil

Ativar ou desativar a autenticação para atualizações em lote via [!DNL Adobe Target] APIs e gerar um token de autenticação de perfil.

[!DNL Adobe Target]O cria e mantém um perfil para cada usuário individual. Esse perfil é armazenado no [!DNL Target] cluster de borda e é atualizado em tempo real após cada visita; no entanto, é possível atualizar um perfil individualmente ou em massa por meio da API.

Para maior segurança, você pode fazer com que uma chamada de API de atualização em massa solicite um token de acesso válido a ser enviado no cabeçalho da solicitação.

**Para solicitar a autenticação e gerar um token de acesso usando a interface de usuário do Target:**

1. Clique em **[!UICONTROL Administração]** > **[!UICONTROL Implementação]**.
1. Em **[!UICONTROL API de perfil]** deslize o **[!UICONTROL Exigir autenticação]** alterne para a posição ativada ou desativada.

   ![](assets/profile_api_settings.png)

1. (Condicional) Se você ativou requisitos de autenticação, clique em **[!UICONTROL Gerar novo token de autenticação de perfil]**.

   ![](assets/profile_api_settings_2.png)

   O token expira de acordo com o tempo listado na caixa [!UICONTROL Expira em].

   Você deve ter uma das seguintes permissões de usuário para gerar um token de autenticação:

   * Pelo menos permissão de [!UICONTROL Editor] (ou [!UICONTROL Aprovador])

      Para obter mais informações para clientes do [!DNL Target Standard], consulte [Especificar funções e permissões](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) em *Usuários*. Para obter mais informações para clientes do [!DNL Target Premium], consulte [Configurar permissões corporativas](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Função de administrador no nível de espaço de trabalho/perfil de produto

      Os espaços de trabalho estão disponíveis somente para clientes do [!DNL Target Premium]. Para obter mais informações, consulte [Configurar permissões corporativas](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md).

   * Direitos de administrador (permissão de Sysadmin) no nível do produto [!DNL Adobe Target]
   >[!NOTE]
   >
   >Também é possível gerar um token de autenticação de perfil por meio da API. Para obter mais informações, consulte [Perfis](https://developers.adobetarget.com/api/#profiles) no site de [desenvolvedores do Adobe Target](https://developers.adobetarget.com/).

1. Copie o token e inclua-o no cabeçalho da solicitação, em formato: &quot;Autorização&quot; : &quot;Portador&quot;

Clique em [!UICONTROL Gerar novo token de autenticação de perfil] para gerar novamente o token, conforme necessário.

>[!IMPORTANT]
>
>Redefinir esse token resulta em falha das chamadas de API usando o token atual. Isso necessitará da atualização de qualquer script ou aplicativo que use esse token.
