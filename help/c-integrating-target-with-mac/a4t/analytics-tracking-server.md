---
keywords: analytics tracking server;A4T;Adobe Experience Cloud debugger;reporting source
description: Se estiver usando uma versão mais antiga da at.js ou da mbox.js, deverá especificar um servidor de rastreamento de análise para as atividades que usam o Analytics for Target (A4T).
title: Usar um servidor de rastreamento do Analytics
feature: a4t general
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 53%

---


# Usar um servidor de rastreamento do Analytics{#use-an-analytics-tracking-server}

If you are using an older version of at.js or mbox.js, you must specify an analytics tracking server for activities that use [!DNL Analytics] for [!DNL Target] (A4T).

>[!NOTE]
>
>If you use [!DNL Analytics] as your activity&#39;s reporting source, you do not need to specify a tracking server during activity creation if you are using mbox.js version 61 (or later) or at.js version 0.9.1 (or later). A biblioteca mbox.js ou at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].

To ensure that data from [!DNL Target] goes to the correct location in [!DNL Analytics], A4T requires an analytics tracking server to be sent in all calls to Modstats from [!DNL Target]. For implementations using multiple tracking servers you can use the [!DNL Adobe Experience Cloud Debugger] to determine the correct tracking server for your activity.

O depurador deve ser visualizado em uma página na qual a atividade será entregue para garantir a seleção do servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página na qual você está criando sua atividade, abra o [!DNL Adobe Experience Cloud Debugger].

   Se você não tiver instalado o depurador, consulte [Instalar o Experience Cloud Debugger](https://docs.adobe.com/content/help/en/debugger/using/install-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

   The analytics tracking server is found in the [!UICONTROL SiteCatalyst Image] section of the debugger. O campo é chamado *Cookies próprios* ou *Cookies de terceiros*, dependendo da implementação, e o valor do servidor de rastreamento do estará em um desses formatos:[!DNL Analytics]

   * (para implementações CNAME)
   * (para implementações não RDC)
   * (para implementações RDC)

   *Empresa*[!DNL Analytics] representa o nome da empresa do , *métricas* é um exemplo de um valor CNAME e *d1* é um exemplo de um data center do [!DNL Analytics]
1. Copie todo o conteúdo do campo.
1. Na seção [!UICONTROL Configurações de relatório] da tela [!UICONTROL Meta e configurações]**[!UICONTROL da atividade, cole as informações do servidor de rastreamento no campo Servidor de rastreamento.]**

   >[!NOTE]
   >
   >You must select [!UICONTROL Analytics as the Reporting Source] for your activity for the [!UICONTROL Tracking Server] field to be available.

