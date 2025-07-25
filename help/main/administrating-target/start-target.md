---
keywords: Administração; função de aprovador; aprovador
description: Execute as primeiras tarefas que os administradores do  [!DNL Adobe Target]  devem realizar após receber o convite enviado por email para o  [!DNL Adobe Experience Cloud].
title: Onde Começar A Administrar O  [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: b60236da-20ae-4bab-b261-6a33d2f70e23
source-git-commit: 614fd89c9746ce55f502debd5b689c34de400ae5
workflow-type: tm+mt
source-wordcount: '436'
ht-degree: 32%

---

# Primeiros passos do administrador

Este artigo contém as primeiras etapas que os administradores do [!DNL Adobe Target] devem realizar após receber o convite enviado por email para o [!DNL Adobe Experience Cloud].

## Seja convidado para [!DNL Target] {#task_3E0817630774431983FAA3D2CB2E75BD}

Um administrador do sistema no [!DNL Adobe Admin Console] deve adicioná-lo como usuário no [!DNL Target], convidando-o para entrar. O administrador do sistema deve então adicioná-lo a um ou mais perfis de produto com função específica (grupos de usuários). Ambas as tarefas são executadas no [Adobe Admin Console](https://adminconsole.adobe.com).

Para obter mais informações, consulte [Gerenciar grupos de usuários](https://helpx.adobe.com/enterprise/using/users.html).

Você receberá um email de convite depois que o administrador do sistema executar essas etapas.

## Aceite o convite {#task_24FE66659E634B24AB61DB8497772E17}

Depois de receber o convite para entrar no [!DNL Adobe Experience Cloud], aceite-o, faça logon e aceite o [!UICONTROL End User License Agreement] (EULA).

1. Aceite o convite para o [!DNL Adobe Experience Cloud].
1. Se ainda não tiver uma Adobe ID, você receberá uma solicitação para criar uma.

   Se você tiver uma Adobe ID, seu Adobe ID será reconhecido e você receberá uma solicitação para fazer logon.
1. Aceite o [!UICONTROL Terms of Use].
1. Analise o resumo do que você fez até agora e clique em **[!UICONTROL Continue to Experience Cloud]**.
1. Entre no [!DNL Adobe Experience Cloud] e clique em **[!UICONTROL Link Account]**.

   >[!NOTE]
   >
   >Caso não vincule sua conta, não será possível acessar o [!DNL Target].

   Todos os produtos [!UICONTROL Experience Cloud] aparecem na página de vinculação. Clique em `Link Target` e digite seu nome de usuário e senha [!DNL Target] para acessar [!DNL Target].
1. Clique em **[!UICONTROL Continue to Experience Cloud]**.

   Nesse ponto, você ainda não tem nenhum grupo configurado com qualificações para você vincular.
1. Se desejar, assista ao vídeo que apresenta você ao [!DNL Adobe Experience Cloud].
1. Para ver seus novos privilégios e acessar o produto, saia da [!DNL Adobe Experience Cloud] e entre novamente.
1. Prossiga para a próxima etapa [, atribuindo a função de Aprovador](/help/main/administrating-target/start-target.md#task_15CAA437A71444E2932B333D5E66A3C7).

## Atribuir a função de aprovador a si próprio {#task_15CAA437A71444E2932B333D5E66A3C7}

Depois de aceitar o convite para entrar no [!DNL Adobe Experience Cloud] e fazer logon, confirme se [!DNL Target] foi adicionado à sua conta do [!DNL Experience Cloud] e atribua a si mesmo a função [!UICONTROL Approver] para [!DNL Target].

Se sua organização tiver uma licença do [Target Standard](/help/main/c-intro/intro.md#section_ACD5EFF17AAB4E979CBEFA0145CCD905), consulte [Especificar funções e permissões](/help/main/administrating-target/c-user-management/c-user-management/user-management.md#roles-permissions) em *Usuários*.

Se sua organização tiver uma licença do [Target Premium](/help/main/c-intro/intro.md#premium), consulte [Etapa 6: especificar funções e permissões](/help/main/administrating-target/c-user-management/property-channel/properties-overview.md#section_8C425E43E5DD4111BBFC734A2B7ABC80) em *Configurar permissões corporativas*.

A próxima etapa deve ser configurar usuários em [!DNL Target Standard] e [!DNL Target Premium]. Para obter mais informações, consulte [Gerenciamento de usuários](/help/main/administrating-target/c-user-management/user-management.md).

## Permissões necessárias para editar configurações de [!UICONTROL Administration] {#admin-permissions}

**Antes de 22 de abril de 2025**: os usuários com direitos de [!UICONTROL Approvers] no [!DNL Adobe Admin Console] podem editar ou alterar todas as configurações na página [[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md) de [!DNL Target], independentemente da sua função [!DNL Target].

**A partir de 22 de abril de 2025**: somente administradores do [!UICONTROL Product] e do [!UICONTROL Solutions] poderão atualizar configurações nas seções [[!UICONTROL Administration]](/help/main/administrating-target/administrating-target.md), independentemente de suas funções nos espaços de trabalho [!DNL Target]. Os usuários sem esta permissão terão acesso somente leitura às seções [!UICONTROL Administration].

Essa atualização melhora o controle organizacional sobre as configurações da instância [!DNL Target], evitando atualizações acidentais que podem afetar a entrega da atividade em várias equipes de teste e personalização.
