---
keywords: Direcionamento;sucesso;métrica de conversão;métrica de pontuação da página;métricas de exibições de página;métricas de receita;métrica de tempo no site;valor estimado;configurações avançadas;métricas de sucesso;configurações avançadas;dependência;dependente;Incrementar contagem e manter usuário em atividade;Incrementar contagem, liberar usuário, & permitir reentrada;incrementar contagem, liberar usuário, & impedir de reentrada
description: Saiba mais sobre as métricas de sucesso do Adobe [!DNL Target]  que ajudam você a determinar o sucesso de uma atividade. As métricas de sucesso incluem Conversão, Receita, Visualizações de página, Pontuação personalizada e Tempo no site.
title: O que são métricas de sucesso?
feature: Success Metrics
hide: true
hidefromtoc: true
source-git-commit: 99ea312405e397e97e64e32d2685e8a6966d8928
workflow-type: tm+mt
source-wordcount: '1190'
ht-degree: 41%

---

# Métricas de sucesso

Em [!DNL Adobe Target] métricas de sucesso são parâmetros usados para medir o sucesso de uma atividade. As métricas de sucesso incluem as principais medidas de negócios que permitem determinar o sucesso de uma determinada experiência ou oferta em uma atividade do [!DNL Target].

Por exemplo, você pode determinar se uma nova oferta aumenta sua receita por visitante ou adicionar um item ao carrinho de compras. As métricas de sucesso podem ser úteis para descobrir problemas nos funis de registro, pedido ou compra, além de facilitar a descoberta de problemas no envolvimento de visitantes ou clientes.

## Visão geral

No [!DNL Target], as métricas de sucesso são pré-configuradas com as opções ideais para relatórios e rastreamento.

Por padrão, os eventos de conversão são definidos como &quot;[!UICONTROL Increment count & keep user in activity]&quot;. As conversões são contadas apenas uma vez, nenhuma conversão repetida é contada e o visitante sempre vê o conteúdo da atividade.

Métricas de receita definidas como &quot;[!UICONTROL Increment count & keep user in activity]&quot; registram detalhes da ordem somente para a primeira ordem feita pelo mesmo visitante. Todos os pedidos subsequentes aumentam a contagem de conversão, mas não adicionarão receita a RPV/AOV/Vendas e não serão incluídos no relatório [!UICONTROL Order Details].

>[!NOTE]
>
>Para atividades que usam o [Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), a métrica de meta sempre usará as configurações &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; e &quot;[!UICONTROL On Every Impression]&quot;. Isto é *não* configurável.

As seguintes métricas estão disponíveis:

| Métrica de Sucesso | Abordagem de medida | Definição |
|--- |--- |--- |
| Conversão | Com base em conversão | A conversão é quando um visitante executa uma ação no site definida por você, como <ul><li>Clicou em um botão</li><li>Visualizou uma página</li><li>Concluiu uma pesquisa</li><li>Fez uma compra</li></ul>Uma conversão pode ser contada uma vez por visitante ou cada vez que um visitante conclui uma conversão. |
| Receita | Com base em conversão | A receita gerada pela visita. Você pode escolher entre as seguintes métricas de campanha:<ul><li>Receita por Visitante (RPV)</li><li>Valor Médio de Pedido (AOV)</li><li>Vendas Totais</li><li>Pedidos</li></ul> |
| Exibições de página | Com base em participação | Cada visitante único é contado como uma conversão. |
| Pontuação personalizada | Com base em participação | Pontuação agregada com base no valor atribuído às páginas visitadas no site, a partir do momento em que o visitante vê a primeira solicitação de exibição [!DNL Target] da atividade. |
| Tempo no Site | Com base em participação | Tempo gasto na visita (em segundos) desde o momento em que o visitante visualiza a primeira solicitação de exibição [!DNL Target] da atividade até o carregamento da página final com uma solicitação na sessão. |

Para métricas com base em participação (diferente de métricas com base em conversão e com base na receita), os visitantes devem se requalificar para a atividade em cada visita para incrementar a contagem dessa sessão. A métrica associada começa a incrementar após a requalificação e interrompe no final de cada sessão do visitante. Uma sessão é finalizada depois de 30 minutos de inatividade. Portanto, você não verá os resultados imediatamente durante o teste; no entanto, todos os resultados dessa sessão estarão disponíveis dentro de alguns minutos após o término da sessão.

## Métricas de sucesso personalizadas

Também é possível criar métricas de sucesso personalizadas.

Depois de selecionar a métrica de sucesso, selecione a ação executada por um visitante para atingir essa meta. Por exemplo, escolha uma métrica [!UICONTROL Conversion], defina-a para ser contada uma vez por visitante e, em seguida, defina se o sucesso será obtido quando um visitante visualizar determinada página (ou conjunto de páginas), visualizar uma solicitação [!DNL Target] específica ou clicar em um link específico.

Se estiver habilitado, o campo [!UICONTROL Estimated Value of one conversion] (não disponível para as métricas [!UICONTROL Page Score]) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] e [!UICONTROL Orders]), a estimativa usa [!UICONTROL Revenue per Visitor]. O tipo de dados é a moeda. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

As métricas de sucesso escolhidas para sua atividade estão disponíveis nas configurações de relatório quando você exibe um relatório da atividade.

Algumas métricas, como [!UICONTROL Custom Scoring] e [!UICONTROL Revenue Per Visitor], exigem uma implementação personalizada que transmite informações como totais de pedidos e IDs de pedidos.

## Configurações avançadas {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use as configurações avançadas para gerenciar a medição do sucesso. As opções incluem adicionar dependências, escolher se deseja manter o usuário na atividade ou removê-lo e se deseja contar a métrica uma vez por participante ou em cada impressão.

Para acessar as opções de [!UICONTROL Advanced Settings], clique no ícone **[!UICONTROL More Actions]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallListVert.svg) ) e clique em **[!UICONTROL Advanced Settings]**.

![Menu Configurações avançadas](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. A opção [!UICONTROL Advanced Settings] não estará disponível. Para obter mais informações, consulte [Adobe Analytics como origem de relatório do Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Adicionar dependência

Você pode usar as configurações avançadas para criar métricas de sucesso dependentes, incrementando apenas uma métrica se um visitante atingir outra métrica primeiro.

Por exemplo, uma conversão de teste só pode ser válida se o visitante clica na oferta ou atinge uma página específica antes da conversão.

A funcionalidade de dependência *não* tem suporte para o seguinte:

* [!UICONTROL Recommendations] atividades. Esta funcionalidade é compatível com todos os outros tipos de atividade.
* Se você usa o [Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* O tipo de métrica &quot;Visualizou uma página&quot;.
* O tipo de métrica &quot;Clicou em um elemento&quot; para atividades do Visual Experience Composer (VEC).

As métricas de sucesso dependentes não serão convertidas nos seguintes casos:

* Se você criar uma dependência circular na qual a métrica1 é dependente da métrica2 e a métrica2 é dependente da métrica1, nenhuma métrica poderá ser convertida.
* [!UICONTROL Automated Personalization] atividades liberam usuários e reiniciam a atividade quando as métricas de conversão são atingidas, portanto, as métricas dependentes da métrica de conversão não serão convertidas.

### O que acontece depois que um usuário atinge esta métrica de meta?

Use as configurações avançadas para determinar o que acontece depois que um usuário atinge a métrica de meta. A tabela a seguir mostra as opções disponíveis:

| Depois que um usuário atinge esta métrica de meta | Opções |
|--- |--- |
| [!UICONTROL Increment Count & Keep User in Activity] | Especifique como a contagem é incrementada:<ul><li>Uma vez por participante (padrão)</li><li>Em todas as impressões, excluindo as atualizações de página</li><li>Em todas as impressões</li></ul> |
| [!UICONTROL Increment Count, Release user, & Allow Reentry] | Selecione a experiência que o visitante vê ao entrar na atividade novamente:<ul><li>Mesma experiência (padrão)</li><li>Experiência aleatória</li><li>Experiência invisível</li></ul> |
| [!UICONTROL Increment Count, Release User, & Bar from Reentry] | Determine o que o usuário vê no lugar do conteúdo da atividade:<ul><li>Mesma experiência, sem rastreamento (padrão)</li><li>Conteúdo padrão ou outro conteúdo da atividade</li></ul> |

>[!NOTE]
>
>Se você configurar uma métrica para uma das [!UICONTROL Increment Count] opções (mencionadas acima), a contagem de métricas será incrementada corretamente uma vez por participante somente no nível do visitante. A contagem de métricas é incrementada uma vez por visita para cada nova sessão no nível da visita.

### Como a contagem será incrementada:

Escolha o comportamento desejado:

* Uma vez por participante
* Em todas as impressões (excluindo atualizações de página)
* Em todas as impressões

## Problemas conhecidos

* Métricas de sucesso com opção avançada &quot;Como a contagem será incrementada&quot; definida como &quot;a cada impressão&quot; ou &quot;a cada impressão (exceto atualizações)&quot; não pode ser usada como uma métrica de sucesso da qual dependeria outra métrica.

Quando uma métrica de sucesso é definida para incrementar a cada impressão, [!DNL Target] conta o visitante novamente sempre que ele visitar a métrica de sucesso. [!DNL Target] então redefine a métrica de sucesso &quot;associação&quot; para 0 para que ela possa contar novamente na próxima impressão. Portanto, se outra métrica exigir que essa métrica tenha sido visualizada primeiro, [!DNL Target] nunca reconhecerá que o usuário viu a primeira métrica.

## Vídeo de treinamento: métricas de atividade

Estes vídeos mostram como usar métricas de atividade.

* Compreender métricas de &quot;meta&quot;
* Entender e construir métricas de conversão, receita e envolvimento
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)
