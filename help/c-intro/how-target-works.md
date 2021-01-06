---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;seo;search engine optimization;edge clusters, central clusters;at.js;mbox.js;
description: Informações sobre como o Adobe Target funciona, incluindo informações sobre o Adobe Experience Platform Web SDK, as bibliotecas do JavaScript do Público alvo (at.js e mbox.js) e os vários tipos de atividade que você pode criar no Público alvo.
title: Funcionamento do Adobe Target
feature: Overview
translation-type: tm+mt
source-git-commit: 1b426e0b2004e729ba75d218a9b6ccd5195449cd
workflow-type: tm+mt
source-wordcount: '2530'
ht-degree: 70%

---


# Funcionamento do Adobe Target

Informações sobre como [!DNL Adobe Target] funciona, incluindo informações sobre [!DNL Adobe Experience Platform Web SDK], as [!DNL Target] bibliotecas JavaScript (at.js e mbox.js) e os vários tipos de atividade que você pode criar usando o Público alvo.

## SDKs da Web da Plataforma de públicos alvos e bibliotecas JavaScript {#libraries}

A Adobe Target integra-se a sites por meio das bibliotecas [!DNL AEP Web SDK] ou JavaScript:

* **Adobe Experience Platform Web SDK:** O  [AEP Web ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) SDK é uma nova biblioteca JavaScript do lado do cliente que permite  [!DNL Adobe Experience Cloud] a interação dos clientes com os vários serviços na rede  [!DNL Experience Cloud] (incluindo  [!DNL Target]) por meio da  [!DNL Adobe Experience Platform] Edge Network. Consulte [Visão geral do Público alvo](https://experienceleague.adobe.com/docs/experience-platform/edge/personalization/adobe-target/target-overview.html) para obter [!DNL Target] informações específicas.
* **at.js:** A biblioteca [da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) é a nova biblioteca de implementação do Target. A biblioteca at.js melhora os tempos de carregamento de página de implementações da Web e fornece opções de implementações melhores para aplicativos de página única. A at.js é a biblioteca de implementação recomendada e é atualizada frequentemente com novos recursos. Recomendamos que todos os clientes implementem ou migrem para a  [última versão da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).
* **mbox.js:**[ a mbox.js é a biblioteca de implementação herdada para o Target. ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md) A biblioteca mbox.js é compatível até 31 de março de 2021, mas não haverá atualizações de recursos.

>[!IMPORTANT]
>
>Todos os clientes devem migrar para [!DNL AEP Web SDK] ou para a versão mais recente do at.js. Para obter mais informações, consulte [Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html) ou [Migrar para at.js de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

Você deve consultar [!DNL AEP Web SDK] ou at.js em cada página do site. Por exemplo, você pode adicionar um desses ao cabeçalho global. Como alternativa, considere usar [Adobe Platform Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html).

Os recursos a seguir ajudarão você a implementar o AEP Web SDK ou o at.js:

* [Extensão SDK da Adobe Experience Platform Web](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [Implementação do Target usando o Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

Cada vez que um visitante solicita uma página que foi otimizada para [!DNL Target], uma solicitação é enviada ao sistema de definição de metas para determinar qual conteúdo será enviado a um visitante. Esse processo ocorre em tempo real, sempre que uma página é carregada, uma solicitação para o conteúdo é feita e preenchida pelo sistema. O conteúdo é regulado pelas leis de atividades e experiências controladas pelo comerciante e direcionado para o visitante individual do site. O conteúdo é enviado para todo visitante do site com maior probabilidade de responder, interagir e comprar, maximizando as taxas de resposta e de aquisição e a receita.

Em [!DNL Target], cada elemento na página faz parte de uma única experiência para a página inteira. Cada experiência pode incluir vários elementos na página.

O conteúdo exibido para os visitantes depende do tipo de atividade que você cria:

### Teste A/B

Consulte [Criar um teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) para obter mais informações.

O conteúdo que exibe um teste A/B básico é escolhido aleatoriamente entre os ativos que você atribui à atividade, de acordo com os percentuais escolhidos para cada experiência. Em resultado dessa divisão aleatória de tráfego, pode ser necessário muito tráfego inicial mesmo antes de as porcentagens aparecerem. Por exemplo, se você criar duas experiências, a inicial será escolhida aleatoriamente. Se houver pouco tráfego, é possível que a porcentagem de visitantes venha a tender para uma experiência. Com o aumento do tráfego, as porcentagens devem se igualar cada vez mais.

É possível especificar as metas de porcentagem para cada experiência. Nesse caso, um número aleatório será gerado e usado para escolher a experiência que será exibida. As porcentagens resultantes talvez não correspondam exatamente às metas especificadas, mas um maior tráfego significa que as experiências deverão ser divididas em maior harmonia com as metas-alvo.

1. Um cliente solicita uma página do seu servidor e ela é exibida no navegador.
2. Um cookie próprio é configurado no navegador do cliente para armazenar o comportamento do cliente.
3. A página chama o sistema de direcionamento.
4. O conteúdo é exibido com base nas regras da sua atividade.

### Alocação automática

Consulte [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) para obter mais informações.

A Alocação automática identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para a experiência vencedora, a fim de aumentar as conversões enquanto o teste continua a ser executado e aprendido.

### Direcionamento automático (AT)

Consulte [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) para obter mais informações.

O Direcionamento automático usa aprendizagem de máquina avançada para selecionar entre várias experiências definidas pelo profissional de marketing com desempenho elevado e retorna a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares, a fim de personalizar o conteúdo e gerar conversões.

### Personalização automatizada (AP)

Consulte [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) para obter mais informações.

A Personalização automatizada (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançada para corresponder diferentes variações de oferta a cada visitante com base em seu perfil de cliente individual, a fim de personalizar o conteúdo e impulsionar o incentivo.

### Direcionamento de experiência (XT)

[Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4)

O Direcionamento de experiência (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.

O Direcionamento de experiência, incluindo a geolocalização, é algo valioso para definir regras que direcionem uma experiência ou conteúdo específico para um público em particular. Várias regras podem ser definidas em uma atividade para levar diferentes variações de conteúdo para públicos-alvo diferentes. Quando visitantes acessam seu site, o direcionamento de experiência (XT) os avalia para determinar se eles atendem os critérios que você definiu. Se cumprirem os critérios, eles entram na atividade e a experiência projetada para o público-alvo qualificado é exibida. Você pode criar experiências para diversos públicos-alvo dentro de uma única atividade.

### Teste multivariado (MVT)

Consulte [Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) para obter mais informações.

O Teste multivariado (MVT) compara combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico e identifica qual elemento afeta mais o sucesso da atividade.

### Recommendations

Consulte [Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) para obter mais informações.

As atividades do Recommendations exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base em atividades do usuário anteriores ou outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.

## A rede de borda {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Uma &quot;Edge&quot; é uma arquitetura de serviço distribuída geograficamente que garante tempos de resposta ideais para usuários finais que solicitem conteúdo, independentemente de onde estejam localizados em todo o mundo.

Para melhorar os tempos de resposta, as bordas do Público alvo hospedam apenas a lógica de atividade, perfis em cache e informações de oferta.

Bancos de dados de atividade e conteúdo, [!DNL Analytics] dados, APIs e interfaces de usuário do comerciante são abrigados nos clusters centrais do Adobe. As atualizações são então enviadas para as Bordas do Público alvo. Os clusters centrais e os clusters de borda são sincronizados automaticamente para atualizar continuamente os dados de atividade em cache. Toda a modelagem 1:1 também é armazenada em cada borda, de modo que essas solicitações mais complexas também podem ser processadas na borda.

Cada cluster de borda tem todas as informações necessárias para responder à solicitação de conteúdo do usuário e rastrear os dados de análise dessa solicitação. As solicitações do usuário são roteadas para o Cluster de Borda mais próximo.

Para obter mais informações, consulte o white paper [Visão geral da segurança no Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

A solução [!DNL Adobe Target] é hospedada em data centers proprietários de Adobe e alugados por Adobe em todo o mundo.

Os locais de Cluster Central contêm um centro de coleta de dados e um centro de processamento de dados. Os locais do Edge Cluster contêm apenas um centro de coleta de dados. Cada conjunto de relatórios é atribuído a um centro de processamento de dados específico.

Os dados de atividade do local do cliente são coletados pelo mais próximo de sete Clusters de Borda e direcionados para o destino do Cluster Central predeterminado de um cliente (um dos três locais: Oregon, Dublin, Cingapura) para processamento. Os dados do perfil Visitante são armazenados no Edge Cluster mais próximo do visitante do site (os locais incluem os locais do Central Cluster e Virginia, Amsterdam, Sydney, Tokyo e Hong Kong).

Em vez de responder a todas as solicitações de direcionamento de um único local, as solicitações são processadas pelo cluster de Borda mais próximo ao visitante, reduzindo o impacto do tempo de deslocamento de rede/Internet.

![Tipos de mapa de servidores de Públicos alvos](/help/c-intro/assets/target-servers.png)

Os Clusters do Público alvo Central, hospedados nos Serviços da Web da Amazon (AWS), estão localizados em:

* Oregon, EUA
* Dublin, Irlanda
* República de Cingapura

Os públicos alvos Edge Clusters, hospedados no AWS, estão localizados em:

* Mumbai, Índia
* Tóquio, Japão
* Virgínia, EUA
* Oregon, EUA
* Sydney, Austrália
* Dublin, Irlanda
* República de Cingapura

O serviço [!DNL Target Recommendations] está hospedado em um data center [!DNL Adobe] no Oregon.

>[!IMPORTANT]
>
>[!DNL Adobe Target] atualmente não tem um cluster Edge na China e o desempenho do usuário final continuará a ser limitado para  [!DNL Target] os clientes na China. Devido ao firewall e à falta de clusters de borda no país, as experiências de sites com [!DNL Target] implantados serão lentas e as cargas de página serão afetadas. Além disso, os profissionais de marketing podem experimentar latência ao usar a interface de criação [!DNL Target].

Você pode lista de permissões os Públicos alvos de Arestas de Arestas, se desejar. Para obter mais informações, consulte [lista de permissões nós de borda do Público alvo](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md).

## Experiência protegida do usuário {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

A Adobe assegura que a disponibilidade e o desempenho da infraestrutura da definição de metas tenham a maior confiabilidade possível. No entanto, um detalhamento de comunicação entre o navegador de um usuário final e os servidores da Adobe pode causar uma interrupção na entrega de conteúdo.

Como proteção contra interrupções do serviço e problemas de conectividade, todos os locais são configurados para incluir o conteúdo padrão (definido pelo cliente), que é exibido se não for possível conectar o navegador do usuário ao [!DNL Target].

Nenhuma alteração será feita na página se o navegador do usuário não puder se conectar em um período de tempo limite definido (por padrão, 15 segundos). Se esse tempo limite for atingido, o conteúdo padrão do local será exibido.

A Adobe protege a experiência do usuário por otimizar e salvaguardar o desempenho.

* A Adobe assegura referências de desempenho com base em padrões do setor, que são garantidos pelo Contrato de nível de serviço da Adobe.
* A rede Edge assegura a entrega de dados em tempo hábil.
* A Adobe emprega uma abordagem em múltiplas camadas para proteger seus aplicativos, fornecendo o maior nível de disponibilidade e confiabilidade para os clientes.
* O [!DNL Target] Consulting oferece assistência na implementação e suporte contínuo ao produto.

## Teste compatível com a Otimização do mecanismo de pesquisa (SEO){#concept_C0C865663CAB4251B66A1F250FD25E6A}

O [!DNL Adobe Target] está alinhado às diretrizes de mecanismo de busca para teste.

A Google encoraja os testes por usuários e declarou em sua documentação que testes A/B e multivariados não prejudicam as classificações de mecanismos de pesquisa orgânicos, contanto que algumas diretrizes simples sejam seguidas.

Para obter mais informações, consulte os seguintes recursos da Google:

* [Testes de site e pesquisa Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentos e cloaking](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

As diretrizes foram apresentadas em uma publicação do [Blog da Central do Webmaster da Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Embora a publicação seja datada de 2012, ela continua sendo a declaração mais recente da Google sobre o assunto e as diretrizes continuam relevantes.

* **Sem cloaking** - Cloaking é exibir um conjunto de conteúdo aos seus usuários e um conjunto diferente de conteúdo para os bots do mecanismo de pesquisa, identificando-os especificamente e enviando conteúdo diferente propositalmente.

   O Target, como uma plataforma, foi configurado para tratar bots de mecanismo de pesquisa como qualquer usuário. Isso significa que os bots podem ser incluídos em testes que você está executando, se selecionados aleatoriamente, e &quot;ver&quot; as variações de teste.

* **Use rel=&quot;canonical&quot;** - Algumas vezes, um teste A/B precisa ser configurado usando URLs diferentes para as variações. Nesses casos, todas as variações devem conter uma tag `rel="canonical"` que faça referência à URL original (controle). Por exemplo, se a Adobe estivesse testando sua página inicial usando URLs diferentes para cada variação, a tag canônica a seguir para a página inicial seria inserida na tag `<head>` para cada uma das variações:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Use redirecionamentos 302 (temporários)** - Nos casos onde forem utilizados URLs individuais para as variações de páginas em um teste, a Google recomenda o uso de um redirecionamento 302 para direcionar o tráfego para as variações em teste. Isso diz aos mecanismos de pesquisa que o redirecionamento é temporário e só estará ativo durante a execução do teste.

   Um redirecionamento 302 é um redirecionamento no lado do servidor e o Target, juntamente com a maioria dos provedores de otimização, usa as capacidades do lado do cliente. Portanto, essa é uma área onde o Target não está em total conformidade com as recomendações da Google. Isso, entretanto, só exerce impacto sobre uma pequena fração dos testes. A abordagem padrão para execução de testes por meio do Target pede alteração do conteúdo em um único URL, então não há necessidade de redirecionamentos. Há casos em que os clientes precisam usar vários URLs para representar suas variações no teste. Nesses casos, o Target usa o comando `window.location` do JavaScript para direcionar usuários para variações do teste, que não indica explicitamente se o redirecionamento é um 301 ou 302.

   Embora continuemos a procurar soluções viáveis para obter alinhamento total com as diretrizes do mecanismo de pesquisa, para esses clientes que precisam usar URLs separados para testes, estamos confiantes de que a implementação apropriada das tags canônicas mencionadas acima diminui o risco associado a esta abordagem.

* **Execute experimentos somente conforme necessário** - Acreditamos que &quot;conforme necessário&quot; é o quanto for necessário para atingir significância estatística. O Target [fornece práticas recomendadas](https://docs.adobe.com/content/target-microsite/testcalculator.html) para determinar quando seu teste atingiu este ponto. Recomendamos que você incorpore a implementação codificada permanentemente de testes vencedores no seu fluxo de trabalho de testes e aloque os recursos apropriados.

   Usando a plataforma Target para &quot;publicar&quot; testes vencedores não é recomendado como solução permanente, mas contanto que o teste vencedor é publicado para 100% dos usuários em 100% do tempo, essa abordagem pode ser usada enquanto o processo de codificação permanente do teste vencedor é concluído.

   É importante levar em consideração também o que seu teste alterou. Simplesmente atualizar a cor de botões ou outros itens de menor importância não baseados em texto na página não exercerá qualquer influência sobre suas classificações orgânicas. As alterações, entretanto, devem ser codificadas permanentemente.

   Também é importante considerar a acessibilidade da sua página que você está testando. Se a página não estiver acessível para os mecanismos de pesquisa e nunca tiver sido concebida para classificar em pesquisa orgânica inicialmente, nenhuma das considerações acima é aplicável.

O Google declara que seguir essas diretrizes &quot;deve resultar em pequeno ou nenhum impacto dos seus testes sobre o seu site nos resultados de pesquisa&quot;.

Além dessas diretrizes, a Google também fornece mais uma diretriz na documentação de sua ferramenta de Experiências com Conteúdo:

* &quot;Suas variações de páginas devem manter o espírito do conteúdo das suas páginas originais. Essas variações não devem alterar o significado da percepção geral do seu usuário sobre aquele conteúdo original&quot;.

A Google afirma, como um exemplo, que &quot;se a página original de um site é carregada com palavras-chave não relacionadas às combinações sendo exibidas aos usuários, nós podemos remover esse site do nosso índice.&quot;

Acreditamos que seria difícil alterar involuntariamente o significado do conteúdo original contido nas variações de teste, mas recomendamos que esteja ciente dos temas das palavras-chave em uma página e manter esses temas. Alterações no conteúdo da página, especialmente adicionando ou excluindo palavras-chave relevantes, pode resultar em alterações de classificação ao URL na pesquisa orgânica. Recomendamos que você envolva seu parceiro de SEO como parte de seu protocolo de testes.

## Bots {#bots}

A Adobe Target usa [DeviceAtlas](https://deviceatlas.com/) para detectar bots conhecidos. O tráfego identificado como sendo gerado por um bot ainda recebe conteúdo, como um usuário comum, para garantir que esteja alinhado às diretrizes de SEO. O uso do tráfego de bot pode distorcer testes A/B ou algoritmos de personalização se forem tratados como usuários normais. Portanto, se um bot conhecido for detectado na atividade do Target, o tráfego será tratado de uma forma um pouco diferente. A remoção do tráfego de bot fornece uma medida mais precisa da atividade do usuário.

Especificamente, para o tráfego de bot conhecido, o Target não:

* Cria ou recupera um perfil do visitante
* Registra os atributos de perfil ou executa scripts de perfil
* Procura segmentos do Adobe Audience Manager (AAM) (se aplicável)
* Usa tráfego de bot na modelagem e veiculação de conteúdo personalizado para as atividades do Recommendations, Direcionamento automático, Automated Personalization ou alocação automática
* Registra uma visita de atividade para relatório
* Registra dados a serem enviados para a plataforma da Adobe Experience Cloud
