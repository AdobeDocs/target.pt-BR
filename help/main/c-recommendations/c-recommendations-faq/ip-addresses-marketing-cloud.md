---
keywords: Endereço IP; endereços IP; lista de permissões; lista de permissões; firewall; recs; feed; servidores; adobe experience cloud; recomendações
description: Visualize uma lista de endereços IP usados em servidores de processamento de feed do  [!DNL Target]  Recommendations para ajudar você a configurar o firewall a fim de permitir endereços IP originados de servidores da Adobe.
title: Quais endereços IP os servidores de processamento de feed do Recommendations usam?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
source-git-commit: be5b3158c758fa08802c1dc0541c9e989a2c7740
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 35%

---

# Endereços IP usados por [!DNL Recommendations] servidores de processamento de feed

Lista de endereços IP usados em servidores de processamento de feed do [!DNL Adobe Target] [!DNL Recommendations] para ajudar você a configurar o firewall a fim de permitir endereços IP originados de servidores do [!DNL Adobe].

>[!IMPORTANT]
>
>A equipe [!DNL Target] está atualizando os endereços de gateway NAT para baixar os feeds [!DNL Recommendations]. Se você implementar o incluir na lista de permissões de IP, certifique-se de incluir na lista de permissões os novos hosts AWS a seguir. Os hosts existentes estão programados para serem desativados em 30 de junho de 2024. Para garantir uma transição tranquila, inclua na lista de permissões todos os nove endereços. Não há urgência para remover os endereços existentes.

[!DNL Target] [!UICONTROL Recommendations] atividades usam os seguintes hosts AWS ao acessar os servidores FTP dos clientes:

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

As APIs de [!DNL Target] [!UICONTROL Recommendations] também usam os mesmos hosts AWS.
