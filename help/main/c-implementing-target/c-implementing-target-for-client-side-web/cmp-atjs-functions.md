---
keywords: at.js; funções; biblioteca javascript
description: Exiba uma lista de funções que podem ser usadas com as versões 1.x e 2.x da biblioteca at.js de JavaScript no Adobe Target.
title: Quais funções posso usar com a at.js?
feature: at.js
role: Developer
exl-id: a386e478-16f4-4bf6-9771-6b1e75f2e362
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 65%

---

# Funções da at.js

Lista de funções que podem ser usadas com a biblioteca de JavaScript at.js do Adobe Target. Clique nos links na coluna Função para obter mais informações e exemplos.

| Função | Detalhes |
| --- | --- | 
| [adobe.target.getOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffer/){target=_blank} | Esta função envia uma solicitação para obter uma oferta do Target. Use com `adobe.target.applyOffer()` para processar a resposta ou use sua própria manipulação de sucesso. |
| [adobe.target.getOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-getoffers-atjs-2/){target=_blank}<br>(at.js 2.x) | Essa função permite que você recupere várias ofertas passando em várias mboxes. Além disso, várias ofertas podem ser recuperadas para todas as exibições em atividades ativas.<br>**Observação:** essa função foi introduzida com a at.js 2.x. Essa função não está disponível para a at.js versão 1.*x*. |
| [adobe.target.applyOffer(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffer/){target=_blank} | Esta função aplica o conteúdo de resposta. |
| [adobe.target.applyOffers(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-applyoffers-atjs-2/){target=_blank}<br>(at.js 2.x) | Essa função permite aplicar mais de uma oferta que foi recuperada por adobe.target.getOffers().<br>**Observação:** essa função foi introduzida com a at.js 2.x. Essa função não está disponível para a at.js versão 1.*x*. |
| [adobe.target.triggerView (viewName, opções)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-triggerview-atjs-2/){target=_blank}<br>(at.js 2.x) | Essa função pode ser chamada sempre que uma nova página é carregada ou quando um componente em uma página é renderizado novamente.<br> Essa função deve ser implementada para aplicativos de página única (SPA){target=_blank} para usar o Visual Experience Composer (VEC) para criar atividades de teste A/B e direcionamento de experiência (XT). |
| [adobe.target.trackEvent(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-trackevent/){target=_blank} | Essa função aciona uma solicitação para relatar ações do usuário, como cliques e conversões. Não entrega atividades na resposta. |
| [mboxCreate(mbox,params)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxcreate-atjs/){target=_blank}<br>(at.js 1.x) | Executa uma solicitação e aplica a oferta ao DIV mais próximo com o nome de classe mboxDefault.<br>**Observação:** essa função está disponível para a at.js versão 1.somente *x*. Essa função foi descontinuada pelo lançamento da at.js 2.x. Ela retorna o conteúdo padrão se for usada com a 2.x. |
| [mboxDefine(options) e mboxUpdate(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/mboxdefine-mboxupdate-atjs-1x/){target=_blank}<br>(at.js 1.x) | Defina e atualize um mbox.<br>**Observação:** essa função está disponível para a at.js versão 1.somente *x*. Essa função foi descontinuada pelo lançamento da at.js 2.x. Ela retorna o conteúdo padrão se for usada com a 2.x. |
| [targetGlobalSettings(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetglobalsettings/){target=_blank} | Você pode substituir as configurações na biblioteca at.js usando `targetGlobalSettings()`, em vez de definir as configurações na interface do usuário do Target Standard/Premium ou usar APIs REST.<ul><li>Provedores de dados: essa configuração permite que clientes reúnam dados de provedores de dados de terceiros, como Demandbase, BlueKai e serviços personalizados, além de passar os dados para o Target como parâmetros da mbox na solicitação global da mbox.</li></ul> |
| [targetPageParams(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparams/){target=_blank} | Este método permite anexar parâmetros ao mbox global de fora do código da solicitação. |
| [targetPageParamsAll(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/targetpageparamsall/){target=_blank} | Este método permite anexar parâmetros a todos os mboxes de fora do código da solicitação. |
| [registerExtension(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/registerextension-atjs-1x/){target=_blank}<br>(at.js 1.x) | Fornece uma forma padrão de registrar uma extensão específica.<br>**Observação:** essa função está disponível para a at.js versão 1.somente *x*. Essa função foi descontinuada pelo lançamento da at.js 2.x. Ela retorna o conteúdo padrão se for usada com a 2.x. |
| [Eventos personalizados da at.js](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/atjs-custom-events/){target=_blank} | Os eventos personalizados da at.js informam quando uma solicitação de mbox ou oferta falha ou é bem-sucedida. |
| [adobe.target.sendNotifications(options)](https://developer.adobe.com/target/implement/client-side/atjs/atjs-functions/adobe-target-sendnotifications-atjs-21/){target=_blank}<br>(at.js 2.1.0) | Esta função envia uma notificação para a borda do Target quando uma experiência é renderizada sem usar `adobe.target.applyOffer()` ou `adobe.target.applyOffers()`.<br>**Observação**: esta função foi introduzida na at.js 2.1.0 e estará disponível em todas as versões a partir da 2.1.0. |
