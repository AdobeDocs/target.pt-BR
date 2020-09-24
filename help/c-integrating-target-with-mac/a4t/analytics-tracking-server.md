---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;Adobe Experience Cloud debugger;reporting source;developer tools
description: Se estiver usando uma versão mais antiga da at.js ou da mbox.js, deverá especificar um servidor de rastreamento de análise para as atividades que usam o Analytics for Target (A4T).
title: Usar um servidor de rastreamento do Analytics
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 570f844c8b4ff6a4240262e6a1d2acf0e264ad18
workflow-type: tm+mt
source-wordcount: '649'
ht-degree: 24%

---


# Usar um servidor de rastreamento do Analytics{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). A biblioteca mbox.js ou at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].
>
>A [!DNL Target] equipe suporta ambos o at.js 1.*x* e at.js 2.*x*. Atualize para a atualização mais recente da versão principal do at.js para garantir que você esteja executando uma versão compatível. For more information, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Platform Debugger] or your browser&#39;s Developer Tools to determine the correct tracking server for your activity.

## Obtenha o servidor de rastreamento do Analytics usando o Adobe Experience Platform Debugger

O depurador deve ser visualizado em uma página na qual a atividade será entregue para garantir a seleção do servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página na qual você está criando sua atividade, abra o [!DNL Adobe Experience Platform Debugger].

   Se você não instalou o depurador, consulte [Introdução ao Adobe Experience Platform Debugger](https://docs.adobe.com/content/help/en/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. Clique em **[!UICONTROL Analytics]** no menu de navegação esquerdo.

   The analytics tracking server is found in the [!UICONTROL Hostname] section of the debugger.

   * **Servidor** de rastreamento primário: Se o nome do host da solicitação corresponder ao domínio em que você está, então ele será um servidor de rastreamento primário. Por exemplo, se você estiver ativo `adobe.com`, `adobe.com` será o servidor de rastreamento primário.
   * **Servidor** de rastreamento de terceiros: Geralmente, um servidor de rastreamento de terceiros é aquele `[company].sc.omtrdc.net` em que a empresa é o nome da empresa, mas sempre termina `sc.omtrdc.net`.
   * **Implementações** CNAME: `sstats.adobe.com` é um exemplo de um servidor de rastreamento primário CNAME para uma solicitação https (segura). `stats.adobe.com` é um exemplo de uma solicitação primária CNAME para uma página http (não segura).

1. Copie todo o conteúdo do campo.
1. Na seção **[!UICONTROL Configurações de relatório]** da tela **[!UICONTROL Meta e configurações]****[!UICONTROL da atividade, cole as informações do servidor de rastreamento no campo Servidor de rastreamento.]**

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

## Obtenha o servidor de rastreamento do Analytics usando as Ferramentas do desenvolvedor do seu navegador

As Ferramentas do desenvolvedor devem ser exibidas em uma página onde a atividade será entregue para garantir que você selecione o servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página em que você está criando sua atividade, abra as Ferramentas do desenvolvedor do navegador (no Google Chrome, clique nas três elipses verticais no canto superior direito > Mais ferramentas > Ferramentas do desenvolvedor).

   ![Ferramentas para desenvolvedores do Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Click the **[!UICONTROL Network]** tab.

1. Filtre para exibir `/ss,` as solicitações de análise.

   ![Ferramentas de desenvolvedor do Chrome com pesquisa /ss](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   O servidor de rastreamento é o nome do host da solicitação.

   * **Servidor** de rastreamento primário: Se o nome do host da solicitação corresponder ao domínio em que você está, então ele será um servidor de rastreamento primário. Por exemplo, se você estiver ativo `adobe.com`, `adobe.com` será o servidor de rastreamento primário.
   * **Servidor** de rastreamento de terceiros: Geralmente, um servidor de rastreamento de terceiros é aquele `[company].sc.omtrdc.net` em que a empresa é o nome da empresa, mas sempre termina `sc.omtrdc.net`.
   * **Implementações** CNAME: `sstats.adobe.com` é um exemplo de um servidor de rastreamento primário CNAME para uma solicitação https (segura). `stats.adobe.com` é um exemplo de uma solicitação primária CNAME para uma página http (não segura).

