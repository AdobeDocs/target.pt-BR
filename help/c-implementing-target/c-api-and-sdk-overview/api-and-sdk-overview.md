---
description: Informações sobre as APIs de entrega do lado do servidor do Target, as APIs do Recommendations e o SDK do NodeJS.
keywords: lado do servidor; no lado do servidor; api; sdk; nodejs; node js; api de recomendações
seo-description: Informações sobre apis de entrega do lado do servidor do Adobe Target, apis do Recommendations e o NDK nodejs.
seo-title: Implementação do Adobe Target no servidor
solution: Target
title: 'Lado do servidor: implementação do Target'
topic: Recommendations
uuid: 21d321c7-3da4-44a2-a04f-1807cc2a893b
translation-type: tm+mt
source-git-commit: 385864d9daae19468c4557e51043d5b788924658

---


# Lado do servidor: implementação do Target{#server-side-implement-target}

Informações sobre [!DNL Adobe Target] apis de entrega do lado do servidor, apis de entrega em lote do servidor, apis do nodejs, [!DNL Target Recommendations] apis e [!DNL Target Classic] apis (descontinuado).

O processo a seguir ocorre em uma implementação do lado do servidor de [!DNL Target]:

1. Um dispositivo cliente faz uma solicitação para uma experiência por meio do seu servidor.
1. Seu servidor envia essa solicitação [!DNL Target]para.
1. [!DNL Target] envia a resposta para o servidor.
1. Seu servidor decide sobre qual experiência deve ser entregue ao dispositivo cliente para que ele seja renderizado.

A experiência não precisa ser exibida em um navegador; pode ser exibido em um email ou quiosque, por um assistente de voz ou por alguma outra experiência não visual ou dispositivo não baseado em navegador. Como seu servidor se situa entre o cliente e [!DNL Target], este tipo de implementação também é ideal se você precisar de maior controle e segurança, ou ter processos de backend complexos que você deseja executar em seu servidor.

A seção a seguir lista as várias APIs e o NDK nodejs, além de fornecer informações adicionais:

## APIs de entrega no lado do servidor

Link: [Apis de entrega no servidor](https://developers.adobetarget.com/api/#server-side-delivery)

`/rest/v1/mbox`

[!DNL Target]O permite que o aplicativo faça chamadas da mbox de qualquer navegador, dispositivo móvel ou até mesmo de outro servidor. A API de entrega do lado do servidor é projetada especificamente para se integrar [!DNL Target] a qualquer plataforma do servidor que faça chamadas HTTP/HTTPS.

Você pode usar a API para integrar o aplicativo personalizado com o [!DNL Target]. Isso é especialmente valioso para organizações que desejam fornecer direcionamento para um dispositivo IoT sem navegador, como uma TV conectada, um quiosque ou uma tela digital na loja.

Esse terminal pode retornar ofertas apenas para as mboxes comuns. Você também pode buscar conteúdo apenas para uma única mbox.

Essa API implementa recursos da mbox existentes de acordo com o RESTful.

Ela não processa cookies ou redireciona chamadas.

## APIs de entrega em lote no lado do servidor

Link: [Apis de entrega em lote do servidor](https://developers.adobetarget.com/api/#server-side-batch-delivery)

`/rest/v2/batchmbox`

A API de entrega em lote permite que o aplicativo solicite conteúdo para várias mboxes em uma única chamada. Ele também tem um modo de busca prévia que permite aos clientes como aplicativos móveis, servidores etc. para buscar conteúdo para várias mboxes em uma solicitação, armazená-lo localmente e notificar posteriormente [!DNL Target] quando o usuário visita essas mboxes.

Esse terminal pode retornar ofertas apenas para as mboxes comuns. Como você pode buscar conteúdo para várias mboxes, para fins de desempenho, faz mais sentido usar a API de mbox em lote. Ela evita a execução de várias solicitações HTTP, o que pode ser caro.

## SDK do NodeJS

Link: [Nodejs SDK](https://www.npmjs.com/package/@adobe/target-node-client)

Em termos de SDKs, atualmente temos apenas um, o SDK do NodeJS.

O SDK do NodeJS é um invólucro fino em torno do módulo HTTP / HTTPS principal do NodeJS. Em segundo plano, as APIs de SDK do NodeJS usam as mesmas APIs de APIs de entrega no lado do servidor.

Este é o mapeamento:

* `MarketingCloudClient.getOffer() \*- invokes \*/res/v1/mbox endpoint`
* `MarketingCloudClient.getOffers() \*- invokes \*/res/v2/batchmbox endpoint`

## [!DNL Target Recommendations] APIs

Link: [Apis do Target Recommendations](https://developers.adobetarget.com/api/recommendations)

As APIs do Recommendations permitem interagir programaticamente com os servidores de recomendações do Target. Essas APIs podem ser integradas a uma variedade de pilhas de aplicativos para executar funções que normalmente seriam realizadas por meio da interface do usuário.

## [!DNL Target Classic] APIs

A [!DNL Target Classic] interface do usuário e as apis foram descontinuadas. Para obter mais informações sobre como alternar para as APIs modernas do Target, consulte [Transição das APIs legadas do Target para o Adobe I/O](../../c-implementing-target/c-api-and-sdk-overview/target-api-documentation.md#concept_3A31E26C8FAF49598152ACFE088BD4D2).

>[!NOTE]
>As APIs de criação (nas quais você cria atividades, ofertas, públicos-alvo e assim por diante) não oferecem suporte para o CORS (Cross Origin Resource Sharing).

## Diferenças entre as APIs de entrega no lado do servidor e o SDK do NodeJS {#section_10336B7934F54CE98E35907A4748A4A4}

Muitos clientes estão confusos sobre as diferenças entre as APIs de entrega no lado do servidor e o SDK do NodeJS. Isto é especialmente verdadeiro quando se trata de desempenho.

As seguintes perguntas frequentes devem ajudá-lo a decidir qual usar:

**Quando usar APIs do lado do servidor &quot;básicas&quot; versus o SDK do NodeJS?**

Idealmente, se estiver usando o NodeJS como a tecnologia de back-end, o SDK do NodeJS será uma escolha natural. O SDK lida com muitos detalhes, como cookies, cabeçalhos, carga útil, entre outros. Isso permite focar no centro do aplicativo.

**Terei melhorias de desempenho com o uso do SDK do NodeJS?**

Infelizmente, não temos nenhum número de desempenho. No entanto, no geral, o SDK do NodeJS deve ter bom desempenho, graças à arquitetura orientada por eventos do NodeJS. Saiba que a maior parte do tempo é gasta no [!DNL Target] backend. O SDK do NodeJS faz muito pouco processamento. O SDK é basicamente responsável por empacotar uma [!DNL Target] solicitação e analisar [!DNL Target] uma resposta.
