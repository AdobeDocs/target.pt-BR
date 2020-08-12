---
keywords: IP address;IP addresses;whitelist;allowlist;firewall;recs;feed;servers;adobe marketing cloud;recommendations
description: Utilização de lista de endereços IP nos servidores de processamento de feeds do Recommendations, localizados no data center de Oregon, para ajudá-lo a configurar seu firewall para permitir os endereços IP originados de servidores da Adobe.
title: Endereços IP usados pelos servidores de processamento de feed do Recommendations
feature: null
uuid: 8e1943b6-274c-4347-8f4b-7ac108845926
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 87%

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
>For the complete, most up-to-date list, see [IP Addresses used in the Adobe Experience Cloud](https://helpx.adobe.com/analytics/kb/adobe-ip-addresses.html).

