---
keywords: troubleshooting;metric discrepancies;FAQ;reports
description: Lista de perguntas frequentes sobre relatórios no Adobe Target.
title: Perguntas frequentes sobre relatórios do Adobe Target
topic: Standard
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 7b57ef37f2764f5ec58c9a090edc295e81fdaaa9
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 50%

---


# Perguntas frequentes de geração de relatórios{#reporting-faq}

Lista de perguntas frequentes sobre relatórios no [!DNL Target].

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

Para obter mais informações sobre os ambientes, consulte [Hosts](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).

## Por que a divisão de tráfego entre minhas experiências é irregular na minha atividade A/B ou MVT? {#uneven}

Por exemplo, eu defini a divisão de tráfego como 50/50 ou 25/25/25/25, mas estou vendo uma distribuição muito diferente entre as experiências no relatórios. Há vários motivos explicáveis para contagens de visitantes desiguais no [!DNL Target] relatórios:

* Quando uma [!DNL Target] atividade é iniciada pela primeira vez, a distribuição do tráfego pode ser irregular devido à arquitetura do nó da borda que [!DNL Target] usa para otimizar o delivery da experiência. A melhor prática é dar a uma atividade algum tempo para coletar dados adicionais e a distribuição se normalizará. Para obter mais informações sobre [!DNL Adobe Target] arquitetura e nós do Edge, consulte [Como o Público alvo da Adobe funciona](/help/c-intro/how-target-works.md).
* Se você estiver dentro [!DNL Target] ou [!DNL Analytics] estiver usando a métrica **[!UICONTROL Visitas]** , lembre-se de que [!DNL Target] é um sistema baseado em visitante e que a distribuição de tráfego para um teste A/B ou MVT é atribuída no nível do visitante. Assim, se você examinar os resultados da atividade usando a métrica **[!UICONTROL Visitas]** , a distribuição do tráfego pode parecer irregular, pois determinados visitantes podem ter várias visitas. Visitantes é a métrica de normalização padrão ao avaliar o desempenho da atividade.
* A prática recomendada para testes A/B e MVT é manter as divisões de tráfego uniformes. Alterar a distribuição do tráfego entre experiências (por exemplo, de 10/90 para 50/50) durante um teste pode levar a visitantes desiguais entre experiências. A menor experiência de tráfego pode nunca &quot;alcançar&quot;.
* Se você estiver seguindo as práticas recomendadas acima e a divisão de tráfego não normalizar ao longo do tempo, verifique o seguinte:

   * Você está usando a biblioteca mais recente do at.js? Para obter mais informações sobre a versão atual e as notas de versão associadas, consulte os detalhes [da versão do](/help/c-implementing-target/c-implementing-target-for-client-side-web/target-atjs-versions.md)at.js.

   * É um teste de redirecionamento? A sincronização incorreta das tags acionadas na página pode resultar em divisões de tráfego desiguais, especialmente ao usar [!DNL Analytics] como fonte de dados para uma [!DNL Target] atividade. Para obter detalhes sobre como corrigir a distribuição irregular de tráfego em uma atividade de redirecionamento com o Analytics for Público alvo (A4T), consulte Perguntas frequentes sobre [Redirecionamento de oferta - A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-redirect-offers.md).
