---
keywords: Direcionamento;sucesso;métrica de conversão;métrica de pontuação da página;métricas de exibições de página;métricas de receita;métrica de tempo no site;valor estimado;configurações avançadas;métricas de sucesso;configurações avançadas;dependência;dependente;Incrementar contagem e manter usuário em atividade;Incrementar contagem, liberar usuário, & permitir reentrada;incrementar contagem, liberar usuário, & impedir de reentrada
description: Saiba mais sobre as métricas de sucesso que ajudam você a determinar o sucesso de uma atividade. As métricas de sucesso incluem Conversão, Receita, Visualizações de página, Pontuação personalizada e Tempo no site.
title: O que são métricas de sucesso?
feature: Success Metrics
exl-id: 38d5314d-4950-4106-a058-0d221faf5a24
TQID: https://experienceleague.adobe.com/utsuikYtBrKHv0bbdIu1KmlFyjXMgoC-2yaOP3-QJr8
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
feature_v2:
  - id: c93393a4-e558-47e1-992e-c91ed4d480ce
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5520579-b31f-4df7-9281-f0d9f91e2edc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
source-git-commit: 51d3993ca3daaae824b9c598529ff4038fdcdb77
workflow-type: tm+mt
source-wordcount: 1502
ht-degree: 21%

---

# [!UICONTROL Métricas de sucesso]

As métricas de sucesso do [!DNL Adobe Target] são indicadores-chave que ajudam a medir o desempenho de suas atividades. Essas métricas capturam resultados comerciais importantes, como conversões, receita por visitante e envolvimento do cliente, permitindo avaliar o impacto de experiências ou ofertas específicas.

Por exemplo, você pode rastrear se uma nova promoção aumenta a receita por visitante ou leva a mais itens adicionados aos carrinhos de compras. As métricas de sucesso também ajudam a identificar problemas nos fluxos de usuário, como registro, finalização ou processos de compra, enquanto fornecem insights sobre o comportamento geral do visitante.

## Visão geral

No [!DNL Target], as métricas de sucesso são pré-configuradas com as configurações recomendadas para garantir relatórios precisos e rastreamento eficaz.

Por padrão, os eventos de conversão usam a configuração **[!UICONTROL Aumentar contagem e manter o usuário na atividade].** Essa configuração significa que cada visitante é contado como uma conversão apenas uma vez. Nenhuma conversão repetida é contada. Esses visitantes continuam vendo o conteúdo da atividade durante toda a sessão.

Para métricas de receita que usam a mesma configuração, somente a primeira ordem de um visitante registra detalhes da ordem. Embora pedidos subsequentes aumentem a contagem de conversão, eles não contribuem para métricas baseadas em receita, como [!UICONTROL Receita por visitante (RPV)], [!UICONTROL Valor médio de pedido (AOV)] ou [!DNL Total Sales]. Esses pedidos adicionais também são excluídos do relatório [!UICONTROL Detalhes do pedido].

>[!NOTE]
>
>Para atividades que usam o [Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T), a métrica de meta sempre usa as configurações &quot;[!UICONTROL Incrementar contagem e manter usuário na atividade]&quot; e &quot;[!UICONTROL Em todas as impressões]&quot;. Estas configurações são *não* configuráveis.

As seguintes métricas de sucesso podem ser configuradas na seção [!UICONTROL Configurações de relatórios] da [!UICONTROL página Configurações da atividade], na etapa [!UICONTROL Metas e configurações]:

| Métrica de Sucesso | Abordagem de medida | Definição |
|--- |--- |--- |
| [!UICONTROL Conversão] | Com base em conversão | A conversão é quando um visitante executa uma ação no site definida por você, como <ul><li>Visualizou uma página</li><li>Visualizou uma mbox</li><li>Clicou em um elemento</li></ul>Uma conversão pode ser contada uma vez por visitante ou cada vez que um visitante conclui uma conversão. |
| [!UICONTROL Receita] | Com base em conversão | A receita gerada pela visita. Você pode escolher apenas uma métrica de receita:<ul><li>Visualizou uma mbox</li></ul>Para obter mais informações sobre alterações na interface atualizada do usuário [!DNL Target], pois ela se refere às métricas de sucesso de receita, consulte [Alterações atualizadas [!DNL Target] na interface](#changes) abaixo. |
| [!UICONTROL Participação] | Com base no engajamento | Engajamento gerado pela visita. Você pode escolher entre as seguintes métricas de envolvimento:<UL><li>Exibições de página: cada visita única é contada como uma conversão.</li><li>[!UICONTROL Pontuação personalizada]: pontuação agregada com base no valor atribuído às páginas visitadas no site, a partir do momento em que o visitante exibe a primeira solicitação de [!DNL Target] da atividade.</li>[!DNL Time on Site]: Tempo gasto na visita (em segundos) a partir do momento em que o visitante visualiza a primeira solicitação [!DNL Target] de exibição da atividade até o carregamento da página final com uma solicitação na sessão.</UL> |

Para métricas baseadas em participação (diferente de métricas baseadas em conversão e baseadas em receita), os visitantes devem se requalificar para a atividade em cada visita para incrementar a contagem dessa sessão. A métrica associada começa a incrementar após a requalificação e interrompe no final de cada sessão do visitante. Uma sessão é finalizada depois de 30 minutos de inatividade. Portanto, você não vê os resultados imediatamente durante o teste; no entanto, todos os resultados dessa sessão estão disponíveis dentro de alguns minutos após o término da sessão.

## Métricas de sucesso personalizadas

Também é possível criar métricas de sucesso personalizadas.

Depois de selecionar a métrica de sucesso, selecione a ação executada por um visitante para atingir essa meta. Por exemplo, escolha uma métrica de [!UICONTROL Conversão], defina-a para ser contada uma vez por visitante e defina se o sucesso será obtido quando um visitante visualizar determinada página (ou conjunto de páginas), visualizar uma solicitação [!DNL Target] específica ou clicar em um link específico.

Se estiver habilitado, o campo [!UICONTROL Valor estimado de uma conversão] (não disponível para as métricas [!UICONTROL Pontuação da página]) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Receita por visitante], [!UICONTROL Valor médio de pedido], [!UICONTROL Vendas totais] e [!UICONTROL Pedidos]), a estimativa usa [!UICONTROL Receita por visitante]. O tipo de dados é a moeda. Consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md) para obter mais informações.

As métricas de sucesso escolhidas para a atividade estão disponíveis nas configurações do relatório quando você exibe um relatório para a atividade.

Algumas métricas, como [!UICONTROL Pontuação personalizada] e [!UICONTROL Receita por visitante], exigem uma implementação personalizada que transmita informações, como totais de pedidos e IDs de pedidos.

## Configurações avançadas {#section_7CE95A2FA8F5438E936C365A6D43BC5B}

Use as configurações avançadas para gerenciar a medição do sucesso. As opções incluem adicionar dependências, escolher se deseja manter o usuário na atividade ou removê-lo e se deseja contar a métrica uma vez por participante ou em cada impressão.

Para acessar as opções de [!UICONTROL Configurações Avançadas], clique no ícone **[!UICONTROL Mais Ações]** ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallListVert.svg) ) e clique em **[!UICONTROL Configurações Avançadas]**.

![Menu Configurações avançadas](/help/main/c-activities/r-success-metrics/assets/advanced-settings-refresh.png)

Para obter mais informações sobre as opções de [!UICONTROL Configurações avançadas] (&quot;[!UICONTROL O que acontecerá após um usuário encontrar essa meta]&quot; e &quot;[!UICONTROL Como a contagem será incrementada]&quot;), consulte [O que acontece após um usuário encontrar essa métrica de meta](#what-happens)?

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. A opção [!UICONTROL Configurações Avançadas] não está disponível. Para obter mais informações, consulte [Adobe Analytics como origem de relatório do Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

### Adicionar dependência

Você pode usar as configurações avançadas para criar métricas de sucesso dependentes, incrementando apenas uma métrica se um visitante atingir outra métrica primeiro.

Por exemplo, uma conversão de teste só pode ser válida se o visitante clica na oferta ou atinge uma página específica antes da conversão.

A funcionalidade de dependência *não* tem suporte para o seguinte:

* [!UICONTROL Recomendações] atividades. Esta funcionalidade é compatível com todos os outros tipos de atividade.
* Se você usa o [Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* O tipo de métrica &quot;Visualizou uma página&quot;.
* O tipo de métrica &quot;Clicou em um elemento&quot; para atividades do Visual Experience Composer (VEC).

As métricas de sucesso dependentes não são convertidas nos seguintes casos:

* Se você criar uma dependência circular na qual a métrica1 é dependente da métrica2 e a métrica2 é dependente da métrica1, nenhuma métrica poderá ser convertida.
* As atividades do [!UICONTROL Automated Personalization] liberam os usuários e reiniciam a atividade quando as métricas de conversão são atingidas, portanto, as métricas dependentes da métrica de conversão não são convertidas.

### O que acontece depois que um usuário atinge esta métrica de meta? {#what-happens}

Use as configurações avançadas para determinar o que acontece depois que um usuário atinge a métrica de meta. A tabela a seguir mostra as opções disponíveis:

| Depois que um usuário atinge esta métrica de meta | Opções |
|--- |--- |
| [!UICONTROL Incrementar contagem e manter usuário na atividade] | Especifique como a contagem é incrementada:<ul><li>Uma vez por participante (padrão)</li><li>Em todas as impressões, excluindo as atualizações de página</li><li>Em todas as impressões</li></ul> |
| [!UICONTROL Incrementar contagem, liberar usuário e permitir reentrada] | Selecione a experiência que o visitante vê ao entrar na atividade novamente:<ul><li>Mesma experiência (padrão)</li><li>Experiência aleatória</li><li>Experiência invisível</li></ul> |
| [!UICONTROL Incrementar contagem, liberar usuário e impedir a reentrada] | Determine o que o usuário vê no lugar do conteúdo da atividade:<ul><li>Mesma experiência, sem rastreamento (padrão)</li><li>Conteúdo padrão ou outro conteúdo da atividade</li></ul> |

>[!NOTE]
>
>Se você configurar uma métrica para uma das opções [!UICONTROL Aumentar contagem] (mencionadas acima), a contagem da métrica será incrementada corretamente uma vez por participante somente no nível do visitante. A contagem de métricas é incrementada uma vez por visita para cada nova sessão no nível da visita.

### Como a contagem é incrementada:

Escolha o comportamento desejado:

* Uma vez por participante
* Em todas as impressões (excluindo atualizações de página)
* Em todas as impressões

## Problemas conhecidos

* Métricas de sucesso com opção avançada &quot;Como a contagem será incrementada&quot; definida como &quot;a cada impressão&quot; ou &quot;a cada impressão (exceto atualizações)&quot; não pode ser usada como uma métrica de sucesso da qual dependeria outra métrica.

  Quando uma métrica de sucesso é definida para incrementar a cada impressão, [!DNL Target] conta o visitante novamente sempre que ele visitar a métrica de sucesso. [!DNL Target] então redefine a métrica de sucesso &quot;associação&quot; para 0 para que ela possa contar novamente na próxima impressão. Portanto, se outra métrica exigir que essa métrica tenha sido visualizada primeiro, [!DNL Target] nunca reconhecerá que o usuário viu a primeira métrica.

## Atualizadas [!DNL Target] alterações na interface {#changes}

A versão [[!DNL Target Standard/Premium] 25.2.1](/help/main/r-release-notes/release-notes-for-previous-releases.md#ui-update-2), iniciada em 17 de fevereiro de 2015, apresentou interfaces atualizadas do [!DNL Target] e do [!UICONTROL Visual Experience Composer] (VEC). Esta seção descreve as principais diferenças entre a interface herdada e a atualizada, especificamente porque estão relacionadas à configuração e ao gerenciamento de métricas de sucesso.

### Alterações na interface do usuário relacionadas às métricas de sucesso de [!UICONTROL Receita]

Na interface [!DNL Target] atualizada, o menu suspenso [!UICONTROL Modo de Exibição Padrão de Relatórios] foi removido. Este campo era redundante, pois anteriormente salvava o modo de exibição de relatórios padrão em [!DNL Overview] > [!UICONTROL Relatórios] na interface herdada.

Com a interface atualizada, a métrica de relatórios padrão agora é sempre definida como [!UICONTROL Receita por visitante (RPV)]. Você ainda pode personalizar o modo de exibição na seção [!UICONTROL Relatórios] para exibir as métricas mais relevantes para a sua análise.

Essa alteração não afeta as métricas de entrega. Essa alteração afeta somente o filtro padrão mostrado na exibição de relatórios. Como o RPV é a métrica mais usada entre os clientes, esse padrão foi selecionado para simplificar os workflows de relatórios. Você pode alternar para outras métricas a qualquer momento na seção [!UICONTROL Relatórios].