---
keywords: intervalo de tempo, data de início, data de término, datas de início/término, intervalo de tempo, agenda do target, divisão de semana, divisão de dia, divisão
description: Saiba como usar datas e horas de início e término para direcionar usuários que visitam seu site durante um período específico.
title: Posso Direcionar Visitantes Que Visitam Meu Site Em Momentos Específicos?
feature: Públicos-alvo
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: b46966a8dbb2ff6d2efbfb8f126783f750c2f08c
workflow-type: tm+mt
source-wordcount: '425'
ht-degree: 45%

---

# Intervalo de tempo

Você pode adicionar datas e horas de início e término em [!DNL Adobe Target] para direcionar usuários que visitam seu site durante um período específico. Também é possível definir opções de Divisão de semana e dia para criar padrões recorrentes de direcionamento de público-alvo.

Por exemplo, usando o [recurso de públicos-alvo ad hoc combinados](/help/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5), você pode direcionar os usuários com conteúdo específico durante os três dias que antecedem a Black Friday e com outro conteúdo após a Black Friday.

1. Na interface do [!DNL Target], clique em **[!UICONTROL Públicos-alvo]** > **[!UICONTROL Criar público-alvo]**.
1. 
   1. Nomeie o público-alvo e adicione uma descrição opcional.
1. Arraste e solte **[!UICONTROL Intervalo de tempo]** no painel do construtor de público-alvo.

   ![](assets/target_timeframe_dialog.png)

1. Especifique as datas e horas de [!UICONTROL Início] e [!UICONTROL Término] para o público-alvo.

   Deixe a data de início em branco para iniciar a segmentação de acordo com a agenda da atividade. Deixe a data de término em branco para continuar a segmentação até a data e hora de término da atividade.

   Você também pode deixar as datas de início ou término em branco. Essa funcionalidade permite usar o mesmo público-alvo em várias atividades (sem fazer uma cópia do público-alvo), enquanto controla as datas de início e término no nível da atividade.

   >[!NOTE]
   >
   >O fuso horário é exibido para datas de início/término como GMT +/- NN:NN, onde NN:NN é o deslocamento de GMT e reflete o fuso horário no nível da conta, em vez do fuso horário do visitante. Por exemplo, o fuso horário da Califórnia seria exibido como GMT -08:00.

1. (Condicional) Clique em **[!UICONTROL Definir frequência]** para definir padrões recorrentes, incluindo dias das semanas e horas.

   ![Divisão de semana e dia](assets/week_and_day_parting.png)

   Você pode usar as opções de [!UICONTROL Frequency], por exemplo, para exibir uma opção de &quot;Bate-papo agora&quot; para os visitantes somente durante os dias e horas em que a central de atendimento estiver funcionando.

   Selecione um ou mais dias da semana e defina as horas de início e término. Clique em **[!UICONTROL Adicionar frequência]** para especificar padrões adicionais, conforme desejado.

   >[!NOTE]
   >
   >O fuso horário é exibido para [!UICONTROL Divisão de semana e dia] como GMT +/- NN:NN, onde NN:NN é o deslocamento de GMT e reflete o fuso horário no nível da conta, em vez do fuso horário do visitante. Por exemplo, o fuso horário da Califórnia para Horário de Verão do Pacífico seria exibido como GMT -07:00.

1. (Opcional) Configure regras adicionais para o público-alvo.

   Você pode repetir a Etapa 5 para cada regra, se desejar.

1. Clique em **[!UICONTROL Concluído]**.

## Vídeo de treinamento: Criação de públicos-alvo ![Selo de visão geral](/help/assets/overview.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
