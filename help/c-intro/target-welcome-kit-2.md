---
keywords: kit de boas-vindas, kit de boas-vindas do target, introdução, introdução, introdução
description: Dê uma olhada no Adobe Target de alto nível. Saiba mais sobre as atividades, canais, implementação, integrações disponíveis e muito mais.
title: Onde posso encontrar uma introdução de alto nível ao Target?
feature: Visão geral
exl-id: 19238d4c-b7e1-418d-96e5-c46a3769f7bf
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '2520'
ht-degree: 17%

---

# Capítulo 2: Adobe [!DNL Target] de relance

Antes de começar a usar [!DNL Adobe Target], pode ser útil obter uma visão geral de alto nível da solução. Neste capítulo, conheça os principais recursos da solução, os pontos de contato da marca nos quais você pode usá-la, as opções de implementação, os importantes recursos e fluxos de trabalho da interface do usuário, os recursos de governança e sua função no [!DNL Adobe Experience Cloud] geral. A menos que seja observado como recursos [!DNL Adobe Target Premium], os itens descritos neste capítulo estão disponíveis com [!DNL Adobe Target Premium] e [!DNL Adobe Target Standard]. Para obter mais informações, consulte [Introdução ao Target](/help/c-intro/intro.md).

## Recursos e atividades

Teste e personalização são os dois tipos amplos de recursos que [!DNL Target] oferece e que você pode usar ao criar uma &quot;atividade&quot; em [!DNL Target]. Você pode ver o termo &quot;teste&quot; usado alternadamente com &quot;otimização&quot; e &quot;personalização&quot; usado alternadamente com &quot;definição de metas&quot;.

Em uma atividade de teste, você compara uma variação de uma experiência digital com uma ou mais variações para descobrir que uma que faz com que a maioria dos visitantes tome a ação desejada. [!DNL Target] O oferece os seguintes recursos de teste: Teste A/B, teste multivariado (MVT) e alocação automática.

Com uma atividade de personalização, você fornece uma experiência digital personalizada para um grupo específico de visitantes ou para cada visitante individual. [!DNL Target] O oferece estes recursos de personalização: Direcionamento de experiência, Direcionamento automático, Automated Personalization e Recommendations.

Para obter uma compreensão mais detalhada de quando e como usar cada recurso, consulte [Tipos de atividade do Target](/help/c-activities/target-activities-guide.md).

| Tipo de atividade | Detalhes |
| --- | --- |
| Teste A/B | Compare duas ou mais variações de suas experiências ou ofertas no seu site ou outro ponto de contato de cliente digital para ver qual variação melhora as principais medidas de negócios durante um período de teste pré-especificado. Os testes A/B são adequados para grandes alterações, como novos layouts de página da Web, diferentes abordagens da navegação do site ou tratamentos drasticamente diferentes de elementos individuais de uma experiência digital, como cópia, imagens e botões de chamada para ação. [Saiba mais](/help/c-activities/t-test-ab/test-ab.md). |
| Alocação automática | Identifique a experiência com melhor desempenho entre duas ou mais experiências e realoque automaticamente mais tráfego para o vencedor a fim de aumentar as conversões enquanto o teste continua a ser executado e aprendido. Usa Inteligência artificial fornecida por [!DNL Adobe Sensei]. [Saiba mais](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md). |
| Direcionamento automático<br>(Premium) | Aproveite a IA do Adobe Sensei em [!DNL Target] para determinar e fornecer a melhor experiência de vários visitantes com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares. O Direcionamento automático permite a personalização em escala. [Saiba mais](/help/c-activities/auto-target/auto-target-to-optimize.md). |
| Automated Personalization<br>(Premium) | Use algoritmos avançados de aprendizado de máquina e automação fornecidos por [!DNL Adobe Sensei] para revisar diferentes combinações de imagens, cópias e outros elementos em uma oferta e fornecer a melhor combinação para cada visitante, com base na qual o melhor atinge objetivos de negócios, como maior conversão ou receita por visitante. [Saiba mais](/help/c-activities/t-automated-personalization/automated-personalization.md). |
| Direcionamento de experiência (XT) | Forneça conteúdo para um público-alvo específico com base em um conjunto de regras e critérios definidos pelo usuário. **[!UICONTROL O]** Direcionamento de experiência é importante para direcionar uma experiência ou conteúdo específico a um público-alvo específico, quando você entende que um público-alvo é valioso e tem uma boa noção do que a experiência significa. [Saiba mais](/help/c-activities/t-experience-target/experience-target.md). |
| Teste multivariado (MVT) | Compare todas as combinações possíveis de variações de elementos na sua página ou experiência digital, por exemplo, três imagens de plano de fundo diferentes, duas variações de cópia e duas cores de botão diferentes. O MVT determina qual combinação tem o melhor desempenho para um público-alvo específico e quais elementos afetam mais os resultados. [Saiba mais](/help/c-activities/c-multivariate-testing/multivariate-testing.md). |
| Recommendations<br>(Premium) | Use o Adobe Sensei AI para sugerir automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base na atividade anterior e de outros clientes. [Saiba mais](/help/c-recommendations/recommendations.md). |

## Canais

Você pode usar [!DNL Target] para testar e personalizar experiências digitais em praticamente qualquer lugar, pontos de contato digitais tradicionais como site, site para dispositivos móveis e aplicativo para dispositivos móveis, mas também em pontos de contato como quiosques, email, dispositivos IoT, consoles de jogos e até mesmo assistentes de voz como Alexa e Cortana. Muitas empresas começam a usar [!DNL Target] em seu site. No entanto, pesquisas recentes indicam que mais pessoas visitam marcas de seus dispositivos móveis. Otimizar seus canais móveis agora é essencial. Idealmente, você conectará as experiências do visitante em todos os seus pontos de contato para oferecer uma experiência contínua e consistente.

| Canal | Detalhes |
| --- | --- |
| Site | [!DNL Target] O pode ser usado para executar testes A/B, Multivariate Testing, direcionamento de experiência, alocação automática, direcionamento automático, Automated Personalization e atividades do Recommendations em páginas de seu aplicativo de página única (SPA) e de várias páginas, além de sites móveis, para melhorar a participação do visitante e do cliente, aumentar as conversões e aumentar a receita. |
| Web móvel | [!DNL Target] O pode ser usado para executar todos os mesmos tipos de atividades que você executa em seu site em páginas de site para dispositivos móveis para melhorar de forma semelhante a participação do visitante e do cliente, aumentar as conversões e aumentar a receita. |
| Aplicativo móvel | [!DNL Target] O pode ser usado para testar e personalizar experiências de aplicativos móveis com base no comportamento do usuário e no contexto móvel. [!DNL Target] O permite fornecer interações que interagem e convertem por meio de testes iterativos, bem como Direcionamento de experiência e personalização por meio de IA. Para usar [!DNL Target] no aplicativo móvel, você deve usar o SDK do Adobe Mobile Services. |
| IoT/Em Qualquer Lugar | [!DNL Target] O oferece uma implementação do lado do servidor para que você possa usar os mesmos recursos de teste e personalização em atividades que você usa no seu site tradicional, site para dispositivos móveis e aplicativos para dispositivos móveis em emails e pontos de contato que não têm navegador ou não usam código JavaScript. Por exemplo, para testar e personalizar quiosques, decodificadores de sinais, consoles de jogos, assistentes de voz e outros pontos de contato não tradicionais. |

## Implementações

Muitos de vocês podem querer usar [!DNL Target] para testar e personalizar seus vários pontos de contato digitais diferentes, incluindo pontos de contato tradicionais da Web e móveis, mas também pontos de contato que não têm um navegador ou que não usam o código JavaScript. Em alguns casos, a política interna ou externa requer níveis adicionais de controle e segurança. Você também pode ter processos que precisam ser executados em um servidor de back-end por motivos de desempenho. Para atender a essa grande variedade de usos, oferecemos a capacidade de implementar [!DNL Target] de diferentes maneiras: lado do cliente, lado do servidor ou uma combinação dos dois.

| Tipo de implementação | Detalhes |
| --- | --- |
| Lado do cliente | Com essa implementação de [!DNL Target], [!DNL Target] fornece as experiências associadas a uma atividade diretamente para o navegador do cliente. O navegador decide qual experiência será exibida e realiza a ação. No lado do cliente, você pode usar um editor WYSIWYG, o **[!UICONTROL Visual Experience Composer]** (VEC) ou uma interface não visual, o **[!UICONTROL Experience Composer baseado em formulário]**, para criar suas experiências de teste e personalização. [Saiba mais](/help/c-implementing-target/c-implementing-target-for-client-side-web/c-how-atjs-works/how-atjs-works.md). |
| Lado do servidor | Nesse tipo de implementação [!DNL Target], um dispositivo cliente faz uma solicitação para uma experiência por meio do seu servidor, seu servidor envia essa solicitação para [!DNL Target], [!DNL Target] envia a resposta para seu servidor e seu servidor decide qual experiência deve ser entregue ao dispositivo cliente para que seja renderizada. A experiência não precisa ser exibida em um navegador; ela pode ser exibida em um email ou quiosque, por um assistente de voz ou por alguma outra experiência não visual ou dispositivo não baseado em navegador. Como o servidor fica entre o cliente e o [!DNL Target], esse tipo de implementação também será ideal se você precisar de mais controle e segurança ou de processos de back-end complexos que deseja executar no servidor. [Saiba mais](/help/c-implementing-target/c-api-and-sdk-overview/api-and-sdk-overview.md). |
| Implementação híbrida | Nesta implementação, você escolhe a abordagem de implementação que funciona melhor para um determinado caso de uso. Por exemplo, você pode usar uma implementação do lado do cliente para testar uma oferta em um banner principal na página inicial, mas também usar uma implementação do lado do servidor para determinar os resultados da pesquisa interna a serem exibidos em um navegador do cliente, a experiência a ser exibida em um painel do smart car ou a resposta da voz a ser entregue por um assistente de voz. |

## Elementos da atividade

Em [!DNL Target], você pode criar uma atividade de personalização, uma atividade de otimização ou uma atividade que otimize sua abordagem de personalização. Cada atividade tem elementos-chave: as experiências ou ofertas que você está testando ou personalizando, os públicos-alvo ou indivíduos para os quais você está fornecendo uma experiência, as métricas pelas quais você mede o impacto da atividade e os relatórios que exibem visualmente esse impacto.

| Tipo de elemento | Detalhes |
| --- | --- |
| Experiências | Uma oferta, imagem, texto, botão, vídeo, combinação desses diferentes elementos em uma página, uma página da Web completa ou um conjunto de páginas que talvez formem um funil de compra ou alguma outra sequência lógica de páginas. Também pode ser a resposta de um assistente de voz, um script de atendimento ao cliente ou até mesmo um sabor personalizado de uma máquina bebidas. Teste ou personalize experiências nas atividades do [!DNL Target]. [Saiba mais](/help/c-experiences/experiences.md). |
| Ofertas | Um bloco de conteúdo que pode conter imagens, texto, HTML, links, vídeo, um botão de ação, uma resposta do assistente de voz ou qualquer outro tipo de conteúdo. Uma oferta pode ser de desconto, frete grátis e assim por diante. Uma oferta pode ser exibida em uma página da Web, mas também pode ser acessada em qualquer ponto de contato do cliente, como um assistente de voz ou console de jogos. Ao testar uma oferta, você mede seu sucesso em comparação a outras ofertas ou nenhuma oferta. [Saiba mais](/help/c-experiences/c-manage-content/manage-content.md). |
| Públicos-alvo | Um grupo de pessoas com as mesmas características, como um novo visitante, um visitante recorrente ou visitantes recorrentes do meio-oeste. O recurso de Público permite direcionar conteúdo e experiências diferentes para públicos-alvo específicos para otimizar o marketing digital, ao exibir as mensagens certas para as pessoas certas, na hora certa. Se um visitante for identificado como parte de um público-alvo de direcionamento, [!DNL Target] determinará qual experiência deve ser exibida, com base nos critérios definidos durante a criação da atividade. [Saiba mais](/help/c-target/target.md). |
| Métricas de sucesso | As principais medidas de negócios que permitem determinar o sucesso de uma determinada experiência ou oferta em uma atividade [!DNL Target] . Por exemplo, você pode determinar se uma nova oferta aumenta sua receita por visitante ou adicionar um item ao carrinho de compras. As métricas de sucesso podem ser úteis para descobrir problemas nos funis de registro, pedido ou compra, além de facilitar a descoberta de problemas no envolvimento de visitantes ou clientes. [Saiba mais](/help/c-activities/r-success-metrics/success-metrics.md). |
| Relatórios | Informações sobre o progresso e os resultados de suas atividades que ajudam a tomar decisões com base em seus dados. Os dados dos relatórios podem ajudá-lo a decidir quando finalizar um teste, mostrar a experiência ou a oferta vencedora e fornecer os insights ou os aprendizados necessários para determinar as próximas ações. [Saiba mais](/help/c-reports/reports.md). |

## Ferramentas de criação de atividades

[!DNL Target] O fornece três principais maneiras de configurar suas atividades de teste e personalização, o  [!UICONTROL Visual Experience Composer]  (VEC), o Experience Composer baseado em  [!UICONTROL formulário] e o Visual Experience Composer [!UICONTROL  de aplicativo de página ]única (SPA). Ambos o orientam pelo processo de configuração da atividade em três etapas: definindo as experiências, selecionando ou definindo os públicos-alvo e selecionando as métricas de sucesso primárias e secundárias pelas quais você medirá os resultados de sua atividade.

| Ferramenta | Detalhes |
| --- | --- |
| Visual Experience Composer (VEC) | Uma interface WYSIWYG que permite criar e testar facilmente experiências e ofertas personalizadas no contexto do site. Você pode criar experiências e ofertas para atividades [!DNL Target] arrastando e soltando, alternando e modificando o layout e o conteúdo de uma página da Web (ou oferta) ou página da Web móvel. [Saiba mais](/help/c-experiences/c-visual-experience-composer/visual-experience-composer.md). |
| [!UICONTROL Experience Composer baseado em formulário] | Uma experiência não visual e interface de criação de ofertas útil para criar experiências para uso em testes A/B, direcionamento de experiência, Automated Personalization e atividades do Recommendations quando o Visual Experience Composer não estiver disponível ou for prático para uso. Por exemplo, você pode usar o composer baseado em formulário para criar experiências e ofertas para entrega em emails, quiosques e assistentes de voz. [Saiba mais](/help/c-experiences/form-experience-composer.md). |
| [!UICONTROL Aplicativo de página única (SPA) no Visual Experience Composer] | O VEC para SPAs permite que os comerciantes criem testes e personalizem conteúdo em SPAs de forma autônoma, sem dependências de desenvolvimento contínuas. O VEC pode ser usado para criar atividades de teste A/B e Direcionamento de experiência (XT) em estruturas populares, como o React e o Angular. [Saiba mais](/help/c-experiences/spa-visual-experience-composer.md). |

## Governança e controlo

Para fornecer às pessoas certas as funções e os níveis associados de acesso e permissões para [!DNL Target], temos um console administrativo. Para usuários do [!UICONTROL Target Premium], oferecemos controle e controle mais detalhados
com [!UICONTROL Permissões empresariais].

| Ferramenta | Detalhes |
| --- | --- |
| [!UICONTROL Adobe Admin Console for Enterprise] | Adicione usuários ao Adobe Target e atribua permissões do Adobe Admin Console. [Saiba mais](/help/administrating-target/c-user-management/c-user-management/user-management.md). |
| [!UICONTROL Permissões empresariais] <br> (Premium) | Um meio de administrar formalmente o acesso de usuários empresariais no [!DNL Target]. Adicione usuários a [!DNL Target], atribua permissões com base em suas funções e crie espaços de trabalho para equipes com base em diferentes departamentos, locais globais, canais e outros agrupamentos lógicos. É possível atribuir aos usuários as funções de Observador, Editor, Editor ou Aprovador. [Saiba mais](/help/administrating-target/c-user-management/property-channel/property-channel.md). |

## Integrações

[!DNL Target] O pode integrar com muitos sistemas originais, secundários e de terceiros. Esses
as integrações podem ser valiosas para fornecer acesso aos dados de visitantes e clientes disponíveis nesses sistemas para uso na criação de públicos-alvo para testes e personalização. Como parte de [!DNL Adobe Experience Cloud], [!DNL Target] integra-se perfeitamente com as soluções [!DNL Experience Cloud] e seus Serviços principais.

| Integração | Detalhes |
| --- | --- |
| Adobe Experience Cloud | [!DNL Target] O tem recursos incorporados com outras  [!DNL Adobe Experience Cloud] soluções para personalizar experiências em escala. Aproveite o poder de [!DNL Target] junto com [Adobe Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md), [Experience Cloud Audiences](/help/c-integrating-target-with-mac/mmp.md), [Adobe Campaign](/help/c-integrating-target-with-mac/campaign-and-target.md), [Adobe Audience Manager](/help/c-integrating-target-with-mac/audience-manager-target-integration.md) (AAM) e [Adobe Experience Manager](/help/c-experiences/c-manage-content/aem-experience-fragments.md) (AEM). |
| APIs do Target (Premium) | [!UICONTROL O ] Target oferece mais de 40 APIs que você pode usar para integrar o Adobe Target com sistemas primários, secundários e de terceiros. [Saiba mais](/help/api/api-overview.md). |

## Lembre-se

Considere as seguintes ideias antes de passarmos para o próximo capítulo: &quot;Desenvolver suas ideias de teste e personalização.&quot;

### Práticas recomendadas para otimização

* **Boa estratégia**: Qual é o nosso objetivo e a nossa hipótese? Eles estão alinhados? Por exemplo, queremos aumentar os envios de aplicativos de empréstimo, portanto, hipóteses de que a redução do número de campos no formulário de aplicativo fará isso.
* **Disciplinar** metodologiaEstamos começando a testar nos lugares certos? Por exemplo, você precisa de locais com tráfego suficiente e que afetam as métricas importantes    à empresa.
* **** Configuração adequadaNossa atividade está configurada para atingir nosso objetivo? Por exemplo, se estamos tentando aumentar os envios de pedidos de empréstimo, devemos direcionar os interessados em empréstimos e medir cliques do botão &quot;Enviar&quot;.
* **Análise** completa: A atividade de teste foi executada até a conclusão? O que dizem os resultados? Execute sua atividade até atingir 95% a 99% de confiança estatística. Documente por que você acha que a experiência vencedora ganhou e aplique o aprendizado em outro lugar.
* **Teste** iterativo: Estamos a partir dos conhecimentos de atividades anteriores? Se você encontrar uma tática vencedora, tente aprimorá-la ou fazer alterações que funcionem com ela para melhorar ainda mais sua métrica de sucesso.

### As opiniões podem afetar negativamente os resultados

* Opiniões que podem afetar negativamente a sua eficácia. Opinião da pessoa paga mais alta (HIPPO), atitudes, preconceitos. Por exemplo, o CEO deseja reduzir o tamanho da caixa de pesquisa para criar mais espaço em cada página. Devemos testar para garantir que não reduza o número de pesquisas.
* O senhor está atuando com base em opiniões? Eu não gosto da aparência do teste. O cliente não vai gostar dessa experiência. Embora a intuição seja útil, o teste A/B tem provado, repetidas vezes, que nem sempre é pontual.
* Ou você tem uma mentalidade de otimização? Estou animado em ver qual experiência vence. Temos opções suficientes para testar?

### Os pressupostos também podem afetar negativamente os resultados

* Pressupostos que podem afetar negativamente sua eficácia. Mentalidade de herança (é assim que nossos concorrentes fazem isso). Por exemplo, todos os nossos concorrentes usam banners de heróis com imagens rotativas, então também deveríamos.
* Supondo que saibamos por que algo está ou não funcionando. Supondo que não precisemos testar algo. Por exemplo, sempre listamos os quartos de hotel na ordem do preço mais alto ao mais baixo como padrão.
* Você está agindo com suposições? Não precisamos testar isso, verificamos a análise. (Sim, mas pode haver mais informações na história do que o analytics revela.)
* Ou você tem uma mentalidade de otimização? Nós testamos tudo.
