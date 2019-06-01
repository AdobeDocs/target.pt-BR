---
description: Lista de funções que podem ser usadas com a at.js.
keywords: adobe.target.notificação; elemento; seletor; notificação; extensão
seo-description: Lista de funções que podem ser usadas com a biblioteca de JavaScript at.js do Adobe Target.
seo-title: Funções do Adobe Target at.js
solution: Target
subtopic: Introdução
title: Funções da at.js.
topic: Padrão
uuid: ec5f27a7-b22a-48c9-968c-9eb02830a2a6
translation-type: tm+mt
source-git-commit: 9c139e43a49082888ab560d7da8ef423842311d3

---


# Funções da at.js{#at-js-functions}

Lista de funções que podem ser usadas com a biblioteca de JavaScript at.js do Adobe Target. Clique nos links na coluna Função para obter mais informações e exemplos.

| Função | Detalhes |
| --- | --- | 
| [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md) | Esta função envia uma solicitação para obter uma oferta do Target. Use com `adobe.target.applyOffer()` para processar a resposta ou use sua própria manipulação de sucesso. |
| [adobe. target. getoffers (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffers-atjs-2.md)<br>(at. js 2. x) | Essa função permite que você recupere várias ofertas passando em várias mboxes. Além disso, várias ofertas podem ser recuperadas para todas as exibições em atividades ativas.<br>**Observação:** Esta função foi introduzida com at. js 2. x. Essa função não está disponível para o at. js versão 1.*x*. |
| [adobe.target.applyOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffer.md) | Esta função aplica o conteúdo de resposta. |
| [adobe. target. applyoffers (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-applyoffers-atjs-2.md)<br>(at. js 2. x) | Essa função permite aplicar mais de uma oferta recuperada por adobe. target. getoffers ().<br>**Observação:** Esta função foi introduzida com at. js 2. x. Essa função não está disponível para o at. js versão 1.*x*. |
| [adobe. target. triggerview (viewname, options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-triggerview-atjs-2.md)<br>(at. js 2. x) | Essa função pode ser chamada sempre que uma nova página é carregada ou quando um componente em uma página é renderizado novamente.<br> Essa função deve ser implementada para aplicativos de página única (spas) para usar o Visual Experience Composer (VEC) para criar atividades de teste A/B e direcionamento de experiência (XT). |
| [adobe.target.trackEvent(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-trackevent.md) | Essa função aciona uma solicitação para relatar ações do usuário, como cliques e conversões. Não entrega atividades na resposta. |
| [Mboxcreate (mbox, params)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxcreate-atjs.md)<br>(at. js 1. x) | Executa uma solicitação e aplica a oferta ao DIV mais próximo com o nome de classe mboxDefault.<br>**Observação:** Essa função está disponível para o at. js versões 1.somente *x*. Essa função foi substituída pelo lançamento do at. js 2. x. Essa função retorna o conteúdo padrão se for usado com o at. js 2. x. |
| [Mboxdefine (opções) e mboxupdate (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/mboxdefine-mboxupdate-atjs-1x.md)<br>(at. js 1. x) | Defina e atualize um mbox.<br>**Observação:** Essa função está disponível para o at. js versões 1.somente *x*. Essa função foi substituída pelo lançamento do at. js 2. x. Essa função retorna o conteúdo padrão se for usado com o at. js 2. x. |
| [Targetglobalsettings (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) | Você pode substituir as configurações na biblioteca do at. js usando `targetGlobalSettings()`, em vez de configurar as configurações na interface do usuário do Target Standard/Premium ou usando apis REST.<ul><li>Provedores de dados: Essa configuração permite que os clientes coletem dados de provedores de dados de terceiros, como Demandbase, bluekai e serviços personalizados, e passe os dados para o Target como parâmetros de mbox na solicitação de mbox global.</li></ul> |
| [Targetpageparams (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparams.md) | Este método permite anexar parâmetros ao mbox global de fora do código da solicitação. |
| [Targetpageparamsall (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetpageparamsall.md) | Este método permite anexar parâmetros a todos os mboxes de fora do código da solicitação. |
| [Registerextension (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/registerextension-atjs-1x.md)<br>(at. js 1. x) | Fornece uma forma padrão de registrar uma extensão específica.<br>**Observação:** Essa função está disponível para o at. js versões 1.somente *x*. Essa função foi substituída pelo lançamento do at. js 2. x. Essa função retorna o conteúdo padrão se for usado com o at. js 2. x. |
| [Eventos personalizados da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md) | Os eventos personalizados do at. js permitem saber quando uma solicitação de mbox ou oferta falha ou tem êxito. |
| [adobe. target. sendnotifications (opções)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md)<br>(at. js 2.1.0) | Esta função envia uma notificação para a borda do Target quando uma experiência é renderizada sem usar `adobe.target.applyOffer()` ou `adobe.target.applyOffers()`.<br>**Observação**: Esta função foi introduzida no at. js 2.1.0 e estará disponível para qualquer versão acima de 2.1.0. |

