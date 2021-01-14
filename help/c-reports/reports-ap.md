---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Relatórios especializados estão disponíveis para usuários do Automated Personalization atividade no Adobe Target.
title: Relatórios de resumo de Automated Personalization
feature: Reports
translation-type: tm+mt
source-git-commit: 7b86db4b45f93a3c6169caf81c2cd52236bb5a45
workflow-type: tm+mt
source-wordcount: '388'
ht-degree: 72%

---


# ![PREMIUM](/help/assets/premium.png) Relatórios de resumo da personalização automatizada{#automated-personalization-summary-reports}

Relatórios especializados estão disponíveis para usuários de [!UICONTROL Automated Personalization] atividades em [!DNL Adobe Target].

>[!NOTE]
>
>A [!UICONTROL Personalização automatizada] está disponível como parte da solução [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] como uma licença do [Target Premium](/help/c-intro/intro.md#premium).

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada de [!UICONTROL Personalização automatizada] da lista, em seguida, clique na guia **[!UICONTROL Relatórios.]**

   Se você tiver muitas atividades, pode filtrar a lista ao selecionar [!UICONTROL Personalização automatizada] na lista suspensa [!UICONTROL Tipo].

1. (Opcional) Clique no ícone de [!UICONTROL Baixar] para baixar a exibição resumida (por exemplo, comparação de tráfego de Controle e Direcionado) conforme detalhado por todas as métricas de sucesso disponíveis.

[!UICONTROL Personalização automatizada] fornece os relatórios a seguir:

## Relatório de nível de atividade {#section_6F72FC5C790B4492B3DCECBFFA971337}

O relatório [!UICONTROL Nível de atividade] compara o desempenho agregado de usar um algoritmo de [!UICONTROL Personalização automatizada] para um conteúdo veiculado aleatoriamente (controle).

![Relatório de nível de atividade](/help/c-reports/assets/box_plot_ap.png)

As regras padrão da interpretação de resultados do teste A/B ainda são aplicáveis, incluindo incentivo, confiança, tendência, duração e assim por diante. Para obter mais informações sobre a interpretação de resultados, consulte  [Sobre o Índice de conversão](/help/c-reports/conversion-rate.md#concept_2D9FEDE8F94A485DAC86D611BFBDC844).

## Relatório de nível de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

O relatório [!UICONTROL Nível da oferta] para a experiência Random Forest compara o desempenho de cada algoritmo aplicado à oferta à mesma oferta veiculada aleatoriamente (Controle). Portanto, as ofertas não devem ser comparadas entre si nessa exibição.

Clique no algoritmo de experiência (Random Forest ou controle) para visualização do relatório [!UICONTROL Nível de Oferta].

![](assets/ap_OfferLevelRpt.png)

As ofertas podem ser mostradas em grupos de relatórios, e esses grupos de relatórios podem ser recolhidos e expandidos. Selecione [!UICONTROL Grupo de relatórios] na lista suspensa para exibir as informações com roll-up, em vez das ofertas.

>[!NOTE]
>
>O ícone de relógio indica que o modelo de algoritmo ainda está sendo criado. O ícone de marca de verificação indica que o algoritmo de base foi estabelecido.

## Segmentos automatizados

Clique no ícone [!UICONTROL Segmentos automatizados]. Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

![Ícone Segmentos automatizados](/help/c-reports/assets/icon-automated-sements-ap.png)

Para obter mais informações, consulte [Relatório de segmentos automatizados](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Clique no ícone [!UICONTROL Atributos importantes]. Este relatório mostra como, em atividades diferentes, atributos diferentes são mais (ou menos) importantes para como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

![Ícone de atributos importantes](/help/c-reports/assets/icon-important-attributes-ap.png)

Para obter mais informações, consulte [Relatório de atributos importantes](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md).