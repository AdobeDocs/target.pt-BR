---
keywords: Endereço IP; endereços IP; lista de permissões; lista de permissões; firewall; recs; feed; servidores; adobe experience cloud; recommendations
description: 'Exiba uma lista de endereços IP usados nos servidores de processamento de feeds do Recommendations para ajudá-lo a configurar seu firewall para permitir endereços IP originados de servidores Adobe. [!DNL Target] '
title: Quais endereços IP os servidores de processamento de feed do Recommendations usam?
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 24%

---

# ![PREMIUM](/help/assets/premium.png) Endereços IP usados &#x200B;&#x200B;pelos servidores de processamento de feeds do Recommendations

Lista de endereços IP usados nos servidores de processamento de feeds [!DNL Adobe Target] [!DNL Recommendations] para ajudá-lo a configurar seu firewall para permitir endereços IP originários de servidores Adobe.

[!DNL Target]  As atividades do Recommendations usam os seguintes hosts AWS ao acessar os servidores FTP dos clientes:

| Localização | Host |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

[!DNL Target]  As APIs do Recommendations também usam os mesmos hosts AWS.

>[!NOTE]
>
>Esses endereços IP foram atualizados pela última vez em 16 de março de 2021. Anteriormente, os servidores que acessavam os servidores FTP estavam no bloco CIDR de endereço IP 192.243.242.0/24 . Os servidores que hospedam APIs da Recommendations estavam no bloco CIDR de endereço IP 192.243.224.0/20.
