---
keywords: Endereço IP; endereços IP; lista de permissões; lista de permissões; firewall; recs; feed; servidores; adobe experience cloud; recomendações
description: Visualize uma lista de endereços IP usados em servidores de processamento de feed do  [!DNL Target]  Recomendações para ajudar você a configurar o firewall a fim de permitir endereços IP originados de servidores da Adobe.
title: Quais são os endereços IP usados pelos servidores de processamento de feed do Recomendações?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: a666cfc4-ed74-44e8-9ff5-212e4fd65c03
TQID: https://experienceleague.adobe.com/-EhfjK6jTuHX33utQig-XYhf-nzkWlxb58VRmK9fLWo
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 189
ht-degree: 32%

---

# Endereços IP usados por [!DNL Recommendations] servidores de processamento de feed

Lista de endereços IP usados em servidores de processamento de feed do [!DNL Adobe Target] [!DNL Recommendations] para ajudar você a configurar o firewall a fim de permitir endereços IP originados de servidores do [!DNL Adobe].

>[!IMPORTANT]
>
>A equipe [!DNL Target] está atualizando os endereços de gateway NAT para baixar os feeds [!DNL Recommendations]. Se você implementar o incluir na lista de permissões de IP, certifique-se de incluir na lista de permissões os novos hosts da AWS a seguir. Os hosts existentes estão programados para serem desativados em 30 de junho de 2024. Para garantir uma transição suave, inclua na lista de permissões todos os nove endereços. Não há urgência para remover os endereços existentes.

As atividades do [!DNL Target] [!UICONTROL Recommendations] usam os seguintes hosts da AWS ao acessar os servidores FTP dos clientes:

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

As APIs do [!DNL Target] [!UICONTROL Recommendations] também usam os mesmos hosts do AWS.
