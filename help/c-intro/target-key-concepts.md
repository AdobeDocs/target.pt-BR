---
keywords: Overview and Reference;act
description: Informações sobre os principais conceitos que ajudarão você a entender os recursos e capacidades do Adobe Target.
title: Conceitos-chave do Target
feature: intro
subtopic: Getting Started
topic: Standard
uuid: c62ac156-b4cf-494c-979f-33f889abd118
translation-type: tm+mt
source-git-commit: 95450abc32be19d04b791af3c62673e9411ab53c
workflow-type: tm+mt
source-wordcount: '1515'
ht-degree: 98%

---


# Conceitos-chave do Target{#target-key-concepts}

Informações sobre os principais conceitos que ajudarão você a entender os recursos e capacidades do Adobe Target.

## Atividades e testes {#section_BEA0A0C51A8847579B566060206DE7E8}

Uma atividade determina as experiências que um visitante do site pode ter.

Por exemplo, você pode criar uma atividade que teste duas páginas de aterrissagem diferentes, uma destacando informações sobre sapatos femininos de verão e outra destacando vestuário de verão mais geral. A atividade determina as condições que controlam quando cada uma dessas páginas de aterrissagem será exibida e as métricas que determinam qual página tem maior sucesso. A atividade está configurada para iniciar e terminar quando as condições específicas forem cumpridas, como entre datas específicas, ou para iniciar quando a atividade for aprovada e terminar quando ela for desativada.

Ao projetar uma atividade, você deve planejar com cuidado. Determine quando a atividade vai começar e quanto tempo ela durará. Depois, relacione as ofertas e atribua um público-alvo a cada uma.

O Target inclui vários tipos de atividades. A tabela a seguir fornece uma visão geral de cada tipo de atividade com links para ajudá-lo a saber mais. Para ajudá-lo a escolher de maneira mais eficaz o melhor tipo de atividade para suas finalidades, também criamos o [Guia de atividades do Adobe Target](/help/c-activities/target-activities-guide.md).

| Tipo de atividade | Descrição |
|--- |--- |
| [Teste A/B](/help/c-activities/t-test-ab/test-ab.md) | O teste A/B compara duas ou mais versões do conteúdo do seu site para ver qual versão melhora suas conversões durante um período de teste pré-especificado.<br>**Observação:** agora você pode incluir [recomendações nas atividades de Teste A/B](/help/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/c-intro/intro.md#premium). |
| [Alocação automática](/help/c-activities/automated-traffic-allocation/automated-traffic-allocation.md) | A Alocação automática identifica um vencedor entre duas ou mais experiências e realoca automaticamente mais tráfego para o vencedor a fim de aumentar as conversões enquanto o teste continua a ser executado e aprendido.<br>**Observação:** agora você pode incluir [recomendações nas atividades de Alocação automática](/help/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/c-intro/intro.md#premium). |
| [Direcionamento automático](/help/c-activities/auto-target/auto-target-to-optimize.md)<br>![Target Premium](/help/assets/premium.png) | O Direcionamento automático usa aprendizagem de máquina avançada para identificar várias experiências definidas pelo profissional de marketing com desempenho elevado e retorna a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares, a fim de personalizar o conteúdo e gerar conversões.<br>**Observação:** agora você pode incluir [recomendações nas atividades de Direcionamento automático](/help/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/c-intro/intro.md#premium). |
| [Uso de dados do Analytics](/help/c-activities/t-test-ab/t-test-create-ab/create-a4t.md) (A4T) | Você pode configurar uma atividade para usar o [!DNL Adobe Analytics] como fonte de geração de relatórios. Este tipo de atividade requer a vinculação da sua conta da [!DNL Adobe Experience Cloud] ao [!DNL Analytics] e ao [!DNL Target]. |
| [Teste multivariado](/help/c-activities/c-multivariate-testing/multivariate-testing.md) | O Teste multivariado (MVT) compara combinações de ofertas em elementos em uma página para determinar qual combinação tem o melhor desempenho para um público-alvo específico e identifica qual elemento afeta mais o sucesso da atividade. |
| [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md) | O Direcionamento de experiência (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.<br>**Observação:** agora você pode incluir [recomendações nas atividades de Direcionamento de experiência](/help/c-recommendations/recommendations-as-an-offer.md). Essa funcionalidade exige uma [licença do Target Premium](/help/c-intro/intro.md#premium). |
| [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md)<br>![Target Premium](/help/assets/premium.png) | A Personalização automatizada (AP) combina ofertas ou mensagens e usa aprendizagem de máquina avançada para corresponder diferentes variações a cada visitante com base em seu perfil de cliente individual, a fim de personalizar o conteúdo e impulsionar conversões. |
| [Recommendations](/help/c-recommendations/recommendations.md)<br>![Target Premium](/help/assets/premium.png) | Uma recomendação determina como um produto é sugerido para um usuário do site, dependendo das atividades desse usuário no site.<br>Por exemplo, talvez você queira incentivar as pessoas que compraram uma mochila a pensar em comprar um tênis para caminhada e bastões de marcha. Você pode criar uma recomendação que mostre itens que são frequentemente comprados juntos, usando o algoritmo &quot;Pessoas que compraram isso também compraram aquilo&quot;. Ou talvez você queira incentivar os visitantes a passarem mais tempo no seu site de mídia recomendando vídeos semelhantes aos que eles assistiram, usando o algoritmo &quot;Pessoas que visualizaram isso também visualizaram aquilo&quot;.<br>**Observação:** agora, você pode incluir recomendações nas atividades de Teste A/B (incluindo Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT). Consulte [Recommendations como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md). |

## Localizações {#section_F18FBF1ED23340ED9F39C51971A4E874}

Fundamentalmente, uma localização é uma página no site. Pode também referir-se a um local em um aplicativo móvel, um email ou qualquer outro lugar onde você executa uma otimização.

Os locais são essenciais para as atividades e experiências. Você pode decidir se um local executará uma, ambas ou nenhuma das funções a seguir:

* Exibir e trocar conteúdo para visitantes.
* Registrar em log o comportamento do visitante.

No [!DNL Target Standard], um local pode ser qualquer elemento em uma página, desde que a página contenha uma única linha de código que ative o [!DNL Target] na seção `<head>` de cada página que você deseja rastrear. Essa linha de código chama as bibliotecas JavaScript necessárias para coletar informações e oferecer experiências direcionadas aos visitantes.

As localizações são combinadas aos públicos para fornecer um número quase infinito de opções para direcionar informações para os clientes. Por exemplo, se um visitante nunca tiver visitado o site antes, você poderá exibir um cupom de desconto para novos clientes. Da mesma forma, a página poderá ser alterada para exibir ofertas mais otimizadas para clientes que retornam.

Você também pode usar locais para rastrear o progresso do visitante no site da Web ou pode rastrear se o visitante atende a uma métrica específica de sucesso, como adicionar um item ao carrinho de compras ou concluir uma compra.

## Experiências e designs de página {#section_B806FB752EC1470784755C1EB3D4AC70}

Uma experiência, às vezes chamada de receita, define o conteúdo que é exibido na página, bem como os outros elementos da página, como links.

Uma experiência determina qual oferta é exibida em um determinado local quando condições específicas de direcionamento forem cumpridas. Por exemplo, a experiência determina que, quando um visitante visitar seu site a partir de Utah, uma oferta de envio em dois dias seja exibida em uma mbox no topo da página. A experiência também determina que, quando um novo visitante visualiza a página, um desconto de 10% aparece no mesmo local.

Uma experiência consiste em ofertas, ativos de imagem ou outros elementos HTML (como links) que aparecem na página para ajudar a direcionar o visitante para o resultado desejado. O [!DNL Target] combina locais, ofertas e experiências para determinar qual conteúdo aparece em seu site durante um teste específico.

Uma experiência também pode ser um design de página diferente. Por exemplo, uma experiência pode ter um conjunto de links na parte superior da página, onde outra experiência tem links diferentes ou os mesmos links organizados em uma ordem diferente. Talvez você queira testar se uma imagem é mais importante do que outra, ou se um anúncio tem maior probabilidade de receber um clique perto da parte superior da sua página ou em um local diferente.

O [!DNL Target] otimiza experiências para cada um dos visitantes nos pontos de contato digitais e para testar experiências diferentes para determinar o que terá maior sucesso. Ao planejar cuidadosamente o direcionamento das experiências, você pode garantir que os visitantes do seu site vejam as ofertas mais relevantes nos locais certos na sua página, melhorando suas chances de uma visita bem-sucedida.

## Ofertas {#section_973D4CC4CEB44711BBB9A21BF74B89E9}

Uma oferta é o conteúdo exibido nas suas páginas da Web durante campanhas ou atividades.

Ao testar suas páginas da Web, você mede o sucesso de cada experiência com diferentes ofertas em seus locais.

Uma oferta pode conter tipos diferentes de conteúdo, incluindo:

* Imagem
* Texto
* HTML
* Link
* Botão

Por exemplo, uma página da Web pode exibir uma de duas ofertas, dependendo se o visitante já esteve no site antes.

Uma *experiência* determina qual conteúdo será exibido quando condições específicas forem cumpridas.

## Públicos-alvo{#section_3F32DA46BDF947878DD79DBB97040D01}

Otimize o conteúdo de destino para os participantes da atividade que atenderem aos critérios específicos.

Os públicos-alvo definem a meta para sua atividade e são usados em qualquer lugar em que o direcionamento estiver disponível.

Os públicos-alvo do [!DNL Target] são um conjunto definido de critérios de visitante. As ofertas podem ser direcionadas a públicos-alvo específicos (ou segmentos). Somente os visitantes que pertencerem a esse público-alvo visualizarão a experiência direcionada a eles.

Por exemplo, talvez você queira direcionar uma atividade a um público-alvo constituído por visitantes que usam um determinado navegador ou sistema operacional.

Ou sua atividade deve ser direcionada aos visitantes de uma região geográfica ou a pessoas que acessam sua página usando determinado mecanismo de busca.

É possível salvar os públicos para reutilização em várias atividades ou eles podem ser criados para uma atividade específica.

| Tipo de público-alvo | Descrição |
|--- |--- |
| Públicos-alvo reutilizáveis | Os públicos reutilizáveis podem ser selecionados para qualquer atividade. A mudança de um desses públicos-alvo é refletida para todas as atividades que o utilizam. |
| Segmentos personalizados | Segmentos personalizados (conhecidos também como segmentos específicos de campanha) são específicos de uma campanha no Target Classic. Eles são criados como parte da campanha e não podem ser reutilizados em outras campanhas. |
| Públicos-alvo compartilhados | Os públicos-alvo podem ser compartilhados nas soluções [!DNL Adobe Experience Cloud]. See [Audiences](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html) for examples. |

Para obter informações sobre como o perfil do visitante acompanha informações sobre visitantes do site, consulte [Perfis de visitante](/help/c-target/c-visitor-profile/visitor-profile.md#concept_5E53D1A6DF224D7BAE76F4AE390B9DA1).

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Tipos de atividades (9:03) ![Etiqueta de visão geral](/help/assets/overview.png)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium].

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Usando o Audiência no Adobe Target (6:21) ![emblema de visão geral](/help/assets/overview.png)

Este vídeo explica como usar os públicos-alvo no [!DNL Target Standard/Premium].

* Explique o termo &quot;público-alvo&quot;
* Explicar as duas maneiras como o público-alvo é usado para otimização
* Encontre públicos-alvo na lista de públicos-alvo
* Segmente uma atividade para um público-alvo
* Use públicos-alvo para relatórios passivos em uma atividade

>[!VIDEO](https://video.tv.adobe.com/v/17398)
