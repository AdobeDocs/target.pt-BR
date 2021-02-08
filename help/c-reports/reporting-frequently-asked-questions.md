---
keywords: solução de problemas;discrepâncias de métricas;FAQ;relatórios;novo visitante;novos visitantes;retornar visitante;retornar visitantes;retornar visita;nova visita
description: Explore uma lista de perguntas frequentes e respostas sobre o relatórios Adobe Target.
title: Onde posso encontrar respostas para perguntas sobre o Público alvo?
feature: Reports
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '1135'
ht-degree: 29%

---


# Perguntas frequentes de geração de relatórios{#reporting-faq}

Lista de perguntas frequentes sobre relatórios no [!DNL Target].

## Como as métricas Novos Visitantes e Visitantes de Retorno são contadas?

As informações a seguir explicam como Novos Visitantes e Visitantes de Retorno são contados e fornecem exemplos de por que a soma desses dois segmentos nem sempre soma ao número total de visitantes.

### Novos visitantes

Um visitante é incluído no segmento Novos Visitantes se uma das seguintes condições for atendida:

* É a primeira vez que o visitante visita o site.
* É a primeira vez que o visitante visita o site desde a limpeza dos cookies.
* É a primeira vez que o visitante visita o site desde que [duração do perfil do Visitante](/help/c-target/c-visitor-profile/visitor-profile-lifetime.md) expirou.

### Visitantes que retornam

O visitante é incluído no segmento Visitantes recorrentes se o usuário visitou o site anteriormente, saiu por pelo menos 30 minutos e retornou ao site novamente com os mesmos cookies. Desde que o visitante retorne dentro da duração do perfil, será um visitante recorrente.

Suponha que a duração do seu perfil seja definida para 14 dias (o padrão). Um visitante é incluído no segmento Visitantes de retorno se as seguintes condições forem atendidas:

* Um visitante visita o site pela primeira vez e é registrado como um Novo Visitante.
* O visitante deixa o site, mas retorna seis dias depois.

Como a duração do perfil é definida para 14 dias, esse visitante é incluído no segmento Visitantes de retorno. Observe que se o visitante tiver excluído cookies dentro desse período de seis dias, esse visitante será incluído no segmento Novos Visitantes.

### Exemplos que explicam discrepâncias entre contagens de métricas

**Exemplo 1**: Se esses dois segmentos forem aplicados a uma atividade, o segmento Novos Visitantes e o segmento Visitantes de Retorno nem sempre serão adicionados ao número total de visitantes.

Considere o exemplo a seguir, considerando as condições mencionadas acima para Novos Visitantes e Visitantes de Retorno:

* Um visitante visita o site pela primeira vez e é contado como um Novo Visitante.
* O visitante retorna ao site depois que as condições são atendidas para Visitantes de retorno e é contado como um Visitante de retorno.

Esse visitante é contado como um único visitante na contagem geral de visitantes da atividade, mesmo sendo contado nos segmentos Novos Visitantes e Visitantes de Retorno.

**Exemplo 2**: As discrepâncias entre as contagens de Novos Visitantes e Visitantes de Retorno também dependem de como você configura as métricas [ de ](/help/c-activities/r-success-metrics/success-metrics.md)sucesso de atividade.

Por exemplo:

Vários visitantes novos visitam seu site e estão qualificados para uma atividade. Esses novos visitantes são contados para o segmento Novos Visitantes. Todos esses visitantes também registraram uma visita àquela atividade.

Alguns visitantes acessaram a métrica de conversão, que foi configurada como &quot;Aumentar a contagem e manter o usuário na Atividade&quot;. Suponha que alguns desses usuários acessem a métrica de conversão várias vezes, a métrica de conversão não aumentará. Entretanto, considerando essa configuração, alguns usuários podem atingir a métrica de conversão e, em seguida, navegar de volta para o home page, se qualificando para a atividade novamente para gravar uma nova visita.

## Por que os relatórios de [!UICONTROL Direcionamento de experiência] (XT) contêm métricas para controlar experiências?

As atividades de XT devem sempre ter uma experiência de controle. Se você estiver usando uma atividade de XT de maneira semelhante a uma atividade de [!UICONTROL Teste A/B], que é um cenário bastante comum, os dados da experiência de controle são úteis. Você pode ignorar os dados da experiência de controle se não forem úteis nos relatórios.

## Por que os números de visitas são menores no [!DNL Target] do que em outras soluções da [!DNL Adobe Experience Cloud]? {#section_7E626FDB417E41B8B58BBF30FB207409}

Os números métricos, por exemplos, visitas, informados pelo [!DNL Target] sempre serão menores que os números informados em outras soluções da [!DNL Experience Cloud] por vários motivos:

* O [!DNL Target] conta visitas somente para visitantes que se qualificaram para a atividade. Outra soluções contam as visitas de visitantes que exibem a página, independentemente de qual atividade os levou à página.
* Pode haver situações em que diferentes atividades competem pelo mesmo local (mutuamente exclusivo). Como resultado, os visitantes visualizam diferentes conteúdos em uma página da Web, afetando os números de métrica informados pelo [!DNL Target].

## Por que não há dados disponíveis para o meu relatório de atividade? {#section_E4722F6445884130951DF79981C8289B}

Se um conteúdo de atividade foi entregue com sucesso aos usuários, mas o relatório não contiver dados, verifique se você selecionou o ambiente correto ([grupo de hosts](/help/administrating-target/hosts.md)) nas configurações do relatório.

Se você tem um ambiente de desenvolvimento selecionado, pode ver a seguinte mensagem de erro: &quot;Não há dados disponíveis para as configurações de relatório selecionadas&quot;.

Para alterar o ambiente de um relatório de atividade:

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista, em seguida, clique na guia **[!UICONTROL Relatórios.]**
1. Clique no ícone de engrenagem para configurar o relatório.

   ![Caixa de diálogo Configurações A/B](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >O ícone de engrenagem não está disponível para os relatórios de [!UICONTROL Automated Personalization] (AP).

1. Na lista suspensa **[!UICONTROL Ambiente]**, selecione **[!UICONTROL Produção]**.

   Os dados de relatório podem não estar disponíveis se você tem um ambiente de desenvolvimento selecionado.

1. Clique em **[!UICONTROL Salvar]**.

Para obter mais informações sobre os ambientes, consulte [Hosts](/help/administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

## Por que a divisão de tráfego entre minhas experiências é irregular na minha atividade A/B ou MVT? {#uneven}

Por exemplo, eu defini a divisão de tráfego como 50/50 ou 25/25/25/25, mas estou vendo uma distribuição muito diferente entre as experiências no relatórios. Há vários motivos explicáveis para contagens de visitantes irregulares no relatórios [!DNL Target]:

* Quando uma atividade [!DNL Target] é iniciada pela primeira vez, a distribuição do tráfego pode ser irregular devido à arquitetura do nó da borda que [!DNL Target] usa para otimizar o delivery da experiência. A melhor prática é dar a uma atividade algum tempo para coletar dados adicionais e a distribuição se normalizará. Para obter mais informações sobre a arquitetura [!DNL Adobe Target] e nós de Borda, consulte [Como a Adobe Target funciona](/help/c-intro/how-target-works.md).
* Se você estiver em [!DNL Target] ou [!DNL Analytics] e estiver usando a métrica **[!UICONTROL Visitas]**, lembre-se de que [!DNL Target] é um sistema baseado em visitante e a distribuição de tráfego para um teste A/B ou MVT é atribuída no nível do visitante. Portanto, se você examinar os resultados da atividade usando a métrica **[!UICONTROL Visitas]**, a distribuição do tráfego pode parecer irregular, pois determinados visitantes podem ter várias visitas. Visitantes é a métrica de normalização padrão ao avaliar o desempenho da atividade.
* A prática recomendada para testes A/B e MVT é manter as divisões de tráfego uniformes. Alterar a distribuição do tráfego entre experiências (por exemplo, de 10/90 para 50/50) durante um teste pode levar a visitantes desiguais entre experiências. A menor experiência de tráfego pode nunca &quot;alcançar&quot;.
* Se você estiver seguindo as práticas recomendadas acima e a divisão de tráfego não normalizar ao longo do tempo, verifique o seguinte:

   * Você está usando a biblioteca mais recente do at.js? Para obter mais informações sobre a versão atual e as notas de versão associadas, consulte [detalhes da versão do at.js](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md).

   * É um teste de redirecionamento? A sincronização incorreta das tags acionadas na página pode resultar em divisões de tráfego desiguais, especialmente ao usar [!DNL Analytics] como fonte de dados para uma atividade [!DNL Target]. Para obter detalhes sobre como corrigir a distribuição irregular de tráfego em uma atividade de redirecionamento com o Analytics para Público alvo (A4T), consulte [Redirecionar ofertas - Perguntas frequentes sobre A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
