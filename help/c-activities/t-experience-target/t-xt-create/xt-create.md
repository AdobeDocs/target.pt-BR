---
description: Use o Visual Experience Composer para criar uma atividade de direcionamento de experiência em uma página habilitada pelo Target e modificar partes da página no Target.
seo-description: Use o Visual Experience Composer para criar uma atividade de direcionamento de experiência em uma página ativada pelo Target e modificar partes da página no Adobe Target.
seo-title: Criar uma atividade de direcionamento de experiência
solution: Target
subtopic: Teste multivariado
title: Criar uma atividade de direcionamento de experiência
topic: Padrão
uuid: 6299982b-b1ba-4dd0-9c69-36a76680a3e1
translation-type: tm+mt
source-git-commit: 5eb79fcd0407e0da841048bcd0a1b64393490fcf

---


# Criar uma atividade de direcionamento de experiência{#create-an-experience-targeting-activity}

Use [!UICONTROL o Visual Experience Composer] (VEC) para criar uma [!UICONTROL atividade de direcionamento] de experiência (XT) em uma página habilitada para o Target e modificar partes da página dentro [!DNL Adobe Target].

1. Na lista [!UICONTROL Atividades], clique em **[!UICONTROL Criar atividade]** &gt; **[!UICONTROL Direcionamento de experiência]**.

   ![Criar atividade &gt; Direcionamento da experiência](/help/c-activities/t-experience-target/t-xt-create/assets/xt_select-1.png)

   >[!NOTE]
   >
   >Os tipos de atividades disponíveis dependem da sua conta do Target. Alguns tipos de atividades podem não aparecer na lista. Por exemplo, a Personalização automatizada é um [recurso Target Premium](/help/c-intro/intro.md#premium).

   Para obter informações sobre os tipos de atividades, consulte [Tipos de atividades](../../../c-activities/activities.md#concept_D317A95A1AB54674BA7AB65C7985BA03) e [atividades do Target](/help/c-activities/target-activities-guide.md).

1. Selecione **[!UICONTROL Visual (Padrão)]**, se necessário.

   ![Caixa de diálogo Criar atividade de direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/assets/form_url-new.png)

   Selecione essa opção se preferir usar o Experience Composer baseado em formulário. Consulte [Experience Composer baseado em formulário](https://marketing.adobe.com/resources/help/en_US/target/target/t_form_experience_composer.html).

   >[!NOTE]
   >
   >Além do VEC e do Criador de experiências baseado em forma, o Target oferece o VEC do aplicativo de página única e o VEC para aplicativos móveis. Para obter mais informações sobre os vários compositores, consulte [Experiências e ofertas](/help/c-experiences/experiences.md).

   Em caso de problemas, para obter informações sobre a solução de problemas do VEC, consulte [Solução de problemas do Visual Experience Composer](../../../c-experiences/c-visual-experience-composer/r-troubleshoot-composer/troubleshoot-composer.md#reference_77743144F10143A3A89D56E116D296E4).

1. Especifique o [URL da atividade](../../../c-activities/t-experience-target/t-xt-create/xt-activity-url.md#concept_D28549AAA0A14E3BB5F05F32BE8ABC90)e clique **[!UICONTROL em Avançar]**.

   Se sua conta foi configurada com um URL padrão, esse URL aparece por padrão. Você pode trocar o URL padrão por outro URL.

   O Visual Experience Composer é aberto, mostrando a página especificada no URL.

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

1. Crie quaisquer novas experiências alterando os elementos na página.

   Para obter instruções passo a passo, consulte [Adicionar experiência](/help/c-activities/t-experience-target/t-xt-create/xt-add-experience.md).

   Por padrão, o Visual Experience Composer não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar o JavaScript se deseja poder alterar esses elementos usando o Visual Experience Composer.

   À medida que passa o mouse sobre os elementos da página, eles são destacados. Qualquer elemento destacado pode ser alterado usando o VEC. Para obter uma lista de ações que podem ser executadas em um elemento para alterar a experiência, consulte [Opções do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Se você criou uma mbox na página usando o Target Classic, (antes Test&amp;Target), essa mbox aparece como um elemento que mostra o seu nome e pode ser modificada como qualquer outro elemento.

1. Especifique as [metas e configurações](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) da atividade.
