---
description: O mbox 3 rdpartyid é a ID de visitante da sua empresa, como a ID de associação do programa de fidelidade da sua empresa.
keywords: mbox; mbox 3 rdpartyid; sincronização de perfil; sincronização de perfil; PCID
seo-description: 'Informações sobre o perfil em tempo real '
seo-title: Sincronização de perfil em tempo real para mbox 3 rdpartyid no Adobe Target
solution: Target
title: Sincronização de perfil em tempo real para mbox 3 rdpartyid
topic: Padrão
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: f54dba622e449fb8dac44cb37ff711419f8eda4b

---


# Real-time profile syncing for mbox3rdPartyId{#real-time-profile-syncing-for-mbox-rdpartyid}

O mbox 3 rdpartyid é a ID de visitante da sua empresa, como a ID de associação do programa de fidelidade da sua empresa.

Quando um visitante faz logon no site de uma empresa, a empresa normalmente cria uma ID associada à conta, ao cartão de fidelidade, ao número de associado ou a outros identificadores aplicáveis do visitante dessa empresa.

When a visitor accesses a page on which [!DNL Target] is enabled, that visitor is assigned a [!DNL Target] PCID. If the visitor then logs in, and the implementation passes the mbox3rdPartyId to [!DNL Target], [!DNL Target] connects that visitor's mbox3rdPartyId with the [!DNL Target] PCID.

A cada intervalo de 3 a 5 minutos, as atualizações são sincronizadas com o banco de dados. Quando o visitante faz logout, os dados mesclados substituem os dados anteriores associados ao mbox 3 rdpartyid, criando um registro mais completo das ações do visitante. Se o mesmo atributo existir em ambas as IDs—por exemplo, a PCID possui categoria = chapéu e mbox 3 rdpartyid tem categoria = skis, ou se o visitante viu a experiência A antes de efetuar logon, mas a experiência B é armazenada no mbox 3 rdpartyid—o atributo armazenado no mbox 3 rdpartyid substitui o atributo pela PCID. Se o visitante estava em uma atividade ou experiência antes de fazer logon, mas uma atividade e uma experiência diferentes são armazenadas no mbox 3 rdpartyid, após o logon desse visitante ser colocado na atividade e experiência do mbox 3 rdpartyid.

| PCID (sem logon) | mbox 3 rdpartyid (conectado) | Mesclado e salvo em mbox 3 rdpartyid |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Atividade 1, experiência A | Atividade 1, experiência B | Atividade 1, experiência B |
| Atividade 1 |  | Atividade 1 |

Quando o visitante faz logoff, o perfil mesclado é mantido.

>[!NOTE]
>
>[!DNL Adobe Analytics] as metas não serão rastreadas nos casos em que a [!DNL Adobe Experience Cloud] ID (MID) muda (por exemplo, o visitante que muda os dispositivos), embora o [!DNL Target] perfil possa ser mesclado com base no mbox 3 rdpartyid e ainda tem informações de atividade. Para visitantes identificados com a mesma MID (aqueles que acessam a página com o mesmo dispositivo), o [!DNL Analytics for Target] (A4T) deve funcionar conforme esperado.

## Considerações {#considerations}

Se a página contiver várias mboxes e somente alguns usarem 3 rdpartyid, o Target não terá um perfil/contexto de visitante separado para cada solicitação de visitante. O contexto 3 rdpartyid tem prioridade sobre o contexto PCID. É suficiente para uma mbox passar 3 rdpartyid para que seu contexto tenha prioridade sobre PCID.

Por exemplo, suponha que um visitante acessa uma página antes de fazer logon e visualizar uma experiência. A mbox global não usa 3 rdpartyid. Depois de fazer logon, o visitante visualiza uma das três experiências com mboxes secundárias, sendo que alguns usam 3 rdpartyid. O visitante visita várias páginas no site e usa o botão Voltar para retornar à página principal acessada antes de fazer logon e visualizar uma experiência diferente. Neste cenário, a mbox global não passou 3 rdpartyid, mas uma ou mais mboxes secundárias. 3 Rdpartyid tem prioridade sobre PCID.
