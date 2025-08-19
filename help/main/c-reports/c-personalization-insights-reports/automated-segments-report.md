---
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, direcionamento automático, direcionamento automático, relatório de direcionamento automático, relatório de direcionamento automático, personalização, insights, segmentos automatizados, perguntas frequentes, perguntas frequentes
description: Saiba como diferentes segmentos definidos pelos modelos de personalização do Adobe [!DNL Target]  respondem às ofertas/experiências na atividade ao exibir o relatório de Segmentos automatizados.
title: O que é o relatório de Segmentos automatizados?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: d21517b7-770b-4618-9899-7ac4948c2a8b
source-git-commit: c1a71d1fb6fa9b5c14e22fa3199358a4594bb4a1
workflow-type: tm+mt
source-wordcount: '2066'
ht-degree: 60%

---

# Relatório de [!UICONTROL Automated Segments]

Informações sobre o relatório [!UICONTROL Automated Segments], um dos dois relatórios especializados disponíveis aos usuários de atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] (AT).

>[!NOTE]
>
>Leve em consideração o seguinte ao usar relatórios de [!UICONTROL Personalization Insights]:
>
>* As atividades de AP e AT estão disponíveis como parte da solução [!DNL Target Premium]. Não estão incluídos com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium].
>
>* Os relatórios [!UICONTROL Personalization Insights] estão disponíveis somente para atividades de AP e AT que usam uma meta de otimização de conversão. As atividades em que a meta de otimização foi alterada para a conversão da receita após a atividade já estar ativa também não são compatíveis.
>
>* [!UICONTROL Personalization Insights] relatórios estão disponíveis somente se [!UICONTROL Primary Goal] estiver selecionado na lista suspensa [!UICONTROL Report Metric].
>
>* Há suporte para [!UICONTROL Personalization Insights] relatórios somente no [ambiente padrão](/help/main/administrating-target/hosts.md).
>
>* Os relatórios [!UICONTROL Personalization Insights] são gerados apenas para atividades que estão no status [!UICONTROL Live] e foram ativadas e receberam tráfego por pelo menos 15 dias.

Visitantes diferentes respondem de forma distinta às ofertas/experiências na atividade de AP/AT. Este relatório mostra como diferentes segmentos automatizados, definidos pelos modelos de personalização do Target, responderam às ofertas/experiências na atividade.

## Acessar o relatório de Segmentos automatizados {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Clique em **[!UICONTROL Activities]** e depois clique na atividade [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) desejada da lista.

   Se você tiver muitas atividades, clique no ícone Filtro ( ![Ícone Filtro](/help/main/assets/icons/Filter.svg) ) para filtrar a lista selecionando opções nas listas suspensas [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] e [!UICONTROL Activity Source].

1. Clique em **[!UICONTROL Reports]**.

   O relatório do [Resumo do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) ou do [Resumo do Direcionamento automático](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) é exibido e fornece informações sobre o desempenho de suas atividades, representado pelo primeiro ícone da tela. Os dois ícones adicionais representam os dois relatórios do [!UICONTROL Personalization Insights]: **[!UICONTROL Automated Segments]** ( ![relatório de Segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) e **[!UICONTROL Important Attributes]** ( ![ícone de Atributos importantes](/help/main/assets/icons/ViewList.svg) ). O Direcionamento automático tem um ícone de gráfico extra para a exibição gráfica do relatório [!UICONTROL Summary].

   >[!IMPORTANT]
   >
   >O relatório [!UICONTROL Automated Segments] somente estará disponível em, no mínimo, 15 dias após você ter ativado a sua atividade. Durante esse período inicial, você não poderá acessar esse relatório ou clicar no ícone [!UICONTROL Automated Segments]. Após 15 dias, supondo que haja tráfego personalizado suficiente em sua atividade, o relatório [!UICONTROL Automated Segments] estará disponível.

1. Após 15 dias da ativação da atividade, você pode clicar no ícone **[!UICONTROL Automated Segments]**.

1. Selecione o intervalo de datas desejado.

   Ao contrário do relatório do [!UICONTROL Summary] (relatórios de desempenho), o [!UICONTROL Personalization Insights], incluindo o [!UICONTROL Automated Segments], está disponível apenas para intervalos de datas fixos: 15 dias, 30 dias e 60 dias. Esses intervalos de datas fixos permitem que [!UICONTROL Personalization Insights] use um intervalo de dados grande o suficiente para reduzir a probabilidade de obter insights de um padrão de curta duração na atividade. As duas decisões que você pode fazer para o intervalo de datas é a &quot;Data final&quot; e a &quot;Duração&quot;. Você notará que a opção &quot;Iniciar&quot; está esmaecida. A data inicial muda automaticamente com base nas seleções de data final e duração.

   Você pode acessar os intervalos de datas fixos disponíveis na lista suspensa [!UICONTROL Preset Date Range].

1. Revise os dados do relatório [!UICONTROL Automated Segments].

1. (Opcional) Clique no ícone **[!UICONTROL Download]** ( ![Ícone de download](/help/main/assets/icons/Download.svg) ) para [baixar o relatório no formato CSV](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) para análise no Excel e em outras ferramentas.

   >[!NOTE]
   >
   >O relatório de interface do usuário dos Insights de personalização contém informações selecionadas. O download do CSV para o relatório de Segmentos automatizados contém detalhes adicionais. O download do relatório de Segmentos automatizados contém Segmentos automatizados adicionais, além dos principais segmentos incluídos na interface do usuário, juntamente com a forma como esses segmentos são executados em relação às ofertas ou experiências.

## Interpretar o relatório de Segmentos automatizados

A tabela a seguir explica como interpretar o relatório e descreve seus elementos:

| Elemento | Detalhes |
|--- |--- |
| Painel lateral esquerdo | O painel lateral esquerdo lista os 20 maiores &quot;segmentos automatizados&quot; identificados pelos modelos de personalização do Target para esta atividade. Um &quot;segmento automatizado&quot; é como um público-alvo, mas é definido pelos modelos de personalização do Target, e não pelo profissional de marketing. Cada segmento automatizado é composto de valores específicos (ou intervalos de valores), de atributos específicos.<br>Segmentos automatizados podem sobrepor. Os segmentos automatizados podem ser definidos por um, dois, três ou quatro atributos. Consulte os exemplos abaixo para obter mais detalhes.<br>Para saber mais sobre os modelos de personalização do Target, consulte [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md). Para saber mais sobre os atributos que os modelos de personalização do Target usam para criar segmentos automatizados, consulte [Coleta de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md). |
| Gráfico central | Os gráficos centrais mostram como o conteúdo da atividade foi executado para o segmento automatizado destacado. Ao clicar em segmentos diferentes no painel esquerdo, os gráficos centrais são atualizados. |
| Gráficos de pizza | Os gráficos de pizza na parte superior do painel central mostram o tamanho do segmento automatizado, bem como o número total de visitas personalizadas na atividade (por exemplo, o tráfego para essa atividade que foi distribuído pelo modelo de personalização. Não inclui o tráfego de controle ou o tráfego distribuído pelo modelo vencedor global). O tamanho do segmento se baseia somente em visitas personalizadas.<br>![Gráfico de pizza](/help/main/c-reports/assets/pie.png) |
| Gráfico de barras de dois eixos | O gráfico de barras de dois eixos inclui informações de visita e conversão por meio da oferta ou experiência para esse segmento automatizado específico. |
| Barra rosa | A barra rosa representa a taxa de conversão e usa o eixo inferior do gráfico. Você pode passar o mouse sobre a barra para obter mais informações |
| Barra azul | A barra azul representa o número de visitas e usa o eixo superior do gráfico. Você pode passar o mouse sobre a barra para obter mais informações. |
| Linha pontilhada cinza | A linha pontilhada cinza representa a taxa de conversão para todas as visitas personalizadas na atividade, em todas as ofertas/experiências e segmentos automatizados. |

**Exemplo de segmento automatizado 1**

Este segmento automatizado é definido com base em apenas um atributo. Os visitantes incluídos neste segmento automatizado viram esta atividade de AP em um dia de semana fora do horário normal de trabalho ou em um final de semana.

![Exemplo de relatório de Segmentos automatizados 1](/help/main/c-reports/assets/automated_segment_example_1.png)

**Exemplo de segmento automatizado 2**

Este segmento automatizado é definido com base em dois atributos. Os visitantes incluídos neste segmento automatizado que viram esta atividade de AP tinham menos de três visualizações de página em sua visita atual e estavam geograficamente localizados na Latitude 42,57 e 47,29 (aproximadamente entre New Hampshire/Oregon e Washington/Maine para uma empresa com sede nos EUA).

![Exemplo de relatório de Segmentos automatizados 2](/help/main/c-reports/assets/automated_segment_example_2.png)

## Perguntas frequentes de Segmentos automáticos {#section_740910A52FA646B4AC9452F98C2F5719}

**Relatórios de Insights de personalização não estão disponíveis ainda para minha atividade. Por que isso ocorre?**

Há vários motivos pelos quais os relatórios [!UICONTROL Personalization Insights] ainda não estão disponíveis para a sua atividade:

* Não se passaram 15 dias desde que você ativou a atividade. Os relatórios de Segmentos automatizados e Atributos importantes não estarão disponíveis até pelo menos 15 dias após o início da atividade. Durante esse período inicial, você não poderá acessar esses relatórios ou clicar nos ícones de Segmentos automatizados e Atributos personalizados do modelo.
* Sua atividade não teve tráfego suficiente durante o intervalo de tempo especificado. Após 15 dias, supondo que haja tráfego personalizado suficiente na atividade para criar modelos de personalização, os relatórios de Segmentos automatizados e Atributos importantes ficarão disponíveis.
* Sua atividade tem uma meta de otimização de receita. Atualmente, o [!UICONTROL Personalization Insights] está disponível apenas para atividades com meta de otimização de conversão. A Adobe adicionará suporte para atividades com meta de otimização de receita em uma versão futura.

**O que é um atributo?**

Um atributo é a informação sobre um visitante ou sua visita específica usada pelos algoritmos de personalização para saber como personalizar o tráfego. Por exemplo, um atributo pode ser o tipo de navegador, a localização, a hora do dia da visita e assim por diante.

Para obter mais informações sobre quais atributos o [!DNL Target] usa em seus modelos de personalização, consulte [Coleta de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md). Para obter mais informações sobre como fazer upload de novos atributos no Target para usar nos modelos de personalização do Target, consulte [Métodos para colocar os dados no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}.

**O que é um segmento automatizado?**

Um &quot;segmento automatizado&quot; é como um público-alvo, mas é definido pelos modelos de personalização do Target, e não pelo profissional de marketing.

Um segmento automatizado é composto de valores específicos (ou intervalos de valores), de atributos específicos. Consulte a Etapa 5 acima para obter exemplos de segmentos automatizados. Segmentos podem se sobrepor.

Para saber mais sobre o algoritmo de personalização random forest, que é a base para os modelos de personalização do Target, consulte [Algoritmo Random Forest](/help/main/c-activities/t-automated-personalization/algo-random-forest.md).

**O que decide a ordem dos segmentos automatizados?**

Uma pontuação é calculada para cada segmento, com base no seu tamanho e desempenho diferenciado no conteúdo da sua atividade. A combinação dessas informações determina a ordem dos segmentos automatizados, de modo que os segmentos maiores, com maiores diferenças na forma como responderam ao conteúdo distinto, aparecerão mais perto do topo da lista de segmentos.

**Por que apenas algumas das minhas ofertas/experiências são exibidas no relatório dos Segmentos automatizados?**

As atividades de AP e de AT criam um modelo por oferta (no caso de AP) e um modelo por experiência (no caso de AT). Essas atividades começam distribuindo o tráfego personalizado e criam o seu [!UICONTROL Personalization Insights] com apenas dois modelos compilados. Se não visualizar todas as suas ofertas/experiências no [!UICONTROL Personalization Insights], é provável que você não tenha modelos criados para essas ofertas/experiências específicas. Você pode verificar o relatório de [!UICONTROL Summary] da sua atividade e ver se há um ícone de relógio ao lado dessa oferta/experiência. Esse ícone indica que os modelos ainda não foram criados para essa oferta/experiência.

**Por que algumas ofertas/experiências com uma taxa de conversão mais baixa recebem uma quantidade maior de tráfego em comparação a outras ofertas/experiências para um determinado segmento automatizado?**

Há vários motivos possíveis pelos quais você pode ver mais visitas para uma oferta ou experiência de conversão mais baixa em um segmento automatizado, incluindo:

* Um pequeno número de visualizações para algumas ou todas as ofertas/experiências de um determinado segmento automatizado.
* Atividades com volume menor, nas quais determinadas ofertas/experiências não têm modelos criados ou os modelos foram criados antes para algumas ofertas/experiências do que para outras.
* Regras de direcionamento em uma oferta específica que limitam quais visitantes podem ver quais ofertas/experiências.

**As informações nos relatórios [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes] são as mesmas do download do CSV?**

Não, o relatório da interface do usuário contém informações selecionadas. O download do CSV contém detalhes adicionais. O download do relatório de Insights do segmento automatizado contém Segmentos automatizados adicionais, além dos principais segmentos incluídos na interface do usuário, juntamente com a forma como esses segmentos são executados em relação às ofertas ou experiências. O relatório de Atributos importantes inclui os 100 principais atributos de visitantes e sua importância relativa, enquanto a interface do usuário inclui apenas os 10 principais atributos de visitantes.

**Posso ver [!UICONTROL Personalization Insights] para um intervalo de datas personalizado?**

Os relatórios do Personalization Insights ([!UICONTROL Automated Segments] e [!UICONTROL Important Attributes]) estão disponíveis apenas para intervalos de datas fixos: 15 dias, 30 dias e 60 dias. Esses intervalos de datas fixos permitem que [!UICONTROL Personalization Insights] use um intervalo de dados grande o suficiente para reduzir a probabilidade de obter insights de um padrão de curta duração na atividade. Você pode selecionar essas durações para qualquer data final (onde esses dados são suficientes na atividade para atender a duração).

**Como [!UICONTROL Personalization Insights] é criado?**

O [!UICONTROL Personalization Insights] foi criado usando uma técnica de patente pendente da Adobe chamada MAGIX (Model Agnostic Globally Interpretable Explanations). Você pode saber mais sobre o MAGIX no paper publicado pela equipe de pesquisa da Adobe no [site do arXiv.org](https://arxiv.org/abs/1706.07160).

**Por que o total de dados de tráfego dos visitantes no relatório [!UICONTROL Automated Segments] não corresponde ao meu relatório de Resumo/Desempenho de AP ou AT?**

Os relatórios [!UICONTROL Personalization Insights] incluem somente visitantes que viram uma parte do conteúdo selecionado por modelos de personalização do Target (isto é, não considera o tráfego de controle ou o tráfego distribuído pelo modelo vencedor global). Esse tipo de tráfego é chamado de tráfego &quot;personalizado&quot;. O relatório de resumo/desempenho em AP/AT inclui controle versus tráfego &quot;direcionado&quot;. O tráfego direcionado inclui o tráfego personalizado, bem como o distribuído usando o modelo vencedor global e algum tráfego distribuído aleatoriamente para continuar o aprendizado.

**Os segmentos automatizados são mutuamente exclusivos?**

Não, há uma sobreposição entre os segmentos automatizados.

**O [!UICONTROL Personalization Insights] está disponível para metas de modelagem baseadas em receita/meta principal?**

No momento, o [!UICONTROL Personalization Insights] está disponível apenas para atividades com meta de otimização de conversão. A Adobe adicionará suporte para atividades com meta de otimização de receita em uma versão futura.

**Quais são as diferentes formas de usar as informações nos Insights de personalização?**

* Descubra novos públicos-alvo para o target: se você vir um segmento automatizado específico com bom desempenho, poderá considerar a criação de um público-alvo para reutilizar esse segmento em outros relatórios.
* Teste a hipótese do tipo de visitante que responde a cada uma de suas experiências.
* Obtenha informações sobre o conteúdo que funcionou para que tipo de visitantes: quais ofertas foram responsáveis pelo aumento de visitantes.
* Identifique o conteúdo com baixo desempenho.
* Entenda quais atributos foram mais importantes para a forma como o modelo aprendeu.
* Veja quais atributos são usados nos modelos de personalização e qual a importância deles.
* Identifique as oportunidades para os pontos de dados adicionais que você pode passar para o Target para informar ainda mais a sua personalização.

**Há alguma lógica na ordem de exibição dos atributos em um cartão de segmento?**

Não, a ordem dos cartões é baseada apenas em uma classificação descrita acima. A ordem dos atributos em um cartão não se baseia em nenhuma lógica.
