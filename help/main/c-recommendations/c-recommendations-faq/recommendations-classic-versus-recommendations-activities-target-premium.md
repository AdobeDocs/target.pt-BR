---
keywords: Recomendações, algoritmos do recommendations, atividade do recommendations, recommendations classic
description: Examine as informações para ajudar você a entender as diferenças entre as atividades herdadas do Recommendations Classic e do Recomendações no  [!DNL Target] Premium.
title: Qual é a diferença entre o Recommendations Classic e o Recomendações no  [!DNL Target] Premium?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 07548155-9548-4870-b886-6cb4ff37a0bd
TQID: https://experienceleague.adobe.com/EoTkyY0kOwRKT52WIwOuTCoUziIJOnNtTo6llsTNpsM
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 665
ht-degree: 86%

---

# Atividades do Recommendations Classic versus Recommendations no [!DNL Target] Premium

Informações para escolher entre as atividades Recommendations Classic e Recomendações no Target Premium.

>[!NOTE]
>
>As atividades do Recomendações estão disponíveis como parte da solução do [!DNL Target Premium]. Elas não estão disponíveis no [!DNL Target Standard] sem uma licença do [!DNL Target Premium].

No produto do [!DNL Recommendations] clássico, as recomendações foram exibidas com a criação de uma mbox de coleta de dados em uma página seguida da adição de uma mbox de exibição em um local específico da página. A atividade do [!DNL Recommendations] no [!DNL Target Premium] permite a criação de recomendações em qualquer lugar da página, sem a necessidade de criar uma mbox para cada local onde deseja recomendar os produtos ou conteúdo. Uma simples referência de JavaScript no cabeçalho da página habilita recomendações em qualquer lugar da página. Use essa referência do JavaScript para enviar as chaves à mbox do [!DNL Target], como as chaves do `entity.id` e `entity.categoryId`.

O [!DNL Recommendations Classic] é exibido como o seu próprio cartão na interface do usuário da [!DNL Experience Cloud]. Uma atividade do [!DNL Recommendations] está disponível com o fluxo de trabalho do [!DNL Target Premium].

Os usuários do [!DNL Recommendations Classic] podem continuar a usar as mboxes do [!DNL Recommendations] no [!DNL Target Recommendations]. Eles também podem combinar as abordagens clássicas e [!DNL Target] ao manter as mboxes e usar o código do JavaScript no cabeçalho para ativar a funcionalidade do [!DNL Recommendations] para outros elementos da página. No entanto, para obter a funcionalidade total do [!DNL Target], os usuários do [!DNL Recommendations Classic] podem preferir excluir a mbox antiga e confiar somente no [!DNL Target Recommendations].

A atividade do [!DNL Recommendations] no [!DNL Target] aprimora o [!DNL Recommendations Classic] nas principais áreas a seguir:

## Recomendações como oferta

Você pode incluir recomendações nas atividades de [!UICONTROL A/B Test] (inclusive [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target]) e [!UICONTROL Experience Targeting] (XT).

Essa funcionalidade permite capacidades nunca antes vistas, como:

* Teste e direcione conteúdo de recomendações e não recomendações em uma mesma atividade.
* Experimente com facilidade a colocação de recomendações na página, incluindo a ordem de várias recomendações.
* Impulsione automaticamente o tráfego para a experiência do recommendations com melhor desempenho usando o [!UICONTROL Auto-Allocate].
* Atribua de maneira dinâmica os visitantes a experiências de recomendação personalizadas com base em seus perfis usando o [!UICONTROL Auto-Target].

Para começar, crie uma atividade [!UICONTROL A/B Test] ou [!UICONTROL Experience Targeting] usando o [!UICONTROL Visual Experience Composer] e use a ação [!UICONTROL Insert Before], [!UICONTROL Insert After] ou [!UICONTROL Replace With] para adicionar recomendações a uma experiência.

Para obter mais informações, consulte [Recomendações como uma oferta](/help/main/c-recommendations/recommendations-as-an-offer.md).

## Critérios {#section_117709846DAA404580EBE879FFCBD9BA}

[!DNL Target Recommendations] inclui uma biblioteca de critérios com conjuntos pré-embalados de regras e configurações. No [!DNL Recommendations Classic], cada recomendação foi criada manualmente através do preenchimento de um formulário e escolhida em uma grande lista de regras. Agora, ao criar uma atividade do [!DNL Recommendations], basta escolher um conjunto de critérios predefinidos. Você ainda pode criar recomendações personalizadas, mas a biblioteca de critérios contém muitas das configurações mais comuns, pré-criadas para simplificar o processo e usando uma linguagem simples. Estes critérios pré-embalados podem ser usados como estão ou podem ser copiados e editados para atender às suas necessidades específicas.

![imagem de overview_criteria](assets/overview_criteria.png)

Os critérios são predefinidos e classificados por setores da indústria, tipos de página e implementação. Por exemplo, você pode procurar pelos critérios que se aplicam ao setor varejista, para o uso em uma página do produto, mostrando produtos dentro de uma categoria específica (como definido pelo parâmetro `entity.categoryID`).

Para obter mais informações sobre o uso e a criação de critérios, consulte [Critérios](/help/main/c-recommendations/c-algorithms/algorithms.md).

## Fluxo de trabalho (WRK) {#section_76B4A26297BF422382DE2C79A2713D3C}

O fluxo de trabalho do [!DNL Recommendations] foi simplificado. Em vez de preencher formulários complicados, você segue um fluxo de trabalho visual para:

1. Selecionar o critério.
1. Selecione um [design](/help/main/c-recommendations/c-design-overview/create-design.md#task_CC5BD28C364742218C1ACAF0D45E0E14) pré-configurado.
1. Visualize as recomendações resultantes.

## Visualização do visual {#section_639B9E38C9EC4093BF9023EE0F2A15AC}

Você pode visualizar suas recomendações depois de configurá-las e fazer as alterações necessárias, sem ter que criá-las na página e testá-las. As visualizações estão disponíveis no [!DNL Target].

## Direcionamento {#section_93295EA0DBA14210B8518AF4802A459F}

No [!DNL Recommendations Classic], existem seis opções de direcionamento. As atividades do Recomendações usam a linha completa de opções de direcionamento do Target. Defina um público-alvo usando o [!DNL Target] ou outros públicos da [!DNL Adobe Experience Cloud] (como o [!DNL Audience Manager] e [!DNL Analytics]), em seguida, selecione o percentual de participantes da atividade que visualizam cada design e que visualizam o controle.

![imagem de &lbrace;overview_targeting](assets/overview_targeting.png)

## Relatório {#section_25C2FCCE4BC1488496C517C0470B5CD6}

No [!DNL Target], o [!DNL Recommendations] fornece relatórios aprimorados que aproveitam os recursos fornecidos pelo [!DNL Target] e a [!DNL Experience Cloud]. Em vez de simplesmente mostrar o incentivo fornecido pelo [!DNL Recommendations] em comparação com os resultados sem ele, você pode visualizar as informações completas sobre as atividades do [!DNL Recommendations].

![imagem do overview_report](assets/overview_report.png)
