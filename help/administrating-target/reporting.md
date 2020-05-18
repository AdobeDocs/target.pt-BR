---
keywords: report;reports;reporting;experience cloud solution;timezone;time zone;currency;exclude IPs;estimated lift in revenue;revenue;lift in revenue;fine-grained priorities;fine-grained
description: Configure o Adobe Público alvo Visual Experience Composer (VEC) especificando suas configurações gerais, configuração do visor móvel e seletores de CSS.
title: Configurar relatórios no Adobe Público alvo
topic: Standard
translation-type: tm+mt
source-git-commit: 34c4c48602df8550287e86c535ebc350fe2185f7
workflow-type: tm+mt
source-wordcount: '648'
ht-degree: 69%

---


# Configurar relatórios no Público alvo

Defina as configurações gerais a serem usadas no relatórios do Público alvo que se aplicam a toda a sua [!DNL Target] conta.

Para acessar a página de configuração do [!UICONTROL Relatórios] , clique em **[!UICONTROL Administração]** > **[!UICONTROL Relatórios].**

Você pode especificar as seguintes configurações nesta página:

* A solução da Adobe Experience Cloud a ser usada para o relatórios
* O fuso horário a ser usado para o relatórios
* A moeda a ser usada para o relatórios
* Endereços IP a serem excluídos do relatórios
* Mostrar ou não o aumento estimado na receita no relatórios
* Se as prioridades refinadas devem ser ativadas

![página Relatórios](/help/administrating-target/assets/reporting.png)

## Solução da Relatórios Cloud

Defina as opções que determinam quais dados são usados para os resultados e relatórios.

Selecione a fonte de relatórios das suas atividades: o [!DNL Target] ou o Adobe Analytics. Também é possível optar por selecionar sua origem de relatórios por atividade.

Considere as informações a seguir ao escolher sua origem de relatórios:

* Criação, ativação e desativação de atividades de [!UICONTROL Alocação automática], [!UICONTROL Direcionamento automático] e [!UICONTROL Personalização automatizada] (AP) são permitidas independentemente da fonte de relatórios selecionada. Esses tipos de atividades não são compatíveis quando você escolhe o [Adobe Analytics como origem de relatórios para o Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md). Mesmo que você especifique o Analytics como fonte de geração de relatórios, [!DNL Target] será usado como a fonte de relatórios para esses tipos de atividades.
* Se a fonte de relatórios for definida aqui como Analytics, você não poderá ativar uma atividade que usa [!DNL Target] como fonte de relatórios (a fonte de relatórios é especificada como Target por atividade). Você deve alterar a origem de relatórios para Analytics na sua atividade ou alterar o mecanismo de relatórios para Selecionar por atividade em Configurar > Preferências.
* Se a origem de relatório for definida aqui para [!DNL Target], você não poderá ativar uma atividade que usa o Analytics como a origem de relatório. Você deve alterar a origem de relatórios para [!DNL Target] na sua atividade ou alterar a origem de relatório para Selecionar por atividade em Configurar > Preferências.
* Se a origem de relatório for definida aqui para Selecionar por atividade, você pode criar, ativar e desativar atividades compatíveis com a origem de relatório selecionada. Para obter uma matriz de atividades compatíveis, consulte [Adobe Analytics como origem de relatório para o Adobe Target](/help/c-integrating-target-with-mac/a4t/a4t.md) (A4T).
* Quando você alternar do manual A/B para [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático], todas as métricas e públicos-alvo serão perdidos se a origem de relatórios da atividade manual A/B não for compatível nas atividades de [!UICONTROL Alocação automática] ou [!UICONTROL Direcionamento automático].

## Fuso horário do Relatórios

Especifique o fuso horário a ser usado para o relatórios.

## Moeda do Relatórios

Especifique a moeda a ser usada para o relatórios.

## IPs a serem excluídos dos dados do relatórios do Público alvo

Especifique quaisquer endereços IP que você deseja excluir dos dados do relatórios. Por exemplo, excluir endereços de empresa internos é uma boa maneira de garantir que seus dados de relatórios reflitam as interações do cliente em seu site.

Insira cada endereço IP em uma nova linha.

## Mostrar aumento estimado na receita

Você pode optar por mostrar o aumento estimado na receita se informar um valor monetário para sua meta. [!DNL Target]O pode fazer uma estimativa do aumento de receita que você obterá se todos os usuários visualizarem a experiência vencedora. O recurso de aumento estimado está desativado por padrão.

Apenas usuários de Administração da Experience Cloud podem habilitar ou desabilitar esse recurso. Se uma estimativa de aumento for desabilitada, os campos correspondentes não aparecerão na interface. Desabilitar o recurso não resulta em perda de dados, inclusive os dados usados para as estimativas. As estimativas são baseadas em dados coletados independentemente de o recurso estar habilitado ou não.

Para obter informações detalhadas, consulte [Aumento estimado na receita](/help/administrating-target/r-target-account-preferences/estimating-lift-in-revenue.md).

## Ativar prioridades otimizadas

Permitir entradas numéricas para prioridades que variam de 0 a 999.

Dependendo das configurações, a interface do usuário e as opções de Prioridade variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.
