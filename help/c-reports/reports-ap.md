---
keywords: Targeting;AP reports;automated personalization reports;activity level report;offer level report;offer detail report
description: Como usar os relatórios de Resumo da Automated Personalization?
title: Relatórios de resumo de Automated Personalization
feature: Reports
translation-type: tm+mt
source-git-commit: de8245e237be407f5a6a6a0ccf2d40209eb7fda1
workflow-type: tm+mt
source-wordcount: '632'
ht-degree: 43%

---


# ![PREMIUM](/help/assets/premium.png) Relatórios de resumo da personalização automatizada

Relatórios especializados estão disponíveis para usuários de [!UICONTROL Automated Personalization] atividades em [!DNL Adobe Target].

>[!NOTE]
>
>A [!UICONTROL Personalização automatizada] está disponível como parte da solução [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] como uma licença do [Target Premium](/help/c-intro/intro.md#premium).

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada de [!UICONTROL Personalização automatizada] da lista, em seguida, clique na guia **[!UICONTROL Relatórios.]**

   Se você tiver muitas atividades, pode filtrar a lista ao selecionar [!UICONTROL Personalização automatizada] na lista suspensa [!UICONTROL Tipo].

1. (Opcional) Clique no ícone de **[!UICONTROL Baixar]** para baixar a exibição resumida (por exemplo, comparação de tráfego de Controle e Direcionado) conforme detalhado por todas as métricas de sucesso disponíveis.

[!UICONTROL Personalização automatizada] fornece os relatórios a seguir:

* Nível de atividade
* Nível de oferta
* Segmentos automatizados
* Atributos importantes

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
>O ícone de relógio indica que o modelo de algoritmo ainda está sendo criado. O ícone de marca de seleção indica que o algoritmo base foi estabelecido.

## Segmentos automatizados

Clique no ícone [!UICONTROL Segmentos automatizados]. Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

![Ícone Segmentos automatizados](/help/c-reports/assets/icon-automated-sements-ap.png)

Para obter mais informações, consulte [Relatório de segmentos automatizados](/help/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Clique no ícone [!UICONTROL Atributos importantes]. Este relatório mostra como, em atividades diferentes, atributos diferentes são mais (ou menos) importantes para como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

![Ícone de atributos importantes](/help/c-reports/assets/icon-important-attributes-ap.png)

Para obter mais informações, consulte [Relatório de atributos importantes](/help/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Perguntas frequentes

### Por que existem diferenças nos dados entre os relatórios de Nível de Atividade e Nível de Oferta?

**[!UICONTROL Atividade ] Levelreport**: Visitas registradas no relatório de  [!UICONTROL Nível de ] Atividade capturam o número de visitas para a(s) experiência(s) de controle vs. tráfego &quot;direcionado&quot;. O tráfego direcionado inclui uma combinação de tráfego de exploração e tráfego personalizado.

**Relatório** de nível de oferta: As impressões gravadas no relatório  [!UICONTROL Níveis de ] Oferta capturam o número de impressões de cada oferta. Portanto, em uma atividade com mais de um local, o número total de visitas registradas no relatório [!UICONTROL Nível de Oferta] em todos os Grupos de Relatórios é igual ao múltiplo do número de visitas registradas para o Controle ou o tráfego Direcionado no relatório [!UICONTROL Nível de Atividade] é igual ao número total de locais na atividade. As impressões de conteúdo padrão que ocorrem em locais onde o conteúdo padrão era uma opção disponível são registradas no grupo de ofertas &quot;Conteúdo padrão&quot;. As impressões de ofertas que não foram atribuídas a um grupo de relatórios são registradas no grupo de ofertas &quot;Não agrupadas&quot;.

>[!NOTE]

O número de impressões registradas no relatório [!UICONTROL Nível de Oferta] pode não ser um número inteiro exato de visitas registrado no relatório [!UICONTROL Nível de Atividade]. Isso se deve a pequenas discrepâncias que ocorrem na captura do tráfego de dados do relatórios pela Internet (a taxa de discrepância típica é inferior a 5%). Assim, o número de impressões não será um múltiplo exato quando o número de locais disponíveis na atividade for alterado após a atividade ser ativada.
