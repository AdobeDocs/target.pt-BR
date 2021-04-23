---
keywords: perguntas frequentes; perguntas frequentes; analytics for target; a4T; configuração de atividades
description: Encontre respostas para perguntas sobre a configuração da atividade ao usar o Analytics para  [!DNL Target] (A4T). A4T lets you use Analytics reporting for [!DNL Target] atividades.
title: Onde posso encontrar perguntas frequentes sobre as configurações de atividade com o A4T?
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 25%

---

# Configurações de atividade - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre a configuração de atividades e o uso de [!DNL Analytics] como fonte de relatórios para [!DNL Target] (A4T).

## Quais tipos de atividade são compatíveis com o Analytics como fonte de geração de relatórios (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

Para obter uma lista completa, consulte &quot;Tipos de atividade suportados&quot; no [Adobe Analytics como a Fonte de relatórios do Adobe Target (A4T)](/help/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

## Ao configurar minhas Métricas de meta, por que não posso acessar as Configurações avançadas?

Para atividades que usam [!DNL Analytics] como fonte de relatórios (A4T), a métrica de meta usa as configurações &quot;[!UICONTROL Aumentar contagem e manter o usuário na atividade]&quot; e &quot;[!UICONTROL Em todas as impressões]&quot;. Essas configurações são *não* configuráveis.

Para obter mais informações, consulte &quot;Ao configurar minhas métricas de meta, por que não posso acessar as opções de Configurações avançadas?&quot; em [Definições de métrica - Perguntas frequentes sobre o A4T](/help/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

## Acabei de criar um atividade. Por que não vejo nenhum dado chegando?   {#section_9F8092BE4225442896F926540292F221}

Quando uma atividade é criada, [!DNL Target] envia um arquivo de classificação para [!DNL Analytics]. Embora [!DNL Analytics] esteja capturando e processando os dados, isso não mostra que nos relatórios, até que o arquivo de classificação tenha sido atualizado. Esse processo pode levar até 24 horas. Se depois de 48 horas você não visualizar seus dados, [entre em contato com o Atendimento ao Cliente](/help/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Como alternativa, se você souber que iniciará uma atividade, poderá criar a atividade alguns dias antes e as classificações serão enviadas quando a atividade for salva. Dessa forma, os dados aparecem nos relatórios logo no início. Observe que leva de 45 a 90 minutos para que os dados sejam processados no [!DNL Analytics].

## Por que não consigo selecionar o Analytics como minha fonte de relatórios quando eu crio uma atividade? {#section_9F4F69C3085F4C2480AF439127EB27CD}

Você pode alterar as opções de [!UICONTROL Configurações de relatório] em [!UICONTROL Administração].

1. Em [!DNL Target], clique em **[!UICONTROL Administração]**.
1. Na solução **[!UICONTROL Experience Cloud usada para a lista suspensa de]** relatórios, clique em **[!UICONTROL Selecionar por atividade]**.

![](assets/select-per-activity.png)

A lista suspensa de **[!UICONTROL Fonte de geração de relatório]** está habilitada na tela **[!UICONTROL Meta e configurações]** para criar e editar atividades.

Para sempre usar [!DNL Analytics] como fonte de relatórios, selecione **[!UICONTROL Adobe Analytics]** na lista suspensa em [!UICONTROL Administration].

## Um visitante pode alternar entre experiências direcionadas e controladas em visitas diferentes em uma atividade de Direcionamento automático que usa o A4T?

O seguinte é verdadeiro, supondo que a visitorId não seja alterada para um visitante entre visitas.

Se a porcentagem de alocação de tráfego for ajustada no meio da atividade, é possível que um visitante possa se mover entre as experiências de direcionamento e de controle.

Se as porcentagens não forem ajustadas no meio da atividade, um visitante que inicialmente vê o controle será sempre enviado para o controle. Um visitante que é enviado para experiências direcionadas é sempre enviado para experiências direcionadas.

* Depois de estar no &quot;bucket&quot; direcionado do tráfego, o visitante pode ser enviado a uma experiência diferente da visita, caso os modelos de aprendizado de máquina determinem que uma experiência diferente é relevante para a nova visita.
* Depois de ser atribuído ao &quot;bucket&quot; de controle do tráfego, um visitante sempre verá a mesma experiência, pois a atribuição de experiência é baseada em um hash pseudo-aleatório determinístico da visitorId do visitante.
