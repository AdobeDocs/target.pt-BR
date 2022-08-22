---
keywords: Direcionamento, sucesso, métrica de conversão, métrica de pontuação da página, métrica de exibições de página, métricas de receita, métrica de tempo no site, valor estimado, configurações avançadas, métricas de sucesso, configurações avançadas, dependência, Aumentar contagem e manter o usuário na atividade, Aumentar contagem, liberar usuário e permitir reentrada, aumentar contagem, liberar usuário e impedir a reentrada
description: Saiba mais sobre as métricas de sucesso no Adobe [!DNL Target] que ajudam a determinar o sucesso de uma atividade. As métricas de sucesso incluem Conversão, Receita, Exibições de página, Pontuação personalizada e Tempo no site.
title: O que são métricas de sucesso?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
source-git-commit: 7dd3e3167b7dcb4de9e2980e6fc41661a2574abc
workflow-type: tm+mt
source-wordcount: '1171'
ht-degree: 44%

---

# Métricas de sucesso

Em [!DNL Adobe Target] métricas de sucesso são parâmetros usados para medir o sucesso de uma atividade. As métricas de sucesso incluem as principais medidas de negócios que permitem determinar o sucesso de uma determinada experiência ou oferta em uma [!DNL Target] atividade .

Por exemplo, você pode determinar se uma nova oferta aumenta sua receita por visitante ou adicionar um item ao carrinho de compras. As métricas de sucesso podem ser úteis para descobrir problemas nos funis de registro, pedido ou compra, além de facilitar a descoberta de problemas no envolvimento de visitantes ou clientes.

## Visão geral

Em [!DNL Target], as métricas de sucesso são pré-configuradas com as opções ideais para fins de relatório e rastreamento.

Por padrão, os eventos de conversão são definidos como &quot;[!UICONTROL Incrementar a contagem e manter o usuário na atividade].&quot; As conversões são contadas apenas uma vez, nenhuma conversão repetida é contada e o visitante sempre vê o conteúdo da atividade.

Métricas de receita definidas como &quot;[!UICONTROL Incrementar a contagem e manter o usuário na atividade]&quot; registrar detalhes do pedido somente para o primeiro pedido feito pelo mesmo visitante. Todos os pedidos subsequentes aumentam a contagem de conversão, mas não adicionam receita a RPV/AOV/Vendas e não serão incluídos na [!UICONTROL Detalhes do pedido] relatório.

>[!NOTE]
>
>Para atividades que usam [Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), a métrica de meta sempre usará o &quot;[!UICONTROL Aumentar a contagem e manter o usuário na atividade]&quot; e &quot;[!UICONTROL Em todas as impressões]&quot;. Isso é *not* configurável.

As seguintes métricas estão disponíveis:

| Métrica de Sucesso | Abordagem de medida | Definição |
|--- |--- |--- |
| Conversão | Com base em conversão | A conversão ocorre quando um visitante executa uma ação definida no site, como <ul><li>Clicou em um botão</li><li>Visualizou uma página</li><li>Concluída uma pesquisa</li><li>Compra realizada</li></ul>Uma conversão pode ser contada uma vez por visitante ou sempre que um visitante concluir uma conversão. |
| Receita | Com base em conversão | A receita gerada pela visita. Você pode escolher entre as seguintes métricas de campanha:<ul><li>Receita por Visitante (RPV)</li><li>Valor Médio de Pedido (AOV)</li><li>Vendas Totais</li><li>Pedidos</li></ul> |
| Exibições de página | Com base em participação | Cada visitante único é contado como uma conversão. |
| Pontuação personalizada | Com base em participação | Pontuação agregada com base no valor atribuído às páginas visitadas no site, a partir do momento em que o visitante exibe a primeira atividade [!DNL Target] solicitação. |
| Tempo no Site | Com base em participação | Tempo gasto na visita (em segundos) a partir do momento em que o visitante visualiza a primeira exibição da atividade [!DNL Target] à carga da página final com uma solicitação na sessão. |

Para métricas com base em participação (diferente de métricas com base em conversão e com base na receita), os visitantes devem se requalificar para a atividade em cada visita para incrementar a contagem dessa sessão. A métrica associada começa a incrementar após a requalificação e interrompe no final de cada sessão do visitante. Uma sessão é finalizada depois de 30 minutos de inatividade. Portanto, você não verá resultados imediatamente durante os testes; no entanto, todos os resultados dessa sessão estarão disponíveis dentro de alguns minutos do término da sessão.

## Métricas de sucesso personalizadas

Também é possível criar métricas de sucesso personalizadas.

Depois de selecionar a métrica de sucesso, selecione a ação executada por um visitante para atingir essa meta. Por exemplo, escolha uma [!UICONTROL Conversão] , defina-a para ser contada uma vez por visitante e defina se o sucesso será obtido quando um visitante visualizar uma determinada página (ou conjunto de páginas), visualizar um [!DNL Target] ou clicar em um link específico.

Se estiver habilitado, a variável [!UICONTROL Valor estimado de uma conversão] (não disponível para a variável [!UICONTROL Pontuação da página] métricas) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Receita por visitante], [!UICONTROL Valor médio de pedido], [!UICONTROL Vendas totais]e [!UICONTROL Pedidos]), a estimativa utiliza [!UICONTROL Receita por visitante]. O tipo de dados é a moeda. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

As métricas de sucesso escolhidas para sua atividade estão disponíveis nas configurações de relatório quando você exibe um relatório da atividade.

Algumas métricas, como [!UICONTROL Pontuação personalizada] e [!UICONTROL Receita por visitante], exigem uma implementação personalizada que passa informações como totais do pedido e IDs do pedido.

## Configurações avançadas {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use as configurações avançadas para gerenciar a medição do sucesso. As opções incluem adicionar dependências, escolher manter o usuário na atividade ou removê-lo e contar a métrica uma vez por participante ou em todas as impressões.

Para acessar o [!UICONTROL Configurações avançadas] clique no botão **[!UICONTROL elipses verticais]** > **[!UICONTROL Configurações avançadas]**.

![Menu Configurações avançadas](/help/main/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. O [!UICONTROL Configurações avançadas] não estará disponível. Para obter mais informações, consulte [Adobe Analytics como origem de relatório do Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Adicionar dependência

Você pode usar as configurações avançadas para criar métricas de sucesso dependentes, incrementando uma métrica somente se um visitante atingir outra métrica primeiro.

![Adicionar dependência](/help/main/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Por exemplo, uma conversão de teste só pode ser válida se o visitante clica na oferta ou atinge uma página específica antes da conversão.

A funcionalidade de dependência é *not* suportado pelo seguinte:

* Atividades do [!UICONTROL Recommendations. ] Esta funcionalidade é compatível com todos os outros tipos de atividade.
* Se você usar [Analytics como sua fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* O tipo de métrica “Visualizou uma página”.
* O tipo de métrica “Clicou em um elemento” para as atividades do Visual Experience Composer (VEC).

As métricas de sucesso dependentes não serão convertidas nos seguintes casos:

* Se você criar uma dependência circular na qual a métrica1 é dependente da métrica2 e a métrica2 é dependente da métrica1, nenhuma métrica poderá ser convertida.
* As atividades de Personalização automatizada liberam os usuários e reiniciam a atividade quando as métricas de conversão são atingidas; portanto, qualquer métrica dependente da métrica de conversão não será convertida.

### O que acontece depois que um usuário atinge esta métrica de meta?

Use as configurações avançadas para determinar o que acontece depois que um usuário atinge a métrica de meta. A tabela a seguir mostra as opções disponíveis:

| Depois que um usuário atinge esta métrica de meta | Opções |
|--- |--- |
| [!UICONTROL Incrementar contagem e manter usuário em atividade] | Especifique como a contagem é incrementada:<ul><li>Uma vez por participante (padrão)</li><li>Em todas as impressões, excluindo as atualizações de página</li><li>Em todas as impressões</li></ul> |
| [!UICONTROL Aumentar a contagem, liberar o usuário e permitir reentrada] | Selecione a experiência que o visitante vê ao entrar na atividade novamente:<ul><li>Mesma experiência (padrão)</li><li>Experiência aleatória</li><li>Experiência invisível</li></ul> |
| [!UICONTROL Aumentar a contagem, liberar o usuário e impedir a reentrada] | Determine o que o usuário vê no lugar do conteúdo da atividade:<ul><li>Mesma experiência, sem rastreamento (padrão)</li><li>Conteúdo padrão ou outro conteúdo da atividade</li></ul> |

>[!NOTE]
>
>Se você configurar uma métrica para uma das [!UICONTROL Contagem de incrementos] opções (mencionadas acima), a contagem de métrica é incrementada corretamente uma vez por participante somente no nível do visitante. A contagem de métricas é incrementada uma vez por visita para cada nova sessão no nível da visita.

### De que maneira a contagem será incrementada:

Escolha o comportamento desejado:

* Uma vez por participante
* Em todas as impressões (excluindo atualizações de página)
* Em todas as impressões

## Vídeo de treinamento: métricas de atividade

Estes vídeos mostram como usar métricas de atividade.

* Compreender métricas de &quot;meta&quot;
* Entender e construir métricas de conversão, receita e envolvimento
* Criar uma métrica de rastreamento de cliques

>[!VIDEO](https://video.tv.adobe.com/v/17380)
