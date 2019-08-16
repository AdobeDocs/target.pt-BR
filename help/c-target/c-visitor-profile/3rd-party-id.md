---
description: A mbox3rdPartyID é a ID de visitante de sua empresa, como a ID de associação do programa de fidelidade da empresa.
keywords: mbox, mbox3rdPartyID, sincronização de perfil, perfil sincronizado; PCID
seo-description: 'Informações sobre o perfil em tempo real '
seo-title: Sincronização de perfil em tempo real para mbox 3 rdpartyid no Adobe Target
solution: Target
title: Sincronização de perfil em tempo real para mbox3rdPartyID
topic: Padrão
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 647776170531230a0d0f0aa3d97565fbb75bc963

---


# Sincronização de perfil em tempo real para mbox3rdPartyID{#real-time-profile-syncing-for-mbox-rdpartyid}

A mbox3rdPartyID é a ID de visitante de sua empresa, como a ID de associação do programa de fidelidade da empresa.

Quando um visitante faz logon no site de uma empresa, a empresa normalmente cria uma ID associada à conta, ao cartão de fidelidade, ao número de associado ou a outros identificadores aplicáveis do visitante dessa empresa.

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyID to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyID with the [!DNL Target] PCID.

As atualizações são sincronizadas com o banco de dados a cada três a cinco minutos. Quando o visitante faz logout, os dados mesclados substituem os dados anteriores associados ao mbox3rdPartyID, criando um registro mais completo das ações desse visitante. Se o mesmo atributo existe em ambas as IDs, por exemplo, o PCID tem categoria "chapéus", e o mbox3rdPartyID tem categoria "esquis", ou se o visitante viu a experiência A antes de fazer logon, mas a experiência B está armazenada no mbox3rdPartyID, o atributo armazenado no mbox3rdPartyID substitui o atributo do PCID. Se o visitante estava em uma atividade ou experiência antes de fazer logon, mas uma atividade e uma experiência diferentes estão armazenadas no mbox3rdPartyID, esse visitante é colocado na atividade e na experiência do mbox3rdPartyID depois de fazer logon.

| PCID (não conectado) | mbox3rdPartyID (com logon) | Mesclado e salvo em mbox3rdPartyID |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Atividade 1, experiência A | Atividade 1, experiência B | Atividade 1, experiência B |
| Atividade 1 |  | Atividade 1 |

Quando o visitante faz logoff, o perfil mesclado é mantido.

>[!NOTE]
>
>As metas do [!DNL Adobe Analytics] não serão rastreadas nos casos em que a ID (MID) do [!DNL Adobe Experience Cloud] for alterada (por exemplo, o visitante que muda os dispositivos), embora o perfil do [!DNL Target] possa ser combinado com base na mbox3rdPartyID e ainda ter informações de atividade. Para visitantes identificados com a mesma MID (aqueles que acessam a página com o mesmo dispositivo), o [!DNL Analytics for Target] (A4T) deve funcionar conforme esperado.

## Considerações {#considerations}

Se a página contiver várias mboxes e somente alguns usarem 3 rdpartyid, o Target não terá um perfil/contexto de visitante separado para cada solicitação de visitante. O contexto 3 rdpartyid tem prioridade sobre o contexto PCID. É suficiente para uma mbox passar 3 rdpartyid para que seu contexto tenha prioridade sobre PCID.

Por exemplo, suponha que um visitante acessa uma página antes de fazer logon e visualizar uma experiência. A mbox global não usa 3 rdpartyid. Depois de fazer logon, o visitante visualiza uma das três experiências com mboxes secundárias, sendo que alguns usam 3 rdpartyid. O visitante visita várias páginas no site e usa o botão Voltar para retornar à página principal acessada antes de fazer logon e visualizar uma experiência diferente. Neste cenário, a mbox global não passou 3 rdpartyid, mas uma ou mais mboxes secundárias. 3 Rdpartyid tem prioridade sobre PCID.
