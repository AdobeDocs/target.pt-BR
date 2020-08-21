---
description: Use o Visual Experience Composer para criar uma atividade de Direcionamento de experiência (XT) em uma página habilitada pelo Target e modificar partes da página no Adobe Target.
title: Criar uma atividade de direcionamento de experiência
feature: xt
subtopic: Multivariate Test
topic: Standard
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 8d0faeb83e7fe854dcf99c89081fb656cf16c4c0
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 100%

---


# Criar uma atividade de direcionamento de experiência{#create-an-experience-targeting-activity}

Use o [!UICONTROL Visual Experience Composer] (VEC) para criar uma atividade de [!UICONTROL Direcionamento de experiência] (XT) em uma página habilitada pelo Target e modificar partes da página no [!DNL Adobe Target].

O Direcionamento de experiência (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.

O Direcionamento de experiência, incluindo o [Direcionamento geográfico](/help/c-target/c-audiences/c-target-rules/geo.md), é importante para definir regras que direcionem uma experiência ou conteúdo específico para um determinado público-alvo. Várias regras podem ser definidas em uma atividade para levar diferentes variações de conteúdo para públicos-alvo diferentes.

Para obter mais informações sobre Direcionamento de experiência, um cenário de casos de uso e vídeos de treinamento, consulte [Direcionamento de experiência](/help/c-activities/t-experience-target/experience-target.md).

**Para criar uma atividade de XT:**

1. Na lista [!UICONTROL Atividades], clique em **[!UICONTROL Criar atividade]** > **[!UICONTROL Direcionamento de experiência]**.

   ![Criar atividade > Direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do Target. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, a [!UICONTROL Personalização automatizada] é um [recurso do Target Premium](/help/c-intro/intro.md#premium).
   >
   >Para obter mais informações sobre os diversos tipos de atividades disponíveis no [!DNL Target] e suas diferenças, consulte [Atividades](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). Consulte [Tipos de atividade do Target](/help/c-activities/target-activities-guide.md) para ajudá-lo a decidir qual tipo de atividade se adapta melhor as suas necessidades.

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   ![Caixa de diálogo Criar atividade de Direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Se preferir usar o Experience Composer baseado em formulário, selecione [!UICONTROL Formulário]. Consulte [Experience Composer baseado em formulário](/help/c-experiences/form-experience-composer.md) para obter mais informações.

   >[!NOTE]
   >
   >Além do VEC e do Experience Composer baseado em formulário, o Target oferece o VEC para aplicativo de página única e o VEC para aplicativos móveis. Para obter mais informações sobre os vários composers, consulte [Experiências e ofertas](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >A opção [!UICONTROL Escolher local de trabalho] na ilustração anterior é um recurso do [Target Premium](/help/c-intro/intro.md). Caso não veja essa opção, a licença da organização é do Target Standard.

1. (Condicional) Se você for um cliente do Target Premium, [escolha um espaço de trabalho](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Especifique o [URL da atividade](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90) e clique em **[!UICONTROL Próximo]**.

   Se sua conta foi [configurada com um URL padrão](/help/administrating-target/visual-experience-composer-set-up.md), esse URL aparece por padrão. Você pode alterar o URL padrão por outro, se necessário.

   O VEC é aberto, mostrando a página especificada no URL.

   ![Atividade de Direcionamento de experiência no VEC](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Digite um nome para a atividade no espaço fornecido.

   ![Campo nome](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

   Os seguintes caracteres não são permitidos em um nome de atividade:

   | Caractere | Descrição |
   |--- |--- |
   | `/` | Barra |
   | `?` | Ponto de interrogação |
   | `#` | Sinal numérico |
   | `:` | Dois-pontos |
   | `=` | Igual a |
   | `+` | Plus |
   | `-` | menos |
   | `@` | Sinal de arroba |

1. Crie novas experiências direcionadas para públicos-alvo diferentes.

   Para obter instruções passo a passo, consulte [Adicionar experiência](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Especifique as [metas e configurações](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) da atividade.