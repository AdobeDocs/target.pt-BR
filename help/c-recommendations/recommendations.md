---
keywords: Recommendations;Recommendations criteria;recommendations algorithms;recommendations activity;criteria;recommendations targeting;recs
description: O Recommendations atividade no Adobe Target exibe automaticamente produtos ou conteúdo que podem interessar aos seus clientes com base na atividade do usuário anterior ou em outros algoritmos. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.
title: Adobe Target Recommendations
feature: recommendations general
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '930'
ht-degree: 59%

---


# ![Recommendations ](/help/assets/premium.png)PREMIUM{#recommendations}

[!DNL Adobe Target Recommendations] O atividade exibe automaticamente produtos, serviços ou conteúdo que podem interessar aos seus visitantes com base em atividades do usuário, preferências ou outros critérios anteriores. [!DNL Target Recommendations] ajuda a direcionar o visitante para itens relevantes que, de outra forma, talvez eles não conhecessem. [!DNL Recommendations] permite que você forneça aos seus visitantes conteúdo relevante na hora certa e no lugar certo.

>[!NOTE]
>
>As atividades do [!DNL Recommendations] estão disponíveis como parte da [solução Target Premium. ](/help/c-intro/intro.md#premium) Não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].
>
>Se você tiver o [!DNL Recommendations Classic], consulte [Atividades do Recommendations Classic versus Recommendations no Target Premium](/help/c-recommendations/c-recommendations-faq/recommendations-classic-versus-recommendations-activities-target-premium.md#concept_A80223EF66634EA380580C2823A581C5) para obter mais informações sobre as duas soluções.

O [!DNL Recommendations] ajuda você a otimizar e personalizar as sugestões em tempo real entre os canais, aplicativos, páginas, mensagens de email e outras opções para aumentar a participação e a conversão enquanto reduz o esforço de gerenciamento.

O [!DNL Recommendations] ajuda a:

* Criar critérios sofisticados (regras) para automatizar as recomendações
* Exibir automaticamente as recomendações usando alguns fragmentos de JavaScript
* Testar e otimizar os critérios de recomendações e os designs que exibem as recomendações
* Informar os resultados de suas atividades de recomendações

A ilustração a seguir mostra as recomendações em página da Web:

![](assets/velocity_example.png)

Uma recomendação determina como um produto é sugerido a um visitante, dependendo das atividades desse visitante no site. Por exemplo:

| Ação desejada | Recomendação |
|--- |--- |
| Incentive pessoas que compram uma mochila a considerar a compra de tênis de trilha e varas de trekking. | Crie uma recomendação para mostrar itens que são frequentemente comprados juntos, usando o critério &quot;Pessoas que compraram isso também compraram aquilo&quot;. |
| Aumente o tempo que os visitantes gastam no seu site de mídia ao recomendar conteúdo de mídia similar semelhante àqueles que estão assistindo. | Crie uma recomendação que sugira outros vídeos, usando o critério &quot;Pessoas que viram isso viral aquilo&quot;. |
| Sugira que clientes que visualizaram informações sobre planos de economia no banco também leiam sobre contas IRA. | Mostre outros produtos que as pessoas adquiriram após visualizar um produto sem mostrar o primeiro produto nas recomendações, usando o critério &quot;pessoas que viram isso também compraram&quot;. |

Para mais informações sobre estes e outros critérios do [!DNL Recommendations], consulte [Critérios](/help/c-recommendations/c-algorithms/algorithms.md).

## Termos

Antes de começar a usar [!DNL Recommendations], é útil se familiarizar com alguns dos termos usados nesta seção. Não se preocupe se você ainda não compreender totalmente esses termos, você se familiarizará com eles à medida que configurar suas atividades do [!DNL Recommendations].

| Termo | Definição |
| --- | --- |
| Atividade | As atividades em [!DNL Target] permitem que você personalize o conteúdo para audiências específicas e teste designs de página. [!DNL Recommendations] é apenas um dos muitos tipos de atividades disponíveis em  [!DNL Target]. Para obter mais informações, consulte [tipos de atividade de Público alvo](/help/c-activities/target-activities-guide.md). |
| Entidades | As entidades referem-se a itens que você quer recomendar. As entidades podem ser qualquer coisa como produtos, conteúdo (artigos, apresentações de slides, imagens, filmes e programas de tv), listas de trabalhos, restaurantes e assim por diante. Para obter mais informações, consulte [Entidades](/help/c-recommendations/c-products/products.md). |
| Feeds | Os feeds são usados para obter entidades importadas em [!DNL Recommendations]. As entidades podem ser enviadas usando arquivos CSV, o formato de feed do Google Product Search e as classificações de produtos do Adobe Analytics. Para obter mais informações, consulte  [Feeds](/help/c-recommendations/c-products/feeds.md). |
| Catálogo | Os catálogos se referem a todo o conjunto de produtos (entidades). Seu catálogo pode conter muitas coleções, uma forma de organizar seus produtos em compartimentos lógicos. |
| Coleção | As coleções se referem a um conjunto de itens semelhantes ou relacionados, como uma única categoria de produto. No entanto, você pode agrupar qualquer item em uma categoria que faça sentido para o seu negócio, como produtos em uma determinada faixa de preço ou cor, ou itens que possam ser interessantes em uma área geográfica específica. Para obter mais informações, consulte [Coleções](/help/c-recommendations/c-products/collections.md). |
| Critérios | Critérios são regras que determinam quais produtos recomendar com base em um conjunto predeterminado de comportamentos do visitante.<br>Alguns exemplos de critérios incluem: <ul><li>Pessoas que compraram isto, compraram aquilo</li><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Itens com atributos similares</li><li>Último item comprado</li><li>Categoria favorita</li></ul>  Para obter mais informações, consulte [Critérios](/help/c-recommendations/c-algorithms/algorithms.md). |
| Designs | Os designs definem a aparência das recomendações em uma atividade [!DNL Recommendations], como uma linha, coluna, tabela ou grade. A ilustração na parte superior deste artigo mostra um design de 4 x 1. Para obter mais informações, consulte [Criar um design](/help/c-recommendations/c-design-overview/create-design.md). |
| Localizações | Os locais se referem a uma área de conteúdo específica em uma página da Web, aplicativo móvel ou email no qual você executa uma atividade para fins de personalização e otimização. |
| Públicos-alvo | Audiências são grupos de participantes de atividades semelhantes que verão uma atividade direcionada. Um público-alvo é um grupo de pessoas com as mesmas características, como um novo visitante, um visitante recorrente ou visitantes recorrentes do meio-oeste. O recurso de Público permite direcionar conteúdo e experiências diferentes para públicos-alvo específicos para otimizar o marketing digital, ao exibir as mensagens certas para as pessoas certas, na hora certa. Para obter mais informações, consulte [Públicos](/help/c-target/target.md). |
| Recommendations como uma oferta | Um recurso que permite incluir recomendações dentro das atividades de teste A/B (incluindo Autoalocação e Público alvo automático) e direcionamento de experiência (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md). |

## Vídeo de treinamento: Tipos de atividade ![emblema de visão geral](/help/assets/overview.png)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium]. O [!DNL Recommendations] é discutido a partir de 7:20.

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Webinar de noções básicas do Adobe Target: Introdução ao Recommendations ![Etiqueta do tutorial](/help/assets/tutorial.png) {#intro-to-recs}

O webinar de *Introdução ao Recommendations* inclui uma análise detalhada de como utilizar o valor de [!DNL Adobe Target Recommendations]. Descubra como essa atividade do [!DNL Target] exibe automaticamente os produtos ou conteúdos que talvez interessem aos seus clientes, otimizando sugestões em tempo real com base nas visitas anteriores. Além disso, acesse a interface do usuário do [!DNL Target] para obter uma visão geral passo a passo sobre como criar uma atividade do [!DNL Recommendations].

[Introdução ao Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)