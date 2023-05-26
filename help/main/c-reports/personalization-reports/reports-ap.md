---
keywords: Direcionamento;relatórios de AP;relatórios de personalização automatizada;relatório de nível de atividade;relatório de nível de oferta;relatório de detalhes da oferta;perguntas frequentes
description: Saiba como interpretar o relatório de resumo do Automated Personalization no Adobe Target. Você pode alternar para os relatórios de Segmentos automatizados e Atributos importantes a partir desse relatório.
title: Como usar os relatórios de resumo do Automated Personalization?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="See what's included in Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: 07062b7df75300bd7558a24da5121df454520e42
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 33%

---

# Relatórios de resumo de Automated Personalization

Relatórios de resumo especializados estão disponíveis para usuários do [!UICONTROL Automated Personalization] atividades no [!DNL Adobe Target].

>[!NOTE]
>
>A [!UICONTROL Personalização automatizada] está disponível como parte da solução [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] como uma licença do [Target Premium](/help/main/c-intro/intro.md#premium).

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada de [!UICONTROL Personalização automatizada] da lista, em seguida, clique na guia **[!UICONTROL Relatórios.]**

   Se você tiver muitas atividades, pode filtrar a lista ao selecionar [!UICONTROL Personalização automatizada] na lista suspensa [!UICONTROL Tipo].

1. (Opcional) Clique no ícone de **[!UICONTROL Baixar]** para baixar a exibição resumida (por exemplo, comparação de tráfego de Controle e Direcionado) conforme detalhado por todas as métricas de sucesso disponíveis.

[!UICONTROL Personalização automatizada] fornece os relatórios a seguir:

* Nível de atividade
* Nível da oferta
* Segmentos automatizados
* Atributos importantes

## Relatório de nível de atividade {#section_6F72FC5C790B4492B3DCECBFFA971337}

O relatório [!UICONTROL Nível de atividade] compara o desempenho agregado de usar um algoritmo de [!UICONTROL Personalização automatizada] para um conteúdo veiculado aleatoriamente (controle).

![Relatório de nível de atividade](/help/main/c-reports/assets/box_plot_ap.png)

As regras padrão da interpretação de resultados do teste A/B ainda são aplicáveis, incluindo incentivo, confiança, tendência, duração e assim por diante. Para obter mais informações sobre a interpretação de resultados, consulte  [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Relatório de nível de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

O relatório [!UICONTROL Nível da oferta] para a experiência Random Forest compara o desempenho de cada algoritmo aplicado à oferta à mesma oferta veiculada aleatoriamente (Controle). Portanto, as ofertas não devem ser comparadas entre si nessa exibição.

Clique no algoritmo da experiência (Random Forest ou controle) para visualizar o [!UICONTROL Nível da oferta] relatório.

![Relatório de nível de oferta no Adobe Target](/help/main/c-reports/assets/ap_OfferLevelRpt.png)

>[!NOTE]
>
>Um ícone de relógio indica que o modelo de algoritmo ainda está sendo criado. Um ícone de marca de verificação indica que o algoritmo de base foi estabelecido.

As ofertas podem ser exibidas em [grupos de relatórios](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md)e esses grupos de relatórios podem ser recolhidos e expandidos. Clique em **[!UICONTROL Controle]** ou **[!UICONTROL Direcionado]** na tabela para exibir informações acumuladas por grupos de relatórios, em vez de por ofertas.

## Segmentos automatizados

Clique em [!UICONTROL Segmentos automatizados] ícone. Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

![Ícone de Segmentos automatizados](/help/main/c-reports/assets/icon-automated-sements-ap.png)

Para obter mais informações, consulte [Relatório de Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Clique em [!UICONTROL Atributos importantes] ícone. Este relatório mostra como, em atividades diferentes, atributos distintos são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

![Ícone de atributos importantes](/help/main/c-reports/assets/icon-important-attributes-ap.png)

Para obter mais informações, consulte [Relatório de atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Perguntas frequentes

### Por que há diferenças nos dados entre os relatórios de Nível de atividade e Nível de oferta?

**[!UICONTROL Nível de atividade] relatório**: visitas registradas no [!UICONTROL Nível de atividade] o relatório captura o número de visitas à(s) experiência(s) de controle vs. tráfego &quot;direcionado&quot;. O tráfego direcionado inclui uma combinação de tráfego de exploração e tráfego personalizado.

**Relatório de nível de oferta**: Impressões gravadas na [!UICONTROL Nível da oferta] Esse relatório captura o número de impressões para cada oferta. Portanto, em uma atividade com mais de um local, o número total de visitas registradas no [!UICONTROL Nível da oferta] relatório em todos os Grupos de relatórios é igual ao múltiplo do número de visitas registradas para tráfego de Controle ou Direcionado no [!UICONTROL Nível de atividade] relatório vezes o número total de locais na atividade. As impressões de conteúdo padrão que ocorrem em locais onde o conteúdo padrão era uma opção disponível são registradas no grupo de ofertas &quot;Conteúdo padrão&quot;. As impressões das ofertas que foram desatribuídas a um grupo de relatórios são registradas no grupo de ofertas &quot;Desagrupado&quot;.

>[!NOTE]
>
>O número de impressões registradas no [!UICONTROL Nível da oferta] O relatório pode não ser um múltiplo inteiro exato do número de visitas registradas na variável [!UICONTROL Nível de atividade] relatório. Isso se deve a pequenas discrepâncias que ocorrem na captura do tráfego de dados de relatórios pela Internet (a taxa de discrepância típica é inferior a 5%). Assim, o número de impressões não será um múltiplo exato quando o número de locais disponíveis na atividade for alterado após a ativação da atividade.
