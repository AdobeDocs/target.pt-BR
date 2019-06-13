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
source-git-commit: f81d3ab49dc2cd01b4025f542d3174abf0a3c0d6

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

1. [Crie quaisquer novas experiências](../../../c-activities/t-experience-target/t-xt-create/xt-add-experience.md#task_454646F2895242D3B92DC395A0CE1A00) alterando os elementos na página.



   Por padrão, o Visual Experience Composer não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar o JavaScript se deseja poder alterar esses elementos usando o Visual Experience Composer.

   >[!NOTE]
   >
   >Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.

   À medida que passa o mouse sobre os elementos da página, eles são destacados. Qualquer elemento destacado pode ser alterado usando o Experience Composer.

   Se você criou uma mbox na página usando o Target Classic, (antes Test&amp;Target), essa mbox aparece como um elemento que mostra o seu nome e pode ser modificada como qualquer outro elemento.

   >[!NOTE]
   >
   >Se você apresentar uma imagem de uma fonte diferente da sua página principal (como uma imagem hospedada em akamai.net e oferecida em dell.com), ela não será exibida na miniatura da página mostrada no diagrama de fluxo.

1. Clique em **[!UICONTROL Avançar]**.

   O diagrama do fluxo é aberto.

   ![](assets/xt_diagram.png)

   O diagrama do fluxo guia você pelas etapas da escolha do público-alvo para a atividade e da configuração das experiências.
1. Passe o mouse sobre o público-alvo, clique no ícone **[!UICONTROL Editar]** (três elipses verticais) que é exibido, clique em **[!UICONTROL Alterar público-alvo]** e selecione o público para a primeira experiência na atividade.

   ![](assets/xt_change_audience.png)

   A biblioteca de público-alvo é exibida. A biblioteca de público-alvo contém públicos que foram definidos previamente, inclusive alguns comuns que são predefinidos como parte do Target. Você pode selecionar um público-alvo da biblioteca ou [criar um novo público-alvo](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271). Para mostrar a mesma experiência a todos os participantes, escolha Todos os visitantes.

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Ao criar um público-alvo, você pode selecionar um local (mbox) e especificar os parâmetros para esse local. Em Parâmetros personalizados, selecione a mbox e especifique os parâmetros desejados.

   >[!NOTE]
   >
   >Os públicos-alvo são importados automaticamente em segundo plano quando você abre a lista de públicos-alvo e os públicos importados foram criados há mais de 10 minutos.

   Você pode clicar no ícone [!UICONTROL Editar] (três elipses verticais) que aparece e depois clicar em [!UICONTROL Remover público-alvo] para remover um público existente.
1. Clique em **[!UICONTROL Adicionar direcionamento de experiência]**.

   >[!NOTE]
   >
   >Se você estiver direcionando uma experiência para um público-alvo, selecione-o antes de incluir uma experiência. Aparece uma mensagem para lembrá-lo de escolher seu público-alvo.

1. (Opcional) Clique em **[!UICONTROL Adicionar]** e configure experiências direcionadas adicionais.

   ![](assets/xt_add_xt.png)

   Clique em **[!UICONTROL Continuar]ao concluir esta etapa.**
1. Especifique as [metas e configurações](../../../c-activities/t-experience-target/t-xt-create/xt-goals-and-settings.md#reference_B25389FD6F3A4989801E740364B089CC) da atividade.

   ![](assets/xt_settings.png)

1. Clique em **[!UICONTROL Salvar e fechar]**.
