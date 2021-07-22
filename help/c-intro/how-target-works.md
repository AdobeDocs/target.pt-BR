---
keywords: Adobe Experience Platform Web SDK;sdk web aep;sdk aep;otimização de mecanismo de pesquisa;otimização de mecanismo de pesquisa;seo;clusters de borda, clusters centrais;at.js;mbox.js;
description: Saiba mais sobre Adobe  [!DNL Target] works, including information about the [!DNL Target]  bibliotecas JavaScript (at.js e Experience Platform Web SDK), centros de dados da Adobe e testes de SEO.
title: Como o  [!DNL Target]  funciona?
feature: Visão geral
exl-id: 8a93e061-0be7-4ecc-b511-2210094547f2
source-git-commit: dd20791535e47c83d0f0ac60addfe0888748f86a
workflow-type: tm+mt
source-wordcount: '2532'
ht-degree: 100%

---

# Como o Adobe [!DNL Target] funciona

Saiba como o [!DNL Adobe Target] funciona, incluindo informações sobre o [!DNL Adobe Experience Platform Web SDK] e as bibliotecas do JavaScript (at.js e mbox.js). Este artigo também apresenta os vários tipos de atividades que você pode criar usando o [!DNL Target]. Você também pode saber mais sobre a rede de borda do [!DNL Target], a Otimização do mecanismo de pesquisa (SEO) e como o [!DNL Target] detecta bots.

## [!DNL Target] SDKs da Web da plataforma do e bibliotecas de JavaScript {#libraries}

[!DNL Target] integra-se a sites usando as bibliotecas do [!DNL Experience Platform Web SDK] ou do JavaScript:

* **Adobe Experience Platform Web SDK**: o [Experience Platform Web SDK](/help/c-implementing-target/c-implementing-target-for-client-side-web/aep-web-sdk.md) é uma nova biblioteca JavaScript do lado do cliente. O Experience Platform Web SDK permite que os clientes da [!DNL Adobe Experience Cloud] interajam com os vários serviços na [!DNL Experience Cloud] (incluindo o [!DNL Target]) por meio da [!DNL Experience Platform] Edge Network. O Adobe recomenda que todos os novos clientes do [!DNL Target] implementem o [!DNL Experience Platform Web SDK].
* **at.js:** A biblioteca at.js é uma biblioteca de implementação para [!DNL Target]. A biblioteca at.js melhora os tempos de carregamento de página de implementações da Web e fornece opções de implementações melhores para aplicativos de página única. A at.js é atualizada frequentemente com novos recursos. O Adobe recomenda que todos os clientes que usam at.js atualizem suas implementações para a [versão mais recente da at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md#reference_DBB5EDB79EC44E558F9E08D4774A0F7A).
* **mbox.js:** A biblioteca mbox.js é a biblioteca de implementação legada do [!DNL Target]. Não ha mais suporte para a biblioteca mbox.js após 31 de março de 2021.

Consulte o [!DNL Experience Platform Web SDK] ou at.js em todas as páginas do site. Por exemplo, você pode adicionar uma dessas bibliotecas ao seu cabeçalho global. Como alternativa, considere usar o [Adobe Platform Launch](https://experienceleague.adobe.com/docs/launch/using/overview.html?lang=pt-BR) para implementar o [!DNL Target].

Os seguintes recursos contêm informações detalhadas para ajudar a implementar o Experience Platform Web SDK ou a at.js:

* [Extensão do Adobe Experience Platform Web SDK](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/aep-extension/overview.html?lang=pt-BR#configure-the-aep-web-sdk-extension)
* [Implementar o  [!DNL Target]  usando o Adobe Experience Platform Launch](/help/c-implementing-target/c-implementing-target-for-client-side-web/how-to-deployatjs/cmp-implementing-target-using-adobe-launch.md)

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

Consulte [Criar um teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/test-create-ab.md) para obter mais informações.

### [!UICONTROL Alocação automática]

[!UICONTROL A alocação automática] identifica um vencedor entre duas ou mais experiências. [!UICONTROL A alocação automática] realoca automaticamente mais tráfego para a experiência vencedora, o que ajuda a aumentar as conversões enquanto o teste continua a ser executado e aprendido.

Consulte [[!UICONTROL Alocação automática]](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md#concept_A1407678796B4C569E94CBA8A9F7F5D4) para obter mais informações.

### [!UICONTROL Direcionamento automático] (AT)

O direcionamento automático usa aprendizagem de máquina avançada para selecionar várias experiências definidas pelo profissional de marketing com desempenho elevado. O direcionamento automático veicula a experiência mais personalizada para cada visitante. A entrega de experiência é baseada em perfis de clientes individuais e no comportamento de visitantes anteriores com perfis semelhantes. Use o direcionamento automático para personalizar o conteúdo e gerar conversões.

Consulte [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md) para obter mais informações.

### [!UICONTROL Personalização automatizada] (AP)

A Automated Personalization (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançado para combinar diferentes variações de oferta a cada visitante. A entrega de experiência é baseada em perfis de clientes individuais para personalizar o conteúdo e aumentar o incentivo.

Consulte [Automated Personalization](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) para obter mais informações.

### [!UICONTROL Direcionamento de experiência] (XT)

O Direcionamento de experiência (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.

O Direcionamento de experiência, incluindo a geolocalização, é algo valioso para definir regras que direcionem uma experiência ou conteúdo específico para um público em particular. Várias regras podem ser definidas em uma atividade para levar diferentes variações de conteúdo para públicos-alvo diferentes. Quando visitantes acessam seu site, o direcionamento de experiência (XT) os avalia para determinar se eles atendem os critérios que você definiu. Se cumprirem os critérios, eles entram na atividade e a experiência projetada para o público-alvo qualificado é exibida. Você pode criar experiências para diversos públicos-alvo dentro de uma única atividade.

Consulte [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md#task_A53DF336CB9F4D7BB87EF2106099EFC4) para obter mais informações.

### [!UICONTROL Teste multivariado] (MVT)

O Multivariate Testing (MVT) compara combinações de ofertas entre elementos em uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico. O MVT ajuda a identificar qual elemento afeta mais o sucesso da atividade.

Consulte [Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md#concept_628695CDC71B449B8DCC2F5654C11499) para obter mais informações.

### [!UICONTROL Recommendations]

As atividades do Recommendations exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base em atividades do usuário anteriores. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.

Consulte [Recommendations](/help/c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) para obter mais informações.

## A rede de borda {#concept_0AE2ED8E9DE64288A8B30FCBF1040934}

A &quot;borda&quot; é uma arquitetura de fornecimento distribuída geograficamente que garante os tempos de resposta ideais para visitantes que solicitem o conteúdo, independentemente de sua localização no mundo.

Para melhorar os tempos de resposta, a borda [!DNL Target] hospeda somente a lógica de atividade, os perfis em cache e as informações da oferta.

Bancos de dados de atividade e conteúdo, dados do [!DNL Analytics], APIs e interfaces de usuário dos profissionais de marketing são abrigados nos clusters centrais da Adobe. As atualizações são enviadas para os nós de bordas do [!DNL Target]. Os clusters centrais e nós de borda são sincronizados automaticamente para atualizar continuamente os dados de atividade em cache. Como a modelagem 1:1 também é armazenada em cada borda, as solicitações mais complexas também podem ser processadas na borda.

Cada nó de borda tem todas as informações necessárias para responder à solicitação de conteúdo do visitante e rastrear os dados de análise da solicitação. As solicitações do usuário são roteadas para o nó de borda mais próximo.

Para obter mais informações, consulte o white paper [Visão geral da segurança no Adobe Target](https://www.adobe.com/content/dam/cc/en/security/pdfs/AdobeTargetSecurityOverview.pdf).

A solução [!DNL Target] é hospedada em data centers próprios e alugados pela Adobe no mundo inteiro.

Os locais do cluster central contêm um centro de coleta de dados e um centro de processamento de dados. Os locais de cluster de bordam contêm apenas um centro de coleta de dados. Cada conjunto de relatórios é atribuído a um centro de processamento de dados específico.

Os dados de atividade do site do cliente são coletados pelo mais próximo de sete clusters de borda. Esses dados são direcionados para o destino de cluster central predeterminado de um cliente (um dos três locais: Oregon, Dublin, Singapura) para processamento. Os dados do perfil do visitante são armazenados no cluster de borda mais próximo do visitante do site. Os locais dos clusters de borda incluem os locais centrais de cluster, além de Virgínia, Mumbai, Sydney, e Tóquio.

Em vez de responder a todas as solicitações de direcionamento de um único local, as solicitações são processadas pelo cluster de borda mais próximo do visitante. Esse processo ajuda a reduzir o impacto do tempo de deslocamento da Internet/rede.

![Mapa mostrando os diferentes tipos de servidores do Target](/help/c-intro/assets/target-servers.png)

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

Você pode adicionar clusters de borda do [!DNL Target] à lista de permissões, se desejar. Para obter mais informações, consulte [lista de permissões de nós de borda do Target](/help/c-implementing-target/c-considerations-before-you-implement-target/allowlist-edges.md).

## Experiência do usuário protegida {#concept_40A5E781D90A41E4955F80EA9E5F8F96}

A Adobe assegura que a disponibilidade e o desempenho da infraestrutura da definição de metas tenham a maior confiabilidade possível. No entanto, um detalhamento de comunicação entre o navegador de um visitante e os servidores da Adobe pode causar uma interrupção na entrega de conteúdo.

Como proteção contra interrupções do serviço e problemas de conectividade, todos os locais são configurados para incluir o conteúdo padrão (definido pelo cliente). Esse conteúdo padrão é exibido se o navegador do usuário não puder se conectar ao [!DNL Target].

Nenhuma alteração será feita na página se o navegador do usuário não puder se conectar em um período de tempo limite definido (por padrão, 15 segundos). Se esse tempo limite for atingido, o conteúdo padrão do local será exibido.

A Adobe protege a experiência do usuário por otimizar e salvaguardar o desempenho.

* A Adobe assegura referências de desempenho com base em padrões do setor, que são garantidos pelo Contrato de nível de serviço da Adobe.
* A rede Edge assegura a entrega de dados em tempo hábil.
* A Adobe emprega uma abordagem em múltiplas camadas para proteger seus aplicativos, fornecendo o maior nível de disponibilidade e confiabilidade para os clientes.
* O [!DNL Target] Consulting oferece assistência na implementação e suporte contínuo ao produto.

## Teste compatível com a Otimização do mecanismo de pesquisa (SEO) {#concept_C0C865663CAB4251B66A1F250FD25E6A}

O [!DNL Adobe Target] está alinhado às diretrizes de mecanismo de busca para teste.

O Google incentiva os usuários a testarem. O Google declara em sua documentação que os testes A/B e o Multivariate Testing não prejudicam as classificações dos mecanismos de pesquisa orgânica se você seguir determinadas diretrizes.

Para obter mais informações, consulte os seguintes recursos da Google:

* [Testes de site e pesquisa Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html)
* [Experimentos e cloaking](https://support.google.com/analytics/answer/2576845?hl=pt-BR&amp;ref_topic=1745207)

As diretrizes foram apresentadas em uma publicação do [Blog da Central do Webmaster da Google](https://webmasters.googleblog.com/2012/08/website-testing-google-search.html). Embora a publicação seja datada de 2012, ela continua sendo a declaração mais recente da Google sobre o assunto e as diretrizes continuam relevantes.

* **Sem cloaking**: o cloaking mostra um conjunto de conteúdo para seus usuários e um conjunto diferente de conteúdo para os bots do mecanismo de pesquisa. O cloaking é realizado ao identificar bots especificamente e enviar conteúdo diferente propositalmente.

   O [!DNL Target], como uma plataforma, foi configurado para tratar bots de mecanismo de pesquisa como qualquer usuário. Como resultado, os bots podem ser incluídos em atividades caso sejam selecionados aleatoriamente e &quot;vejam&quot; as variações do teste.

* **Use rel=&quot;canonical&quot;**: algumas vezes, um teste A/B precisa ser configurado utilizando URLs diferentes para as variações. Nesses casos, todas as variações devem conter uma tag `rel="canonical"` que faça referência à URL original (controle). Por exemplo, suponha que a Adobe esteja testando sua página inicial usando URLs diferentes para cada variação. A tag canônica a seguir para a página inicial seria inserida na tag `<head>` para cada uma das variações:

   `<link rel="canonical" href="https://www.adobe.com" />`

* **Use redirecionamentos 302 (temporário) redirects**: Nos casos em que são utilizados URLs individuais para as variações de páginas em um teste, o Google recomenda o uso de um redirecionamento 302 a fim de direcionar o tráfego para as variações de teste. O redirecionamento 302 informa aos mecanismos de pesquisa que o redirecionamento é temporário e está ativo somente enquanto o teste estiver em execução.

   Um redirecionamento 302 é um redirecionamento no lado do servidor e o [!DNL Target], juntamente com a maioria dos provedores de otimização, utiliza as capacidades do lado do cliente. Portanto, essa é uma área em que o [!DNL Target] não está em total conformidade com as recomendações do Google. Isso, entretanto, só afeta uma pequena fração dos testes. A abordagem padrão para execução de testes por meio do [!DNL Target] pede a alteração do conteúdo em um único URL, então não há necessidade de redirecionamentos. Há casos em que os clientes precisam usar vários URLs para representar suas variações no teste. Nesses casos, o [!DNL Target] usa o comando `window.location` do JavaScript. Esse comando direciona os usuários para variações do teste, o que não indica explicitamente se o redirecionamento é um 301 ou 302.

   O Adobe continua a procurar soluções viáveis para se alinhar completamente às diretrizes do mecanismo de pesquisa. Para os clientes que devem usar URLs separados para testes, a Adobe está confiante de que a implementação adequada das tags canônicas diminui o risco associado a essa abordagem.

* **Execute experimentos somente conforme necessário**: acreditamos que &quot;conforme necessário&quot; é o quanto for necessário para atingir significância estatística. [!DNL Target] [O fornece práticas recomendadas](https://experienceleague.adobe.com/tools/calculator/testcalculator.html?lang=pt-BR) para determinar quando seu teste atingiu este ponto. A Adobe recomenda que você incorpore a implementação codificada permanentemente de testes vencedores no seu fluxo de trabalho de testes e aloque os recursos apropriados.

   A utilização da plataforma [!DNL Target] para &quot;publicar&quot; testes vencedores não é recomendada como uma solução permanente. Se o teste vencedor for publicado para 100% dos usuários em 100% das vezes, essa abordagem poderá ser usada enquanto o processo de codificação rígida do teste vencedor for concluído.

   É importante levar em consideração também o que seu teste alterou. Apenas atualizar a cor de botões ou outros itens de menor importância não baseados em texto na página não exercerá qualquer influência sobre suas classificações orgânicas. As alterações, entretanto, devem ser codificadas permanentemente.

   Também é importante considerar a acessibilidade da sua página que você está testando. Se a página não estiver acessível para mecanismos de pesquisa e nunca tiver sido projetada para classificar em pesquisa orgânica, nenhuma das considerações acima se aplicam. Um exemplo é uma página de aterrissagem dedicada a uma campanha de email.

O Google declara que seguir essas diretrizes &quot;deve resultar em pequeno ou nenhum impacto dos seus testes sobre o seu site nos resultados de pesquisa&quot;.

Além dessas diretrizes, a Google também fornece mais uma diretriz na documentação de sua ferramenta de Experiências com Conteúdo:

* &quot;Suas variações de páginas devem manter o espírito do conteúdo das suas páginas originais. Essas variações não devem alterar o significado da percepção geral do seu usuário sobre aquele conteúdo original&quot;.

A Google afirma, como um exemplo, que &quot;se a página original de um site é carregada com palavras-chave não relacionadas às combinações sendo exibidas aos usuários, nós podemos remover esse site do nosso índice.&quot;

A Adobe acha que seria difícil alterar involuntariamente o significado do conteúdo original nas variações de teste. No entanto, a Adobe recomenda estar ciente dos temas de palavras-chave em uma página e mantê-los. Alterações no conteúdo da página, especialmente adicionando ou excluindo palavras-chave relevantes, pode resultar em alterações de classificação ao URL na pesquisa orgânica. A Adobe recomenda que você envolva seu parceiro de SEO como parte de protocolo de testes.

## Bots {#bots}

O Adobe [!DNL Target] usa a métrica &quot;isRobot&quot; do [DeviceAtlas](https://deviceatlas.com/device-data/user-agent-tester/) para detectar bots conhecidos com base na sequência de agente do usuário transmitida no cabeçalho da solicitação.

>[!NOTE]
>
> Para solicitações de [!DNL Server-Side], o valor transmitido no [nó &quot;Contexto&quot; da solicitação](https://developers.adobetarget.com/api/delivery-api/#tag/Delivery-API) tem prioridade sobre a sequência de agente do usuário para detecção de bot.

O tráfego identificado como sendo gerado por um bot ainda recebe conteúdo. Os bots são tratados como um usuário regular para garantir que o [!DNL Target] esteja em conformidade com as diretrizes de SEO. O uso do tráfego de bot pode distorcer testes A/B ou algoritmos de personalização se forem tratados como usuários normais. Portanto, se um bot conhecido for detectado na atividade do [!DNL Target], o tráfego será tratado de maneira um pouco diferente. A remoção do tráfego de bot fornece uma medida mais precisa da atividade do usuário.

Especificamente para o tráfego de bot conhecido, o [!DNL Target] não:

* Cria ou recupera um perfil do visitante
* Registra os atributos de perfil ou executa scripts de perfil
* Procura segmentos do Adobe Audience Manager (AAM) (se aplicável)
* Use o tráfego de bots na modelagem e veiculação de conteúdo personalizado para atividades do Recommendations, Auto-Target, Automated Personalization ou [!UICONTROL Auto-Allocate]
* Registra uma visita de atividade para relatório
* Registra dados a serem enviados para a plataforma da [!DNL Adobe Experience Cloud]
