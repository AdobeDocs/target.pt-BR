---
keywords: faq;frequently asked questions;analytics for target;a4T;activity setup
description: Este tópico contém respostas para as perguntas mais frequentes sobre a configuração de atividades e o uso do Analytics como origem de geração de relatórios para o Target (A4T).
title: Configurações de atividade - Perguntas frequentes sobre o A4T
feature: a4t troubleshooting
topic: Standard
uuid: 3472ab3c-908b-40f8-81a6-512dccde64a6
translation-type: tm+mt
source-git-commit: e203dc94e9bb34c4090f5795cbf73869808ada88
workflow-type: tm+mt
source-wordcount: '285'
ht-degree: 89%

---


# Configurações de atividade - Perguntas frequentes sobre o A4T{#activity-settings-a-t-faq}

Este tópico contém respostas para as perguntas mais frequentes sobre a configuração de atividades e o uso do Analytics como origem de geração de relatórios para o Target (A4T).

## Quais tipos de atividade são compatíveis com o Analytics como fonte de geração de relatórios (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

Para obter uma lista completa, consulte &quot;Tipos de atividade suportados&quot; no [Adobe Analytics como a Fonte de relatórios do Adobe Target (A4T)](../../../c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Acabei de criar um atividade. Por que não vejo nenhum dado chegando?  {#section_9F8092BE4225442896F926540292F221}

Quando uma atividade é criada, o Target envia um arquivo de classificação ao Analytics. Embora o Analytics esteja capturando e processando os dados, eles não são exibidos nos relatórios até que o arquivo de classificação tenha sido atualizado. Isso pode levar até 24 horas. Se depois de 48 horas você não visualizar seus dados, [entre em contato com o Atendimento ao Cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Alternativamente, se você sabe que vai iniciar uma atividade, você pode criar a atividade alguns dias antes e as classificações serão enviadas quando a atividade for salva. Dessa forma, os dados aparecem nos relatórios logo no início. Observe que leva de 45 a 90 minutos para que os dados sejam processados no Analytics.

## Por que não consigo selecionar o Analytics como minha fonte de geração de relatórios quando eu crio uma nova atividade?  {#section_9F4F69C3085F4C2480AF439127EB27CD}

É possível alterar as opções de Configurações do Relatórios em Administração.

1. In Adobe Target, click **[!UICONTROL Administration]**.
1. Na solução **[!UICONTROL Experience Cloud usada para a lista suspensa de]** relatórios, clique em **[!UICONTROL Selecionar por atividade]**.

![](assets/select-per-activity.png)

A lista suspensa de **[!UICONTROL Fonte de geração de relatório]** está habilitada na tela **[!UICONTROL Meta e configurações]** para criar e editar atividades.

To always use Analytics as the reporting source, select **[!UICONTROL Adobe Analytics]** from the drop-down list in Administration.
