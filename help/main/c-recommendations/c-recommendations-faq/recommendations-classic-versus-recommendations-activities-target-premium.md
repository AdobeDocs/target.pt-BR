---
keywords: Recomendações, algoritmos do recommendations, atividade do recommendations, recommendations classic
description: Examine as informações para ajudar você a entender as diferenças entre as atividades herdadas do Recommendations Classic e do Recommendations no [!DNL Target] Premium.
title: Qual é a diferença entre o Recommendations Classic e o Recommendations no [!DNL Target] Premium?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 07548155-9548-4870-b886-6cb4ff37a0bd
TQID: 'https://experienceleague.adobe.com/EoTkyY0kOwRKT52WIwOuTCoUziIJOnNtTo6llsTNpsM'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
    internal-label: Implementation
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 19%
---
# Atividades do Recommendations Classic versus Recommendations no [!DNL Target] Premium {#classic-versus-activities}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como [!DNL Recommendations Classic] difere de [!DNL Recommendations] atividades em [!DNL Target Premium] para escolher entre elas.

>[!ENDSHADEBOX]

>[!NOTE]
>
>As atividades do [!DNL Recommendations] estão disponíveis como parte da solução do [!DNL Target Premium]. Elas não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

No produto do [!DNL Recommendations] clássico, as recomendações foram exibidas com a criação de uma mbox de coleta de dados em uma página seguida da adição de uma mbox de exibição em um local específico da página. A atividade [!DNL Recommendations] do [!DNL Target Premium] coleta informações do visitante e cria as recomendações em qualquer lugar da página, sem uma mbox para cada local onde os produtos ou conteúdo são recomendados. Uma referência de JavaScript no cabeçalho da página ativa recomendações em qualquer lugar da página. Essa referência passa chaves, como as chaves `entity.id` e `entity.categoryId`, para a mbox global [!DNL Target].

O [!DNL Recommendations Classic] é exibido como o seu próprio cartão na interface do usuário da [!DNL Experience Cloud]. Uma atividade do [!DNL Recommendations] está disponível com o fluxo de trabalho do [!DNL Target Premium].

Os usuários do [!DNL Recommendations Classic] podem continuar a usar as mboxes do [!DNL Recommendations] no [!DNL Target Recommendations]. As abordagens clássica e [!DNL Target] também podem ser combinadas, mantendo as mboxes e usando o código JavaScript no cabeçalho para ativar a funcionalidade [!DNL Recommendations] para os outros elementos da página. No entanto, para obter a funcionalidade total do [!DNL Target], os usuários do [!DNL Recommendations Classic] podem preferir excluir a mbox antiga e confiar somente no [!DNL Target Recommendations].

A atividade [!DNL Recommendations] no [!DNL Target] aprimora o [!DNL Recommendations Classic] nas principais áreas a seguir.

## Recomendações como oferta {#recs-as-offer}

As recomendações podem ser incluídas nas atividades de [!UICONTROL Teste A/B] (incluindo [!UICONTROL Alocação automática] e [!UICONTROL Direcionamento automático]) e [!UICONTROL Direcionamento de experiência] (XT). Isso permite testar e direcionar conteúdo de recomendações e não recomendações na mesma atividade, entre outros recursos. Para obter mais informações, consulte [Recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

## Critérios {#criteria-comparison}

[!DNL Target Recommendations] inclui uma biblioteca de critérios com conjuntos pré-empacotados de regras e configurações. No [!DNL Recommendations Classic], cada recomendação foi criada manualmente através do preenchimento de um formulário e escolhida em uma grande lista de regras. Quando uma atividade [!DNL Recommendations] é criada, um conjunto de critérios pré-configurado é escolhido. Recomendações personalizadas ainda podem ser criadas, mas a biblioteca de critérios contém muitas das configurações mais comuns, pré-criadas para simplificar o processo e usar uma linguagem que as pessoas entendem. Os critérios pré-embalados podem ser usados como estão ou copiados e editados para atender a necessidades específicas.

![Slide mostrando um cartão de critérios, venda adicional, com a linguagem que as pessoas entendem, as regras e a lógica e a configuração rotulada](assets/overview_criteria.png)

Os critérios são predefinidos e classificados por setores da indústria, tipos de página e implementação. Por exemplo, os critérios que se aplicam ao setor varejista podem ser encontrados para uso em uma página de produto, mostrando produtos dentro de uma categoria específica (como definido pelo parâmetro `entity.categoryID`).

Para obter mais informações sobre o uso e a criação de critérios, consulte [Critérios](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Fluxo de trabalho (WRK) {#workflow-comparison}

O fluxo de trabalho do [!DNL Recommendations] está simplificado. Em vez de formulários complicados, um fluxo de trabalho visual orienta pelas seguintes etapas:

1. Selecionar o critério.
1. Selecione um [design](/help/main/c-recommendations/c-design-overview/create-design.md#create-design) pré-configurado.
1. Visualize as recomendações resultantes.

## Visualização visual {#visual-preview}

As recomendações podem ser visualizadas depois de configuradas e quaisquer alterações necessárias podem ser feitas, sem criar as recomendações na página e depois testá-las. As visualizações estão disponíveis no [!DNL Target].

## Direcionamento {#targeting-comparison}

[!DNL Recommendations Classic] tinha seis opções de direcionamento. [!DNL Recommendations] atividades usam o intervalo completo de [!DNL Target] opções de direcionamento. Um público é definido usando [!DNL Target] ou outros [!DNL Adobe Experience Cloud] públicos (como [!DNL Audience Manager] e [!DNL Analytics]). A porcentagem de participantes da atividade que visualizam cada design e a porcentagem de que visualizam o controle são selecionadas.

![Diagrama de fluxo com o público-alvo Todos os visitantes, os critérios de venda adicional, três designs com 30% de tráfego cada e o grupo de controle Sem recomendação](assets/overview_targeting.png)

## Relatório {#reporting-comparison}

No [!DNL Target], o [!DNL Recommendations] fornece relatórios aprimorados que aproveitam os recursos do [!DNL Target] e do [!DNL Experience Cloud]. Em vez de mostrar apenas o aumento que [!DNL Recommendations] fornece em comparação aos resultados sem ele, os relatórios mostram informações completas sobre a atividade [!DNL Recommendations].

