---
keywords: solução de problemas, discrepâncias de métricas, FAQ, relatórios, novo visitante, novos visitantes, visitante recorrente, visitantes recorrentes, visita de retorno, nova visita
description: Explore uma lista de perguntas e respostas frequentes sobre o Adobe [!DNL Target] relatórios.
title: Onde posso encontrar respostas para perguntas sobre [!DNL Target] Relatando?
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: 719eb95049dad3bee5925dff794871cd65969f79
workflow-type: tm+mt
source-wordcount: '1227'
ht-degree: 32%

---

# Perguntas frequentes de geração de relatórios

Lista de perguntas frequentes sobre relatórios no [!DNL Adobe Target].

## Como são contadas as métricas Novos visitantes e Visitantes recorrentes? {#methodology}

A primeira visita de um novo visitante dura, desde que o visitante esteja ativo no site.
Se o usuário estiver inativo por 30 minutos ou mais, a sessão será redefinida. Redefinir a sessão significa que esse visitante se torna um Visitante de retorno na próxima visita ou se torna ativo novamente após 30 minutos de inatividade.
Se o visitante se mover pelo site a cada 29 minutos por um dia inteiro, esse visitante será contado como um Novo visitante durante o dia inteiro. A sessão nunca foi redefinida porque o visitante nunca ultrapassou o limite de 30 minutos.

As informações a seguir explicam com mais detalhes como são contados Novos visitantes e Visitantes recorrentes. Os exemplos também são incluídos explicando por que a soma desses dois segmentos nem sempre adiciona ao número total de visitantes.

### Novos visitantes

Um visitante é incluído no segmento Novos visitantes se uma das seguintes condições for atendida:

* É a primeira vez que o visitante acessa o site.
* É a primeira vez que o visitante acessa o site desde a limpeza dos cookies.
* É a primeira vez que o visitante acessa o site desde que expiração do [tempo de vida do perfil do visitante.](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md)

### Visitantes que retornam

O visitante é incluído no segmento Visitante recorrente se o usuário tiver visitado o site antes, sair dele por pelo menos 30 minutos, e retornar com os mesmos cookies. Desde que o visitante retorne dentro da duração do perfil, ele será um visitante recorrente.

Suponha que a duração do seu perfil esteja definida para 14 dias (o padrão). Um visitante é incluído no segmento Visitantes recorrentes se as seguintes condições forem atendidas:

* Um visitante visita o site pela primeira vez e é registrado como um Novo visitante.
* O visitante deixa o site, mas retorna seis dias depois.

Como a duração do perfil é definida para 14 dias, esse visitante é incluído no segmento Visitantes recorrentes. Se o visitante tiver excluído cookies dentro desse período de seis dias, esse visitante será incluído no segmento Novos visitantes .

### Exemplos que explicam as discrepâncias entre as contagens de métrica

**Exemplo 1**: Se esses dois segmentos forem aplicados a uma atividade, o segmento Novos visitantes e o segmento de Visitantes recorrentes nem sempre somam ao número total de visitantes.

Considere o exemplo a seguir, considerando as condições mencionadas acima para Novos visitantes e Visitantes recorrentes:

* Um visitante visita o site pela primeira vez e é contado como um novo visitante.
* O visitante volta ao site depois que as condições são atendidas para Visitantes recorrentes e é contado como um Visitante recorrente.

Esse visitante é contado como um único visitante na contagem geral de visitantes da atividade, mesmo sendo contado nos segmentos de Novos visitantes e Visitantes recorrentes.

**Exemplo 2**: As discrepâncias entre as contagens para Novos visitantes e Visitantes recorrentes também dependem de como você configura o [métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md).

Por exemplo:

Vários novos visitantes visitam seu site e estão qualificados para uma atividade. Esses novos visitantes são contados no segmento Novos visitantes . Todos esses visitantes também registraram uma visita nessa atividade.

Alguns visitantes acessaram a métrica de conversão, que foi configurada como &quot;Aumentar a contagem e manter o usuário na atividade&quot;. Suponha que alguns desses usuários acessem a métrica de conversão várias vezes, a métrica de conversão não aumente. Considerando essa configuração, no entanto, alguns usuários podem atingir a métrica de conversão e depois navegar de volta para a página inicial, se qualificando para a atividade novamente para registrar uma nova visita.

## Por que os relatórios de [!UICONTROL Direcionamento de experiência] (XT) contêm métricas para controlar experiências?

As atividades de XT devem sempre ter uma experiência de controle. Se você estiver usando uma atividade de XT de maneira semelhante a uma atividade de [!UICONTROL Teste A/B], que é um cenário bastante comum, os dados da experiência de controle são úteis. Você pode ignorar os dados da experiência de controle se não forem úteis nos relatórios.

## Por que os números de visitas são menores no [!DNL Target] do que em outras soluções da [!DNL Adobe Experience Cloud]?  {#section_7E626FDB417E41B8B58BBF30FB207409}

Números de métrica, por exemplo, visitas, relatados por [!DNL Target] são sempre inferiores aos números relatados em outros [!DNL Experience Cloud] soluções por vários motivos:

* O [!DNL Target] conta visitas somente para visitantes que se qualificaram para a atividade. Outra soluções contam as visitas de visitantes que exibem a página, independentemente de qual atividade os levou à página.
* Pode haver situações em que diferentes atividades competem pelo mesmo local (mutuamente exclusivo). Como resultado, os visitantes visualizam diferentes conteúdos em uma página da Web, afetando os números de métrica informados pelo [!DNL Target].

## Por que não há dados disponíveis para o meu relatório de atividade? {#section_E4722F6445884130951DF79981C8289B}

Se um conteúdo de atividade foi entregue com sucesso aos usuários, mas o relatório não contiver dados, verifique se você selecionou o ambiente correto ([grupo de hosts](/help/main/administrating-target/hosts.md)) nas configurações do relatório.

Se você tem um ambiente de desenvolvimento selecionado, pode ver a seguinte mensagem de erro: &quot;Não há dados disponíveis para as configurações de relatório selecionadas&quot;.

Para alterar o ambiente de um relatório de atividade:

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista, em seguida, clique na guia **[!UICONTROL Relatórios.]**
1. Clique no ícone de engrenagem para configurar o relatório.

   ![Caixa de diálogo Configurações A/B](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >O ícone de engrenagem não está disponível para os relatórios de [!UICONTROL Automated Personalization] (AP).

1. Na lista suspensa **[!UICONTROL Ambiente]**, selecione **[!UICONTROL Produção]**.

   Os dados de relatório podem não estar disponíveis se você tem um ambiente de desenvolvimento selecionado.

1. Clique em **[!UICONTROL Salvar]**.

Para obter mais informações sobre os ambientes, consulte [Hosts](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

## Por que a divisão de tráfego entre minhas experiências é desigual na minha atividade A/B ou MVT? {#uneven}

Por exemplo, defini a divisão de tráfego para 50/50 ou 25/25/25/25, mas estou vendo uma distribuição muito diferente entre experiências nos relatórios. Há vários motivos explicáveis para contagens desiguais de visitantes em [!DNL Target] relatórios:

* Quando uma [!DNL Target] for iniciada pela primeira vez, a distribuição de tráfego pode ser desigual devido à arquitetura do nó de borda que [!DNL Target] O usa o para otimizar a entrega da experiência. A prática recomendada é dar a uma atividade algum tempo para coletar mais dados e a distribuição normalizará. Para obter mais informações sobre [!DNL Adobe Target] arquitetura e nós do Edge, consulte [Como o Adobe Target funciona](/help/main/c-intro/how-target-works.md).
* Se você estiver em [!DNL Target] ou [!DNL Analytics] e você está usando o **[!UICONTROL Visitas]** , lembre-se [!DNL Target] é um sistema baseado em visitantes e a distribuição de tráfego de um teste A/B ou MVT é atribuída no nível do visitante. Assim, se você examinar os resultados da atividade usando o **[!UICONTROL Visitas]** , a distribuição do tráfego pode parecer irregular, pois alguns visitantes podem ter várias visitas. Visitantes é a métrica padrão de normalização ao avaliar o desempenho da atividade.
* A prática recomendada para testes A/B e MVT é manter as divisões de tráfego equilibradas. Alterar a distribuição do tráfego entre experiências (digamos de 10/90 a 50/50) durante um teste pode levar a visitantes desiguais em todas as experiências. A experiência de tráfego mais baixa pode nunca &quot;alcançar&quot;.
* Se você estiver seguindo as práticas recomendadas acima e a divisão de tráfego não normalizar ao longo do tempo, verifique o seguinte:

   * Você está usando a biblioteca at.js mais recente? Para obter mais informações sobre a versão atual e as notas de versão associadas, consulte [Detalhes da versão da at.js](https://developer.adobe.com/target/implement/client-side/atjs/target-atjs-versions/){target=_blank}.

   * É um teste de redirecionamento? O tempo incorreto de disparo de tags na página pode levar a divisões de tráfego desiguais, especialmente ao usar [!DNL Analytics] como a fonte de dados de um [!DNL Target] atividade . Para obter detalhes para corrigir a distribuição desigual de tráfego em uma atividade de redirecionamento com o Analytics for Target (A4T), consulte [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
