---
keywords: versões da at.js; versões da at.js; notas de versão
description: Veja os detalhes sobre as alterações em cada versão da biblioteca JavaScript do Adobe [!DNL Target] at.js .
title: O que está incluído em cada versão da at.js?
feature: at.js
role: Developer
source-git-commit: f028d2b439fee5c2a622748126bb0a34d550a395
workflow-type: tm+mt
source-wordcount: '4143'
ht-degree: 89%

---


# Detalhes da versão da at.js

Detalhes sobre alterações em cada versão da biblioteca at.js de JavaScript do [!DNL Adobe Target].

>[!IMPORTANT]
>
>A equipe do Target é compatível com o at.js 1.*x* e at.js 2.*x*. Atualize para a atualização mais recente de qualquer versão principal do at.js para garantir que você esteja executando uma versão compatível.
>
>[Adobe Experience Platform ](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md) Launch é o método preferido para atualizar a at.js. Os desenvolvedores de extensão adicionam continuamente novos recursos a suas extensões e corrigem erros com frequência. Essas atualizações são colocadas em novas versões de uma extensão e disponibilizadas no catálogo [!DNL Launch] como atualizações. Para obter mais informações, consulte [Atualização de extensão](https://experienceleague.adobe.com/docs/launch/using/reference/manage-resources/extensions/extension-upgrade.html) no *Guia do Usuário do Experience Platform Launch*.

## at.js 2.5.0 (13 de maio de 2021)

Essa versão da at.js inclui os seguintes aprimoramentos e alterações:

* [Suporte à decisão no dispositivo](/help/c-implementing-target/c-implementing-target-for-client-side-web/on-device-decisioning/on-device-decisioning.md) para at.js.
* [Suporte a links de pré-visualização](/help/c-activities/c-activity-qa/activity-qa.md) para atividade de Automated Personalization

Esta versão também remove o suporte ao Microsoft Internet Explorer 10 e versões posteriores.

## at.js 2.4.1 (23 de março de 2021)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* Correção de um problema em que `targetPageParams` era incluído nas solicitações da mbox. `targetPageParams` deve ser incluído somente em solicitações `pageLoad`. (TNT-40247)
* Janela otimizada e global de documentos que fazem referência à extensão [!DNL Adobe Experience Platform Launch]. (TNT-37124)

## at.js 2.4.0 (14 de janeiro de 2021)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* Adiciona suporte para id de perfil/plataforma unificada para API de entrega de customerIds.
* Corrige a injeção de tag de estilo inválida.

## at.js 2.3.3 (13 de novembro de 2020)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* Correção de um problema relacionado ao rastreamento de cliques de mbox e ao A4T. Com o clique de 0, o Target acionou uma chamada de API de entrega com os parâmetros mbox e mbox corretos. No entanto, a SDID não correspondeu à chamada [!DNL Analytics], portanto, não houve agrupamento e conversão de ocorrência. (TNT-38372)

## at.js 2.3.2 (24 de julho de 2020)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* Correção de um erro quando um script ou código adicionava uma propriedade padrão à janela ou ao documento.

## at.js 1.8.2 (15 de junho de 2020)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* Correção de um problema ao usar a substituição de CNAME e borda, at.js 1.O *x* pode criar o domínio do servidor incorretamente, o que resultou na falha da solicitação do [!DNL Target]. (TNT-35064)

## Versões 2.3.1 da at.js (15 de junho de 2020)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* A configuração `deviceIdLifetime` foi substituída por [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md). (TNT-36349)
* Correção de um problema ao usar a substituição de CNAME e borda, at.js 2.O *x* pode criar o domínio do servidor incorretamente, o que resultou na falha da solicitação do [!DNL Target]. (TNT-35065)
* Correção de um problema ao usar a extensão [!DNL Target] [!DNL Launch] v2 e a extensão [!DNL Adobe Analytics] [!DNL Launch], [!DNL Target] atrasava a chamada [!DNL Analytics] `sendBeacon`. (TNT-36407, TNT-35990, TNT-36000)

## at.js versão 2.3.0 (25 de março de 2020)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* Suporte à configuração da Política de segurança de conteúdo nas tags SCRIPT e STYLE anexadas ao DOM da página ao aplicar ofertas do Target entregues. Os clientes podem definir `targetGlobalSettings.cspScriptNonce` e `targetGlobalSettings.cspStyleNonce` para que a at.js possa definir o script correspondente e as funções de tag de estilo nas ofertas aplicadas. Consulte [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md) para obter mais detalhes.
* Correção de um problema ao compilar a at.js com o compilador do Google Closure para a implantação do Google Tag Manager.
* O cookie de verificação da at.js foi renomeado de `check` para `at_check` para evitar colisões com as implementações dos clientes.

## at.js versão 1.8.1 (25 de março de 2020)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

* O cookie de verificação da at.js foi renomeado de `check` para `at_check` para evitar colisões com as implementações dos clientes.

## at.js versão 2.2.0 (10 de outubro de 2019)

Essa versão da at.js inclui os seguintes aprimoramentos e correções:

* Correção de um problema em que o rastreamento de cliques não relatava conversões no Analytics for Target (A4T) quando o código do Adobe Analytics não estava presente nos elementos da página.
* Desempenho aprimorado ao usar o Serviço de ID de Experience Cloud (ECID) v4.4 e o at.js 2.2 em suas páginas da Web.
* Anteriormente, a ECID fazia duas chamadas de bloqueio antes que a at.js pudesse buscar experiências. Isso foi reduzido a uma única chamada, o que melhora significativamente o desempenho.
* Correção de um processamento de exibição com busca prévia incorreto, no qual os tokens de evento das ofertas padrão não eram incluídos nas notificações enviadas.

   >[!NOTE]
   >
   >Atualize sua extensão do Launch ECID para v4.4 para aproveitar esse aprimoramento de desempenho.

* A at.js versão 2.2 também fornece uma nova configuração chamada `serverState`. Essa configuração pode ser usada para otimizar o desempenho da página quando uma integração híbrida do Target é implementada. A integração híbrida significa que você está usando a at.js v2.2+ no lado do cliente e a API de entrega ou um SDK do Target no lado do servidor para fornecer experiências. O `serverState` fornece ao at.js v2.2+ a capacidade de aplicar experiências diretamente de conteúdo buscado no lado do servidor e retornado ao cliente como parte da página que está sendo veiculada. Para obter mais informações, consulte &quot;serverState&quot; em [targetGlobalSettings](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#server-state).

## at.js versão 1.8.0 (10 de outubro de 2019)

Essa versão da at.js inclui os seguintes aprimoramentos e correções:

* Desempenho aprimorado ao usar o Serviço de Experience Cloud ID (ECID) v4.4 e o at.js 1.8 em suas páginas da Web.
* Anteriormente, a ECID fazia duas chamadas de bloqueio antes que a at.js pudesse buscar experiências. Isso foi reduzido a uma única chamada, o que melhora significativamente o desempenho.

>[!NOTE]
>
>Atualize sua extensão do Launch ECID para v4.4 para aproveitar esse aprimoramento de desempenho.

## at.js versão 2.1.1 (24 de julho de 2019)

Essa versão do at.js é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

(Os números de edição entre parênteses são para uso interno da Adobe.)

* Correção de um problema que fazia com que vários beacons fossem acionados ao usar a métrica de Rastreamento de cliques na página Metas e configurações no Visual Experience Composer (VEC). (TNT-32812)
* Correção de um problema que fazia com que o `triggerView()` não renderizasse ofertas mais de uma vez. (TNT-32780)
* Correção de um problema no `triggerView()` para garantir que a solicitação contivesse informações da Experience Cloud ID (ECID). (TNT-32776)
* Correção de um problema que impedia o acionamento da notificação do `triggerView()`, mesmo se não houvesse exibições salvas. (TNT-32614)
* Correção de um problema que causava um erro devido ao uso de decodeURIcomponent, que causava problemas quando o URL continha um parâmetro da sequência de consulta malformado. (TNT-32710)
* Agora o sinalizador de beacon é definido como “true” no contexto de solicitações de entrega enviadas por meio da API do `Navigator.sendBeacon()`. (TNT-32683)
* Correção de um problema que impedia que as ofertas do Recommendations fossem exibidas nos sites de alguns clientes. Os clientes podem ver o conteúdo da oferta na chamada da API de entrega, mas a oferta não foi aplicada no site. (TNT-32680)
* Correção de um problema que fazia com que o rastreamento de cliques em várias experiências não funcionasse como esperado. (TNT-32644)
* Correção de um problema que impedia o at.js de aplicar a segunda métrica após a falha da renderização da primeira métrica. (TNT-32628)
* Correção de um problema ao passar o `mboxThirdPartyId` usando a função do `targetPageParams` que fazia com que a carga da solicitação não estivesse presente nos parâmetros de consulta ou na carga da solicitação. (TNT-32613)
* Correção de um problema que fazia com que as respostas da notificação de cliques fossem bloqueadas nos navegadores Chromium (incluindo Google Chrome). (TNT-32290)

## at.js versão 2.1.0 (segunda-feira, 3 de junho de 2019)

Esta versão inclui os seguintes recursos e melhorias:

* **Suporte ao Adobe Opt-in**: o Adobe Opt-in é uma maneira de simplificar as integrações das soluções da Adobe com as plataformas de gerenciamento de consentimento. Para obter mais informações sobre o Adobe Opt-in, consulte [Privacidade e Regulamento Geral sobre a Proteção de Dados (GDPR)](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md).

* **Compatível com o CSP padrão do setor**: a at.js não usa mais eval() para executar o JavaScript.

* **Registro de análises do cliente**: forneça aos clientes controle total sobre como enviar dados de análise para o Adobe Analytics, seja no cliente ou no servidor.

   Para obter mais informações, consulte [Registro de análises no cliente](/help/c-integrating-target-with-mac/a4t/before-implement.md#client-side) em *Antes de implementar*.

* **Enviar notificações**: permite aos desenvolvedores enviar notificações quando uma experiência é renderizada pelo seu código em vez de usar `applyOffer()` ou `applyOffers()`.

   Para obter mais informações, consulte [adobe.target.sendNotifications(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe.target.sendnotifications-atjs-21.md).

* **Tamanho da at.js reduzido em ~24%**: o tamanho da at.js foi reduzido em ~24%. O tamanho de arquivo menor melhora o desempenho do carregamento da página e reduz o tempo para baixar a at.js na página.

## at.js versão 2.0.1 (terça-feira, 19 de março de 2019)

Essa é uma versão de manutenção e inclui os seguintes aprimoramentos e correções:

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

* Correção de uma condição de corrida no código de pesquisa DOM que causava exceções de JavaScript para determinados clientes. (TNT-31869)
* As notificações que renderizaram as exibições foram desassociadas dos manipuladores de eventos do rastreamento de cliques. Inicialmente, o Target não enviava notificações se os manipuladores de eventos de clique que pertenciam a uma exibição renderizada não pudessem ser anexados. O Target agora envia uma notificação de exibição mesmo se os elementos de clique não forem encontrados. (TNT-31969)
* Correção de um problema que fazia com que o sinalizador de redirecionamento do evento de solicitação sucedida fosse sempre definido como verdadeiro. (TNT-31907)
* Correção de um problema que fazia com que a ação de reorganizar do VEC fosse registrada como êxito, mesmo quando os elementos estavam ausentes. (TNT-31924)
* Correção de um problema que fazia com que as notificações de determinados clientes não contivessem o token de propriedade das Permissões empresariais. (TNT-31999)

## at.js versão 1.7.1 (terça-feira, 19 de março de 2019)

Essa é uma versão de manutenção e inclui a seguinte correção:

(Os números de edição entre parênteses são para uso interno da [!DNL Adobe].)

* Correção de uma condição de corrida no código de pesquisa DOM que causava exceções de JavaScript para determinados clientes. (TNT-31869)

## at.js versão 2.0.0 {#at-js-200}

A at.js 2.x fornece conjuntos de recursos avançados para sua empresa personalizar tecnologias de próxima geração no lado do cliente. Essa nova versão tem como foco a atualização da at.js para ter interações harmoniosas com aplicativos de página única (SPAs).

Estes são alguns benefícios do uso da at.js 2.x que não estão disponíveis nas versões anteriores:

* A capacidade de armazenar todas as ofertas em cache quando a página é carregada para reduzir o número de chamadas de servidor a apenas uma chamada.
* Melhore bastante as experiências dos usuários finais em seu site, uma vez que as ofertas são exibidas imediatamente por meio do cache, sem o atraso imposto pelas chamadas tradicionais do servidor.
* Uma linha de código simples e uma configuração de desenvolvedor única para permitir que seus profissionais de marketing criem e executem atividades A/B e Experience (XT) por meio do Visual Experience Composer (VEC) em seus aplicativos de página única.

A at.js 2.x apresenta as seguintes novas funções:

* getOffers()
* applyOffers()
* triggerView()

As seguintes funções foram descontinuadas com a introdução da at.js 2.x:

* mboxCreate()
* mboxDefine
* registerExtension()

Para obter mais informações, consulte [Atualização da at.js 1.x para at.js 2.x](/help/c-implementing-target/c-implementing-target-for-client-side-web/upgrading-from-atjs-1x-to-atjs-20.md) e [funções da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/cmp-atjs-functions.md).

>[!NOTE]
>
>Se você precisar de suporte do Adobe Opt-in para o [Regulamento Geral sobre a Proteção de Dados ](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md)(GDPR), use a at.js 1.7.0 ou 2.1.0.

## at.js versão 1.7.0 {#at-js-170}

O at.js 1.7.0 traz suporte à Adobe Opt-In. O Adobe Opt-In é uma maneira de simplificar as integrações das soluções da Adobe com as plataformas de gerenciamento de consentimento.

Para obter mais informações sobre o Adobe Opt-in, consulte [Privacidade e Regulamento Geral sobre a Proteção de Dados](/help/c-implementing-target/c-considerations-before-you-implement-target/c-privacy/cmp-privacy-and-general-data-protection-regulation.md) (GDPR).

Esta versão também corrige um problema em que o Target pode substituir parâmetros de URL de redirecionamento por parâmetros provenientes do URL de redirecionamento.

>[!NOTE]
>
>Se você precisar de suporte do Adobe Opt-in para o GDPR, use a at.js 1.7.0 ou 2.1.0.<br>Para obter uma lista de todas as versões, consulte [Detalhes de versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

## at.js versão 1.6.4 {#at-js-164}

O at.js 1.6.4 é uma versão de manutenção e aborda o seguinte problema:

* Correção de uma condição de corrida que se manifestava no Microsoft Internet Explorer 11 e que causava a aplicação de ofertas duplicadas.

## at.js versão 1.6.3 {#section_484A56774E004282B98FFFF851E4E670}

A versão 1.6.3 do at.js inclui as seguintes correções e aprimoramentos:

* Os seletores agora têm o CSS ignorado se contiverem IDs ou classes CSS que comecem com um dígito, dois hifens ou um hífen seguido de um dígito (por exemplo #-123). (TNT-31061)
* Correção de um problema introduzido na at.js 1.6.2 em que as ofertas do Visual Experience Composer (VEC) com diferentes atividades aplicáveis a um mesmo seletor CSS não respeitavam a prioridade das atividades. (TNT-31052)
* Correção de um problema de limite de tempo para promessas em ambientes em que não havia suporte nativo a promessas. (TNT-30974)
* Os problemas agora são capturados e relatados corretamente pelo evento de falha de renderização de conteúdo. Anteriormente, o JavaScript podia relatar uma execução bem-sucedida, mesmo que não fosse o caso. (TNT-30599)

## at.js versão 1.6.2 {#section_88BE2F69943D4280B8170F377886B58E}

Esta é uma versão de manutenção e aborda o seguinte problema:

* Corrigido um problema que, em alguns sites de clientes, resultava em um loop &quot;async&quot; infinito.

>[!IMPORTANT]
>
>Além disso, a versão 1.6.2 da at.js também contém todos os aprimoramentos e correções incluídos na versão 1.6.1 e 1.6.0 da at.js. Essas versões não estão mais disponíveis para download. Recomendamos que você atualize para a versão 1.6.2, se estiver usando a 1.6.1 ou 1.6.0

Aqui estão as melhorias e correções incluídas na at.js versão 1.6.1:

* Corrigido um problema na at.js 1.6.0 que fazia com que as recomendações fossem duplicadas no Microsoft Internet Explorer 11. (TNT-30593)
* A at.js agora garante que a lógica de substituição de borda verifique a existência de um cookie de cluster de borda para evitar um número de borda diferente se um usuário pular bordas durante uma sessão. (TNT-30563)
* Corrigido um problema que impedia a at.js de executar ações subsequentes se o conteúdo HTML contivesse um código JS inválido. A at.js agora registra o erro e renderiza as ações restantes sem problema. (TNT-30546)
* Foram feitas alterações para que haja uma exceção quando uma página de redirecionamento se requalificar para uma atividade de redirecionamento. (TNT-30532)
* Corrigido um problema que impedia que o tempo limite de solicitação correto fosse propagado da solicitação da API getOffer (). (TNT-30498)
* Corrigido um problema que impedia a at.js 1.6.0 de salvar cookies ao usar o protocolo de arquivo. (TNT-30454)
* Corrigido um problema que fazia com que nem todas as experiências fossem entregues com redirecionamentos ao usar o Analytics for Target (A4T). (TNT-30444)
* Corrigido um problema que fazia com que a página ficasse oculta após a chamada bem-sucedida do Target. (TNT-30358)

Aqui estão as melhorias e correções incluídas na at.js versão 1.6.0:

* As ofertas de redirecionamento agora são automaticamente compatíveis na integração do Analytics for Target (A4T). A solução alternativa do lado do cliente foi removida. (TNT-30247)
* O roteamento de borda do lado do cliente agora está ativado por padrão. (TNT-30261)
* Corrigido um problema com a renderização de ação do Visual Experience Composer (VEC) quando há dependências entre as ações. (TNT-30248)

## at.js versão 1.5.0 {#section_128C6761884C4DA8AE50D6A605FF6F55}

A at.js versão 1.5.0 já está disponível.

* Os detalhes do evento `at-request-succeeded` contêm sinalizador de redirecionamento. Esse sinalizador pode ser usado para determinar se a página será redirecionada a um URL diferente. Caso queira saber o URL, cadastre-se em `at-content-rendering-redirect`. (TNT-29834)
* Correção de um problema que fazia com que `window.targetGlobalSettings.enabled` falhasse com uma exceção de tempo de execução se fosse definido como false. (TNT-29829)
* Correção de um problema que fazia com que a página falhasse ao carregar o Visual Experience Composer (VEC) se estivesse usando o código personalizado para acionar uma solicitação de mbox global o usando ocultação do evento body. (TNT-29795)
* Suporte adicionado para `screenOrientation`, `devicePixelRatio`e `webGLRenderer`. Esses novos parâmetros de solicitação do Target são usados para detecção de iPhone X e outra detecção de dispositivo moderna. Para obter mais informações, consulte [Dispositivo móvel](/help/c-target/c-audiences/c-target-rules/mobile.md#concept_2A794199DC1A4D349FFFBC7DCF1FEB89). (TNT-29781)
* Correção de um problema em que a dica de localização do Adobe Audience Manager (AAM) não é sempre enviada. (TNT-29695)
* Em navegadores com suporte para isso, o at.js 1.5.0 é alternado para MutationObserver para polling de seletor. Versões anteriores ao at.js 1.0.0 usavam um polyfill MutationObserver, que se mostrou problemático. Para evitar problemas de polyfill, a versão 1.5.0 usa o seguinte pseudocódigo para decidir qual mecanismo de agendamento utilizar:

   ```
   if MutationObserver is supported
     scheduler = MutationObserver
   else if document is visible
     scheduler = requestAnimationFrame
   else
     scheduler = setTimeout
   ```

## at.js versão 1.3.0 {#section_24EAAE1CFA814EF8B19E61842F4D8321}

A at.js versão 1.3.0 já está disponível.

* Os seguintes novos eventos estão disponíveis para ajudar no rastreamento, depuração e personalização das interações com a at.js:

   * LIBRARY_LOADED
   * REQUEST_START
   * CONTENT_RENDERING_START
   * CONTENT_RENDERING_NO_OFFERS
   * CONTENT_RENDERING_REDIRECT

   Para obter mais informações, consulte [Eventos personalizados da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/atjs-custom-events.md).

* É possível aumentar uma solicitação de at.js com parâmetros adicionais provenientes de provedores de dados. Os provedores de dados devem ser adicionados a `window.targetGlobalSettings` sob o `dataProviders key`.

   Para obter mais informações, consulte [Provedores de dados](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

* As solicitações de at.js agora usam GET, mas mudam para POST quando o tamanho do URL excede 2048 caracteres. Existe uma nova propriedade chamada `urlSizeLimit`, na qual você pode aumentar o limite de tamanho, se necessário. Essa alteração permite que o Target alinhe a at.js ao AppMeasurement, que usa a mesma técnica.
* O Target agora reforça que a chave da `mbox` é usada na função `adobe.target.applyOffer(options)`. Essa chave era exigida anteriormente, mas o Target agora a aplica para garantir que tenha a validação adequada e que os clientes estejam usando a função corretamente.
* A at.js melhorou a funcionalidade de rastreamento de eventos e cliques. O at.js usa `navigator.sendBeacon()` para enviar dados de rastreamento de eventos e fallback para XHR síncrono quando `navigator.sendBeacon()` não é suportado. Esse fallback afeta, principalmente, o Internet Explorer 10 e 11 e algumas versões do Safari. O Safari adicionará suporte para `navigator.sendBeacon()` no próximo iOS versão 11.3.
* A at.js agora pode renderizar ofertas mesmo quando uma página é aberta em guias em segundo plano. Alguns clientes do Target encontraram um problema quando `requestAnimationFrame()` foi desativado devido ao comportamento de controle do navegador para guias em segundo plano.
* Esta versão adiciona muitas melhorias de desempenho, incluindo callstacks mais curtos ao inspecionar um perfil de CPU do Chrome.
* A at.js 1.3.0 não oferece mais suporte à entrega de conteúdo no Microsoft Internet Explorer 9. Para obter uma lista de navegadores compatíveis, consulte [Navegadores suportados](/help/c-implementing-target/c-considerations-before-you-implement-target/supported-browsers.md#reference_01B4BF99E7D545A7998773202A2F6100). A partir de agora, todas as solicitações serão executadas por `XMLHttpRequest` com suporte ao CORS sem solicitações JSONP. Essa alteração melhora muito a segurança.

## at.js versão 1.2.3 {#section_CE4D14AF00D04F4C8A2F0513F5EA1A84}

A [!DNL at.js] versão 1.2.3 já está disponível.

* Adiciona suporte para ofertas JSON. As ofertas JSON são suportadas apenas em atividades criadas usando o Experience Composer baseado em formulário. Atualmente, a única maneira de usar as ofertas do JSON é por meio de chamadas diretas à API. Consulte [Criar ofertas JSON](/help/c-experiences/c-manage-content/create-json-offer.md#concept_63C7BEE1F0DB4A7596D997219B7C136D).

## at.js versão 1.2.2 {#section_4E96D13F2DFE4F1F81A1089877D53649}

A [!DNL at.js] versão 1.2.2 já está disponível.

* Correção de um problema que retornava um erro de JavaScript quando a biblioteca do Target era carregada em uma página usando o modo QUIRKS. (TNT-28312)
* Correção de um problema que fazia com que o rastreamento de cliques no Target segmentasse as chamadas de coleta de dados do Analytics. (TNT-28261)
* Correção de um problema que causava a falha dos `getOffer() params` quando `targetPageParams()` retornava uma string em branco. (TNT-28359)
* Correção de um problema com geração da ID de sessão ao usar somente x. (TNT-28361)

## at.js versão 1.2.1 {#section_F757C8174BBA4F68AC5524ADC3D9C5E3}

A [!DNL at.js] versão 1.2.1 já está disponível.

* Correção de um problema no rastreamento de cliques em que um link com target=&quot;_blank&quot; impedia o Target de abrir o link em uma nova guia.

## at.js versão 1.2.0 {#section_1C3A18C595C34B25A14A440D213F3B9C}

A [!DNL at.js] versão 1.2 já está disponível como uma versão de manutenção que contém a maioria das correções de problemas.

* Correção de um problema que impedia ações padrão para casos especiais de rastreamento de cliques. (TNT-28089)
* Correção de um problema no rastreamento de cliques em que um link com `target="_blank"` impedia o Target de abrir o link em uma nova guia. (TNT-28072)
* Endereços IP podem ser usados como domínios de cookies. (TNT-28002)
* Correção de um problema que causava cintilação nas ofertas de redirecionamento com uma mbox global ou outras mboxes regionais. (TNT-27978)
* Correção de um problema que fazia a configuração da atividade de Direcionamento de experiência falhar no VEC ao alternar entre Procurar e Compor. (TNT-27942)
* Correção de tratamento incorreto em classes de estilo de cintilação para elementos de rastreamento de cliques. (TNT-27896)
* Correção de um problema que fazia com que os parâmetros globais da mbox se misturassem com todos os parâmetros da mbox. (TNT-27846)
* Alterações feitas para garantir que o Handlebars, o Mustache e outras bibliotecas de modelos do lado do cliente sejam manipuladas adequadamente pela [!DNL at.js]. (TNT-27831)
* Alterações feitas para garantir que `sdidParamExpiry` seja inicializado e passado corretamente para a API do visitante. Esta é uma regressão que foi adicionada à `at.js 1.1.0`. As versões anteriores da [!DNL at.js] não foram afetadas. Isso afeta apenas clientes que usam ofertas de redirecionamento e o A4T. (TNT-27791)
* Alterações feitas para garantir que `SCRIPT` seja executado, independentemente do atributo de tipo que está sendo usado. (TNT-27865)

## at.js versão 1.1.0 {#section_8F494E1EA94E48A9B169F5CF9FE6DC56}

**Data:** 2 de agosto de 2017

Os seguintes aprimoramentos e correções estão incluídos na [!DNL at.js] versão 1.1:

* Adição do tratamento de token de resposta. Para obter mais informações, consulte [Tokens de resposta](/help/administrating-target/response-tokens.md#concept_2B21B222F6A344D68CA5929817E836C4).
* Solução de um problema para que `document.currentScript polyfill` não interfira com o Angular 1.X.
* Alterações feitas para garantir que o rastreamento de cliques não interfira na propriedade de visibilidade. Os elementos de rastreamento de cliques são marcados com a classe CSS `at-element-click-tracking`, em vez de `at-element-marker`.

## at.js versão 1.0.0 {#section_37A3D23FC4AD42A68AA831B89E03E725}

**Data:** sexta-feira, 7 de julho de 2017

Os seguintes aprimoramentos e correções estão incluídos na at.js versão 1.0:

* Suporte para carregar a at.js de forma assíncrona para carregamentos de página mais rápidos.
* Suporte para pré-ocultar o conteúdo da página ao carregar a at.js de forma assíncrona.
* Mensagem de erro melhorada quando a entrega de conteúdo está desativada.
* Melhorias de desempenho ao entregar várias atividades.
* Suporte ao Compactador YUI.
* Relatório de erros para eventos personalizados durante a entrega da atividade.
* Correção para problemas de desempenho no Microsoft Internet Explorer 11.
* Correção para a função `getOffer()` que retornava um erro em alguns sites.
* Carregue a biblioteca do Target de forma assíncrona. Para obter mais informações, consulte [Perguntas frequentes da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-target-atjs-faq/target-atjs-faq.md#concept_D6EFE8D84A06476DB5ABD494D7E8C769).

## at.js versão 0.9.7 {#section_6C7B698BE21E40E495FD2850EFBF3E80}

**Data:** segunda-feira, 22 de maio de 2017

Os seguintes aprimoramentos e correções estão incluídos na [!DNL at.js] versão 0.9.7:

* Correção de um problema relacionado a uma chave de ativo que estava faltando nas ações `insertAfter` e `insertBefore` no Visual Experience Composer (VEC). Esses problemas estavam relacionados com a migração de ofertas visuais para modelos de ofertas.

## at.js versão 0.9.6 {#section_EEFA6413F2F947AD8C4A88128B90245D}

**Data:** quinta-feira, 13 de abril de 2017

Os seguintes aprimoramentos e correções estão incluídos na [!DNL at.js] versão 0.9.6:

* Suporte à oferta de redirecionamento para A4T. Depois de baixar e instalar a [!DNL at.js] versão 0.9.6, poderá usar as ofertas de redirecionamento nas atividades que usam o [!DNL Adobe Analytics] como Fonte dos relatórios para o [!DNL Target] (A4T). Além da [!DNL at.js] versão 0.9.6, há outros requisitos mínimos que sua implementação deve atender para usar as ofertas de redirecionamento e o A4T. Para obter mais informações e outras informações importantes que você deveria saber, consulte [Perguntas frequentes das Ofertas de redirecionamento - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md#concept_21BF213F10E1414A9DCD4A98AF207905).
* Antes da [!DNL at.js] 0.9.6, quando a API de visitante estava presente na página e a configuração `visitorApiTimeout` era muito agressiva, poderia ocorrer uma situação no em que nenhum dado MCID era enviado na solicitação do [!DNL Target]Target. Isso pode levar a problemas como ocorrências não corrigidas no [!DNL Analytics] ao usar o A4T.

   Este comportamento foi alterado na [!DNL at.js] 0.9.6, mesmo que `visitorApiTimeout` seja definido para 1 ms, o Target tentará coletar dados de SDID, servidores de rastreamento e IDs do cliente e enviá-los na solicitação.

* Adição da configuração `selectorsPollingTimeout`. Para obter mais informações, consulte [targetGlobalSettings()](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md).
* O formato do formulário de resposta de `getOffer()` foi alterado. Para obter mais informações, consulte [adobe.target.getOffer(options)](/help/c-implementing-target/c-implementing-target-for-client-side-web/adobe-target-getoffer.md).
* O registro do console foi adicionado para declarações `<!DOCTYPE>` não suportadas.
* Correção de um problema em que os plug-ins do [!DNL Target Classic] não eram aplicados corretamente quando várias ofertas padrão eram entregues a uma única mbox. (TGT-22664)
* Melhoria na configuração de cookies para dois domínios de alto nível (TLDs) para garantir que o cookie da mbox seja definido corretamente para esses domínios (por exemplo, [!DNL test.no] e [!DNL autodrives.ca] e assim por diante).
* O algoritmo para extrair o domínio de nível superior que deve ser usado ao salvar cookies foi alterado na at.js versão 0.9.6. Por causa dessa alteração, os cookies não pode ser salvos em endereços que usam IP. Na maioria das vezes, os endereços IP são usados para fins de teste, mas, como solução alternativa, é possível usar entradas de DNS ou ajustar o arquivo de hosts em uma caixa local.
* Correção das ações de mover e reorganizar quando as propriedades são valores de cadeia de caracteres em vez de números inteiros.

## at.js versão 0.9.4 {#section_A15B12F12CD94F07B3F56613A79A815F}

**Data:** quinta-feira, 19 de janeiro de 2017

* Os nomes das mboxes agora podem conter caracteres especiais, incluindo &quot;E&quot; comercial (&amp;), para ser consistente com os requisitos de nomenclatura das mboxes usando a mbox.js.

   Para obter uma lista de caracteres especiais permitidos, consulte [Configurações da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#concept_2FA0456607D04F82B0539C5BF5309812).

* Adição da configuração `secureOnly`, que indica se a at.js deve usar somente HTTPS ou pode alternar entre HTTP e HTTPS com base no protocolo da página. Esta é uma configuração avançada cujo padrão é Falso e pode ser substituída por `targetGlobalSettings`.
* A opção [!UICONTROL Suporte a navegador herdado] está disponível na at.js versão 0.9.3 e posteriores. Esta opção foi removida na at.js versão 0.9.4.

## at.js versão 0.9.3 {#section_DF13BC1D7C994AE7A36B81937A699DF4}

**Data:** segunda-feira, 10 de outubro de 2016

* Garante que as chamadas da mbox sejam acionadas no Microsoft Internet Explorer 11 quando os navegadores herdados estiverem desativados nas configurações da at.js.
* Garante que o conteúdo padrão seja renderizado se uma oferta remota dinâmica falhar (por exemplo, se o URL estiver incorreto e retornar um erro 404).
* Garante que os elementos sejam revelados rapidamente quando os seletores de rastreamento de cliques do VEC não puderem ser encontrados no DOM.

## at.js versão 0.9.2 {#section_148549CBB4F046BAA8F79C79B64EC889}

**Data:** quarta-feira, 21 de setembro de 2016

* Adição de uma configuração `optoutEnabled` para ativar ou desativar a não participação no Gráfico de dispositivos. Se essa configuração for definida como `true` e o visitante tiver desativado o rastreamento, o navegador do visitante não fará chamadas de mbox. O Gráfico de dispositivos está atualmente na versão beta. Esta configuração é definida para `false` por padrão, mas deve ser definido para `true` se você estiver usando o Gráfico de dispositivos.
* Adição do suporte a `CustomEvent` ao mecanismo de notificação. Anteriormente, o mecanismo de notificação de eventos da at.js não podia ser usado por meio das APIs DOM padrão, como `document.addEventListener()`. Agora você pode usar `document.addEventListener()` para assinar eventos at.js, como eventos de solicitação e eventos de renderização de conteúdo.
* Correção de um problema relacionado às ofertas criadas no Visual Experience Composer (VEC). Antes desta versão, o Target ocultava os seletores e os exibia apenas quando todos os seletores eram correspondidos. Na at.js 0.9.2, o Target exibe os seletores assim que correspondidos.

## at.js versão 0.9.1 {#section_DAFB99114D604CFB8416C1BC7DEEAEEE}

**Data:** quinta-feira, 14 de julho de 2016

* Fornece à at.js um tempo limite para o Serviço de ID de visitante, que é independente do tempo limite do próprio serviço.
* Corrige um problema na versão 0.9.0 que afetava as implementações que usavam at.js em algumas páginas e mbox.js em outras.
* Se você usar o Adobe Analytics como a fonte de relatórios da sua atividade, não será necessário especificar um servidor de rastreamento durante a criação da atividade usando a mbox.js versão 61 (ou posterior) ou a at.js versão 0.9.1 (ou posterior). A biblioteca at.js envia automaticamente os valores do servidor de rastreamento para [!DNL Target]. Durante a criação da atividade, é possível deixar o campo [!UICONTROL Servidor de rastreamento] em branco na página [!UICONTROL Metas e configurações].

## at.js versão 0.9.0 {#section_2981CC9792F245389B39BB5B69F84C4E}

**Versão do Target:** 16.6.1

**Data:** 23 de junho de 2016

* Corrige um problema de tela branca ao usar ofertas do VEC. Qualquer pessoa que utilize a [!DNL at.js] deve atualizar para esta nova versão.
* Nova API `registerExtension`.

   Esta nova API permite que os desenvolvedores acessem determinados módulos jQuery usados na [!DNL at.js] para desenvolver extensões (também conhecidos como plug-ins) para a biblioteca. Existem algumas implicações para essa alteração. Isso afeta apenas os usuários que usam esses recursos:

   * A API `getSettings()` () removida, mas a mesma funcionalidade está disponível usando `registerExtension()`.
   * A API `getTracking()` () removida, mas a mesma funcionalidade está disponível usando `registerExtension()`.

   * A extensões existentes (por exemplo, as extensões AngularJS) devem ser atualizadas para usar a abordagem `registerExtension()`.

* Nova API de notificação da at.js.

   O objetivo desse sistema de notificação é fornecer mais informações sobre o que a [!DNL at.js] está fazendo na página e quando há problemas. Um problema comum observado com o VEC: uma versão de TI altera a página, um seletor de VEC é interrompido e o teste para de fornecer conteúdo corretamente. Um objetivo desse sistema de notificação é tornar esse problema de entrega conhecido na página, para que os desenvolvedores possam acessar essas informações, transmiti-las para um sistema como o [!DNL Adobe Analytics] e enviar alertas aos proprietários do negócio, informando-os de que ocorreram problemas no teste.

* Novo método da API `targetGlobalSettings()`.

   Você pode substituir as configurações na biblioteca da at.js, em vez de configurar as configurações no [!DNL Target Standard/Premium UI]ou usando as apis REST.

## at.js versão 0.8.0 {#section_E1C7B08EC0494388A022C28A8B8FE807}

**Data:** 5 de maio de 2016.

Esta é a primeira versão oficial da biblioteca [!DNL at.js].

A [!DNL at.js] é uma nova biblioteca de implementação do [!DNL Target], projetada para implementações típicas da Web e aplicativos de página única.

[!DNL at.js] substitui [!DNL mbox.js] para implementações de [!DNL Adobe Target].

Entre outros benefícios, a [!DNL at.js] melhora o tempo de carregamento de página para implementação da Web, melhora a segurança e fornece opções de implementações melhores para aplicativos de página única.

A [!DNL at.js] contém os componentes que foram incluídos em [!DNL target.js]; portanto, [!DNL target.js] não é mais chamada.

Ao implementar a [!DNL at.js], esteja ciente do seguinte:

* As versões do Internet Explorer anteriores à 8 não são suportadas.
* A implementação assíncrona significa que integrações legadas, como [!DNL Test&Target] para o plug-in do [!DNL SiteCatalyst], podem não funcionar.
* [!DNL Target]Os plug-ins do que referenciam objetos e métodos da não são suportados.[!DNL mbox.js]
* Todas as chamadas ao [!DNL Target] são feitas por XMLHTTPRequest e o conteúdo é retornado por JSON.
