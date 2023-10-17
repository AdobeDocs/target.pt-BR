---
keywords: relatório;relatórios;relatório;solução da experience cloud;fuso horário;fuso horário;moeda;excluir IPs;aumento estimado na receita;receita;aumento na receita;prioridades otimizadas;otimizado
description: Uso [!DNL Target] Para o Adobe Analytics como fonte de relatórios, especifique o fuso horário e o formato da moeda padrão, adicione endereços IP a serem excluídos dos relatórios e muito mais.
title: Como configurar relatórios no Target?
feature: Administration & Configuration
role: Admin
exl-id: fd83e60e-64a6-4d0e-909f-480d13bac32b
source-git-commit: d414f1554e1875e873f1ce557a7edf86b88ee79e
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 32%

---

# Configurar relatórios no Target

Definir as configurações gerais a serem usadas no [!DNL Adobe Target] relatórios que se aplicam a todo o seu [!DNL Target] conta.

Para acessar o [!UICONTROL Relatórios] configuração, clique em **[!UICONTROL Administração]** > **[!UICONTROL Relatórios].**

Você pode especificar as seguintes configurações nesta página:

* A solução da Adobe Experience Cloud para usar em relatórios
* O fuso horário a ser usado para relatórios
* A moeda a ser usada para relatórios
* Endereços IP a serem excluídos dos relatórios
* Mostrar ou não a elevação estimada na receita em relatórios
* Se as prioridades otimizadas devem ser habilitadas

>[!NOTE]
>
>Esteja ciente de que o fuso horário, a moeda e os endereços IP para excluir as configurações se aplicam às atividades que usam o [!DNL Target] relatórios. Essas configurações não se aplicam a atividades que usam [Analytics for Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md) como fonte de relatórios.

![Página de relatórios](/help/main/administrating-target/assets/reporting.png)

## Solução da Reporting Cloud {#solution}

Defina as opções que determinam quais dados são usados para os resultados e relatórios.

Selecione a fonte de relatórios das suas atividades: o [!DNL Target] ou o [!DNL Adobe Analytics]. Também é possível optar por selecionar sua origem de relatórios por atividade.

Considere as informações a seguir ao escolher sua origem de relatórios:

* Se a origem de relatório for definida aqui para **[!DNL Target]**, você não poderá ativar uma atividade que usa o como a origem de relatório. [!DNL Analytics] Você deve alterar a origem de relatórios para [!DNL Target] na atividade ou altere a fonte de relatórios para **[!UICONTROL Selecionar por atividade]** in **[!UICONTROL Administração] > [!UICONTROL Relatórios]**.
* Se a fonte de relatórios estiver definida como **[!DNL Analytics]** aqui, você não tem permissão para ativar uma atividade que usa [!DNL Target] como fonte de relatórios (a fonte de relatórios é especificada como **[!UICONTROL Target por atividade])**. Você deve alterar a origem de relatórios para [!DNL Analytics] na atividade ou altere o mecanismo de relatórios para **[!UICONTROL Selecionar por atividade]** in **[!UICONTROL Administração] > [!UICONTROL Relatórios]**.
* Se a fonte de relatórios estiver definida como **[!UICONTROL Selecionar por atividade]** aqui, você pode criar, ativar e desativar atividades compatíveis com a fonte de relatórios selecionada. Para obter uma matriz de atividades compatíveis, consulte [Tipos de atividades compatíveis](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics como origem de relatório do Adobe Target (A4T)*.
* [!UICONTROL Automated Personalization] A criação, ativação e desativação de atividades (AP) são permitidas independentemente da fonte de relatórios selecionada. As atividades do Automated Personalization não são compatíveis quando você escolhe [Adobe Analytics como origem de relatório do Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md). Mesmo que você especifique [!DNL Analytics] como sua fonte de geração de relatórios, [!DNL Target] é usada como a fonte de relatórios para atividades do Automated Personalization. Para obter mais informações, consulte [Tipos de atividades compatíveis](/help/main/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) in *Adobe Analytics como origem de relatório do Adobe Target (A4T)*.

## Fuso horário para relatórios

Especifique o fuso horário a ser usado para relatórios.

## Moeda para relatórios

Especifique a moeda a ser usada para relatórios.

## IPs a serem excluídos do [!DNL Target] dados de relatórios

Especifique os endereços IP que deseja excluir dos dados de relatório. Por exemplo, excluir endereços internos da empresa é uma boa maneira de garantir que os dados de relatórios reflitam as interações do cliente no seu site.

Insira cada endereço IP em uma nova linha.

## Mostrar aumento estimado na receita

Você pode optar por mostrar o aumento estimado na receita se inserir um valor monetário para sua meta. [!DNL Target]O pode fazer uma estimativa do aumento de receita que você obterá se todos os usuários visualizarem a experiência vencedora. O recurso de aumento estimado está desativado por padrão.

Somente [!DNL Experience Cloud] Usuários administradores podem ativar ou desativar esse recurso. Se uma estimativa de aumento for desabilitada, os campos correspondentes não aparecerão na interface. Desabilitar o recurso não resulta em perda de dados, inclusive os dados usados para as estimativas. As estimativas são baseadas em dados coletados independentemente de o recurso estar habilitado ou não.

Para obter informações detalhadas, consulte [Aumento estimado na receita](/help/main/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Ativar prioridades otimizadas

Permitir entradas numéricas para prioridades que variam de 0 a 999.

Dependendo das configurações, a interface do usuário e as opções de Prioridade variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.
