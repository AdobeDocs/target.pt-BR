---
description: O Visual Experience Composer (VEC) fornece uma interface visual para editar as experiências na sua página em uma atividade de direcionamento de experiência (XT).
keywords: criar experiência, experiência criar, prioridade, público-alvo, experiência, visual experience composer
seo-description: O Adobe Target Visual Experience Composer (VEC) fornece uma interface visual para editar as experiências na sua página em uma atividade de direcionamento de experiência (XT).
seo-title: Criar experiência
solution: Target
title: Criar experiência
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 8bd57fb3bb467d8dae50535b6c367995f2acabac

---


# Create experience{#create-experience}

O Visual Experience Composer (VEC) fornece uma interface visual para editar as experiências na sua página em uma atividade de direcionamento de experiência (XT).

1. Selecione os elementos que você deseja alterar e faça as modificações desejadas.

   While [creating an XT activity](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), step one of the three-part guided workflow (Experiences) displays the default [!UICONTROL Experience A] with an [!UICONTROL All Visitors] audience.

   ![Público-alvo de todos os visitantes](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Any changes you make now apply to Experience A. In a step below, you'll click **[!UICONTROL Add Experience Targeting]** to create additional experiences.

   À medida que passa o mouse sobre os elementos da página, eles são destacados. Qualquer elemento destacado pode ser alterado usando o VEC. For a list of actions that can be performed on an element to change the experience, see [Visual Experience Composer Options](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Se você criou uma mbox na página usando o Target Classic, (antes Test&amp;Target), essa mbox aparece como um elemento que mostra o seu nome e pode ser modificada como qualquer outro elemento.

   >[!NOTE]
   >
   >Por padrão, o Visual Experience Composer não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar o javascript caso deseje poder alterar esses elementos usando o VEC.

1. To create additional experiences, click **[!Add Experience Targeting]**.

   ![Adicionar link de direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   The [!UICONTROL Choose Audience] dialog box displays. Para direcionar uma experiência a um público-alvo, você deve selecionar o público-alvo antes de adicionar uma experiência.

   A biblioteca de público-alvo contém públicos que foram definidos previamente, inclusive alguns comuns que são predefinidos como parte do Target. Você pode selecionar um público-alvo da biblioteca ou [criar um novo público-alvo](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Ao criar um público-alvo, você pode selecionar um local (mbox) e especificar os parâmetros para esse local. Under [!UICONTROL Custom] (Create Audience &gt; Add Rule &gt; Custom), select the mbox, then specify the desired parameters.

   >[!NOTE]
   >
   >Os públicos-alvo são importados automaticamente em segundo plano quando você abre a lista de públicos-alvo e os públicos importados foram criados há mais de 10 minutos.

1. Select one or more audiences to target with the experience, then click **[!UICONTROL Done]**.

   ![Experiência B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   Você observará que a Experiência B agora é exibida na ilustração anterior e essa experiência é direcionada ao público-alvo dos visitantes dos EUA.

1. Selecione os elementos que deseja alterar para essa experiência e faça as alterações desejadas, uma explicada na Etapa 1 acima.

1. Repita as etapas anteriores para criar experiências direcionadas adicionais, conforme necessário.

1. Click **[!UICONTROL Next]** when you are finished designing your experiences.

   O diagrama da atividade é exibido:

   ![Diagrama de definição de metas XT](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Se você entregar uma imagem de uma fonte diferente da sua página principal (como uma imagem hospedada no akamai. net e entregue em adobe.com), essa imagem não será exibida na miniatura da página mostrada no diagrama de fluxo.

1. (Condicional) Arraste e solte pares de público-alvo/experiência ao criar ou editar atividades XT para organizar os pares na ordem desejada.

   Os visitantes são avaliados para experiências em ordem, de cima para baixo.

   ![Mover experiências](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   O direcionamento de experiência assume que a ordem é importante. Se um visitante cair no primeiro par de público-alvo/experiência, a primeira experiência é entregue.

   Por exemplo, suponha que você não sabia que a ordem era importante ao criar uma atividade XT. Mais tarde você percebe durante os testes que visitantes que você pensava que deveriam se qualificar para as experiências B ou C estão se qualificando para a experiência A. Isso pode ocorrer pois os públicos-alvo não são mutualmente exclusivos e não estão na ordem correta (por exemplo, experiência A = Estados Unidos, experiência B = São Francisco e experiência C = Califórnia). Nesse cenários, todos usuários dos Estados Unidos se qualificam para a experiência A, mesmo se estiverem em São Francisco ou em outro lugar da Califórnia. Você pode reordenar os pares de público-alvo/experiência do mais restritivo para o menos restritivo (São Francisco &gt; Califórnia &gt; Estados Unidos) sem ter que recriar a atividade inteira.

   If you have an [!UICONTROL All Visitors] audience, ensure that it is not the first audience in the diagram. Uma experiência direcionada para "Todos os visitantes" pode ser usada como a última experiência na atividade de direcionamento de experiência para "capturar" todos os visitantes que não se enquadram em nenhuma outra experiência.

## Renomear ou editar uma experiência

You can click the [!UICONTROL Edit] icon (three vertical ellipses) on an experience in an XT activity and choose from the following options, as necessary:

* Renomear
* Editar

![Opções Renomear e Editar](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Excluir uma experiência

On the **[!UICONTROL Experiences]** page (the first step in the three-step guided workflow), click the three vertical ellipses &gt; **[!UICONTROL Delete]**.

![Excluir experiência](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicar uma experiência

Você pode copiar uma experiência em uma atividade de Direcionamento de experiência (XT) para fazer pequenas alterações nela sem ter que recriar a experiência do zero.

Na página **[!UICONTROL Experiências]** (a primeira etapa no fluxo de trabalho guiado de três etapas), clique nos três elipses verticais &gt; **[!UICONTROL Duplicar]**.

![Experiência duplicada](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### De testes A/B para direcionamento de experiência

Este vídeo descreve como elevar os testes A/B para o próximo nível com o direcionamento de experiência (XT).

* Descreve o fluxo de trabalho guiado de três etapas para configurar uma atividade XT
* Descreve como entregar conteúdo específico de localidade para públicos -alvo localizados em áreas geográficas diferentes
* Descreve como reorganizar experiências para garantir que o conteúdo correto seja entregue ao público-alvo certo

>[!VIDEO](https://video.tv.adobe.com/v/22418/?captions=por_br)

### Tipos de atividades (9:03)

Este vídeo explica os tipos de atividade disponíveis no Target Standard/Premium. Direcionamento de experiência começa a ser examinado aos 5:15

* Descreva os tipos de atividades incluídas em [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386?captions=por_br)

### Uso do Visual Experience Composer

Este vídeo fornece informações sobre o uso das opções do Visual Experience Composer.

* Alterar o conteúdo de uma página
* Alterar o layout de uma página

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=por_br)