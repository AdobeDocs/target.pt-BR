---
keywords: Targeting;success;conversion metric;page score metric;page views metric;revenue metrics;time on site metric;estimated value;advanced settings;success metrics;advanced settings
description: No Adobe Target, as métricas de sucesso são parâmetros usados para medir o sucesso de uma atividade. As métricas de sucesso incluem as principais medidas de negócios que permitem determinar o sucesso de uma dada experiência ou oferta em uma atividade do Target.
title: Métricas de sucesso no Adobe Target
feature: success metrics
uuid: 24e9ae0f-099b-430b-b2bb-03b405f88929
translation-type: tm+mt
source-git-commit: b2f80c89ecceb6f88a176db7a90e71a162a24641
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 53%

---


# Métricas de sucesso{#success-metrics}

In [!DNL Adobe Target] success metrics are parameters used to measure the success of an activity. Success metrics include key business measures that enable you to determine the success of a given experience or offer in a [!DNL Target] activity.

Por exemplo, você pode determinar se uma nova oferta aumenta sua receita por visitante ou adicionar um item ao carrinho de compras. As métricas de sucesso podem ser úteis para descobrir problemas nos funis de registro, pedido ou compra, além de facilitar a descoberta de problemas no envolvimento de visitantes ou clientes.

## Visão geral

Em [!DNL Target]geral, as métricas de sucesso são pré-configuradas com as opções ideais para fins de relatórios e rastreamento.

Por padrão, os eventos de conversão são definidos como &quot;[!UICONTROL Aumentar a contagem e manter o usuário na atividade]&quot;. As conversões são contadas apenas uma vez, nenhuma conversão repetida é contada e o visitante sempre visualiza o conteúdo da atividade.

Revenue metrics that are set to &quot;[!UICONTROL Increment count &amp; keep user in activity]&quot; log order details only for the first order made by the same visitor. All subsequent orders increase conversion count, but will not add revenue to RPV/AOV/Sales, and will not be included in the [!UICONTROL Order Details] report.

>[!NOTE]
>
>O comportamento padrão do atividade que usa o [Analytics como fonte](/help/c-integrating-target-with-mac/a4t/a4t.md) de relatórios (A4T) é &quot;[!UICONTROL Aumentar a contagem e manter o usuário na atividade]&quot; com &quot;[!UICONTROL Uma vez por participante]&quot;.

As seguintes métricas estão disponíveis:

| Métrica de Sucesso | Abordagem de medida | Definição |
|--- |--- |--- |
| Conversão | Com base em conversão | A conversão ocorre quando um visitante executa uma ação no site definida por você, como <ul><li>Clicou em um botão</li><li>Visualizou uma página</li><li>Concluída uma pesquisa</li><li>Compra realizada</li></ul>Uma conversão pode ser contada uma vez por visitante ou sempre que um visitante concluir uma conversão. |
| Receita | Com base em conversão | A receita gerada pela visita. Você pode escolher entre as seguintes métricas de campanha:<ul><li>Receita por Visitante (RPV)</li><li>Valor Médio de Pedido (AOV)</li><li>Vendas Totais</li><li>Pedidos</li></ul> |
| Exibições de página | Com base em participação | Cada visitante único é contado como uma conversão. |
| Pontuação personalizada | Com base em participação | Aggregated score based on the value assigned to pages visited on the site, from the point the visitor first sees the activity&#39;s first display [!DNL Target] request. |
| Tempo no Site | Com base em participação | Time spent in the visit (in seconds) from the point the visitor sees the activity&#39;s first display [!DNL Target] request to the load of the final page with a request in the session. |

Para métricas com base em participação (diferente de métricas com base em conversão e com base na receita), os visitantes devem se requalificar para a atividade em cada visita para incrementar a contagem dessa sessão. A métrica associada começa a incrementar após a requalificação e interrompe no final de cada sessão do visitante. Uma sessão é finalizada depois de 30 minutos de inatividade. Portanto, você não verá resultados imediatamente durante os testes. no entanto, todos os resultados dessa sessão estarão disponíveis em alguns minutos após o término da sessão.

## Métricas de sucesso personalizadas

Também é possível criar métricas de sucesso personalizadas.

Depois de selecionar a métrica de sucesso, selecione a ação executada por um visitante para atingir essa meta. For example, choose a [!UICONTROL Conversion] metric, set it to be counted once per visitor, then set whether success is achieved when a visitor views a certain page (or set of pages), views a specific [!DNL Target] request, or clicks a specific link.

If enabled, the [!UICONTROL Estimated Value of one conversion] field (not available for the [!UICONTROL Page Score] metrics) provides a value for your goal, but not for other metrics. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. For all revenue metrics ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales], and [!UICONTROL Orders]), the estimate uses [!UICONTROL Revenue per Visitor]. O tipo de dados é a moeda. Consulte [Aumento estimado na receita](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

As métricas de sucesso escolhidas para sua atividade estão disponíveis nas configurações de relatório quando você exibe um relatório da atividade.

Some metrics, such as [!UICONTROL Custom Scoring] and [!UICONTROL Revenue Per Visitor], require a customized implementation that passes in information such as order totals and order IDs.

## Configurações avançadas {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use as configurações avançadas para gerenciar a medição do sucesso. As opções incluem a contagem da métrica por impressão ou uma vez a cada visitante e a escolha entre manter o usuário na atividade ou removê-lo.

Para acessar as opções de Configurações  avançadas, clique nas elipses **[!UICONTROL verticais]** > Configurações **** avançadas.

![Menu Configurações avançadas](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. The [!UICONTROL Advanced Settings] option will not be available. For more information, see [Adobe Analytics as the reporting source for Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).

Também é possível usar as configurações avançadas para criar métricas de sucesso dependentes, incrementando somente uma métrica se um visitante atingir outra métrica primeiro.

![Adicionar dependência](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Por exemplo, uma conversão de teste só pode ser válida se o visitante clica na oferta ou atinge uma página específica antes da conversão.

Métricas de sucesso dependentes são suportadas nas atividades de teste A/B, Personalização automatizada, Direcionamento de experiência e teste multivariado. As atividades do Recommendations atualmente não suportam métricas de sucesso dependentes.

>[!NOTE]
>
>As métricas de sucesso dependentes não serão convertidas nos seguintes casos:
>
>* Se você criar uma dependência circular na qual a métrica1 é dependente da métrica2 e a métrica2 é dependente da métrica1, nenhuma métrica poderá ser convertida.
>* As atividades de Personalização automatizada liberam os usuários e reiniciam a atividade quando as métricas de conversão são atingidas; portanto, qualquer métrica dependente da métrica de conversão não será convertida.


Use as configurações avançadas para determinar o que acontece depois que um usuário atinge a métrica de meta. A tabela a seguir mostra as opções disponíveis:

| Depois que um usuário atinge esta métrica de meta | Opções |
|--- |--- |
| [!UICONTROL Incrementar contagem e manter usuário em atividade] | Especifique como a contagem é incrementada:<ul><li>Uma vez por participante (padrão)</li><li>Em todas as impressões, excluindo as atualizações de página</li><li>Em todas as impressões</li></ul> |
| [!UICONTROL Aumentar contagem, liberar usuário e permitir reentrada] | Selecione a experiência que o visitante vê ao entrar na atividade novamente:<ul><li>Mesma experiência (padrão)</li><li>Experiência aleatória</li><li>Experiência invisível</li></ul> |
| [!UICONTROL Aumentar a contagem, liberar o usuário e impedir a reentrada] | Determine o que o usuário vê no lugar do conteúdo da atividade:<ul><li>Mesma experiência, sem rastreamento (padrão)</li><li>Conteúdo padrão ou outro conteúdo da atividade</li></ul> |

>[!NOTE]
>
>Se você configurar uma métrica para uma das opções de Contagem [!UICONTROL de] incrementos (mencionadas acima), a contagem de métricas incrementará corretamente apenas uma vez por participante no nível do visitante. A contagem de métricas aumenta uma vez por visita para cada nova sessão no nível da visita.

## Vídeo de treinamento: métricas de atividade

Estes vídeos mostram como usar métricas de atividade.

* Compreender métricas de &quot;meta&quot;
* Entender e construir métricas de conversão, receita e envolvimento
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)