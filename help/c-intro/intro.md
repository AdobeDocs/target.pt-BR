---
keywords: Target Standard;Recommendations;Target Premium;Automated Personalization;auto-target;auto target;permissions;what is adobe target;
description: O Adobe Target é a solução da Adobe Experience Cloud que oferece tudo o que você precisa para ajustar e personalizar a experiência do cliente e maximizar a receita em sites da Web e móveis, aplicativos, mídia social e outros canais digitais.
title: Introdução ao Adobe Target
feature: intro
topic: Advanced
uuid: 70ccfbe9-c240-4380-9f43-522af51c1d5f
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '906'
ht-degree: 86%

---


# Introdução ao Target{#introduction-to-target}

[!DNL Adobe Target]O é a solução da que oferece tudo o que você precisa para ajustar e personalizar a experiência do cliente e maximizar a receita em sites da Web e móveis, aplicativos, mídia social e outros canais digitais.[!DNL Adobe Experience Cloud]

A solução [!DNL Adobe Target] contém vários componentes:

## Target Standard {#section_ACD5EFF17AAB4E979CBEFA0145CCD905}

O [!DNL Target Standard] é um front-end para o [!DNL Adobe Target] que o ajuda a criar visualmente e gerenciar testes A/B e atividades de direcionamento baseadas em regras e conectar à Adobe Experience Cloud. O [!DNL Target Standard] suporta a inserção de código personalizado dentro e fora do fluxo de Trabalho do [!UICONTROL Visual Experience Composer]. O [!DNL Target Standard] oferece uma estratégia de implementação simplificada com suas propriedades digitais: somente uma linha de código em cada página gerencia toda a comunicação necessária entre o seu site e o [!DNL Adobe Target].

As práticas recomendadas do setor são criadas no [!DNL Target Standard] e projetadas para serem usadas por usuários novos e experientes. É possível compartilhar dados e resultados e colaborar facilmente com membros de outra equipe que usam a [!DNL Adobe Experience Cloud].

## Target Premium {#premium}

O [!DNL Target Premium] é uma licença avançada do [!DNL Target] que adiciona recursos premium ao [!DNL Target Standard].

[!DNL Target Premium] os tópicos desta ajuda incluem o selo Premium na parte superior da página:

![Selo premium](/help/assets/premium.png)

O Target Premium inclui os seguintes recursos premium:

### Personalização automatizada

A [Personalização automatizada](../c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) oferece algoritmos avançados de aprendizado automatizado, que impulsionam experiências personalizadas e taxas de conversão aprimoradas para experiências digitais.

A personalização automatizada (anteriormente Test&amp;Target 1:1) registra a atividade de visitantes no site, criando um perfil de visitantes para que o conteúdo possa ser direcionado para visitantes semelhantes. Ele rastreia respostas ao conteúdo, tanto para indivíduos como populações como um todo, e utiliza abordagens de modelagem sofisticadas para direcionar automaticamente cada indivíduo, levando em conta tudo o que se sabe sobre esse visitante.

A personalização automatizada aprende sozinha e requer um mínimo de análise humana. Completamente automatizado, ele aprende continuamente. O sistema constrói modelos e aprende automaticamente quais produtos provavelmente serão mais interessantes para um visitante individual. Toda vez que um visitante interage com o site, as informações são coletadas e armazenadas no perfil do visitante. Há vários algoritmos disponíveis para fornecer o melhor modelo para o seu sistema.

### Direcionamento automático

[O Direcionamento automático para experiências personalizadas](../c-activities/auto-target-to-optimize.md#concept_67779E5B7F67427A97D7EA2A6FB919B3) usa aprendizagem de máquina avançada para identificar várias experiências definidas pelo profissional de marketing com desempenho elevado e retorna a experiência mais personalizada para cada visitante com base no perfil individual do cliente e no comportamento de visitantes anteriores com perfis similares, a fim de personalizar o conteúdo e gerar conversões.

### Recommendations

As atividades do [Recommendations](../c-recommendations/recommendations.md#concept_7556C8A4543942F2A77B13A29339C0C0) exibem automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base em atividades do usuário anteriores. O Recommendations ajuda a direcionar os clientes para itens relevantes que podem ser novidade para eles.

Uma recomendação determina como um produto é sugerido a um cliente, dependendo das atividades desse cliente no site. Por exemplo:

* Incentive pessoas que compram uma mochila a considerar a compra de tênis de trilha e varas de trekking.

   Crie uma recomendação para mostrar itens que são frequentemente comprados juntos, usando o critério &quot;Pessoas que compraram isso também compraram aquilo&quot;.

* Aumente o tempo que os visitantes gastam no seu site de mídia ao recomendar conteúdo de vídeos semelhante àqueles que estão assistindo atualmente.

   Crie uma recomendação que sugira outros vídeos, usando o critério &quot;Pessoas que viram isso viral aquilo&quot;.

* Sugira que clientes que visualizaram informações sobre planos de economia no banco também leiam sobre contas IRA.

   Mostre outros produtos que as pessoas adquiriram após visualizar um produto sem mostrar o primeiro produto nas recomendações, usando o critério &quot;pessoas que viram isso também compraram&quot;.

### Recommendations como uma oferta

[As recomendações como uma oferta](/help/c-recommendations/recommendations-as-an-offer.md) permitem inclui-las nas atividades de [!UICONTROL Teste A/B] (inclusive [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) e [!UICONTROL Direcionamento de experiência] (XT).

Essa funcionalidade permite capacidades nunca antes vistas, como:

* Teste e direcione conteúdo de recomendações e não recomendações em uma mesma atividade.
* Experimente com facilidade a colocação de recomendações na página, incluindo a ordem de várias recomendações.
* Impulsione automaticamente o tráfego para a experiência do recommendations com melhor desempenho usando [!UICONTROL Alocação automática].
* Atribua de maneira dinâmica os visitantes a experiências de recomendação personalizadas com base em seus perfis usando o [!UICONTROL Direcionamento automático].

### Permissões de usuário empresarial

[A funcionalidade Permissões](../administrating-target/c-user-management/property-channel/property-channel.md#concept_E396B16FA2024ADBA27BC056138F9838) de usuário corporativo permite criar projetos diferentes (chamados de &quot;Perfis de produto&quot; no [!DNL Adobe Admin Console for Enterprise]) para permitir que você atribua permissões diferentes a um único usuário que dita os direitos de acesso desse usuário para cada projeto. Esses projetos distintos podem ser comparados à maneira como os conjuntos de relatórios funcionam no [!DNL Adobe Analytics]. Cada projeto pode ter usuários específicos com funções específicas que se aplicam a um conjunto de propriedades. O resultado é que os clientes poderão restringir o acesso à visualização, editar, aprovar e publicar aos seus usuários com base na região, ambiente (dev/stage/prod), canal ou outros critérios personalizados.

## Recommendations Classic {#section_9554068100054D2DBDB298CBE5A0E413}

O [!DNL Recommendations Classic] exibe automaticamente produtos ou conteúdo que podem ser do interesse dos clientes com base na atividade do usuário anterior no seu site da Web. O Recommendations ajuda a direcionar clientes para itens que, de outra forma, eles talvez eles não conhecessem, melhorando as vendas geradas no seu site.

Para obter mais informações, consulte a [documentação do Recommendations Classic](../assets/adobe-recommendations-classic.pdf).

## Experience League: o kit de boas-vindas do Adobe Target {#kit}

Crie seu programa de otimização e personalização no Adobe Target com este kit de boas-vindas! It includes key information, tools, and resources to help you prepare for and launch your first [!DNL Adobe Target] activity, with short-term quick wins and long-term optimization strategies.

[O kit de boas-vindas da Adobe Target](https://expleague.azureedge.net/pdf/Adobe-Target-Welcome-Kit.pdf)

## Vídeo de treinamento: Etiqueta de ![Visão Geral de Tipos de atividades (9:03)](/help/assets/overview.png)

O vídeo a seguir explica os tipos de atividade disponíveis no [!DNL Target Standard/Premium] e como o fluxo de Trabalho guiado em três etapas do Target pode ajudar você a alcançar as metas do seu site.

* Descreva os tipos de atividade incluídos no Adobe Target
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)
