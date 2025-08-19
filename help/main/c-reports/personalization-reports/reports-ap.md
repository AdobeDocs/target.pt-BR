---
keywords: Direcionamento;relatórios de AP;relatórios de personalização automatizada;relatório de nível de atividade;relatório de nível de oferta;relatório de detalhes da oferta;perguntas frequentes
description: Saiba como interpretar o relatório de resumo do Automated Personalization no Adobe Target. Você pode alternar para os relatórios de Segmentos automatizados e Atributos importantes a partir desse relatório.
title: Como usar os relatórios de resumo do Automated Personalization?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: 2708eba4-72d5-4e6b-b01b-d27de03463b2
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '641'
ht-degree: 11%

---

# Relatórios de resumo de Automated Personalization

Relatórios de resumo especializados estão disponíveis para usuários de atividades de [!UICONTROL Automated Personalization] em [!DNL Adobe Target].

>[!NOTE]
>
>[!UICONTROL Automated Personalization] está disponível como parte da solução [!DNL Target Premium]. Ela não está incluída no [!DNL Target Standard] sem uma [licença do Target Premium](/help/main/c-intro/intro.md#premium).

1. Clique em **[!UICONTROL Activities]**, clique na atividade [!UICONTROL Automated Personalization] desejada da lista, em seguida, clique na guia **[!UICONTROL Reports]**.

   Se você tiver muitas atividades, clique no ícone Filtro ( ![Ícone Filtro](/help/main/assets/icons/Filter.svg) ) para filtrar a lista selecionando opções nas listas suspensas [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] e [!UICONTROL Activity Source].

1. (Opcional) Clique no ícone **[!UICONTROL Download]** ( ![Ícone de download](/help/main/assets/icons/Download.svg) ) para baixar a exibição de resumo (por exemplo, comparação de Controle e Tráfego direcionado) conforme detalhado por todas as métricas de sucesso disponíveis.

[!UICONTROL Automated Personalization] fornece os seguintes relatórios:

* Nível de atividade
* Nível da oferta
* Segmentos automatizados
* Atributos importantes

## Relatório de nível de atividade {#section_6F72FC5C790B4492B3DCECBFFA971337}

O relatório [!UICONTROL Activity Level] compara o desempenho agregado do uso de um algoritmo [!UICONTROL Automated Personalization] com o conteúdo disponibilizado aleatoriamente (controle).

As regras padrão da interpretação de resultados do teste A/B ainda são aplicáveis, incluindo incentivo, confiança, tendência, duração e assim por diante. Para obter mais informações sobre como interpretar resultados, consulte [Cálculos estatísticos em testes A/Bn](/help/main/c-reports/statistical-methodology/statistical-calculations.md).

## Relatório de nível de oferta {#section_CAA6409879E349C6906E2BE8156D87A1}

O relatório [!UICONTROL Offer Level] da experiência do Random Forest compara o desempenho de cada oferta aplicada por algoritmo à mesma oferta disponibilizada aleatoriamente (Controle). Portanto, as ofertas não devem ser comparadas nesta visualização.

Clique no algoritmo da experiência (Floresta Aleatória ou controle) para exibir o relatório [!UICONTROL Offer Level].

>[!NOTE]
>
>Um ícone de relógio indica que o modelo de algoritmo ainda está sendo criado. Um ícone de marca de verificação indica que o algoritmo de base foi estabelecido.

As ofertas podem ser exibidas em [grupos de relatórios](/help/main/c-activities/t-automated-personalization/offer-reporting-groups-in-automated-personalization.md), e esses grupos de relatórios podem ser recolhidos e expandidos. Clique em **[!UICONTROL Control]** ou **[!UICONTROL Targeted]** na tabela para exibir informações acumuladas por grupos de relatórios, em vez de por ofertas.

## Segmentos automatizados

Clique no ícone [!UICONTROL Automated Segments]. Este relatório mostra como visitantes diferentes respondem de forma diferente às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

Para obter mais informações, consulte [Relatório de Segmentos automatizados](/help/main/c-reports/c-personalization-insights-reports/automated-segments-report.md).

## Atributos importantes

Clique no ícone [!UICONTROL Important Attributes]. Este relatório mostra como, em atividades diferentes, atributos distintos são mais (ou menos) importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

Para obter mais informações, consulte [Relatório de atributos importantes](/help/main/c-reports/c-personalization-insights-reports/important-attributes-report.md).

## Perguntas frequentes

### Por que há diferenças nos dados entre os relatórios de Nível de atividade e Nível de oferta?

**[!UICONTROL Activity Level]relatório**: as visitas registradas no relatório [!UICONTROL Activity Level] capturam o número de visitas à(s) experiência(s) de controle vs. tráfego &quot;direcionado&quot;. O tráfego direcionado inclui uma combinação de tráfego de exploração e tráfego personalizado.

**Relatório de nível de oferta**: as impressões registradas no relatório [!UICONTROL Offer Level] capturam o número de impressões para cada oferta. Portanto, em uma atividade com mais de um local, o número total de visitas registradas no relatório [!UICONTROL Offer Level] em todos os Grupos de Relatórios é igual ao múltiplo do número de visitas registradas para tráfego de Controle ou Direcionado no relatório [!UICONTROL Activity Level] vezes o número total de locais na atividade. As impressões de conteúdo padrão que ocorrem em locais onde o conteúdo padrão era uma opção disponível são registradas no grupo de ofertas &quot;Conteúdo padrão&quot;. As impressões das ofertas que foram desatribuídas a um grupo de relatórios são registradas no grupo de ofertas &quot;Desagrupado&quot;.

>[!NOTE]
>
>O número de impressões registradas no relatório [!UICONTROL Offer Level] pode não ser um múltiplo inteiro exato do número de visitas registradas no relatório [!UICONTROL Activity Level]. Isso se deve a pequenas discrepâncias que ocorrem na captura do tráfego de dados de relatórios pela Internet (a taxa de discrepância típica é inferior a 5%). Assim, o número de impressões não será um múltiplo exato quando o número de locais disponíveis na atividade for alterado após a ativação da atividade.
