---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: Use [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] as the reporting source, specify the default time zone and currency format, add IP addresses to exclude from reporting, and more.
title: How Do I Configure Reporting in [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: 12831d6584acc482db415629d7e70a18e39c47c2
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 22%

---

# Configure reporting in [!DNL Target]

Configure general settings to use in [!DNL Adobe Target] reporting that apply to your entire [!DNL Target] account.

{{permissions-update}}

Para acessar a página de configuração [!UICONTROL Reporting], clique em **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

Você pode especificar as seguintes configurações nesta página:

* A solução da Adobe Experience Cloud para usar em relatórios
* O fuso horário a ser usado para relatórios
* A moeda a ser usada para relatórios
* Endereços IP a serem excluídos dos relatórios
* Whether to show estimated lift in revenue in reporting
* Whether to enable fine-grained priorities

>[!NOTE]
>
>Be aware that the time zone, currency, and IP addresses to exclude settings apply to activities that use [!DNL Target] reporting. These settings do not apply to activities that use [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) or [!DNL Customer Journey Analytics] as the reporting source.

![Reporting page](/help/main/administrating-target/assets/reporting.png)

## Solução da Reporting Cloud {#solution}

Defina as opções que determinam quais dados são usados para os resultados e relatórios.

Selecione a fonte de relatórios das suas atividades: [!DNL Target], [!DNL Adobe Analytics] ou [!DNL Adobe Customer Journey Analytics]. Você também pode optar por selecionar a fonte de relatórios por atividade como parte do fluxo de trabalho guiado de três partes ao criar a atividade.

Considere as informações a seguir ao escolher sua origem de relatórios:

* **[!DNL Adobe Target]**: Se a fonte de relatórios for definida aqui como **[!DNL Target]**, você não poderá criar ou ativar uma atividade que usa [!DNL Analytics] ou [!DNL Customer Journey Analytics] como fonte de relatórios. Você deve alterar a fonte de relatórios para **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Analytics]**: Se a fonte de relatórios for definida aqui como **[!DNL Analytics]**, você não poderá criar ou ativar uma atividade que usa [!DNL Target] ou [!DNL Customer Journey Analytics] como fonte de relatórios. Você deve alterar a fonte de relatórios para **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Customer Journey Analytics]**: Se a fonte de relatórios for definida aqui como **[!DNL Customer Journey Analytics]**, você não poderá criar ou ativar uma atividade que usa [!DNL Target] ou [!DNL Analytics] como fonte de relatórios. Você deve alterar a fonte de relatórios para **[!UICONTROL Select per activity]**.
* **Select per activity**: If the reporting source is set to **[!UICONTROL Select per activity]** here, you can create and activate activities that are supported by the selected reporting source.

When determining your reporting source, consider the following information:

* **[!DNL Analytics]**: Para obter uma matriz de atividades com suporte usando [!DNL Analytics] como fonte de relatórios (A4T), consulte [Tipos de atividades com suporte](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) no *Adobe Analytics como fonte de relatórios do Adobe Target (A4T)*.

  A criação e a ativação de atividades de [!UICONTROL Automated Personalization] (AP) são permitidas independentemente da fonte de relatórios selecionada. Não há suporte para atividades [!UICONTROL Automated Personalization] ao escolher [Adobe Analytics como fonte de relatórios para o Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

  Mesmo que você especifique [!DNL Analytics] como fonte de geração de relatórios, [!DNL Target] será usado como fonte de relatórios para [!DNL Automated Personalization] atividades.

* **[!DNL Customer Journey Analytics]**: Para obter uma matriz de atividades com suporte usando os relatórios [!DNL Target] em [!DNL Customer Journey Analytics], consulte [Tipos de atividades com suporte](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities) em *[!DNL Target]relatórios em[!DNL Adobe Customer Journey Analytics]*.

  Criação e ativação de atividades de [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] são permitidas independentemente da fonte de relatórios selecionada. Estas atividades não são suportadas quando você escolhe a [Adobe Customer Journey Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

  Mesmo que você especifique [!DNL Customer Journey Analytics] como fonte de geração de relatórios, [!DNL Target] será usado como fonte de relatórios para [!DNL Automated Personalization] atividades.

  If you specify [!DNL Customer Journey Analytics] as your reporting source for [!UICONTROL Auto-Allocate] or [!UICONTROL Auto-Target] activities, [!DNL Target] or [!DNL Analytics] can be used as the reporting source.

## Timezone for Reporting

Specify the time zone to use for reporting.

## Currency for Reporting

Especifique a moeda a ser usada para relatórios.

## IPs a serem excluídos dos dados de relatório de [!DNL Target]

Especifique os endereços IP que deseja excluir dos dados de relatório. Por exemplo, excluir endereços internos da empresa é uma boa maneira de garantir que os dados de relatórios reflitam as interações do cliente no seu site.

Insira cada endereço IP em uma nova linha.

## Mostrar aumento estimado na receita

You can choose to show the estimated lift in revenue if you enter a monetary value for your goal. [!DNL Target]O pode fazer uma estimativa do aumento de receita que você obterá se todos os usuários visualizarem a experiência vencedora. O recurso de aumento estimado está desativado por padrão.

Only [!DNL Experience Cloud] Admin users can enable or disable this feature. Se uma estimativa de aumento for desabilitada, os campos correspondentes não aparecerão na interface. Desabilitar o recurso não resulta em perda de dados, inclusive os dados usados para as estimativas. As estimativas são baseadas em dados coletados independentemente de o recurso estar habilitado ou não.

Para obter informações detalhadas, consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Ativar prioridades otimizadas

Permitir entradas numéricas para prioridades que variam de 0 a 999.

Depending on your settings, the UI and options for Priority  vary. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.
