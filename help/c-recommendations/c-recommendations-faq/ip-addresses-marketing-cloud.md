---
keywords: Endereço IP, endereços IP, lista de permissões, lista de permissões, firewall, recs, feed, servidores, adobe marketing cloud, recommendations
description: Exiba uma lista de endereços IP usados nos servidores de processamento de feeds do Target Recommendations para ajudar você a configurar seu firewall para permitir endereços IP originários de servidores da Adobe.
title: Quais endereços IP os servidores de processamento de feed do Recommendations usam?
feature: Recommendations
translation-type: tm+mt
source-git-commit: 801a2717615a1f0ff2ce306cda59f68cc5c4a8f8
workflow-type: tm+mt
source-wordcount: '175'
ht-degree: 15%

---


# ![PREMIUM](/help/assets/premium.png) Endereços IP usados &#x200B;&#x200B;pelos servidores de processamento de feeds do Recommendations

Lista de endereços IP usados nos servidores de processamento de feeds [!DNL Adobe Target] [!DNL Recommendations] no data center de Oregon para ajudá-lo a configurar seu firewall para permitir endereços IP originários de servidores da Adobe.

[!DNL Target]  As atividades do Recommendations usam os seguintes endereços IP no data center de Oregon ao acessar os servidores de FTP dos clientes (certifique-se de verificar o link abaixo para obter as informações mais atuais):

| Notação CIDR | IP inicial | IP final |
|---|---|---|
| 192.243.242.0/24 | 192.243.242.0 | 192.243.242.255 |

[!DNL Target]  As APIs do Recommendations usam os seguintes endereços IP no data center de Oregon (certifique-se de verificar o link abaixo para obter as informações mais atuais):

| Notação CIDR | IP inicial | IP final |
|---|---|---|
| 192.243.224.0/20 | 192.243.224.0 | 192.243.239.255 |

>[!NOTE]
>
>Para obter a lista completa e mais atualizada, consulte [Endereços IP usados na Adobe Experience Cloud](https://helpx.adobe.com/analytics/kb/adobe-ip-addresses.html).

