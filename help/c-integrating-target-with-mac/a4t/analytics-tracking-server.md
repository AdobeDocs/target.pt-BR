---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Platform debugger;reporting source;developer tools
description: Se estiver usando uma versão mais antiga da at.js ou da mbox.js, deverá especificar um servidor de rastreamento de análise para as atividades que usam o Analytics for Target (A4T).
title: Usar um servidor de rastreamento do Analytics
feature: a4t general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '696'
ht-degree: 27%

---


# Usar um servidor de rastreamento do Analytics

Se você estiver usando uma versão anterior do at.js ou mbox.js, deverá especificar um servidor de rastreamento do Analytics para atividades que usam [!DNL Analytics] para [!DNL Target] (A4T).

>[!NOTE]
>
>Se você usar [!DNL Analytics] como fonte de relatórios do atividade, não será necessário especificar um servidor de rastreamento durante a criação da atividade se estiver usando a versão 61 (ou posterior) ou a versão 0.9.1 (ou posterior) do at.js. A biblioteca mbox.js ou at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].
>
>A equipe [!DNL Target] oferece suporte para o at.js 1.*x* e at.js 2.*x*. Atualize para a atualização mais recente da versão principal do at.js para garantir que você esteja executando uma versão compatível. Para obter mais informações, consulte [detalhes da versão do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Para garantir que os dados de [!DNL Target] vão para o local correto em [!DNL Analytics], o A4T exige que um servidor de rastreamento do Analytics seja enviado em todas as chamadas para Modstats de [!DNL Target]. Para implementações que usam vários servidores de rastreamento, você pode usar as [!DNL Adobe Experience Platform Debugger] ou as Ferramentas do desenvolvedor do seu navegador para determinar o servidor de rastreamento correto para sua atividade.

## Obtenha o servidor de rastreamento do Analytics usando o Adobe Experience Platform Debugger

O depurador deve ser visualizado em uma página na qual a atividade será entregue para garantir a seleção do servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página na qual você está criando sua atividade, abra [!DNL Adobe Experience Platform Debugger].

   Se você não instalou o depurador, consulte [Introdução ao Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. Clique em **[!UICONTROL Analytics]** no menu de navegação esquerdo.

   O servidor de rastreamento do Analytics está localizado na seção [!UICONTROL Nome do host] do depurador.

   * **Servidor** de rastreamento primário: Se o nome do host da solicitação corresponder ao domínio em que você está, então ele será um servidor de rastreamento primário. Por exemplo, se você estiver em `adobe.com`, `adobe.com` será o servidor de rastreamento primário.
   * **Servidor** de rastreamento de terceiros: Geralmente, um servidor de rastreamento de terceiros é  `[company].sc.omtrdc.net` onde a empresa é o nome da empresa, mas sempre termina  `sc.omtrdc.net`.
   * **Implementações** CNAME:  `sstats.adobe.com` é um exemplo de um servidor de rastreamento primário CNAME para uma solicitação https (segura). `stats.adobe.com` é um exemplo de uma solicitação primária CNAME para uma página http (não segura).

1. Copie todo o conteúdo do campo.

1. Na seção **[!UICONTROL Configurações de relatório]** da tela **[!UICONTROL Meta e configurações]****[!UICONTROL da atividade, cole as informações do servidor de rastreamento no campo Servidor de rastreamento.]**

   >[!NOTE]
   >
   >Você deve selecionar [!UICONTROL Analytics como a Fonte do Relatórios] para sua atividade para que o campo [!UICONTROL Servidor de rastreamento] esteja disponível.

## Obtenha o servidor de rastreamento do Analytics usando as Ferramentas do desenvolvedor do seu navegador

As Ferramentas do desenvolvedor devem ser exibidas em uma página onde a atividade será entregue para garantir que você selecione o servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página em que você está criando sua atividade, abra as Ferramentas do desenvolvedor do navegador (no Google Chrome, clique nas três elipses verticais no canto superior direito > Mais ferramentas > Ferramentas do desenvolvedor).

   ![Ferramentas para desenvolvedores do Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Clique na guia **[!UICONTROL Rede]**.

1. Filtre por `/ss,` para exibir as solicitações do Analytics.

   ![Ferramentas de desenvolvedor do Chrome com pesquisa /ss](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   O servidor de rastreamento é o nome do host da solicitação.

   * **Servidor** de rastreamento primário: Se o nome do host da solicitação corresponder ao domínio em que você está, então ele será um servidor de rastreamento primário. Por exemplo, se você estiver em `adobe.com`, `adobe.com` será o servidor de rastreamento primário.
   * **Servidor** de rastreamento de terceiros: Geralmente, um servidor de rastreamento de terceiros é  `[company].sc.omtrdc.net` onde a empresa é o nome da empresa, mas sempre termina  `sc.omtrdc.net`.
   * **Implementações** CNAME:  `sstats.adobe.com` é um exemplo de um servidor de rastreamento primário CNAME para uma solicitação https (segura). `stats.adobe.com` é um exemplo de uma solicitação primária CNAME para uma página http (não segura).

1. Copie todo o conteúdo do campo.

1. Na seção **[!UICONTROL Configurações de relatório]** da tela **[!UICONTROL Meta e configurações]****[!UICONTROL da atividade, cole as informações do servidor de rastreamento no campo Servidor de rastreamento.]**

   >[!NOTE]
   >
   >Você deve selecionar [!UICONTROL Analytics como a Fonte do Relatórios] para sua atividade para que o campo [!UICONTROL Servidor de rastreamento] esteja disponível.

