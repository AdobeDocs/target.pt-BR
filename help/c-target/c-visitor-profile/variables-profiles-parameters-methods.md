---
description: Essa página relaciona perfis, variáveis e parâmetros úteis em scripts de perfil.
keywords: variáveis, perfis, parâmetros, perfis internos, métodos, variáveis de url, perfis geográficos, perfis de terceiros, variáveis da mbox, variáveis de campanha, atributos do cliente
seo-description: Essa página relaciona perfis, variáveis e parâmetros úteis em scripts de perfil.
seo-title: Glossário de variáveis e perfis
solution: Target
title: Glossário de variáveis e perfis
topic: Padrão
uuid: 9286467c-cbb5-42be-99c0-6687ffab0969
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Glossário de variáveis e perfis{#profile-and-variable-glossary}

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
| user.header | Todos os perfis `user.header` são incorporados nos dados do cabeçalho da solicitação de mbox |
| user.header('x-cluster-client-ip') | O endereço IP voltado para o público da conexão de rede do visitante.<br>É possível obter isso de várias maneiras, por exemplo [whatismyip.com](https://www.whatismyip.com/). O endereço IP não é o endereço NAT (endereço interno), que começa com 10., 192.168. ou 172. |
| user.header('host') | Nome do host do site |
| user.header('cookie') | Dados de cookie do visitante |
| user.header('user-agent') | Agente do usuário do navegador do visitante |
| user.header('accept-language') | Idioma do visitante |
| user.header('accept-encoding') | Codificação de caractere do visitante |
| user.header('accept') | Idioma e codificação de caractere do visitante |
| user.header('connection') | Conexão do servidor. Por exemplo: keep-live |
| user.header('referrer') | URL do site da página atual do visitante. Não funciona no Internet Explorer. |
| user.getLocal('param_name','value'); |  |
| user.setLocal('param_name','value'); |  |
| user.get('param_name') |  |
| user.parameter | Atributos de perfil persistentes criados a partir de scripts de perfil. Também faz referência a perfis de "sistema", como localização geográfica, contagem de visitas, etc. |
| profile.get('param_name') |  |
| profile.param('param_name'); |  |
| profile.parameter('parameter_name'); | Os parâmetros da mbox que são tornados persistentes devido ao seu prefixo profile. . |
| profile.browserTime | A hora do navegador local do visitante. Para a hora do sistema, crie um novo objeto de data no script de perfil |
| profile.averageDaysBetweenVisits |  |
| profile.sessionCount |  |
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
| mbox.param('param_name') |  |
| Parâmetros enviados automaticamente com cada solicitação:<ul><li>mbox.param('browserHeight')</li><li>mbox.param('browserTimeOffset')</li><li>mbox.param('browserWidth')</li><li>mbox.param('colorDepth')</li><li>mbox.param('mboxXDomain')</li><li>mbox.param('mboxTime')</li><li>mbox.param('screenHeight')</li><li>mbox.param('screenWidth')</li></ul> |
| Parâmetros enviados com as mboxes do pedido:<ul><li>mbox.param('orderId')</li><li>mbox.param('orderTotal')</li><li>mbox.param('productPurchasedId')</li></ul> |
| mbox3rdPartyId | Um parâmetro de mbox para sincronizar uma ID de cliente com a mboxPCID do Target. Uma ID de cliente é uma ID que sua empresa usa para rastrear visitantes, como uma ID de CRM, uma ID de associação ou algo semelhante. Essa ID pode ser usada para adicionar informações por meio das APIs de perfil e [Atributos do cliente](/help/c-target/c-visitor-profile/working-with-customer-attributes.md). |
| mboxPageValue | Em cada chamada de mbox, a página recebe um valor. |
| mboxDebug | Usado somente para depurar informações. Adicionado ao url da página em que a mbox.js procura isso. |
| mboxOverride.browserIp | Define uma geografia diferente do local real para que seja possível testar como algo seria em outro local.<br>**Observação:** os parâmetros mboxOverride devem ser usados somente durante o teste da atividade e não em produção. O uso de qualquer parâmetro mboxOverride pode causar discrepâncias no relatório ao usar o [Analytics para Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T). Você deve usar o [modo de QA da atividade](/help/c-activities/c-activity-qa/activity-qa.md) durante o teste para garantir que sua atividade funciona como o esperado antes de enviar a atividade para o ambiente ativo. |

## Atributos do cliente {#section_62B4821EB6564FF4A14159A837AD4EDB}

Os atributos do cliente podem ser referenciados em scripts de perfil, formatados como `crs.get('<Datasource Name>.<Attribute name>')`.

Esses atributos também ficam disponíveis como tokens em scripts de perfil e diretamente em ofertas, sem exigir primeiramente um script de perfil. O token deve estar no formato: `$crs.datasourceName.attributeName`.
