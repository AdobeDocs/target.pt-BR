---
keywords: perfil do visitante, perfil do visitante do target
description: Saiba como criar públicos-alvo no [!DNL Adobe Target] para direcionar os visitantes que atendem a parâmetros de perfil específicos, como visitante novo ou recorrente, afinidade de categorias e muito mais.
title: Posso Direcionar Visitantes Que Atendem A Parâmetros De Perfil Específicos?
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
source-git-commit: 293b2869957c2781be8272cfd0cc9f82d8e4f0f0
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 46%

---

# Perfil do visitante

Criar públicos-alvo no [!DNL Adobe Target] para direcionar os visitantes que atendem a parâmetros de perfil específicos.

1. Na interface do [!DNL Target], clique em **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Criar público-alvo]**.
1. Nomeie o público-alvo e adicione uma descrição opcional.
1. Arrastar e soltar **[!UICONTROL Perfil do visitante]** no painel do audience builder.

1. Clique em **[!UICONTROL Selecionar]** e selecione uma destas opções:

   ![imagem target_visitor_profile](assets/target_visitor_profile.png)

   Os parâmetros de perfil do visitante são passados por meio da mbox (perfil). Você pode direcionar visitantes novos ou que retornam, ou incluir todos os usuários.

   * [!UICONTROL Novo visitante]
   * [!UICONTROL Visitante Recorrente]
   * [!UICONTROL Em outros testes]
   * [!UICONTROL Não em outros testes]
   * [!UICONTROL Primeira página da sessão]
   * [!UICONTROL Não é a primeira página da sessão]
   * [!UICONTROL Afinidade de categorias]

   Um perfil de visitante é criado na memória de borda local para cada chamada de mbox com um novo `mboxPC`. Após 30 minutos de inatividade, o perfil é salvo na [!DNL Target] banco de dados e pode ser acessada de outras bordas.

   Quando um visitante do site faz logon no meio de uma sessão e obtém um `3rdpartyId`, todos os atributos de perfil previamente carregados e vinculados ao `3rdPartyId` estão imediatamente disponíveis.

   Você pode direcionar parâmetros de perfis personalizados e parâmetros de `user.`. Escolha o parâmetro que deseja usar para direcionar sua atividade. Se o parâmetro desejado não for exibido, o parâmetro não foi acionado por uma mbox.

1. (Opcional) Configure regras adicionais para o público-alvo.
1. Clique em **[!UICONTROL Concluído]**.

## Vídeo de treinamento: Criação de públicos-alvo ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
