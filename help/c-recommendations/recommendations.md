---
keywords: Recommendations, critérios do Recommendations, algoritmos do recommendations, atividade do recommendations, critérios, direcionamento do recommendations
description: Saiba mais sobre as atividades do Recommendations no Adobe [!DNL Target] que exibem automaticamente conteúdo que pode ser do interesse dos clientes com base em atividades anteriores do usuário ou em outros algoritmos.
title: O que é o [!DNL Target] Recommendations?
feature: Recommendations
exl-id: 0d986e17-bc99-4c08-a963-7f9a6619609a
translation-type: tm+mt
source-git-commit: cb42be6b0791711d3a9ddf5680cf6d6e32045579
workflow-type: tm+mt
source-wordcount: '929'
ht-degree: 97%

---

# ![PREMIUM](/help/assets/premium.png) Recommendations

As atividades do [!DNL Adobe Target Recommendations] exibem automaticamente produtos, serviços ou conteúdo que podem ser do interesse dos visitantes com base em atividades do usuário anteriores, preferências ou outros critérios. O [!DNL Target Recommendations] ajuda a direcionar o visitante para itens relevantes que podem ser novidade para ele. O [!DNL Recommendations] permite fornecer aos visitantes conteúdo relevante na hora certa e no lugar adequado.

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

Uma recomendação determina como um produto é sugerido a um visitante, dependendo das atividades dele no site. Por exemplo:

| Ação desejada | Recomendação |
|--- |--- |
| Incentive pessoas que compram uma mochila a considerar a compra de tênis de trilha e varas de trekking. | Crie uma recomendação para mostrar itens que são frequentemente comprados juntos, usando o critério &quot;Pessoas que compraram isso também compraram aquilo&quot;. |
| Aumente o tempo que os visitantes gastam no seu site de mídia ao recomendar conteúdo de mídia similar semelhante àqueles que estão assistindo. | Crie uma recomendação que sugira outros vídeos, usando o critério &quot;Pessoas que viram isso viral aquilo&quot;. |
| Sugira que clientes que visualizaram informações sobre planos de economia no banco também leiam sobre contas IRA. | Mostre outros produtos que as pessoas adquiriram após visualizar um produto sem mostrar o primeiro produto nas recomendações, usando o critério &quot;pessoas que viram isso também compraram&quot;. |

Para mais informações sobre estes e outros critérios do [!DNL Recommendations], consulte [Critérios](/help/c-recommendations/c-algorithms/algorithms.md).

## Termos

Antes de começar a usar o [!DNL Recommendations], é útil se familiarizar com alguns dos termos usados nesta seção. Não se preocupe se você ainda não entender totalmente esses termos. Você se familiarizará com eles ao configurar suas atividades do [!DNL Recommendations].

| Termo | Definição |
| --- | --- |
| Atividade | As atividades no [!DNL Target] permitem personalizar o conteúdo para públicos específicos e testar designs de página. O [!DNL Recommendations] é apenas um dos muitos tipos de atividade disponíveis no [!DNL Target]. Para obter mais informações, consulte [Tipos de atividade do Target](/help/c-activities/target-activities-guide.md). |
| Entidades | As entidades referem-se a itens que você quer recomendar. As entidades podem ser produtos, conteúdo (como artigos, apresentação de slides, imagens, filmes e programas de TV), listas de trabalho, restaurantes e assim por diante. Para obter mais informações, consulte [Entidades](/help/c-recommendations/c-products/products.md). |
| Feeds | Os feeds são usados para importar entidades no [!DNL Recommendations]. As entidades podem ser enviadas usando arquivos CSV, o formato de feed do Google Product Search e as classificações de produtos do Adobe Analytics. Para obter mais informações, consulte  [Feeds](/help/c-recommendations/c-products/feeds.md). |
| Catálogo | Catálogos se referem a todo o conjunto de produtos (entidades). O catálogo pode conter muitas coleções, uma maneira de organizar seus produtos em compartimentos lógicos. |
| Coleção | As coleções se referem a um conjunto de itens semelhantes ou relacionados, como uma única categoria de produto. No entanto, você pode agrupar qualquer item em uma categoria que faça sentido para o seu negócio, como produtos em uma determinada faixa de preço ou cor, ou itens que possam ser interessantes em uma área geográfica específica. Para obter mais informações, consulte [Coleções](/help/c-recommendations/c-products/collections.md). |
| Critérios | Critérios são regras que determinam quais produtos recomendar com base em um conjunto predeterminado de comportamentos do visitante.<br>Alguns exemplos de critérios incluem: <ul><li>Pessoas que compraram isto, compraram aquilo</li><li>Pessoas que visualizaram isto, visualizaram aquilo</li><li>Itens com atributos similares</li><li>Último item comprado</li><li>Categoria favorita</li></ul>  Para obter mais informações, consulte [Critérios](/help/c-recommendations/c-algorithms/algorithms.md). |
| Designs | Os designs definem a aparência das recomendações em uma atividade do [!DNL Recommendations], como uma linha, coluna, tabela ou grade. A ilustração na parte superior deste artigo mostra um design 4 x 1. Para obter mais informações, consulte [Criar um design](/help/c-recommendations/c-design-overview/create-design.md). |
| Localizações | Os locais se referem a uma área de conteúdo específica em uma página da Web, aplicativo móvel ou email, em que você executa uma atividade para fins de personalização e otimização. |
| Públicos-alvo | Públicos são grupos de atividades semelhantes que verão uma atividade direcionada. Um público-alvo é um grupo de pessoas com as mesmas características, como um novo visitante, um visitante recorrente ou visitantes recorrentes do meio-oeste. O recurso de Público permite direcionar conteúdo e experiências diferentes para públicos-alvo específicos para otimizar o marketing digital, ao exibir as mensagens certas para as pessoas certas, na hora certa. Para obter mais informações, consulte [Públicos](/help/c-target/target.md). |
| Recommendations como uma oferta | As recomendações como uma oferta permitem inclui-las nas atividades de Teste A/B (inclusive Alocação automática e Direcionamento automático) e Direcionamento de experiência (XT). Para obter mais informações, consulte [Recommendations como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md). |

## Vídeo de treinamento: tipos de atividade ![Selo de visão geral](/help/assets/overview.png)

Este vídeo explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium]. O [!DNL Recommendations] é discutido a partir de 7:20.

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)

## Webinar de noções básicas do Adobe Target: Introdução ao Recommendations ![Selo de tutorial ](/help/assets/tutorial.png) {#intro-to-recs}

O webinar de *Introdução ao Recommendations* inclui uma análise detalhada de como utilizar o valor de [!DNL Adobe Target Recommendations]. Descubra como essa atividade do [!DNL Target] exibe automaticamente os produtos ou conteúdos que talvez interessem aos seus clientes, otimizando sugestões em tempo real com base nas visitas anteriores. Além disso, acesse a interface do usuário do [!DNL Target] para obter uma visão geral passo a passo sobre como criar uma atividade do [!DNL Recommendations].

[Introdução ao Recommendations](https://adobecustomersuccess.adobeconnect.com/p8gt31drhs3e/?OWASP_CSRFTOKEN=4bd6cac5d0806167ee0a5449ba93d6300548d09c922bcb751c38973897a5703a)
