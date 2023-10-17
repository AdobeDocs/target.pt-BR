---
keywords: solução de problemas;discrepâncias de métricas;FAQ;relatórios;novo visitante;novos visitantes;visitante recorrente;visitantes recorrentes;visita de retorno;nova visita
description: Veja uma lista de perguntas frequentes e respostas sobre o Adobe [!DNL Target] relatórios.
title: Onde posso encontrar respostas para perguntas sobre o [!DNL Target] Reportando?
feature: Reports
exl-id: 1a345a67-5050-4bd3-858d-99731d2c1dd3
source-git-commit: 5856bed8dd3bf59164c842eef687757f4e877bd5
workflow-type: tm+mt
source-wordcount: '1376'
ht-degree: 27%

---

# Perguntas frequentes de geração de relatórios

Lista de perguntas frequentes sobre relatórios no [!DNL Adobe Target].

## Como são contadas as métricas Novos visitantes e Visitantes recorrentes? {#methodology}

A primeira visita de um novo visitante dura, desde que o visitante esteja ativo no site.
Se o usuário estiver inativo por 30 minutos ou mais, a sessão será redefinida. Redefinir a sessão significa que esse visitante se torna um Visitante de retorno na próxima visita ou se torna ativo novamente após 30 minutos de inatividade.
Se o visitante se mover pelo site a cada 29 minutos por um dia inteiro, ele será contado como um Novo visitante nesse dia inteiro. A sessão nunca foi redefinida porque o visitante nunca ultrapassou o limite de 30 minutos.

As informações a seguir explicam em mais detalhes como Novos visitantes e Visitantes recorrentes são contados. Também são incluídos exemplos explicando por que a soma desses dois segmentos nem sempre soma o número total de visitantes.

### Novos visitantes

Um visitante é incluído no segmento Novos visitantes se uma das seguintes condições for atendida:

* É a primeira vez que o visitante acessa o site.
* É a primeira vez que o visitante acessa o site desde a limpeza dos cookies.
* É a primeira vez que o visitante acessa o site desde que [Tempo de vida do perfil do visitante](/help/main/c-target/c-visitor-profile/visitor-profile-lifetime.md) expirou.

### Visitantes que retornam

O visitante é incluído no segmento Visitante recorrente se o usuário tiver visitado o site antes, sair dele por pelo menos 30 minutos, e retornar com os mesmos cookies. Desde que o visitante retorne dentro da duração do perfil, ele será um visitante recorrente.

Suponha que a duração do seu perfil esteja definida para 14 dias (o padrão). Um visitante é incluído no segmento Visitantes recorrentes se as seguintes condições forem atendidas:

* Um visitante visita o site pela primeira vez e é registrado como um Novo visitante.
* O visitante sai do site, mas retorna seis dias depois.

Como a duração do perfil é definida para 14 dias, esse visitante é incluído no segmento Visitantes recorrentes. Se o visitante tiver excluído os cookies dentro desse período de seis dias, ele será incluído no segmento Novos visitantes.

### Exemplos que explicam discrepâncias entre contagens de métrica

**Exemplo 1**: se esses dois segmentos forem aplicados a uma atividade, o segmento Novos visitantes e o segmento Visitantes recorrentes nem sempre somam o número total de visitantes.

Considere o exemplo a seguir, considerando as condições mencionadas acima para Novos visitantes e Visitantes recorrentes:

* Um visitante visita o site pela primeira vez e é contado como um Novo visitante.
* O visitante retorna ao site depois que as condições são atendidas para Visitantes recorrentes e é contado como um Visitante recorrente.

Esse visitante é contado como um único visitante na contagem geral de visitantes da atividade, mesmo sendo contado nos segmentos Novos visitantes e Visitantes recorrentes.

**Exemplo 2**: as discrepâncias entre as contagens de Novos visitantes e Visitantes recorrentes também dependem de como você configura a variável [métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md).

Por exemplo:

Vários novos visitantes visitam seu site e são qualificados para uma atividade. Esses novos visitantes são contados no segmento Novos visitantes. Todos esses visitantes também registraram uma visita nessa atividade.

Alguns visitantes acessam a métrica de conversão, que foi configurada como &quot;Aumentar contagem e manter o usuário na atividade&quot;. Suponha que alguns desses usuários acessem a métrica de conversão várias vezes, a métrica de conversão não aumenta. Dada essa configuração, no entanto, alguns usuários podem atingir a métrica de conversão e navegar de volta para a página inicial, qualificando-se para a atividade novamente para registrar uma nova visita.

## Por que os relatórios de [!UICONTROL Direcionamento de experiência] (XT) contêm métricas para controlar experiências?

As atividades de XT devem sempre ter uma experiência de controle. Se você estiver usando uma atividade de XT de maneira semelhante a uma atividade de [!UICONTROL Teste A/B], que é um cenário bastante comum, os dados da experiência de controle são úteis. Você pode ignorar os dados da experiência de controle se não forem úteis nos relatórios.

## Por que os números de visitas são menores no [!DNL Target] do que em outras soluções da [!DNL Adobe Experience Cloud]?  {#section_7E626FDB417E41B8B58BBF30FB207409}

Números de métrica, por exemplo, visitas, informados por [!DNL Target] são sempre inferiores aos números relatados em outros [!DNL Experience Cloud] por vários motivos:

* O [!DNL Target] conta visitas somente para visitantes que se qualificaram para a atividade. Outra soluções contam as visitas de visitantes que exibem a página, independentemente de qual atividade os levou à página.
* Pode haver situações em que diferentes atividades competem pelo mesmo local (mutuamente exclusivo). Como resultado, os visitantes visualizam diferentes conteúdos em uma página da Web, afetando os números de métrica informados pelo [!DNL Target].

## Por que não há dados disponíveis para o meu relatório de atividade? {#section_E4722F6445884130951DF79981C8289B}

Se um conteúdo de atividade foi entregue com sucesso aos visitantes, mas o relatório não contiver dados, a seguinte mensagem de erro poderá ser exibida: &quot;Não há dados disponíveis para as configurações de relatório selecionadas&quot;.

Há alguns motivos possíveis para a ausência de dados nos relatórios de atividade:

* Você não tem o ambiente correto selecionado nas configurações do relatório
* Você não tem nenhum tráfego alocado para a experiência de controle

### Você não tem o ambiente correto selecionado nas configurações do relatório:

Se um conteúdo de atividade foi entregue com sucesso aos usuários, mas o relatório não contiver dados, verifique se você selecionou o ambiente correto ([grupo de hosts](/help/main/administrating-target/hosts.md)) nas configurações do relatório.

Para alterar o ambiente de um relatório de atividade:

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista, em seguida, clique na guia **[!UICONTROL Relatórios.]**
1. Clique no ícone de engrenagem para configurar o relatório.

   ![Caixa de diálogo Configurações A/B](/help/main/c-reports/c-report-settings/assets/ab_settings_dialog.png)

1. Na lista suspensa **[!UICONTROL Ambiente]**, selecione **[!UICONTROL Produção]**.

   Os dados de relatório podem não estar disponíveis se você tem um ambiente de desenvolvimento selecionado.

1. Clique em **[!UICONTROL Salvar]**.

Para obter mais informações sobre os ambientes, consulte [Hosts](/help/main/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

### Você não tem nenhum tráfego alocado para a experiência de controle

Se um conteúdo de atividade foi entregue com sucesso aos usuários, mas o relatório não contiver dados, certifique-se de usar uma experiência com tráfego como experiência de controle.

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista, em seguida, clique na guia **[!UICONTROL Relatórios.]**
1. Clique no ícone de engrenagem para configurar o relatório.

1. No **[!UICONTROL Controle]** selecione uma experiência que receba tráfego.

1. Clique em **[!UICONTROL Salvar]**.

>[!NOTE]
>
>Para obter mais informações sobre como atualizar uma [!UICONTROL Automated Personalization] e alterar a experiência de controle para uma experiência que recebe tráfego, consulte [Selecione o controle da atividade de Automated Personalization ou Direcionamento automático](/help/main/c-activities/t-automated-personalization/experience-as-control.md).


## Por que o tráfego é dividido entre minhas experiências de forma desigual na minha atividade de A/B ou MVT? {#uneven}

Por exemplo, eu defini a divisão de tráfego para 50/50 ou 25/25/25/25, mas estou vendo uma distribuição muito diferente entre as experiências nos relatórios. Há vários motivos explicáveis para contagens desiguais de visitantes em [!DNL Target] relatórios:

* Quando um [!DNL Target] for iniciada pela primeira vez, a distribuição de tráfego poderá ser desigual devido à arquitetura de nó de borda que [!DNL Target] O usa o para otimizar a entrega da experiência. A prática recomendada é dar a uma atividade algum tempo para coletar mais dados e a distribuição normalizará. Para obter mais informações sobre [!DNL Adobe Target] e nós Edge, consulte [Como o Adobe Target funciona](/help/main/c-intro/how-target-works.md).
* Se você estiver em [!DNL Target] ou [!DNL Analytics] e você estiver usando o **[!UICONTROL Visitas]** , lembre-se [!DNL Target] é um sistema baseado em visitantes e a distribuição de tráfego para um teste A/B ou MVT é atribuída no nível do visitante. Assim, se você examinar os resultados da atividade usando o **[!UICONTROL Visitas]** , a distribuição do tráfego pode parecer desigual porque alguns visitantes podem ter várias visitas. Visitantes é a métrica de normalização padrão ao avaliar o desempenho da atividade.
* A prática recomendada para testes A/B e MVT é manter as divisões de tráfego uniformes. Alterar a distribuição de tráfego entre experiências (por exemplo, de 90/10 para 50/50) durante um teste pode levar a visitantes desiguais entre experiências. A experiência de tráfego mais baixo pode nunca &quot;alcançar o topo&quot;.
* Se estiver seguindo as práticas recomendadas acima e a divisão de tráfego não normalizar ao longo do tempo, verifique o seguinte:

   * Você está usando a biblioteca at.js mais recente? Para obter mais informações sobre a versão atual e as notas de versão associadas, consulte [Detalhes da versão da at.js](https://experienceleague.corp.adobe.com/docs/target-dev/developer/client-side/at-js-implementation/target-atjs-versions.html?lang=pt-BR){target=_blank}.

   * É um teste de redirecionamento? O tempo incorreto de disparo de tags na página pode gerar divisões de tráfego desiguais, especialmente ao usar [!DNL Analytics] como a fonte de dados de um [!DNL Target] atividade. Para obter detalhes sobre como solucionar a distribuição de tráfego desigual em uma atividade de redirecionamento com o Analytics for Target (A4T), consulte [Ofertas de redirecionamento - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
