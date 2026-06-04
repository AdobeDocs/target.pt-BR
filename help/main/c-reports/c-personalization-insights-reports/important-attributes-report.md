---
keywords: Direcionamento, relatórios de AP, relatórios de personalização automatizada, direcionamento automático, direcionamento automático, relatório do direcionamento automático, relatório de direcionamento automático, personalização, insights, perguntas frequentes, perguntas frequentes, atributos importantes
description: Saiba como usar o relatório de [!UICONTROL Atributos importantes] que mostra os atributos principais que influenciam o modelo de personalização e sua importância relativa.
title: O que é o Relatório de atributos importantes?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Reports
exl-id: c1069ca7-e221-4865-a82e-6cff5b4c0055
TQID: https://experienceleague.adobe.com/4G8mYap2O5RW5wr9YvXEaHm2k-oNQVVCHyKv4ltaNHo
product_v2: id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2: id: adee20bd-51f4-461d-b9db-d215f8756eebid: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: bce87dde-a4ab-44c9-8a18-ad66e4ddb377id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1id: d3cdead0-685a-4489-9250-4bb709942f66id: e0eb8757-182f-49f3-94a4-1587d16f5094id: e1e0219c-f879-479f-8427-888ed2a6e9c2id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1937
ht-degree: 61%

---

# Relatório de atributos importantes

Informações sobre o relatório de [!UICONTROL Atributos importantes], um dos dois relatórios especializados disponíveis aos usuários de atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] (AT).

>[!NOTE]
>
>Considere o seguinte ao usar os [!UICONTROL relatórios do Personalization Insights]:
>
>* As atividades de AP e AT estão disponíveis como parte da solução [!DNL Target Premium]. Não estão incluídos com o [!DNL Target Standard] sem uma licença do [!DNL Target Premium].
>
>* Os relatórios do [!UICONTROL Personalization Insights] estão disponíveis apenas para atividades de AP e AT que usam uma meta de otimização de conversão. As atividades em que a meta de otimização foi alterada para a conversão da receita após a atividade já estar ativa também não são compatíveis.
>
>* Os relatórios do [!UICONTROL Personalization Insights] só estarão disponíveis se a [!UICONTROL Meta primária] for selecionada na lista suspensa [!UICONTROL Métrica de relatório].
>
>* Há suporte para os relatórios do [!UICONTROL Personalization Insights] somente no [ambiente padrão](/help/main/administrating-target/hosts.md).
>
>* Os relatórios do [!UICONTROL Personalization Insights] são gerados apenas para atividades que estão no status [!UICONTROL Live] e foram ativadas e receberam tráfego por pelo menos 15 dias.

Em atividades diferentes, atributos distintos são mais ou menos importantes para a forma como o modelo decide personalizar. Este relatório mostra os principais atributos que influenciaram o modelo e sua importância relativa.

## Acessar o relatório de [!UICONTROL Atributos importantes] {#section_8E8F997AAAF44A1B9EE06EB6FB652801}

1. Clique em **[!UICONTROL Atividades]** e clique na atividade desejada do [Automated Personalization](/help/main/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9) ou do [Direcionamento automático](/help/main/c-activities/auto-target/auto-target-to-optimize.md) da lista.

   Se você tiver muitas atividades, clique no ícone Filtro ( ![Ícone Filtro](/help/main/assets/icons/Filter.svg) ) para filtrar a lista selecionando opções nas listas suspensas [!UICONTROL Tipo], [!UICONTROL Status], [!UICONTROL Source de Relatórios], [!UICONTROL Experience Composer], [!UICONTROL Tipo de Métricas] e [!UICONTROL Source de Atividades].

1. Clique em **[!UICONTROL Relatórios]**.

   O relatório do [Resumo do Automated Personalization](/help/main/c-reports/personalization-reports/reports-ap.md) ou do [Resumo do Direcionamento automático](/help/main/c-reports/personalization-reports/auto-target-summary-report.md) é exibido e fornece informações sobre o desempenho de suas atividades, representado pelo primeiro ícone da tela. Os dois ícones adicionais representam os dois relatórios do [!UICONTROL Personalization Insights]: **[!UICONTROL Segmentos automatizados]** ( ![relatório de Segmentos automatizados](/help/main/assets/icons/AutomatedSegment.svg) ) e **[!UICONTROL Atributos importantes]** ( ![ícone de Atributos importantes](/help/main/assets/icons/ViewList.svg) ).


   Observe que [!UICONTROL Direcionamento automático] tem um ícone de gráfico adicional para a exibição gráfica do relatório de [!UICONTROL Resumo].

   >[!IMPORTANT]
   >
   >O relatório de [!UICONTROL Atributos importantes] somente estará disponível em, no mínimo, 15 dias após você ter ativado a sua atividade. Durante esse período inicial, você não poderá acessar esse relatório ou clicar no ícone de [!UICONTROL Atributos importantes]. Após 15 dias, supondo que haja tráfego personalizado suficiente em sua atividade, o relatório [!UICONTROL Atributos importantes] ficará disponível.

1. Após 15 dias da ativação da atividade, clique no ícone de **[!UICONTROL Atributos importantes]** ( ![Ícone de atributos importantes](/help/main/assets/icons/ViewList.svg) ).

1. Selecione o intervalo de datas desejado.

   Ao contrário do relatório de [!UICONTROL Resumo] (relatórios de desempenho), o [!UICONTROL Personalization Insights], incluindo os [!UICONTROL Atributos importantes], está disponível apenas para intervalos de datas fixos: 15 dias, 30 dias e 60 dias.

   Esses intervalos de datas fixos permitem que os [!UICONTROL Insights de personalização] usem um intervalo de dados grande o suficiente para reduzir a probabilidade de obter insights de um padrão de curta duração na atividade. As duas decisões que você pode fazer para o intervalo de datas é a &quot;Data final&quot; e a &quot;Duração&quot;. Você perceberá que a opção &quot;Iniciar&quot; está em cinza. A data inicial muda automaticamente com base nas seleções de data final e duração.

   Você pode acessar os intervalos de datas fixos disponíveis na lista suspensa [!UICONTROL Intervalo de datas predefinido].

1. Revise os dados do relatório de [!UICONTROL Atributos importantes].

1. (Opcional) Clique no ícone Baixar ( ![ícone Baixar](/help/main/assets/icons/Download.svg) ) para [baixar o relatório no formato CSV](/help/main/c-reports/c-report-settings/report-settings.md#section_77E65C50BAAF4AB79242DB3A8778ADEF) para análise no Excel e em outras ferramentas.

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

Consulte as seguintes perguntas frequentes para obter respostas sobre o uso do relatório de [!UICONTROL Atributos importantes].

### Os relatórios do Personalization Insights ainda não estão disponíveis para minha atividade. Por que isso ocorre?

Há vários motivos pelos quais os [!UICONTROL Personalization Insights] relatórios podem ainda não estar disponíveis para a sua atividade:

* O prazo de 15 dias desde que a atividade foi ativada não decorreu. Os relatórios de Segmentos automatizados e Atributos importantes não estarão disponíveis até pelo menos 15 dias após o início da atividade. Durante esse período inicial, você não poderá acessar esses relatórios ou clicar nos ícones de Segmentos automatizados e Atributos personalizados do modelo.
* Sua atividade não teve tráfego suficiente durante o intervalo de tempo especificado. Após 15 dias, supondo que haja [tráfego personalizado suficiente](/help/main/c-activities/auto-target/auto-target-to-optimize.md#section_BA4D83BE40F14A96BE7CBC7C7CF2A8FB) na atividade para criar modelos de personalização, os relatórios de Segmentos automatizados e Atributos importantes ficarão disponíveis.
* Sua atividade tem uma meta de otimização de receita. No momento, os [!UICONTROL Insights de personalização] estão disponíveis apenas para atividades com meta de otimização de conversão. O suporte será adicionado para atividades com meta de otimização de receita em uma versão futura.

### O que é um atributo?

Um atributo é a informação sobre um visitante ou sua visita específica usada pelos algoritmos de personalização para saber como personalizar o tráfego. Por exemplo, um atributo pode ser o tipo de navegador, a localização, a hora do dia da visita e assim por diante.

Para obter mais informações sobre quais atributos o [!DNL Target] usa em seus modelos de personalização, consulte [Coleta de dados para os algoritmos de personalização do Target](/help/main/c-activities/t-automated-personalization/ap-data.md). Para obter mais informações sobre como fazer upload de novos atributos no Target para usar nos modelos de personalização do Target, consulte [Métodos para colocar os dados no Target](https://experienceleague.adobe.com/docs/target-dev/developer/implementation/methods/methods-to-get-data-into-target.html?lang=pt-BR){target=_blank}.

### Há um ou mais atributos que não desejo que o modelo use para treinamento. Posso remover esses atributos do modelo de treinamento? {#models-api}

A [!UICONTROL API de Modelos], também chamada de API de Inclui na lista de bloqueios, permite que os usuários visualizem e gerenciem a lista de atributos (também chamados de recursos) usados em modelos de aprendizado de máquina de atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] (AT). Se você quiser excluir um ou mais atributos de serem usados pelos modelos para atividades de AP ou AT, poderá usar a API de modelos para adicionar esses atributos ao &quot;incluo na lista de bloqueios&quot;.

Para obter informações detalhadas, consulte [Visão geral da API de modelos](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api.html){target=_blank} no *Guia do Desenvolvedor do Adobe Target*. Para usar a API para bloquear atributos, consulte [API de modelos](https://experienceleague.adobe.com/docs/target-dev/developer/api/models-api/models-api-overview.html){target=_blank}.

### As informações nos [!UICONTROL Segmentos automatizados] e [!UICONTROL Atributos importantes] são as mesmas que no download do CSV?

Não, o relatório da interface do usuário contém informações selecionadas. O download do CSV contém detalhes adicionais. O download do relatório de Insights do segmento automatizado contém Segmentos automatizados adicionais, além dos principais segmentos incluídos na interface do usuário, juntamente com a forma como esses segmentos são executados em relação às ofertas ou experiências. O relatório de Atributos importantes inclui os 100 principais atributos de visitantes e sua importância relativa, enquanto a interface do usuário inclui apenas os 10 principais atributos de visitantes.

### Posso ver o Personalization Insights para um intervalo de datas personalizado?

Os relatórios dos Insights de personalização (os [!UICONTROL Segmentos automatizados] e [!UICONTROL Atributos importantes]) estão disponíveis apenas para intervalos de datas fixos: 15 dias, 30 dias, 45 dias, 60 dias e 90 dias. Esses intervalos de datas fixos permitem que os [!UICONTROL Insights de personalização] usem um intervalo de dados grande o suficiente para reduzir a probabilidade de obter insights de um padrão de curta duração na atividade. Você pode selecionar essas durações para qualquer data final (onde esses dados são suficientes na atividade para atender a duração).

### Como o [!UICONTROL Personalization Insights] é criado?

[!UICONTROL Os Insights de personalização são criados usando uma técnica de patente pendente da Adobe chamada MAGIX (Model Agnostic Globally Interpretable Explanations). ] Você pode saber mais sobre o MAGIX no paper publicado pela equipe de pesquisa da Adobe no [site do arXiv.org](https://arxiv.org/abs/1706.07160).

### Os [!UICONTROL Personalization Insights] estão disponíveis para metas de modelagem baseadas em receita/meta principal?

No momento, os [!UICONTROL Insights de personalização] estão disponíveis apenas para atividades com meta de otimização de conversão. O suporte será adicionado para atividades com meta de otimização de receita em uma versão futura.

### Qual é a pontuação de importância do atributo no relatório de Atributos importantes?

A pontuação de importância na parte do relatório &quot;Classificação de importância do atributo&quot; fornece informações sobre quais variáveis usadas pelo algoritmo para aprender eram mais importantes ao determinar como dividir todos os visitantes nos segmentos identificados. Ele atribuiu uma pontuação percentual aos 100 principais atributos usados pelo modelo.

### Por que algumas ofertas/experiências com uma taxa de conversão mais baixa recebem uma quantidade maior de tráfego em comparação a outras ofertas/experiências para um determinado segmento automatizado?

Há vários motivos possíveis pelos quais você pode ver mais visitas para uma oferta/experiência de conversão mais baixa em um segmento automatizado, incluindo:

* Um pequeno número de visualizações para algumas ou todas as ofertas/experiências de um determinado segmento automatizado.
* Atividades de volume inferior nas quais determinadas ofertas ou experiências não têm modelos criados.
* Atividades de volume inferior nas quais foram criados modelos para algumas ofertas/experiências antes do que para outras. Por exemplo, suponha que um modelo adicional foi criado no dia 22 e você está analisando os dados dos dias 10 a 24.
* Regras de direcionamento em uma oferta específica que limitam quais visitantes podem ver quais ofertas/experiências.
* Não há intervalos de confiança no relatório de insight. No entanto, se os índices de conversão estiverem próximos o suficiente, o modelo poderá fornecer tráfego para que o número seja maior em um ponto, mas não &quot;estatisticamente diferente&quot; do outro.

Pode ser útil saber como o modelo fornece o tráfego. Cada pessoa é servida com base no seu perfil total. No entanto, os relatórios de Insights generalizam esse comportamento para facilitar sua interpretação por um humano. Como resultado, os segmentos não são mutuamente exclusivos. Isso pode fazer com que segmentos individuais exibam esse tipo de comportamento, pois uma mesma pessoa pode aparecer em vários segmentos.

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

* Os nomes de segmento do [!DNL Adobe Experience Platform] não são exibidos no relatório de [!UICONTROL Atributos importantes] para as atividades de [!UICONTROL Automated Personalization] (AP) e [!UICONTROL Direcionamento automático] (AT). (TOP-3813)
