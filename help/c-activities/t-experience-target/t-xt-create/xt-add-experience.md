---
keywords: create experience;experience create;priority;audience;experience;visual experience composer
description: O Visual Experience Composer (VEC) do Adobe Target fornece uma interface visual para editar as experiências em sua página da atividade de Direcionamento de experiência (XT).
title: Criar experiência
feature: null
topic: Advanced,Standard,Classic
uuid: ce559c3c-5a16-46b8-b2a7-df696626c7c0
translation-type: tm+mt
source-git-commit: a51addc6155f2681f01f2329b25d72327de36701
workflow-type: tm+mt
source-wordcount: '962'
ht-degree: 93%

---


# Criar experiência{#create-experience}

O [!UICONTROL Visual Experience Composer] (VEC) do fornece uma interface visual para editar as experiências em sua página da atividade de [!UICONTROL Direcionamento de experiência] (XT).

1. Selecione os elementos que você deseja alterar e faça as modificações desejadas.

   Ao [criar uma atividade de XT](/help/c-activities/t-experience-target/t-xt-create/xt-create.md), a etapa um do fluxo de trabalho guiado de três etapas ([!UICONTROL Experiências]) exibe a [!UICONTROL Experiência A] padrão com o público-alvo [!UICONTROL Todos os visitantes].

   ![Público-alvo de todos os visitantes](/help/c-activities/t-experience-target/t-xt-create/assets/all-visitors.png)

   Todas as alterações feitas agora se aplicam à Experiência A. Em uma etapa abaixo, você clicará em **[!UICONTROL Adicionar Direcionamento de experiência]** para criar experiências adicionais.

   À medida que passa o mouse sobre os elementos da página, eles são destacados. Qualquer elemento destacado pode ser alterado usando o VEC. Para ver uma lista de ações que podem ser executadas em um elemento para alterar a experiência, consulte [Opções do Visual Experience Composer](/help/c-experiences/c-visual-experience-composer/viztarget-options.md).

   If you created a [!DNL Target] request on the page using [!DNL Target Classic], that [!DNL Target] request appears as an element that shows the request name, and can be modified like any other element.

   >[!NOTE]
   >
   >Por padrão, o VEC não permite alterações a elementos que contenham JavaScript, como banners giratórios. Você pode selecionar a desativação do JavaScript para alterar esses elementos usando o VEC.

1. Para criar experiências adicionais, clique em **[!UICONTROL Adicionar direcionamento de experiência]**.

   ![Link Adicionar Direcionamento de experiência](/help/c-activities/t-experience-target/t-xt-create/assets/add-experience-targeting.png)

   A caixa de diálogo [!UICONTROL Escolher público-alvo] é exibida. Para direcionar uma experiência para um público-alvo, selecione-o antes de incluir uma experiência.

   A biblioteca de público-alvo contém públicos que foram definidos previamente, inclusive alguns comuns que são predefinidos como parte do [!DNL Target]. Você pode selecionar um público-alvo da biblioteca ou [criar um novo público-alvo](../../../c-target/c-audiences/audiences.md#concept_65BE870D290E412D8BBF557EEA67C271).

   >[!NOTE]
   >
   >Além de selecionar um público-alvo existente, você pode combinar vários deles para criar públicos-alvo combinados ad hoc em vez de criar um novo. Para obter mais informações, consulte [Combinar vários públicos-alvo](../../../c-target/combining-multiple-audiences.md#concept_A7386F1EA4394BD2AB72399C225981E5).

   Ao criar uma audiência, você pode selecionar um local e especificar parâmetros para esse local. Under [!UICONTROL Custom] (Create Audience > Add Rule > Custom), select the location, then specify the desired parameters.

   >[!NOTE]
   >
   >Os públicos-alvo são importados automaticamente em segundo plano quando você abre a lista de públicos-alvo e os públicos importados foram criados há mais de 10 minutos.

1. Selecione um ou mais públicos-alvo para direcionar com a experiência e clique em **[!UICONTROL Concluído]**.

   ![Experiência B](/help/c-activities/t-experience-target/t-xt-create/assets/experience-b.png)

   Você observará que a Experiência B agora é exibida na ilustração anterior e essa experiência é direcionada ao público-alvo de visitantes dos EUA.

1. Selecione os elementos que deseja alterar para essa experiência e faça as alterações, conforme explicado na Etapa 1 acima.

1. Repita as etapas anteriores para criar experiências direcionadas adicionais, conforme necessário.

1. Clique em **[!UICONTROL Avançar]** ao concluir a criação das experiências.

   O diagrama da atividade é exibido:

   ![Diagrama de Direcionamento XT](/help/c-activities/t-experience-target/t-xt-create/assets/xt_diagram-new.png)

   >[!NOTE]
   >
   >Se você apresentar uma imagem de uma fonte diferente da sua página principal (como uma imagem hospedada em `akamai.net` e disponibilizada em `adobe.com`), ela não será exibida na miniatura da página mostrada no diagrama de fluxo.

1. (Condicional) Arraste e solte pares de público-alvo/experiência ao criar ou editar atividades de XT para reorganizar os pares na ordem desejada.

   Os visitantes são avaliados quanto às experiências em ordem, de cima para baixo.

   ![Mover experiências](/help/c-activities/t-experience-target/t-xt-create/assets/move_experiences-new.png)

   [!UICONTROL O direcionamento de experiência assume que a ordem é importante. ] Se um visitante cair no primeiro par de público-alvo/experiência, a primeira experiência é entregue.

   Por exemplo, suponha que você não sabia que a ordem era importante ao criar uma atividade XT. Mais tarde você percebe durante os testes que visitantes que você pensava que deveriam se qualificar para as experiências B ou C estão se qualificando para a experiência A. Isso pode ocorrer pois os públicos-alvo não são mutualmente exclusivos e não estão na ordem correta (por exemplo, experiência A = Estados Unidos, experiência B = São Francisco e experiência C = Califórnia). Nesse cenários, todos usuários dos Estados Unidos se qualificam para a experiência A, mesmo se estiverem em São Francisco ou em outro lugar da Califórnia. Você pode reordenar os pares de público-alvo/experiência do mais restritivo para o menos restritivo (São Francisco > Califórnia > Estados Unidos) sem ter que recriar a atividade inteira.

   Se você tiver um público-alvo de [!UICONTROL Todos os visitantes], certifique-se de que não seja o primeiro no diagrama. Uma experiência direcionada para &quot;Todos os visitantes&quot; pode ser usada como a última experiência na atividade de direcionamento de experiência para &quot;capturar&quot; todos os visitantes que não se enquadram em nenhuma outra experiência.

## Renomear ou editar uma experiência

Você pode clicar no ícone [!UICONTROL Editar] (três elipses verticais) em uma experiência de uma atividade de XT e escolher as seguintes opções, conforme necessário:

* Renomear
* Editar

![Opções Renomear e Editar](/help/c-activities/t-experience-target/t-xt-create/assets/experience_edit-new.png)

## Excluir uma experiência

Na página **[!UICONTROL Experiências]** (a primeira etapa no fluxo de trabalho guiado de três etapas), clique nos três elipses verticais > **[!UICONTROL Excluir]**.

![Excluir experiência](/help/c-activities/t-experience-target/t-xt-create/assets/delete-experience.png)

## Duplicar uma experiência

Você pode copiar uma experiência em uma atividade de XT para fazer pequenas alterações nela sem ter que recriar a experiência do zero.

Na página **[!UICONTROL Experiências]** (a primeira etapa no fluxo de trabalho guiado de três etapas), clique nos três elipses verticais > **[!UICONTROL Duplicar]**.

![Experiência duplicada](/help/c-activities/t-experience-target/t-xt-create/assets/duplicate_experience-new.png)

## Vídeos de treinamento:

Os vídeos a seguir contêm mais informações sobre os conceitos discutidos neste artigo.

### De testes A/B para direcionamento de experiência

Este vídeo descreve como elevar os testes A/B para o próximo nível com o direcionamento de experiência (XT).

* Descreve o fluxo de trabalho guiado de três etapas para configurar uma atividade XT
* Descreve como entregar conteúdo específico de localidade para públicos -alvo localizados em áreas geográficas diferentes
* Descreve como reorganizar experiências para garantir que o conteúdo correto seja entregue ao público-alvo certo

>[!VIDEO](https://video.tv.adobe.com/v/22418/)

### Tipos de atividades (9:03)

Este vídeo explica os tipos de atividade disponíveis no Target Standard/Premium. Direcionamento de experiência começa a ser examinado aos 5:15.

* Descreva os tipos de atividade incluídos no [!DNL Adobe Target]
* Selecione o tipo de atividade apropriado para atingir suas metas
* Descreva o fluxo de trabalho guiado em três etapas que se aplica a todos os tipos de atividade

>[!VIDEO](https://video.tv.adobe.com/v/17386)

### Uso do Visual Experience Composer

Este vídeo fornece informações sobre o uso das opções do Visual Experience Composer.

* Alterar o conteúdo de uma página
* Alterar o layout de uma página

>[!VIDEO](https://video.tv.adobe.com/v/17399)