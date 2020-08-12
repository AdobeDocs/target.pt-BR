---
keywords: mbox;mbox3rdPartyId;profile syncing;profile synch;PCID
description: 'Informações sobre o perfil em tempo real '
title: Sincronização de perfil em tempo real para mbox3rdPartyId no Adobe Target
feature: null
topic: Standard
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 81%

---


# Sincronização de perfil em tempo real para mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

A mbox3rdPartyId é a ID de visitante de sua empresa, como a ID de associação do programa de fidelidade da empresa.

Quando um visitante faz logon no site de uma empresa, a empresa normalmente cria uma ID associada à conta, ao cartão de fidelidade, ao número de associado ou a outros identificadores aplicáveis do visitante dessa empresa.

Quando um visitante acessa uma página em que o [!DNL Target] está ativado, esse visitante recebe uma PCID do [!DNL Target]. Se o visitante fizer logon e a implementação transmitir a mbox3rdPartyId para o [!DNL Target], o [!DNL Target] conecta a mbox3rdPartyId desse visitante com a PCID do [!DNL Target].

A cada intervalo de 3 a 5 minutos, as atualizações são sincronizadas com o banco de dados. Quando o visitante faz logoff, os dados mesclados substituem os dados anteriores associados à mbox3rdPartyId, criando um registro mais completo das ações desse visitante. Se o mesmo atributo existe em ambas as IDs, por exemplo, a PCID apresenta category=hats e a mbox3rdPartyId apresenta category=skis, ou se o visitante viu a experiência A antes de fazer logon, mas a experiência B está armazenada na mbox3rdPartyId, o atributo armazenado na mbox3rdPartyId substitui o atributo da PCID. Se o visitante estava em uma atividade ou experiência antes de fazer logon, mas uma atividade e uma experiência diferentes estão armazenadas na mbox3rdPartyId, esse visitante é colocado na atividade e na experiência da mbox3rdPartyId depois de fazer logon.

| PCID (sem logon) | mbox3rdPartyId (com logon) | Mesclado e salvo em mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Atividade 1, experiência A | Atividade 1, experiência B | Atividade 1, experiência B |
| Atividade 1 |  | Atividade 1 |

Quando o visitante faz logoff, o perfil mesclado é mantido.

>[!NOTE]
>
>Se você quiser distinguir entre usuários autenticados (conectados) e não autenticados, use o Adobe Experience Cloud Identity Service (ECID) em vez de mbox3rdPartyID. Depois que um usuário é associado a mbox3rdPartyID, ele permanece associado ao usuário mesmo depois de sair.

>[!NOTE]
>
>[!DNL Adobe Analytics] os objetivos não serão rastreados nos casos em que a [!DNL Adobe Experience Cloud] ID (EDID) muda (por exemplo, o visitante muda de dispositivos), mesmo que o [!DNL Target] perfil possa ser mesclado com base na mbox3rdPartyId e ainda tenha informações de atividade. For visitors identified with the same EDID (those who access the page with the same device), [!DNL Analytics for Target] (A4T) should work as expected.

## Considerações {#considerations}

Se a página contiver várias mboxes e somente algumas usam a 3rdPartyID, o Target não terá um perfil do visitante/contexto separado para cada solicitação do visitante. O contexto da 3rdPartyID tem prioridade sobre o contexto da PCID. Basta que uma mbox transmita a 3rdPartyId para que o contexto tenha prioridade sobre a PCID.

Por exemplo, suponha que um visitante acesse uma página antes de fazer logon e visualizar uma experiência. A mbox global não usa a 3rdPartyID. Depois de fazer logon, o visitante visualiza uma das três experiências com mboxes secundárias, sendo que algumas usam a 3rdPartyID. O visitante visita várias páginas no site e usa o botão Voltar para retornar à página principal acessada antes de fazer logon e visualizar uma experiência diferente. Neste cenário, a mbox global não transmitiu a 3rdPartyID, mas uma ou mais mboxes secundárias transmitiram. A 3rdPartyID teve prioridade sobre a PCID.
