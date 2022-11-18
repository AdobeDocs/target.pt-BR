---
keywords: Adobe Experience Platform Web SDK;sdk web aep;sdk aep;otimização de mecanismo de pesquisa;otimização de mecanismo de pesquisa;seo;clusters de borda, clusters centrais;at.js;mbox.js;
description: Saiba como o  [!DNL Adobe Target]  funciona, incluindo informações sobre bibliotecas JavaScript (SDK da Web do AEP e at.js), data centers da Adobe, testes de SEO e bots.
title: Como o  [!DNL Target]  funciona?
feature: Overview
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: 4564e0b95bbd19f20c75e5e83d452d12a5403083
workflow-type: ht
source-wordcount: '2583'
ht-degree: 100%

---

# Como o [!DNL Adobe Target] funciona

Saiba como o [!DNL Adobe Target] funciona, incluindo informações sobre as bibliotecas de JavaScript ([!DNL Adobe Experience Platform Web SDK] e at.js). Este artigo também apresenta os vários tipos de atividades que você pode criar usando o [!DNL Target]. Você também pode saber mais sobre a rede de borda do [!DNL Target], a Otimização do mecanismo de pesquisa (SEO) e como o [!DNL Target] detecta bots.

## Bibliotecas de JavaScript do [!DNL Adobe Target] {#libraries}

O [!DNL Target] integra-se a sites usando o [!DNL Experience Platform Web SDK] ou a at.js:

* **[!DNL Adobe Experience Platform Web SDK]:** O [SDK da Web da Experience Platform](https://developer.adobe.com/target/implement/client-side/aep-web-sdk/){target=_blank} é uma nova biblioteca de JavaScript do lado do cliente. O [!DNL Experience Platform Web SDK] permite que os clientes da [!DNL Adobe Experience Cloud] interajam com os vários serviços na [!DNL Experience Cloud] (incluindo o [!DNL Target]) por meio da rede de borda da [!DNL Experience Platform]. A [!DNL Adobe] recomenda que todos os novos clientes do [!DNL Target] implementem o [!DNL Experience Platform Web SDK].
* **at.js:** A biblioteca at.js é uma biblioteca de implementação para [!DNL Target]. A biblioteca at.js melhora os tempos de carregamento de página de implementações da Web e fornece opções de implementações melhores para aplicativos de página única. A at.js é atualizada frequentemente com novos recursos. A [!DNL Adobe] recomenda que todos os clientes que usam a at.js atualizem suas implementações para a [versão mais recente da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.

>[!NOTE]
>
>A biblioteca mbox.js é a biblioteca de implementação herdada do [!DNL Target]. Não há mais suporte para a biblioteca mbox.js após 31 de março de 2021. Atualize para o SDK da Web da Experience Platform (preferencial) ou para a versão mais recente da at.js.

Consulte o [!DNL Experience Platform Web SDK] ou at.js em todas as páginas do site. Por exemplo, você pode adicionar uma dessas bibliotecas ao seu cabeçalho global. Como alternativa, considere usar [tags na Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=pt-BR) para implementar o [!DNL Target].

Os seguintes recursos contêm informações detalhadas para ajudar você a implementar o [!DNL Experience Platform Web SDK] ou a at.js:

* [[!DNL Adobe Experience Platform Web SDK] extensão](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/sdk/overview.html?lang=pt-BR)
* [Implementar o  [!DNL Target]  usando a  [!DNL Adobe Experience Platform]](https://developer.adobe.com/target/implement/client-side/atjs/how-to-deployatjs/implement-target-using-adobe-launch/)

Cada vez que um visitante solicita uma página que foi otimizada para [!DNL Target], uma solicitação é enviada para o sistema de direcionamento. A solicitação ajuda a determinar qual conteúdo será enviado para esse visitante. Esse processo ocorre em tempo real. Esse processo ocorre em tempo real. Sempre que uma página é carregada, uma solicitação para o conteúdo é feita e preenchida pelo sistema. O conteúdo é regulado pelas leis de atividades e experiências controladas pelo comerciante e direcionado para o visitante individual do site. O conteúdo é disponibilizado para cada visitante do site com maior probabilidade de responder, interagir ou comprar. O conteúdo personalizado ajuda a maximizar as taxas de resposta, as taxas de aquisição e a receita.

No [!DNL Target], cada elemento na página faz parte de uma única experiência para a página inteira. Cada experiência pode incluir vários elementos na página.

O conteúdo exibido para os visitantes depende do tipo de atividade que você cria:

### [!UICONTROL Teste A/B]

O conteúdo exibido em um teste A/B básico é escolhido aleatoriamente a partir das experiências atribuídas à atividade. É possível atribuir as porcentagens de alocação de tráfego para cada experiência. Como resultado dessa divisão aleatória de tráfego, pode ser necessário muito tráfego inicial mesmo antes das porcentagens aparecerem. Por exemplo, se você criar duas experiências, a inicial será escolhida aleatoriamente. Se houver pouco tráfego, é possível que a porcentagem de visitantes venha a tender para uma experiência. À medida que o tráfego aumenta, as porcentagens ficam iguais.

É possível especificar as metas de porcentagem para cada experiência. Nesse caso, um número aleatório será gerado e usado para escolher a experiência que será exibida. As porcentagens resultantes talvez não correspondam exatamente às metas especificadas, mas um maior tráfego significa que as experiências deverão ser divididas em maior harmonia com as metas-alvo.

1. Um cliente solicita uma página do seu servidor e ela é exibida no navegador.
1. Um cookie primárico é configurado no navegador do cliente para armazenar o comportamento do cliente.
1. A página chama o sistema de direcionamento.
1. O conteúdo é exibido com base nas regras da sua atividade.

Consulte [Criar um teste A/B](/help/main/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) para obter mais informações.

### [!UICONTROL Alocação automática]

[!UICONTROL A alocação automática] identifica um vencedor entre duas ou mais experiências. [!UICONTROL A alocação automática] realoca automaticamente mais tráfego para a experiência vencedora, o que ajuda a aumentar as conversões enquanto o teste continua a ser executado e aprendido.

Consulte [[!UICONTROL Alocação automática]](/help/main/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) para obter mais informações.

### [!UICONTROL Direcionamento automático] (AT)

O [!UICONTROL direcionamento automático] usa aprendizagem de máquina avançada para selecionar várias experiências definidas pelo profissional de marketing com desempenho elevado. O [!UICONTROL direcionamento automático] entrega a experiência mais personalizada para cada visitante. A entrega de experiência é baseada em perfis de clientes individuais e no comportamento de visitantes anteriores com perfis semelhantes. Use o [!UICONTROL direcionamento automático] para personalizar o conteúdo e gerar conversões.

Consulte [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) para obter mais informações.

### [!UICONTROL Personalização automatizada] (AP)

A [!UICONTROL Automated Personalization] (AP) combina ofertas ou mensagens e usa aprendizado de máquina avançado para combinar diferentes variações de oferta para cada visitante. A entrega de experiência é baseada em perfis de clientes individuais para personalizar o conteúdo e aumentar o incentivo.

Consulte [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) para obter mais informações.

### [!UICONTROL Direcionamento de experiência] (XT)

O [!UICONTROL Direcionamento de experiência] (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.

O [!UICONTROL Direcionamento de experiência], incluindo a geolocalização, é algo valioso para definir regras que direcionem uma experiência ou conteúdo específico para um público em particular. Várias regras podem ser definidas em uma atividade para levar diferentes variações de conteúdo para públicos-alvo diferentes. Quando visitantes acessam o seu site, o [!UICONTROL direcionamento de experiência] (XT) os avalia para determinar se eles atendem aos critérios que você definiu. Se cumprirem os critérios, eles entram na atividade e a experiência projetada para o público-alvo qualificado é exibida. Você pode criar experiências para diversos públicos-alvo dentro de uma única atividade.

Consulte [Direcionamento de experiência](/help/main/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) para obter mais informações.

### [!UICONTROL Teste multivariado] (MVT)

O [!UICONTROL teste multivariado] (MVT) compara combinações de ofertas entre elementos de uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico. O MVT ajuda a identificar qual elemento afeta mais o sucesso da atividade.

Consulte [Teste multivariado](/help/main/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) para obter mais informações.

### [!UICONTROL Recommendations]

As atividades do [!UICONTROL Recommendations] exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base em atividades do usuário anteriores. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.

Consulte [Recommendations](/help/main/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) para obter mais informações.

## A rede de borda {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

Uma “borda” é uma arquitetura de fornecimento distribuída geograficamente que garante tempos de resposta ideais para visitantes que solicitam conteúdo, independentemente de sua localização no mundo.

Para melhorar os tempos de resposta, a borda [!DNL Target] hospeda somente a lógica de atividade, os perfis em cache e as informações da oferta.

Bancos de dados de atividade e conteúdo, dados do [!DNL Analytics], APIs e interfaces de profissionais de marketing são abrigados nos clusters centrais da Adobe. As atualizações são enviadas para os nós de bordas do [!DNL Target]. Os clusters centrais e nós de borda são sincronizados automaticamente para atualizar continuamente os dados de atividade em cache. Como a modelagem 1:1 também é armazenada em cada borda, as solicitações mais complexas também podem ser processadas na borda.

Cada nó de borda tem todas as informações necessárias para responder à solicitação de conteúdo do visitante e rastrear os dados de análise da solicitação. As solicitações do usuário são roteadas para o nó de borda mais próximo.

Para obter mais informações, consulte o white paper [Visão geral da segurança no Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

A solução [!DNL Target] é hospedada em data centers próprios e alugados pela Adobe no mundo inteiro.

Os locais do cluster central contêm um centro de coleta de dados e um centro de processamento de dados. Os locais de cluster de bordam contêm apenas um centro de coleta de dados. Cada conjunto de relatórios é atribuído a um centro de processamento de dados específico.

Os dados de atividade do site do cliente são coletados pelo mais próximo de sete clusters de borda. Esses dados são direcionados para o destino de cluster central predeterminado de um cliente (um dos três locais: Oregon, Dublin, Singapura) para processamento. Os dados do perfil do visitante são armazenados no cluster de borda mais próximo do visitante do site. Os locais dos clusters de borda incluem os locais centrais de cluster, além de Virgínia, Mumbai, Sydney, e Tóquio.

Em vez de responder a todas as solicitações de direcionamento de um único local, as solicitações são processadas pelo cluster de borda mais próximo do visitante. Esse processo ajuda a reduzir o impacto do tempo de deslocamento da Internet/rede.

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
>No momento, o [!DNL Adobe Target] não tem um cluster de borda na China e o desempenho do visitante permanece limitado para clientes do [!DNL Target] na China. Devido ao firewall e à falta de clusters de borda no país, as experiências dos sites com [!DNL Target] implantado podem ser afetadas. As experiências podem ser renderizadas lentamente e os carregamentos de página podem ser afetados. Além disso, os profissionais de marketing podem identificar latência ao usar a interface de criação do [!DNL Target].

Você pode adicionar clusters de borda do [!DNL Target] à lista de permissões, se desejar. Para obter mais informações, consulte [lista de permissões de nós de borda do Target](https://developer.adobe.com/target/before-implement/privacy/allowlist-edges/){target=_blank}.

## Experiência do usuário protegida {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

A [!DNL Adobe] assegura que a disponibilidade e o desempenho da infraestrutura de direcionamento tenham a maior confiabilidade possível. No entanto, um detalhamento da comunicação entre o navegador de um visitante e os servidores da [!DNL Adobe] pode causar uma interrupção na entrega de conteúdo.

Como proteção contra interrupções do serviço e problemas de conectividade, todos os locais são configurados para incluir o conteúdo padrão (definido pelo cliente). Esse conteúdo padrão é exibido se o navegador do usuário não puder se conectar ao [!DNL Target].

Nenhuma alteração será feita na página se o navegador do usuário não puder se conectar em um período de tempo limite definido (por padrão: 15 segundos). Se esse tempo limite for atingido, o conteúdo padrão do local será exibido.

A [!DNL Adobe] protege a experiência do usuário por otimizar e salvaguardar o desempenho.

* A [!DNL Adobe] assegura referências de desempenho com base em padrões do setor, que são garantidos pelo Contrato de nível de serviço da Adobe.
* A rede de borda assegura a entrega de dados em tempo hábil.
* A [!UICONTROL Adobe] emprega uma abordagem de múltiplas camadas para proteger seus aplicativos, fornecendo o maior nível de disponibilidade e confiabilidade para os clientes.
* O [!DNL Target] Consulting oferece assistência na implementação e suporte contínuo ao produto.

## Teste compatível com a Otimização do mecanismo de pesquisa (SEO) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

O [!DNL Adobe Target] está alinhado às diretrizes de mecanismo de busca para teste.

O Google incentiva os usuários a testarem. O Google declara em sua documentação que os testes A/B e o [!UICONTROL teste multivariado] não prejudicam as classificações dos mecanismos de pesquisa orgânica se determinadas diretrizes forem obedecidas.

Para obter mais informações, consulte os seguintes recursos da Google:

* [Testes de site e pesquisa Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentos e cloaking](https://support.google.com/analytics/answer/2576845?hl=pt-BR&amp;ref_topic=1745207)

As diretrizes foram apresentadas em uma publicação do [Blog da Central do Webmaster da Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Embora a publicação seja datada de 2012, ela continua sendo a declaração mais recente da Google sobre o assunto e as diretrizes continuam relevantes.

* **Sem cloaking**: o cloaking mostra um conjunto de conteúdo para seus usuários e um conjunto diferente de conteúdo para os bots do mecanismo de pesquisa. O cloaking é realizado ao identificar bots especificamente e enviar conteúdo diferente propositalmente.

   O [!DNL Target], como uma plataforma, foi configurado para tratar bots de mecanismo de pesquisa como qualquer usuário. Como resultado, os bots podem ser incluídos em atividades caso sejam selecionados aleatoriamente e “vejam” as variações do teste.

* **Use rel=&quot;canonical&quot;**: algumas vezes, um teste A/B precisa ser configurado utilizando URLs diferentes para as variações. Nesses casos, todas as variações devem conter uma tag `rel="canonical"` que faça referência à URL original (controle). Por exemplo, suponha que a [!DNL Adobe] esteja testando sua página inicial usando URLs diferentes para cada variação. A tag canônica a seguir para a página inicial seria inserida na tag `<head>` para cada uma das variações:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Use redirecionamentos 302 (temporário) redirects**: Nos casos em que são utilizados URLs individuais para as variações de páginas em um teste, o Google recomenda o uso de um redirecionamento 302 a fim de direcionar o tráfego para as variações de teste. O redirecionamento 302 informa aos mecanismos de pesquisa que o redirecionamento é temporário e está ativo somente enquanto o teste estiver em execução.

   Um redirecionamento 302 é um redirecionamento no lado do servidor e o [!DNL Target], juntamente com a maioria dos provedores de otimização, utiliza as capacidades do lado do cliente. Portanto, essa é uma área em que o [!DNL Target] não está em total conformidade com as recomendações do Google. Isso, entretanto, só afeta uma pequena fração dos testes. A abordagem padrão para execução de testes por meio do [!DNL Target] pede a alteração do conteúdo em um único URL, então não há necessidade de redirecionamentos. Há casos em que os clientes precisam usar vários URLs para representar suas variações no teste. Nesses casos, o [!DNL Target] usa o comando `window.location` do JavaScript. Esse comando direciona os usuários para variações do teste, o que não indica explicitamente se o redirecionamento é um 301 ou 302.

   O [!DNL Adobe] continua a procurar soluções viáveis para se alinhar completamente às diretrizes do mecanismo de pesquisa. Para os clientes que devem usar URLs separados para testes, a [!DNL Adobe] está confiante de que a implementação adequada das tags canônicas diminui o risco associado a essa abordagem.

* **Execute experimentos somente enquanto for necessário**: a [!DNL Adobe] acredita que “conforme necessário” é o quanto for necessário para atingir significância estatística. O [!DNL Target] fornece práticas recomendadas e a [Calculadora de tamanho da amostra](/help/main/c-activities/t-test-ab/sample-size-determination.md#section_6B8725BD704C4AFE939EF2A6B6E834E6) do [!DNL Adobe Target] para determinar quando seu teste atingiu esse ponto. A [!DNL Adobe] recomenda que você incorpore a implementação codificada permanentemente de testes vencedores no seu fluxo de trabalho de testes e aloque os recursos apropriados.

   A utilização da plataforma [!DNL Target] para “publicar” testes vencedores não é recomendada como uma solução permanente. Se o teste vencedor for publicado para 100% dos usuários em 100% das vezes, essa abordagem poderá ser usada enquanto o processo de codificação rígida do teste vencedor for concluído.

   É importante levar em consideração também o que seu teste alterou. Apenas atualizar a cor de botões ou outros itens de menor importância não baseados em texto na página não exercerá qualquer influência sobre suas classificações orgânicas. As alterações, entretanto, devem ser codificadas permanentemente.

   Também é importante considerar a acessibilidade da sua página que você está testando. Se a página não estiver acessível para mecanismos de pesquisa e nunca tiver sido projetada para classificar em pesquisa orgânica, nenhuma das considerações acima se aplicam. Um exemplo é uma página de aterrissagem dedicada a uma campanha de email.

O Google declara que seguir essas diretrizes “deve resultar em pequeno ou nenhum impacto dos seus testes sobre o seu site nos resultados de pesquisa”.

Além dessas diretrizes, a Google também fornece mais uma diretriz na documentação de sua ferramenta de Experiências com Conteúdo:

* “Suas variações de páginas devem manter o espírito do conteúdo das suas páginas originais. Essas variações não devem alterar o significado da percepção geral do seu usuário sobre aquele conteúdo original”.

A Google afirma, como um exemplo, que “se a página original de um site é carregada com palavras-chave não relacionadas às combinações sendo exibidas aos usuários, nós podemos remover esse site do nosso índice.”

A [!UICONTROL Adobe] acha que seria difícil alterar involuntariamente o significado do conteúdo original nas variações de teste. No entanto, a [!UICONTROL Adobe] recomenda estar ciente dos temas de palavras-chave em uma página e mantê-los. Alterações no conteúdo da página, especialmente adicionando ou excluindo palavras-chave relevantes, pode resultar em alterações de classificação ao URL na pesquisa orgânica. A [!DNL Adobe] recomenda que você envolva seu parceiro de SEO como parte de protocolo de testes.

## Bots {#bots}

O Adobe [!DNL Target] usa a métrica “isRobot” do [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) para detectar bots conhecidos com base na sequência de agente do usuário transmitida no cabeçalho da solicitação.

>[!NOTE]
>
> Para solicitações de [!DNL Server-Side], o valor transmitido no [nó “Contexto” da solicitação](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) tem prioridade sobre a sequência de agente do usuário para detecção de bot.

O tráfego identificado como sendo gerado por um bot ainda recebe conteúdo. Os bots são tratados como um usuário regular para garantir que o [!DNL Target] esteja em conformidade com as diretrizes de SEO. O uso do tráfego de bot pode distorcer testes A/B ou algoritmos de personalização se forem tratados como usuários normais. Portanto, se um bot conhecido for detectado na atividade do [!DNL Target], o tráfego será tratado de maneira um pouco diferente. A remoção do tráfego de bot fornece uma medida mais precisa da atividade do usuário.

Especificamente para o tráfego de bot conhecido, o [!DNL Target] não:

* Cria ou recupera um perfil do visitante
* Registra os atributos de perfil ou executa scripts de perfil
* Procura segmentos do [!DNL Adobe Audience Manager] (AAM) (se aplicável)
* Use o tráfego de bots na modelagem e veiculação de conteúdo personalizado para atividades do [!UICONTROL Recommendations], [!UICONTROL Auto-Target], [!UICONTROL Automated Personalization] ou [!UICONTROL Auto-Allocate]
* Registra uma visita de atividade para relatório
* Registra dados a serem enviados para a plataforma da [!DNL Adobe Experience Cloud]

Para tráfego de bot conhecido ao usar o [!UICONTROL Analytics for Target] (A4T), o [!DNL Target] não:

* Envia eventos para o [!DNL Analytics]

Para tráfego de bot conhecido ao usar o registro do lado do cliente, o [!DNL Target] não retorna:

* carga tnta
