---
keywords: variáveis, perfis, parâmetros, perfis internos, métodos, variáveis de url, perfis geográficos, perfis de terceiros, variáveis da mbox, variáveis de campanha, atributos do cliente
description: Veja uma lista de vários perfis, variáveis e parâmetros úteis em scripts de perfil no Adobe Target.
title: Quais Perfis, Variáveis e Parâmetros São Usados no  [!DNL Target]?
feature: Audiences
exl-id: 96ef9a56-fe76-428e-a164-c01829fdf45d
source-git-commit: 4395caa7e40717c59067eaedff5e53776768eda9
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 67%

---

# Glossário de variáveis e perfis

Essa página relaciona perfis, variáveis e parâmetros úteis em scripts de perfil.

## Perfis incorporados {#section_2B694370003C4F8E8E29E0B2F6E52045}

| Perfil | Notas |
|--- |--- |
| user.activeActivities<br>user.activeCampaigns | Retorne a ID da campanha para todas as campanhas/atividades nas quais o usuário está, mesmo que ele não tenha interagido com a campanha/atividade na sessão atual. |
| user.pcId |  |
| user.sessionId |  |
| user.categoryAffinity |  |
| user.categoryAffinities | Retorne uma matriz das afinidades que um visitante preencheu |
| user.isFirstSession |  |
| user.isNewSession |  |
| user.daysSinceLastVisit |  |
| user.browser | O agente do usuário |
| user.browserType | Retorna o tipo de navegador, por exemplo, safari, chrome e assim por diante. |
| user.header | Todos os perfis `user.header` são incorporados nos dados do cabeçalho da solicitação de mbox |
| user.header(&#39;x-forwarded-for&#39;) | O endereço IP voltado para o público da conexão de rede do visitante.<br>Você pode obter isso de várias maneiras, por exemplo [whatismyip.com](https://www.whatismyip.com/). O endereço IP não é o endereço NAT (endereço interno), que começa com 10., 192.168. ou 172.<br>Observação: user.header(&#39;x-cluster-client-ip&#39;) foi descontinuado. |
| user.header(&#39;host&#39;) | Nome do host do site |
| user.header(&#39;cookie&#39;) | Dados de cookie do visitante |
| user.header(&#39;user-agent&#39;) | Agente do usuário do navegador do visitante |
| user.header(&#39;accept-language&#39;) | Idioma do visitante |
| user.header(&#39;accept-encoding&#39;) | Codificação de caractere do visitante |
| user.header(&#39;accept&#39;) | Idioma e codificação de caractere do visitante |
| user.header(&#39;connection&#39;) | Conexão do servidor. Por exemplo: keep-live |
| user.header(&#39;referrer&#39;) | URL do site da página atual do visitante. Não funciona no Internet Explorer. |
| user.getLocal(&#39;param_name&#39;); | Recupere o valor definido usando `user.setLocal`. |
| user.setLocal(&#39;param_name&#39;,&#39;value&#39;) | Crie valores de perfil persistentes em um script de perfil. Esses valores persistem como um script de perfil, mas você só tem acesso a ele dentro do script em que foi definido. |
| user.get(&#39;param_name&#39;) |  |
| user.parameter | Atributos de perfil persistentes criados a partir de scripts de perfil. Também faz referência a perfis de &quot;sistema&quot; como geolocalização, contagem de visitas etc. |
| profile.get(&#39;param_name&#39;) | A maneira correta de obter um parâmetro de perfil a ser usado em um script de perfil é o método profile.get(&#39;param_name&#39;). |
| profile.param(&#39;param_name&#39;); |  |
| profile.parameter(&#39;parameter_name&#39;); | Os parâmetros da mbox que são tornados persistentes devido ao seu prefixo profile. . |
| profile.browserTime | A hora do navegador local do visitante. Para a hora do sistema, crie um novo objeto de data no script de perfil |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
| profile.mobile.isTablet | O dispositivo do visitante é um tablet.<P>**OBSERVAÇÃO**: este perfil substitui o Navegador herdado obsoleto pela categoria de público-alvo do iPad. Consulte [Navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md#profile-scripts) para obter mais informações. |
| profile.mobile.isMobilePhone | O dispositivo do visitante é um telefone celular.<P>**OBSERVAÇÃO**: este perfil substitui o Navegador herdado obsoleto pela categoria de público-alvo do iPhone. Consulte [Navegador](/help/main/c-target/c-audiences/c-target-rules/browser.md#profile-scripts) para obter mais informações. |
| parameter= | Termo genérico para valores adicionais transmitidos com uma mbox, normalmente como pares de nome/valor. Não é persistente, a menos que tornado persistente com `profile.parameter` ou `user.parameter`. |

## Variáveis de URL {#section_8F25958273164EBAA6DC659302993FD3}

| `landing` | `referrer` | `page` |
|---|---|---|
| `landing.url` | `referrer.url` | `page.url` |
| `landing.domain` | `referrer.domain` | `page.domain` |
| `landing.protocol` | `referrer.protocol` | `page.protocol` |
| `landing.param` | `referrer.param` | `page.param` |
| `landing.query` | `referrer.query` | `page.query` |

## Perfis de operadora de celular e geografia {#section_08441DA42E7346918FBB345818854997}

* `profile.geolocation.country`
* `profile.geolocation.state`
* `profile.geolocation.city`
* `profile.geolocation.zip`
* `profile.geolocation.dma`
* `profile.geolocation.domainName`
* `profile.geolocation.ispName`
* `profile.geolocation.connectionSpeed`
* `profile.geolocation.mobileCarrier`
* `profile.geolocation.latitude`
* `profile.geolocation.longitude`

## Variáveis de mbox {#section_C42F0D33BD8044BE812FA0B7905CC0ED}

| Variável | Notas |
|--- |--- |
| `mbox.name` |  |
| mbox.param(&#39;param_name&#39;) |  |
| Parâmetros enviados automaticamente com cada solicitação:<ul><li>mbox.param(&#39;browserHeight&#39;)</li><li>mbox.param(&#39;browserTimeOffset&#39;)</li><li>mbox.param(&#39;browserWidth&#39;)</li><li>mbox.param(&#39;colorDepth&#39;)</li><li>mbox.param(&#39;mboxXDomain&#39;)</li><li>mbox.param(&#39;mboxTime&#39;)</li><li>mbox.param(&#39;screenHeight&#39;)</li><li>mbox.param(&#39;screenWidth&#39;)</li></ul> |
| Parâmetros enviados com as mboxes do pedido:<ul><li>mbox.param(&#39;orderId&#39;)</li><li>mbox.param(&#39;orderTotal&#39;)</li><li>mbox.param(&#39;productPurchasedId&#39;)</li></ul> |
| mbox3rdPartyId | Um parâmetro de mbox para sincronizar uma ID de cliente com a mboxPCID do Target. Uma ID de cliente é uma ID que sua empresa usa para rastrear visitantes, como uma ID de CRM, uma ID de associação ou algo semelhante. Essa ID pode ser usada para adicionar informações por meio das APIs de perfil e dos [Atributos do cliente](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/customer-attributes.html?lang=pt-BR){target=_blank}. |
| mboxPageValue | Em cada chamada de mbox, a página recebe um valor. |
| mboxDebug | Usado somente para depurar informações. Adicionado ao url da página em que o at.js procura isso. |
| mboxOverride.browserIp | Define uma geografia diferente do local real para que seja possível testar como algo seria em outro local.<br>**Observação:** os parâmetros mboxOverride devem ser usados somente durante o teste da atividade e não em produção. O uso de qualquer parâmetro mboxOverride pode causar discrepâncias no relatório ao usar o [Analytics para Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Você deve usar o [modo de QA da atividade](/help/main/c-activities/c-activity-qa/activity-qa.md) durante o teste para garantir que sua atividade funciona como o esperado antes de enviar a atividade para o ambiente ativo. |

## Atributos do cliente {#section_62B4821EB6564FF4A14159A837AD4EDB}

Os atributos do cliente podem ser referenciados em scripts de perfil, formatados como `crs.get('<Datasource Name>.<Attribute name>')`.

Esses atributos também ficam disponíveis como tokens em scripts de perfil e diretamente em ofertas, sem exigir primeiramente um script de perfil. O token deve estar no formato: `${crs.datasourceName.attributeName}`. Observe que os espaços em `datasourceName` devem ser removidos de qualquer chamada de API.
