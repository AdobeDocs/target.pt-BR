---
keywords: servidor de rastreamento de análises;depurador do Adobe Experience Cloud;depurador do Adobe Experience Platform;fonte de relatórios;ferramentas do desenvolvedor
description: Saiba como especificar um servidor de rastreamento do Analytics para atividades que usam o Analytics for [!DNL Target] (A4T) se estiver usando uma versão mais antiga da at.js.
title: Como usar um servidor de rastreamento do Analytics?
feature: Analytics for Target (A4T)
exl-id: 8066d6a6-661e-428b-9d5c-18537a80fb43
source-git-commit: 2fc704a1779414a370ffd00ef5442fce36e7a5dd
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 15%

---

# Usar um servidor de rastreamento do [!DNL Analytics]

Se você estiver usando uma versão mais antiga da at.js, deverá especificar um servidor de rastreamento do [!DNL Analytics] para atividades que usam o [!DNL Adobe Analytics] for [!DNL Adobe Target] (A4T).

>[!NOTE]
>
>Você não precisa especificar um servidor de rastreamento durante a criação da atividade se estiver usando a at.js versão 0.9.1 (ou posterior). A biblioteca at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Tracking Server] vazio na página [!UICONTROL Goals & Settings].
>
>A equipe [!DNL Target] dá suporte a at.js 1.*x* e at.js 2.*x*. Atualize para a atualização mais recente de qualquer versão principal do at.js para garantir que você esteja executando uma versão compatível. Para obter mais informações, consulte [detalhes da versão do at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank}.

Para garantir que os dados de [!DNL Target] vão para o local correto em [!DNL Analytics], O A4T requer que um servidor de rastreamento [!DNL Analytics] seja enviado em todas as chamadas para Modstats de [!DNL Target]. Para implementações que usam vários servidores de rastreamento, use o [!DNL Adobe Experience Platform Debugger] ou as Ferramentas do desenvolvedor do seu navegador para determinar o servidor de rastreamento correto para sua atividade.

## Obter o servidor de rastreamento [!DNL Analytics] usando o [!DNL Adobe Experience Platform Debugger]

O depurador deve ser exibido em uma página onde a atividade é entregue para garantir que você selecione o servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página em que você está criando sua atividade, abra o [!DNL Adobe Experience Platform Debugger].

   Se você não tiver instalado o depurador, consulte [visão geral do Adobe Experience Platform Debugger](https://experienceleague.adobe.com/docs/platform-learn/data-collection/debugger/overview.html).

1. Clique em **[!UICONTROL Analytics]** no menu de navegação esquerdo.

   ![Imagem de Screen_DebuggerTrackServ](assets/Screen_DebuggerTrackServ.png)

   O servidor de rastreamento [!DNL Analytics] foi encontrado na seção [!UICONTROL Hostname] do depurador.

   * **Servidor de rastreamento próprio**: se o nome de host da solicitação corresponder ao domínio em que você está, ele será um servidor de rastreamento próprio. Por exemplo, se você estiver em `adobe.com`, `adobe.com` será o servidor de rastreamento próprio.
   * **Servidor de rastreamento de terceiros**: normalmente, um servidor de rastreamento de terceiros é `[company].sc.omtrdc.net`, em que a empresa é o nome da sua empresa, mas sempre termina em `sc.omtrdc.net`.
   * **Implementações CNAME**: `sstats.adobe.com` é um exemplo de servidor de rastreamento próprio CNAME para uma solicitação https (segura). `stats.adobe.com` é um exemplo de uma solicitação CNAME própria para uma página http (não segura).

1. Copie todo o conteúdo do campo.

1. Na seção **[!UICONTROL Reporting Settings]** da tela **[!UICONTROL Goal & Settings]** da sua atividade, cole as informações do servidor de rastreamento no campo **[!UICONTROL Tracking Server]**.

   >[!NOTE]
   >
   >Selecione [!UICONTROL Analytics as the Reporting Source] para sua atividade para que o campo [!UICONTROL Tracking Server] fique disponível.

## Obtenha o servidor de rastreamento do [!DNL Analytics] usando as Ferramentas do Desenvolvedor do seu navegador

As Ferramentas do desenvolvedor devem ser visualizadas em uma página onde a atividade é entregue para garantir que você selecione o servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página em que você está criando sua atividade, abra as Ferramentas do desenvolvedor do navegador (no Google Chrome, clique nos três elipses verticais no canto superior direito > Mais ferramentas > Ferramentas do desenvolvedor).

   ![ferramentas para desenvolvedores do Chrome](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-dev-tools.png)

1. Clique na guia **[!UICONTROL Network]**.

1. Filtro para `/ss,` para exibir as [!DNL Analytics] solicitações.

   ![ferramentas para desenvolvedores do Chrome com /ss search](/help/main/c-integrating-target-with-mac/a4t/assets/chrome-search.png)

   O servidor de rastreamento é o nome de host da solicitação.

   * **Servidor de rastreamento próprio**: se o nome de host da solicitação corresponder ao domínio em que você está, ele será um servidor de rastreamento próprio. Por exemplo, se você estiver em `adobe.com`, `adobe.com` será o servidor de rastreamento próprio.
   * **Servidor de rastreamento de terceiros**: normalmente, um servidor de rastreamento de terceiros é `[company].sc.omtrdc.net`, em que a empresa é o nome da sua empresa, mas sempre termina em `sc.omtrdc.net`.
   * **Implementações CNAME**: `sstats.adobe.com` é um exemplo de servidor de rastreamento próprio CNAME para uma solicitação https (segura). `stats.adobe.com` é um exemplo de uma solicitação CNAME própria para uma página http (não segura).

1. Copie todo o conteúdo do campo.

1. Na seção **[!UICONTROL Reporting Settings]** da tela **[!UICONTROL Goal & Settings]** da sua atividade, cole as informações do servidor de rastreamento no campo **[!UICONTROL Tracking Server]**.

   >[!NOTE]
   >
   >Selecione [!UICONTROL Analytics as the Reporting Source] para sua atividade para que o campo [!UICONTROL Tracking Server] fique disponível.
