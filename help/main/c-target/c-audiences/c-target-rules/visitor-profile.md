---
keywords: perfil do visitante, perfil do visitante do target
description: Saiba como criar públicos-alvo no  [!DNL Adobe Target]  para direcionar visitantes que atendem a parâmetros de perfil específicos, como visitantes novos ou recorrentes, afinidade de categorias e muito mais.
title: Posso Direcionar Visitantes Que Atendem A Parâmetros De Perfil Específicos?
feature: Audiences
exl-id: aca45b80-660d-4b8e-a0d7-84627b8fd77b
TQID: https://experienceleague.adobe.com/lGNJLzHHa7aBUY3ZzJUU-9I8aPNsZgye1zmnN2mGHc4
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eeb
topic_v2: id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 250
ht-degree: 36%

---

# Perfil do visitante

Crie públicos-alvo no [!DNL Adobe Target] para direcionar visitantes que atendem a parâmetros de perfil específicos.

1. Na interface [!DNL Target], clique em **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Criar público]**.
1. Nomeie o público-alvo e adicione uma descrição opcional.
1. Arraste e solte **[!UICONTROL Perfil do visitante]** no painel do construtor de público-alvo.

1. Clique em **[!UICONTROL Selecionar]** e selecione uma destas opções:

   ![imagem target_visitor_profile](assets/target_visitor_profile.png)

   Os parâmetros de perfil do visitante são passados por meio da mbox (perfil). Você pode direcionar visitantes novos ou que retornam, ou incluir todos os usuários.

   * [!UICONTROL Novo visitante]
   * [!UICONTROL Visitante Recorrente]
   * [!UICONTROL Em Outros Testes]
   * [!UICONTROL Não Em Outros Testes]
   * [!UICONTROL Primeira Página da Sessão]
   * [!UICONTROL Não é a Primeira Página da Sessão]
   * [!UICONTROL Afinidade de categorias]

   Um perfil de visitante é criado na memória de borda local para cada chamada de mbox com um novo `mboxPC`. Após 30 minutos de inatividade, o perfil é salvo no banco de dados [!DNL Target] e pode ser acessado de outras bordas.

   Quando um visitante do site faz logon no meio de uma sessão e obtém um `3rdpartyId`, todos os atributos de perfil previamente carregados e vinculados ao `3rdPartyId` ficam imediatamente disponíveis.

   Você pode direcionar parâmetros de perfis personalizados e parâmetros de `user.`. Escolha o parâmetro que deseja usar para direcionar sua atividade. Se o parâmetro desejado não for exibido, o parâmetro não foi acionado por uma mbox.

1. (Opcional) Configure regras adicionais para o público-alvo.
1. Clique em **[!UICONTROL Concluído]**.

## Vídeo de treinamento: Criando públicos-alvo ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
