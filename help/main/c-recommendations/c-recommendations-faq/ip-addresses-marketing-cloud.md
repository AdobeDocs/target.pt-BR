---
keywords: Endereço IP; endereços IP; lista de permissões; lista de permissões; firewall; recs; feed; servidores; adobe experience cloud; recomendações
description: Visualize uma lista de endereços IP usados em servidores de processamento de feed do  [!DNL Target]  Recommendations para ajudar você a configurar o firewall a fim de permitir endereços IP originados de servidores da Adobe.
title: Quais endereços IP os servidores de processamento de feed do Recommendations usam?
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '136'
ht-degree: 100%

---

# ![PREMIUM](/help/main/assets/premium.png) Endereços IP usados &#x200B;&#x200B;pelos servidores de processamento de feeds do Recommendations

Lista de endereços IP usados em servidores de processamento de feed do [!DNL Adobe Target] [!DNL Recommendations] para ajudar você a configurar o firewall a fim de permitir endereços IP originados de servidores da Adobe.

As atividades do[!DNL Target] [!UICONTROL  Recommendations] usam os seguintes hosts AWS ao acessar os servidores FTP dos clientes:

| Localização | Host |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

As APIs do[!DNL Target] [!UICONTROL  Recommendations] APIs também usam os mesmos hosts AWS.

>[!NOTE]
>
>Esses endereços IP foram atualizados pela última vez em 16 de março de 2021. Anteriormente, os servidores que acessavam os servidores FTP estavam no bloco CIDR de endereço IP 192.243.242.0/24. Os servidores que hospedam APIs do Recommendations estavam no bloco CIDR de endereço IP 192.243.224.0/20.
