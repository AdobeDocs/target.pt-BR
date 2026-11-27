---
keywords: Recomendações, Configurações, nome, objetivo, prioridade, duração, configurações de relatórios, outros metadados
description: Saiba como definir as configurações usadas para descrever e controlar uma atividade do Recommendations no Adobe Target.
title: Como Definir As Configurações De Atividade Do Recommendations?
badgePremium: label="Premium" type="Positive" url="https://experienceleague.adobe.com/docs/target/using/introduction/intro.html?lang=en#premium newtab=true" tooltip="Consulte o que está incluído no Target Premium."
feature: Recommendations
exl-id: 77bb14fc-342d-41cd-8084-e21067f277af
TQID: 'https://experienceleague.adobe.com/pfMAvl6MmLCtH3PZfOR4Ve-WFIc3e2iN2Bh-cIzjeC0'
product_v2:
  - id: e43347a8-f2c5-4aa4-8623-6f13875d7e3a
    internal-label: Target
feature_v2:
  - id: adee20bd-51f4-461d-b9db-d215f8756eeb
    internal-label: Audiences
  - id: f69bc5f1-ebdb-4306-a281-f2e77daf734c
    internal-label: Activities and tests
subfeature_v2:
  - id: ed58f4a1-16eb-4c8c-b505-be9da766a9ec
    internal-label: Recommendations
topic_v2:
  - id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dc
    internal-label: Metadata
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
    internal-label: Customer experience
source-git-commit: 1ca30ccbd1acc115980ffe3780ba6c0dbb343806
workflow-type: tm+mt
source-wordcount: '488'
ht-degree: 13%
---
# Configurações de atividade do Recomendações {#recs-activity-settings}

>[!BEGINSHADEBOX]

**Nesta página:** Saiba mais sobre as configurações que descrevem e controlam uma atividade [!DNL Recommendations] no [!DNL Adobe Target].

>[!ENDSHADEBOX]

As configurações de atividade identificam uma atividade [!DNL Recommendations], controlam quando e onde ela é exibida e definem como seus resultados são relatados.

## Nome

Clique no ícone Mais Ações ( ![ícone Mais Ações](/help/main/assets/icons/MoreSmallListVert.svg) ) e em **[!UICONTROL Renomear]** para dar à atividade um nome descritivo que ajude a identificá-la.

Os seguintes caracteres não são permitidos em um nome de atividade: `/`, `?`, `#`, `:`, `=`, `+`, `-` e `@`.

Se o nome de uma atividade [!DNL Recommendations] já existir para outra atividade no [!UICONTROL Recommendations Classic], a nova atividade será ressincronizada com um novo nome. O novo nome é o nome original com um carimbo de data e hora anexado para torná-lo exclusivo. Ele é exibido no [!DNL Target Standard/Premium] e no [!UICONTROL Recommendations Classic].

## Objetivo

(Opcional) Descreva a meta da atividade.

## Prioridade

Ajuste o controle deslizante para definir o nível de prioridade.

A prioridade é usada quando várias atividades são atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.

## Duração

Defina a duração da atividade.

A atividade pode ser iniciada quando é ativada ou em uma data e hora específicas. Da mesma forma, ele pode terminar quando é desativado ou em uma data e hora específicas.

O seletor de hora usa um relógio de 24 horas, sendo 00h a meia-noite. O fuso horário é o configurado no navegador. Para usar um fuso horário diferente, defina o navegador para esse fuso horário e reinicie o navegador.

## Configurações da geração de relatórios

As configurações a seguir definem como os resultados da atividade são relatados.

* **[!UICONTROL Source de Relatórios]:** Especifica a solução da qual os dados são coletados: [!DNL Adobe Target], [!DNL Adobe Analytics] ou [!DNL Adobe Customer Journey Analytics].

  Se uma solução de relatório for especificada nas [configurações da conta](/help/main/administrating-target/reporting.md), essa solução será usada e essa configuração não ficará visível. A fonte de relatórios não pode ser alterada depois que a atividade é publicada, para que os relatórios sejam consistentes.

  **[!DNL Adobe Analytics]**: Consulte [[!DNL Adobe Analytics] como fonte de relatórios para [!DNL Target]](/help/main/c-integrating-target-with-mac/a4t/a4t.md) para conhecer as diferenças entre as soluções de relatórios e as vantagens de cada uma. Para a seleção do conjunto de relatórios [!DNL Analytics] e do servidor de rastreamento, consulte [Source de Relatórios](/help/main/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reporting-source).

  **[!DNL Adobe Customer Journey Analytics]**: Consulte [[!DNL Target] relatórios em [!DNL Adobe Customer Journey Analytics]](/help/main/c-integrating-target-with-mac/cja/target-reporting-in-cja.md) para obter mais informações sobre a integração entre [!DNL Adobe Customer Journey Analytics] e [!DNL Target].

* **[!UICONTROL Métrica de objetivo]:** seleciona a métrica de sucesso que determina se a atividade é bem-sucedida.
* **[!UICONTROL Métricas Adicionais]:** Configura métricas de sucesso adicionais para os relatórios.
* **[!UICONTROL Públicos-alvo para relatórios]:** Define os públicos-alvo que podem ser usados para filtrar os relatórios.

## Outros metadados

Insira observações sobre a atividade.

## Vídeo de treinamento: configurações da atividade (3:02) ![Selo do tutorial](/help/main/assets/tutorial.png)

Este vídeo aborda as seguintes configurações de atividade:

* Insira um objetivo para a atividade.
* Defina o nível de prioridade da atividade.
* Agendar as horas de início e término.
* Adicione públicos-alvo para relatórios a fim de criar filtros de relatório.
* Insira observações para a atividade.

>[!VIDEO](https://video.tv.adobe.com/v/17381)
