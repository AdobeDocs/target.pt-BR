---
description: A mbox3rdPartyId é a ID de visitante da sua empresa, como a ID de associação do programa de fidelidade da sua empresa.
keywords: mbox;mbox3rdPartyId;sincronização de perfil;sincronização de perfil;PCID
seo-description: 'Informações sobre o perfil em tempo real '
seo-title: Sincronização de perfil em tempo real para mbox3rdPartyId no Adobe Target
solution: Target
title: Sincronização de perfil em tempo real para mbox3rdPartyId
topic: Padrão
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

A mbox3rdPartyId é a ID de visitante da sua empresa, como a ID de associação do programa de fidelidade da sua empresa.

Quando um visitante faz logon no site de uma empresa, a empresa normalmente cria uma ID associada à conta, ao cartão de fidelidade, ao número de associado ou a outros identificadores aplicáveis do visitante dessa empresa.

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

A cada intervalo de 3 a 5 minutos, as atualizações são sincronizadas com o banco de dados. Quando o visitante faz logout, os dados unidos substituem os dados anteriores associados ao mbox3rdPartyId, criando um registro mais completo das ações do visitante. Se o mesmo atributo existir em ambas as IDs — por exemplo, o PCID tem category=hats e o mbox3rdPartyId tem category=skis, ou se o visitante viu a experiência A antes de fazer logon, mas a experiência B é armazenada no mbox3rdPartyId — o atributo armazenado no mbox3rdPartyId substitui o atributo do PCID. Se o visitante estava em uma atividade ou experiência antes de fazer logon, mas uma atividade e experiência diferentes são armazenadas no mbox3rdPartyId, depois de fazer logon, o visitante é colocado na atividade e experiência do mbox3rdPartyId.

| PCID (sem logon) | mbox3rdPartyId (conectado) | Mesclado e salvo em mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Atividade 1, experiência A | Atividade 1, experiência B | Atividade 1, experiência B |
| Atividade 1 |  | Atividade 1 |

Quando o visitante faz logoff, o perfil mesclado é mantido.

>[!NOTE]
>
>[!DNL Adobe Analytics] as metas não serão rastreadas nos casos em que a [!DNL Adobe Experience Cloud] ID (MID) muda (por exemplo, o visitante muda de dispositivo), mesmo que o [!DNL Target] perfil possa ser mesclado com base na mbox3rdPartyId e ainda tenha informações de atividade. Para visitantes identificados com a mesma MID (aqueles que acessam a página com o mesmo dispositivo), o [!DNL Analytics for Target] (A4T) deve funcionar conforme esperado.

## Considerações {#considerations}

Se sua página contém várias mboxes e apenas algumas usam 3rdPartyID, o Target não tem um perfil/contexto de visitante separado para cada solicitação de visitante. O contexto 3rdPartyID tem prioridade sobre o contexto PCID. Basta que uma mbox passe 3rdPartyId para que seu contexto tenha prioridade sobre PCID.

Por exemplo, suponha que um visitante acesse uma página antes de fazer logon e veja uma experiência. A mbox global não usa 3rdPartyID. Depois de fazer logon, o visitante visualiza uma das três experiências com mboxes secundárias, algumas das quais usam 3rdPartyID. O visitante visita várias páginas no site e usa o botão Voltar para retornar à página principal acessada antes de fazer logon e visualizar uma experiência diferente. Nesse cenário, a mbox global não passou por 3rdPartyID, mas uma ou mais mboxes secundárias passaram. 3rdPartyID teve prioridade sobre PCID.
