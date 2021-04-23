---
keywords: Direcionamento, sucesso, métrica de conversão, métrica de pontuação da página, métrica de exibições de página, métricas de receita, métrica de tempo no site, valor estimado, configurações avançadas, métricas de sucesso, configurações avançadas, dependência, Aumentar contagem e manter o usuário na atividade, Aumentar contagem, liberar usuário e permitir reentrada, aumentar contagem, liberar usuário e impedir a reentrada
description: Saiba mais sobre as métricas de sucesso no Adobe [!DNL Target] que ajudam a determinar o sucesso de uma atividade. As métricas de sucesso incluem Conversão, Receita, Exibições de página, Pontuação personalizada e Tempo no site.
title: O que são métricas de sucesso?
feature: Métricas de sucesso
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '1174'
ht-degree: 44%

---

# Métricas de sucesso

Em [!DNL Adobe Target] as métricas de sucesso são parâmetros usados para medir o sucesso de uma atividade. As métricas de sucesso incluem medidas comerciais essenciais que permitem determinar o sucesso de uma determinada experiência ou oferta em uma atividade [!DNL Target] .

Por exemplo, você pode determinar se uma nova oferta aumenta sua receita por visitante ou adicionar um item ao carrinho de compras. As métricas de sucesso podem ser úteis para descobrir problemas nos funis de registro, pedido ou compra, além de facilitar a descoberta de problemas no envolvimento de visitantes ou clientes.

## Visão geral

Em [!DNL Target], as métricas de sucesso são pré-configuradas com as opções ideais para fins de relatório e rastreamento.

Por padrão, os eventos de conversão são definidos como &quot;[!UICONTROL Incrementar contagem e manter o usuário em atividade]&quot;. As conversões são contadas apenas uma vez, nenhuma conversão repetida é contada e o visitante sempre vê o conteúdo da atividade.

Métricas de receita definidas como &quot;[!UICONTROL Incrementar contagem e manter o usuário em atividade]&quot; registram detalhes do pedido somente para o primeiro pedido feito pelo mesmo visitante. Todos os pedidos subsequentes aumentam a contagem de conversão, mas não adicionam receita a RPV/AOV/Vendas, e não serão incluídos no relatório [!UICONTROL Detalhes do pedido].

>[!NOTE]
>
>Para atividades que usam [Analytics como fonte de relatórios](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T), a métrica de meta sempre usará as configurações &quot;[!UICONTROL Aumentar contagem e manter o usuário na atividade]&quot; e &quot;[!UICONTROL Em todas as impressões]&quot;. Isso é *não* configurável.

As seguintes métricas estão disponíveis:

| Métrica de Sucesso | Abordagem de medida | Definição |
|--- |--- |--- |
| Conversão | Com base em conversão | A conversão ocorre quando um visitante executa uma ação definida no site, como <ul><li>Clicou em um botão</li><li>Visualizou uma página</li><li>Concluída uma pesquisa</li><li>Compra realizada</li></ul>Uma conversão pode ser contada uma vez por visitante ou sempre que um visitante concluir uma conversão. |
| Receita | Com base em conversão | A receita gerada pela visita. Você pode escolher entre as seguintes métricas de campanha:<ul><li>Receita por Visitante (RPV)</li><li>Valor Médio de Pedido (AOV)</li><li>Vendas Totais</li><li>Pedidos</li></ul> |
| Exibições de página | Com base em participação | Cada visitante único é contado como uma conversão. |
| Pontuação personalizada | Com base em participação | A pontuação agregada com base no valor atribuído às páginas visitadas no site, a partir do momento em que o visitante exibe a primeira solicitação [!DNL Target] da atividade. |
| Tempo no Site | Com base em participação | O tempo gasto na visita (em segundos) a partir do momento em que o visitante visualiza a primeira solicitação de exibição da atividade [!DNL Target] até o carregamento da página final com uma solicitação na sessão. |

Para métricas com base em participação (diferente de métricas com base em conversão e com base na receita), os visitantes devem se requalificar para a atividade em cada visita para incrementar a contagem dessa sessão. A métrica associada começa a incrementar após a requalificação e interrompe no final de cada sessão do visitante. Uma sessão é finalizada depois de 30 minutos de inatividade. Portanto, você não verá resultados imediatamente durante os testes; no entanto, todos os resultados dessa sessão estarão disponíveis dentro de alguns minutos do término da sessão.

## Métricas de sucesso personalizadas

Também é possível criar métricas de sucesso personalizadas.

Depois de selecionar a métrica de sucesso, selecione a ação executada por um visitante para atingir essa meta. Por exemplo, escolha uma métrica de [!UICONTROL Conversão], defina-a para ser contada uma vez por visitante e defina se o sucesso será obtido quando um visitante visualizar uma determinada página (ou conjunto de páginas), visualizar uma solicitação [!DNL Target] específica ou clicar em um link específico.

Se estiver habilitado, o campo [!UICONTROL Valor estimado de uma conversão] (não disponível para as métricas [!UICONTROL Pontuação da página]) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Receita por visitante], [!UICONTROL Valor médio do pedido], [!UICONTROL Vendas totais] e [!UICONTROL Pedidos]), a estimativa usa [!UICONTROL Receita por visitante]. O tipo de dados é a moeda. Consulte [Aumento estimado na receita](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

As métricas de sucesso escolhidas para sua atividade estão disponíveis nas configurações de relatório quando você exibe um relatório da atividade.

Algumas métricas, como [!UICONTROL Pontuação personalizada] e [!UICONTROL Receita por visitante], exigem uma implementação personalizada que passa informações como totais do pedido e IDs do pedido.

## Configurações avançadas {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use as configurações avançadas para gerenciar a medição do sucesso. As opções incluem adicionar dependências, escolher manter o usuário na atividade ou removê-lo e contar a métrica uma vez por participante ou em todas as impressões.

Para acessar as opções [!UICONTROL Configurações avançadas], clique no **[!UICONTROL elipses verticais]** > **[!UICONTROL Configurações avançadas]**.

![Menu Configurações avançadas](/help/c-activities/r-success-metrics/assets/advanced-settings.png)

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. A opção [!UICONTROL Configurações avançadas] não estará disponível. Para obter mais informações, consulte [Adobe Analytics como fonte de relatórios para Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md).

### Adicionar dependência

Você pode usar as configurações avançadas para criar métricas de sucesso dependentes, incrementando uma métrica somente se um visitante atingir outra métrica primeiro.

![Adicionar dependência](/help/c-activities/r-success-metrics/assets/UI_dep_success_metric.png)

Por exemplo, uma conversão de teste só pode ser válida se o visitante clica na oferta ou atinge uma página específica antes da conversão.

A funcionalidade de dependência é *não* suportada para o seguinte:

* [!UICONTROL Atividades do Recommendations. ] Esta funcionalidade é compatível com todos os outros tipos de atividade.
* Se você usar o [Analytics como fonte de relatórios](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
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
>Se você configurar uma métrica para uma das opções [!UICONTROL Incrementar contagem] (mencionadas acima), a contagem de métrica será incrementada corretamente uma vez por participante somente no nível do visitante. A contagem de métricas é incrementada uma vez por visita para cada nova sessão no nível da visita.

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
