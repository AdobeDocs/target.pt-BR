---
description: O Experience Composer oferece uma interface visual para editar as experiências na página.
keywords: criar experiência, experiência criar, prioridade, público-alvo, experiência, visual experience composer
seo-description: O Experience Composer oferece uma interface visual para editar as experiências na página.
seo-title: Criar experiência
solution: Target
title: Criar experiência
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: 9b8f39240cbbd7a494d74dc0016ed666a58fd870

---


# Criar experiência{#create-experience}

O Experience Composer oferece uma interface visual para editar as experiências na página.

Para obter mais detalhes sobre experiências, consulte [Experiências](../../../c-experiences/experiences.md#concept_A2E10F6AFB3D4AEAB6951EE14688848D).

1. Clique em **[!UICONTROL Adicionar experiência]**.

   >[!NOTE]
   >
   >Se você estiver direcionando uma experiência para um público-alvo, selecione-o antes de incluir uma experiência. Aparece uma mensagem para lembrá-lo de escolher seu público-alvo.

1. Quando solicitado, insira o URL da atividade. Digite o URL completo (incluindo `https://`) e clique em **[!UICONTROL Continuar]**.

   O Experience Composer (consulte [Experiências](../../../c-experiences/experiences.md#concept_1D011219034B492BB03C08B3BB80E3F0)) abre a página que está especificada nas Preferências da conta. Para exibir uma página diferente, clique no ícone de Globo e insira o URL na caixa Selecionar URL no Experience Composer e clique em **[!UICONTROL Continuar]**. Caso tenha inserido um URL para um site que não inclui o código JavaScript do Target Standard, você não pode selecionar elementos da página.

   Por padrão, o Visual Experience Composer não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode desativar o JavaScript se deseja poder alterar esses elementos usando o Visual Experience Composer.

   >[!NOTE]
   >
   >Se você alterar o URL após fazer alterações de uma ou mais experiências em uma página, a experiência será redefinida usando a nova página, e as alterações que você fez são perdidas.

1. Selecione os elementos que você deseja alterar e faça as modificações desejadas.

   À medida que passa o mouse sobre os elementos da página, eles são destacados. Qualquer elemento destacado pode ser alterado usando o Experience Composer.

   Se você criou uma mbox na página usando o Target Classic, (antes Test&amp;Target), essa mbox aparece como um elemento que mostra o seu nome e pode ser modificada como qualquer outro elemento.

   Para ver uma lista de ações que podem ser executadas em um elemento de uma página exibida para alterar a experiência, consulte [Opções do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   >[!NOTE]
   >
   >Se você apresentar uma imagem de uma fonte diferente da sua página principal (como uma imagem hospedada em akamai.net e oferecida em dell.com), ela não será exibida na miniatura da página mostrada no diagrama de fluxo.

1. Clique no botão Marca de seleção quando tiver terminado de criar a experiência.

   O diagrama da atividade é exibido:

   ![](assets/xt_diagram.png)

   Se uma experiência incluir conteúdo entre domínios, a miniatura poderá não ser exibida corretamente e será substituída por um ícone.
1. Crie experiências adicionais, conforme desejar.

   >[!NOTE]
   >
   >Você pode arrastar e soltar pares de público-alvo/experiência enquanto cria ou edita atividades de XT para reorganizar os pares na ordem desejada. Os visitantes serão avaliados quanto às experiências em ordem, de cima para baixo.

   ![](assets/move_experiences.jpg)

   O direcionamento de experiência assume que a ordem é importante. Se um visitante cair no primeiro par de público-alvo/experiência, a primeira experiência é entregue.

   Por exemplo, suponha que você não sabia que a ordem era importante ao criar uma atividade XT. Mais tarde você percebe durante os testes que visitantes que você pensava que deveriam se qualificar para as experiências B ou C estão se qualificando para a experiência A. Isso pode ocorrer pois os públicos-alvo não são mutualmente exclusivos e não estão na ordem correta (por exemplo, experiência A = Estados Unidos, experiência B = São Francisco e experiência C = Califórnia). Nesse cenários, todos usuários dos Estados Unidos se qualificam para a experiência A, mesmo se estiverem em São Francisco ou em outro lugar da Califórnia. Você pode reordenar os pares de público-alvo/experiência do mais restritivo para o menos restritivo (São Francisco &gt; Califórnia &gt; Estados Unidos) sem ter que recriar a atividade inteira.

## Renomear, editar ou excluir uma experiência

Você pode clicar no ícone Editar (três elipses verticais) em uma experiência em uma atividade de Teste A/B ou de Direcionamento de experiência (XT) e escolher as seguintes opções, conforme necessário:

* Renomear
* Editar
* Excluir

![](assets/experience_edit.png)

Clique em **[!UICONTROL Continuar]ao concluir esta etapa.**

## Duplicar uma experiência

Você pode copiar uma experiência em uma atividade de Direcionamento de experiência (XT) para fazer pequenas alterações nela sem ter que recriar a experiência do zero.

Na página **[!UICONTROL Experiências]** (a primeira etapa no fluxo de trabalho guiado de três etapas), clique nos três elipses verticais &gt; **[!UICONTROL Duplicar]**.

![](assets/duplicate_experience.png)

## Vídeo de treinamento: uso do Visual Experience Composer

Este vídeo fornece informações sobre o uso das opções do Visual Experience Composer.

* Alterar o conteúdo de uma página
* Alterar o layout de uma página

>[!VIDEO](https://video.tv.adobe.com/v/17399)