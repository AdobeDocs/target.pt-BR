---
keywords: perguntas frequentes; perguntas frequentes; analytics for target; a4T; configuração de atividades
description: Encontre respostas para perguntas sobre a configuração de atividades ao usar o Analytics for [!DNL Target] (A4T). O A4T permite usar os relatórios do Analytics para  [!DNL Target]  atividades.
title: Onde posso encontrar perguntas frequentes sobre configurações de atividade com o A4T?
feature: Analytics for Target (A4T)
exl-id: 8a8cdbb9-89f6-4e4a-a53e-8f33adab4d61
source-git-commit: 981cff428d9e8849b9bbcbf7bef389dad0fbb32a
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 10%

---

# Configurações de atividade - Perguntas frequentes sobre o A4T

Este tópico contém respostas para as perguntas mais frequentes sobre a configuração de atividades e o uso do [!DNL Analytics] como fonte de relatórios para o [!DNL Target] (A4T).

## Quais tipos de atividade são compatíveis com [!DNL Analytics] como fonte de geração de relatórios (A4T)? {#section_5E4F58CD25A5424E869E6FE0803968EF}

+++Resposta
Para obter uma lista completa, consulte &quot;Tipos de atividade suportados&quot; no [Adobe Analytics como a Fonte de relatórios do Adobe Target (A4T)](/help/main/c-integrating-target-with-mac/a4t/a4t.md#concept_7540C8C04259434AB6EE33B09F47A1DE).

+++

## Posso usar o mesmo nome de atividade para duas atividades de espaços de trabalho separados ao usar os relatórios do A4T?

+++Resposta

Não use o mesmo nome de atividade para duas atividades de [espaços de trabalho](/help/main/administrating-target/c-user-management/property-channel/property-channel.md) separados que estejam usando o relatório A4T.

Embora isso seja suportado ao usar [!DNL Target] como fonte de relatórios, o uso do mesmo nome de atividade para duas atividades não é suportado ao usar [!UICONTROL Analytics for Target] como fonte de relatórios.

+++

## Ao configurar minhas Métricas de meta, por que não posso acessar as Configurações avançadas?

+++Resposta
Para atividades que usam [!DNL Analytics] como fonte de relatórios (A4T), a métrica de meta usa as configurações &quot;[!UICONTROL Increment Count & Keep User in Activity]&quot; e &quot;[!UICONTROL On Every Impression]&quot;. Estas configurações são *não* configuráveis.

Para obter mais informações, consulte &quot;Ao configurar minhas métricas de meta, por que não posso acessar as opções de Configurações avançadas?&quot; em [Definições de métrica - Perguntas frequentes sobre o A4T](/help/main/c-integrating-target-with-mac/a4t/r-a4t-faq/a4t-faq-metric-definition.md).

+++

## Acabei de criar um atividade. Por que não vejo nenhum dado chegando?  {#section_9F8092BE4225442896F926540292F221}


+++Resposta
Quando uma atividade é criada, [!DNL Target] envia um arquivo de classificação para [!DNL Analytics]. Embora [!DNL Analytics] esteja capturando e processando os dados, ele não mostra isso nos relatórios até que o arquivo de classificação tenha sido atualizado. Esse processo pode levar de 24 a 72 horas para ser concluído. Se, após 72 horas, você não visualizar seus dados, [contate o Atendimento ao Cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C). Como alternativa, se você souber que iniciou uma atividade, poderá criar a atividade alguns dias antes e as classificações serão enviadas quando a atividade for salva. Dessa forma, os dados aparecem nos relatórios logo no início. Observe que leva de 45 a 90 minutos para os dados serem processados em [!DNL Analytics].

+++

## Por que não consigo selecionar o Analytics como minha fonte de geração de relatórios quando crio uma atividade? {#section_9F4F69C3085F4C2480AF439127EB27CD}

+++Resposta
Você pode alterar suas opções de [!UICONTROL Reporting Settings] em [!UICONTROL Administration].

1. Em [!DNL Target], clique em **[!UICONTROL Administration]**.
1. Na lista suspensa **[!UICONTROL Experience Cloud solution used for reporting]**, clique em **[!UICONTROL Select per Activity]**.

![imagem select-per-activity](assets/select-per-activity.png)

A lista suspensa **[!UICONTROL Reporting Source]** está habilitada na tela **[!UICONTROL Goal & Settings]** para criar e editar atividades.

Para sempre usar [!DNL Analytics] como fonte de relatórios, selecione **[!UICONTROL Adobe Analytics]** na lista suspensa em [!UICONTROL Administration].

+++

## Um visitante pode alternar entre experiências direcionadas e controladas em visitas diferentes em uma atividade de Direcionamento automático que usa o A4T?

+++Resposta
O seguinte é verdadeiro supondo que visitorId não seja alterado para um visitante entre visitas.

Se a porcentagem de alocação de tráfego for ajustada no meio da atividade, é possível que um visitante se mova entre experiências direcionadas e de controle.

Se as porcentagens não forem ajustadas no meio da atividade, um visitante que vê inicialmente o controle é sempre enviado para o controle. Um visitante que é enviado para experiências direcionadas é sempre enviado para experiências direcionadas.

* Depois de estar no &quot;intervalo&quot; de tráfego direcionado, o visitante pode ser enviado para uma experiência diferente de visita para visita se os modelos de aprendizado de máquina determinarem que uma experiência diferente é relevante para a nova visita.
* Depois de ser atribuído ao &quot;bucket&quot; de controle de tráfego, um visitante sempre verá a mesma experiência, pois a atribuição de experiência se baseia em um hash pseudo-aleatório determinístico da visitorId do visitante.

+++

## Posso usar uma métrica binomial [!DNL Analytics] com um segmento aplicado como meta de otimização em uma atividade [!UICONTROL Auto-Allocate]? {#binomial}

+++Resposta
Você não pode usar uma métrica [!DNL Analytics] com um segmento aplicado como meta de otimização em uma atividade [!UICONTROL Auto-Allocate]. Como solução alternativa, você pode definir um Evento personalizado que atinja o mesmo objetivo e usá-lo como a métrica de meta de otimização.

+++
