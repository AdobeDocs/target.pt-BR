---
keywords: perguntas frequentes; perguntas frequentes; analytics for target; a4T; configuração de atividades
description: Encontre respostas para perguntas sobre a configuração da atividade ao usar o Analytics para Públicos alvos (A4T). O A4T permite que você use o relatórios do Analytics para atividades do Público alvo.
title: Onde posso encontrar perguntas frequentes sobre configurações de Atividade com A4T?
feature: Analytics for Target (A4T)
translation-type: tm+mt
source-git-commit: bb27f6e540998f7dbe7642551f7a5013f2fd25b4
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 34%

---


# Configurações de atividade - Perguntas frequentes sobre o A4T

Este tópico contém respostas a perguntas frequentes sobre a configuração da atividade e o uso de [!DNL Analytics] como a fonte do relatórios para [!DNL Target] (A4T).

## Quais tipos de atividade são compatíveis com o Analytics como fonte de geração de relatórios (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

Para obter uma lista completa, consulte &quot;Tipos de atividade suportados&quot; no [Adobe Analytics como a Fonte de relatórios do Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Ao configurar minhas métricas de metas, por que não posso acessar as configurações avançadas?

Para atividades que usam [!DNL Analytics] como fonte de relatórios (A4T), a métrica de objetivo sempre usará as configurações &quot;[!UICONTROL Aumentar a contagem e manter o usuário na Atividade]&quot; e &quot;[!UICONTROL Em cada impressão]&quot;. Isso é *não* configurável.

Para obter mais informações, consulte &quot;Ao configurar minhas métricas de objetivo, por que não posso acessar as opções de Configurações avançadas?&quot; em [Definições de métricas - Perguntas frequentes sobre a A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Acabei de criar um atividade. Por que não vejo nenhum dado chegando?   {#section_9F8092BE4225442896F926540292F221}

Quando uma atividade é criada, [!DNL Target] envia um arquivo de classificação para [!DNL Analytics]. Embora [!DNL Analytics] esteja capturando e processando os dados, ele não é exibido nos relatórios até que o arquivo de classificação seja atualizado. Isso pode levar até 24 horas. Se depois de 48 horas você não visualizar seus dados, [entre em contato com o Atendimento ao Cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Alternativamente, se você sabe que vai iniciar uma atividade, você pode criar a atividade alguns dias antes e as classificações serão enviadas quando a atividade for salva. Dessa forma, os dados aparecem nos relatórios logo no início. Observe que leva de 45 a 90 minutos para que os dados sejam processados no [!DNL Analytics].

## Por que não consigo selecionar o Analytics como minha fonte de geração de relatórios quando eu crio uma nova atividade?   {#section_9F4F69C3085F4C2480AF439127EB27CD}

Você pode alterar as opções [!UICONTROL Configurações do Relatórios] em [!UICONTROL Administração].

1. Em [!DNL Target], clique em **[!UICONTROL Administração]**.
1. Na solução **[!UICONTROL Experience Cloud usada para a lista suspensa de]** relatórios, clique em **[!UICONTROL Selecionar por atividade]**.

![](assets/select-per-activity.png)

A lista suspensa de **[!UICONTROL Fonte de geração de relatório]** está habilitada na tela **[!UICONTROL Meta e configurações]** para criar e editar atividades.

Para sempre usar [!DNL Analytics] como fonte de relatórios, selecione **[!UICONTROL Adobe Analytics]** na lista suspensa em [!UICONTROL Administration].

## Um visitante pode alternar entre experiências direcionadas e controladas em visitas diferentes em uma atividade de Público alvo automático que usa A4T?

O seguinte é verdadeiro, desde que a visitorId não seja alterada para um visitante entre visitas.

Se a porcentagem de alocação de tráfego for ajustada para atividade média, é possível que um visitante se mova entre as experiências de direcionamento e controle.

Se as porcentagens não forem ajustadas no meio da atividade, um visitante que inicialmente visualizar o controle sempre será enviado para controle. Um visitante enviado para experiências direcionadas sempre será enviado para experiências direcionadas.

* Depois de estar no &quot;bucket&quot; de tráfego direcionado, o visitante pode ser enviado a uma experiência diferente da visita para a visita se os modelos de aprendizado de máquina determinarem que uma experiência diferente é relevante para a nova visita.
* Depois de ser atribuído ao &quot;bucket&quot; de controle do tráfego, um visitante sempre visualizará a mesma experiência, pois a atribuição da experiência é baseada em um hash pseudo-aleatório determinístico do visitorId do visitante.
