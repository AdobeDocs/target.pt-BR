---
description: Se estiver usando uma versão mais antiga da at.js ou da mbox.js, deverá especificar um servidor de rastreamento de análise para as atividades que usam o Analytics for Target (A4T).
keywords: servidor de rastreamento de análises; A4T; Depurador da Adobe Experience Cloud; fonte de relatórios
seo-description: Se estiver usando uma versão mais antiga da at.js ou da mbox.js, deverá especificar um servidor de rastreamento de análise para as atividades que usam o Analytics for Target (A4T).
seo-title: Usar um servidor de rastreamento do Analytics
title: Usar um servidor de rastreamento do Analytics
uuid: ad700b90-f409-496a-bc26-0f0367410a85
translation-type: tm+mt
source-git-commit: 74a6f402bc0c9dae6f89cbdb632d7dbc53743593

---


# Usar um servidor de rastreamento do Analytics{#use-an-analytics-tracking-server}

Se estiver usando uma versão mais antiga da at.js ou da mbox.js, deverá especificar um servidor de rastreamento de análise para as atividades que usam o Analytics for Target (A4T).

>[!NOTE]
>
>Se você usar o Adobe Analytics como a fonte de relatórios da sua atividade, não será necessário especificar um servidor de rastreamento durante a criação da atividade usando a mbox.js versão 61 (ou posterior) ou a at.js versão 0.9.1 (ou posterior). A biblioteca mbox.js ou at.js envia automaticamente os valores do servidor de rastreamento ao [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].

Para garantir que os dados do Target sejam enviados para o local correto no Analytics, o A4T exige que todas as chamadas ao Modstats do Target sejam enviadas para um servidor de rastreamento. Para implementações que usam vários servidores de rastreamento, é possível usar o depurador da Adobe Experience Cloud para determinar o servidor de rastreamento correto para a sua atividade.

O depurador deve ser visualizado em uma página na qual a atividade será entregue para garantir a seleção do servidor de rastreamento correto. Também é possível pode especificar um servidor de rastreamento padrão para cada conta. Entre em contato com o Atendimento ao cliente para especificar ou modificar o padrão.

1. Na página em que você está criando sua atividade, abra o depurador da Adobe Experience Cloud.

   Se não tiver instalado o depurador, siga as [instruções de instalação do depurador da Adobe](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger_install.html).

   ![](assets/Screen_DebuggerTrackServ.png)

   O servidor de rastreamento do Analytics pode ser encontrado na seção Imagem do SiteCatalyst do depurador. O campo é chamado *Cookies próprios* ou *Cookies de terceiros*, dependendo da implementação, e o valor do servidor de rastreamento do Analytics estará em um desses formatos:

   * (para implementações CNAME)
   * (para implementações não RDC)
   * (para implementações RDC)
   *Empresa* representa o nome da empresa do Analytics, *métricas* é um exemplo de um valor CNAMEe *d1* é um exemplo de um data center do Analytics.
1. Copie todo o conteúdo do campo.
1. Na seção [!UICONTROL Configurações de relatório] da tela [!UICONTROL Meta e configurações]**da atividade, cole as informações do servidor de rastreamento no campo[!UICONTROL Servidor de rastreamento.]**

   >[!NOTE]
   >
   >É necessário selecionar o Adobe Analytics como a Fonte de relatórios da sua atividade para que o campo Servidor de rastreamento fique disponível.

