---
keywords: endereço IP;endereços IP;lista de permissões;lista de permissões;firewall;recs;feed;servidores;adobe marketing cloud;recomendações;endereço IP;lista de permissões;;firewall;recs;feed;servidores;adobe marketing cloud;Recomendações
description: Visualização uma lista de endereços IP usados em servidores de processamento de feed Recommendations Público alvo para ajudá-lo a configurar seu firewall para permitir endereços IP originários de servidores Adobe.
title: Quais endereços IP os servidores de processamento de feed da Recommendations usam?
feature: Recommendations
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '178'
ht-degree: 61%

---


# ![PREMIUM](/help/assets/premium.png) Endereços IP usados &#x200B;&#x200B;pelos servidores de processamento de feeds do Recommendations{#ip-addresses-used-by-recommendations-feed-processing-servers}

Utilização de lista de endereços IP nos servidores de processamento de feeds do Recommendations, localizados no data center de Oregon, para ajudá-lo a configurar seu firewall para permitir os endereços IP originados de servidores da Adobe.

As atividades do [!DNL Target] [!UICONTROL Recommendations] usam os seguintes endereços IP localizados no data center de Oregon ao acessar os servidores de FTP dos clientes (certifique-se de verificar o link abaixo para obter as informações mais atuais):

| Notação CIDR | IP inicial | IP final |
|---|---|---|
| 192.243.242.0/24 | 192.243.242.0 | 192.243.242.255 |

As APIs do [!DNL Target] [!UICONTROL Recommendations] usam os seguintes endereços IP localizados no data center de Oregon (certifique-se de verificar o link abaixo para obter as informações mais atuais):

| Notação CIDR | IP inicial | IP final |
|---|---|---|
| 192.243.224.0/20 | 192.243.224.0 | 192.243.239.255 |

>[!NOTE]
>
>Para obter a lista completa e mais atualizada, consulte [Endereços IP usados no Adobe Experience Cloud](https://helpx.adobe.com/analytics/kb/adobe-ip-addresses.html).

