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
source-git-commit: 48d265feb329355f5aabe34a6a950d78df981966

---


# Notas de versão do Target (pré-lançamento){#target-release-notes-prerelease}

Estas notas de versão fornecem informações sobre recursos, aprimoramentos e correções para as versões mais recentes ou que serão lançadas em breve do [!DNL Adobe Target].

**Última atualização: 19 de julho de 2019**

>[!NOTE]
>
>Essas notas de versão contêm informações de pré-lançamento. As datas de lançamento, os recursos e outras informações estão sujeitos a alteração sem aviso prévio. Para ver informações sobre a versão atual, consulte [Notas de versão do Target](release-notes.md). As informações nessas páginas podem ser iguais ou diferentes, dependendo do tempo das versões.
>
>The issue numbers in parentheses are for internal [!DNL Adobe] use.

## Target Standard/Premium 19.7.1 (24 de julho de 2019) {#tgt-19-7-1}

Esta versão inclui os seguintes novos recursos e melhorias:

| Recurso / Aprimoramento | Descrição |
| --- | --- |
| Aplicativo para dispositivos móveis do Visual Experience Composer | Um novo painel Modificações é exibido no VEC do aplicativo móvel que exibe os elementos configurados para rastreamento de cliques. (TGT-31741) |
| ![Premium badgereelogations](/help/assets/premium.png)<br>em atividades de teste A/B e direcionamento de experiência (XT) | O status da oferta do Recommendations (algoritmo) é exibido na página Visão geral das atividades de teste A/B e XT que contêm ofertas do Recommendations. Os status incluem: Resultados prontos, Resultados não prontos e Falha do feed. (TGT-33649) |
| Suporte de rastreamento entre domínios para at. js 2.0 + por meio da biblioteca da Experience Cloud ID (ECID) | Anteriormente, o rastreamento entre domínios não era compatível com o at. js 2.*x*. Com esta versão, os clientes que usam at. js 2.0 ou superior agora podem utilizar rastreamento entre domínios por meio da biblioteca ECID. A biblioteca ECID deve ser instalada na página juntamente com o at. js 2.0 ou superior para que o rastreamento entre domínios funcione. [A biblioteca da Experience Cloud ID 4.3.0 +](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) deve ser usada. |
| Suporte do Target para ITP 2.1 e ITP 2.2 da Apple por meio da biblioteca da Experience Cloud ID (ECID) 4.3 | Hoje, os clientes do Target podem reduzir o ITP 2.1 e ITP 2.2 da Apple aproveitando o programa de certificação CNAME da Adobe. With this release, Target introduces a seamless integration with the ECID library 4.3, which leverages a server-side cookie to mitigate ITP 2.1 and ITP 2.2. It is highly recommended that Target customers deploy [ECID library 4.3+](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-release-notes.html) in conjunction with Target’s JavaScript library to mitigate any future ITP releases. A biblioteca ECID continuará a executar melhorias que fornecem uma solução robusta para as políticas de cookie que mudam constantemente, introduzidas pelos navegadores. |

## Informações de pré-lançamento {#section_7B9D4AAFC6A74388B9D7DEF0658D8B63}

Para receber notificações antecipadas sobre as melhorias futuras de produtos para o Target e outras soluções da Adobe Experience Cloud, inscreva-se para obter a Atualização prioritária de produtos da Adobe:

[https://www.adobe.com/subscription/priority-product-update.html](https://www.adobe.com/subscription/priority-product-update.html)
