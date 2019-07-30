---
description: Lista de perguntas frequentes sobre relatórios no Target.
keywords: solução de problemas, discrepância de métricas, FAQ, relatórios
seo-description: Lista de perguntas frequentes sobre relatórios no Adobe Target.
seo-title: Perguntas frequentes sobre o relatório do Adobe Target
solution: Target
title: Perguntas frequentes de geração de relatórios
topic: Padrão
uuid: 0be40d3f-3274-493d-899b-cb7bb3612baf
translation-type: tm+mt
source-git-commit: a6f2eceaddf67653b36a1687ba071f7226169516

---


# Perguntas frequentes de geração de relatórios{#reporting-faq}

Lista de perguntas frequentes sobre relatórios no [!DNL Target].

## Why do my [!UICONTROL Experience Targeting] (XT) reports contain metrics for control experiences?

As atividades XT devem sempre ter uma experiência de controle. If you are using an XT activity in a similar manner to an [!UICONTROL A/B Test] activity, which is a fairly common scenario, the control experience data is useful. Você pode ignorar os dados de experiência de controle se não for útil em seus relatórios.

## Why are the number of visits lower in [!DNL Target] than in other [!DNL Adobe Experience Cloud] solutions? {#section_7E626FDB417E41B8B58BBF30FB207409}

Os números métricos, por exemplos, visitas, informados pelo [!DNL Target] sempre serão menores que os números informados em outras soluções da [!DNL Experience Cloud] por vários motivos:

* O [!DNL Target] conta visitas somente para visitantes que se qualificaram para a atividade. Outra soluções contam as visitas de visitantes que exibem a página, independentemente de qual atividade os levou à página.
* Pode haver situações em que atividades diferentes competem pelo mesmo local (mutuamente exclusivo). Como resultado, os visitantes visualizam diferentes conteúdos em uma página da Web, afetando os números de métrica informados pelo [!DNL Target].

## Por que não há dados disponíveis para o meu relatório de atividade? {#section_E4722F6445884130951DF79981C8289B}

If an activity's content was successfully delivered to users but its report contains no data, ensure that you have the correct environment ([host group](/help/administrating-target/hosts.md)) selected in the report's settings.

Se você tem um ambiente de desenvolvimento selecionado, pode ver a seguinte mensagem de erro: "Não há dados disponíveis para as configurações de relatório selecionadas".

Para alterar o ambiente de um relatório de atividade:

1. Clique em **[!UICONTROL Atividades]**, clique na atividade desejada da lista, em seguida, clique na guia **Relatórios[!UICONTROL .]**
1. Clique no ícone de engrenagem para configurar o relatório.

   ![Caixa de diálogo Configurações A/B](/help/c-reports/c-report-settings/assets/ab_settings_dialog.png)

   >[!NOTE]
   >
   >The gear icon is not available for [!UICONTROL Automated Personalization] (AP) reports.

1. Na lista suspensa **[!UICONTROL Ambiente]**, selecione **[!UICONTROL Produção]**.

   Os dados de relatório podem não estar disponíveis se você tem um ambiente de desenvolvimento selecionado.

1. Clique em **[!UICONTROL Salvar]**.

Para obter mais informações sobre os ambientes, consulte [Hosts](../administrating-target/hosts.md#concept_516BB01EBFBD4449AB03940D31AEB66E).
