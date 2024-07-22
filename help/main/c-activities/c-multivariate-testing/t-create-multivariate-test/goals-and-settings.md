---
keywords: configurações de atividade;metas e configurações;multivariado;activity settings;goals and settings;multivariate;mvt
description: Saiba como usar a página [!UICONTROL Goals & Settings] em  [!DNL Adobe Target]  para especificar informações sobre as metas de uma atividade de [!UICONTROL Multivariate Test] (MVT).
title: Como Especificar Metas e Configurações em uma Atividade de [!UICONTROL Multivariate Test] (MVT)?
feature: Multivariate Tests
exl-id: 823a1435-ccb9-4357-9c33-a0968d704b7a
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 41%

---

# Metas e Configurações ([!UICONTROL Multivariate Test])

A página [!UICONTROL Goals & Settings] em [!DNL Adobe Target] é onde você insere informações sobre as metas de suas atividades do [!UICONTROL Multivariate Test] (MVT).

As seguintes seções estão disponíveis:

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

As configurações disponíveis em cada seção dependem se você usa [!DNL Target] ou [!DNL Analytics] como a fonte de relatórios.

## Configurações de atividade {#section_DCBDC354261F420EBD4B43EA34947BAC}

As seguintes configurações estão disponíveis:

### Objetivo

Digite um objetivo opcional. O objetivo pode ser qualquer informação que ajuda você e os membros da sua equipe a identificarem a campanha.

### Prioridade

Dependendo das configurações, a interface do usuário do [!DNL Target] e as opções para [!UICONTROL Priority] variam. Você pode usar as configurações herdadas de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou pode habilitar prioridades otimizadas de 0 a 999.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.

Se esta opção não estiver habilitada em [!UICONTROL Administration] > [!UICONTROL Reporting] (padrão), especifique uma prioridade: [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High].

Para habilitar prioridades otimizadas, clique em [!UICONTROL Administration] > [!UICONTROL Reporting] e alterne a opção [!UICONTROL Enable Fine-Grained Priorities] para a posição &quot;Ativado&quot;.

Se esta opção estiver ativada, especifique um valor de 0 a 999:

* 0 = Baixo
* 999 = Alto

Para atividades criadas em versões anteriores do [!DNL Target], a prioridade [!UICONTROL Low] é convertida para 0, a prioridade [!UICONTROL Medium] é convertida para 5 e a prioridade [!UICONTROL High] é convertida para 10. É possível ajustar esses valores conforme necessário.

>[!NOTE]
>
>Antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10.

### Duração

A atividade pode começar quando aprovada ou você pode definir data e hora específicas. Da mesma maneira, a atividade não pode terminar quando é desativada, ou você pode definir uma data e hora. O seletor de hora usa um relógio de 24 horas, sendo 00h a meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o.

## Configurações da geração de relatórios {#section_13119392051044FBA6387D9B3B1C43CF}

As seguintes configurações estão disponíveis:

### Fonte de geração de relatórios

Especificar de qual solução os dados são coletados:

* [!DNL Adobe Target]
* [!DNL Adobe Analytics]
* [!DNL Adobe Customer Journey Analytics]

Se uma solução de relatório for especificada nas [configurações da conta](/help/main/administrating-target/reporting.md), a solução especificada será usada e essa configuração não ficará visível.

Não é possível alterar sua fonte de relatórios após a atividade entrar em vigor para manter os relatórios consistentes.

**[!DNL Adobe Analytics]**: Consulte [[!DNL Adobe Analytics] como fonte de relatórios para [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para saber mais sobre as diferenças entre as soluções de relatórios e as vantagens de cada uma.

Ao selecionar [!DNL Analytics] como fonte de relatórios para [!DNL Target] (A4T), você seleciona um conjunto de relatórios [!DNL Analytics] para receber dados de atividade de [!DNL Target]. Para fazer isso, primeiro escolha uma das [!DNL Analytics] empresas vinculadas à sua conta e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para conexão com [!DNL Target] estão disponíveis para seleção. Se você não vir o conjunto de relatórios esperado, primeiro tente fazer logoff e depois fazer logon novamente no [!DNL Adobe Experience Cloud] para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, contate o [Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

O [!DNL Analytics for Target] (A4T) requer um servidor de rastreamento para relatar os resultados corretamente. Um servidor de rastreamento padrão é exibido no campo [!UICONTROL Tracking Server]. Se você usar mais de um servidor de rastreamento, inclua o servidor de rastreamento correto neste campo. Consulte [Usando um servidor de rastreamento do Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obter mais informações.

**[!DNL Adobe Customer Journey Analytics]**: Consulte [[!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obter mais informações sobre a integração entre [!DNL Adobe Customer Journey Analytics] e [!DNL Target].

### Métrica de objetivo

Selecione a ação executada por um visitante para atingir a meta. Por exemplo, escolha uma métrica [!UICONTROL Conversion] e defina os parâmetros que determinam quando o sucesso é obtido.

>[!NOTE]
>
>Se a solução de relatório for definida como [!DNL Analytics], a única métrica de meta disponível será [!UICONTROL Conversion]. [!DNL Analytics] métricas não podem ser selecionadas como uma meta.

Quando você selecionar sua métrica de sucesso, um seletor será exibido. Use esse seletor para escolher as especificações da métrica de sucesso.

Se estiver habilitado, o campo [!UICONTROL Estimated Value of the Conversion] (não disponível para as métricas [!UICONTROL Page Score]) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] e [!UICONTROL Orders]), a estimativa usa [!UICONTROL Revenue per Visitor]. O tipo de dados é a moeda.

Após atingir o objetivo da atividade, um visitante continua vendo o conteúdo da atividade, a menos que o visitante esteja qualificado para uma atividade de prioridade mais alta. Se o visitante atingir o objetivo novamente, será contado como outra conversão. Esse comportamento é diferente do comportamento padrão em [!DNL Target Classic], que conta os visitantes como novos se visualizarem o teste novamente.

### Métricas adicionais

Crie métricas de sucesso adicionais.

Esta configuração não estará disponível se a solução de relatório estiver definida como [!DNL Analytics]. Nesse caso, as métricas definidas para o conjunto de relatórios [!DNL Analytics] são aplicadas.

### Públicos-alvo para geração de relatórios

Por padrão, os relatórios mostram os resultados para todos os visitantes qualificados. Você pode incluir públicos-alvo do relatório para mostrar apenas informações sobre públicos-alvo específicos.

### Configurações avançadas {#section_E2FE441AFB324E498793ABB025ED9974}

As configurações avançadas estão disponíveis para [!UICONTROL Multivariate Test] métricas de meta.

![Menu Configurações avançadas](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/Menu_AdvancedSettings.png)

>[!NOTE]
>
>Se você usa o [!DNL Adobe Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. A opção de configurações avançadas não está disponível.

#### Qual métrica de sucesso deve ser atingida antes do aumento dessa métrica?

Use essa opção para contar apenas alguém que atingiu a métrica de sucesso se já tiver atingido uma métrica de sucesso diferente. Por exemplo, uma conversão de teste só pode ser válida se o visitante clicar na oferta ou acessar uma página específica antes da conversão.

É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada.

Defina ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra.

A opção [!UICONTROL Add Dependency] permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada.

Para adicionar uma dependência:

1. Depois de adicionar outras métricas, clique em **[!UICONTROL Advanced Settings]**.
2. Clique na opção **[!UICONTROL Add Dependency]**:

   ![Adicionar dependência](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency.png)

3. Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em **[!UICONTROL Reached]** para alternar a configuração entre Alcançado e Não alcançado.

   ![Dependência atingida](/help/main/c-activities/c-multivariate-testing/t-create-multivariate-test/assets/add_dependency_reached.png)

É possível editar ou remover dependências depois de adicioná-las.

### O que acontece depois que um usuário atinge esta métrica de meta?

Há três opções para o que acontece depois que um visitante atinge a métrica de meta:

* [!UICONTROL Select Increment Count & Keep User in Activity] para especificar como a contagem é incrementada.
* [!UICONTROL Select Increment Count, Release User & Allow Reentry] para especificar a experiência que o usuário vê ao entrar na atividade novamente.
* [!UICONTROL Select Increment Count, Release User & Bar from Reentry] para especificar o que o usuário vê em vez do conteúdo da atividade.

Consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) para obter mais informações sobre configurações avançadas.

## Outros metadados {#section_2E8917BEFB954480A4206B9E9E917F80}

A seguinte configuração está disponível:

### Notas

Digite quaisquer informações sobre sua atividade que sejam úteis para você mesmo ou para outros membros da equipe. O painel [!UICONTROL Notes] é redimensionável.

## Vídeos de treinamento

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### Configurações de atividade (3:02)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

>[!VIDEO](https://video.tv.adobe.com/v/17381)

### Criação de testes multivariados (9:25)

Este vídeo demonstra como criar um teste multivariado usando o fluxo de trabalho guiado de três etapas do [!DNL Target]. Metas e configurações são discutidas a partir de 7:00.

* Definir e projetar um teste multivariado
* Criar um teste multivariado

>[!VIDEO](https://video.tv.adobe.com/v/17395)
