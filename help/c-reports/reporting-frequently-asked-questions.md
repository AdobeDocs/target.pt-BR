---
keywords: solução de problemas, discrepância de métricas, FAQ, relatórios
description: Lista de perguntas frequentes sobre relatórios no Adobe Target.
title: Perguntas frequentes sobre relatórios do Adobe Target
topic: Padrão
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: 217ca811521e67dcd1b063d77a644ba3ae94a72c

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

Se você tem um ambiente de desenvolvimento selecionado, pode ver a seguinte mensagem de erro: "Não há dados disponíveis para as configurações de relatório selecionadas".

Para alterar o ambiente de um relatório de atividade:

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista, em seguida, clique na guia **Relatórios[!UICONTROL .]**
1. Clique no ícone de engrenagem para configurar o relatório.

   ![Caixa de diálogo Configurações A/B](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >O ícone de engrenagem não está disponível para os relatórios de [!UICONTROL Automated Personalization] (AP).

1. Na lista suspensa **[!UICONTROL Ambiente]**, selecione **[!UICONTROL Produção]**.

   Os dados de relatório podem não estar disponíveis se você tem um ambiente de desenvolvimento selecionado.

1. Clique em **[!UICONTROL Salvar]**.

Para obter mais informações sobre os ambientes, consulte [Hosts](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
