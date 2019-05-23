---
description: Informações sobre as APIs de entrega do lado do servidor do Target, as APIs do Recommendations e o SDK do NodeJS.
keywords: lado do servidor; no lado do servidor; api; sdk; nodejs; node js; api de recomendações
seo-description: Informações sobre as APIs de entrega do lado do servidor do Target, as APIs do Recommendations e o SDK do NodeJS.
seo-title: Implementação do Target no lado do servidor
solution: Target
title: Implementação do Target no lado do servidor
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 845fdba274a5aef740ffd4787d36e62bd769942a

---


# Lado do servidor: implementação do Target{#server-side-implement-target}

Informações sobre APIs de entrega do lado do servidor do Target, APIs de entrega em lote do servidor, APIs do Target, APIs do Target Recommendations e APIs do Target Classic (descontinuado).

A seção a seguir lista as várias APIs e o NDK nodejs, além de fornecer informações adicionais:

## APIs de entrega no lado do servidor

Link: [Apis de entrega no servidor](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

O Adobe Target permite que o aplicativo faça chamadas da mbox de qualquer navegador, dispositivo móvel ou até mesmo de outro servidor. A APIs de entrega do lado do servidor é projetada especificamente para integrar o Adobe Target a qualquer plataforma do lado do servidor que faça chamadas HTTP/HTTPS.

Você pode usar a API para integrar o aplicativo personalizado com o Target. Isso é especialmente valioso para organizações que desejam fornecer direcionamento para um dispositivo IoT sem navegador, como uma TV conectada, um quiosque ou uma tela digital na loja.

Esse terminal pode retornar ofertas apenas para as mboxes comuns. Você também pode buscar conteúdo apenas para uma única mbox.

Essa API implementa recursos da mbox existentes de acordo com o RESTful.

Ela não processa cookies ou redireciona chamadas.

## APIs de entrega em lote no lado do servidor

Link: [Apis de entrega em lote do servidor](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

A API de entrega em lote permite que o aplicativo solicite conteúdo para várias mboxes em uma única chamada. Ela também possui um modo de pré-busca que permite que os clientes, como aplicativos móveis, servidores e outros, busquem conteúdo para várias mboxes em uma solicitação, armazenem em cache localmente e depois notifiquem o Target quando o usuário visitar essas mboxes.

Esse terminal pode retornar ofertas apenas para as mboxes comuns. Como você pode buscar conteúdo para várias mboxes, para fins de desempenho, faz mais sentido usar a API de mbox em lote. Ela evita a execução de várias solicitações HTTP, o que pode ser caro.

## SDK do NodeJS

Link: [Nodejs SDK](https://www.npmjs.com/package/@adobe/target-node-client)

Em termos de SDKs, atualmente temos apenas um, o SDK do NodeJS.

O SDK do NodeJS é um invólucro fino em torno do módulo HTTP / HTTPS principal do NodeJS. Em segundo plano, as APIs de SDK do NodeJS usam as mesmas APIs de APIs de entrega no lado do servidor.

Este é o mapeamento:

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## APIs do Target Recommendations

Link: [Apis do Target Recommendations](https://developers.adobetarget.com/api/recommendations)

As APIs do Recommendations permitem interagir programaticamente com os servidores de recomendações do Target. Essas APIs podem ser integradas a uma variedade de pilhas de aplicativos para executar funções que normalmente seriam realizadas por meio da interface do usuário.

## APIs do Target Classic

A interface do usuário e as APIs do Target Classic foram desativadas. Para obter mais informações sobre como alternar para as APIs modernas do Target, consulte [Transição das APIs legadas do Target para o Adobe I/O](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2).

>[!NOTE]
>As APIs de criação (nas quais você cria atividades, ofertas, públicos-alvo e assim por diante) não oferecem suporte para o CORS (Cross Origin Resource Sharing).

## Diferenças entre as APIs de entrega no lado do servidor e o SDK do NodeJS {#section_10336B7934F54CE98E35907A4748A4A4}

Muitos clientes estão confusos sobre as diferenças entre as APIs de entrega no lado do servidor e o SDK do NodeJS. Isto é especialmente verdadeiro quando se trata de desempenho.

As seguintes perguntas frequentes devem ajudá-lo a decidir qual usar:

**Quando usar APIs do lado do servidor &quot;básicas&quot; versus o SDK do NodeJS?**

Idealmente, se estiver usando o NodeJS como a tecnologia de back-end, o SDK do NodeJS será uma escolha natural. O SDK lida com muitos detalhes, como cookies, cabeçalhos, carga útil, entre outros. Isso permite focar no centro do aplicativo.

**Terei melhorias de desempenho com o uso do SDK do NodeJS?**

Infelizmente, não temos nenhum número de desempenho. No entanto, no geral, o SDK do NodeJS deve ter bom desempenho, graças à arquitetura orientada por eventos do NodeJS. Esteja ciente de que a maior parte do tempo é gasto no back-end do Target. O SDK do NodeJS faz muito pouco processamento. O SDK é basicamente responsável por empacotar uma solicitação e analisar uma resposta do Target.
