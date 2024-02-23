---
keywords: Endereço IP; endereços IP; lista de permissões; lista de permissões; firewall; recs; feed; servidores; adobe experience cloud; recomendações
description: Visualize uma lista de endereços IP usados em servidores de processamento de feed do  [!DNL Target]  Recommendations para ajudar você a configurar o firewall a fim de permitir endereços IP originados de servidores da Adobe.
title: Quais endereços IP os servidores de processamento de feed do Recommendations usam?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: 558de92e672c276474bc76fad19e5461ae7d4c88
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 49%

---

# Endereços IP usados por [!DNL Recommendations] servidores de processamento de feeds

Lista de endereços IP usados no [!DNL Adobe Target] [!DNL Recommendations] servidores de processamento de feed do para ajudar você a configurar o firewall a fim de permitir endereços IP originados de [!DNL Adobe] servidores.

>[!IMPORTANT]
>
>23 de fevereiro de 2023: O [!DNL Target] A equipe está atualizando os endereços de gateway NAT para download [!DNL Recommendations] Feeds. Se você implementar o incluir na lista de permissões de IP, certifique-se de incluir na lista de permissões os novos hosts AWS a seguir. Os hosts existentes estão programados para serem descontinuados no futuro. Todos os nove hosts agora estão operacionais.

As atividades do[!DNL Target] [!UICONTROL  Recommendations] usam os seguintes hosts AWS ao acessar os servidores FTP dos clientes:

**Novos hosts**:

| Localização | Host |
| --- | --- |
| Oregon | `52.40.124.129` |
| Oregon | `54.148.219.69` |
| Oregon | `54.189.208.212` |
| Oregon | `44.230.236.35` |
| Oregon | `54.190.78.243` |
| Oregon | `52.41.73.133` |

**Hosts existentes**:

| Localização | Host |
| --- | --- |
| Oregon | `44.241.237.28` |
| Oregon | `44.232.167.82` |
| Oregon | `52.41.252.205` |

As APIs do[!DNL Target] [!UICONTROL  Recommendations] APIs também usam os mesmos hosts AWS.
