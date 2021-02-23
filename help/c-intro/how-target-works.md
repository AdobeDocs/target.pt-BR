---
keywords: Adobe Experience Platform Web SDK;aep web sdk;aep sdk;otimização do mecanismo de pesquisa;seo;clusters de borda, clusters centrais;at.js;mbox.js;
description: Saiba mais sobre como a Adobe Target funciona, incluindo informações sobre as bibliotecas do JavaScript do Público alvo (at.js e AEP Web SDK), os data centers do Adobe e os testes SEO.
title: Como Funciona O Público alvo?
feature: Visão geral
translation-type: tm+mt
source-git-commit: 2a06eccf27ce214a9d43bced25b15afbc291d814
workflow-type: tm+mt
source-wordcount: '2567'
ht-degree: 32%

---


# Funcionamento do Adobe Target

Saiba como o [!DNL Adobe Target] funciona, incluindo informações sobre as bibliotecas [!DNL Adobe Experience Platform Web SDK] e JavaScript (at.js e mbox.js). Este artigo também apresenta os vários tipos de atividade que você pode criar usando [!DNL Target]. Você também pode saber mais sobre a [!DNL Target] rede de borda, a Search Engine Otimization (SEO) e como [!DNL Target] detecta bots.

## SDKs da Web da Plataforma de públicos alvos e bibliotecas JavaScript {#libraries}

[!DNL Target] integra-se a sites que usam as bibliotecas  [!DNL AEP Web SDK] ou JavaScript:

* **Adobe Experience Platform Web SDK:** O  [AEP Web ](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) SDK é uma nova biblioteca JavaScript do lado do cliente. O AEP Web SDK permite que os clientes de [!DNL Adobe Experience Cloud] interajam com os vários serviços em [!DNL Experience Cloud] (incluindo [!DNL Target]) por meio da [!DNL AEP] Edge Network. A Adobe recomenda que todos os clientes [!DNL Target] novos implementem o [!DNL AEP Web SDK].
* **at.js:** A biblioteca  [at.js ](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-atjs-implementation.md#concept_8AC8D169E02944B1A547A0CAD97EAC17) é uma biblioteca de implementação para  [!DNL Target]. A biblioteca at.js melhora os tempos de carregamento de página de implementações da Web e fornece opções de implementações melhores para aplicativos de página única. O at.js é atualizado com frequência com novos recursos. A Adobe recomenda que todos os clientes que usam o at.js atualizem suas implementações para a versão mais recente do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).[
* **mbox.js:**[](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/mbox-download.md) a mbox.js é a biblioteca de implementação herdada para o [!DNL Target]. A biblioteca mbox.js é compatível até 31 de março de 2021; no entanto, não haverá atualizações de recursos.

>[!IMPORTANT]
>
>Todos os clientes devem migrar para [!DNL AEP Web SDK] ou para a versão mais recente do at.js. Para obter mais informações, consulte [Adobe Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) ou [Migrar para at.js de mbox.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/t-mbox-download/c-target-atjs-implementation/target-migrate-atjs.md#task_DE55DCE9AC2F49728395665DE1B1E6EA).

Consulte [!DNL AEP Web SDK] ou at.js em cada página do site. Por exemplo, você pode adicionar uma dessas bibliotecas ao cabeçalho global. Como alternativa, considere usar [Adobe Platform Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html) para implementar [!DNL Target].

Os seguintes recursos contêm informações detalhadas para ajudá-lo a implementar o AEP Web SDK ou o at.js:

* [Extensão SDK da Adobe Experience Platform Web](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=en#configure-the-aep-web-sdk-extension)
* [Implementação do Target usando o Adobe Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

Cada vez que um visitante solicita uma página que foi otimizada para [!DNL Target], uma solicitação é enviada ao sistema de definição de metas. A solicitação ajuda a determinar qual conteúdo será enviado para esse visitante. Esse processo ocorre em tempo real. Toda vez que uma página é carregada, uma solicitação para o conteúdo é feita e preenchida pelo sistema. O conteúdo é regulado pelas leis de atividades e experiências controladas pelo comerciante e direcionado para o visitante individual do site. O conteúdo é disponibilizado para cada visitante do site com maior probabilidade de responder, interagir ou, por fim, comprar. O conteúdo personalizado ajuda a maximizar as taxas de resposta, as taxas de aquisição e a receita.

Em [!DNL Target], cada elemento na página faz parte de uma única experiência para a página inteira. Cada experiência pode incluir vários elementos na página.

O conteúdo exibido para os visitantes depende do tipo de atividade que você cria:

### Teste A/B

O conteúdo exibido em um teste A/B básico é escolhido aleatoriamente entre as experiências atribuídas à atividade. Você pode atribuir as porcentagens de alocação de tráfego para cada experiência. Como resultado dessa divisão aleatória do tráfego, pode ser necessária uma quantidade significativa do tráfego inicial antes que as porcentagens desapareçam. Por exemplo, se você criar duas experiências, a inicial será escolhida aleatoriamente. Se houver pouco tráfego, é possível que a porcentagem de visitantes venha a tender para uma experiência. À medida que o tráfego aumenta, as porcentagens são equalizadas.

É possível especificar as metas de porcentagem para cada experiência. Nesse caso, um número aleatório será gerado e usado para escolher a experiência que será exibida. As porcentagens resultantes talvez não correspondam exatamente às metas especificadas, mas um maior tráfego significa que as experiências deverão ser divididas em maior harmonia com as metas-alvo.

1. Um cliente solicita uma página do seu servidor e ela é exibida no navegador.
2. Um cookie primário é definido no navegador do cliente para armazenar o comportamento do cliente.
3. A página chama o sistema de direcionamento.
4. O conteúdo é exibido com base nas regras da sua atividade.

Consulte [Criar um teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) para obter mais informações.

### Alocação automática

A Autoalocação identifica um vencedor entre duas ou mais experiências. A Autoalocação aloca automaticamente mais tráfego para a experiência vencedora para aumentar as conversões enquanto o teste continua em execução e aprende.

Consulte [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) para obter mais informações.

### Direcionamento automático (AT)

O Público alvo automático usa o aprendizado de máquina avançado para selecionar entre várias experiências definidas pelo profissional de marketing de alto desempenho. O Público alvo automático serve a experiência mais personalizada para cada visitante. O delivery da experiência é baseado em perfis individuais do cliente e no comportamento de visitantes anteriores com perfis semelhantes. Use o Público alvo automático para personalizar o conteúdo e gerar conversões.

Consulte [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) para obter mais informações.

### Personalização automatizada (AP)

O Automated Personalization (AP) combina ofertas ou mensagens e usa o aprendizado de máquina avançado para corresponder às diferentes variações de oferta de cada visitante. O delivery da experiência é baseado em perfis individuais do cliente para personalizar o conteúdo e impulsionar o incentivo.

Consulte [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) para obter mais informações.

### Direcionamento de experiência (XT)

O Direcionamento de experiência (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.

O Direcionamento de experiência, incluindo a geolocalização, é algo valioso para definir regras que direcionem uma experiência ou conteúdo específico para um público em particular. Várias regras podem ser definidas em uma atividade para levar diferentes variações de conteúdo para públicos-alvo diferentes. Quando visitantes acessam seu site, o direcionamento de experiência (XT) os avalia para determinar se eles atendem os critérios que você definiu. Se cumprirem os critérios, eles entram na atividade e a experiência projetada para o público-alvo qualificado é exibida. Você pode criar experiências para diversos públicos-alvo dentro de uma única atividade.

Consulte [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) para obter mais informações.

### Teste multivariado (MVT)

O Multivariate Testing (MVT) compara combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho para uma audiência específica. O MVT ajuda a identificar qual elemento mais afeta o sucesso da atividade.

Consulte [Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) para obter mais informações.

### Recommendations

As atividades do Recommendations exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base em atividades do usuário anteriores ou outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.

Consulte [Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) para obter mais informações.

## A rede de borda {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Uma &quot;Edge&quot; é uma arquitetura de serviço distribuída geograficamente que garante tempos de resposta ideais para visitantes que solicitam conteúdo, independentemente de onde estejam localizados no mundo inteiro.

Para melhorar os tempos de resposta, [!DNL Target] borda somente a lógica de atividade, perfis em cache e informações de oferta do host.

Bancos de dados de atividade e conteúdo, [!DNL Analytics] dados, APIs e interfaces de usuário do comerciante são abrigados nos clusters centrais do Adobe. As atualizações são então enviadas para as bordas [!DNL Target]. Os clusters centrais e os clusters de borda são sincronizados automaticamente para atualizar continuamente os dados de atividade em cache. Toda a modelagem 1:1 também é armazenada em cada borda, de modo que essas solicitações mais complexas também podem ser processadas na borda.

Cada Cluster de Borda tem todas as informações necessárias para responder à solicitação de conteúdo do visitante e rastrear os dados de análise dessa solicitação. As solicitações de visitante são roteadas para o Cluster de Borda mais próximo.

Para obter mais informações, consulte o white paper [Visão geral da segurança no Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

A solução [!DNL Target] é hospedada em data centers proprietários de Adobe e alugados por Adobe em todo o mundo.

Os locais de Cluster Central contêm um centro de coleta de dados e um centro de processamento de dados. Os locais do Edge Cluster contêm apenas um centro de coleta de dados. Cada conjunto de relatórios é atribuído a um centro de processamento de dados específico.

Os dados de atividade do local do cliente são coletados pelo mais próximo de sete Clusters de Borda. Esses dados são direcionados para o destino do Cluster Central predeterminado de um cliente (um dos três locais: Oregon, Dublin, Cingapura) para processamento. Os dados do perfil do visitante são armazenados no Cluster de Borda mais próximo ao visitante do site. Os locais dos clusters de borda incluem os locais dos clusters centrais e Virgínia, Amsterdã, Sydney, Tóquio e Hong Kong.

Em vez de responder a todas as solicitações de direcionamento de um único local, as solicitações são processadas pelo Cluster de Borda mais próximo ao visitante. Esse processo ajuda a atenuar o impacto do tempo de viagem da rede/Internet.

![Tipos de mapa de servidores de Públicos alvos](/help/c-intro/assets/target-servers.png)

[!DNL Target] Os clusters centrais, hospedados no Amazon Web Services (AWS), incluem:

* Oregon, EUA
* Dublin, Irlanda
* República de Cingapura

[!DNL Target] Os clusters de borda, hospedados no AWS, incluem:

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
>[!DNL Adobe Target] atualmente não tem um cluster Edge na China e o desempenho do visitante continua a ser limitado para  [!DNL Target] clientes na China. Devido ao firewall e à falta de clusters de borda no país, as experiências de sites com [!DNL Target] implantados podem ser afetadas. As experiências podem ser lentas na renderização e as cargas de página podem ser afetadas. Além disso, os profissionais de marketing podem experimentar latência ao usar a interface de criação [!DNL Target].

Você pode lista de permissões [!DNL Target] Clusters de Borda, se desejar. Para obter mais informações, consulte [lista de permissões nós de borda do Público alvo](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md).

## Experiência protegida do usuário {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

A Adobe assegura que a disponibilidade e o desempenho da infraestrutura da definição de metas tenham a maior confiabilidade possível. No entanto, um detalhamento de comunicação entre o navegador de um visitante e os servidores do Adobe pode causar uma interrupção no delivery do conteúdo.

Para proteger contra interrupções de serviço e problemas de conectividade, todos os locais são configurados para incluir o conteúdo padrão (definido pelo cliente). Esse conteúdo padrão será exibido se o navegador do usuário não conseguir se conectar a [!DNL Target].

Nenhuma alteração será feita na página se o navegador do usuário não puder se conectar em um período de tempo limite definido (por padrão, 15 segundos). Se esse tempo limite for atingido, o conteúdo padrão do local será exibido.

A Adobe protege a experiência do usuário por otimizar e salvaguardar o desempenho.

* A Adobe assegura referências de desempenho com base em padrões do setor, que são garantidos pelo Contrato de nível de serviço da Adobe.
* A rede Edge assegura a entrega de dados em tempo hábil.
* A Adobe emprega uma abordagem em múltiplas camadas para proteger seus aplicativos, fornecendo o maior nível de disponibilidade e confiabilidade para os clientes.
* O [!DNL Target] Consulting oferece assistência na implementação e suporte contínuo ao produto.

## Teste compatível com a Otimização do mecanismo de pesquisa (SEO){#concept_C0C865663CAB4251B66A1F250FD25E6A}

O [!DNL Adobe Target] está alinhado às diretrizes de mecanismo de busca para teste.

O Google incentiva o teste do usuário. O Google afirma em sua documentação que A/B e Multivariate Testing não prejudicam as classificações dos mecanismos de pesquisa orgânicos se você seguir determinadas diretrizes.

Para obter mais informações, consulte os seguintes recursos da Google:

* [Testes de site e pesquisa Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentos e cloaking](https://support.google.com/analytics/answer/2576845?hl=en&amp;ref_topic=1745207)

As diretrizes foram apresentadas em uma publicação do [Blog da Central do Webmaster da Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Embora a publicação seja datada de 2012, ela continua sendo a declaração mais recente da Google sobre o assunto e as diretrizes continuam relevantes.

* **Sem encobrimento**: O encobrimento mostra um conjunto de conteúdo para seus usuários e um conjunto diferente de conteúdo para robôs de mecanismo de pesquisa. O encobrimento é feito identificando especificamente bots e alimentando-os com propósito de conteúdo diferente.

   [!DNL Target]O , como uma plataforma, foi configurado para tratar bots de mecanismo de pesquisa como qualquer usuário. Como resultado, os bots podem ser incluídos no atividade se os bots forem selecionados aleatoriamente e &quot;ver&quot; as variações do teste.

* **Use rel=&quot;canônico&quot;**: Às vezes, um teste A/B deve ser configurado usando URLs diferentes para as variações. Nesses casos, todas as variações devem conter uma tag `rel="canonical"` que faça referência à URL original (controle). Por exemplo, suponha que o Adobe esteja testando seu home page usando URLs diferentes para cada variação. A seguinte tag canônica para o home page apareceria na tag `<head>` para cada uma das variações:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Usar redirecionamentos** 302 (temporários): Nos casos em que URLs separados são usados para as páginas de variação em um teste, o Google recomenda usar um redirecionamento 302 para direcionar o tráfego para as variações de teste. O redirecionamento 302 informa aos mecanismos de pesquisa que o redirecionamento é temporário e está ativo somente enquanto o teste estiver em execução.

   Um redirecionamento 302 é um redirecionamento do lado do servidor e [!DNL Target], juntamente com a maioria dos provedores de otimização, usa recursos do lado do cliente. Portanto, essa é uma área em que [!DNL Target] não é totalmente compatível com as recomendações do Google. Essa prática, porém, afeta apenas uma pequena fração dos testes. A abordagem padrão para executar testes por meio de [!DNL Target] requer a alteração do conteúdo em um único URL, portanto, nenhum redirecionamento é necessário. Há instâncias em que os clientes devem usar vários URLs para representar suas variações de teste. Nesses casos, [!DNL Target] usa o comando JavaScript `window.location`. Esse comando direciona os usuários para testar variações, o que não significa explicitamente se o redirecionamento é 301 ou 302.

   A Adobe continua buscando soluções viáveis para se alinhar completamente com as diretrizes do mecanismo de pesquisa. Para os clientes que precisam usar URLs separados para testes, o Adobe está confiante de que a implementação adequada das tags canônicas reduz o risco associado a essa abordagem.

* **Executar experimentos apenas enquanto for necessário**: Adobe acredita que &quot;o tempo necessário&quot; seja o tempo necessário para alcançar significância estatística. [!DNL Target][O fornece práticas recomendadas](https://docs.adobe.com/content/target-microsite/testcalculator.html) para determinar quando seu teste atingiu este ponto. A Adobe recomenda que você incorpore a implementação codificada de testes vencedores ao seu fluxo de trabalho de teste e atribua os recursos apropriados.

   O uso da plataforma [!DNL Target] para &quot;publicar&quot; testes vencedores não é recomendado como uma solução permanente. Se o teste vencedor for publicado para 100% dos usuários 100% do tempo, essa abordagem poderá ser usada enquanto o processo de codificação de hardware do teste vencedor for concluído.

   É importante levar em consideração também o que seu teste alterou. Simplesmente atualizar a cor dos botões ou outros itens não baseados em texto na página não influencia suas classificações orgânicas. As alterações, entretanto, devem ser codificadas permanentemente.

   Também é importante considerar a acessibilidade da sua página que você está testando. Se a página não estiver acessível para mecanismos de pesquisa e nunca tiver sido projetada para classificar em pesquisa orgânica, em primeiro lugar, nenhuma das considerações acima se aplica. Um exemplo é uma landing page dedicada para uma campanha de email.

O Google declara que seguir essas diretrizes &quot;deve resultar em pequeno ou nenhum impacto dos seus testes sobre o seu site nos resultados de pesquisa&quot;.

Além dessas diretrizes, a Google também fornece mais uma diretriz na documentação de sua ferramenta de Experiências com Conteúdo:

* &quot;Suas variações de páginas devem manter o espírito do conteúdo das suas páginas originais. Essas variações não devem alterar o significado da percepção geral do seu usuário sobre aquele conteúdo original&quot;.

A Google afirma, como um exemplo, que &quot;se a página original de um site é carregada com palavras-chave não relacionadas às combinações sendo exibidas aos usuários, nós podemos remover esse site do nosso índice.&quot;

Adobe acha que seria difícil alterar involuntariamente o significado do conteúdo original em variações de teste. No entanto, o Adobe recomenda estar ciente dos temas de palavra-chave em uma página e manter esses temas. Alterações no conteúdo da página, especialmente adicionando ou excluindo palavras-chave relevantes, pode resultar em alterações de classificação ao URL na pesquisa orgânica. A Adobe recomenda que você se envolva com seu parceiro SEO como parte do protocolo de teste.

## Bots {#bots}

O Adobe [!DNL Target] usa a métrica [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) &quot;isRobot&quot; para detectar bots conhecidos com base na string do agente do usuário transmitida no cabeçalho da solicitação.

>[!NOTE]
>
> Para solicitações [!DNL Server-Side], o valor passado no nó &quot;Contexto&quot; [da solicitação](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) recebe prioridade sobre a String do Agente do Usuário para detecção de bot.

O tráfego que é identificado como sendo gerado por um robô ainda serve o conteúdo. Os bots são tratados como um usuário comum para garantir que [!DNL Target] esteja em conformidade com as diretrizes de SEO. O uso do tráfego de bot pode distorcer testes A/B ou algoritmos de personalização se forem tratados como usuários normais. Portanto, se um bot conhecido for detectado na atividade [!DNL Target], o tráfego será tratado de forma ligeiramente diferente. A remoção do tráfego de bot fornece uma medida mais precisa da atividade do usuário.

Especificamente, para o tráfego de robô conhecido [!DNL Target] não:

* Cria ou recupera um perfil do visitante
* Registra os atributos de perfil ou executa scripts de perfil
* Procura segmentos do Adobe Audience Manager (AAM) (se aplicável)
* Use o tráfego de robô em modelagem e fornecimento de conteúdo personalizado para Recommendations, Público alvo automático, Automated Personalization ou Autoalocação de atividades
* Registra uma visita de atividade para relatório
* Registre os dados a serem enviados para a plataforma [!DNL Adobe Experience Cloud]
