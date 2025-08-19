---
keywords: configurações de atividade, metas e configurações de direcionamento da experiência, metas e configurações xt, direcionamento da experiência, configurações de relatórios, métricas de meta, métricas de sucesso, métricas dependentes de sucesso, configurações avançadas, meta principal, métricas adicionais, objetivo, prioridade, duração, solução de relatórios, meta, públicos-alvo para relatórios, qual métrica de sucesso deve ser alcançada antes de incremento dessa métrica, o que acontecerá após o usuário encontrar essa métrica de meta, observações
description: Saiba como usar a página [!UICONTROL Goals & Settings] no  [!DNL Adobe Target]  para especificar informações sobre as metas de uma atividade do [!UICONTROL Experience Targeting] (XT).
title: Como Especificar [!UICONTROL Goals & Settings] em uma Atividade [!UICONTROL Experience Targeting]?
feature: Experience Targeting
exl-id: 80cb7eff-4e9c-43d7-a3d8-7a9de79c91b9
source-git-commit: af8291a27e62a588046f66f20f8d3a47c8af0a18
workflow-type: tm+mt
source-wordcount: '1147'
ht-degree: 38%

---

# Metas e Configurações nas atividades de [!UICONTROL Experience Targeting] (XT)

A página [!UICONTROL Goals & Settings] é onde você insere informações sobre as metas do teste:

* [!UICONTROL Activity Settings]
* [!UICONTROL Reporting Settings]
* [!UICONTROL Other Metadata]

As configurações disponíveis dependem se você usa [!DNL Target] ou [!DNL Analytics] como a fonte de relatórios.

## [!UICONTROL Activity Settings] {#section_DCBDC354261F420EBD4B43EA34947BAC}

As seguintes configurações estão disponíveis:

### [!UICONTROL Objective]

Digite um objetivo opcional. O objetivo pode ser qualquer informação que ajuda você e os membros da sua equipe a identificarem a campanha.

### [!UICONTROL Priority]

Dependendo das configurações, a interface do usuário do [!DNL Target] e as opções para [!UICONTROL Priority] variam. Você pode usar as configurações herdadas de [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High], ou pode habilitar prioridades otimizadas de 0 a 999.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.

Se esta opção não estiver habilitada em [!UICONTROL Administration] (padrão), especifique uma prioridade: [!UICONTROL Low], [!UICONTROL Medium] ou [!UICONTROL High].

Para habilitar prioridades otimizadas, clique em **[!UICONTROL Administration]** > **[!UICONTROL Reporting]** e alterne a opção [!UICONTROL Enable Fine-Grained Priorities] para a posição &quot;Ativado&quot;.

Se esta opção estiver ativada, especifique um valor de 0 a 999:

* 0 = Baixo
* 999 = Alto

Para atividades criadas em versões anteriores do [!DNL Target], a prioridade [!UICONTROL Low] é convertida para 0, [!UICONTROL Medium] é convertida para 5 e [!UICONTROL High] é convertida para 10. É possível ajustar esses valores conforme necessário.

>[!NOTE]
>
>Antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10.

### [!UICONTROL Duration]

A atividade pode começar quando aprovada ou você pode definir data e hora específicas. Da mesma forma, a atividade pode terminar quando é desativada ou você pode definir uma data e hora para a atividade terminar. O seletor de hora usa um relógio de 24 horas, sendo 00:00 meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o.

## [!UICONTROL Reporting Settings] {#section_13119392051044FBA6387D9B3B1C43CF}

As seguintes configurações estão disponíveis:

### [!UICONTROL Reporting Source]

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

### [!UICONTROL Goal Metric]

Selecione a ação executada por um visitante para atingir a meta. Por exemplo, escolha uma métrica [!UICONTROL Conversion] e defina os parâmetros que determinam quando o sucesso é obtido.

Para obter mais informações sobre como configurar métricas, consulte [Definir métricas](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-set-metrics.md#task_A04AB66007C1467DA1C21A519A5C7BEB).

>[!NOTE]
>
>Se a solução de relatório for definida como [!DNL Analytics], a única métrica de meta disponível será [!UICONTROL Conversion]. [!DNL Analytics] métricas não podem ser selecionadas como uma meta.

Quando você selecionar sua métrica de sucesso, um seletor será exibido. Use esse seletor para escolher as especificações da métrica de sucesso.

Se estiver habilitado, o campo [!UICONTROL Estimated Value of the Conversion] (não disponível para métricas [!UICONTROL Page Score]) fornece um valor para a meta, mas não para outras métricas. Este valor permite que o [!DNL Target] calcule a estimativa de aumento da receita. Este campo é opcional, mas a receita incremental para qualquer métrica que não seja de receita não pode ser calculada sem ele. Para todas as métricas de receita ([!UICONTROL Revenue per Visitor], [!UICONTROL Average Order Value], [!UICONTROL Total Sales] e [!UICONTROL Orders]), a estimativa usa [!UICONTROL Revenue per Visitor]. O tipo de dados é a moeda.

Após atingir o objetivo da atividade, um visitante continua vendo o conteúdo da atividade, a menos que o visitante esteja qualificado para uma atividade de prioridade mais alta. Se o visitante atingir o objetivo novamente, será contado como outra conversão. Esse comportamento é diferente do comportamento padrão em [!DNL Target Classic], que contava os visitantes como novos se eles vissem o teste novamente.

### [!UICONTROL Additional Metrics]

Crie métricas de sucesso adicionais.

Esta configuração não estará disponível se a solução de relatório estiver definida como [!DNL Analytics]. Nesse caso, as métricas definidas para o conjunto de relatórios [!DNL Analytics] são aplicadas.

### [!UICONTROL Audiences for Reporting]

Por padrão, os relatórios mostram os resultados para todos os visitantes qualificados. Você pode incluir públicos-alvo do relatório para mostrar apenas informações sobre públicos-alvo específicos.

Esta configuração não estará disponível se você escolher [!DNL Analytics] como sua solução de relatório. A audiência definida para o conjunto de relatórios [!DNL Analytics] é aplicada.

## [!UICONTROL Other Meta Data]

Digite quaisquer informações sobre sua atividade que sejam úteis para você mesmo ou para outros membros da equipe. O painel [!UICONTROL Notes] é redimensionável.

## [!UICONTROL Advanced Settings] {#section_E2FE441AFB324E498793ABB025ED9974}

As configurações avançadas estão disponíveis para [!UICONTROL Experience Targeting] métricas de meta.

![Configurações avançadas](/help/main/c-activities/t-experience-target/t-xt-create/assets/Menu_AdvancedSettings-new.png)

>[!NOTE]
>
>Se você usa o [!DNL Analytics] como a fonte de geração de relatórios, as configurações são gerenciadas pelo servidor do [!DNL Analytics]. Opção [!UICONTROL Advanced Settings] não disponível.

As seguintes configurações estão disponíveis:

### [!UICONTROL Which success metric must be reached before incrementing this metric?]

Use essa opção para contar apenas os visitantes que atingiram a métrica de sucesso se já tiverem atingido uma métrica de sucesso diferente. Por exemplo, uma conversão de teste só pode ser válida se o visitante clicar na oferta ou acessar uma página específica antes da conversão.

É possível fornecer dependência em várias métricas, juntamente com a flexibilidade para escolher se a métrica deve ser alcançada ou não para que a contagem seja incrementada.

Você deve definir ambas as métricas de sucesso (ou várias) para poder tornar uma dependente da outra.

A opção [!UICONTROL Add Dependency] permite que a métrica de sucesso seja incrementada se outra métrica de sucesso for ou não alcançada.

Para adicionar uma dependência:

1. Depois de adicionar outras métricas, clique em **[!UICONTROL Advanced Settings]**.
2. Clique em **[!UICONTROL Add Dependency]**:

   ![Link Adicionar dependência](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency-new.png)

3. Arraste e solte as métricas desejadas do painel esquerdo para o painel direito e clique em **[!UICONTROL Reached]** para alternar a configuração entre [!UICONTROL Reached] e [!UICONTROL Not Reached].

   ![Caixa de diálogo Adicionar dependência de métricas](/help/main/c-activities/t-experience-target/t-xt-create/assets/add_dependency_reached-new.png)

É possível editar ou remover dependências depois de adicioná-las.

### [!UICONTROL What will happen after a user encounters this goal metric?]

Há três opções para o que acontece depois que um visitante atinge a métrica de meta:

* Selecione [!UICONTROL Increment Count & Keep User in Activity] para especificar como a contagem é incrementada.
* Selecione [!UICONTROL Increment Count, Release User & Allow Reentry] para especificar a experiência que o usuário vê ao entrar na atividade novamente.
* Selecione [!UICONTROL Increment Count, Release User & Bar from Reentry] para especificar o que o usuário vê em vez do conteúdo da atividade.

Consulte [Métricas de sucesso](/help/main/c-activities/r-success-metrics/success-metrics.md#reference_D011575C85DA48E989A244593D9B9924) para obter mais informações sobre configurações avançadas.

## Vídeo de treinamento: configurações da atividade (3:02)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

>[!VIDEO](https://video.tv.adobe.com/v/17381)
