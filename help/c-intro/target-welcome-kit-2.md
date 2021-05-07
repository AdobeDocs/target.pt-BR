---
keywords: kit de boas-vindas; kit de boas-vindas do target; introdução; introdução do
description: Obtenha uma visão geral do Adobe Target. Saiba mais sobre atividades, canais, implementação, integrações disponíveis e muito mais.
title: Onde posso encontrar uma introdução de alto nível ao Target?
feature: Visão geral
exl-id: 19238d4c-b7e1-418d-96e5-c46a3769f7bf
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2520'
ht-degree: 99%

---

# Capítulo 2: Adobe [!DNL Target] de relance

Antes de começar a usar o [!DNL Adobe Target], pode ser útil obter uma visão geral de alto nível da solução. Neste capítulo, conheça os principais recursos da solução, os pontos de contato da marca nos quais você pode usá-la, as opções de implementação, os recursos e os workflows importantes da interface do usuário, os recursos de governança e sua função no [!DNL Adobe Experience Cloud] em geral. A menos que sejam descritos como recursos do [!DNL Adobe Target Premium], os itens descritos neste capítulo estão disponíveis com o [!DNL Adobe Target Premium] e o [!DNL Adobe Target Standard]. Para obter mais informações sobre o Target, consulte [Introdução ao Target](/help/c-intro/intro.md).

## Recursos e atividades

Teste e personalização são os dois tipos amplos de recursos que o [!DNL Target] oferece e que podem ser utilizados ao criar uma &quot;atividade&quot; no [!DNL Target]. Você pode ver o termo &quot;teste&quot; usado intercambialmente com &quot;otimização&quot; e o termo &quot;personalização&quot; usado alternadamente com &quot;direcionamento&quot;.

Em uma atividade de teste, você compara uma variação de uma experiência digital com uma ou mais variações para descobrir aquela que faz com que o maior número de visitantes realize a ação desejada. O [!DNL Target] oferece os seguintes recursos de teste: Teste A/B, Multivariate testing (MVT) e alocação automática.

Com uma atividade de personalização, você fornece uma experiência digital personalizada para um grupo específico de visitantes ou para cada visitante individual. O [!DNL Target] oferece estes recursos de personalização: Direcionamento de experiência, Direcionamento automático, Automated Personalization e Recommendations.

Para obter uma compreensão mais detalhada de quando e como usar cada recurso, consulte [Tipos de atividade do Target](/help/c-activities/target-activities-guide.md).

| Tipo de atividade | Detalhes |
| --- | --- |
| Teste A/B | Compare duas ou mais variações de suas experiências ou ofertas no seu site ou outro ponto de contato de cliente digital para ver qual variação melhora as principais medidas de negócios durante um período de teste pré-especificado. Os testes A/B são adequados para grandes alterações, como novos layouts de página da Web, diferentes abordagens da navegação do site ou tratamentos drasticamente diferentes de elementos individuais de uma experiência digital, como cópia, imagens e botões de chamada para ação. [Saiba mais](/help/c-activities/t-test-ab/test-ab.md). |
| Alocação automática | Identifique a experiência de melhor desempenho entre duas ou mais experiências e realoque automaticamente mais tráfego para o vencedor a fim de aumentar as conversões enquanto o teste continua a ser executado e a aprender. Usa a inteligência artificial do [!DNL Adobe Sensei]. [Saiba mais](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| Direcionamento automático<br>(Premium) | Aproveite a IA do Adobe Sensei no [!DNL Target] para determinar e fornecer a melhor experiência de vários visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis semelhantes. O Direcionamento automático permite a personalização em escala. [Saiba mais](/help/c-activities/auto-target/auto-target-to-optimize.md). |
| Automated Personalization<br>(Premium) | Use algoritmos avançados de aprendizado de máquina e automação fornecidos pelo [!DNL Adobe Sensei] para examinar diferentes combinações de imagens, cópias e outros elementos em uma oferta e fornecer a melhor combinação a cada visitante, com base na que melhor atinge objetivos de negócios, como maior conversão ou receita por visitante. [Saiba mais](/help/c-activities/t-automated-personalization/automated-personalization.md). |
| Direcionamento de experiência (XT) | Forneça conteúdo a um público específico com base em um conjunto de regras e critérios definidos pelo usuário. O **[!UICONTROL Direcionamento de experiência]** é importante para direcionar uma experiência ou conteúdo específico a um público específico quando você entende que um público é valioso e tem uma boa noção do que a experiência significa. [Saiba mais](/help/c-activities/t-experience-target/experience-target.md). |
| Multivariate Testing (MVT) | Compare todas as combinações possíveis de variações de elementos na sua página ou experiência digital: por exemplo, três imagens de fundo diferentes, duas variações de cópia e duas cores de botão diferentes. O MVT determina qual combinação tem o melhor desempenho para um público específico e quais elementos afetam mais os resultados. [Saiba mais](/help/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Recommendations<br>(Premium) | Use a IA do Adobe Sensei para sugerir automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base na atividade anterior e de outros clientes. [Saiba mais](/help/c-recommendations/recommendations.md). |

## Canais

Você pode usar o [!DNL Target] para testar e personalizar experiências digitais em praticamente qualquer lugar: em pontos de contato digitais tradicionais como seu site, site para dispositivos móveis e aplicativo para dispositivos móveis, mas também em pontos de contato como quiosques, email, dispositivos da IoT, consoles de jogos e até mesmo assistentes de voz como Alexa e Cortana. Muitas empresas começam a usar o [!DNL Target] em seu site. No entanto, pesquisas recentes indicam que mais pessoas visitam marcas por meio de seus dispositivos móveis. Otimizar seus canais móveis agora é essencial. Se possível, você conectará as experiências do visitante em todos os seus pontos de contato para oferecer uma experiência contínua e consistente.

| Canal | Detalhes |
| --- | --- |
| Site | O [!DNL Target] pode ser usado para executar testes A/B, Multivariate Testing, direcionamento de experiência, alocação automática, direcionamento automático, Automated Personalization e atividades do Recommendations em páginas de seu aplicativo de página única (SPA) e de várias páginas, além de sites móveis para melhorar o envolvimento do visitante e do cliente, aumentar as conversões e aumentar a receita. |
| Web móvel | O [!DNL Target] pode ser usado para executar todos os mesmos tipos de atividades que você executa em seu site em páginas de site para dispositivos móveis para melhorar de forma semelhante o envolvimento do visitante e do cliente, aumentar as conversões e aumentar a receita. |
| Aplicativo móvel | O [!DNL Target] pode ser usado para testar e personalizar experiências de aplicativos móveis com base no comportamento do usuário e no contexto móvel. O [!DNL Target] permite que você forneça interações que envolvem e convertem por meio de testes interativos, bem como direcionamento de experiência e personalização baseada em IA. Para usar o [!DNL Target] no aplicativo móvel, você deve usar o SDK do Adobe Mobile Services. |
| IoT/Em Qualquer Lugar | O [!DNL Target] oferece uma implementação do lado do servidor para que você possa usar os mesmos recursos de teste e personalização em atividades que você usa no seu site tradicional, site para dispositivos móveis e aplicativos para dispositivos móveis em emails e pontos de contato que não têm navegador ou não usam código JavaScript. Por exemplo, para testar e personalizar quiosques, decodificadores de sinais, consoles de jogos, assistentes de voz e outros pontos de contato não tradicionais. |

## Implementações

Muitos de vocês podem querer usar o [!DNL Target] para testar e personalizar seus vários pontos de contato digitais diferentes, incluindo pontos de contato tradicionais da Web e móveis, mas também pontos de contato que não têm um navegador ou que não usam o código JavaScript. Em alguns casos, a política interna ou externa requer níveis adicionais de controle e segurança. Você também pode ter processos que precisam ser executados em um servidor de back-end por motivos de desempenho. Para atender a essa grande variedade de usos, oferecemos a capacidade de implementar o [!DNL Target] de diferentes maneiras: do lado do cliente, do lado do servidor ou uma combinação dos dois.

| Tipo de implementação | Detalhes |
| --- | --- |
| Lado do cliente | Em uma implementação no lado do cliente do [!DNL Target], o [!DNL Target] fornece as experiências associadas a uma atividade diretamente para o navegador do cliente. O navegador decide qual experiência será exibida e realiza a ação. Com uma implementação no lado do cliente, você pode usar um editor WYSIWYG, o **[!UICONTROL Visual Experience Composer]** (VEC) ou uma interface não visual, o **[!UICONTROL Experience Composer baseado em formulário]**, para criar experiências de teste e personalização. [Saiba mais](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). |
| Lado do servidor | Nesse tipo de implementação do [!DNL Target], um dispositivo cliente faz uma solicitação para uma experiência por meio do seu servidor, que envia essa solicitação para o [!DNL Target]. Em seguida, o [!DNL Target] envia a resposta para seu servidor, que decide qual experiência deve ser entregue ao dispositivo do cliente para que seja renderizada. A experiência não precisa ser exibida em um navegador; ela pode ser exibida em um email ou quiosque, por um assistente de voz ou por alguma outra experiência não visual ou dispositivo não baseado em navegador. Como o servidor fica entre o cliente e o [!DNL Target], esse tipo de implementação também será ideal se você precisar de mais controle e segurança ou de processos de back-end complexos que deseja executar no servidor. [Saiba mais](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Implementação híbrida | Nesta implementação, você escolhe a abordagem de implementação que funciona melhor para determinado caso de uso. Por exemplo, você pode usar uma implementação do lado do cliente para fazer um teste A/B de uma oferta em um banner principal na página inicial, mas também usar uma implementação do lado do servidor para determinar os resultados da pesquisa interna a serem exibidos em um navegador do cliente, a experiência a ser exibida em um painel de carro inteligente ou a resposta de voz a ser fornecida por um assistente de voz. |

## Elementos da atividade

No [!DNL Target], você pode criar uma atividade de personalização, uma atividade de otimização ou uma atividade que otimize sua abordagem de personalização. Cada atividade tem elementos-chave: as experiências ou ofertas que você está testando ou personalizando, os públicos ou indivíduos aos quais você está fornecendo uma experiência, as métricas pelas quais você avalia o impacto da atividade e os relatórios que exibem visualmente esse impacto.

| Tipo de elemento | Detalhes |
| --- | --- |
| Experiências | Uma oferta, imagem, texto, botão, vídeo, combinação desses diferentes elementos em uma página, uma página da Web completa ou um conjunto de páginas que talvez formem um funil de compra ou alguma outra sequência lógica de páginas. Também pode ser a resposta de um assistente de voz, um script de atendimento ao cliente ou até mesmo um sabor personalizado de uma máquina bebidas. Teste ou personalize experiências nas atividades do [!DNL Target]. [Saiba mais](/help/c-experiences/experiences.md). |
| Ofertas | Um bloco de conteúdo que pode ter imagens, texto, HTML, links, vídeo, um botão de ação, uma resposta do assistente de voz ou qualquer outro tipo de conteúdo. Uma oferta pode ser de desconto, frete grátis e assim por diante. Uma oferta pode ser exibida em uma página da Web, mas também pode ser acessada em qualquer ponto de contato do cliente, como um assistente de voz ou console de jogos. Ao testar uma oferta, você avalia seu sucesso em comparação a outras ofertas ou nenhuma oferta. [Saiba mais](/help/c-experiences/c-manage-content/manage-content.md). |
| Públicos-alvo | Um grupo de pessoas com as mesmas características, como um novo visitante, um visitante recorrente ou visitantes recorrentes do meio-oeste. O recurso de Público permite direcionar conteúdo e experiências diferentes para públicos-alvo específicos para otimizar o marketing digital, ao exibir as mensagens certas para as pessoas certas, na hora certa. Se um visitante for identificado como parte de um público de direcionamento, o [!DNL Target] determinará qual experiência deve ser exibida, com base nos critérios estabelecidos quando a atividade foi criada. [Saiba mais](/help/c-target/target.md). |
| Métricas de sucesso | As métricas de sucesso incluem as principais medidas de negócios que permitem determinar o sucesso de determinada experiência ou oferta em uma atividade do [!DNL Target]. Por exemplo, você pode determinar se uma nova oferta aumenta sua receita por visitante ou adicionar um item ao carrinho de compras. As métricas de sucesso podem ser úteis para descobrir problemas nos funis de registro, pedido ou compra, além de facilitar a descoberta de problemas no envolvimento de visitantes ou clientes. [Saiba mais](/help/c-activities/r-success-metrics/success-metrics.md). |
| Relatórios | Os relatórios fornecem informações sobre o progresso e os resultados das suas atividades que ajudam a tomar decisões baseadas nos dados. Os dados dos relatórios podem ajudá-lo a decidir quando finalizar um teste, mostrar a experiência ou a oferta vencedora e fornecer os insights ou os aprendizados necessários para determinar as próximas ações. [Saiba mais](/help/c-reports/reports.md). |

## Ferramentas de criação de atividades

O [!DNL Target] fornece três principais maneiras de configurar suas atividades de teste e personalização, o [!UICONTROL Visual Experience Composer] (VEC), o [!UICONTROL Experience Composer com base em formulário] e o [!UICONTROL Visual Experience Composer de SPA (aplicativo de página única)]. Ambos fornecem orientações sobre o processo de configuração da atividade em três etapas: definição das experiências, seleção ou definição dos públicos e seleção das métricas de sucesso primárias e secundárias pelas quais você avalia os resultados da atividade.

| Ferramenta | Detalhes |
| --- | --- |
| [!UICONTROL Visual Experience Composer] (VEC) | Uma interface WYSIWYG que permite criar e testar facilmente experiências e ofertas personalizadas no contexto do site. Você pode criar experiências e ofertas para atividades do [!DNL Target] arrastando e soltando, trocando e modificando o layout e o conteúdo de uma página da Web (ou oferta) ou página da Web móvel. [Saiba mais](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md). |
| [!UICONTROL Experience Composer baseado em formulário] | Uma interface de criação de ofertas e experiências não visuais que é útil na criação de experiências para uso em testes A/B, no Direcionamento de experiência, na Automated Personalization e em atividades do Recommendations quando o Visual Experience Composer não estiver disponível ou não for prático. Por exemplo, você pode usar o composer baseado em formulário para criar experiências e ofertas para entrega em emails, quiosques e assistentes de voz. [Saiba mais](/help/c-experiences/form-experience-composer.md). |
| [!UICONTROL Aplicativo de página única (SPA) no Visual Experience Composer] | O VEC para SPAs permite que os comerciantes criem testes e personalizem conteúdo em SPAs de forma autônoma, sem dependências de desenvolvimento contínuas. O VEC pode ser usado para criar atividades de teste A/B e Direcionamento de experiência (XT) em estruturas populares, como o React e o Angular. [Saiba mais](/help/c-experiences/spa-visual-experience-composer.md). |

## Governança e controle

Há um console administrativo para fornecer às pessoas certas as funções e os níveis associados de acesso e permissões para [!DNL Target]. Para usuários do [!UICONTROL Target Premium], oferecemos governança e controle mais detalhados
com [!UICONTROL Permissões empresariais].

| Ferramenta | Detalhes |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | Adicione usuários ao Adobe Target e atribua permissões do Adobe Admin Console. [Saiba mais](/help/administrating-target/c-user-management/c-user-management/user-management.md). |
| [!UICONTROL Permissão empresarial] <br> (Premium) | Um meio de administrar formalmente o acesso de usuários empresariais no [!DNL Target]. Adicione usuários ao [!DNL Target], atribua permissões com base em suas funções e crie espaços de trabalho para equipes com base em diferentes departamentos, localidades globais, canais e outros agrupamentos lógicos. É possível atribuir aos usuários as funções de Observador, Editor, Publicador ou Aprovador. [Saiba mais](/help/administrating-target/c-user-management/property-channel/property-channel.md). |

## Integrações

O [!DNL Target] pode se integrar a muitos sistemas originais, secundários e de terceiros. Essas
integrações podem ser valiosas para fornecer acesso aos dados de visitantes e clientes disponíveis nesses sistemas para uso na criação de públicos-alvo para testes e personalização. Como parte da [!DNL Adobe Experience Cloud], o [!DNL Target] integra-se perfeitamente com as soluções da [!DNL Experience Cloud] e seus serviços principais.

| Integração | Detalhes |
| --- | --- |
| Adobe Experience Cloud | O [!DNL Target] tem recursos incorporados com outras soluções da [!DNL Adobe Experience Cloud] para personalizar experiências em escala. Aproveite os recursos do [!DNL Target] juntamente com o [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), o [Experience Cloud Audiences](/help/c-integrating-target-with-mac/mmp.md), o [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), o [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) e o [Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM). |
| APIs do Target (Premium) | O [!UICONTROL Target] oferece mais de 40 APIs que você pode usar para integrar o Adobe Target com sistemas primários, secundários e de terceiros. [Saiba mais](/help/api/api-overview.md). |

## Lembre-se

Considere as ideias a seguir antes de passarmos para o próximo capítulo: &quot;Desenvolver suas ideias de teste e personalização&quot;.

### Práticas recomendadas de otimização

* **Boa estratégia**: qual é o nosso objetivo e a nossa hipótese? Eles estão alinhados? Por exemplo, queremos aumentar os envios de aplicativos de empréstimo, então, imaginamos que a redução do número de campos no formulário de aplicativo pode fazer isso.
* **Metodologia disciplinada** Estamos começando a testar nos lugares certos? Por exemplo, você precisa de locais com tráfego suficiente e que afetam as métricas importantes para a empresa.
* **Configuração adequada** Nossa atividade está configurada para atingir o objetivo? Por exemplo, se estamos tentando aumentar os envios de pedidos de empréstimo, devemos direcionar os interessados em empréstimos e medir cliques do botão &quot;Enviar&quot;.
* **Análise completa**: a atividade de teste foi executada até a conclusão? O que dizem os resultados? Execute sua atividade até atingir 95% a 99% de confiança estatística. Documente por que você acha que a experiência vencedora ganhou e aplique o aprendizado em outro lugar.
* **Teste iterativo**: estamos aproveitando o que foi aprendido em atividades anteriores? Se você encontrar uma tática vencedora, tente aprimorá-la ou fazer alterações que funcionem com ela para melhorar ainda mais suas métricas de sucesso.

### As opiniões podem afetar negativamente os resultados

* Opiniões que podem afetar negativamente a sua eficácia. Opinião da pessoa paga mais alta (HIPPO), atitudes, propensões. Por exemplo, o CEO deseja reduzir o tamanho da caixa de pesquisa para criar mais espaço em cada página. Devemos testar para garantir que isso não reduza o número de pesquisas.
* A atuação tem por base opiniões? Eu não gosto da aparência do teste. O cliente não vai gostar dessa experiência. Embora a intuição seja útil, o teste A/B tem provado, repetidas vezes, que nem sempre ela é precisa.
* Ou você tem uma mentalidade de otimização? Estou animado para ver qual será a experiência vencedora. Temos opções suficientes para testar?

### As suposições também podem afetar negativamente os resultados

* Suposições que podem afetar negativamente sua eficácia. Mentalidade de rebanho (é assim que nossos concorrentes fazem isso). Por exemplo, todos os nossos concorrentes usam banners ilustrativos com imagens rotativas, então, também deveríamos fazer isso.
* Supor que nós sabemos por que algo está funcionando ou não. Supor que não precisamos testar algo. Por exemplo, sempre listamos os quartos de hotel na ordem do preço mais alto ao mais baixo como padrão.
* Você está agindo com base em suposições? Não precisamos testar isso, verificamos a análise. (Sim, mas pode haver mais informações envolvidas do que a análise revela.)
* Ou você tem uma mentalidade de otimização? Nós testamos tudo.
