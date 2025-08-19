---
keywords: mbox;mbox3rdPartyId;sincronização de perfil;sincronização de perfil;PCID
description: Saiba como usar a mbox3rdPartyId, que é a ID de visitante da sua empresa, como a ID de associação ou o programa de fidelidade da sua empresa.
title: Como utilizar a sincronização de perfil em tempo real para mbox3rdPartyId?
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: 152257a52d836a88ffcd76cd9af5b3fbfbdc0839
workflow-type: tm+mt
source-wordcount: '734'
ht-degree: 80%

---

# Sincronização de perfil em tempo real para mbox3rdPartyId

A `mbox3rdPartyId` no [!DNL Adobe Target] é a ID de visitante da sua empresa, como a ID de associação do programa de fidelidade da empresa.

Quando um visitante faz logon no site de uma empresa, a empresa normalmente cria uma ID associada à conta, ao cartão de fidelidade, ao número de associado ou a outros identificadores aplicáveis do visitante dessa empresa.

Quando um visitante acessa uma página em que o [!DNL Target] está ativado, esse visitante recebe uma PCID do [!DNL Target]. Se o visitante fizer logon e a implementação transmitir a `mbox3rdPartyId` para o [!DNL Target], o [!DNL Target] conectará a `mbox3rdPartyId` desse visitante à PCID do [!DNL Target].

As atualizações são sincronizadas com a loja de perfis a cada 5-10 minutos. Quando a sessão do visitante terminar, os dados mesclados substituirão os dados anteriores associados ao `mbox3rdPartyId`, criando um registro completo das ações desse visitante. Se o mesmo atributo existir em ambas as IDs, por exemplo, a PCID tem category=hats e a `mbox3rdPartyId` tem category=skis, ou se o visitante visualizar a experiência A antes de fazer logon, mas a experiência B está armazenada na `mbox3rdPartyId`, o atributo armazenado na `mbox3rdPartyId` substitui o atributo da PCID. Se o visitante estava em uma atividade ou experiência antes de fazer logon, mas uma atividade e uma experiência diferente está armazenada na `mbox3rdPartyId`, esse visitante é colocado na atividade e na experiência da `mbox3rdPartyId` após o logon.

| PCID (sem logon) | mbox3rdPartyId (com logon) | Mesclado e salvo em mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|   | store=94103 | store=94103 |
| Atividade 1, experiência A | Atividade 1, experiência B | Atividade 1, experiência B |
| Atividade 1 |  | Atividade 1 |

Quando o visitante faz logoff, o perfil mesclado é mantido.

>[!NOTE]
>
>Se você deseja distinguir usuários autenticados (conectados) de usuários não autenticados, use o [!DNL Adobe Experience Cloud Identity Service] (ECID) no lugar da mbox3rdPartyID. Depois que um usuário é associado à mbox3rdPartyID, ela permanece associada ao usuário mesmo após desconectar.

>[!NOTE]
>
>As metas do [!DNL Adobe Analytics] não são rastreadas nos casos em que a ID do [!DNL Adobe Experience Cloud] (ECID) é alterada (por exemplo, o visitante muda os dispositivos), embora o perfil do [!DNL Target] possa ser combinado com base na mbox3rdPartyId e ainda ter informações de atividade. Para visitantes identificados com a mesma ECID (aqueles que acessam a página com o mesmo dispositivo), o [!DNL Analytics for Target] (A4T) deve funcionar conforme esperado.

## Considerações {#considerations}

* Se a página contiver várias mboxes e somente algumas usarem a `3rdPartyID`, o [!DNL Target] não terá um perfil do visitante/contexto separado para cada solicitação do visitante. O contexto da `3rdPartyID` tem prioridade sobre o contexto da PCID. Basta que uma mbox transmita a `3rdPartyId` para que o contexto tenha prioridade sobre a PCID.

  Por exemplo, suponha que um visitante acesse uma página antes de fazer logon e visualize uma experiência. A mbox global não usa a `3rdPartyID`. Depois de fazer logon, o visitante visualiza uma das três experiências com mboxes filhas, sendo que algumas usam a `3rdPartyID`. O visitante visita várias páginas no site e usa o botão Voltar para retornar à página principal acessada antes de fazer logon e visualizar uma experiência diferente. Neste cenário, a mbox global não transmitiu a `3rdPartyID`, mas uma ou mais mboxes filhas transmitiram. A `3rdPartyID` teve prioridade sobre a PCID.

* Você pode enviar as IDs de cliente dos visitantes para o [!DNL Target] usando duas abordagens:

   1. Use `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` é o nome do parâmetro ao usar `targetPageParams` ou `targetPageParamsAll`
      * `thirdPartyId` é o nome do parâmetro definido diretamente na carga da API de entrega.
      * Você pode enviar apenas um valor neste parâmetro.

   1. Use a função `setCustomerId`/`customerIds` do serviço ECID.

      * `setCustomerId` é uma função que você pode usar em implementações do lado do cliente (navegador) quando VisitorAPI.js estiver disponível na página.
      * `customerIds` é o nome do parâmetro usado ao defini-lo diretamente na carga da API de entrega e geralmente é feito em implementações do lado do servidor ou de IOT (Internet das coisas).
      * Ao contrário da `mbox3rdPartyId`/`thirdPartyId`, você pode enviar várias IDs como uma lista nesta abordagem, mas como o [!DNL Target] suporta apenas uma única ID de cliente por TnT Id, ele usa a primeira ID na lista com um alias conhecido (alias configurado na interface do usuário de atributos do cliente).

  Você pode usar o `mbox3rdPartyId`/`thirdPartyId` se [!DNL Target] for sua única solução do [!DNL Adobe Experience Cloud] e não quiser usar os Atributos do cliente. Para todos os outros casos, recomendamos que você use o `setCustomerId`/`customerIds` para enviar suas IDs de cliente.

  >[!IMPORTANT]
  >
  > Usar as duas abordagens mencionadas acima alternadamente para um único visitante pode resultar em mesclagens incorretas dos perfis autenticados e não autenticados do [!DNL Target].
  >
  >A Adobe não recomenda usar `mbox3rdPartyId`/`thirdPartyId` e `setCustomerID`/`customerIds` juntos.
  >
  >Se você precisar usar ambas as abordagens alternadamente, verifique se a primeira ID na lista usada por `setCustomerID`/`customerIds` é a mesma usada por `thirdPartyId`/`mbox3rdPartyId` e vice-versa.

