---
keywords: Adobe Experience Platform Web SDK;sdk web aep;sdk aep;otimização de mecanismo de pesquisa;otimização de mecanismo de pesquisa;seo;clusters de borda, clusters centrais;at.js;mbox.js;
description: Saiba como o [!DNL Adobe Target] funciona, incluindo informações sobre bibliotecas JavaScript (AEP Web SDK at.js), estratégias de uso de chamada de servidor, uso, data centers da Adobe, testes de SEO e bots.
title: Como o  [!DNL Target]  funciona?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: c5cca9b4b95289626ade1654bb508ee9f0bf35f3
workflow-type: tm+mt
source-wordcount: '2215'
ht-degree: 24%

---

# Como o [!DNL Adobe Target] funciona

Saiba como o [!DNL Adobe Target] funciona, incluindo detalhes sobre as bibliotecas JavaScript ([!DNL Adobe Experience Platform Web SDK] e at.js). Este artigo também aborda os vários tipos de atividades que você pode criar, as estratégias de contagem de uso do [!DNL Target], o Edge Network do [!DNL Target], o SEO e a detecção de bot.

Os principais pontos incluem:

* **Bibliotecas de JavaScript**: saiba mais sobre as [!DNL Target] bibliotecas JavaScript: [!DNL Adobe Experience Platform Web SDK] e at.js.
* **Estratégias de uso de chamada de servidor**: Entenda como o [!DNL Target] conta várias chamadas de servidor, incluindo pontos de extremidade, mbox única, mbox em lote, executar, pré-busca e chamadas de notificação.
* **Edge Network**: Descubra como [!DNL Target] interage com o [!DNL Adobe Experience Platform Edge Network].
* **Experiência de usuário protegida**: saiba como o [!DNL Adobe] garante a disponibilidade e o desempenho de sua infraestrutura de direcionamento.
* **Diretrizes de SEO**: siga as práticas recomendadas para alinhar as atividades de [!DNL Target] com as diretrizes de SEO.
* **Tráfego de bot**: saiba como o Target lida com o tráfego de bot para evitar testes de inclinação e algoritmos de personalização.

## Bibliotecas de JavaScript do [!DNL Adobe Target] {#libraries}

O Target integra-se a sites usando o [!DNL Experience Platform Web SDK] ou a at.js:

* **[Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/aep-web-sdk.html?lang=pt-BR){target=_blank}**: esta biblioteca JavaScript do lado do cliente permite que os clientes do [!DNL Adobe Experience Cloud] interajam com vários serviços através do [!DNL Experience Platform Edge Network]. A [!DNL Adobe] recomenda que os novos clientes do [!DNL Target] implementem o [!DNL Experience Platform Web SDK].
* **[at.js](https://experienceleague.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/overview.html?lang=pt-BR){target=_blank}**: esta biblioteca de implementação do [!DNL Target] melhora os tempos de carregamento de página de implementações da Web e oferece opções melhores para aplicativos de página única. Atualizado com frequência com novos recursos, o [!DNL Adobe] recomenda que todos os [usuários do at.js atualizem para a versão mais recente](https://experienceleague-review.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html){target=_blank}.

>[!NOTE]
>
>A biblioteca mbox.js é uma implementação herdada do [!DNL Target] e não é mais suportada após 31 de março de 2021. Atualize para o [!UICONTROL Experience Platform Web SDK] (preferencial) ou para a versão mais recente do at.js.

Consulte o [!UICONTROL Experience Platform Web SDK] ou a at.js em todas as páginas do site. Por exemplo, adicione uma dessas bibliotecas ao seu cabeçalho global. Como alternativa, use [tags na Adobe Experience Platform](https://experienceleague.adobe.com/pt-br/docs/experience-platform/tags/home){target=_blank} para implementar o [!DNL Target].

Os seguintes recursos contêm informações detalhadas para ajudar você a implementar o [!DNL Experience Platform Web SDK] ou a at.js:

* [[!DNL Adobe Experience Platform Web SDK] extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=pt-BR){target=_blank}
* [Implementar o  [!DNL Target]  usando a  [!DNL Adobe Experience Platform]](https://experienceleague.adobe.com/pt-br/docs/target-dev/developer/client-side/at-js-implementation/deploy-at-js/implement-target-using-adobe-launch){target=_blank}

Cada vez que um visitante solicita uma página otimizada para [!DNL Target], uma solicitação em tempo real é enviada para o sistema de direcionamento para determinar o conteúdo a ser veiculado. Essa solicitação é feita e preenchida sempre que uma página é carregada, regida por atividades e experiências controladas pelo profissional de marketing. O conteúdo é direcionado para visitantes individuais do site, maximizando as taxas de resposta, as taxas de aquisição e a receita. O conteúdo personalizado ajuda a garantir que os visitantes respondam, interajam ou façam compras.

No [!DNL Target], cada elemento na página faz parte de uma única experiência, que pode incluir vários elementos.

O conteúdo exibido depende do tipo de atividade que você cria:

### [!UICONTROL A/B Test]

Em um teste A/B básico, o conteúdo é escolhido aleatoriamente a partir das experiências atribuídas. É possível definir porcentagens de alocação de tráfego para cada experiência. Inicialmente, o tráfego pode ser distribuído de forma desigual devido à divisão aleatória, mas é equalizado à medida que o tráfego aumenta. Por exemplo, com duas experiências, a experiência inicial é escolhida aleatoriamente. Tráfego baixo pode distorcer as porcentagens de visitantes em direção a uma experiência, mas essa situação equilibra com mais tráfego.

Especifique metas de porcentagem para cada experiência. Um número aleatório é gerado para selecionar a experiência a ser exibida. Embora as porcentagens resultantes possam não corresponder exatamente aos alvos, um tráfego maior leva a uma divisão mais próxima dos objetivos do alvo.

1. Um cliente solicita uma página do seu servidor, que é exibida no navegador.
1. Um cookie próprio é definido no navegador do cliente para armazenar seu comportamento.
1. A página chama o sistema de direcionamento.
1. O conteúdo é exibido com base nas regras de atividade.

Consulte [Criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) para obter mais informações.

### [!UICONTROL Auto-Allocate]

[!UICONTROL Auto-Allocate] identifica a experiência vencedora entre duas ou mais opções. Em seguida, ele realoca automaticamente mais tráfego para o vencedor, aumentando as conversões conforme o teste continua a ser executado e aprendido.

Consulte [[!UICONTROL Auto-Allocate]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) para obter mais informações.

### [!UICONTROL Auto-Target] (ÀS)

O [!UICONTROL Auto-Target] aproveita o aprendizado de máquina avançado para escolher entre várias experiências de alto desempenho definidas pelo profissional de marketing. O [!UICONTROL Auto-Target] fornece a experiência mais personalizada para cada visitante com base em perfis de clientes individuais e no comportamento de visitantes anteriores com perfis similares. Use o [!UICONTROL Auto-Target] para personalizar o conteúdo e gerar conversões.

Consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para obter mais informações.

### [!UICONTROL Automated Personalization] (AP)

A [!UICONTROL Automated Personalization] (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançada para corresponder diferentes variações a cada visitante. A AP personaliza o conteúdo com base em perfis de clientes individuais para impulsionar um aumento.

Consulte [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) para obter mais informações.

### [!UICONTROL Experience Targeting] (XT)

O [!UICONTROL Experience Targeting] (XT) fornece conteúdo a públicos-alvo específicos com base em regras e critérios definidos pelo profissional de marketing. Incluindo a geolocalização, o XT é importante para definir regras que direcionem experiências ou conteúdo específicos para públicos-alvo específicos. Várias regras podem ser definidas em uma atividade para fornecer diferentes variações de conteúdo para públicos diferentes. Quando visitantes acessam o seu site, o XT os avalia para determinar se eles atendem aos critérios. Se qualificados, eles entram na atividade e veem a experiência projetada para eles. Você pode criar experiências para diversos públicos-alvo dentro de uma única atividade.

Consulte [Direcionamento de experiência](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) para obter mais informações.

### [!UICONTROL Multivariate Test] (MVT)

O [!UICONTROL Multivariate Testing] (MVT) compara combinações de ofertas em elementos da página para determinar qual combinação tem melhor desempenho para um público-alvo específico. O MVT ajuda a identificar qual elemento afeta mais o sucesso da atividade.

Consulte [Teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) para obter mais informações.

### [!UICONTROL Recommendations]

As atividades do [!UICONTROL Recommendations] exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base em suas atividades anteriores ou em outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem não ser detectados de outra forma.

Consulte [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) para obter mais informações.

<!--
## How [!DNL Target] counts server-call usage {#usage}

[!DNL Target] counts only server calls that provide value to customers. The following table shows how [!DNL Target] counts endpoints, single mbox, batch mbox calls, execute, prefetch, and notification calls.

The following information helps you understand the counting strategy used for [!DNL Target] server calls, as shown in the table below:

* **Count Once**: Counts once per API call.
* **Count the Number of mboxes**: Counts the number of mboxes under the array in the payload of a single API call.
* **Ignore**: Is not counted at all.
* **Count the Number of Views (Once)**: Counts the number of views under the array in the payload. In a typical implementation, a view notification has only one view under the notifications array, making this equivalent to counting once in most implementations.

|Endpoint|Fetch type|Options|Counting strategy|
|--- |--- |--- |-- |
|`rest//v1/mbox`|Single|[!UICONTROL execute]|Count once|
|`rest/v2/batchmbox`|Batch|[!UICONTROL execute]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch]|Ignore|
||Batch|[!UICONTROL notifications]|Count the number of mboxes|
|`/ubox/[raw\|image\|page]`|Single|[!UICONTROL execute]|Count once|
|`rest/v1/delivery`<p>`/rest/v1/target-upstream`|Single|[!UICONTROL execute] > [!UICONTROL pageLoad]|Count once|
||Single|[!UICONTROL prefetch] > [!UICONTROL pageLoad]|Ignore|
||Single|[!UICONTROL prefetch] > [!UICONTROL views]|Ignore|
||Batch|[!UICONTROL execute] > [!UICONTROL mboxes]|Count the number of mboxes|
||Batch|[!UICONTROL prefetch] > [!UICONTROL mboxes]|Ignore|
||Batch|[!UICONTROL notifications] > [!UICONTROL views]|Count the number of views (once)|
||Batch|[!UICONTROL notifications] > [!UICONTROL pageLoad]|Count once|
||Batch|[!UICONTROL notifications] > type ([!UICONTROL conversions])|Count once|
||Batch|[!UICONTROL notifications] > [!UICONTROL mboxes]|Count the number of mboxes|

-->

## A rede de borda {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Uma &quot;Edge&quot; é uma arquitetura de fornecimento distribuída geograficamente que garante os tempos de resposta ideais para visitantes que solicitam conteúdo, independentemente da localização.

Para melhorar os tempos de resposta, a borda [!DNL Target] hospeda somente a lógica de atividade, os perfis em cache e as informações da oferta.

Bancos de dados de atividade e conteúdo, [!DNL Analytics] dados, APIs e interfaces de usuário dos profissionais de marketing são abrigados em [!DNL Adobe] clusters centrais. As atualizações são enviadas para as bordas [!DNL Target], que são sincronizadas automaticamente com os clusters centrais para atualizar continuamente os dados de atividade em cache. A modelagem 1:1 também é armazenada em cada borda, permitindo que solicitações complexas sejam processadas localmente.

Cada cluster do Edge contém todas as informações necessárias para responder às solicitações de conteúdo do visitante e rastrear os dados de análise. As solicitações do usuário são roteadas para o nó de borda mais próximo.

Para obter mais informações, consulte o white paper [Visão geral da segurança no Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

O [!DNL Target] está hospedado em data centers próprios e alugados pela Adobe Adobe no mundo inteiro.

Os locais do cluster central abrigam centros de coleta e processamento de dados. Os locais do Edge Cluster contêm apenas centros de coleta de dados. Cada conjunto de relatórios é atribuído a um centro de processamento de dados específico.

Os dados de atividade do site do cliente são coletados pelo mais próximo de sete clusters Edge. Esses dados são então direcionados a um destino de cluster central predeterminado (Oregon, Dublin ou Singapura) para processamento. Os dados do perfil do visitante são armazenados no cluster de borda mais próximo do visitante do site. Os locais do Edge Cluster incluem os locais centrais do Cluster, bem como Virgínia, Mumbai, Sydney e Tóquio.

Em vez de processar todas as solicitações de direcionamento de um único local, as solicitações são tratadas pelo cluster do Edge mais próximo do visitante. Essa abordagem reduz o impacto do tempo de deslocamento da Internet e da rede.

![Mapa mostrando os diferentes tipos de servidores do Target](/help/main/c-intro/assets/target-servers.png)

[!DNL Target] Os clusters centrais hospedados na Amazon Web Services (AWS) incluem:

* Oregon, EUA
* Dublin, Irlanda
* República de Singapura

[!DNL Target] Os clusters de borda hospedados na AWS incluem:

* Mumbai, Índia
* Tóquio, Japão
* Virgínia, EUA
* Oregon, EUA
* Sydney, Austrália
* Dublin, Irlanda
* República de Singapura

O serviço [!DNL Target Recommendations] é hospedado em um data center [!DNL Adobe] no Oregon.

>[!IMPORTANT]
>
>Atualmente, o [!DNL Target] não tem um cluster do Edge na China, o que limita o desempenho do visitante para [!DNL Target] clientes na região. O firewall e a ausência de clusters do Edge podem afetar as experiências do site, causando renderização lenta e tempos de carregamento de página. Além disso, os profissionais de marketing podem experimentar latência ao usar a interface de criação do [!DNL Target].

Você pode adicionar clusters de borda do [!DNL Target] à lista de permissões, se desejar. Para obter mais informações, consulte [lista de permissões de nós de borda do Target](https://experienceleague.adobe.com/pt-br/docs/target-dev/developer/implementation/privacy/allowlist-edges){target=_blank}.

## Experiência do usuário protegida {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

A [!DNL Adobe] garante que a disponibilidade e o desempenho de sua infraestrutura de direcionamento tenham a maior confiabilidade possível. No entanto, detalhamentos de comunicação entre o navegador de um visitante e os servidores do [!DNL Adobe] podem interromper a entrega de conteúdo.

Como proteção contra interrupções do serviço e problemas de conectividade, todos os locais são configurados para incluir o conteúdo padrão (definido pelo cliente). Este conteúdo padrão é exibido se o navegador do visitante não puder se conectar a [!DNL Target].

Nenhuma alteração será feita na página se o navegador do visitante não puder se conectar em um período de tempo limite definido (padrão: 15 segundos). Se esse tempo limite for atingido, o conteúdo padrão do local será exibido.

A [!DNL Adobe] protege a experiência do usuário por otimizar e salvaguardar o desempenho.

* O [!DNL Adobe] garante referências de desempenho com base em padrões do setor, garantidos pelo [!UICONTROL Adobe Service Level Agreement].
* A rede de borda assegura a entrega de dados em tempo hábil.
* O [!UICONTROL Adobe] emprega uma abordagem de múltiplas camadas para proteger seus aplicativos, fornecendo o mais alto nível de disponibilidade e confiabilidade para os clientes.
* O [!DNL Target] Consulting oferece assistência na implementação e suporte contínuo ao produto.

## Teste compatível com a Otimização do mecanismo de pesquisa (SEO) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

[!DNL Adobe Target] está alinhado com as diretrizes de mecanismo de busca para teste. O [!DNL Google] incentiva os usuários a testarem e declara que o A/B e o [!UICONTROL Multivariate Testing] não prejudicam as classificações dos mecanismos de pesquisa orgânica se determinadas diretrizes forem seguidas.

O [!DNL Adobe Target] está alinhado às diretrizes de mecanismo de busca para teste.

Para obter mais informações, consulte os seguintes recursos da Google:

* [Testes de site e pesquisa Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentos e cloaking](https://support.google.com/analytics/answer/12979939?hl)


As diretrizes foram apresentadas em uma publicação do [Blog da Central do Webmaster da Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Embora a publicação seja datada de 2012, ela continua sendo a declaração mais recente de [!DNL Google] sobre o assunto, e as diretrizes ainda são relevantes.

* **Sem cloaking**: o cloaking envolve a exibição de um conjunto de conteúdo para os usuários e um conjunto diferente para os bots do mecanismo de pesquisa, identificando bots especificamente e enviando conteúdo diferente para eles.

  [!DNL Target] está configurado para tratar bots de mecanismo de pesquisa como qualquer usuário. Consequentemente, os bots podem ser incluídos em atividades caso sejam selecionados aleatoriamente e &quot;vejam&quot; as variações do teste.

* **Use rel=&quot;canonical&quot;**: às vezes, um teste A/B requer URLs diferentes para variações. Nesses casos, todas as variações devem incluir uma tag rel=&quot;canonical&quot; fazendo referência ao URL original (controle). Por exemplo, se [!DNL Adobe] estiver testando sua página inicial com URLs diferentes para cada variação, a tag canônica a seguir para a página inicial deverá ser colocada na tag `<head>` de cada variação:

  `<link rel="canonical" href="https://www.adobe.com" />`

* **Usar redirecionamentos 302 (temporário)**: quando URLs separadas são usadas para variações de páginas em um teste, o [!DNL Google] recomenda o uso de um redirecionamento 302 para direcionar o tráfego para as variações em teste. O redirecionamento 302 informa aos mecanismos de pesquisa que o redirecionamento é temporário e está ativo somente enquanto o teste está em execução.

  Um redirecionamento 302 é um redirecionamento no lado do servidor, enquanto o [!DNL Target] e a maioria dos provedores de otimização usam recursos do lado do cliente. Portanto, [!DNL Target] não é totalmente compatível com as recomendações de [!DNL Google] para redirecionamentos. No entanto, isso afeta apenas uma pequena fração dos testes. A abordagem padrão para execução de testes por meio do [!DNL Target] envolve a alteração do conteúdo em uma única URL, eliminando a necessidade de redirecionamentos. Nos casos em que são necessárias várias URLs para variações de teste, o [!DNL Target] usa o comando `window.location` do JavaScript, que não especifica se o redirecionamento é um 301 ou 302.

  O [!DNL Adobe] está ativamente buscando soluções para cumprir totalmente as diretrizes do mecanismo de pesquisa. Para clientes que precisam de URLs separados para testes, a [!DNL Adobe] acredita que a implementação correta de tags canônicas diminui os riscos associados.

* **Executar experimentos somente enquanto necessário**: [!DNL Adobe] define &quot;conforme necessário&quot; como o tempo necessário para atingir significância estatística. [!DNL Target] oferece práticas recomendadas e a [!DNL Adobe Target] [Calculadora de tamanho da amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) para determinar quando seu teste atingiu este ponto. A [!DNL Adobe] recomenda incorporar a implementação codificada permanentemente de testes vencedores no seu fluxo de trabalho de testes e alocar os recursos apropriados.

  O uso do [!DNL Target] para &quot;publicar&quot; testes vencedores não é recomendado como uma solução permanente. Se o teste vencedor for publicado para 100% dos usuários o tempo todo, essa abordagem poderá ser usada temporariamente enquanto o teste vencedor é codificado.

  Considere o que seu teste alterou. Pequenas atualizações, como cores de botões, não afetam as classificações orgânicas. No entanto, as alterações de texto devem ser codificadas.

  Além disso, considere a acessibilidade da página que você está testando. Se a página não estiver acessível para mecanismos de pesquisa e nunca tiver sido projetada para classificar na pesquisa orgânica, essas considerações não se aplicam. Um exemplo é uma página de aterrissagem dedicada a uma campanha de email.

O Google declara que seguir essas diretrizes “deve resultar em pequeno ou nenhum impacto dos seus testes sobre o seu site nos resultados de pesquisa”.

Além dessas diretrizes, a Google também fornece mais uma diretriz na documentação de sua ferramenta de Experiências com Conteúdo:

* “Suas variações de páginas devem manter o espírito do conteúdo das suas páginas originais. Essas variações não devem alterar o significado da percepção geral do seu usuário sobre aquele conteúdo original”.

A Google afirma, como um exemplo, que “se a página original de um site é carregada com palavras-chave não relacionadas às combinações sendo exibidas aos usuários, nós podemos remover esse site do nosso índice.”

[!UICONTROL Adobe] acha que seria difícil alterar involuntariamente o significado do conteúdo original nas variações de teste. No entanto, o [!UICONTROL Adobe] recomenda estar ciente dos temas de palavras-chave em uma página e mantê-los. Alterações no conteúdo da página, especialmente adicionando ou excluindo palavras-chave relevantes, pode resultar em alterações de classificação ao URL na pesquisa orgânica. A [!DNL Adobe] recomenda que você envolva seu parceiro de SEO como parte de protocolo de testes.

## Bots {#bots}

[!DNL Target] usa a métrica &quot;isRobot&quot; do [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) para detectar bots conhecidos com base na Cadeia de Caracteres do Agente do Usuário transmitida no Cabeçalho da Solicitação.

>[!NOTE]
>
> Para solicitações de [!DNL Server-Side], o valor transmitido no [nó “Contexto” da solicitação](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) tem prioridade sobre a sequência de agente do usuário para detecção de bot.

O tráfego identificado como gerado pelo bot ainda recebe conteúdo. Os bots são tratados como usuários regulares para garantir que o [!DNL Target] se alinhe às diretrizes de SEO. No entanto, o tráfego de bot pode distorcer testes A/B ou algoritmos de personalização se for tratado como usuários normais. Portanto, o tráfego de bot conhecido na atividade [!DNL Target] é tratado de forma diferente. A remoção do tráfego de bot fornece uma medida mais precisa da atividade do usuário.

Para tráfego de bot conhecido, [!DNL Target] não:

* Cria ou recupera um perfil do visitante
* Registrar atributos de perfil ou executar scripts de perfil
* Procura segmentos do [!DNL Adobe Audience Manager] (AAM) (se aplicável)
* Use o tráfego de bot para modelar ou veicular conteúdo personalizado para atividades do [!UICONTROL Recommendations], [!UICONTROL Auto-Target], [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Allocate]
* Registra uma visita de atividade para relatório
* Registra dados a serem enviados para a plataforma da [!DNL Adobe Experience Cloud]

Para tráfego de bot conhecido, ao usar o [!UICONTROL Analytics for Target] (A4T), o [!DNL Target] não:

* Envia eventos para o [!DNL Analytics]

Para tráfego de bot conhecido ao usar o log de `client_side`, [!DNL Target] não retorna:

* `tnta payload`
