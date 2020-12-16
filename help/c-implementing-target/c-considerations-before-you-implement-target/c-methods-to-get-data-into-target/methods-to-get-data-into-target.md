---
keywords: implement;implementing;setting up;setup;page parameter;tomcat;url encoded;in-page profile attribute;mbox parameter;in-page profile attributes;script profile attribute;bulk profile update API;single file update API;customer attributes;data providers;dataprovider;data provider
description: Informações sobre os vários métodos que você pode usar para inserir dados no Target, incluindo parâmetros de página, atributos de perfil na página, atributos de script de perfil, provedores de dados, a API de atualização de perfil em massa, a API de atualização de perfil único e atributos do cliente.
title: Métodos para colocar os dados no Target
feature: implementation general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '1936'
ht-degree: 96%

---


# Métodos para colocar os dados no Target{#methods-to-get-data-into-target}

Informações sobre os diferentes métodos que você pode usar para inserir dados no Target, incluindo parâmetros de página, atributos de perfil na página, atributos de perfil de script, provedores de dados, a API de atualização de perfil em massa, a API de atualização de perfil único e atributos do cliente.

## Parâmetros da página (também denominados &quot;parâmetros de mbox&quot;) {#section_5A297816173C4FE48DC4FE03860CB42B}

Os parâmetros de página são pares de nome/valor enviados diretamente pelo código de página que não são armazenados no perfil do visitante para uso futuro.

Os parâmetros de página são úteis para enviar dados de página adicionais ao Target, que não precisam ser armazenados no perfil do visitante para uso de direcionamento futuro. Esses valores são usados para descrever a página ou a ação que o usuário fez na página específica.

### Formato

Os parâmetros da página são enviados ao Target por uma chamada de servidor como par de nome/valor de cadeia de caracteres. Os nomes e valores do parâmetro são personalizáveis (embora alguns sejam &quot;nomes reservados&quot; para usos específicos).

Exemplos:

* `page=productPage`

* `categoryId=homeLoans`

### Exemplo de casos de uso

**Páginas do produto**: envia as informações sobre o produto específico exibido (esta é a forma de funcionamento do Recommendations)

**Detalhes do pedido**: envia a ID do pedido, orderTotal e assim por diante para a coleção de pedidos

**Afinidade de categorias**: envia informações visualizadas por categoria para o Target, gerando conhecimento da afinidade do usuário a determinadas categorias do site

**Dados de terceiros**: envia informações de fontes de dados de terceiros, como provedores de definição de direcionamento meteorológico, dados de conta (por exemplo, DemandBase), dados demográficos (por exemplo, Experiência) e muito mais.

### Benefícios do método

Os dados são enviados ao Target em tempo real, e podem ser usados na mesma chamada de servidor dos dados em que estão contidos.

### Avisos

* Precisa de atualização do código da página (diretamente ou por meio de um sistema de gerenciamento de tags).
* Se os dados precisarem ser usados para direcionamento em uma chamada de página/servidor subsequente, eles precisam ser traduzidos para um script de perfil.
* As sequências de caracteres podem conter somente os caracteres, conforme o padrão [Internet Engineering Task Force (IETF)](https://www.ietf.org/rfc/rfc3986.txt).

   Além dos mencionados no site do IETF, o Target permite os caracteres a seguir nas sequências de consulta:

   `&lt; > # % &quot; { } | \\ ^ \[\] \``

   O restante deve ser codificado em url. O padrão especifica o seguinte formato ( [https://www.ietf.org/rfc/rfc1738.txt](https://www.ietf.org/rfc/rfc1738.txt) ), conforme ilustrado abaixo:

   ![](assets/ietf1.png)

   Ou, a lista completa para simplicidade:

   ![](assets/ietf2.png)

### Exemplo de código

targetPageParamsAll (anexa os parâmetros a todas as chamadas de mbox na página):

`function targetPageParamsAll() { return "param1=value1&param2=value2&p3=hello%20world";`

targetPageParams (anexa os parâmetros ao mbox global na página):

`function targetPageParams() { return "param1=value1&param2=value2&p3=hello%20world";`

Parâmetros no código mboxCreate:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','param1=value1','param2=value2'); </script>`

### Links para informações relevantes

Recommendations: [implementação de acordo com o tipo de página](/help/c-recommendations/plan-implement.md#reference_DE38BB07BD3C4511B176CDAB45E126FC)

Confirmação do pedido: [rastreia conversões](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/implementing-target-without-a-tag-manager.md#task_E85D2F64FEB84201A594F2288FABF053)

Afinidade de categorias: [afinidade de categorias](/help/c-target/c-visitor-profile/category-affinity.md#concept_75EC1E1123014448B8B92AD16B2D72CC)

## Os atributos de perfil na página (também chamados &quot;atributos de perfil in-mbox&quot;){#section_57E1C161AA7B444689B40B6F459302B6}

Os atributos de perfil na página são pares de nome/valor enviados diretamente pelo código de página que são armazenados no perfil do visitante para uso futuro.

Os atributos de perfil na página permitem que os dados específicos do usuário sejam armazenados no perfil do Target para direcionamento e segmentação posteriores.

### Formato

Os atributos de perfil na página são enviados ao Target por uma chamada de servidor como par de nome/valor com o prefixo &quot;profile&quot;. antes do nome do Atributo.

Os nomes e valores do atributo são personalizáveis (embora alguns sejam &quot;nomes reservados&quot; para usos específicos).

Exemplos:

* `profile.membershipLevel=silver`
* `profile.visitCount=3`

### Exemplo de casos de uso

**Informações de login**: compartilha dados que não são PII (Informações de identificação pessoal) com o Target com base no login do usuário. Isso poderia ser um status de associação, histórico de pedido ou mais.

**Armazenar informações**: rastreia qual loja é a localização preferencial deste usuário.

**Interações anteriores**: rastreia o que o usuário fez no site antes para informar sobre personalizações futuras.

### Benefícios do método

Os dados são enviados ao Target em tempo real, e podem ser usados na mesma chamada de servidor dos dados em que são originados.

### Avisos

Precisa de atualizações do código da página (diretamente ou por meio de um sistema de gerenciamento de tags).

Os atributos e valores estão visíveis nas chamadas do servidor, para que um visitante possa ver os valores. Se estiver compartilhando informações, como faixas de crédito ou outras informações possivelmente confidenciais, essa pode não ser a melhor abordagem.

### Exemplo de código

targetPageParamsAll (anexa os atributos a todas as chamadas de mbox na página):

`function targetPageParamsAll() { return "profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

targetPageParams (anexa os atributos ao mbox global na página):

`function targetPageParams() { return profile.param1=value1&profile.param2=value2&profile.p3=hello%20world"; }`

Atributos no código mboxCreate:

`<div class="mboxDefault"> default content to replace by offer </div> <script> mboxCreate('mboxName','profile.param1=value1','profile.param2=value2'); </script>`

### Links para informações relevantes

[Atributos do perfil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_01A30B4762D64CD5946B3AA38DC8A201)

[Perfil do visitante](/help/c-target/c-audiences/c-target-rules/visitor-profile.md#concept_E972690B9A4C4372A34229FA37EDA38E)

## Atributos de perfil de script {#section_3E27B58C841448C38BDDCFE943984F8D}

Atributos de perfil de script são pares de nome/valor definidos na solução Target. O valor é determinado na execução de um snippet do JavaScript no servidor Target, a cada chamada do servidor.

Os usuários gravam pequenos snippets de código que são executados de acordo com a chamada de mbox e antes de um visitante ser avaliado para associação de público-alvo e atividade.

### Formato

Os atributos de perfil do script são criados na seção Públicos-alvo do Target. Qualquer nome de atributo é válido e o valor é resultado de uma função do JavaScript gravada pelo usuário do Target. O nome do atributo é automaticamente pré-fixado pelo &quot;usuário. &quot; no Target para diferenciar de atributos de perfil na página.

O snippet de código é gravado em linguagem Rhino JS e podem fazer referência a tokens e outros valores.

### Exemplo de casos de uso

**Abandono do carrinho**: quando o visitante chega no carrinho de compras, defina o script de perfil como 1. Quando o visitante faz a conversão, redefina-o para 0. Se o valor =1, então o visitante tem um item no carrinho.

**Contagem de visitas**: em cada nova visita, incremente a contagem em 1 para rastrear a frequência com que um visitante retorna ao site.

### Benefícios do método

Não requer atualizações de código de página.

Executado antes das decisões de associação de público-alvo e atividade, portanto esses atributos de script de perfil pode afetar a associação em uma única chamada do servidor.

Pode ser bastante robusto. Cerca de 2.000 instruções podem ser executadas por script.

### Avisos

Requer conhecimento de JavaScript.

O pedido de execução dos scripts de perfil não pode ser garantido, então não podem depender uns dos outros.

A depuração pode ser difícil.

### Exemplo de código

Os scripts de perfil são bastante flexíveis:

`user.purchase_recency: var dayInMillis = 3600 * 24 * 1000; if (mbox.name == 'orderThankyouPage') {  user.setLocal('lastPurchaseTime', new Date().getTime()); } var lastPurchaseTime = user.getLocal('lastPurchaseTime'); if (lastPurchaseTime) {  return ((new Date()).getTime()-lastPurchaseTime)/dayInMillis; }`

### Links para informações relevantes

[Atributos de script de perfil](/help/c-target/c-visitor-profile/profile-parameters.md#concept_8C07AEAB0A144FECA8B4FEB091AED4D2)

## Provedores de dados {#section_14FF3BE20DAA42369E4812D8D50FBDAE}

Os provedores de dados são uma função que permite passar dados de terceiros facilmente para o Target.

Observação: os provedores de dados exigem o at.js 1.3 ou posterior.

### Formato

A configuração `window.targetGlobalSettings.dataProviders` é uma matriz de provedores de dados.

Para obter mais informações sobre a estrutura de cada provedor de dados, consulte [Provedores de dados](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Exemplo de casos de uso

Colete dados de terceiros, como um serviço meteorológico, um DMP ou até mesmo seu próprio serviço da Web. É possível então usar esses dados para criar públicos-alvo, conteúdo de direcionamento e enriquecer o perfil do visitante.

### Benefícios do método

Essa configuração permite que clientes reúnam dados de provedores de dados de terceiros, como Demandbase, BlueKai e serviços personalizados, além de enviar os dados ao Target como parâmetros da mbox na solicitação global da mbox.

Ela é compatível com a coleta de dados de múltiplos provedores via solicitações síncronas e assíncronas.

Usar esta abordagem facilita o gerenciamento de cintilação ou conteúdo padrão da página, enquanto inclui tempos limites independentes para cada provedor para limitar o impacto sobre o desempenho da página

### Avisos

Se os provedores de dados adicionados a `window.targetGlobalSettings.dataProviders` forem assíncronos, serão executados em paralelo. A solicitação da API de visitante será executada em paralelo com funções adicionadas a `window.targetGlobalSettings.dataProviders` para permitir um tempo mínimo de espera.

at.js não tentará armazenar os dados em cache. Se o provedor de dados obtiver os dados apenas uma vez, deverá certificar-se de que os dados estão armazenados em cache e, quando a função de provedor for invocada, servir os dados do cache para a segunda invocação.

### Exemplo de código

Vários exemplos podem ser encontrados em [Provedores de dados](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers).

### Links para informações relevantes

Documentação: [Provedores de dados](/help/c-implementing-target/c-implementing-target-for-client-side-web/targetgobalsettings.md#data-providers)

### Vídeos de treinamento:

* [Uso de provedores de dados do Adobe Target](https://helpx.adobe.com/br/target/kt/using/dataProviders-atjs-feature-video-use.html)
* [Implementação de provedores de dados no Adobe Target](https://helpx.adobe.com/br/target/kt/using/dataProviders-atjs-technical-video-implement.html)

## API de atualização de perfil em massa {#section_92AB4820A5624C669D9A1F1B6220D4FA}

Via API, envia um arquivo .csv ao Target com atualizações de perfil de visitante para muitos visitantes. Cada perfil do visitante pode ser atualizado com vários atributos de perfil na página em uma chamada.

Essa opção é muito parecida com Atributos do cliente, contendo algumas diferenças:

* Os Atributos do cliente usam um carregamento de FTP, enquanto a API de atualização de perfil em massa do Target usa uma API HTTP POST.
* Os dados de atributo do cliente podem ser compartilhados com o Analytics. A Atualização de perfil em massa é utilizável somente no Target.
* Os Atributos do cliente suportam a criação de um perfil para um usuário que o Target ainda não visualizou. A API de atualização do perfil em massa atualiza somente os perfis existentes do Target.
* Os Atributos do cliente necessitam do uso de uma Experience Cloud ID (ECID). A API de atualização do perfil em massa requer ID de TNT ou `mbox3rdPartyId`.
* Não é possível enviar os seguintes caracteres em `mbox3rdPartyID`: sinal de adição (+) e barra invertida (/).

### Formato

O arquivo .csv deve fazer referência a cada visitante por meio de Target PCID ou mboxThirdPartyId. A Experience Cloud ID (ECID) não é suportada. Todos os atributos/valores de perfil são criados e atualizados via API. Os detalhes de formato estão disponíveis na documentação da API.

### Exemplo de casos de uso

Seu CRM ou outro sistema interno armazena dados importantes sobre seus visitantes, que devem ser consistentemente atualizados no Target, sem expor os dados de perfil na implementação da página.

### Benefícios do método

Nenhum limite sobre o número de atributos de perfil.

Os atributos de perfil são enviados via site e podem ser atualizados pela API e vice-versa.

### Avisos

O tamanho do arquivo em lote deve ser menor que 50 MB. Além disso, o número total de linhas não deve ultrapassar 500.000 por carregamento.

Não há limite em relação ao número ou linhas que você pode carregar em um período de 24 horas em lotes subsequentes. No entanto, o processo de ingestão pode ter o fluxo controlado em horário comercial, para garantir que outros processos sejam executados com eficiência.

As [chamadas de atualização em lote V2 consecutivas](https://developers.adobetarget.com/api/#updating-profiles) sem chamadas da mbox entre as mesmas thirdPartyIds substituindo as propriedades atualizadas na primeira chamada de atualização em lote.

### Exemplo de código

Consulte [Atualização de perfis](https://developers.adobetarget.com/api/#updating-profiles).

### Links para informações relevantes

[Atualizações de perfis](https://developers.adobetarget.com/api/#updating-profiles)

## API de atualização de perfil único {#section_5D7A9DD7019F40E9AEF2F66F7F345A8D}

Quase idêntica à API de atualização de perfil em massa, mas um perfil de visitante é atualizado por vez, alinhada à chamada de API em vez de um arquivo .csv

### Formato

O visitante deve ser identificado por meio do valor mboxPC do Target ou valor de mboxThirdPartyId. A Experience Cloud ID (ECID) não é suportada.

### Exemplo de casos de uso

Você deseja atualizar o Target em tempo real quando um visitante realiza alguma ação offline, como acessar uma central de atendimento, um empréstimo é financiado, uso de cartão de fidelidade na loja, acesso a um quiosque e assim por diante.

### Benefícios do método

Nenhum limite sobre o número de atributos de perfil.

Os atributos de perfil são enviados via site e podem ser atualizados pela API e vice-versa.

### Avisos

Limite de 1.000.000 de chamadas de API (1 milhão) por 24 horas

Perfis de atualização somente. Não é possível criar um perfil para um usuário potencia que o Target ainda precisa visualizar.

### Exemplo de código

Suporte a GET e POST.   `https://CLIENT.tt.omtrdc.net/m2/client/profile/update?mboxPC=1368007744041-575948.01_00&profile.attr1=0&profile.attr2=1...`

### Links para informações relevantes

[Atualizações de perfis](https://developers.adobetarget.com/api/#updating-profiles)

## Atributos do cliente {#section_C47FC7980A9A4608BD1A5F0BD900FA70}

Os atributos do cliente permitem que você carregue os dados de perfil do visitante via FTP à Experience Cloud. Após o upload, aproveite os dados no Adobe Analytics e no Adobe Target.

Os clientes do Target Standard podem utilizar 5 atributos, os clientes do Target Premium podem utilizar 200 atributos.

### Formato

Um arquivo .csv com Experience Cloud IDs (ECIDs) e os pares de nome/valor de atributo são carregados por FTP ou manualmente na interface de usuário da Experience Cloud.

### Exemplo de casos de uso

Seu CRM ou outros sistemas internos armazenam informações valiosas que deseja compartilhar com a Adobe Experience Cloud, incluindo Target e Analytics.

### Benefícios do método

Carregar os dados do cliente cria uma entrada de perfil para que o visitante no Target, mesmo se o Target ainda precisar visualizar o visitante.

Os mesmos dados estão automaticamente disponíveis no Target e no Analytics.

O FTP pode ser um método de implementação mais simples que a API.

### Avisos

Os clientes do Target Standard podem utilizar 5 atributos, os clientes do Target Premium podem utilizar 200 atributos

Podem atualizar valores via Atributos do cliente, não nas páginas.

Requer a implementação da Experience Cloud ID (ECID).

### Exemplo de código

Detalhes podem ser encontrados em [Crie uma fonte de atributo do cliente e carregue o arquivo de dados](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).

### Links para informações relevantes

[Crie uma fonte de atributo do cliente e faça upload do arquivo de dados](https://experienceleague.adobe.com/docs/core-services/interface/customer-attributes/t-crs-usecase.html).