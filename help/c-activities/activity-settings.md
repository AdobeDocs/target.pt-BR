---
keywords: Meta e configurações; objetivo; prioridade; duração
description: Saiba como usar as Configurações de atividade no Adobe [!DNL Target] para gerenciar o objetivo, a prioridade e a duração de suas atividades.
title: Como Especifique As Configurações Da Atividade?
feature: Atividades
exl-id: 7f34080b-d2ed-4fe5-80ff-3aba16961223
translation-type: tm+mt
source-git-commit: a92e88b46c72971d5d3c752593d651d8290b674e
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 80%

---

# Configurações de atividade

Use [!UICONTROL Configurações da atividade] em [!DNL Adobe Target] para gerenciar o objetivo, a prioridade e a duração de suas atividades.

1. Insira observações sobre o objetivo da atividade.

   Digite qualquer informação sobre sua atividade que seja útil para manter ao seu alcance ou de outros membros da equipe. Arraste para redimensionar o campo [!UICONTROL Objetivo].
1. Definir a prioridade da atividade.

   Dependendo das configurações, a interface do usuário e as opções de [!UICONTROL Prioridade] variam. É possível usar as configurações herdadas de Baixo, Médio ou Alto, ou pode ativar as prioridades otimizadas de 0 a 999.

   A prioridade é usada se várias atividades forem atribuídas para o mesmo local com o mesmo público-alvo. Se duas ou mais atividades forem atribuídas ao local, a atividade com a maior prioridade é exibida.

   Se esta opção não estiver ativada em [!UICONTROL Administration] > [!UICONTROL Reporting] (o padrão), especifique uma prioridade: Baixo, Médio ou Alto.

   Para ativar as prioridades otimizadas, clique em [!UICONTROL Administration] > [!UICONTROL Reporting] e alterne a opção [!UICONTROL Enable Fine-Grained Priorities] para a posição &quot;On&quot;.

   Se esta opção estiver ativada, especifique um valor entre 0 e 999:

   * 0 = Baixo
   * 999 = Alto

   Para atividades criadas em versões anteriores do [!DNL Target Standard/Premium], a prioridade Baixa é convertida para 0, a Média é convertida para 5 e a Alta é convertida para 10. É possível ajustar esses valores conforme necessário.

   >[!NOTE]
   >
   >Antes de poder desabilitar esta opção após o uso de prioridades otimizadas, todas as prioridades devem ser ajustadas novamente para 0, 5 e 10.

1. Defina a duração da atividade.

   É possível ativar e desativar manualmente a atividade ou especificar uma data e hora para a entrega da atividade. O controle de hora usa um relógio de 24 horas, sendo 00:00 a meia-noite. O fuso horário é definido para o que foi configurado no navegador. Para usar um fuso horário diferente, defina o navegador para outro fuso horário e reinicie-o.

   >[!NOTE]
   >
   >O agendamento de uma atividade controla seu prazo de entrega; no entanto, a atividade deve ser ativada explicitamente para poder ser entregue de acordo com o agendamento especificado.

A página [!UICONTROL Meta e configurações] inclui configurações adicionais que variam de acordo com o tipo de atividade que você está criando. Para obter mais informações sobre essas configurações, consulte seu tipo de atividade:

* [Teste A/B](/help/c-activities/t-test-ab/t-test-create-ab/ab-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Personalização automatizada](/help/c-activities/t-automated-personalization/automated-personalization.md#task_8AAF837796D74CF893CA2F88BA1491C9)
* [Direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Teste multivariado](/help/c-activities/c-multivariate-testing/t-create-multivariate-test/goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC)
* [Recommendations](/help/c-recommendations/t-create-recs-activity/recs-activity-settings.md#reference_3FDA8388CEEC4159949151C1829E2FBB)

## Vídeo de treinamento: configurações da atividade  ![Selo do tutorial](/help/assets/tutorial.png)

Este vídeo inclui informações sobre as configurações da atividade.

* Inserir um objetivo para a atividade
* Definir o nível de prioridade das atividades
* Programar as horas de início e término da atividade
* Adicionar públicos-alvo para relatórios a fim de criar filtros de relatórios
* Inserir observações para a atividade

   >[!VIDEO](https://video.tv.adobe.com/v/17381)
