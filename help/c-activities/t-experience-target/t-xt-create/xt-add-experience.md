---
description: O Visual Experience Composer (VEC) fornece uma interface visual para editar as experiências na página.
keywords: criar experiência, experiência criar, prioridade, público-alvo, experiência, visual experience composer
seo-description: O Adobe Target Visual Experience Composer (VEC) fornece uma interface visual para editar as experiências na página.
seo-title: Criar experiência
solution: Target
title: Criar experiência
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 5eb79fcd0407e0da841048bcd0a1b64393490fcf

---


# Criar experiência{#create-experience}

O Visual Experience Composer (VEC) fornece uma interface visual para editar as experiências na sua página em uma atividade de direcionamento de experiência (XT).

1. Selecione os elementos que você deseja alterar e faça as modificações desejadas.

   Ao [criar uma atividade XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), a etapa um do fluxo de trabalho guiado de três partes (Experiências) exibe a [!UICONTROL Experiência A padrão] com o [!UICONTROL público-] alvo Todos os visitantes.

   ![Público-alvo de todos os visitantes](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Todas as alterações feitas agora se aplicam à Experiência A. Em uma etapa abaixo, você clicará [!UICONTROL em Adicionar direcionamento de experiência] para criar experiências adicionais.

   À medida que passa o mouse sobre os elementos da página, eles são destacados. Qualquer elemento destacado pode ser alterado usando o VEC. Para obter uma lista de ações que podem ser executadas em um elemento para alterar a experiência, consulte [Opções do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   Se você criou uma mbox na página usando o Target Classic, (antes Test&amp;Target), essa mbox aparece como um elemento que mostra o seu nome e pode ser modificada como qualquer outro elemento.

1. Para criar experiências adicionais, clique **[!Aem Dd direcionamento de experiência]**.

   ![Adicionar link de direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   A caixa [!UICONTROL de] diálogo Escolher público-alvo é exibida. Para direcionar uma experiência a um público-alvo, você deve selecionar o público-alvo antes de adicionar uma experiência.

   A biblioteca de público-alvo contém públicos que foram definidos previamente, inclusive alguns comuns que são predefinidos como parte do Target. Você pode selecionar um público-alvo da biblioteca ou [criar um novo público-alvo](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271). Para mostrar a mesma experiência a todos os participantes, escolha Todos os visitantes.

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Ao criar um público-alvo, você pode selecionar um local (mbox) e especificar os parâmetros para esse local. Em Parâmetros personalizados, selecione a mbox e especifique os parâmetros desejados.

   >[!NOTE]
   >
   >Os públicos-alvo são importados automaticamente em segundo plano quando você abre a lista de públicos-alvo e os públicos importados foram criados há mais de 10 minutos.

1. Selecione um ou mais públicos-alvo para direcionar com a experiência e clique **[!UICONTROL em Concluído]**.

   ![Experiência B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   Você observará que a Experiência B agora é exibida na ilustração anterior e essa experiência é direcionada ao público-alvo dos visitantes dos EUA.

1. Selecione os elementos que deseja alterar para essa experiência e faça as alterações desejadas, uma explicada na Etapa 1 acima.

1. Repita as etapas anteriores para criar experiências direcionadas adicionais, conforme necessário.

1. Clique **[!UICONTROL em Avançar]** quando terminar de criar as experiências.

   O diagrama da atividade é exibido:

   ![Diagrama de definição de metas XT](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

1. (Condicional) Arraste e solte pares de público-alvo/experiência ao criar ou editar atividades XT para organizar os pares na ordem desejada.

   Os visitantes são avaliados para experiências em ordem, de cima para baixo.

   ![Mover experiências](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   O direcionamento de experiência assume que a ordem é importante. Se um visitante cair no primeiro par de público-alvo/experiência, a primeira experiência é entregue.

   Por exemplo, suponha que você não sabia que a ordem era importante ao criar uma atividade XT. Mais tarde você percebe durante os testes que visitantes que você pensava que deveriam se qualificar para as experiências B ou C estão se qualificando para a experiência A. Isso pode ocorrer pois os públicos-alvo não são mutualmente exclusivos e não estão na ordem correta (por exemplo, experiência A = Estados Unidos, experiência B = São Francisco e experiência C = Califórnia). Nesse cenários, todos usuários dos Estados Unidos se qualificam para a experiência A, mesmo se estiverem em São Francisco ou em outro lugar da Califórnia. Você pode reordenar os pares de público-alvo/experiência do mais restritivo para o menos restritivo (São Francisco &gt; Califórnia &gt; Estados Unidos) sem ter que recriar a atividade inteira.

## Renomear ou editar uma experiência

Você pode clicar no [!UICONTROL ícone Editar] (três elipses verticais) em uma experiência em uma atividade XT e escolher entre as seguintes opções, conforme necessário:

* Renomear
* Editar

![Opções Renomear e Editar](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Excluir uma experiência

Na página **[!UICONTROL Experiências]** (a primeira etapa do fluxo de trabalho guiado em três etapas), clique nas três elipses verticais &gt; **[!UICONTROL Excluir]**.

![Excluir experiência](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicar uma experiência

Você pode copiar uma experiência em uma atividade de Direcionamento de experiência (XT) para fazer pequenas alterações nela sem ter que recriar a experiência do zero.

Na página **[!UICONTROL Experiências]** (a primeira etapa no fluxo de trabalho guiado de três etapas), clique nos três elipses verticais &gt; **[!UICONTROL Duplicar]**.

![Experiência duplicada](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vídeo de treinamento: uso do Visual Experience Composer

Este vídeo fornece informações sobre o uso das opções do Visual Experience Composer.

* Alterar o conteúdo de uma página
* Alterar o layout de uma página

>[!VIDEO](https://video.tv.adobe.com/v/17399?captions=por_br)