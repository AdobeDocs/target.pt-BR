---
description: Várias configurações podem ser usadas para descrever e controlar uma atividade do Recommendations.
keywords: Recommendations, Configurações, nome, objetivo, prioridade, duração, configurações de relatórios, outros metadados
seo-description: Várias configurações podem ser usadas para descrever e controlar uma atividade do Recommendations no Adobe Target.
seo-title: Configurações de atividade do Recommendations no Adobe Target
solution: Target
subtopic: Recommendations
title: Configurações de atividade do Recommendations
title-outputclass: premium
topic: Premium
uuid: 7c66d0e8-cecf-4d0d-8c62-5347a7d80a53
badge: premium
translation-type: tm+mt
source-git-commit: e8e6dcadf307209abcc712798b714af0a5be2e7e

---


# ![PREMIUM](/help/assets/premium.png) Configurações de atividade do Recommendations{#recommendations-activity-settings}

Informações sobre as configurações que podem ser usadas para descrever e controlar uma atividade do [!UICONTROL Recommendations].

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

Se especificar um nome de atividade do [!UICONTROL Recommendations] que já existe para outra atividade no [!UICONTROL Recommendations Classic], a nova atividade será ressincronizada com um novo nome. O novo nome é o nome original anexado com um carimbo de data e hora que o torna exclusivo. O novo nome é exibido no Target Standard/Premium e no [!UICONTROL Recommendations Classic].

## Objetivo

(Opcional) Descreva a meta da atividade.

## Prioridade

Ajuste o controle deslizante para determinar o nível de prioridade.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.

## Duração

Defina a duração da atividade.

A atividade pode começar quando ativada ou você pode definir uma data e hora específicas. Da mesma maneira, a atividade não pode terminar quando é desativada, ou você pode definir uma data e hora. O seletor de hora usa um relógio de 24 horas, sendo 00h a meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o.

## Configurações da geração de relatórios

* **Fonte de relatórios:** Selecione a fonte de relatórios: Adobe Target ou [Analytics](/help/c-integrating-target-with-mac/a4t/a4t.md). Não altere a fonte de relatórios depois que a atividade entrar em execução. Alterar a fonte de relatórios após uma atividade ficar ativa causa relatórios inconsistentes.
* **Métrica de objetivo:** Selecione a métrica de sucesso que determina se a atividade foi bem-sucedida.
* **Métricas adicionais:** configure métricas de sucesso adicionais para serem usadas nos relatórios.
* **Públicos-alvo para relatórios:** defina o público-alvo que pode ser usado ao filtrar os relatórios.

## Outros metadados

Insira observações sobre a atividade.

## Vídeo de treinamento: configurações da atividade (3:02)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

>[!VIDEO](https://video.tv.adobe.com/v/17381?captions=por_br)