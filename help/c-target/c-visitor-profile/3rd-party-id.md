---
keywords: mbox; mbox3rdPartyId; sincronização de perfil; sincronização de perfil; PCID
description: Saiba como usar a mbox3rdPartyId, que é a ID de visitante de sua organização, como a ID de associação ou o programa de fidelidade de sua organização.
title: Como uso a sincronização de perfil em tempo real para mbox3rdPartyId?
feature: Audiences
exl-id: ed409225-fa35-49da-87d1-1770221f2ae0
source-git-commit: f4b490c489427130e78d84b573b2d290a8a60585
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 24%

---

# Sincronização de perfil em tempo real para mbox3rdPartyId

O `mbox3rdPartyId` em [!DNL Adobe Target] é a ID de visitante de sua empresa, como a ID de associação do programa de fidelidade de sua empresa.

Quando um visitante faz logon no site de uma empresa, a empresa normalmente cria uma ID associada à conta, ao cartão de fidelidade, ao número de associado ou a outros identificadores aplicáveis do visitante dessa empresa.

Quando um visitante acessa uma página em que o [!DNL Target] está ativado, esse visitante recebe uma PCID do [!DNL Target]. Se o visitante fizer logon e a implementação transmitir `mbox3rdPartyId` para [!DNL Target], [!DNL Target] conectará `mbox3rdPartyId` desse visitante à PCID [!DNL Target].

A cada intervalo de 3 a 5 minutos, as atualizações são sincronizadas com o banco de dados. Quando o visitante faz logoff, os dados mesclados substituem os dados anteriores associados ao `mbox3rdPartyId`, criando um registro completo das ações desse visitante. Se o mesmo atributo existir em ambas as IDs, por exemplo, a PCID tem category=hats e a `mbox3rdPartyId` tem category=skis, ou se o visitante viu a experiência A antes de fazer logon, mas a experiência B é armazenada no `mbox3rdPartyId`, o atributo armazenado no `mbox3rdPartyId` substitui o atributo da PCID. Se o visitante estava em uma atividade ou experiência antes de fazer logon, mas uma atividade e uma experiência diferentes são armazenadas no `mbox3rdPartyId`, esse visitante é colocado na atividade e na experiência `mbox3rdPartyId` após o logon.

| PCID (sem logon) | mbox3rdPartyId (com logon) | Mesclado e salvo em mbox3rdPartyId |
|---|---|---|
| category=hats | category=skis | category=skis |
|  | store=94103 | store=94103 |
| Atividade 1, experiência A | Atividade 1, experiência B | Atividade 1, experiência B |
| Atividade 1 |  | Atividade 1 |

Quando o visitante faz logoff, o perfil mesclado é mantido.

>[!NOTE]
>
>Se você deseja distinguir entre usuários autenticados (conectados) versus usuários não autenticados, use o [!DNL Adobe Experience Cloud Identity Service] (ECID) em vez de mbox3rdPartyID. Depois que um usuário é associado a mbox3rdPartyID, ele permanece associado ao usuário mesmo depois de sair.

>[!NOTE]
>
>[!DNL Adobe Analytics] As metas do não são rastreadas nos casos em que a  [!DNL Adobe Experience Cloud] ID (EDID) do é alterada (por exemplo, o visitante muda os dispositivos), mesmo que o  [!DNL Target] perfil do possa ser mesclado com base na mbox3rdPartyId e ainda ter informações de atividade. Para visitantes identificados com o mesmo EDID (aqueles que acessam a página com o mesmo dispositivo), [!DNL Analytics for Target] (A4T) deve funcionar conforme esperado.

## Considerações {#considerations}

* Se a página contiver várias mboxes e apenas algumas usam `3rdPartyID`, [!DNL Target] não terá um perfil/contexto de visitante separado para cada solicitação de visitante. O contexto `3rdPartyID` tem prioridade sobre o contexto PCID. Basta que uma mbox transmita `3rdPartyId` para que seu contexto tenha prioridade sobre PCID.

   Por exemplo, suponha que um visitante acesse uma página antes de fazer logon e visualizar uma experiência. A mbox global não usa a `3rdPartyID`. Depois de fazer logon, o visitante visualiza uma das três experiências com mboxes secundárias, sendo que algumas usam a `3rdPartyID`. O visitante visita várias páginas no site e usa o botão Voltar para retornar à página principal acessada antes de fazer logon e visualizar uma experiência diferente. Neste cenário, a mbox global não transmitiu `3rdPartyID`, mas uma ou mais mboxes secundárias transmitiram. `3rdPartyID` prioridade sobre PCID.

* Você pode enviar as IDs do cliente dos visitantes para [!DNL Target] usando duas abordagens:

   1. Use `mbox3rdPartyId`/`thirdPartyId`.

      * `mbox3rdPartyId` é o nome do parâmetro ao usar  `targetPageParams` ou  `targetPageParamsAll`
      * `thirdPartyId` é o nome do parâmetro definido diretamente na carga da API de entrega.
      * Você pode enviar apenas um valor neste parâmetro.
   1. Use a função `setCustomerId`/`customerIds` do Serviço ECID.

      * `setCustomerId` é uma função que você pode usar em implementações do lado do cliente (navegador) quando VisitorAPI.js estiver disponível na página.
      * `customerIds` é o nome do parâmetro usado ao defini-lo diretamente na carga da API de entrega e geralmente é feito em implementações do lado do servidor ou IOT (Internet das coisas).
      * Ao contrário de `mbox3rdPartyId`/`thirdPartyId`, você pode enviar várias IDs como uma lista nesta abordagem, mas como [!DNL Target] suporta apenas uma única ID de cliente por TnT Id, ele usa a primeira ID na lista com um alias conhecido (alias configurado na interface do usuário de atributos do cliente).

   >[!IMPORTANT]
   >
   > Usar as duas abordagens mencionadas acima alternadamente para um único visitante pode resultar em mesclagens de perfil incorretas dos perfis [!DNL Target] não autenticados e autenticados.
   >
   >O Adobe não recomenda usar `mbox3rdPartyId`/`thirdPartyId` e `setCustomerID`/`customerIds` juntos.
   >
   >Se você precisar usar ambas as abordagens alternadamente, verifique se a primeira ID na lista usada por `setCustomerID`/`customerIds` é a usada por `thirdPartyId`/`mbox3rdPartyId` e vice-versa.

