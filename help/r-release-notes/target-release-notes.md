---
description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as mais recentes ou futuras [! Versões do DNL Adobe Target.
keywords: notas de versão
seo-description: Notas de versão que fornecem informações sobre recursos, melhorias e correções para as mais recentes ou futuras [! Versões do DNL Adobe Target.
seo-title: Notas de versão do Adobe Target (pré-lançamento)
solution: Target
title: Notas de versão do Target (pré-lançamento)
topic: Padrão
uuid: 35ecabbe-b8b4-479b-9266-4823c831d79a
translation-type: tm+mt
source-git-commit: f49c0c94afe6bf8aadbfb76930b57bf7cd5602dc

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 24 de julho de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos a alteração sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (24 de julho de 2019) {#tgt-19-7-1}

Esta versão inclui os seguintes novos recursos e melhorias:

| Recurso / Aprimoramento | Descrição |
| --- | --- |
| Aplicativo para dispositivos móveis do Visual Experience Composer | Um novo painel Modificações é exibido no VEC do aplicativo móvel que exibe os elementos configurados para rastreamento de cliques. (TGT-31741)<br> See [Set up click tracking in the Mobile App](/help/c-target-mobile-app/c-mobile-visual-experience-composer/set-up-click-tracking-in-the-mobile-vec.md). |
| ![Premium badgereelogations](/help/assets/premium.png)<br>em atividades de teste A/B e direcionamento de experiência (XT) | O status da oferta do Recommendations (algoritmo) é exibido na página Visão geral das atividades de teste A/B e XT que contêm ofertas do Recommendations. Os status incluem: Resultados prontos, Resultados não prontos e Falha do feed. (TGT-33649)<br>See [Recommendations as an offer](/help/c-recommendations/recommendations-as-an-offer.md#status). |
| Suporte de rastreamento entre domínios para at. js 2.0 + por meio da biblioteca da Experience Cloud ID (ECID) | Anteriormente, o rastreamento entre domínios não era compatível com o at. js 2.*x*. Com esta versão, os clientes que usam at. js 2.0 ou superior agora podem utilizar rastreamento entre domínios por meio da biblioteca ECID. A biblioteca ECID deve ser instalada na página juntamente com o at. js 2.0 ou superior para que o rastreamento entre domínios funcione. [A biblioteca da Experience Cloud ID 4.3.0 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) deve ser usada.<br>Consulte [Suporte de rastreamento entre domínios em at. js 2. x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md#cross-domain). |
| Suporte do Target para ITP 2.1 e ITP 2.2 da Apple por meio da biblioteca da Experience Cloud ID (ECID) 4.3 | Hoje, os clientes do Target podem reduzir o ITP 2.1 e ITP 2.2 da Apple aproveitando o programa de certificação CNAME da Adobe.<br>Com esta versão, o Target apresenta uma integração perfeita com a biblioteca ECID 4.3, que aproveita um cookie do lado do servidor para mitigar ITP 2.1 e ITP 2.2. É altamente recomendado que os clientes do Target implante [a biblioteca ECID 4.3 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) juntamente com a biblioteca javascript do Target para atenuar quaisquer versões futuras do ITP. A biblioteca ECID continuará a executar melhorias que fornecem uma solução robusta para as políticas de cookie que mudam constantemente, introduzidas pelos navegadores.<br>Consulte [Apple Intelligent Tracking Prevention (ITP) 2. x](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/apple-itp-2x.md). |

## at. js versão 2.1.1 (24 de julho de 24 19)

Esta versão do at. js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

(Os números de edição entre parênteses são para uso interno da Adobe.)

* Correção de um problema que fazia com que vários beacons fossem acionados ao usar a métrica de Rastreamento de cliques na página Metas e configurações no Visual Experience Composer (VEC). (TNT-32812)
* Fixed an issue that caused `triggerView()` to not render offers more than once. (TNT-32780)
* Fixed an issue with `triggerView()` to ensure that the request contains Marketing Cloud ID (MCID) information. (TNT-32776)
* Fixed an issue that prevented the `triggerView()` notification to fire even if there are no saved views. (TNT-32614)
* Correção de um problema que causava um erro devido ao uso de decodeuricomponent que causava problemas quando o URL continha um parâmetro de string de consulta malformado. (TNT-32710)
* The beacon flag is now set to "true" in the context of delivery requests sent via the `Navigator.sendBeacon()` API. (TNT-32683)
* Correção de um problema que impedia que as ofertas do Recommendations fossem exibidas em sites para alguns clientes. Os clientes podem ver o conteúdo da oferta na chamada da API de entrega, mas a oferta não foi aplicada no site. (TNT-32680)
* Correção de um problema que fazia com que o rastreamento de cliques em várias experiências não funcionasse como esperado. (TNT-32644)
* Correção de um problema que impedia o at. js de aplicar a segunda métrica depois que a renderização da primeira métrica falha. (TNT-32628)
* Fixed an issue when passing `mboxThirdPartyId` using the `targetPageParams` function that caused the request payload to not be present in either the query parameters or in the request payload. (TNT-32613)
* Correção de um problema que fazia com que as respostas de notificação de cliques e cliques fossem bloqueadas em navegadores Chromium (incluindo Google Chrome). (TNT-32290)

For information about this and previous versions of at.js, see [at.js version details](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

**Melhorias, correções e alterações**

* Correção de um problema que impedia que valores de exclusão nas atividades do Recommendations fossem apagados ao adicionar valores duplicados. (TGT-34996)
* Agora você pode remover um design em uma atividade do Recommendations da página de definição de metas (Etapa 2 do fluxo de trabalho guiado de três partes). Observe que para remover um design, deve haver mais de um design selecionado. (TGT-35118)
* Correção de um problema que impedia que cartões de critérios personalizados fossem carregados corretamente na interface do usuário do Target ou editassem-os. (TGT-35170)

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
