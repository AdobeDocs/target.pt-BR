---
description: A mbox3rdPartyID é a ID de visitante de sua empresa, como a ID de associação do programa de fidelidade da empresa.
keywords: mbox, mbox3rdPartyID, sincronização de perfil, perfil sincronizado
seo-description: A mbox3rdPartyID é a ID de visitante de sua empresa, como a ID de associação do programa de fidelidade da empresa.
seo-title: Sincronização de perfil em tempo real para mbox3rdPartyID
solution: Target
title: Sincronização de perfil em tempo real para mbox3rdPartyID
topic: Padrão
uuid: a88353d1-36e8-48b2-9b5e-71ed437c5b99
translation-type: tm+mt
source-git-commit: 17f0612559bae335d261ebc7654bc5d7fe3c0d12

---


# Sincronização de perfil em tempo real para mbox3rdPartyID{#real-time-profile-syncing-for-mbox-rdpartyid}

A mbox3rdPartyID é a ID de visitante de sua empresa, como a ID de associação do programa de fidelidade da empresa.

Quando um visitante faz logon no site de uma empresa, a empresa normalmente cria uma ID associada à conta, ao cartão de fidelidade, ao número de associado ou a outros identificadores aplicáveis do visitante dessa empresa.

Quando um visitante acessa uma página na qual o Target está ativado, esse visitante recebe um PCID do Target. Em seguida, se o visitante faz logon e a implementação envia o mbox3rdPartyID para o Target, o Target conecta o mbox3rdPartyID desse visitante ao PCID do Target.

As atualizações são sincronizadas com o banco de dados a cada três a cinco minutos. Quando o visitante faz logout, os dados mesclados substituem os dados anteriores associados ao mbox3rdPartyID, criando um registro mais completo das ações desse visitante. Se o mesmo atributo existe em ambas as IDs, por exemplo, o PCID tem categoria &quot;chapéus&quot;, e o mbox3rdPartyID tem categoria &quot;esquis&quot;, ou se o visitante viu a experiência A antes de fazer logon, mas a experiência B está armazenada no mbox3rdPartyID, o atributo armazenado no mbox3rdPartyID substitui o atributo do PCID. Se o visitante estava em uma atividade ou experiência antes de fazer logon, mas uma atividade e uma experiência diferentes estão armazenadas no mbox3rdPartyID, esse visitante é colocado na atividade e na experiência do mbox3rdPartyID depois de fazer logon.

| PCID (não conectado) | mbox3rdPartyID (com logon) | Mesclado e salvo em mbox3rdPartyID |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Atividade 1, experiência A | Atividade 1, experiência B | Atividade 1, experiência B |
| Atividade 1 |  | Atividade 1 |

Quando o visitante faz logoff, o perfil mesclado é mantido.

>[!NOTE]
>
>[!DNL Adobe Analytics] as metas não serão rastreadas nos casos em que a [!DNL Adobe Experience Cloud] ID (MID) muda (por exemplo, o visitante que muda os dispositivos), embora o [!DNL Target] perfil possa ser mesclado com base no mbox 3 rdpartyid e ainda tem informações de atividade. Para visitantes identificados com a mesma MID (aqueles que acessam a página com o mesmo dispositivo), [!DNL Analytics for Target] (A 4 T) devem funcionar conforme esperado.
