---
keywords: relatório;relatórios;relatórios;solução de nuvem de experiência;fuso horário;fuso horário;moeda;excluir IPs;aumento estimado na receita;aumento na receita;prioridades refinadas;com granulado fino
description: Defina as configurações gerais a serem usadas no relatórios Adobe Target que se aplicam a toda a sua conta de Público alvo. Você pode configurar a solução Adobe Experience Cloud para usar para o relatórios (Público alvo ou Analytics), o fuso horário e o formato de moeda a serem usados para o relatórios, os endereços IP para excluir do relatórios e se deve mostrar o aumento estimado na receita e as prioridades refinadas no relatórios.
title: Configurar Relatórios
feature: Administration & Configuration
translation-type: tm+mt
source-git-commit: 48b94f967252f5ddb009597456edf0a43bc54ba6
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 30%

---


# Configurar relatórios no Público alvo

Defina as configurações gerais a serem usadas no relatórios [!DNL Adobe Target] que se aplica a toda a sua conta [!DNL Target].

Para acessar a página de configuração [!UICONTROL Relatórios], clique em **[!UICONTROL Administração]** > **[!UICONTROL Relatórios].**

Você pode especificar as seguintes configurações nesta página:

* A solução Adobe Experience Cloud a ser usada para o relatórios
* O fuso horário a ser usado para o relatórios
* A moeda a ser usada para o relatórios
* Endereços IP a serem excluídos do relatórios
* Mostrar ou não o aumento estimado na receita no relatórios
* Se as prioridades refinadas devem ser ativadas

>[!NOTE]
>
>Observe que o fuso horário, a moeda e os endereços IP para excluir configurações se aplicam às atividades que usam o relatórios [!DNL Target]. Essas configurações não se aplicam a atividades que usam [Analytics para Público alvo (A4T)] como fonte de relatórios (/help/c-integrating-target-with-mac/a4t/a4t.md).

![página relatórios](/help/administrating-target/assets/reporting.png)

## Solução da Relatórios Cloud

Defina as opções que determinam quais dados são usados para os resultados e relatórios.

Selecione a fonte de relatórios das suas atividades: o [!DNL Target] ou o [!DNL Adobe Analytics]. Também é possível optar por selecionar sua origem de relatórios por atividade.

Considere as informações a seguir ao escolher sua origem de relatórios:

* Se a origem de relatório for definida aqui para **[!DNL Target]**, você não poderá ativar uma atividade que usa o como a origem de relatório. [!DNL Analytics] É necessário alterar a fonte do relatórios para [!DNL Target] na atividade ou alterar a fonte do relatórios para **[!UICONTROL Selecionar por atividade]** em **[!UICONTROL Administração] > [!UICONTROL Relatórios]**.
* Se a fonte do relatórios estiver definida como **[!DNL Analytics]** aqui, você não poderá ativar uma atividade que use [!DNL Target] como a fonte do relatórios (a fonte do relatórios é especificada como **[!UICONTROL Público alvo por atividade])**. É necessário alterar a fonte do relatórios para [!DNL Analytics] na atividade ou alterar o mecanismo do relatórios para **[!UICONTROL Selecionar por atividade]** em **[!UICONTROL Administração] > [!UICONTROL Relatórios]**.
* Se a fonte do relatórios estiver definida como **[!UICONTROL Selecione por atividade]** aqui, você poderá criar, ativar e desativar atividades compatíveis com a fonte do relatórios selecionada. Para obter uma matriz de atividades suportadas, consulte [Tipos de atividade suportados](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) em *Adobe Analytics como a fonte de relatórios para Adobe Target (A4t)*.
* [!UICONTROL A criação, a ativação e a desativação de atividades Automated Personalization] (AP) são permitidas independentemente da origem do relatórios selecionada. O Automated Personalization atividade não é suportado ao escolher [Adobe Analytics como a origem do relatórios para Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Mesmo se você especificar [!DNL Analytics] como sua fonte de relatórios, [!DNL Target] será usado como fonte de relatórios para o Automated Personalization atividade. Para obter mais informações, consulte [Tipos de atividade suportados](/help/c-integrating-target-with-mac/a4t/a4t.md#section_F487896214BF4803AF78C552EF1669AA) em *Adobe Analytics como a origem do relatórios para Adobe Target (A4t)*.

## Fuso horário do Relatórios

Especifique o fuso horário a ser usado para o relatórios.

## Moeda do Relatórios

Especifique a moeda a ser usada para o relatórios.

## IPs a serem excluídos dos dados do relatórios do Público alvo

Especifique quaisquer endereços IP que você deseja excluir dos dados do relatórios. Por exemplo, excluir endereços de empresa internos é uma boa maneira de garantir que seus dados de relatórios reflitam as interações do cliente em seu site.

Insira cada endereço IP em uma nova linha.

## Mostrar aumento estimado na receita

Você pode optar por mostrar o aumento estimado na receita se informar um valor monetário para sua meta. [!DNL Target]O pode fazer uma estimativa do aumento de receita que você obterá se todos os usuários visualizarem a experiência vencedora. O recurso de aumento estimado está desativado por padrão.

Somente [!DNL Experience Cloud] usuários administradores podem ativar ou desativar esse recurso. Se uma estimativa de aumento for desabilitada, os campos correspondentes não aparecerão na interface. Desabilitar o recurso não resulta em perda de dados, inclusive os dados usados para as estimativas. As estimativas são baseadas em dados coletados independentemente de o recurso estar habilitado ou não.

Para obter informações detalhadas, consulte [Aumento estimado na receita](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Ativar prioridades otimizadas

Permitir entradas numéricas para prioridades que variam de 0 a 999.

Dependendo das configurações, a interface do usuário e as opções de Prioridade variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.
