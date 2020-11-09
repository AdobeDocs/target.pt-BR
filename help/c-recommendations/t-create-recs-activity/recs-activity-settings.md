---
keywords: Recommendations;Settings;name;objective;priority;duration;reporting settings;other metadata
description: Várias configurações podem ser usadas para descrever e controlar uma atividade do Recommendations no Adobe Target.
title: Configurações de atividade do Recommendations no Adobe Target
feature: recs creation
translation-type: tm+mt
source-git-commit: 968d36d65016e51290f6bf754f69c91fd8f68405
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 89%

---


# ![PREMIUM](/help/assets/premium.png) Configurações de atividade do Recommendations{#recommendations-activity-settings}

Information about the settings you can use to describe and control a [!UICONTROL Recommendations] activity in [!DNL Adobe Target].

![Página Metas e configurações do Recommendations](/help/c-recommendations/t-create-recs-activity/assets/recs-settings.png)

As seções a seguir descrevem as configurações disponíveis para uma atividade do [!UICONTROL Recommendations].

## Nome

Forneça um nome descritivo que vai ajudar você e sua equipe a identificar a atividade.

Os seguintes caracteres não são permitidos em um nome de atividade:

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

Se especificar um nome de atividade do [!UICONTROL Recommendations] que já existe para outra atividade no [!UICONTROL Recommendations Classic], a nova atividade será ressincronizada com um novo nome. O novo nome é o nome original anexado com um carimbo de data e hora que o torna exclusivo. This new name is displayed in both [!DNL Target Standard/Premium] and [!UICONTROL Recommendations Classic].

## Objetivo

(Opcional) Descreva a meta da atividade.

## Prioridade

Ajuste o controle deslizante para determinar o nível de prioridade.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.

## Duração

Defina a duração da atividade.

A atividade pode começar quando aprovada ou você pode definir data e hora específicas. Da mesma maneira, a atividade não pode terminar quando é desativada, ou você pode definir uma data e hora. O seletor de hora usa um relógio de 24 horas, sendo 00h a meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o.

## Configurações da geração de relatórios

* **Fonte do relatórios:** Selecione a fonte do relatórios: [!DNL Adobe Target] ou [do Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md). Não altere a fonte de geração de relatórios após a atividade ficar ativa. Alterar a fonte de geração de relatórios após uma atividade ficar ativa gera relatórios inconsistentes.
* **Métrica de objetivo:** selecione a métrica de sucesso que determina se a atividade é bem sucedida.
* **Métricas adicionais:** configure métricas de sucesso adicionais para serem usadas nos relatórios.
* **Públicos-alvo para relatórios:** defina o público-alvo que pode ser usado ao filtrar os relatórios.

## Outros metadados

Insira observações sobre a atividade.

## Vídeo de treinamento: Configurações de atividade (3:02) ![Etiqueta do tutorial](/help/assets/tutorial.png)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

>[!VIDEO](https://video.tv.adobe.com/v/17381)