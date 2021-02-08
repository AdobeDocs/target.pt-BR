---
keywords: kit de boas-vindas;kit de boas-vindas do público alvo;introdução;introdução;introdução;introdução;introdução
description: Dê uma olhada no Adobe Target. Saiba mais sobre atividades, canais, implementação, integrações e muito mais disponíveis.
title: Onde posso encontrar uma introdução de alto nível ao Público alvo?
feature: Overview
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '2520'
ht-degree: 17%

---


# Capítulo 2: Visão geral do Adobe Target

Antes de começar a usar [!DNL Adobe Target], pode ser útil obter uma visão geral de alto nível da solução. Neste capítulo, conheça os principais recursos da solução, os pontos de contato com a marca nos quais você pode usá-la, as opções de implementação, os recursos e workflows importantes da interface do usuário, os recursos de controle e sua função no [!DNL Adobe Experience Cloud] geral. A menos que os recursos [!DNL Adobe Target Premium] sejam exibidos, os itens descritos neste capítulo estarão disponíveis com [!DNL Adobe Target Premium] e [!DNL Adobe Target Standard]. Para obter mais informações, consulte [Introdução ao Público alvo](/help/c-intro/intro.md).

## Recursos e atividades

Testes e personalização são os dois tipos amplos de recursos que [!DNL Target] ofertas e que você pode usar ao criar uma &quot;atividade&quot; em [!DNL Target]. Você pode ver o termo &quot;teste&quot; usado de forma intercambiável com &quot;otimização&quot; e &quot;personalização&quot; usados de forma intercambiável com &quot;definição de metas&quot;.

Em uma atividade de teste, você compara uma variação de uma experiência digital com uma ou mais variações para descobrir aquela que faz com que a maioria dos visitantes tome a ação desejada. [!DNL Target] oferta os seguintes recursos de teste: Teste A/B, teste multivariado (MVT) e Autoalocação.

Com uma atividade de personalização, você oferece uma experiência digital que é personalizada para um grupo específico de visitantes ou para cada visitante individual. [!DNL Target] oferta estes recursos de personalização: Direcionamento de experiência, Público alvo automático, Automated Personalization e Recommendations.

Para obter uma compreensão mais profunda de quando e como usar cada recurso, consulte [tipos de atividade de Públicos alvos](/help/c-activities/target-activities-guide.md).

| Tipo de atividade | Detalhes |
| --- | --- |
| Teste A/B | Compare duas ou mais variações de suas experiências ou ofertas em seu site ou outro ponto de contato do cliente digital para ver qual variação melhora mais as principais medidas de negócios durante um período de teste pré-especificado. Os testes A/B são adequados para grandes alterações, como novos layouts de página da Web, diferentes abordagens para a navegação do site ou tratamentos drasticamente diferentes de elementos individuais de uma experiência digital, como cópia, imagens e botões de chamada para ação. [Saiba mais](/help/c-activities/t-test-ab/test-ab.md). |
| Alocação automática | Identifique a experiência de melhor desempenho entre duas ou mais experiências e realoque automaticamente mais tráfego para o vencedor para aumentar as conversões enquanto o teste continua sendo executado e aprendido. Usa inteligência artificial capacitada por [!DNL Adobe Sensei]. [Saiba mais](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| Público alvo automático<br>(Premium) | Aproveite a Adobe Sensei AI em [!DNL Target] para determinar e fornecer a melhor experiência de vários para cada visitante com base em seu perfil de cliente individual e no comportamento de visitantes anteriores com perfis semelhantes. O Público alvo automático permite a personalização em escala. [Saiba mais](/help/c-activities/auto-target/auto-target-to-optimize.md). |
| Automated Personalization<br>(Premium) | Use algoritmos avançados de aprendizado de máquina e automação acionados por [!DNL Adobe Sensei] para revisar diferentes combinações de imagens, cópias e outros elementos em uma oferta e fornecer a melhor combinação para cada visitante, com base na qual os objetivos de negócios sejam alcançados da melhor forma, como mais conversões ou mais receita por visitante. [Saiba mais](/help/c-activities/t-automated-personalization/automated-personalization.md). |
| Direcionamento de experiência (XT) | Forneça conteúdo para uma audiência específica com base em um conjunto de regras e critérios definidos pelo usuário. **[!UICONTROL O]** direcionamento de experiência é valioso para direcionar uma experiência ou conteúdo específico a uma audiência específica quando você entende que uma audiência é valiosa e tem uma boa noção do que a experiência traz. [Saiba mais](/help/c-activities/t-experience-target/experience-target.md). |
| Teste multivariado (MVT) | Compare todas as combinações possíveis de variações de elementos na sua página ou experiência digital — por exemplo, três imagens de fundo diferentes, duas variações de cópia e duas cores de botão diferentes. O MVT determina qual combinação tem o melhor desempenho para uma audiência específica e quais elementos têm mais impacto nos resultados. [Saiba mais](/help/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Recommendations<br>(Premium) | Use o Adobe Sensei AI para sugerir automaticamente produtos ou conteúdos que possam interessar seus clientes com base em suas atividades anteriores e de outros clientes. [Saiba mais](/help/c-recommendations/recommendations.md). |

## Canais

Você pode usar [!DNL Target] para testar e personalizar experiências digitais praticamente em qualquer lugar — pontos de contato digitais tradicionais como site, site móvel e aplicativo móvel, mas também em pontos de contato como quiosques, email, dispositivos IoT, consoles de jogos e até mesmo assistentes de voz como Alexa e Cortana. Muitas start do empresa que usam [!DNL Target] no site. Entretanto, pesquisas recentes indicam que mais pessoas visitam marcas de seus dispositivos móveis. A otimização dos canais para portáteis agora é essencial. Idealmente, você conectará as experiências do visitante em todos os pontos de contato para oferecer uma experiência contínua e consistente.

| Canal | Detalhes |
| --- | --- |
| Site | [!DNL Target] pode ser usado para executar testes A/B, Multivariate Testing, direcionamento de experiência, Autoalocação, Público alvo automático, Automated Personalization e Recommendations atividades em páginas de várias páginas, aplicativos de página única (SPA) e sites móveis para melhorar o envolvimento do visitante e do cliente, aumentar as conversões e aumentar a receita. |
| Web móvel | [!DNL Target] pode ser usado para executar todos os mesmos tipos de atividade que você executa em seu site nas páginas de seu site para dispositivos móveis para melhorar de maneira semelhante o envolvimento do visitante e do cliente, aumentar as conversões e aumentar a receita. |
| Aplicativo móvel | [!DNL Target] pode ser usado para testar e personalizar experiências de aplicativos móveis com base no comportamento do usuário e no contexto móvel. [!DNL Target] permite fornecer interações que envolvem e convertem por meio de testes iterativos, bem como direcionamento de experiência e personalização acionada por AI. Para usar [!DNL Target] no aplicativo móvel, você deve usar o SDK do Adobe Mobile Services. |
| IoT/Todo lugar | [!DNL Target] oferta uma implementação do lado do servidor para que você possa usar os mesmos recursos de teste e personalização no atividade que você usa no site tradicional, site móvel e aplicativos móveis em emails e pontos de contato que não possuem um navegador ou não usam o código JavaScript. Por exemplo, você pode testar e personalizar quiosques, decodificadores de sinais, consoles de jogos, assistentes de voz e outros pontos de contato não tradicionais. |

## Implementações

Muitos de vocês podem querer usar [!DNL Target] para testar e personalizar seus vários pontos de contato digitais diferentes, incluindo pontos de contato tradicionais da Web e móveis, mas também pontos de contato que não possuem um navegador ou que não usam o código JavaScript. Em alguns casos, a política interna ou externa exige níveis adicionais de controle e segurança. Você também pode ter processos que precisam ser executados em um servidor backend por motivos de desempenho. Para atender a essa grande variedade de usos, oferecemos a você a capacidade de implementar [!DNL Target] de diferentes maneiras: lado do cliente, lado do servidor ou uma combinação dos dois.

| Tipo de implementação | Detalhes |
| --- | --- |
| Lado do cliente | Com essa implementação de [!DNL Target], [!DNL Target] fornece as experiências associadas a uma atividade diretamente ao navegador do cliente. O navegador decide qual experiência será exibida e realiza a ação. Com o cliente, você pode usar um editor WYSIWYG, o **[!UICONTROL Visual Experience Composer]** (VEC) ou uma interface não visual, o **[!UICONTROL Criador de experiências baseado em forma]**, para criar suas experiências de teste e personalização. [Saiba mais](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). |
| Servidor | Nesse tipo de implementação [!DNL Target], um dispositivo cliente faz uma solicitação para uma experiência por meio do seu servidor, seu servidor envia essa solicitação para [!DNL Target], [!DNL Target] envia a resposta ao seu servidor e seu servidor toma a decisão sobre qual experiência fornecer ao dispositivo cliente para que ele seja renderizado. A experiência não precisa ser exibida em um navegador; ela pode ser exibida em um email ou quiosque, por um assistente de voz ou por alguma outra experiência não visual ou dispositivo não baseado em navegador. Como o servidor fica entre o cliente e o [!DNL Target], esse tipo de implementação também será ideal se você precisar de mais controle e segurança ou de processos de back-end complexos que deseja executar no servidor. [Saiba mais](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Implementação híbrida | Nessa implementação, você escolhe a abordagem de implementação que funciona melhor para um determinado caso de uso. Por exemplo, você pode usar uma implementação do cliente para testar A/B e uma oferta em um banner principal no home page, mas também usar uma implementação do lado do servidor para determinar os resultados da pesquisa interna a serem exibidos em um navegador cliente, a experiência a ser exibida em um painel de carro inteligente ou a resposta de voz a ser fornecida por um assistente de voz. |

## Elementos de atividade

Em [!DNL Target], você pode criar uma atividade de personalização, uma atividade de otimização ou uma atividade que otimize sua abordagem de personalização. Cada atividade tem elementos-chave: as experiências ou ofertas que você está testando ou personalizando, as audiências ou indivíduos para os quais você está fornecendo uma experiência, as métricas pelas quais você mede o impacto da atividade e os relatórios que exibem visualmente esse impacto.

| Tipo de elemento | Detalhes |
| --- | --- |
| Experiências | Uma oferta, imagem, texto, botão, vídeo, combinação desses diferentes elementos em uma página, uma página da Web completa ou um conjunto de páginas que talvez formem um funil de compra ou alguma outra sequência lógica de páginas. Também pode ser a resposta de um assistente de voz, um script de atendimento ao cliente ou até mesmo um sabor personalizado de uma máquina bebidas. Teste ou personalize experiências nas atividades do [!DNL Target]. [Saiba mais](/help/c-experiences/experiences.md). |
| Ofertas | Um bloco de conteúdo que pode conter imagens, texto, HTML, links, vídeo, um botão de ação, uma resposta do assistente de voz ou qualquer outro tipo de conteúdo. Uma oferta pode ser para um desconto, frete grátis e assim por diante. Uma oferta pode ser exibida em uma página da Web, mas também pode ocorrer em qualquer ponto de contato do cliente, como um assistente de voz ou console de jogos. Ao testar uma oferta, você mede seu sucesso em comparação a outras ofertas ou nenhuma oferta. [Saiba mais](/help/c-experiences/c-manage-content/manage-content.md). |
| Públicos-alvo | Um grupo de pessoas com as mesmas características, como um novo visitante, um visitante recorrente ou visitantes recorrentes do meio-oeste. O recurso de Público permite direcionar conteúdo e experiências diferentes para públicos-alvo específicos para otimizar o marketing digital, ao exibir as mensagens certas para as pessoas certas, na hora certa. Se um visitante for identificado como parte de uma audiência de público alvo, [!DNL Target] determinará qual experiência será exibida, com base em critérios definidos durante a criação da atividade. [Saiba mais](/help/c-target/target.md). |
| Métricas de sucesso | Principais medidas de negócios que permitem determinar o sucesso de determinada experiência ou oferta em uma atividade [!DNL Target]. Por exemplo, você pode determinar se uma nova oferta aumenta sua receita por visitante ou adicionar um item ao carrinho de compras. As métricas de sucesso podem ser úteis para descobrir problemas nos funis de registro, pedido ou compra, além de facilitar a descoberta de problemas no envolvimento de visitantes ou clientes. [Saiba mais](/help/c-activities/r-success-metrics/success-metrics.md). |
| Relatórios | Informações sobre o progresso e os resultados de suas atividades que ajudam você a tomar decisões com base em seus dados. Os dados dos relatórios podem ajudá-lo a decidir quando finalizar um teste, mostrar a experiência ou a oferta vencedora e fornecer os insights ou os aprendizados necessários para determinar as próximas ações. [Saiba mais](/help/c-reports/reports.md). |

## Ferramentas de criação de atividades

[!DNL Target] fornece três formas principais de configurar suas atividades de teste e personalização, o  [!UICONTROL Visual Experience Composer]  (VEC), o Criador [!UICONTROL  de experiências baseado em ]forma e o Aplicativo de página  [!UICONTROL única (SPA) Visual Experience Composer]. Ambas o guiarão pelo processo de configuração da atividade em três etapas — definindo as experiências, selecionando ou definindo as audiências e selecionando as métricas de sucesso principal e secundário pelas quais você medirá os resultados da atividade.

| Ferramenta | Detalhes |
| --- | --- |
| Visual Experience Composer (VEC) | Uma interface de usuário WYSIWYG que permite criar e testar facilmente experiências e ofertas personalizadas no contexto do site. Você pode criar experiências e ofertas para [!DNL Target] atividades arrastando e soltando, trocando e modificando o layout e o conteúdo de uma página da Web (ou oferta) ou página da Web móvel. [Saiba mais](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md). |
| [!UICONTROL Experience Composer baseado em formulário] | Uma experiência não visual e uma interface de criação de oferta que é útil na criação de experiências para uso em testes A/B, direcionamento de experiência, Automated Personalization e Recommendations atividade quando o Visual Experience Composer não está disponível ou é prático para uso. Por exemplo, você pode usar o composer baseado em formulário para criar experiências e ofertas para entrega em emails, quiosques e assistentes de voz. [Saiba mais](/help/c-experiences/form-experience-composer.md). |
| [!UICONTROL Aplicativo de página única (SPA) no Visual Experience Composer] | O VEC para SPAs permite que os comerciantes criem testes e personalizem conteúdo em SPAs de forma autônoma, sem dependências de desenvolvimento contínuas. O VEC pode ser usado para criar atividades de teste A/B e Direcionamento de experiência (XT) em estruturas populares, como o React e o Angular. [Saiba mais](/help/c-experiences/spa-visual-experience-composer.md). |

## Governação e controlo

Para fornecer às pessoas certas as funções certas e os níveis associados de acesso e permissões para [!DNL Target], temos um console administrativo. Para usuários do [!UICONTROL Público alvo Premium], ofertas controle e controle mais detalhados
com [!UICONTROL Permissões corporativas].

| Ferramenta | Detalhes |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | Adicione usuários ao Adobe Target e atribua permissões do Adobe Admin Console. [Saiba mais](/help/administrating-target/c-user-management/c-user-management/user-management.md). |
| [!UICONTROL Enterprise ]Permissions<br> (Premium) | Um meio de administrar formalmente o acesso de usuários empresariais no [!DNL Target]. Adicione usuários a [!DNL Target], atribua permissões com base em suas funções e crie espaços de trabalho para equipes com base em diferentes departamentos, locais globais, canais e outros agrupamentos lógicos. Você pode atribuir aos usuários as funções de Observador, Editor, Editor ou Aprovador. [Saiba mais](/help/administrating-target/c-user-management/property-channel/property-channel.md). |

## Integrações

[!DNL Target] pode se integrar com muitos sistemas primários, secundários e de terceiros. Esses
as integrações podem ser importantes para fornecer acesso aos dados do visitante e do cliente disponíveis nesses sistemas para uso na criação de audiências para teste e personalização. Como parte de [!DNL Adobe Experience Cloud], [!DNL Target] integra-se perfeitamente às soluções [!DNL Experience Cloud] e aos seus Principais serviços.

| Integração | Detalhes |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] tem recursos incorporados com outras  [!DNL Adobe Experience Cloud] soluções para personalizar experiências em escala. Aproveite o poder de [!DNL Target] junto com [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), [Experience Cloud Audiência](/help/c-integrating-target-with-mac/mmp.md), [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) e [Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM). |
| APIs de público alvo (Premium) | [!UICONTROL O ] Target oferece mais de 40 APIs que você pode usar para integrar a Adobe Target a sistemas primários, secundários e de terceiros. [Saiba mais](/help/api/api-overview.md). |

## Lembre-se

Considere as seguintes ideias antes de passarmos para o próximo capítulo: &quot;Desenvolver suas ideias de teste e personalização.&quot;

### Práticas recomendadas para otimização

* **Boa estratégia**: Qual é o nosso objetivo e hipótese? Eles estão alinhados? Por exemplo, desejamos aumentar as solicitações de empréstimo, portanto, presumimos que a redução do número de campos no formulário de solicitação fará isso.
* **Disciplinada** metodologiaEstamos começando a testar nos lugares certos? Por exemplo, você precisa de locais com tráfego suficiente e que afetem as métricas importantes    aos negócios.
* **Configuração** adequadaNossa atividade está configurada para atingir nosso objetivo? Por exemplo, se estamos tentando aumentar as solicitações de empréstimo, devemos público alvo pessoas interessadas em empréstimos e avaliar cliques do botão &quot;Enviar&quot;.
* **Análise** complexa: A atividade de teste foi executada até a conclusão? O que dizem os resultados? Execute sua atividade até atingir entre 95% e 99% de confiança estatística. Documento porque você acha que a experiência vencedora ganhou e aplica o aprendizado em outro lugar.
* **Teste** iterativo: Estamos a partir dos conhecimentos de atividades anteriores? Se encontrar uma tática vencedora, tente aprimorá-la ou fazer alterações que funcionem com ela para melhorar ainda mais sua métrica de sucesso.

### As opiniões podem afetar negativamente os seus resultados

* Opiniões que podem afetar negativamente a sua eficácia. Opinião da Pessoa Mais Paga (HIPPO), atitudes, preconceitos. Por exemplo, o CEO deseja reduzir o tamanho da caixa de pesquisa para criar mais espaço em cada página. Devemos testar para garantir que não reduza o número de pesquisas.
* O senhor está agindo sobre opiniões? Eu não gosto da aparência daquele teste. O cliente não vai gostar nem um pouco dessa experiência. Embora a intuição seja útil, o teste A/B provou repetidamente que nem sempre é pontual.
* Ou você tem uma mentalidade de otimização? Estou empolgado em ver qual experiência ganha. Temos opções suficientes para testar?

### Pressupostos também podem afetar negativamente os resultados

* Pressupostos que podem afetar negativamente sua eficácia. Mentalidade hereditária (é assim que nossos concorrentes estão fazendo). Por exemplo, todos os nossos concorrentes usam banners de heróis com imagens rotativas, por isso também deveríamos.
* Supondo que saibamos por que algo está ou não funcionando. Supondo que não precisemos testar algo. Por exemplo, sempre lista quartos de hotel na ordem do preço mais alto ao mais baixo como padrão.
* Você está agindo em suposições? Não precisamos testar isso, verificamos a análise. (Sim, mas pode haver mais na história do que a análise revela.)
* Ou você tem uma mentalidade de otimização? Nós testamos tudo.