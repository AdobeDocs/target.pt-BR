---
keywords: intervalo de tempo, data inicial, data final, datas inicial/final, intervalo de tempo, agenda do target, divisão de semana, divisão de dia, divisão
description: Saiba como usar datas e horas de início e término para direcionar os usuários que visitam seu site durante um período específico.
title: Posso direcionar visitantes que visitam meu site em horários específicos?
feature: Audiences
exl-id: 814d545d-baee-4f8b-a2ed-ed68fceaeb7f
source-git-commit: 0e4698935b90cc0236abe6a47a6183c7fd2a7b20
workflow-type: tm+mt
source-wordcount: '431'
ht-degree: 25%

---

# [!UICONTROL Time Frame]

Você pode adicionar datas e horas de início e término em [!DNL Adobe Target] para direcionar os usuários que visitam seu site durante um intervalo de tempo específico. Também é possível definir opções de Divisão de semana e dia para criar padrões recorrentes de direcionamento de público-alvo.

Por exemplo, usando o [recurso de públicos-alvo ad hoc combinados](/help/main/c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5), você pode direcionar os usuários com conteúdo específico durante os três dias que antecedem a Black Friday e com outro conteúdo após a Black Friday.

1. Na interface [!DNL Target], clique em **[!UICONTROL Audiences]** > **[!UICONTROL Create Audience]**.
1. Nomeie o público-alvo e adicione uma descrição opcional.
1. Arraste e solte **[!UICONTROL Time Frame]** no painel do audience builder.

   ![imagem de target_timeframe_dialog](assets/target_timeframe_dialog.png)

1. Especifique as datas e horas [!UICONTROL Start] e [!UICONTROL End] para o público-alvo.

   Deixe a data de início em branco para iniciar a segmentação de acordo com a agenda da atividade. Deixe a data de término em branco para continuar a segmentação até a data e hora de término da atividade.

   Você também pode deixar as datas de início ou término em branco. Essa funcionalidade permite usar o mesmo público-alvo em várias atividades (sem fazer uma cópia do público-alvo), enquanto controla as datas de início e término no nível da atividade.

   >[!NOTE]
   >
   >Considere o seguinte:
   >
   >* O fuso horário é exibido para datas de Início/Término como GMT +/- NN:NN, onde NN:NN é o deslocamento de GMT e reflete o fuso horário no nível da conta, em vez do fuso horário do visitante. Por exemplo, o fuso horário da Califórnia seria exibido como GMT -08:00.
   >
   >* [!DNL Target] públicos-alvo não consideram as alterações do horário de verão. Você deve salvar os públicos novamente manualmente para levar em conta as alterações de horário de verão.

1. (Condicional) Clique em **[!UICONTROL Set frequency]** para definir padrões recorrentes, incluindo dias das semanas e horas.

   ![Divisão de semana e dia](assets/week_and_day_parting.png)

   Você pode usar [!UICONTROL Frequency] opções, por exemplo, para exibir uma opção &quot;Conversar agora&quot; para os visitantes somente durante os dias e horas em que sua central de atendimento tem pessoal.

   Selecione um ou mais dias da semana e defina as horas de início e término. Clique em **[!UICONTROL Add frequency]** para especificar os padrões adicionais, conforme desejado.

   >[!NOTE]
   >
   >O fuso horário de [!UICONTROL Week and Day Parting] é exibido como GMT +/- NN:NN, onde NN:NN é o deslocamento de GMT e reflete o fuso horário no nível da conta, em vez do fuso horário do visitante. Por exemplo, o fuso horário da Califórnia para o Horário de Verão do Pacífico seria exibido como GMT -07:00.

1. (Opcional) Configure regras adicionais para o público-alvo.

   Se desejar, repita a Etapa 5 para cada regra.

1. Clique em **[!UICONTROL Done]**.

## Vídeo de treinamento: Criando públicos-alvo ![Selo de visão geral](/help/main/assets/overview.png)

Este vídeo inclui as informações sobre o uso das categorias de público-alvo.

* Criar públicos-alvo
* Definir categorias de públicos-alvo

>[!VIDEO](https://video.tv.adobe.com/v/17392)
