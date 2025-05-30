---
keywords: relatório;relatórios;relatório;solução da experience cloud;fuso horário;fuso horário;moeda;excluir IPs;aumento estimado na receita;receita;aumento na receita;prioridades otimizadas;otimizado
description: Use [!DNL Target], [!DNL Adobe Analytics], or [!DNL Adobe Customer Journey Analytics] como fonte de relatórios, especifique o fuso horário e o formato da moeda padrão, adicione endereços IP a serem excluídos dos relatórios e muito mais.
title: Como configurar relatórios no  [!DNL Target]?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: 3e2682acdf8c7be86285c901ddcdae0f43b647f2
workflow-type: tm+mt
source-wordcount: '761'
ht-degree: 22%

---

# Configurar relatórios em [!DNL Target]

Defina as configurações gerais a serem usadas nos relatórios do [!DNL Adobe Target] que se aplicam a toda a sua conta do [!DNL Target].

{{permissions-update}}

Para acessar a página de configuração [!UICONTROL Reporting], clique em **[!UICONTROL Administration]** > **[!UICONTROL Reporting].**

Você pode especificar as seguintes configurações nesta página:

* A solução da Adobe Experience Cloud para usar em relatórios
* O fuso horário a ser usado para relatórios
* A moeda a ser usada para relatórios
* Endereços IP a serem excluídos dos relatórios
* Mostrar ou não a elevação estimada na receita em relatórios
* Se as prioridades otimizadas devem ser habilitadas

>[!NOTE]
>
>Esteja ciente de que o fuso horário, a moeda e os endereços IP para excluir as configurações se aplicam às atividades que usam os relatórios do [!DNL Target]. Estas configurações não se aplicam a atividades que usam o [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) ou o [!DNL Customer Journey Analytics] como fonte de relatórios.

![Página de relatórios](/help/main/administrating-target/assets/reporting.png)

## Solução da Reporting Cloud {#solution}

Defina as opções que determinam quais dados são usados para os resultados e relatórios.

Selecione a fonte de relatórios das suas atividades: [!DNL Target], [!DNL Adobe Analytics] ou [!DNL Adobe Customer Journey Analytics]. Você também pode optar por selecionar a fonte de relatórios por atividade como parte do fluxo de trabalho guiado de três partes ao criar a atividade.

Considere as informações a seguir ao escolher sua origem de relatórios:

* **[!DNL Adobe Target]**: Se a fonte de relatórios for definida aqui como **[!DNL Target]**, você não poderá criar ou ativar uma atividade que usa [!DNL Analytics] ou [!DNL Customer Journey Analytics] como fonte de relatórios. Você deve alterar a fonte de relatórios para **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Analytics]**: Se a fonte de relatórios for definida aqui como **[!DNL Analytics]**, você não poderá criar ou ativar uma atividade que usa [!DNL Target] ou [!DNL Customer Journey Analytics] como fonte de relatórios. Você deve alterar a fonte de relatórios para **[!UICONTROL Select per activity]**.
* **[!DNL Adobe Customer Journey Analytics]**: Se a fonte de relatórios for definida aqui como **[!DNL Customer Journey Analytics]**, você não poderá criar ou ativar uma atividade que usa [!DNL Target] ou [!DNL Analytics] como fonte de relatórios. Você deve alterar a fonte de relatórios para **[!UICONTROL Select per activity]**.
* **Selecionar por atividade**: se a fonte de relatórios estiver definida aqui como **[!UICONTROL Select per activity]**, você poderá criar e ativar atividades compatíveis com a fonte de relatórios selecionada.

Ao determinar sua fonte de geração de relatórios, considere as seguintes informações:

* **[!DNL Analytics]**: Para obter uma matriz de atividades com suporte usando [!DNL Analytics] como fonte de relatórios (A4T), consulte [Tipos de atividades com suporte](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) no *Adobe Analytics como fonte de relatórios do Adobe Target (A4T)*.

  A criação e a ativação de atividades de [!UICONTROL Automated Personalization] (AP) são permitidas independentemente da fonte de relatórios selecionada. Não há suporte para atividades [!UICONTROL Automated Personalization] ao escolher [Adobe Analytics como fonte de relatórios para o Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

  Mesmo que você especifique [!DNL Analytics] como fonte de geração de relatórios, [!DNL Target] será usado como fonte de relatórios para [!DNL Automated Personalization] atividades.

* **[!DNL Customer Journey Analytics]**: Para obter uma matriz de atividades com suporte usando os relatórios [!DNL Target] em [!DNL Customer Journey Analytics], consulte [Tipos de atividades com suporte](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md#supported-activities) em *[!DNL Target]relatórios em[!DNL Adobe Customer Journey Analytics]*.

  Criação e ativação de atividades de [!UICONTROL Automated Personalization] (AP), [!UICONTROL Auto-Allocate] e [!UICONTROL Auto-Target] são permitidas independentemente da fonte de relatórios selecionada. Estas atividades não são suportadas quando você escolhe a [Adobe Customer Journey Analytics como fonte de relatórios](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md).

  Mesmo que você especifique [!DNL Customer Journey Analytics] como fonte de geração de relatórios, [!DNL Target] será usado como fonte de relatórios para [!DNL Automated Personalization] atividades.

  Se você especificar [!DNL Customer Journey Analytics] como fonte de relatórios para atividades de [!UICONTROL Auto-Allocate] ou [!UICONTROL Auto-Target], [!DNL Target] ou [!DNL Analytics] poderá ser usado como fonte de relatórios.

## Fuso horário para relatórios

Especifique o fuso horário a ser usado para relatórios.

## Moeda para relatórios

Especifique a moeda a ser usada para relatórios.

## IPs a serem excluídos dos dados de relatório de [!DNL Target]

Especifique os endereços IP que deseja excluir dos dados de relatório. Por exemplo, excluir endereços internos da empresa é uma boa maneira de garantir que os dados de relatórios reflitam as interações do cliente no seu site.

Insira cada endereço IP em uma nova linha.

## Mostrar aumento estimado na receita

Você pode optar por mostrar o aumento estimado na receita se inserir um valor monetário para sua meta. [!DNL Target]O pode fazer uma estimativa do aumento de receita que você obterá se todos os usuários visualizarem a experiência vencedora. O recurso de aumento estimado está desativado por padrão.

Apenas [!DNL Experience Cloud] usuários administradores podem habilitar ou desabilitar este recurso. Se uma estimativa de aumento for desabilitada, os campos correspondentes não aparecerão na interface. Desabilitar o recurso não resulta em perda de dados, inclusive os dados usados para as estimativas. As estimativas são baseadas em dados coletados independentemente de o recurso estar habilitado ou não.

Para obter informações detalhadas, consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Ativar prioridades otimizadas

Permitir entradas numéricas para prioridades que variam de 0 a 999.

Dependendo das configurações, a interface do usuário e as opções de Prioridade variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.
