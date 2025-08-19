---
keywords: Recommendations, Configurações, nome, objetivo, prioridade, duração, configurações de relatórios, outros metadados
description: Saiba como definir as configurações usadas para descrever e controlar uma atividade do Recommendations no Adobe Target.
title: Como Definir As Configurações De Atividade Do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=pt-BR#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
source-git-commit: b7c7e8d85f7f39024ed5e57177e5c9f628460e9c
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 43%

---

# Configurações de atividade do Recommendations

Informações sobre as configurações que você pode usar para descrever e controlar uma atividade do [!UICONTROL Recommendations] no [!DNL Adobe Target].

As seções a seguir descrevem as configurações disponíveis para uma atividade [!UICONTROL Recommendations].

## Nome

Clique no ícone Mais Ações ( ![Ícone Mais Ações](/help/main/assets/icons/MoreSmallListVert.svg) ) e em **[!UICONTROL Rename]** para fornecer um nome descritivo que ajudará você e sua equipe a identificarem a atividade.

Os seguintes caracteres não são permitidos em um nome de atividade:

`/`
`?`
`#`
`:`
`=`
`+`
`-`
`@`

Se você especificar um nome de atividade [!UICONTROL Recommendations] que já existe para outra atividade em [!UICONTROL Recommendations Classic], a nova atividade será ressincronizada com um novo nome. O novo nome é o nome original anexado com um carimbo de data e hora que o torna exclusivo. O novo nome é exibido no [!DNL Target Standard/Premium] e no [!UICONTROL Recommendations Classic].

## Objetivo

(Opcional) Descreva a meta da atividade.

## Prioridade

Ajuste o controle deslizante para determinar o nível de prioridade.

A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.

## Duração

Defina a duração da atividade.

A atividade pode começar quando aprovada ou você pode definir data e hora específicas. Da mesma maneira, a atividade não pode terminar quando é desativada, ou você pode definir uma data e hora. O seletor de hora usa um relógio de 24 horas, sendo 00:00 meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o.

## Configurações da geração de relatórios

* **Source de Relatórios:** Especifique de quais dados de solução são coletados:

   * [!DNL Adobe Target]
   * [!DNL Adobe Analytics]
   * [!DNL Adobe Customer Journey Analytics]

  Se uma solução de relatório for especificada nas [configurações da conta](/help/main/administrating-target/reporting.md), a solução especificada será usada e essa configuração não ficará visível.

  Não é possível alterar sua fonte de relatórios após a atividade entrar em vigor para manter os relatórios consistentes.

  **[!DNL Adobe Analytics]**: Consulte [[!DNL Adobe Analytics] como fonte de relatórios para [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para saber mais sobre as diferenças entre as soluções de relatórios e as vantagens de cada uma.

  Ao selecionar [!DNL Analytics] como fonte de relatórios para [!DNL Target] (A4T), você seleciona um conjunto de relatórios [!DNL Analytics] para receber dados de atividade de [!DNL Target]. Para fazer isso, primeiro escolha uma das [!DNL Analytics] empresas vinculadas à sua conta e, em seguida, selecione o conjunto de relatórios apropriado para a atividade. Somente conjuntos de relatórios provisionados para conexão com [!DNL Target] estão disponíveis para seleção. Se você não vir o conjunto de relatórios esperado, primeiro tente fazer logoff e depois fazer logon novamente no [!DNL Adobe Experience Cloud] para tentar novamente. Se o conjunto de relatórios ainda estiver ausente na lista, contate o [Atendimento ao cliente](/help/main/cmp-resources-and-contact-information.md#reference_ACA3391A00EF467B87930A450050077C).

  O [!DNL Analytics for Target] (A4T) requer um servidor de rastreamento para relatar os resultados corretamente. Um servidor de rastreamento padrão é exibido no campo [!UICONTROL Tracking Server]. Se você usar mais de um servidor de rastreamento, inclua o servidor de rastreamento correto neste campo. Consulte [Usando um servidor de rastreamento do Analytics](/help/main/c-integrating-target-with-mac/a4t/analytics-tracking-server.md#task_72077BA7E93C4A65A715A18F32228823) para obter mais informações.

  **[!DNL Adobe Customer Journey Analytics]**: Consulte [[!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obter mais informações sobre a integração entre [!DNL Adobe Customer Journey Analytics] e [!DNL Target].

* **Métrica de objetivo:** selecione a métrica de sucesso que determina se a atividade é bem sucedida.
* **Métricas adicionais:** configure métricas de sucesso adicionais para serem usadas nos relatórios.
* **Públicos-alvo para relatórios:** defina o público-alvo que pode ser usado ao filtrar os relatórios.

## Outros metadados

Insira observações sobre a atividade.

## Vídeo de treinamento: configurações da atividade (3:02) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

>[!VIDEO](https://video.tv.adobe.com/v/17381)
