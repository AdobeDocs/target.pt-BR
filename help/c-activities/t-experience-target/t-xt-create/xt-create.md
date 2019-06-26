---
description: Use o Visual Experience Composer para criar uma atividade de direcionamento de experiência em uma página habilitada pelo Target e modificar partes da página no Target.
seo-description: Use o Visual Experience Composer para criar uma atividade de direcionamento de experiência (XT) em uma página ativada pelo Target e modificar partes da página no Adobe Target.
seo-title: Criar uma atividade de direcionamento de experiência
solution: Target
subtopic: Teste multivariado
title: Criar uma atividade de direcionamento de experiência
topic: Padrão
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Criar uma atividade de direcionamento de experiência{#create-an-experience-targeting-activity}

Use the [!UICONTROL Visual Experience Composer] (VEC) to create an [!UICONTROL Experience Targeting] (XT) activity on a Target-enabled page and to modify portions of the page within [!DNL Adobe Target].

O Direcionamento de experiência (XT) fornece conteúdo a um público-alvo específico com base em um conjunto de regras e critérios definidos pelo profissional de marketing.

Experience Targeting, including [geo-targeting](/help/c-target/c-audiences/c-target-rules/geo.md), is valuable for defining rules that target a specific experience or content to a particular audience. Várias regras podem ser definidas em uma atividade para levar diferentes variações de conteúdo para públicos-alvo diferentes.

For more information about Experience Targeting, a use-case scenario, and training videos, see [Experience Targeting](/help/c-activities/t-experience-target/experience-target.md).

**Para criar uma atividade XT:**

1. Na lista [!UICONTROL Atividades], clique em **[!UICONTROL Criar atividade]** &gt; **[!UICONTROL Direcionamento de experiência]**.

   ![Criar atividade &gt; Direcionamento da experiência](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do Target. Alguns tipos de atividades podem não aparecer na lista. For example, [!UICONTROL Automated Personalization] is a [Target Premium feature](/help/c-intro/intro.md#premium).
   >
   >For more information about the various activity types available in [!DNL Target] and their differences, see [Activities](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03). See [Target Activity types](/help/c-activities/target-activities-guide.md) to help you decide which activity type best suites your needs.

1. Select **[!UICONTROL Visual (Default)]**, if necessary.

   ![Caixa de diálogo Criar atividade de direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Se preferir usar o Experience Composer baseado em formulário, selecione [!UICONTROL Formulário]. See [Form-Based Experience Composer](/help/c-experiences/form-experience-composer.md) for more information.

   >[!NOTE]
   >
   >Além do VEC e do Criador de experiências baseado em forma, o Target oferece o VEC do aplicativo de página única e o VEC para aplicativos móveis. For more information about the various composers, see [Experiences and Offers](/help/c-experiences/experiences.md).
   >
   >Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md).
   >
   >The [!UICONTROL Choose Workplace] option in the preceding illustration is a [Target Premium](/help/c-intro/intro.md) feature. Sua organização tem uma licença do Target Standard caso não veja essa opção.]

1. (Conditional) If you are a Target Premium customer, [choose a workspace](/help/administrating-target/c-user-management/property-channel/property-channel.md).

1. Specify your [activity URL](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90), then click **[!UICONTROL Next]**.

   If your account is [configured with a default URL](/help/administrating-target/r-target-account-preferences/target-account-preferences.md), that URL appears by default. Você pode alterar do padrão para outro URL, se necessário.

   A VEC é aberta, mostrando a página especificada no URL.

   ![Atividade de direcionamento de experiência no VEC](/help/c-activities/t-experience-target/t-xt-create/assets/xt-in-vec.png)

1. Digite um nome para a atividade no espaço fornecido.

   ![Campo name](/help/c-activities/t-experience-target/t-xt-create/assets/xt_name-new.png)

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

1. Crie novas experiências direcionadas para públicos-alvo de diferença.

   For step-by-step instructions, see [Add experience](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

1. Especifique as [metas e configurações](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) da atividade.