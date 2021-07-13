---
keywords: servidor de rastreamento do analytics; A4T; Adobe Experience Cloud Debugger; Adobe Experience Platform Debugger; fonte de relatórios; ferramentas do desenvolvedor
description: 'Saiba como especificar um servidor de rastreamento do Analytics para atividades que usam o Analytics para [!DNL Target] (A4T) se estiver usando uma versão mais antiga da at.js. '
title: Como usar um servidor de rastreamento do Analytics?
feature: 'Analytics for Target (A4T) '
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 3c79b2ce70e456275ddf6774a35ae5c36f0ae99d
workflow-type: tm+mt
source-wordcount: '693'
ht-degree: 19%

---

# Usar um servidor de rastreamento do Analytics

Se estiver usando uma versão mais antiga da at.js, deverá especificar um servidor de rastreamento do Analytics para atividades que usam [!DNL Adobe Analytics] para [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>Você não precisa especificar um servidor de rastreamento durante a criação da atividade se estiver usando a at.js versão 0.9.1 (ou posterior). A biblioteca at.js envia automaticamente os valores do servidor de rastreamento para [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].
>
>A equipe [!DNL Target] é compatível com o at.js 1.*x* e at.js 2.*x*. Atualize para a atualização mais recente de qualquer versão principal do at.js para garantir que você esteja executando uma versão compatível. Para obter mais informações, consulte [detalhes da versão do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

Para garantir que os dados de [!DNL Target] vão para o local correto em [!DNL Analytics], o A4T requer que um servidor de rastreamento do Analytics seja enviado em todas as chamadas para Modstats de [!DNL Target]. Para implementações que usam vários servidores de rastreamento, use o [!DNL Adobe Experience Platform Debugger] ou as Ferramentas do desenvolvedor do navegador para determinar o servidor de rastreamento correto para a atividade.

## Obter o servidor de rastreamento do Analytics usando o Adobe Experience Platform Debugger

O depurador deve ser exibido em uma página em que a atividade é entregue para garantir que você selecione o servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página em que você está criando sua atividade, abra o [!DNL Adobe Experience Platform Debugger].

   Se você não tiver instalado o depurador, consulte [Introdução ao Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/tutorials/data-ingestion/web-sdk/introduction-to-the-experience-platform-debugger.html).

   ![](assets/Screen_DebuggerTrackServ.png)

1. Clique em **[!UICONTROL Analytics]** no menu de navegação esquerdo.

   O servidor de rastreamento do Analytics é encontrado na seção [!UICONTROL Hostname] do depurador.

   * **Servidor** de rastreamento próprio: Se o nome do host da solicitação corresponder ao domínio em que você está, ele será um servidor de rastreamento próprio. Por exemplo, se você estiver em `adobe.com`, `adobe.com` será o servidor de rastreamento próprio.
   * **Servidor** de rastreamento de terceiros: Normalmente, um servidor de rastreamento de terceiros é  `[company].sc.omtrdc.net` onde a empresa é o nome de sua empresa, mas sempre termina em  `sc.omtrdc.net`.
   * **Implementações** CNAME:  `sstats.adobe.com` é um exemplo de um servidor de rastreamento primário CNAME para uma solicitação https (secure). `stats.adobe.com` é um exemplo de uma solicitação primária CNAME para uma página http (não segura).

1. Copie todo o conteúdo do campo.

1. Na seção **[!UICONTROL Configurações de relatório]** da tela **[!UICONTROL Meta e configurações]****[!UICONTROL da atividade, cole as informações do servidor de rastreamento no campo Servidor de rastreamento.]**

   >[!NOTE]
   >
   >Selecione [!UICONTROL Analytics como Fonte de relatórios] para sua atividade para que o campo [!UICONTROL Servidor de rastreamento] fique disponível.

## Obtenha o servidor de rastreamento do Analytics usando as Ferramentas do desenvolvedor do navegador

As Ferramentas do desenvolvedor devem ser exibidas em uma página em que a atividade é entregue para garantir que você selecione o servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página em que você está criando sua atividade, abra as Ferramentas do desenvolvedor do navegador (no Google Chrome, clique nos três elipses verticais no canto superior direito > Mais ferramentas > Ferramentas do desenvolvedor).

   ![Ferramentas de desenvolvedor do Chrome](/help/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Clique na guia **[!UICONTROL Rede]**.

1. Filtre por `/ss,` para exibir as solicitações do Analytics.

   ![Ferramentas de desenvolvedor do Chrome com pesquisa /ss](/help/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   O servidor de rastreamento é o nome do host da solicitação.

   * **Servidor** de rastreamento próprio: Se o nome do host da solicitação corresponder ao domínio em que você está, ele será um servidor de rastreamento próprio. Por exemplo, se você estiver em `adobe.com`, `adobe.com` será o servidor de rastreamento próprio.
   * **Servidor** de rastreamento de terceiros: Normalmente, um servidor de rastreamento de terceiros é  `[company].sc.omtrdc.net` onde a empresa é o nome de sua empresa, mas sempre termina em  `sc.omtrdc.net`.
   * **Implementações** CNAME:  `sstats.adobe.com` é um exemplo de um servidor de rastreamento primário CNAME para uma solicitação https (secure). `stats.adobe.com` é um exemplo de uma solicitação primária CNAME para uma página http (não segura).

1. Copie todo o conteúdo do campo.

1. Na seção **[!UICONTROL Configurações de relatório]** da tela **[!UICONTROL Meta e configurações]****[!UICONTROL da atividade, cole as informações do servidor de rastreamento no campo Servidor de rastreamento.]**

   >[!NOTE]
   >
   >Selecione [!UICONTROL Analytics como Fonte de relatórios] para sua atividade para que o campo [!UICONTROL Servidor de rastreamento] fique disponível.
