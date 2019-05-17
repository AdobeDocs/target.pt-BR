---
description: Este tópico contém respostas para as perguntas mais frequentes sobre a configuração de atividades e o uso do Analytics como origem de geração de relatórios para o Target (A4T).
keywords: perguntas frequentes; perguntas frequentes; analytics for target; a4T; configuração de atividades
seo-description: Este tópico contém respostas para as perguntas mais frequentes sobre a configuração de atividades e o uso do Analytics como origem de geração de relatórios para o Target (A4T).
seo-title: Configurações de atividade - Perguntas frequentes sobre o A4T
solution: Target
title: Configurações de atividade - Perguntas frequentes sobre o A4T
topic: Padrão
uuid: 3472ab3c-908b-40f8-81a6-512dccde64a6
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Configurações de atividade - Perguntas frequentes sobre o A4T{#activity-settings-a-t-faq}

Este tópico contém respostas para as perguntas mais frequentes sobre a configuração de atividades e o uso do Analytics como origem de geração de relatórios para o Target (A4T).

## Quais tipos de atividade são compatíveis com o Analytics como fonte de geração de relatórios (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

Para obter uma lista completa, consulte &quot;Tipos de atividade suportados&quot; no [Adobe Analytics como a Fonte de relatórios do Adobe Target (A4T)](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Acabei de criar um atividade. Por que não vejo nenhum dado chegando? {#section_9F8092BE4225442896F926540292F221}

Quando uma atividade é criada, o Target envia um arquivo de classificação ao Analytics. Embora o Analytics esteja capturando e processando os dados, eles não são exibidos nos relatórios até que o arquivo de classificação tenha sido atualizado. Isso pode levar até 24 horas. Se depois de 48 horas você não visualizar seus dados, [entre em contato com o Atendimento ao Cliente](https://marketing.adobe.com/resources/help/en_US/target/target/r_problem.html). Alternativamente, se você sabe que vai iniciar uma atividade, você pode criar a atividade alguns dias antes e as classificações serão enviadas quando a atividade for salva. Dessa forma, os dados aparecem nos relatórios logo no início. Observe que leva de 45 a 90 minutos para que os dados sejam processados no Analytics.

## Por que não consigo selecionar o Analytics como minha fonte de geração de relatórios quando eu crio uma nova atividade? {#section_9F4F69C3085F4C2480AF439127EB27CD}

Você pode alterar suas opções de Configurações de relatório em Configurar.

1. No Adobe Target, clique em **[!UICONTROL Configurar]**.
1. Na solução **[!UICONTROL Experience Cloud usada para a lista suspensa de]** relatórios, clique em **[!UICONTROL Selecionar por atividade]**.

![](assets/select-per-activity.png)

A lista suspensa de **[!UICONTROL Fonte de geração de relatório]** está habilitada na tela **Meta e configurações]para criar e editar atividades.[!UICONTROL **

Para sempre usar o Analytics como fonte de geração de relatório, selecione **[!UICONTROL Adobe Analytics]na lista suspensa em Configurar.**
