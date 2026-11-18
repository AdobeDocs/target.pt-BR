---
keywords: Direcionamento;análise;servidor de rastreamento;análise para destino;a4T
description: Saiba como configurar uma atividade no [!DNL Adobe Target] para usar o [!DNL Adobe Analytics] como fonte de relatórios (A4T).
title: Como posso usar os dados do [!DNL Analytics] no [!DNL Target]?
feature: Analytics for Target (A4T)
exl-id: 85605ff9-c09a-4a1a-9784-bdacda377e1d
TQID: 'https://experienceleague.adobe.com/x38YsYI4a6-92oOr6Fs3RfKrJHbSaLNj0cki5CInPPg'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: 891742a5-242d-5099-966a-ca76c17cd2d2
    internal-label: Analytics for Target (A4T)
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 4876228feee28031373f7e0abe62a66b05b15274
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 0%
---
# Usando dados de [!DNL Adobe Analytics] {#create-a4t}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba como configurar uma atividade para usar o [!DNL Adobe Analytics] como fonte de relatórios (A4T), o que preparar antes de começar e como escolher a meta da atividade.

>[!ENDSHADEBOX]

O Analytics for Target (A4T) mede os resultados de uma atividade [!DNL Adobe Target] com os dados e métricas de [!DNL Adobe Analytics]. Para usar o A4T, configure a atividade para que [!DNL Analytics] seja sua fonte de geração de relatórios. Para obter informações detalhadas sobre como configurar o [!DNL Analytics] como fonte de dados para [!DNL Target], consulte [Adobe Analytics como Source de Relatórios para o Adobe Target](/help/main/c-integrating-target-with-mac/a4t/a4t.md).

## Antes de começar {#before-you-begin}

>[!NOTE]
>
>A opção **[!UICONTROL Adobe Analytics]** está disponível quando a conta [!DNL Adobe Experience Cloud] está vinculada a [!DNL Analytics] e [!DNL Target], mesmo que a integração entre [!DNL Target] e [!DNL Analytics] não tenha sido configurada para a sua conta.

Antes de criar a atividade, estabeleça sua meta, por exemplo, melhorar a receita por visitante (RPV) ou aumentar os cliques no carrinho de compras. Em seguida, escolha a métrica de sucesso final que mede essa meta. Métricas adicionais podem ser selecionadas em [!DNL Analytics] a qualquer momento, mas você ainda deve especificar a métrica que este teste deve afetar.

## Selecione Analytics como fonte de relatórios {#select-reporting-source}

>[!NOTE]
>
>Se você usa a at.js versão 0.9.1 ou posterior, não é necessário especificar um servidor de rastreamento ao criar uma atividade que usa [!DNL Adobe Analytics] como fonte de relatórios. A biblioteca at.js envia automaticamente os valores do servidor de rastreamento para [!DNL Target]. O campo **[!UICONTROL Servidor de Rastreamento]** na página **[!UICONTROL Metas e Configurações]** pode permanecer vazio.

A fonte de relatórios está selecionada na página **[!UICONTROL Metas e Configurações]** da atividade. Nesta página, você escolhe uma empresa [!DNL Analytics] e o conjunto de relatórios que recebe os dados de atividade [!DNL Target] e verifica o servidor de rastreamento.

➡️ Para obter as etapas, os requisitos do conjunto de relatórios e os detalhes do servidor de rastreamento, consulte [Source de Relatórios](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source).

Quando [!DNL Analytics] é a fonte de relatórios, a atividade não oferece uma opção para configurar públicos para relatórios. Em vez disso, [!DNL Analytics] segmentos estão disponíveis no relatório [!DNL Target] **[!UICONTROL Atividades]**.

## Definir a meta da atividade {#set-goal}

Cada atividade requer uma métrica de sucesso como meta. O objetivo é a atividade de conversão que sinaliza uma atividade bem-sucedida. Qualquer métrica disponível no seletor de métrica [!DNL Analytics] pode ser usada. É prática recomendada nunca executar um teste sem um objetivo para melhorar de uma maneira específica.

Definir uma meta não impede que você use outras métricas para avaliar os resultados do teste. No entanto, a meta identifica o que você deseja melhorar com o teste.

Depois que um visitante conclui sua meta, ele não é mais incluído na atividade. Se o visitante entrar na atividade novamente após concluí-la, ele será contado como um novo visitante.
