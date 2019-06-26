---
description: Crie públicos-alvo somente de atividades dentro do fluxo de trabalho orientado de três etapas ao criar uma atividade. Esses públicos-alvo podem ser usados em outros locais na mesma atividade, mas não são armazenados na Biblioteca de público-alvo para uso em outras atividades.
keywords: público-alvo, regras de público-alvo, criar público-alvo, criação de público-alvo, somente atividade, adhoc
seo-description: Crie públicos-alvo somente de atividade a partir do fluxo de trabalho guiado de três etapas do Adobe Target ao criar uma atividade. Esses públicos-alvo podem ser usados em outros locais na mesma atividade, mas não são armazenados na Biblioteca de público-alvo para uso em outras atividades.
seo-title: Criar um público-alvo com apenas uma atividade no Adobe Target
solution: Target
title: Criar um público-alvo com apenas uma atividade
topic: Advanced,Standard,Classic
uuid: 3d0898d0-96e8-4bc9-86bd-3ae39db0e74d
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Criar um público-alvo com apenas uma atividade{#create-an-activity-only-audience}

Crie públicos-alvo somente de atividades dentro do fluxo de trabalho orientado de três etapas ao criar uma atividade. These ad hoc audiences can be used in other places within the same activity, but are not stored in the [!UICONTROL Audiences Library] for use in other activities.

Públicos-alvo somente atividade proporcionam os seguintes benefícios:

* You can use activity-only audiences to create an audience that you want to use only once and you do not want to store it in the [!UICONTROL Audiences Library]. This prevents the [!UICONTROL Audiences Library] from being cluttered with audiences that you never want to use again.
* Activity-only audiences are not visible in the [!UICONTROL Audiences Library]. Por conta disso, elas são protegidas contra alterações indesejada por outros em sua organização.

1. While creating an [activity](../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03), on the **[!UICONTROL Target]** page, click the three vertical ellipses, then click **[!UICONTROL Replace Audience]**.

   ![Resultado da etapa](assets/edit_audience.png)

1. On the [!UICONTROL Choose Audience] page, click **[!UICONTROL Activity Only Audience]**.

   ![](assets/activity-only-aud.png)

1. Clique em **[!UICONTROL Criar público-alvo]**.
1. Digite um nome de público-alvo descritivo.
1. Clique em **[!UICONTROL + Adicionar regra]**.

   As regras possibilitam a limitação do seu público-alvo a um subconjunto dos visitantes do seu site.

1. Selecione um tipo de regra.

   Cada tipo de regra tem seus próprios parâmetros. Consulte [Categorias para públicos-alvo](../c-target/c-audiences/c-target-rules/target-rules.md#concept_E3A77E42F1644503A829B5107B20880D) para mais informações sobre a configuração de cada tipo de regra de público-alvo.

1. Defina os parâmetros da regra.
1. Clique em **[!UICONTROL Salvar]**.

## Considerações

Tenha em mente as informações a seguir enquanto você trabalha com públicos somente-atividades:

* É possível criar públicos-alvo somente atividade no Visual Experience Composer ou no Experience Composer baseado em formulário. Esta funcionalidade substitui regras de refinamento em versões anteriores do Target.
* You can create an activity to store in the [!UICONTROL Audience Library] for reuse in other activities or you create an activity-only audience. Depois de salvar o público-alvo, não é possível mudar o tipo de público-alvo.
* Os refinamentos das atividades existentes são migrados para públicos-alvo somente atividade.
* Activity-only audiences have a status of [!UICONTROL Used] or [!UICONTROL Unused]. Públicos-alvo somente atividade não utilizados são exibidos até que a atividade seja salva. Se deixados não utilizados e você tentar salvar a atividade, uma mensagem de alerta é exibida informando que públicos-alvo somente atividade não utilizados serão excluídos.
* É possível ver os detalhes da definição de público-alvo em um cartão pop-up acessado do seletor de público-alvo sem abrir o público-alvo.
* Você pode [combinar vários públicos](../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5) para criar públicos somente atividade.

