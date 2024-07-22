---
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, direcionamento automático, direcionamento automático, relatório do direcionamento automático, relatório de direcionamento automático, personalização, insights, perguntas frequentes, perguntas frequentes, atributos importantes
description: Saiba como usar o relatório [!UICONTROL Important Attributes] que mostra os principais atributos que influenciam o modelo de personalização e sua importância relativa.
title: O que é o Relatório de atributos importantes?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
source-git-commit: fe1e97710e7692ba7724103853ed7438c3f361b1
workflow-type: tm+mt
source-wordcount: '1790'
ht-degree: 56%

---

# Relatório de atributos importantes

Informações sobre o relatório [!UICONTROL Important Attributes], um dos dois relatórios especializados disponíveis aos usuários de atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] (AT).

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

Em atividades diferentes, atributos distintos são mais ou menos importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

## Acessar o relatório [!UICONTROL Important Attributes] {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Clique em **[!UICONTROL Activities]** e depois clique na atividade [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) desejada da lista.

   Se você tem muitas atividades, você pode filtrar a lista selecionando opções nas listas suspensas [!UICONTROL Type], [!UICONTROL Status], [!UICONTROL Reporting Source], [!UICONTROL Experience Composer], [!UICONTROL Metrics Type] e [!UICONTROL Activity Source].

1. Clique em **[!UICONTROL Reports]**.

   O relatório do [Resumo do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) ou do [Resumo do Direcionamento automático](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) é exibido e fornece informações sobre o desempenho de suas atividades, representado pelo primeiro ícone da tela. Os dois ícones adicionais representam os dois relatórios do [!UICONTROL Personalization Insights]: [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes].

   ![Relatório de resumo da atividade do Automated Personalization](/help/main/c-reports/assets/summary-report-ap.png)

   Observe que [!UICONTROL Auto-Target] tem um ícone de gráfico adicional para a exibição gráfica do relatório [!UICONTROL Summary].

   ![Relatório de resumo da atividade de Direcionamento automático](/help/main/c-reports/assets/personalization_insights.png)

   >[!IMPORTANT]
   >
   >O relatório [!UICONTROL Important Attributes] somente estará disponível em, no mínimo, 15 dias após você ter ativado a sua atividade. Durante esse período inicial, você não poderá acessar esse relatório ou clicar no ícone [!UICONTROL Important Attributes]. Após 15 dias, supondo que haja tráfego personalizado suficiente em sua atividade, o relatório [!UICONTROL Important Attributes] ficará disponível.

1. Após 15 dias da ativação da atividade, clique no ícone **[!UICONTROL Important Attributes]**.

   ![Ícone de Atributos importantes em um relatório do Adobe Target](/help/main/c-reports/assets/model_attribute_ranking.png)

1. Selecione o intervalo de datas desejado.

   Ao contrário do relatório do [!UICONTROL Summary] (relatórios de desempenho), o [!UICONTROL Personalization Insights], incluindo o [!UICONTROL Important Attributes], está disponível apenas para intervalos de datas fixos: 15 dias, 30 dias e 60 dias.

   Esses intervalos de datas fixos permitem que [!UICONTROL Personalization Insights] use um intervalo de dados grande o suficiente para reduzir a probabilidade de obter insights de um padrão de curta duração na atividade. As duas decisões que você pode fazer para o intervalo de datas é a &quot;Data final&quot; e a &quot;Duração&quot;. Você perceberá que a opção &quot;Iniciar&quot; está em cinza. A data inicial muda automaticamente com base nas seleções de data final e duração.

   ![Calendário em um relatório do Adobe Target](/help/main/c-reports/assets/personalization_insights_calendar_1.png)

   Você pode acessar os intervalos de datas fixos disponíveis na lista suspensa [!UICONTROL Choose Duration].

   ![Escolha a lista suspensa Duração em um relatório](/help/main/c-reports/assets/personalization_insights_calendar_2.png)

1. Revise os dados do relatório [!UICONTROL Important Attributes].

   ![Relatório de Atributos Importantes no Adobe Target](/help/main/c-reports/assets/model_attribute_ranking_report.png)

1. (Opcional) [Baixe o relatório no formato CSV](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) para análise no Excel e em outras ferramentas.

   >[!NOTE]
   >
   >O relatório de interface do usuário dos Insights de personalização contém informações selecionadas. O download do CSV para o relatório de Atributos importantes contém detalhes adicionais. O download do relatório de Atributos importantes inclui a lista completa dos 100 principais atributos, enquanto o relatório da interface do usuário inclui apenas os 10 principais. Se estiver procurando por um atributo específico que não esteja no relatório, isso não significa que ele não tenha influenciado a atividade, mas simplesmente que não entrou na lista dos 100 principais atributos.

## Interpretar o relatório de Atributos importantes

A tabela a seguir explica como interpretar o relatório e descreve seus elementos:

| Elemento | Detalhes |
|--- |--- |
| Gráfico de barras | O gráfico de barras multicolorido na parte superior da tela permite visualizar essas pontuações de importância relativa e mapeia a cor do ponto ao lado de cada atributo respectivo na tabela. Você também pode passar o mouse sobre uma cor específica no gráfico de barras para ver o atributo que ela representa.  As pontuações de importância nos 100 principais atributos somam 100%. Para obter mais informações sobre como adicionar mais atributos que podem ser usados pelos modelos de personalização do Target, consulte [Carregando dados para os algoritmos de Personalization do Target](/help/main/c-activities/t-automated-personalization/uploading-data-for-the-target-personalization-algorithms.md). |
| Gráfico de Classificação de atributo do modelo | A Classificação de atributo do modelo inclui os 10 principais atributos que foram mais importantes para a forma como o modelo de personalização do Target decidiu qual conteúdo mostrar para cada visitante. Em relação aos 100 principais atributos, a pontuação de importância mostra o quão importante um atributo específico foi para os modelos de personalização do Target nessa atividade. |

## Perguntas frequentes de atributos importantes {#section_740910A52FA646B4AC9452F98C2F5719}

Consulte as perguntas frequentes a seguir para obter respostas sobre o uso do relatório [!UICONTROL Important Attributes].

### Os relatórios do Personalization Insights ainda não estão disponíveis para minha atividade. Por que isso ocorre?

Há vários motivos pelos quais os relatórios do [!UICONTROL Personalization Insights] podem ainda não estar disponíveis para a sua atividade:

* O prazo de 15 dias desde que a atividade foi ativada não decorreu. Os relatórios de Segmentos automatizados e Atributos importantes não estarão disponíveis até pelo menos 15 dias após o início da atividade. Durante esse período inicial, você não poderá acessar esses relatórios ou clicar nos ícones de Segmentos automatizados e Atributos personalizados do modelo.
* Sua atividade não teve tráfego suficiente durante o intervalo de tempo especificado. Após 15 dias, supondo que haja [tráfego personalizado suficiente](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) na atividade para criar modelos de personalização, os relatórios de Segmentos automatizados e Atributos importantes ficarão disponíveis.
* Sua atividade tem uma meta de otimização de receita. No momento, o [!UICONTROL Personalization Insights] está disponível apenas para atividades com meta de otimização de conversão. O suporte será adicionado para atividades com meta de otimização de receita em uma versão futura.

### O que é um atributo?

Um atributo é a informação sobre um visitante ou sua visita específica usada pelos algoritmos de personalização para saber como personalizar o tráfego. Por exemplo, um atributo pode ser o tipo de navegador, a localização, a hora do dia da visita e assim por diante.

Para obter mais informações sobre quais atributos o [!DNL Target] usa em seus modelos de personalização, consulte [Coleta de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md). Para obter mais informações sobre como carregar novos atributos no Target para usar nos modelos de personalização do Target, consulte [Métodos para obter dados no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}.

### Há um ou mais atributos que não desejo que o modelo use para treinamento. Posso remover esses atributos do modelo de treinamento? {#models-api}

O [!UICONTROL Models API], também chamado de API de Inclui na lista de bloqueios, permite que os usuários visualizem e gerenciem a lista de atributos (também chamados de recursos) usados em modelos de aprendizado de máquina de atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] (AT). Se você quiser excluir um ou mais atributos de serem usados pelos modelos para atividades de AP ou AT, poderá usar a API de modelos para adicionar esses atributos ao &quot;incluo na lista de bloqueios&quot;.

Para obter informações detalhadas, consulte [Visão geral da API de modelos](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} no *Guia do Desenvolvedor do Adobe Target*. Para usar a API para bloquear atributos, consulte [API de modelos](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html){target=_blank}.

### As informações nos relatórios [!UICONTROL Automated Segments] e [!UICONTROL Important Attributes] são as mesmas do download do CSV?

Não, o relatório da interface do usuário contém informações selecionadas. O download do CSV contém detalhes adicionais. O download do relatório de Insights do segmento automatizado contém Segmentos automatizados adicionais, além dos principais segmentos incluídos na interface do usuário, juntamente com a forma como esses segmentos são executados em relação às ofertas ou experiências. O relatório de Atributos importantes inclui os 100 principais atributos de visitantes e sua importância relativa, enquanto a interface do usuário inclui apenas os 10 principais atributos de visitantes.

### Posso ver o Personalization Insights para um intervalo de datas personalizado?

Os relatórios do Personalization Insights ([!UICONTROL Automated Segments] e [!UICONTROL Important Attributes]) estão disponíveis apenas para intervalos de datas fixos: 15 dias, 30 dias, 45 dias, 60 dias e 90 dias. Esses intervalos de datas fixos permitem que [!UICONTROL Personalization Insights] use um intervalo de dados grande o suficiente para reduzir a probabilidade de obter insights de um padrão de curta duração na atividade. Você pode selecionar essas durações para qualquer data final (onde esses dados são suficientes na atividade para atender a duração).

### Como o [!UICONTROL Personalization Insights] é criado?

[!UICONTROL Personalization Insights] é criado usando uma técnica de Adobe com patente pendente chamada MAGIX (Model Agnostic Globally Interpretable Explanations). Você pode saber mais sobre o MAGIX no paper publicado pela equipe de pesquisa do Adobe no [site arXiv.org](https://arxiv.org/abs/1706.07160).

### [!UICONTROL Personalization Insights] está disponível para metas de modelagem baseadas em receita/meta principal?

No momento, o [!UICONTROL Personalization Insights] está disponível apenas para atividades com meta de otimização de conversão. O suporte será adicionado para atividades com meta de otimização de receita em uma versão futura.

### Qual é a pontuação de importância do atributo no relatório de Atributos importantes?

A pontuação de importância na parte do relatório &quot;Classificação de importância do atributo&quot; fornece informações sobre quais variáveis usadas pelo algoritmo para aprender eram mais importantes ao determinar como dividir todos os visitantes nos segmentos identificados. Ele atribuiu uma pontuação percentual aos 100 principais atributos usados pelo modelo.

### Por que algumas ofertas/experiências com uma taxa de conversão mais baixa recebem uma quantidade maior de tráfego em comparação a outras ofertas/experiências para um determinado segmento automatizado?

Há vários motivos possíveis pelos quais você pode ver mais visitas para uma oferta/experiência de conversão mais baixa em um segmento automatizado, incluindo:

* Um pequeno número de visualizações para algumas ou todas as ofertas/experiências de um determinado segmento automatizado.
* Atividades de volume inferior nas quais determinadas ofertas ou experiências não têm modelos criados.
* Atividades de volume inferior nas quais foram criados modelos para algumas ofertas/experiências antes do que para outras. Por exemplo, suponha que um modelo adicional foi criado no dia 22 e você está analisando os dados dos dias 10 a 24.
* Regras de direcionamento em uma oferta específica que limitam quais visitantes podem ver quais ofertas/experiências.
* Não há intervalos de confiança no relatório de insight. No entanto, se os índices de conversão estiverem próximos o suficiente, o modelo poderá fornecer tráfego para que o número seja maior em um ponto, mas não &quot;estatisticamente diferente&quot; do outro.

Pode ser útil saber como o modelo fornece o tráfego. Cada indivíduo é servido com base no seu perfil total. No entanto, os relatórios de Insights generalizam esse comportamento para facilitar sua interpretação por um humano. Como resultado, os segmentos não são mutuamente exclusivos. Isso pode fazer com que segmentos individuais exibam esse tipo de comportamento, pois uma mesma pessoa pode aparecer em vários segmentos.

### Quais são as diferentes maneiras de aproveitar as informações no Personalization Insights?

* Descubra novos públicos-alvo para direcionar: se visualizar um segmento automatizado específico com um desempenho particularmente bom, considere criar um público-alvo para que seja possível reutilizá-lo em outros relatórios.
* Teste suas hipóteses de que tipo de visitantes responderá a quais experiências.
* Obtenha informações sobre o conteúdo que funcionou para que tipo de visitantes: quais ofertas foram responsáveis pelo aumento de visitantes.
* Identifique o conteúdo com baixo desempenho.
* Entenda quais atributos foram mais importantes para a forma como o modelo aprendeu.
* Veja quais atributos são usados nos modelos de personalização e qual a importância deles.
* Identifique as oportunidades para os pontos de dados adicionais que você pode passar para o Target para informar ainda mais a sua personalização.

## Problemas conhecidos

O problema a seguir está sendo investigado pela equipe de engenharia [!DNL Target].

* Os nomes de segmento [!DNL Adobe Experience Platform] não são exibidos no relatório [!UICONTROL Important Attributes] para atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Auto-Target] (AT). (TOP-3813)
