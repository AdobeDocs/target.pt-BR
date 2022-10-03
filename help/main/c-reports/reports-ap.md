---
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, relatório de nível de atividade, relatório de nível de oferta, relatório de detalhes da oferta, perguntas frequentes
description: Saiba como interpretar o relatório de Resumo do Automated Personalization no Adobe Target. Você pode alternar para os relatórios de Segmentos automatizados e Atributos importantes desse relatório.
title: Como uso os relatórios de resumo do Automated Personalization?
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 493ecd762b5228d33377ac8263b90a0f9c73127e
workflow-type: tm+mt
source-wordcount: '673'
ht-degree: 40%

---

# ![PREMIUM](/help/main/assets/premium.png) Relatórios de resumo da personalização automatizada

Relatórios de resumo especializados estão disponíveis para usuários de [!UICONTROL Automated Personalization] atividades em [!DNL Adobe Target].

>[!NOTE]
>
>A [!UICONTROL Personalização automatizada] está disponível como parte da solução [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] como uma licença do [Target Premium](/help/main/c-intro/intro.md#premium).

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada de [!UICONTROL Personalização automatizada] da lista, em seguida, clique na guia **[!UICONTROL Relatórios.]**

   Se você tiver muitas atividades, pode filtrar a lista ao selecionar [!UICONTROL Personalização automatizada] na lista suspensa [!UICONTROL Tipo].

1. (Opcional) Clique no ícone de **[!UICONTROL Baixar]** para baixar a exibição resumida (por exemplo, comparação de tráfego de Controle e Direcionado) conforme detalhado por todas as métricas de sucesso disponíveis.

[!UICONTROL Personalização automatizada] fornece os relatórios a seguir:

* Nível da atividade
* Nível da oferta
* Segmentos automatizados
* Atributos importantes

## Relatório de nível de atividade {#section_6F72FC5C790B4492B3DCECBFFA971337}

O relatório [!UICONTROL Nível de atividade] compara o desempenho agregado de usar um algoritmo de [!UICONTROL Personalização automatizada] para um conteúdo veiculado aleatoriamente (controle).

![Relatório de nível de atividade](/help/main/c-reports/assets/box_plot_ap.png)

As regras padrão da interpretação de resultados do teste A/B ainda são aplicáveis, incluindo incentivo, confiança, tendência, duração e assim por diante. Para obter mais informações sobre a interpretação de resultados, consulte  [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Relatório de nível de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

O relatório [!UICONTROL Nível da oferta] para a experiência Random Forest compara o desempenho de cada algoritmo aplicado à oferta à mesma oferta veiculada aleatoriamente (Controle). Portanto, as ofertas não devem ser comparadas entre si nessa exibição.

Clique no algoritmo de experiência (Random Forest ou controle) para visualizar o [!UICONTROL Nível da oferta] relatório.

![](assets/ap_OfferLevelRpt.png)

As ofertas podem ser mostradas em grupos de relatórios, e esses grupos de relatórios podem ser recolhidos e expandidos. Selecione [!UICONTROL Grupo de relatórios] na lista suspensa para exibir as informações com roll-up, em vez das ofertas.

>[!NOTE]
>
>O ícone de relógio indica que o modelo de algoritmo ainda está sendo criado. O ícone de marca de verificação indica que o algoritmo de base foi estabelecido.

## Segmentos automatizados

Clique no botão [!UICONTROL Segmentos automatizados] ícone . Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

![Ícone de segmentos automatizados](/help/main/c-reports/assets/icon-automated-sements-ap.png)

Para obter mais informações, consulte [Relatório de Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Clique no botão [!UICONTROL Atributos importantes] ícone . Este relatório mostra como, em atividades diferentes, atributos diferentes são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

![Ícone de atributos importantes](/help/main/c-reports/assets/icon-important-attributes-ap.png)

Para obter mais informações, consulte [Relatório de atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Perguntas frequentes

### Por que existem diferenças nos dados entre os relatórios Nível de atividade e Nível de oferta?

**[!UICONTROL Nível da atividade] relatório**: Visitas registradas na [!UICONTROL Nível da atividade] relatório captura o número de visitas à(s) experiência(s) de controle vs. tráfego &quot;direcionado&quot;. O tráfego direcionado inclui uma combinação de tráfego de exploração e tráfego personalizado.

**Relatório de nível de oferta**: Impressões registradas na [!UICONTROL Nível da oferta] relatório captura o número de impressões de cada oferta. Portanto, em uma atividade com mais de um local, o número total de visitas registradas na [!UICONTROL Nível da oferta] em todos os Grupos de relatórios é igual ao múltiplo do número de visitas registradas para o tráfego de Controle ou Direcionado no [!UICONTROL Nível da atividade] relatório vezes o número total de locais na atividade. As impressões do conteúdo padrão que ocorrem em locais onde o conteúdo padrão era uma opção disponível são registradas no grupo de ofertas &quot;Conteúdo padrão&quot;. As impressões de ofertas que não foram atribuídas a um grupo de relatórios são registradas no grupo de ofertas &quot;Não agrupadas&quot;.

>[!NOTE]
>
>O número de impressões registradas na [!UICONTROL Nível da oferta] pode não ser um número inteiro exato múltiplo do número de visitas registradas na variável [!UICONTROL Nível da atividade] relatório. Isso se deve a pequenas discrepâncias que ocorrem na captura do tráfego de dados de relatórios pela Internet (a taxa de discrepância típica é inferior a 5%). Assim, o número de impressões não será um múltiplo exato quando o número de locais disponíveis na atividade for alterado após a atividade ser ativada.
